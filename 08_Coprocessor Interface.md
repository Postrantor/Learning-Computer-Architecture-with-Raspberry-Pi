# Underflow and Denormal Values

Problems arise in computer maths when software has only a limited number of bits to express very, very large or very, very small values. When a value is too large to express in 80 bits (the largest common real-number format) that value "overflows" the number meant to receive it, and an error is generated. Less obviously, the reverse is possible: a value so small (that is, so close to 0) that it cannot be accurately expressed in 80 bits. This is called _underflow_. A special kind of number called a _denormal_ is used to express values resulting from underflows at lower precision, allowing them to be expressed in 80 bits, and used in further calculations without generating an error.

> 当软件只有有限的位数来表示非常、非常大或非常、非常小的值时，计算机数学就会出现问题。当一个值太大，无法用 80 位(最大的常用实数格式)表示时，该值会 "溢出" 接收该值的数字，并生成错误。不太明显的是，相反的情况是可能的：一个非常小的值(也就是说，非常接近 0)，以至于不能用 80 位来精确地表示。这称为 *underflow*。一种称为 *denormal* 的特殊数字用于以较低的精度表示下溢产生的值，允许它们以 80 位表示，并用于进一步的计算而不会产生错误。

Later on, another reason for using coprocessors arose when customisable CPU architectures like those offered by ARM became popular. If the coprocessor is relatively independent of the CPU, it can be included or excluded from custom designs as needed.

> 后来，当 ARM 提供的可定制 CPU 架构变得流行时，使用协处理器的另一个原因出现了。如果协处理器相对独立于 CPU，则可以根据需要将其纳入或排除在定制设计中。

### The ARM Coprocessor Interface

The ARM family of CPUs supports several different types of closely coupled coprocessors, including floating point, SIMD, and system control and cache maintenance. Modern transistor budgets have allowed all of these to be included on the same silicon with the CPU, sometimes as optional elements of custom designs. The ARM11 CPUs have a generalised coprocessor interface allowing as many as 16 coprocessors to cooperate with the CPU. The CPU uses a dedicated set of coprocessor interface instructions to communicate with coprocessors. Coprocessor instructions are compiled or assembled into the stored executable program file on disk or (in the Raspberry Pi) the SD card. They are part of the ordinary ARM instruction stream coming in from memory. They aren’t set apart in a separate memory area or specially treated by the ARM core.

> **ARM 系列 CPU 支持几种不同类型的紧密耦合协处理器，包括浮点、SIMD、系统控制和缓存维护。**现代晶体管预算允许所有这些都包含在与 CPU 相同的硅上，有时作为定制设计的可选元素。ARM11 CPU 具有通用协处理器接口，允许多达 16 个协处理器与 CPU 协作。CPU 使用一组专用的协处理器接口指令与协处理器通信。协处理器指令被编译或组装到磁盘或(在复盆子 Pi 中)SD 卡上存储的可执行程序文件中。它们是来自内存的普通 ARM 指令流的一部分。它们不会被分开放置在单独的内存区域中，也不会被 ARM 内核专门处理。

Each coprocessor present in an ARM system has a unique 4-bit ID code. Coprocessor instructions contain a field for the ID code of the coprocessor on which they will execute. If the CPU core fetches a coprocessor instruction that doesn’t match the ID code of any existing coprocessor, it triggers an undefined instruction exception. (More on this shortly.)

> ARM 系统中的每个协处理器都有一个唯一的 4 位 ID 代码。协处理器指令包含一个字段，用于它们将在其上执行的协处理器的 ID 代码。如果 CPU 内核获取的协处理器指令与任何现有协处理器的 ID 代码不匹配，则会触发未定义的指令异常。(稍后将详细介绍。)

One of the primary goals of the ARM coprocessor interface is not to slow down the CPU core. Beyond checking to see if a coprocessor instruction is coded for an existing coprocessor, the core does not spend time sorting out coprocessor instructions within its own pipeline. The core sends all the instructions it fetches from memory directly to all coprocessors. The coprocessor decodes all incoming instructions, which include both ordinary ARM instructions as well as coprocessor instructions. During the decoding stage, the coprocessor rejects any instructions that are not recognised as its own. This includes both ARM instructions and instructions coded for other coprocessors. The coprocessor recognises its own instructions, and adds only those to its internal execution pipeline. The coprocessor then sends a signal back to the core indicating that it has accepted an instruction.

> ARM 协处理器接口的主要目标之一是不降低 CPU 内核的速度。除了检查协处理器指令是否为现有协处理器编码外，内核不需要花费时间在自己的管道中整理协处理器指令。内核将从内存中获取的所有指令直接发送给所有协处理器。协处理器解码所有传入的指令，包括普通 ARM 指令和协处理器指令。在解码阶段，协处理器拒绝任何未被识别为自己的指令。这包括 ARM 指令和为其他协处理器编码的指令。协处理器识别自己的指令，并只将这些指令添加到内部执行管道中。然后，协处理器向内核发送一个信号，表明它已接受指令。

The first-generation Raspberry Pi’s ARM1176JZF-S CPU includes two coprocessors—the System Control Coprocessor and the Vector Floating Point (VFP) coprocessor—which are described in the next sections.

> 第一代 Raspberry Pi 的 ARM1176JZF-s CPU 包括两个协处理器：系统控制协处理器和矢量浮点(VFP)协处理器，将在下一节中介绍。

### The System Control Coprocessor

The ARM11 System Control Coprocessor exposes a large suite of registers that are used to configure and control the operation of ARM core mechanisms like cache, direct memory access (DMA), the memory management unit (MMU), the TrustZone security system, exception handling and system performance, among others. Where tightly coupled memory (TCM) is present, it is managed by the system control coprocessor. (TCM is optional, and is not implemented in the Raspberry Pi’s BCM2835 silicon.)

> ARM11 系统控制协处理器公开了一大套寄存器，用于配置和控制 ARM 核心机制的操作，如缓存、直接内存访问(DMA)、内存管理单元(MMU)、TrustZone 安全系统、异常处理和系统性能等。如果存在紧密耦合存储器(TCM)，则由系统控制协处理器管理。(TCM 是可选的，不在树莓派的 BCM2835 硅中实现。)

Two ARM instructions handle communication with the system control coprocessor: the `MCR` instruction (from "move from coprocessor to register" ) is used to read data from a coprocessor register; and the `MRC` instruction (from "move from register to coprocessor" ) is used to write data from the core to a coprocessor register. `MCR` and `MRC` instructions can be used to communication with any coprocessor, but they represent the sole means of access to the system control coprocessor as it does not define any data processing operations of its own.

> 两条 ARM 指令处理与系统控制协处理器的通信： "MCR" 指令(来自 "从协处理器移动到寄存器" )用于从协处理器寄存器读取数据；"MRC" 指令(从 "从寄存器到协处理器" )用于将数据从内核写入协处理器寄存器 `MCR" 和 "MRC" 指令可用于与任何协处理器通信，但它们是访问系统控制协处理器的唯一方式，因为它不定义自己的任何数据处理操作。

### The Vector Floating Point (VFP) Coprocessor

There are excellent reasons for gathering _floating point operations_ (that is, computer mathematics operating on fractional values) into a dedicated coprocessor. Floating point maths isn’t used much in a large number of software categories, but scientific and engineering applications, and games, use it a lot. CPUs designed for certain kinds of embedded systems work do not necessarily need a full maths coprocessor. Floating point operations, when required, can be implemented in library subroutines. Furthermore, floating point maths must be able to express values that have many significant figures, which requires registers larger than 32 bits to express.

> 将浮点运算(即对分数进行运算的计算机数学)收集到专用协处理器中有很好的理由。浮点数学在很多软件类别中并不常用，但科学和工程应用程序以及游戏都大量使用它。为某些类型的嵌入式系统设计的 CPU 不一定需要完整的数学协处理器。需要时，可以在库子程序中实现浮点运算。此外，浮点数学必须能够表示具有许多有效数字的值，这需要大于 32 位的寄存器来表示。

The ARM11 core includes an extensive floating point maths coprocessor, the VFP11 Vector Floating Point Coprocessor. As with the ARM core itself, there is an ARM architecture for floating point machine instructions, which has evolved over time and has its own version numbering. VFP11 implements the VFPv2 instruction set architecture, which in turn implements a large subset of the IEEE 754 standard for binary floating point arithmetic. VFP11 is accessed by the ARM11 core through the ARM coprocessor interface, using two dedicated coprocessor numbers: 10 for single-precision instructions and 11 for double-precision instructions. Single precision as used in an ARM11 context means values represented in 32 bits. Double-precision values are represented in 64 bits.

> ARM11 内核包括一个扩展的浮点数学协处理器 VFP11 矢量浮点协处理器。与 ARM 内核本身一样，有一种用于浮点机器指令的 ARM 架构，它随着时间的推移而演变，并有自己的版本编号。VFP11 实现了 VFPv2 指令集架构，进而实现了二进制浮点运算的 IEEE 754 标准的一个子集。ARM11 内核通过 ARM 协处理器接口访问 VFP11，使用两个专用协处理器编号：10 用于单精度指令，11 用于双精度指令。ARM11 上下文中使用的单精度是指以 32 位表示的值。双精度值以 64 位表示。

The term _vector_ as used here denotes a one-dimensional array (that is, a series) of same-type data items. (There is more on arrays and other data structures in [Chapter 5](#08_9781119183938-ch05.xhtml).) This may sound familiar: vector maths is what SIMD instructions were designed to perform. The vector-processing features of VFP are relatively slow and limited and, starting with the Cortex group of ARM architectures, VFP vector maths has been deprecated in favour of the more powerful NEON SIMD coprocessor. (More on NEON later on, in connection with ARM Cortex.)

> 这里使用的术语 *vector* 表示相同类型数据项的一维数组(即一系列)。(在[第 5 章](#08_9781119183938-ch05.xhtml)中有更多关于数组和其他数据结构的内容。)这听起来可能很熟悉：向量数学是 SIMD 指令设计用来执行的。VFP 的矢量处理功能相对较慢且有限，从 ARM 架构的 Cortex 组开始，VFP 矢量数学已被弃用，取而代之的是更强大的 NEON SIMD 协处理器。(稍后关于 NEON 的更多信息，请参阅 ARM Cortex。)

The VFP architecture provides single- and double-precision add, subtract, multiply, divide and square root operations, plus multiply-and-accumulate. This last is a specialised operation often used in digital signal processing (DSP). Given the importance of DSP in media software, optimised instructions for use in DSP work are a big win, performance-wise. Instructions are also provided for conversions between numeric types, and load/store instructions for moving floating point data directly between memory and VFP coprocessor registers. The VFPv2 architecture provides four banks of eight 32-bit registers. Two consecutive registers may be used to hold 64-bit double-precision values.

> VFP 架构提供单精度和双精度加法、减法、乘法、除法和平方根运算，以及乘法和累加。最后一种是数字信号处理(DSP)中经常使用的专用操作。考虑到 DSP 在媒体软件中的重要性，DSP 工作中使用的优化指令在性能方面是一个巨大的胜利。还提供了用于数字类型之间转换的指令，以及用于在存储器和 VFP 协处理器寄存器之间直接移动浮点数据的加载/存储指令。VFPv2 体系结构提供四组八个 32 位寄存器。可以使用两个连续的寄存器来保存 64 位双精度值。

The IEEE 754 standard makes recommendations on how computer logic should implement transcendental functions (the exponential function, logarithms and trigonometry) but with VFPv2 these are not implemented in machine instructions and must be implemented as subroutines in libraries.

> IEEE 754 标准对计算机逻辑应如何实现超越函数(指数函数、对数和三角函数)提出了建议，但对于 VFPv2，这些函数不能在机器指令中实现，必须在库中作为子程序实现。

### Emulating Coprocessors

Nearly all architectures that support coprocessors provide a way to handle coprocessor instructions when the coprocessor in question isn’t present in a system. This is called _instruction emulation_. On the ARM processors, it’s handled by way of the undefined instruction exception.

> 几乎所有支持协处理器的体系结构都提供了一种在系统中不存在相关协处理器时处理协处理器指令的方法。这称为*指令仿真*。在 ARM 处理器上，它是通过未定义的指令异常来处理的。

Instruction emulation requires one subroutine in memory to perform the work of each emulated instruction. The core checks each coprocessor instruction that it fetches to see if the required coprocessor exists on the system. If not, the core triggers an undefined instruction exception. The exception handler contains a jump table with branches to emulation subroutines for all instructions coded for the missing coprocessor. The exception handler inspects the coprocessor instruction that triggered the exception, and branches to the appropriate emulation subroutine. The subroutine does the work that would ordinarily be done inside the coprocessor, and then returns control to the next instruction in the core pipeline.

> 指令仿真需要内存中的一个子例程来执行每个仿真指令的工作。内核检查它获取的每个协处理器指令，以查看系统上是否存在所需的协处理器。如果没有，内核将触发未定义的指令异常。异常处理程序包含一个跳转表，其中包含为缺失协处理器编码的所有指令的仿真子例程的分支。异常处理程序检查触发异常的协处理器指令，并分支到相应的仿真子例程。子例程执行通常在协处理器内部完成的工作，然后将控制权返回到核心流水线中的下一条指令。

Each instruction coded for a non-existent coprocessor triggers a separate exception into an emulation subroutine. As you might imagine, emulating a single-cycle instruction with a subroutine that might require dozens or hundreds of cycles is very slow. However, it’s certainly better than halting the current program.

> 为不存在的协处理器编码的每条指令都会在仿真子例程中触发一个单独的异常。正如您可能想象的那样，用可能需要数十或数百个周期的子程序模拟单周期指令是非常缓慢的。然而，这肯定比停止目前的计划要好。

## ARM Cortex

The ARM11 family was followed by a new group of ARM microarchitectures in 2006: Cortex. Unlike ARM11, which emcompassed only four cores based on the same microarchitecture, the Cortex brand encompasses many different core designs, each optimised for a particular application domain and area/performance/energy trade-off point. The Cortex processors fall into several categories called _profiles_, denoting broad emphasis:

> 在 ARM11 家族之后，2006 年又出现了一组新的 ARM 微体系结构：Cortex。与 ARM11 不同，Cortex 品牌仅基于同一微体系结构对四个内核进行了 EMC 比较，它包含许多不同的内核设计，每一个都针对特定的应用领域和面积/性能/能量平衡点进行了优化。Cortex 处理器分为几个类别，称为 *profiles*，表示广泛强调：

- **Cortex-R:** Cores optimised for real-time embedded system service in automotive and industrial control devices
- **Cortex-M:** Small, inexpensive, low-power cores optimised for use in microcontroller applications
- **Cortex-A:** Cores optimised for use in devices like smartphones, tablets, e-book readers, digital TV appliances and other applications where a full operating system is necessary
- **SecureCore:** Cores optimised for use in high-security financial and communication devices like ATMs, mass transit ticketing, pay-per-view media controllers, e-voting and ID systems

> -**Cortex-R:**针对汽车和工业控制设备中的实时嵌入式系统服务而优化的内核-**Cortex-M:**针对微控制器应用程序而优化的小型、廉价、低功耗内核-**Cortex-A:**针对智能手机、平板电脑、电子书阅读器、，数字电视设备和其他需要完整操作系统的应用程序-**SecureCore:**核心经过优化，可用于高安全性的金融和通信设备，如 ATM、公共交通票务、按次付费媒体控制器、电子投票和 ID 系统

For space reasons, we’re confining this discussion to the A profile and sticking to the high points in the evolution of ARM CPUs.

> 由于篇幅的原因，我们将此讨论局限于 A 配置文件，并坚持 ARM CPU 发展的重点。

### Multiple-Issue and Out-Of-Order Execution

The ARM11 core is a single-issue processor, which means that it loads one machine instruction into the pipeline at a time. The Cortex A8 introduced superscalar execution to ARM, and issues two instructions into its pipeline at once. This is often called dual issue. (See the "[Superscalar Execution](#07_9781119183938-ch04.xhtml#c04-sec-0017)" section earlier in this chapter.) The Cortex A9 core can issue two instructions at once, and the A15 three.

> ARM11 内核是一个单问题处理器，这意味着它一次将一条机器指令加载到流水线中。Cortex A8 将超标量执行引入 ARM，并同时向其流水线发出两条指令。这通常被称为双重问题。(请参阅本章前面的 "[超标量执行](#07_9781119183938-ch04.xhtml#c04-sec-0017)" 部分。)Cortex A9 内核可以同时发出两条指令，A15 内核可以发出三条指令。

The Cortex A9 adds yet another performance trick new to ARM: out-of-order execution (OOE). In simple terms, OOE allows the CPU to determine when a machine instruction has to wait for its operands to be available and sets it aside until it’s ready to be issued to the execution units. Other instructions, taken from later in the instruction stream, can be issued during this time, provided their operands are available. When the operands of an instruction waiting in the dispatch queue arrive, the instruction is then issued to the pipeline.

> Cortex A9 为 ARM 增加了另一个新的性能技巧：无序执行(OOE)。简单来说，OOE 允许 CPU 确定机器指令何时必须等待其操作数可用，并将其放在一边，直到准备好向执行单元发出。如果其他指令的操作数可用，则可以在此期间发出指令流中稍后部分的其他指令。当在调度队列中等待的指令的操作数到达时，该指令将被发送到管道。

Pre-OOE, the terms dispatch and issue meant the same thing: allowing an instruction to enter the execution pipeline. With OOE, an instruction can be dispatched to a queue after it’s been decoded, but the instruction is not issued to the execution units until its data is known to be available.

> 在 OOE 之前，术语分派和发布意味着相同的事情：允许指令进入执行管道。使用 OOE，一条指令在被解码后可以被发送到队列，但在知道其数据可用之前，该指令不会被发送到执行单元。

As you might expect, OOE requires yet more smarts (and lots more transistors) to avoid hazards and perform correctly. Before the instructions are retired, the CPU must ensure that OOE did not affect the results of the task being executed. This is a larger version of the challenge facing pipelined execution generally and superscalar execution in particular.

> 正如你所料，OOE 需要更多的智能(和更多的晶体管)来避免危险并正确运行。在指令失效之前，CPU 必须确保 OOE 不会影响正在执行的任务的结果。这是流水线执行所面临的挑战的更大版本，特别是超标量执行。

### Thumb 2

The Cortex A8 core introduced the Thumb 2 instruction set enhancements. In simplest terms, Thumb 2 augments the original 16-bit Thumb instruction set with a selection of 32-bit instructions, with the result that the Thumb 2 instruction set is nearly feature-equivalent to the full 32-bit ARM one, and the instruction-count penalty associated with Thumb is largely absent. Even with the new 32-bit instructions, 16-bit instructions can be used frequently enough to yield a useful increase in code density (especially on low-cost embedded systems with limited memory).

> Cortex A8 内核引入了 Thumb 2 指令集增强功能。简单地说，Thumb 2 通过选择 32 位指令扩充了原始的 16 位 Thumb 指令集，其结果是 Thumb 2 指令集的功能几乎等同于完整的 32 位 ARM 指令集，并且 Thumb 相关的指令计数惩罚在很大程度上不存在。即使使用新的 32 位指令，也可以频繁使用 16 位指令，以有效提高代码密度(尤其是在内存有限的低成本嵌入式系统上)。

One shortcoming of the Thumb instruction set is the lack of conditional execution. Thumb 2 provides a partial fix for 16-bit Thumb instructions using the new `IT` (IF/THEN) instruction. `IT` provides a condition code that governs a block of up to four subsequent 16-bit instructions. Each instruction in the block can be tagged with either the condition code specified by the `IT` instruction or its complement, and it executes only if the condition is satisfied.

> Thumb 指令集的一个缺点是缺少条件执行。Thumb 2 使用新的 "IT" (IF/THEN)指令为 16 位 Thumb 指令提供部分修复 `IT’提供了一个条件代码，该代码控制最多四个后续 16 位指令的块。块中的每条指令都可以用 "IT" 指令指定的条件代码或其补码标记，并且只有满足条件时才执行。

### Thumb EE

The Cortex A8 core introduced the Thumb-EE execution environment. Thumb-EE is an instruction architecture incorporating Thumb 2 instructions with features optimised for use with just-in-time (JIT) compilation of high-level languages like Java, Python, C# and Perl. Faster cores, larger memory spaces and better JIT compilers have made Jazelle and Thumb EE less necessary, and ARM Holdings deprecated Thumb EE in 2011.

> Cortex A8 内核引入了 Thumb EE 执行环境。Thumb EE 是一种包含 Thumb 2 指令的指令体系结构，其功能经过优化，可用于 Java、Python、C#和 Perl 等高级语言的实时(JIT)编译。更快的内核、更大的内存空间和更好的 JIT 编译器使 Jazelle 和 Thumb EE 不再必要，ARM 控股公司在 2011 年弃用了 Thumb EE。

### big.LITTLE

Power consumption is a critical issue in mobile computing, and much of the innovation in new ARM generations has gone to increasing performance without sacrificing ARM’s traditional advantage in energy efficiency. One technique introduced with the Cortex family goes by the trademark big.LITTLE. In devices implementing big.LITTLE there are two ARM cores (or clusters of cores) working together: a high-performance (out of order, multi-issue) core like the A15 that emphasises performance over energy per instruction, and a lower-performance (in order, single-issue) core like the A7 optimised for much lower energy used per instruction. The operating system can move individual processes between high- and low-energy cores on demand, and shut down unused cores, providing a much broader dynamic range in both processing capability and energy usage than would be available from a single mid-performance core.

> 功耗是移动计算中的一个关键问题，新一代 ARM 的许多创新都致力于提高性能，而不牺牲 ARM 在能效方面的传统优势。Cortex 系列引入的一种技术是 big.LITLE 商标。在实现 big.LITTLE 的设备中，有两个 ARM 内核(或内核集群)协同工作：一个高性能(无序、多问题)内核，如 A15，它强调性能而不是每指令的能量，以及像 A7 这样的低性能(按顺序、单次发行)内核，该内核针对每个指令使用的能量低得多而进行了优化。操作系统可以根据需要在高能耗和低能耗内核之间移动单个进程，并关闭未使用的内核，从而在处理能力和能耗方面提供比单个中等性能内核更大的动态范围。

The big.LITTLE technology was intended for use in custom SoC parts. The paired cores must be architecturally compatible and support multi-cluster cache coherence for the system to work. The A7/A15 pair was the first; the latest is the A53/A57 pair, which implements the new ARMv8 instruction set architecture.

> big.LITLE 技术旨在用于定制 SoC 部件。成对的内核必须在架构上兼容，**并支持多集群缓存一致性**，以使系统正常工作。A7/A15 对是第一对；最新的是 A53/A57 对，它实现了新的 ARMv8 指令集架构。

### The NEON Coprocessor for SIMD

The Cortex family of processors introduced a major new coprocessor: NEON. Prior to the ARMv7 instruction set architecture, SIMD support on ARM was handled by ARMv6 instructions on the ARM core, and acted on four 8-bit quantities held in ARM general-purpose registers. NEON moves SIMD instruction execution out to the coprocessor, and adds more than 100 SIMD instructions to ARMv7. This removes dependence on ARM general-purpose registers, and allows a 128-bit wide SIMD-specific register set. Each of the 16 128-bit NEON registers is interpreted as containing multiple values of the same type. Four data types are supported:

> Cortex 系列处理器推出了一个主要的新协处理器：NEON。在 ARMv7 指令集架构之前，ARM 上的 SIMD 支持由 ARM 内核上的 ARMv6 指令处理，并作用于 ARM 通用寄存器中保存的四个 8 位量。NEON 将 SIMD 指令执行转移到协处理器，并将 100 多条 SIMD 指令添加到 ARMv7。这消除了对 ARM 通用寄存器的依赖，并允许 128 位宽的 SIMD 专用寄存器集。16 个 128 位 NEON 寄存器中的每一个都被解释为包含相同类型的多个值。支持四种数据类型：

- Sixteen 8-bit quantities
- Eight 16-bit quantities
- Four 32-bit quantities
- Two 64-bit quantities

> -16 个 8 位量-8 个 16 位量-4 个 32 位量-2 个 64 位量

Which data type is used depends on the form of the SIMD machine instruction being executed. Underneath it all, the register is just a block of 128 bits. The instruction divides the source and destination registers into _lanes_, which are logical groupings of bits that are treated as separate quantities during SIMD maths (see Figure 4-21).

> 所使用的数据类型取决于所执行的 SIMD 机器指令的形式。在这一切的背后，寄存器只是一个 128 位的块。该指令将源寄存器和目标寄存器划分为 *lanes*，这是位的逻辑分组，在 SIMD 数学过程中被视为单独的数量(见图 4-21)。

![[FIGURE 4-21:](#07_9781119183938-ch04.xhtml#rc04-fig-0021) How NEON SIMD lanes divide 128-bit registers into logical quantities](./media/images/9781119183938-fg0421.png)

The 16 128-bit registers may be accessed as 32 64-bit registers. If calculations don’t require lanes wider than 64 bits, this allows more calculations to be done in registers without additional load/store operations.

> 16 个 128 位寄存器可以作为 32 个 64 位寄存器访问。如果计算不需要比 64 位宽的通道，这允许在寄存器中进行更多的计算，而无需额外的加载/存储操作。

### ARMv8 and 64-Bit Computing

The Cortex family introduced the ARMv7 instruction set architecture. The new (at the time of writing) Cortex A50 family introduces a new ISA, ARMv8. The primary purpose of ARMv8 is to implement 64-bit computation and memory addressing for the ARM core family. In fact, ARMv8 provides three different instruction sets:

> Cortex 系列引入了 ARMv7 指令集架构。新的(在撰写本文时)Cortex A50 系列引入了新的 ISA，ARMv8。ARMv8 的主要目的是为 ARM 核心系列实现 64 位计算和内存寻址。事实上，ARMv8 提供了三种不同的指令集：

- **A32:** The 32-bit ARM instruction set, essentially unchanged from ARMv6 and ARMv7
- **T32:** The Thumb 2 instruction set, essentially unchanged from ARMv7
- **A64:** The new 64-bit instruction set

> -**A32:**32 位 ARM 指令集，基本上与 ARMv6 和 ARMv7 保持不变-**T32:**Thumb 2 指令集，与 ARMv7 基本保持不变-**A64:**新的 64 位指令集

A64 makes significant changes to the Cortex architecture:

> A64 对 Cortex 架构做出了重大改变：

- The general-purpose registers are 64 bits wide instead of 32.
- Machine instructions remain 32 bits in size to retain A32 code density.
- Instructions may take either 32-bit or 64-bit operands.
- The stack pointer and program counter are no longer general-purpose registers.
- An improved exception mechanism makes banked registers unnecessary.
- New optional instructions implement AES (Advanced Encryption Standard) encryption and both the SHA-1 and SHA-256 hashing algorithms in hardware.
- New features support hardware-assisted virtual machine management.

> -通用寄存器的宽度为 64 位，而不是 32 位机器指令保持 32 位大小，以保持 A32 代码密度。-指令可以采用 32 位或 64 位操作数。-堆栈指针和程序计数器不再是通用寄存器。-改进的异常机制使存储体寄存器不必要。-新的可选指令在硬件中实现 AES(高级加密标准)加密以及 SHA-1 和 SHA-256 哈希算法。-新功能支持硬件辅助虚拟机管理。

The Raspberry Pi 3 computer, introduced in February 2016, incorporates an ARMv8 64-bit quad-core CPU. It is thus the first 64-bit Raspberry Pi.

> 树莓派 3 电脑于 2016 年 2 月推出，采用 ARMv8 64 位四核 CPU。因此，它是第一个 64 位树莓派。

## Systems on a Single Chip

It’s easier to describe the architecture of an Intel chip than an ARM-based chip, simply because there are so many more different varieties of the latter "in the wild" . ARM-based chips are custom jobs, in two senses:

> 与基于 ARM 的芯片相比，描述 Intel 芯片的架构更容易，因为 "在野外" 有太多不同种类的 ARM 芯片。基于 ARM 的芯片在两个方面都是定制的工作：

- The CPU itself may be easily customised in terms of cache size, installed coprocessors and other significant features like TrustZone security.
- The CPU very often shares silicon with peripherals like network controllers, graphics processors and even blocks of system memory, to form SoC devices.

> -CPU 本身可以在缓存大小、安装的协处理器和其他重要功能(如 TrustZone 安全性)方面轻松定制。-CPU 通常与网络控制器、图形处理器甚至系统内存块等外围设备共享硅，以形成 SoC 设备。

Some ARM-based SoC parts (for example, the Apple A6X) are custom-designed and manufactured by a specific firm for its own mobile device products. Semiconductor manufacturers offer SoC parts of their own design to device manufacturers that don’t have the in-house resources to create a custom SoC from scratch.

> 一些基于 ARM 的 SoC 部件(例如，Apple A6X)由特定公司为其自己的移动设备产品定制设计和制造。半导体制造商向没有内部资源从头创建定制 SoC 的设备制造商提供自己设计的 SoC 部件。

### The Broadcom BCM2835 SoC

The first-generation Raspberry Pi computers are based on the BCM2835 SoC chip, designed and sold by Broadcom to manufacturers that want to field mobile devices like smartphones, tablets and e-book readers. The BCM2835 contains nearly all the digital logic necessary to create a standalone, graphics-intensive mobile computer. This logic falls into three broad categories:

> 第一代树莓派电脑基于 BCM2835 SoC 芯片，由博通公司设计并销售给那些希望推广智能手机、平板电脑和电子书阅读器等移动设备的制造商。BCM2835 包含创建独立的图形密集型移动计算机所需的几乎所有数字逻辑。这种逻辑分为三大类：

- A single ARM core, the ARM1176JZF-S, licensed from ARM Holdings
- A 1080p30-capable graphics processor, the VideoCore IV, developed and owned by Broadcom
- 128KB of Level 2 cache, shared with the CPU but used primarily by the VideoCore IV processor
- A suite of peripherals for the use of the ARM11 core, including:
- An interrupt controller
- Timers
- A pulse-width modulator (PWM)
- Two universal asynchronous receiver-transmitters (UARTs)
- A general-purpose I/O (GPIO) system providing 54 I/O lines
- An inter-IC sound (IIS or I2S) system and bus
- A serial peripheral interface (SPI) master/slave bus mechanism

> -一个 ARM 内核，ARM1176JZF-S，由 ARM 控股公司授权-一个 1080p30 功能的图形处理器，VideoCore IV，由 Broadcom 开发和拥有-128KB 的 2 级缓存，与 CPU 共享，但主要由 VideoCore IV 处理器使用-一套用于 ARM11 内核的外围设备，包括：-一个中断控制器-定时器-一个脉宽调制器(PWM)-两个通用异步接收器发射器(UART)-一个提供 54 条 I/O 线的通用 I/O(GPIO)系统-一个 IC 间声音(IIS 或 I2S)系统和总线-一个串行外围接口(SPI)主/从总线机制

The BCM2835 does not contain system memory. As described in [Chapter 3](#06_9781119183938-ch03.xhtml), the single SDRAM memory device piggybacks on top of the BCM2835 device, using package-on-package (POP) ball-grid array (BGA) packaging.

> BCM2835 不包含系统内存。如[第 3 章](#06_9781119183938-ch03.xhtml)中所述，使用封装上封装(POP)球栅阵列(BGA)封装，单个 SDRAM 存储器设备搭载在 BCM2835 设备的顶部。

### Broadcom’s Second- and Third-Generation SoC Devices

The Raspberry Pi 2’s release in February 2015 ushered in the second generation of Raspberry Pi computers. At the heart of the Raspberry Pi 2 is the BCM2836 SoC, which differs from the BCM2835 primarily in the CPU and Level 2 (L2) cache. The CPU is a quad-core ARM Cortex A-7 running at 900 MHz. Level 2 cache is 256KB, shared with the VideoCore IV graphics processor. The Raspberry Pi 2 board has 1 GB RAM, and the higher-capacity RAM IC is not mounted atop the SoC as in the Raspberry Pi 1 computers, but elsewhere on the printed circuit board.

> 树莓派 2 于 2015 年 2 月发布，迎来了第二代树莓派电脑。复盆子 Pi 2 的核心是 BCM2836 SoC，它与 BCM2835 的区别主要在于 CPU 和 2 级(L2)缓存。CPU 是一个四核 ARM Cortex a-7，运行频率为 900 MHz。2 级缓存为 256KB，与 VideoCore IV 图形处理器共享。复盆子 Pi 2 板有 1 GB RAM，更高容量的 RAM IC 不像复盆子 Pi1 计算机那样安装在 SoC 上，而是安装在印刷电路板的其他位置。

The Raspberry Pi 3 computer, released in February 2016, is based on the BCM2837 SoC, again with a 1GB RAM IC mounted directly to the printed circuit board and not atop the SoC device itself. The BCM2837 contains a quad-core 64-bit ARM Cortex A-53 CPU, with 512KB shared L2 cache. The dual-core VideoCore IV processor now runs at 400 MHz (300 MHz for 3D graphics) rather than the 250 MHz of the earlier SoCs. Beyond that, it is almost identical to the original BCM2835.

> 树莓派 3 电脑于 2016 年 2 月发布，基于 BCM2837 SoC，同样具有直接安装在印刷电路板上的 1GB RAM IC，而不是安装在 SoC 设备上。BCM2837 包含一个四核 64 位 ARM Cortex a-53 CPU，具有 512KB 的共享二级缓存。双核 VideoCore IV 处理器现在的运行频率为 400 MHz(3D 图形为 300 MHz)，而不是早期 SoC 的 250 MHz。除此之外，它几乎与原始 BCM2835 相同。

### How VLSI Chips Happen

It’s beyond the scope of this book to explain very large scale integration (VLSI) semiconductor fabrication in detail, but some understanding is necessary so that the jargon and the design challenge make sense.

> 详细解释超大规模集成电路(VLSI)半导体制造超出了本书的范围，但需要一些理解，这样术语和设计挑战才有意义。

VLSI chips are fabricated with a photolithography process, which uses short-wavelength ultraviolet (UV) light and a set of photographic masks to chemically impose patterns on a silicon wafer. These patterns are applied in layers that eventually combine to form individual transistors, resistors, diodes and capacitors. People who have made their own printed circuits at home by etching away copper to form patterns of conductive traces on fibreglass boards will have a sense for what’s going on. The difference, of course, is that VLSI fabrication involves patterns that are mere nanometres (billionths of a metre) in size.

> VLSI 芯片采用光刻工艺制造，该工艺使用短波紫外线(UV)和一组照相掩模在硅片上化学施加图案。这些图案被应用于最终组合成单个晶体管、电阻器、二极管和电容器的层中。通过蚀刻掉铜，在玻璃纤维板上形成导电迹线图案，在家里制作自己的印刷电路的人会对发生的事情有所了解。当然，不同的是，超大规模集成电路(VLSI)制造所涉及的图案尺寸仅为纳米(十亿分之一米)。

A single masking operation works like this:

> 单个掩蔽操作的工作原理如下：

1. A coating of a photosensitive chemical called _resist_ is applied to the wafer. 2. The mask is positioned over the wafer. 3. UV light is allowed to shine through the mask, hardening areas exposed to the UV. 4. The mask is removed, and the portions of the resist coating that were not exposed to UV are washed from the wafer. 5. A chemical process is applied to the wafer. Only where the unexposed resist was washed away can the chemicals reach the wafer. 6. The hardened resist is removed chemically in preparation for the next operation.

> 1.将一种称为 *resist* 的光敏化学物质涂层施加到晶片上。2.将掩模定位在晶片上。3.允许 UV 光照射通过掩模，硬化暴露于 UV 的区域。4.去除掩模，从晶片上清洗未暴露于 UV 的抗蚀剂涂层部分。5.对晶片进行化学处理。只有在未曝光的抗蚀剂被冲洗掉的地方，化学品才能到达晶片。6.化学去除硬化的抗蚀剂，为下一次操作做准备。

The chemical process in step 5 can be a number of things. An etchant may be applied to remove silicon. The wafer may be exposed to various chemicals for _doping_ the silicon—that is, infusing small quantities of elements like boron and phosphorus to alter the electrical properties of the silicon. This was originally done by exposing the wafer to dopant chemicals in gaseous or liquid form. These days, to achieve the precision required by increasingly smaller chip features, doping is often done by bombarding the wafer with dopant ions accelerated electromagnetically. Copper or some other metal (generally aluminium) may be applied to resist-free areas of the wafer, creating conductive paths.

> 步骤 5 中的化学过程可以是许多事情。可以施加蚀刻剂以去除硅。晶片可能会暴露在各种化学物质中，以吸附硅，也就是说，注入少量的元素，如硼和磷，以改变硅的电学性质。这最初是通过将晶片暴露于气态或液态的掺杂剂化学物质来完成的。如今，为了实现越来越小的芯片特征所需的精度，掺杂通常通过用电磁加速的掺杂剂离子轰击晶片来完成。铜或一些其他金属(通常是铝)可以被施加以抵抗晶片的自由区域，从而形成导电路径。

Depending on the complexity of the integrated circuit (IC) being fabricated, there can be 20 or 30 separate masks, and as many as 50 masking steps. Masking must be done with a mind-boggling level of precision. If even one masking step is performed out of alignment, the entire wafer will be faulty and must be discarded.

> 根据所制造的集成电路(IC)的复杂性，可以有 20 或 30 个单独的掩模，以及多达 50 个掩模步骤。蒙面必须以令人难以置信的精度进行。如果甚至有一个掩模步骤执行不对齐，则整个晶片将出现故障，必须丢弃。

### Processes, Geometries and Masks

The fabrication process described in the preceding section is a very touchy one. All the elements interact, and none can be changed without affecting the others. The sizes and shapes of the regions in the masks dictate the electrical properties of the silicon regions that the masks are used to create. At the sizes specified in modern IC designs, a difference of just a few million atoms in a P-N junction (a region where P-type and N-type semiconductor material are in contact, creating one or more transistors) can make the difference between a junction that works and one that works poorly or not at all. Leakage across junctions increases as the junction size decreases. Waste heat generated per unit area also increases as the sizes of the devices (transistors, resistors) decrease. All these factors must be taken into account.

> 前一节中描述的制造过程非常棘手。所有元素都是相互作用的，任何元素都不能在不影响其他元素的情况下进行更改。掩模中区域的大小和形状决定了掩模用于创建的硅区域的电性质。在现代 IC 设计中规定的尺寸下，P-N 结(一个 P 型和 N 型半导体材料接触的区域，产生一个或多个晶体管)中只有几百万个原子的差异，就能在工作正常的结和工作不好或根本不工作的结之间产生差异。结间泄漏随着结尺寸的减小而增加。单位面积产生的废热也随着器件(晶体管、电阻器)尺寸的减小而增加。必须考虑所有这些因素。

For these reasons, it’s impossible to shrink an IC design just by optically shrinking the mask patterns used in fabrication. Creating a chip with smaller circuit elements means re-engineering the entire fabrication process from scratch. In fact, engineers use the word _process_ to mean a very specific sequence of steps that cannot be changed in any way. The defining parameter of a fabrication process is the size of the smallest components created on the silicon die. This is called the _process geometry_. At the time of writing, the cutting-edge geometry is 14 nanometres. To put this in perspective, the _lattice constant_ of silicon—the distance between silicon atoms on a smooth crystalline surface—is .54 nanometres. This means that a 14-nanometre feature on a silicon die is about 30 to 35 _atoms_ wide.

> 由于这些原因，仅通过光学收缩制造中使用的掩模图案是不可能收缩 IC 设计的。用更小的电路元件制造芯片意味着从头开始重新设计整个制造过程。事实上，工程师使用单词 *process* 来表示一个非常具体的步骤序列，这些步骤不能以任何方式改变。制造工艺的定义参数是在硅管芯上创建的最小组件的尺寸。这称为过程几何。在撰写本文时，尖端几何尺寸为 14 纳米。为了说明这一点，硅的晶格常数——光滑晶体表面上硅原子之间的距离是.54 纳米。这意味着硅管芯上的 14 纳米特征约为 30 至 35 原子宽。

Because the size of the features drawn on a mask dictates their electrical properties, masks for fabricating a device are process and geometry specific.

> 因为在掩模上绘制的特征的大小决定了它们的电特性，所以用于制造器件的掩模是特定于工艺和几何形状的。

### IP: Cells, Macrocells and Cores

Modern ICs, of whatever function, are almost never created from whole cloth. In other words, design engineers do not sit down at a CAD workstation and begin drawing individual transistors and other components. With hundreds of millions of devices on modern silicon dies, that would take a very long time. Fortunately, it’s also unnecessary.

> 现代 IC，无论其功能如何，几乎从来都不是由整块布料制成的。换句话说，设计工程师不会坐在 CAD 工作站上开始绘制单个晶体管和其他组件。现代硅芯片上有数亿个器件，这需要很长时间。幸运的是，这也是不必要的。

Just as program code can be designed as a library of standard subroutines, digital logic expressed in silicon can be designed as libraries of standard cells. In a custom IC design context, a _cell_ is a single logic element (for example, a gate, an inverter, a flip-flop and so on) that has been laid out in mask form and verified for proper operation. Larger blocks of digital logic (registers, adders, memory blocks and so on) are called _macrocells_. When designers get to a subsystem level (processors, caches, coprocessors) the designs are generally called _cores_.

> 正如程序代码可以被设计为标准子程序库一样，用硅表示的数字逻辑可以被设计成标准单元库。在定制 IC 设计环境中，*cell* 是一个单独的逻辑元件(例如，门、反相器、触发器等)，它以掩模的形式布置，并验证其是否正常工作。较大的数字逻辑块(寄存器、加法器、存储器块等)称为*宏块。当设计者到达子系统级(处理器、缓存、协处理器)时，设计通常被称为\_cores*。

Libraries of standard cells and macrocells, along with complete and tested cores, are often sold by design houses and fabricators to groups wanting to create their own custom designs. The libraries and cores are licensed as intellectual property (IP), and IC design engineers idiomatically refer to any licensed digital logic block as "an IP" .

> 标准单元和宏单元库，以及完整和测试过的核心，通常由设计公司和制造商出售给希望创建自己定制设计的团体。库和内核被许可为知识产权(IP)，IC 设计工程师习惯性地将任何许可的数字逻辑块称为 "IP" 。

### Hard and Soft IP

Design houses sometimes license logic blocks that have already been tested and laid out for masks to be used in a specific fabrication process and geometry. These are called hard IPs, macrocells or cores, and are basically maps of polygons that may be integrated into CAD designs for process masks. Hard IPs are compact and reliable, but they can’t be used in processes other than the ones they were designed for.

> 设计公司有时会对已经测试和布局的逻辑块进行许可，以便在特定的制造工艺和几何结构中使用掩模。这些被称为硬 IP、宏单元或核心，基本上是多边形的地图，可以集成到工艺掩模的 CAD 设计中。硬 IP 结构紧凑、可靠，但不能用于除其设计用途之外的其他过程。

Modern IPs are most often delivered as soft cores. These are descriptions of the logic and electrical behaviour of the IP, but not the physical layout on silicon. Soft IP is licensed in the form of source files written in a hardware description language (HDL) expressing the logic in an abstract form called register-transfer level (RTL). RTL is a way of describing hardware in terms of registers formed of flip-flops and combinatorial logic using simple logic gates. The description is of logic states transferred through clouds of flip-flops and gates, hence the term. RTL descriptions may be written in any of several HDLs, the most popular being Verilog and VHDL.

> 现代 IP 通常以软核的形式提供。这些描述的是 IP 的逻辑和电气行为，但不是硅上的物理布局。软 IP 以硬件描述语言(HDL)编写的源文件的形式获得许可，硬件描述语言以称为寄存器传输级别(RTL)的抽象形式表达逻辑。RTL 是用触发器和使用简单逻辑门的组合逻辑构成的寄存器来描述硬件的一种方式。描述的是通过触发器和门的云传输的逻辑状态，因此得名。RTL 描述可以用几种 HDL 中的任何一种来编写，最流行的是 Verilog 和 VHDL。

With a description of a design’s RTL logic written in an HDL, an IP may be synthesised to a matrix of individual gates called a netlist, and then placed (laid out in two dimensions) and routed (connected to one another) for a particular process. This essentially converts a soft IP to a hard IP, and is referred to as hardening an IP. Most IPs today are delivered as RTL files, and the synthesis and routing are done during the synthesis and routing of the SoC as a whole.

> 通过用 HDL 描述设计的 RTL 逻辑，IP 可以被合成为称为网表的单个门矩阵，然后被放置(以二维布局)和路由(彼此连接)用于特定过程。这基本上将软 IP 转换为硬 IP，并称为硬化 IP。如今，大多数 IP 都是以 RTL 文件的形式交付的，而合成和路由是在整个 SoC 的合成和路由过程中完成的。

### Floorplanning, Layout and Routing

The actual physical creation of an SoC begins with a finished netlist that defines the entire device both logically and electrically. The challenge of creating SoC parts from a netlist lies in arranging cells and macrocells on a silicon die and connecting them as the netlist requires. Creating a tentative layout for an SoC is called _floorplanning_, and the metaphor is apt: engineers have to parcel out the area of a silicon die into regions big enough to hold all the parts of the design, just as architects divide the floor of a building into offices, lift-shafts, hallways and so on. Floorplanning must be done within a number of constraints:

> SoC 的实际物理创建始于完成的网表，该网表在逻辑和电气上定义了整个设备。从网表创建 SoC 部件的挑战在于在硅管芯上排列单元和宏单元，并按照网表的要求连接它们。为 SoC 创建一个初步布局被称为 "楼层规划" ，这个比喻很恰当：工程师必须将硅芯片的区域划分为足够大的区域，以容纳设计的所有部分，就像建筑师将建筑的楼层划分为办公室、电梯井、走廊等。楼层规划必须在若干约束条件下进行：

- There is only so much area on the die.
- Many macrocells (especially hard IPs licensed from design firms) have a fixed size, shape and orientation and thus no "wiggle room" for fitting into a layout.
- There may be a maximum number of connection pads on the device package.
- Some logic blocks (such as line drivers) must be physically close to the connection pads that they serve.
- Data paths must not introduce timing problems or _crosstalk,_ which is electrical interference between adjacent conductors caused by capacitive or inductive effects.

> -模具上只有这么多区域。-许多宏小区(特别是从设计公司获得许可的硬 IP)具有固定的大小、形状和方向，因此没有适合布局的 "摇摆空间" 。-设备封装上可能有最大数量的连接焊盘。-某些逻辑块(如线路驱动器)必须在物理上靠近它们所服务的连接焊盘。-数据路径不得引入定时问题或串扰，这是由电容或电感效应引起的相邻导体之间的电干扰。

Within such constraints, engineers strive to make the layout as small as possible, not only to maximise the number of devices per wafer, but also to minimise signal propagation delays. Floorplanning is a sort of intuitive "first cut" at a layout, to make the later job of the CAD software tools as easy as possible. With a floorplan in hand, engineers turn to placement, during which the precise position of elements in the layout is done using CAD tools. Placement may demand iterative changes in the floorplan, including the size and aspect ratio, which defines the proportions of the rectangle embracing the layout.

> 在这样的限制条件下，工程师们努力使布局尽可能小，不仅要最大化每片晶片的器件数量，而且要最小化信号传播延迟。平面规划是一种直观的布局 "第一步" ，使 CAD 软件工具的后期工作尽可能简单。有了平面布置图，工程师们就可以开始布局了，在布局中元素的精确位置是使用 CAD 工具完成的。布局可能需要在平面布置图中进行迭代更改，包括尺寸和纵横比，这定义了包围布局的矩形的比例。

The final step is _routing_, which encompasses the crucial job of creating data paths, clock distribution paths and power distribution paths. Routing is where issues with crosstalk and capacitive coupling are actually modelled and the resulting timing violations (cases in which signals arrive at a flip-flop too late, or too soon) are corrected when found. Towards the end of the chip design process, the team enters what is termed the timing closure loop: violations are fixed by adjusting transistor sizes or inserting buffers, which in turn creates a (hopefully) smaller number of new violations, which are then fixed in turn until none remain. With routing finished for the desired process, the SoC design may be "taped out" (written to files in a final version) and sent to a chip foundry for mask creation and the eventual fabrication of "first silicon" .

> 最后一步是 *routing*，它包含创建数据路径、时钟分配路径和电源分配路径的关键任务。路由是实际模拟串扰和电容耦合问题的地方，并在发现时纠正由此产生的时序违规(信号到达触发器太晚或太快的情况)。芯片设计过程快结束时，团队进入了所谓的时序闭合循环：通过调整晶体管大小或插入缓冲区来修复违规行为，这反过来又产生了(希望)更少数量的新违规行为，然后依次修复，直到没有剩余。完成所需工艺的布线后，SoC 设计可能会被 "流片" (写入最终版本的文件中)，并发送到芯片代工厂进行掩模创建和最终制造 "第一块硅" 。

### Standards for On-Chip Communication: AMBA

Integration of IP cores from multiple sources and the construction of a bus fabric to tie them together into a coherent whole comprise one of the most challenging steps in the design of any IC. The scale of the challenge grows with the complexity of the design, the clock rates at which it operates and the reduction of the size of the process geometry. Standards can help to simplify the design process by abstracting away the details of bus implementation, allowing IP cores and infrastructure components to be reused elsewhere on the chip, or in new projects.

> 集成来自多个源的 IP 核以及构建总线结构以将它们连接成一个连贯的整体，是任何 IC 设计中最具挑战性的步骤之一。挑战的规模随着设计的复杂性、其运行的时钟速率以及工艺几何尺寸的减小而增大。标准可以通过抽象总线实现的细节来帮助简化设计过程，允许 IP 核和基础设施组件在芯片上的其他地方或在新项目中重用。

In 1996, ARM Holdings introduced the Advanced Microcontroller Bus Architecture (AMBA) to do precisely that: provide standards for creating and reusing IP. ARM later released actual soft IP implementing AMBA-compliant on-chip data buses for SoCs. In the 20 years since its introduction, AMBA has gone through four generations; today it’s the de facto standard for on-chip buses, especially for SoCs that incorporate ARM processor cores. The AMBA standard is public and may be used without payment of royalties to ARM Holdings.

> 1996 年，ARM 控股公司引入了高级微控制器总线体系结构(AMBA)来实现这一目标：为创建和重用 IP 提供标准。ARM 后来发布了实际的软 IP，为 SoC 实现了符合 AMBA 的片上数据总线。自推出以来的 20 年中，AMBA 经历了四代人；今天，它是片上总线的事实标准，特别是对于包含 ARM 处理器内核的 SoC。AMBA 标准是公开的，可以在不向 ARM Holdings 支付版税的情况下使用。

The AMBA spec includes several different bus architecture definitions, which are informally called _protocols_. Each protocol includes specs for both the physical connections between cores and the logic that governs data movement over the connections. The protocol used in the BCM2835 SoC is the Advanced Extensible Interface (AXI), which is part of the AMBA 3 specification. The version of AXI used in the Raspberry Pi is thus referred to as AXI 3. An AXI bus may be configured at design time to be from 8 to 1024 bits wide, in powers of two. The internal buses in the BCM2835 are between 32 and 256 bits wide, depending on the bandwidth required.

> AMBA 规范包括几个不同的总线体系结构定义，这些定义被非正式地称为 *procols*。每个协议都包括核心之间的物理连接和控制连接上数据移动的逻辑的规范。BCM2835 SoC 中使用的协议是高级可扩展接口(AXI)，它是 AMBA 3 规范的一部分。复盆子 Pi 中使用的 AXI 版本因此被称为 AXI 3。AXI 总线可以在设计时被配置为从 8 到 1024 位宽，2 的幂。BCM2835 中的内部总线宽度介于 32 和 256 位之间，具体取决于所需的带宽。

An AXI bus may be imagined (roughly) as an interconnected network of utility trenches dug between several buildings in a corporate campus. Builders lay pipes in the trenches to carry water, electricity, natural gas, wastewater or steam. The pipes are run side-by-side in the trenches but are not interconnected. An AXI bus incorporates five channels that carry data along paths on the SoC silicon, around and between the various cores on the SoC. Each channel is _unidirectional_, meaning that data passes only one way through the channel, just as water or natural gas flows only one way through the pipes that carry it. The flow of data over each bus is controlled using ready-valid signalling: the upstream end asserts (sets to high, or logic 1) a valid signal if it has data to transmit, the downstream end asserts a ready signal if it is able to accept data, and data is transferred during a clock cycle if, and only if, both signals are high.

> AXI 总线可以(粗略地)想象为一个互连的网络，由在企业校园内的多个建筑物之间挖掘的公用设施沟渠组成。建筑商在沟渠中铺设管道，以输送水、电、天然气、废水或蒸汽。管道在沟槽中并排敷设，但不相互连接。AXI 总线包含五个通道，这些通道沿着 SoC 硅上的路径、围绕 SoC 上的各个核心以及在 SoC 上各个核心之间传输数据。每个通道都是单向的，这意味着数据只能单向通过通道，就像水或天然气只能单向通过传输它的管道一样。使用就绪有效信号控制每条总线上的数据流：如果有数据要传输，则上游端断言(设置为高，或逻辑 1)有效信号；如果能够接受数据，则下游端断言就绪信号；如果且仅当两个信号都为高，则在时钟周期内传输数据。

Channels conduct data between two kinds of endpoints: master and slave. These are roughly equivalent to client and server in the network world. The master (which could, for example, be a CPU, graphics processor or video decode engine) requests a transaction, and the slave (which could be an SDRAM controller or a peripheral such as a UART) complies with the master’s request. The master may request either a data read or data write transaction, but in either case the transaction is requested and controlled by the master.

> 通道在两种端点之间传输数据：主端点和从端点。它们大致相当于网络世界中的客户端和服务器。主设备(例如，可以是 CPU、图形处理器或视频解码引擎)请求事务，从设备(可以是 SDRAM 控制器或 UART 等外围设备)遵从主设备的请求。主机可以请求数据读取或数据写入事务，但在任一情况下，事务都由主机请求和控制。

The five AXI3 channels are:

> 五个 AXI3 通道为：

- **Read address channel:** Carries address and control information from a master to a slave endpoint that acts as a data source
- **Read data channel:** Carries the requested data back from the slave to the master
- **Write address channel:** Carries address and control information from a master to a slave endpoint that stores or otherwise uses data
- **Write data channel:** Carries one or more pieces of data associated with a write address from the master to the slave that needs the data
- **Write response channel:** Carries acknowledgment signals from the slave to the master, indicating that the data had been successfully received

> -**读取地址通道：**将地址和控制信息从主机传送到充当数据源的从属端点-**读取数据通道：**从从属端点将请求的数据传送回主机-**写入地址通道：\***将地址和控制信息从主端点传送到存储或以其他方式使用数据的从属端点。**写入数据通道：\***传送一个或多个与从主设备到需要数据的从设备的写入地址相关联的数据段**写入响应信道：**从设备向主设备发送确认信号，表示数据已成功接收

Using these five channels, data may be moved very quickly around the bus (see Figure 4-22).

> 使用这五个通道，数据可以在总线上快速移动(见图 4-22)。

![[FIGURE 4-22:](#07_9781119183938-ch04.xhtml#rc04-fig-0022) AXI3 bus channels](./media/images/9781119183938-fg0422.png)

Three general types of bus component may be inserted into AXI3 channels:

> 三种通用类型的总线组件可插入 AXI3 通道：

- **Register slices:** "Latch" data moving through a bus channel into temporary memory. This allows timing conflicts to be resolved by breaking long paths into shorter ones. Metaphorically, a register slice is a way to place a "slice" of the bus onto a shelf, where it can wait until the other end of the channel signals the register slice that it can accept the slice data. Register slices can be combined to allow pipelining of data passing along the bus, in a way similar to how pipelining works for machine instructions in CPUs.
- **Arbiters:** These merge multiple upstream buses into a single downstream bus. This allows multiple masters to interchange data with a single slave. The arbiter manages control information to ensure that the proper upstream bus receives read data and write responses intended for it. As an example, an arbiter is used to allow the ARM, the graphics processor and the video decode engine inside BCM2835 to share access to main memory.
- **Splitters:** These divide a single upstream bus into multiple downstream buses. This allows a single master to exchange data with multiple slaves. As an example, a splitter is used to allow the ARM11 to access both main memory and the various peripherals on the SoC.

> -**寄存器片：** "锁存" 数据通过总线通道移动到临时存储器。这允许通过将长路径拆分为短路径来解决时间冲突。隐喻地说，寄存器片是将总线的一个 "片" 放在机框上的一种方式，它可以在机框中等待，直到通道的另一端向寄存器片发出可以接受片数据的信号。寄存器片可以组合在一起，以允许沿着总线传输数据的流水线，其方式类似于流水线在 CPU 中处理机器指令的方式。-**仲裁器：**这些将多个上游总线合并为一个下游总线。这允许多个主设备与单个从设备交换数据。仲裁器管理控制信息，以确保正确的上游总线接收到针对它的读数据和写响应。例如，仲裁器用于允许 ARM、图形处理器和 BCM2835 内部的视频解码引擎共享对主存储器的访问。-**拆分器：**这些拆分器

With these three components, an on-chip bus fabric can be made to connect the various cores making up an SoC in almost any useful combination. Much of the effort expended in designing an SoC is devoted to constructing a fabric that is capable of providing real-time masters, such as camera and display interfaces and video decode engines, with the bandwidth and latency quality-of-service (QoS) guarantees they require to meet specified performance goals. This in turn requires us to come up with policies that determine which port of an arbiter is granted access to the downstream bus if multiple upstream buses have pending requests, based on static information (the identity of the requesting master) and dynamic information (recent traffic history). QoS system design remains an active area of research in academic and commercial circles.

> 有了这三个组件，片上总线结构可以以几乎任何有用的组合连接组成 SoC 的各种核心。设计 SoC 所花费的大部分精力都用于构建一种结构，该结构能够提供实时主机，如相机和显示接口以及视频解码引擎，并具有满足特定性能目标所需的带宽和延迟服务质量(QoS)保证。这反过来要求我们根据静态信息(请求主机的身份)和动态信息(最近的流量历史)制定策略，以确定如果多个上游总线有未决请求，仲裁器的哪个端口被授权访问下游总线。QoS 系统设计仍然是学术界和商业界的一个活跃研究领域。
