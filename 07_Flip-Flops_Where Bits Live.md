# Flip-Flops: Where Bits Live

A _flip-flop_ is an electronic circuit that stores a logical state, conventionally described as either 1 or 0. Once set to a particular state by a digital signal on an input (typically a voltage change from 0 volts to 5 volts or 5 to 0) the flip-flop will maintain that state until another input signal changes it. Because a flip-flop can store one of two logical states, it is sometimes described as _bistable_. There are several different types of flip-flop, but the one most used in computer logic is the _D-type_, where D stands for `data` . The 1 and 0 states stored in flip-flops may be used to express computer data, hence the name.

> _flip-flop_ 是一个电子电路，该电子电路存储逻辑状态，通常被描述为 1 或 0。一旦通过输入上的数字信号设置为特定状态(通常是从 0 伏特到 5 伏或 5 伏的电压变化)触发器将维护该状态，直到另一个输入信号更改为止。由于触发器可以存储两个逻辑状态之一，因此有时被描述为 _bistable_。有几种不同类型的触发器，但是计算机逻辑中最常用的一种是 _d-type_，其中 d 代表 `数据` 。存储在触发器中的 1 和 0 状态可用于表达计算机数据，因此可以使用该名称。

A D-type flip-flop takes a snapshot of the D input every time it sees a low-to-high transition on its clock input (a rising clock edge), and presents it on the Q output until the next clock edge arrives. You can build complex systems by combining D-type flip-flops that store state with a combinatorial logic circuit to compute the next state from the current state and (optionally) external inputs.

> D 型触发器每次看到其时钟输入(一个上升的时钟边缘)时，都会对 D 输入进行 d 输入的快照，并将其放在 Q 输出上，直到下一个时钟边缘到达。您可以通过将存储状态的 D 型触发器与组合逻辑电路相结合来构建复杂的系统，从而从当前状态和(选择)外部输入来计算下一个状态。

Figure 4-4 presents a simple example. Assuming you’ve built a piece of combinatorial logic to add 1 to a four-digit binary number, you can implement a counter that increments a four-digit value stored in four flip-flops every time the clock ticks. The maximum clock speed is determined by the longest path through the cloud of combinatorial logic: you need to respond to a change in the values in the flip-flops and get the new value ready before the next clock edge comes along.

> 图 4-4 提出了一个简单的示例。假设您已经构建了一块组合逻辑来将 1 添加到四位数的二进制号码，则可以实现一个计数器，每次时钟滴答时，都会将四位数的值递增四位数的触发器。最大时钟速度取决于结合逻辑云的最长路径：您需要响应触发器中的值的变化，并在下一个时钟边缘出现之前准备好新值。

> ![[FIGURE 4-4:](#07_9781119183938-ch04.xhtml#rc04-fig-0004) A counter built from four flip-flops](./media/images/9781119183938-fg0404.png)

Another useful example is a shift register, shown in Figure 4-5. A shift register hands bits down the chain of flip-flops, advancing by one position every clock edge.

> 另一个有用的示例是移位寄存器，如图 4-5 所示。移位寄存器的手沿触发器链沿着链条链，每个时钟边缘都以一个位置前进。

> ![[FIGURE 4-5:](#07_9781119183938-ch04.xhtml#rc04-fig-0005) A shift register built from four flip-flops](./media/images/9781119183938-fg0405.png)

Everything you see in this chapter is an elaboration of these fundamental principles: clouds of combinatorial logic and D-type edge-triggered flip-flops that store a digital state.

> 您在本章中看到的所有内容都是对这些基本原理的详细说明：组合逻辑和 D 型边缘触发的触发器的云，这些触发器存储了数字状态。

## Inside the CPU

As explained briefly in [Chapter 2](#05_9781119183938-ch02.xhtml), a computer program is just a long series of _very_ small steps. Each of these very small steps is called a _machine instruction_, and it is an `atomic` unit of action that cannot be divided further outside of the CPU. Each family of CPUs has its own unique roster of machine instructions. They may do similar things, but, in general, the machine instructions from one family of CPUs will _not_ execute on another family of CPUs. The definition of a CPU’s machine instructions and what they do is called its _instruction set architecture_ (ISA).

> 正如[第 2 章](%EF%BC%8305_9781119183938-CH02.XHTML)中简要解释的那样，计算机程序只是一系列 _very_ 小步骤。这些很小的步骤中的每一个都称为 _machine 指令_，它是一个 `原子` 动作单位，不能在 CPU 之外进一步划分。每个 CPU 家族都有自己独特的机器说明阵容。他们可能会做类似的事情，但是通常，一个 CPU 家族的机器指令将在另一个 CPU 家族中执行。CPU 的机器指令及其所做的定义称为其 _Instruction set Architecture_(ISA)。

An instruction is represented in memory by a binary value some number of bytes long. (On many 32-bit CPUs like the ARM11 in the original Raspberry Pi, this number is four 8-bit bytes.) Within this binary number are encoded the identity of the instruction (called the _operation code_, or _opcode_), and one or more operands, which are values or addresses associated with the instruction. A binary machine instruction is loaded from memory into the CPU, where the CPU decodes it (takes it apart to determine what must be done) and then executes it, during which the actual work of the instruction is accomplished. When an instruction has been dispatched for execution it’s said to have been issued, and after it is completely executed it’s said to be retired*.* The next instruction in the program is loaded into the CPU for execution. (In modern CPUs, the process is more complicated than that, as we explain later in this chapter.)

> 指令在内存中由二进制值表示一些字节长。(在原始 Raspberry Pi 中的许多 32 位 CPU 中，如 ARM11，该数字为四个 8 位字节。)在此二进制数字中，编码了指令的身份(称为 _operation code_ 或 _opcode_)，一个或一个或一个或一个或一个或一个。更多操作数，是与指令关联的值或地址。将二进制机器指令从内存加载到 CPU 中，在该 CPU 中，CPU 将其解码(将其拆开以确定必须完成的操作)，然后执行它，在此期间完成了指令的实际工作。据说已发出指令进行执行，并且在完全执行后，据说已退休*。*该程序中的下一个指令已加载到 CPU 中进行执行。(在现代 CPU 中，正如我们在本章后面解释的那样，该过程比这更复杂。)

From a height, program execution by the CPU works like this:

> 从高度开始，CPU 的程序执行类似：

1. Fetch the first instruction in the program. 2. Decode the instruction. 3. Execute the instruction. 4. Fetch the next instruction. 5. Decode the instruction. 6. Execute the instruction.

> 1.获取程序中的第一个指令。2.解码说明。3.执行指令。4.获取下一个指令。5.解码说明。6.执行指令。

…and so on, for as many instructions as are in the program. The _program counter_ is a pointer inside the CPU that contains the memory address of the currently executing instruction.

> …等等，依此类推。_program Counter_ 是 CPU 内部的指针，其中包含当前执行指令的内存地址。

Machine instructions do things like

> 机器说明执行诸如

- Add, subtract, multiply or divide
- Perform logical operations like AND, OR, XOR and NOT on binary values
- Shift a multi-bit binary value to the left or right
- Copy data from one location to another
- Compare values against constants or other values
- Perform CPU control functions

>

- 添加，减法，乘或分割
- 执行逻辑操作，例如和或，或者，或在二进制值上，而不是二进制值
- 将多位二进制值向左或右移动
- 将数据从一个位置复制到另一个位置
- 将值与常数或常数或其他值
- 执行 CPU 控制功能

The values on which the machines operate may come from external memory or from one of a comparatively small number of registers inside the CPU itself. A _register_ is a storage location that can hold multiple bits at once; typically 16, 32 or 64, depending on the CPU. Results from machine instruction operations may be stored to memory or to registers.

> 机器运行的值可能来自外部内存或 CPU 本身内部相对较少的寄存器之一。_register_ 是一个可以立即容纳多个位的存储位置；通常取决于 CPU，通常为 16、32 或 64。机器指令操作的结果可以存储到内存或寄存器中。

In modern CPUs, separate subsystems execute different groups of machine instructions:

> 在现代 CPU 中，单独的子系统执行不同的机器指令组：

- **Arithmetic logic unit (ALU):** Handles simple integer maths and logical operations

>

- **算术逻辑单元(ALU)：**处理简单的整数数学和逻辑操作
- **Floating point unit (FPU):** Handles floating point maths

>

- **浮点单元(FPU)：**处理浮点数学
- **Single-instruction, multiple data (SIMD) unit:** Handles vector maths that performs operations on multiple data values at once. This type of maths is essential in audio and video applications.

>

- **单个指导，多个数据(SIMD)单元：**处理一次对多个数据值执行操作的向量数学。这种类型的数学在音频和视频应用中至关重要。

A modern high-performance CPU may have multiple copies of each unit to support parallel execution of instructions, as we explain a little later.

> 正如我们稍后解释的那样，现代的高性能 CPU 可能具有每个单元的多个副本，以支持指令的平行执行。

### Branching and Flags

As useful as executing a linear sequence of instructions may be, the real magic of computing lies in the ability of a program to change its course of execution depending on the results of its work. This is done using _branch instructions_, which have the power to skip forward or backward in the sequence of machine instructions that make up a program. Some branch instructions—called unconditional branch instructions—tell the CPU to `just go` and load the next instruction from a memory address included in the branch instruction.

> 与执行线性指令序列的有用一样，计算的真正魔力在于程序可以根据其工作结果来更改其执行过程的能力。这是使用 _Branch 指令_ 完成的，该指令有能力以组成程序的机器指令的顺序跳过或向后跳过。一些分支说明(未定入数的分支指令)指出 CPU `只需` 并从分支指令中包含的存储地址加载下一个指令。

A conditional branch instruction combines a test of some sort with a branch. These tests generally involve a group of single-bit binary values called _flags_ that are stored somewhere in the CPU, generally in a group called the flags register or status word. When certain machine instructions execute, they set (change to binary 1) or clear (change to binary 0) one or more flags. For example, all CPUs have instructions that compare the values of two registers. If the values are equal, a flag (generally called the zero flag) is set to 1. If the values are not equal, the flag is cleared to zero. The flag is called the `zero` flag because of the way comparisons work. To compare two registers, the CPU subtracts one of them from the other. If the result of the subtraction is zero, they are equal, and the zero flag is set. If the result of the subtraction is anything but zero, the two registers are not equal, and the zero flag is cleared.

> 条件分支指令将某种测试与分支结合在一起。这些测试通常涉及一组称为 _flags_ 的单位二进制值，它们存储在 CPU 中，通常在称为标志寄存器或状态单词的组中。当某些机器指令执行时，它们会设置(更改为二进制 1)或清除(更改为二进制 0)一个或多个标志。例如，所有 CPU 都有比较两个寄存器值的指令。如果值相等，则标志(通常称为零标志)设置为 1。如果值不等于，则将标志清除为零。由于比较工作方式，因此标志称为 `零` 标志。要比较两个寄存器，CPU 从另一个寄存器中减去其中一个。如果减法的结果为零，则它们相等，并且设置了零标志。如果扣除的结果除零之外，则两个寄存器不等，并且清除了零标志。

A machine instruction is just a binary number. Although it is possible to program directly in machine code, for convenience programmers generally use an assembler to convert assembly language directly into machine instructions. Instructions in assembly language are represented by a short string called a mnemonic, and the various operands are written in human-readable form. The assembly language representation of a conditional branch machine instruction might look like this:

> 机器指令只是二进制号码。尽管可以直接在机器代码中进行编程，但为了方便程序员，通常使用汇编器将汇编语言直接转换为机器指令。组装语言中的说明由一个称为助记符的简短字符串表示，各种操作数以人类可读形式编写。条件分支机指令的汇编语言表示可能是这样的：

```
	BEQ [address]
```

What the instruction does is to branch if equal (that is, if the zero flag is set) to the machine instruction stored at the specified memory address; if the zero flag is clear, execution continues to the next instruction in memory.

> 指令的作用是如果等于(即设置了零标志)，则要分支到存储在指定的内存地址上的机器指令；如果零标志是清晰的，则执行继续到内存中的下一个指令。

There may be a dozen or more flags in a CPU’s architecture. Some flags reflect equality or the fact that a register’s value has become zero. Some indicate whether an arithmetic carry has occurred. Some indicate whether a register has been set to a positive or negative value. Some indicate error conditions, like numeric overflow or an attempt to divide by zero. Some reflect the current state of the CPU’s internal machinery. For each flag there are one or more conditional branch instructions that check the value of the flag and branch accordingly.

> CPU 的架构中可能有十二或更多的旗帜。一些标志反映了平等或寄存器值已变为零的事实。一些表明是否发生了算术携带。一些表明寄存器是将寄存器设置为正值还是负值。一些表示错误条件，例如数字溢出或尝试除以零。一些反映了 CPU 内部机械的当前状态。对于每个标志，有一个或多个条件分支指令，可以相应地检查标志的值和分支。

In addition to supporting conditional branch instructions, the ARM CPUs used by the Raspberry Pi has a more general conditional execution feature in its instruction set that is described in some detail later on.

> 除了支持条件分支指令外，Raspberry Pi 使用的 ARM CPU 在其指令集中还具有更一般的条件执行功能，以后在某些详细信息中进行了描述。

### The System Stack

There are a fair number of data structures catalogued and described by computer scientists including arrays, queues, lists, stacks, sets, rings and bags, among others. A few are used so often that some CPUs have hardwired support for them in their machine instructions. The most important of these is the stack.

> 计算机科学家(包括阵列，队列，列表，堆栈，集合，戒指和袋子)等计算机科学家将相当数量的数据结构分类和描述。经常使用一些，以至于某些 CPU 在其机器说明中对他们有硬连线的支持。其中最重要的是**堆栈**。

A _stack_ is a last-in-first-out (LIFO) data storage mechanism essential to the operation of most modern CPUs, including the Raspberry Pi’s ARM11. The key characteristic of stack operation is that data items are removed from the stack in the reverse order of how they were stored.

> *STACK* 是对大多数现代 CPU(包括 Raspberry pi 的 ARM11)运行必不可少的首先出局(LIFO)数据存储机制。堆栈操作的关键特征在于，数据项以相反的顺序从堆栈中删除，以使数据项的存储方式相反。

A metaphor captures this well. If you’ve ever eaten in a school cafeteria, you may have seen a common mechanism for storing plates and saucers: a spring-loaded platform within a metal cylinder, adjusted to balance the weight of whatever plates it contains. When you place a plate in the cylinder the platform moves down just enough to make room for the next plate. When you need a plate, you simply take one from the top of the cylinder. With its load lightened, the platform rises just enough to bring the next plate to the top of the cylinder.

> 一个隐喻抓住了这一点。如果您曾经在学校自助餐厅吃饭，您可能已经看到了一种储存盘子和碟子的通用机制：在金属缸内的弹簧平台，经过调整，以平衡其包含的任何板的重量。当您将盘子放在气缸中时，平台向下移动足以为下一个盘子腾出空间。当您需要盘子时，您只需从圆柱体的顶部取一个即可。随着负载减轻，该平台的上升幅度足以将下一个板带到圆柱体的顶部。

The key to the plate storage cylinder is that the first plate placed in the cylinder is all the way at the bottom. The last plate placed in the cylinder is at the top. The last plate stored is the first one taken out of storage—thus, `last in, first out` .

> 板块存储缸的钥匙是，放置在圆柱体中的第一板一直是底部的。放在圆柱体中的最后一个板位于顶部。存储的最后一个盘子是从存储空间中取出的第一个盘子，其中 `最后，第一个` 。

In a computer system, a stack is an area of memory set aside for LIFO data storage and managed by machine instructions designed to implement the stack data structure. Figure 4-6 shows a simple stack.

> 在计算机系统中，堆栈是用于 LIFO 数据存储的内存区域，并由旨在实现堆栈数据结构的机器指令进行管理。图 4-6 显示了一个简单的堆栈。

> ![[FIGURE 4-6:](#07_9781119183938-ch04.xhtml#rc04-fig-0006) How a stack works](./media/images/9781119183938-fg0406.png)

The stack begins at a location in memory specified by a _base pointer_. (A _pointer_ is simply a memory address.) After it’s loaded with an address, the value of the base pointer doesn’t change. A second pointer, called the _stack pointer_, indicates the memory location to be accessed next. It’s sometimes called the `top of the stack` . In [Figure 4-6](#07_9781119183938-ch04.xhtml#c04-fig-0006), the items at the top of the stack are shaded.

> 堆栈从 *base Pointer* 指定的内存中的位置开始。(*pointer* 只是一个内存地址。)加载地址后，基本指针的值不会更改。第二个指针称为 *Stack Pointer*，指示接下来要访问的内存位置。有时被称为 `堆栈顶部` 。在[图 4-6](%EF%BC%8307_978111919183938-CH04.XHTML%EF%BC%83C04-FIG-0006) 中，堆栈顶部的项目被阴影。

To add an item to a stack, the stack pointer is first incremented so that it points to the next available memory location in the stack. The data item is then written to that location. Informally, this is called pushing an item onto the stack.

> 要将项目添加到堆栈中，首先将堆栈指针递增，以便指向堆栈中的下一个可用内存位置。然后将数据项写入该位置。非正式地，这称为将项目推入堆栈。

To remove an item from the stack, the item at the top of the stack is first copied to a register or some other place in memory, and then the stack pointer is decremented so that it points to what had previously been the top item on the stack. This process is called popping an item from the stack. If you follow the four stack snapshots in [Figure 4-6](#07_9781119183938-ch04.xhtml#c04-fig-0006), you can see how the stack grows or shrinks as items are pushed onto it and popped from it. The last item pushed onto the stack is the first item popped from it—remember, last in, first out.

> 要从堆栈中删除项目，首先将堆栈顶部的项目复制到存储器中的寄存器或其他位置，然后将堆栈指针降低，以便指出以前是以前是该公司的最高项目堆。此过程称为从堆栈中弹出一个项目。如果您遵循[图 4-6]中的四个堆栈快照(＃07_9781119183938-CH04.XHTML＃C04-fig-0006)，您可以看到堆栈如何成长或缩小，因为项目被推到它上并从中弹出并从中弹出。将最后一个推入堆栈的项目是从中弹出的第一项

- 记住，最后，首先。

There are some variations on how stacks are implemented in any given architecture. An _ascending stack_, as just described, grows upwards in memory with each push by incrementing the stack pointer to the next higher memory location. A _descending stack_ grows downwards in memory with each push by decrementing the stack pointer to the next lower memory location. The ARM CPU stack can be configured to work either way, though by convention ARM stacks are descending. Some architectures assume that the stack pointer points to the first free memory location on the stack, whereas others assume that the stack pointer points to the last item pushed onto the stack. If the stack is empty, the stack pointer always points to the first available stack location. Again, ARM processors can be configured either way, but, by default, ARM stacks assume that the stack pointer points to the last item pushed.

> 关于如何在任何给定的体系结构中实现堆栈的情况有一些变化。如刚刚描述的那样，一个 _cascending stack_ 通过将堆栈指针递增到下一个更高的内存位置，在每次推动时都会向上增长。一个 _descending stack_ 通过将堆栈指针降低到下一个较低的内存位置，每次推动都会向下增长。ARM CPU 堆栈可以配置为无论哪种方式都可以工作，尽管通过惯例堆栈正在下降。一些体系结构假设堆栈指针指向堆栈上的第一个免费内存位置，而另一些则假设堆栈指针指向最后一个推向堆栈的项目。如果堆栈为空，则堆栈指针始终指向第一个可用的堆栈位置。同样，可以将 ARM 处理器配置为无论哪种方式，但是默认情况下，ARM 堆栈假设堆栈指针指向最后一个项目。

Stacks are used for temporary storage of both data items (often register values) and memory addresses during subroutine calls. A _subroutine_ is a sequence of actions in a program that is executed as a group and given a name. Any time the subroutine’s actions need to be executed, some other part of the program can _call_ it, meaning transfer execution to the subroutine until the subroutine’s work is finished. Then the subroutine returns execution to the part of the program that called it. In programming languages like C and Python, subroutines are called _functions_. We’ll have much more to say about subroutines and their role in programming in [Chapter 5](#08_9781119183938-ch05.xhtml).

> 堆栈用于临时存储数据项(通常是寄存器值)和子例程调用期间的内存地址。_subroutine_ 是程序中的一系列操作，该序列被作为组执行并给出了名称。每当需要执行子例程的操作时，程序的其他部分都可以 _call_ IT，这意味着将执行执行到子例程，直到子例程的工作完成为止。然后子例程将执行返回到调用它的程序的一部分。在 C 和 Python 等编程语言中，子例程称为 _Functions_。关于子例程及其在[第 5 章](%EF%BC%8308_9781119183938-CH05.XHTML)中的作用中，我们将还有更多的话要说。

Many computer architectures provide a dedicated instruction for calling a subroutine, which automatically pushes the program counter value to the stack before branching to the start address of the subroutine. When the subroutine is finished, the saved program counter (referred to as the return address) may be popped back into the program counter by another dedicated instruction, and the program continues on its way. If the subroutine wants to use a CPU register (which is likely already in use by whoever called the subroutine), it can push the existing value to the stack itself, and pop it back before returning.

> 许多计算机体系结构提供了一个专用指令来调用子例程，该指令在分支到子例程的起始地址之前将程序计数器值自动将其推向堆栈。子例程完成后，保存的程序计数器(称为返回地址)可以通过另一项专用指令将其弹出回到程序计数器中，并且该程序继续前进。如果子例程要使用 CPU 寄存器(任何称为子例程的人已经在使用的 CPU 寄存器)，则可以将现有值推向堆栈本身，并在返回之前将其弹出。

> [!NOTE]
> that although the ARM CPUs can choose to save subroutine return addresses on the stack manually, there is a faster way that doesn’t impose the time penalty of accessing system memory. As you see a little later in this chapter, return addresses are first stored in the link register (LR), allowing some leaf functions (those functions that do not call any functions in turn) to avoid stack accesses altogether.
> 虽然 ARM CPU 可以选择手动将子程序返回地址保存在堆栈上，但有一种更快的方法不会造成访问系统内存的时间损失。正如您在本章后面看到的那样，返回地址首先存储在链接寄存器 (LR) 中，允许一些叶函数(那些不依次调用任何函数的函数)完全避免堆栈访问。

Stacks are useful in that they can manage nested subroutine calls (subroutine calls made from within subroutines). Each time a new nested subroutine call is made, another layer of data and return addresses is added to the stack. Assuming that the stack has room, dozens or even hundreds of nested calls may be made. If the stack becomes full and no longer has room for additional values, an attempt to push anything on the stack causes a stack overflow. If there is no protection in place, for example from a memory management unit, data stored in memory areas adjacent to the stack are then overwritten, and program malfunctions occur.

> 堆栈很有用，因为它们可以管理嵌套的子例程调用(子例程从子例程内制成)。每次进行新的嵌套子例程调用时，都会将另一层数据和返回地址添加到堆栈中。假设堆栈有空间，可以进行数十个甚至数百个嵌套的呼叫。如果堆栈变已满，并且不再有额外值的空间，则尝试在堆栈上推任何东西会导致堆栈溢出。如果没有适当的保护，例如，从内存管理单元中，存储在堆栈附近的存储区域中的数据将被覆盖，并发生程序故障。

### System Clocks and Execution Time

As described earlier in the `[Digital Logic Primer](#07_9781119183938-ch04.xhtml#c04-sec-0005)` section, everything that goes on inside a sequential circuit like a CPU is synchronised to a pulse generator called the _clock_. Each pulse from the clock triggers a _clock cycle_, during which the CPU does some specific work. In very old CPUs, a single machine instruction might take anywhere from 4 clock cycles to 40 clock cycles to complete execution. Different instructions took different times, and some (like multiplication and division instructions) took a lot more time than others.

> 如前所述，在 `[数字逻辑引物](＃07_9781119183938-CH04.XHTML＃C04-SEC-0005)` 部分中，截面，如 CPU 这样的顺序电路内部的所有内容都同步到称为 _CLOCK_ 的脉冲发生器。时钟的每个脉冲都会触发一个 _Clock Cycle_，在此期间，CPU 进行了一些特定的工作。在非常旧的 CPU 中，单个机器指令可能需要从 4 个时钟循环到 40 个时钟周期才能完成执行。不同的说明花费了不同的时间，有些说明(例如乘法和划分说明)比其他时间花费更多的时间。

Why did different instructions take more time? In the early decades of computing, machine instructions were implemented within the CPU silicon as sequences of _microinstructions_, which are very simple mini-steps from which more complex instructions may be built. (Microinstructions are not accessible from outside the CPU.) Microinstructions conserved space on the CPU chip by allowing a large number of machine instructions to be implemented by combining a far smaller number of microinstructions. The digital logic that implements instructions is thus shared across many instructions, reducing the total transistor count required. The list of microinstructions required to perform each instruction is called _microcode_.

> 为什么不同的说明需要更多时间？在计算的几十年中，在 CPU 硅内实现了机器指令作为 *microinstructions* 的序列，这是非常简单的迷你步骤，可以从中构建更复杂的指令。(从 CPU 之外无法访问微型结构。)通过允许大量的机器指令通过组合少量的微型结构来实现 CPU 芯片上的微型结构。因此，在许多指令中共享实现指令的数字逻辑，从而减少了所需的总晶体管计数。执行每种指令所需的微观结构列表称为 *microcode*。

Executing machine instructions implemented as microcode adds significant time to instruction execution. Whenever possible, CPU designers hardwire instructions; that is, they implement each instruction directly with transistor logic dedicated to that single instruction. This takes more transistor budget and more room on the chip than microcode, but it produces _much_ faster instructions. As more transistors could be fitted on a single chip, more and more instructions were hardwired and fewer relied on microcode. Even so, until fairly recently, the use of microcode forced some instructions to take more clock cycles to complete than others. Figure 4-7 shows how this worked on early computers that had slow instructions due to microcode.

> 执行机器指令作为 Microcode 实施为指令执行增加了大量时间。只要有可能，CPU 设计师 Hardwire 说明；也就是说，他们直接使用专用于该指令的晶体管逻辑直接实施每个指令。这需要比 Microcode 更多的晶体管预算和更多的芯片空间，但是它会产生 *much* 的更快说明。由于可以将晶体管安装在单个芯片上，因此越来越多的说明被硬连线，更少依赖于微码。即便如此，直到最近，Microcode 的使用仍强迫一些说明比其他说明要做更多的时钟周期。图 4-7 显示了这是如何在由于微码引起的缓慢指令的早期计算机上起作用的。

> ![[FIGURE 4-7:](#07_9781119183938-ch04.xhtml#rc04-fig-0007) Machine instructions and clock cycles](./media/images/9781119183938-fg0407.png)

Higher transistor budgets allow more hardwired instructions. At some point, there are enough transistors on a chip to hardwire even complicated operations like multiplication and division. When all machine instructions are hardwired, all instructions execute in almost the same amount of time. The Holy Grail in CPU architecture has always been to execute all machine instructions in a single clock cycle. By 2000 or so that goal had mostly been achieved, and the chart of machine instructions versus clock cycles changed to something like Figure 4-8.

> 较高的晶体管预算允许更多的硬连线说明。在某个时候，芯片上有足够的晶体管，即使是复杂的操作，例如乘法和划分。当所有机器指令都是刻连接的时，所有指令在几乎相同的时间内执行。CPU 体系结构中的圣杯一直是在单个时钟周期内执行所有机器指令。到 2000 年左右的时间，该目标大部分已经实现，机器说明图与时钟周期的图表更改为图 4-8。

> ![[FIGURE 4-8:](#07_9781119183938-ch04.xhtml#rc04-fig-0008) Single-cycle machine instructions](./media/images/9781119183938-fg0408.png)

[Figure 4-8](#07_9781119183938-ch04.xhtml#c04-fig-0008) might make you think that instruction execution speed had hit a wall, and the only thing that could be done to get more instructions executed per second would be to increase the clock speed. You’d be wrong.

> [图 4-8](%EF%BC%8307_9781119183938-CH04.XHTML%EF%BC%83C04-FIG-0008) 可能会让您认为指令执行速度已经撞到了墙，而唯一可以完成每秒执行更多指令的方法就是提高时钟速度。你会错的。

### Pipelining

There’s a misunderstanding about CPU operation and clock speeds: the CPU does not operate as quickly as the clock speed demands. The clock speed can only be as fast as the CPU allows. The CPU needs a certain amount of time to do what it does.

> 关于 CPU 操作和时钟速度存在误解：CPU 的运行速度不如时钟速度所需的速度。时钟速度只能与 CPU 允许的速度一样快。CPU 需要一定时间才能完成它的工作。

If you look closely at how a CPU executes a single machine instruction, you see that it happens in a number of relatively distinct stages:

> 如果您仔细查看 CPU 如何执行单个计算机指令，您会发现它在许多相对不同的阶段发生：

1. Fetch the instruction from memory.

> 1.从内存中获取指令。2. Decode the instruction.

> 2.解码说明。3. Execute the instruction.

> 3.执行指令。4. Write back any changes made by the instruction to registers or memory.

> 4.写回到指令对寄存器或内存的任何更改。

When a machine instruction is executed in a single clock cycle, all four stages happen in one wave of transistor activity. This wave propagates through the CPU from the logic that deals with fetching and decoding instructions through the execution stage to the write-back logic. It’s tough to make that wave proceed more quickly, and the maximum clock speed will be determined by the time taken to get a signal down the longest path through all that logic.

> 当在单个时钟周期中执行机器指令时，所有四个阶段都会在一波晶体管活动中发生。该波通过 CPU 从逻辑中传播，该逻辑涉及通过执行阶段到写下逻辑的提取和解码指令。很难使波浪更快地进行，最大的时钟速度将取决于在所有逻辑中获得最长路径所花费的时间。

However, because the four stages occur in a specific order, you can treat each stage as a separate action. If you can engineer the logic that executes machine instructions such that all four stages take roughly the same amount of time, an interesting possibility opens up: you can overlap them. See Figure 4-9.

> 但是，由于四个阶段以特定顺序出现，因此您可以将每个阶段视为单独的动作。如果您可以设计执行机器指令的逻辑，以使所有四个阶段花费大致相同的时间，那么有趣的可能性就可以打开：您可以重叠它们。见图 4-9。

> ![[FIGURE 4-9:](#07_9781119183938-ch04.xhtml#rc04-fig-0009) Overlapping instruction execution](./media/images/9781119183938-fg0409.png)

In [Figure 4-9](#07_9781119183938-ch04.xhtml#c04-fig-0009), each stage of instruction execution takes one clock cycle. This means that the clock can be made faster, because executing an instruction now takes four ticks of the clock rather than one. This sounds like a step back in performance, even if the clock rate doubles. In fact, it sounds at first like a paradox: it takes four clock cycles to complete any single instruction, but one instruction is issued and another retires (that is, finishes its work) every clock cycle. The net result is that you still have instructions executing in a single, much faster clock cycle.

> 在[图 4-9](#07_9781119183938-ch04.xhtml#c04-fig-0009) 中，指令执行的每一阶段需要一个时钟周期。这意味着时钟可以变得更快，因为执行一条指令现在需要四个时钟滴答而不是一个。这听起来像是性能上的倒退，即使时钟速率加倍也是如此。事实上，这乍听起来像是一个悖论：完成任何一条指令需要四个时钟周期，但每个时钟周期一条指令发出，另一条指令退出(即完成其工作)。最终结果是您仍然有指令在一个更快的时钟周期内执行。

To get a sense of this, consider the sort of conveyor-belt pizza ovens that you see baking pizzas behind some pizza counters. The chef drops a raw pizza on the conveyor belt at the opening of the oven. Ten minutes later, the pizza emerges from the oven fully cooked and ready to sell. It takes 10 minutes to bake a pizza. However, there can be five pizzas making their way through the oven at any given time, and assuming that the chef keeps dropping raw pizzas on the belt, a finished pizza will emerge from the oven every two minutes. The first pizza takes 10 minutes. But once the oven is full, a pizza is finished every two minutes.

> 要了解这一点，请考虑一下您在一些披萨柜台后面看到的那种烤披萨的传送带披萨烤箱。厨师将生披萨放在烤箱开口处的传送带上。十分钟后，比萨从烤箱中完全煮熟并准备出售。烤一个披萨需要 10 分钟。然而，在任何给定时间都可能有五个比萨饼通过烤箱，假设厨师不断将生比萨饼放在传送带上，那么每两分钟就会有一个成品比萨饼从烤箱中出来。第一个披萨需要 10 分钟。但是一旦烤箱装满，每两分钟就会完成一个比萨饼。

Overlapping the execution of machine instructions in this way is called _pipelining_. First implemented in supercomputers during the 1980s, pipelining is now the norm in virtually all CPUs, even Microchip Technology’s low-cost PIC (Programmable Intelligent Computer) microcontrollers. Pipelining is second only to memory caching as a contributor to recent CPU performance improvements.

> 以这种方式重叠执行机器指令称为 _pipelining_。流水线于 1980 年代首次在超级计算机中实现，现在几乎已成为所有 CPU 的标准，甚至是 Microchip Technology 的低成本 PIC(可编程智能计算机)微控制器。作为最近 CPU 性能改进的贡献者，流水线仅次于内存缓存。

### Pipelining in Detail

To get a feel for what pipelining involves, take a look at a simple hypothetical non-pipelined processor, as shown in Figure 4-10. Flip-flops hold the current state of the processor (the current program counter (PC) and registers), and a cloud of logic calculates the next state ready to be fed back into the D inputs of the flip-flops in time for the next clock edge. You can roughly divide this cloud into three parts: Instruction Fetch (IF), Decode (DC), and Execute (EX). In the IF part is some logic that works out the next program counter (PC) value—there are no branches in the hypothetical processor example. The registers aren’t needed until the EX part. At the start of each cycle the outputs of some of the flip-flops change, and during the cycle a wave of activity propagates from left to right through the logic cloud. The maximum clock speed is determined by the time taken to traverse the longest path through the cloud’s logic. During the latter parts of the cycle, the left-hand bits of the cloud have reached a steady state, and are just supplying the results to the still-changing logic in the right-hand part. Wouldn’t it be nice to take a snapshot of that steady state and let the left-hand bits get on with something else, such as fetching the next instruction? A pipelined processor inserts pipeline latches (again, flip-flops) into the cloud to do precisely that.

> 要了解流水线涉及的内容，请看一个简单的假想非流水线处理器，如图 4-10 所示。触发器保持处理器的当前状态(当前程序计数器 (PC) 和寄存器)，逻辑云计算下一个状态，准备好及时反馈到触发器的 D 输入，以备下一次使用 时钟边沿。你可以粗略地将这片云分成三部分：指令获取(IF)、解码(DC)和执行(EX)。在 IF 部分是计算下一个程序计数器 (PC) 值的一些逻辑——在假设的处理器示例中没有分支。在 EX 部分之前不需要寄存器。在每个周期开始时，一些触发器的输出发生变化，并且在周期期间，一波活动通过逻辑云从左向右传播。最大时钟速度由遍历云逻辑最长路径所需的时间决定。在周期的后半部分，云的左侧部分已经达到稳定状态，并且只是将结果提供给右侧部分仍在变化的逻辑。拍摄该稳定状态的快照并让左侧位继续处理其他事情(例如获取下一条指令)不是很好吗？ 流水线处理器将流水线锁存器(同样是触发器)插入云中以精确地执行此操作。

> ![[FIGURE 4-10:](#07_9781119183938-ch04.xhtml#rc04-fig-0010) A simple non-pipelined processor](./media/images/9781119183938-fg0410.png)

Figure 4-11 shows a processor with pipeline latches. In the illustration, we split the logic cloud into three subclouds. The IF cloud just needs to get the instruction from memory and figure out the next PC value in time for the first set of pipeline latches to record the result. It can then get on with fetching the next instruction during the next cycle, while the DC cloud logic decodes the previous instruction using the pipeline latch data as its input. The register read/write is all done during the EX part because we weren’t using the registers until the EX part of the original cloud, and we want to be able to write a value to the register file during one cycle and use it in the next cycle.

> 图 4-11 显示了带有流水线锁存器的处理器。在图中，我们将逻辑云分成三个子云。中频云只需要从内存中获取指令，及时计算出下一个 PC 值，让第一组流水线锁存器记录结果。然后它可以在下一个周期继续获取下一条指令，而 DC 云逻辑使用流水线锁存器数据作为其输入来解码前一条指令。寄存器的读/写都是在 EX 部分完成的，因为我们直到原云的 EX 部分才使用寄存器，我们希望能够在一个周期内向寄存器文件写入一个值，并在 下一个循环。

> ![[FIGURE 4-11:](#07_9781119183938-ch04.xhtml#rc04-fig-0011) Adding latches to create a pipeline](./media/images/9781119183938-fg0411.png)

The speed of the CPU is again determined by the time required to traverse the longest path in any part of the cloud, but because we chopped up the cloud into three parts, what was once the longest path is bound to be quicker than in the non-pipelined processor shown in [Figure 4-10](#07_9781119183938-ch04.xhtml#c04-fig-0010).

> CPU 的速度再次取决于云层任何部分中最长路径所需的时间，但是由于我们将云切成三个部分，因此曾经是最长的路径势必要比非非非非非非非行径。

- [图 4-10](%EF%BC%8307_9781119183938-CH04.XHTML%EF%BC%83C04-FIG-0010) 中显示的流行处理器。

Looking at this, you might imagine that the EX stage is a bit `full` . All the interesting stuff, in particularly the arithmetic logic unit (ALU), lives there. If so, you’d be right: in a simple pipeline like this, the EX stage tends to contain the longest path, and thus constrains the pipeline. The next logical step, which you see in the ARM11 in the next section, is to subdivide the EX cloud into multiple smaller stages. This in turn requires you to cope with the issues that arise when the register file is read from and written to in different pipeline stages.

> 看着这一点，您可能会想象前阶段有点 `满` 。所有有趣的东西，尤其是算术逻辑单元(ALU)，都住在那里。如果是这样，您将是对的：在这样的简单管道中，EX 阶段倾向于包含最长的路径，从而限制管道。下一个逻辑步骤，您在下一节中的 ARM11 中看到的是将 EX 云细分为多个较小的阶段。反过来，这要求您应对从不同管道阶段读取并写入寄存器文件时出现的问题。

### Deeper Pipelines and Pipeline Hazards

How much overlap you can create in a given CPU depends primarily on how many stages a CPU’s instruction execution can be broken down to. Early on, 3

- and 4-stage pipelines were state of the art. As you will see later, the ARM11 CPU inside the original Raspberry Pi has an 8-stage instruction pipeline, and many of the current Intel processors have pipelines with 20 stages or more. A challenge for CPU designers pondering longer pipelines is that the different stages of instruction execution don’t all take the same amount of time: because it takes one clock cycle to perform each stage, the length of the clock cycle governing CPU operation is the time required to complete the slowest pipeline stage.

> 您**可以在给定的 CPU 中创建多少重叠，这主要取决于可以分解 CPU 的指令执行的数量**。早期，3 和 4 阶段的管道是最新的。正如您稍后会看到的那样，原始 Raspberry Pi 内部的 ARM11 CPU 具有 8 阶段的说明管道，并且许多当前的英特尔处理器具有 20 阶段或更高阶段的管道。CPU 设计师考虑更长管道的挑战是，指令执行的不同阶段并不全部花费相同的时间：因为要执行每个阶段需要一个时钟周期，因此计时循环的长度管理 CPU 操作是时间完成最慢的管道阶段所需。

Moving instructions through the pipeline at a continuous, uniform rate is crucial. Certain things can disrupt the smooth flow of instructions through a CPU pipeline. These are called pipeline hazards, and they can lead to delays in the pipeline. The delays are called pipeline stalls. There are three general categories of pipeline hazard:

> 以连续均匀的速率通过管道的移动指令至关重要。某些事情会通过 CPU 管道**破坏指令的平稳流动。这些称为管道危害**，它们可能导致管道延迟。延迟称为管道摊位。管道危害有三个一般类别：

- **Control hazards:** Caused by conditional branch instructions
- **Data hazards:** Caused by data dependency between instructions
- **Structural hazards:** Caused by resource conflicts

>

- **控制危害：**是由有条件分支指令引起的
- **数据危害：**由指令之间的数据依赖性引起的
- **结构性危害：**由资源冲突引起的

It’s easy to see how a conditional branch could disrupt a pipeline. If the first instruction shown in the pipeline in [Figure 4-9](#07_9781119183938-ch04.xhtml#c04-fig-0009) is a conditional branch instruction, and if (as is generally the case) the logic that resolves whether a branch is taken is located in the EX stage, you could end up branching away from sequential instructions that are already in the pipeline and have been fetched and decoded. Those instructions would no longer be in the path of program execution. So to preserve the illusion that you’re executing instructions one at a time they would need to be discarded and the pipeline would need to be refilled with instructions starting at the branch target address. Thinking back to the pizza-oven metaphor, if the order-taker submits an incorrect order to the chef, one or more pizzas already on their way through the oven may need to be discarded, and replacements placed on the belt. This leads to a pause before new, valid pizzas start to emerge from the oven—not to mention a loss of overall throughput.

> 很容易看到有条件的分支如何破坏管道。如果[图 4-9]中的管道中显示的第一个指令(＃07_978111919183938-CH04.XHTML＃c04-fig-0009)是有条件的分支指令，并且如果(通常是这种情况)是否解决了是否解决了是否解决了逻辑分支位于 EX 阶段，您最终可能会远离已经在管道中的顺序指令，并已被提取和解码。这些说明将不再是程序执行的道路。因此，为了保留幻想，即您一次需要丢弃指令，并且需要从分支目标地址开始的说明进行补充管道。回想一下披萨玻璃的隐喻，如果订单的订单向厨师提交了不正确的订单，则可能需要丢弃一个或多个通过烤箱的比萨饼，并置于腰带上。这会导致在新的有效的披萨开始从烤箱中出来之前停顿，更不用说整体吞吐量了。

One historical approach to control hazards is to abandon the illusion that you’re executing instructions one at a time and to say that our branches are delayed: sequential instructions that have entered the pipeline at the time when the branch is resolved always execute, regardless of whether the branch is taken. It is then up to the assembly-language programmer or high-level language compiler to find useful work to fill these branch delay slots.

> 控制危害的一种历史方法是放弃您一次执行指令的幻想，并说我们的分支机构被延迟了：在解决分支机构时输入管道的顺序指令始终执行，无论如何是否采用分支。然后，它可以通过组装语言程序员或高级语言编译器来找到有用的工作来填补这些分支延迟插槽。

This behaviour is uncommon, however. Most architectures attempt to mitigate the impact of pipeline hazards through two interrelated mechanisms: _branch prediction_ and _speculative execution_. Here, the CPU’s execution logic attempts to predict which of two possible branch destinations will be taken. The prediction is based on a cumulative history of branches taken in that part of the code. The CPU fetches instructions from the more likely destination before the actual result of the branch is known, and starts executing them speculatively. Recovering from an incorrect prediction involves killing the speculatively executed instructions before they reach a stage of the pipeline that can affect the outside world, generally by replacing them with _bubbles_ (no-op instructions, which do nothing). Speculative execution amounts to the CPU doing some guessing, and bad guesses are expensive. They incur a delay roughly proportional to the depth of the pipeline, which needs time to refill. A delay of 20 cycles is not unusual in a modern high-performance processor, so branch predictor improvements have become a major determinant of CPU performance.

> 但是，这种行为并不常见。大多数体系结构试图通过两种相互关联的机制来减轻管道危害的影响：_branch prediction_ 和 _speculative execution_。在这里，cpu 的执行逻辑尝试预测将采取两个可能的分支目的地中的哪个。该预测是基于该代码该部分中分支的累积历史。cpu 在已知分支的实际结果之前从更可能的目的地获取指令，并开始投机执行。从不正确的预测中恢复涉及杀死投机执行的指令，然后才能到达可能影响外界世界的管道阶段，通常是通过用 _bubbles_ (no-op 指令，无能为力)来代替它们。**投机性执行量相当于 cpu 做一些猜测，而错误的猜测很昂贵。它们会延迟与管道深度大致成正比**，这需要时间进行补充。在现代的高性能处理器中，**延迟 20 个周期并不罕见，因此分支预测器的改进已成为 cpu 性能的主要决定因素**。

Data dependence is more subtle. Suppose the result value from one instruction is needed as an operand by the next instruction in the pipeline. The second instruction may require the value before the first instruction has finished generating it. If you don’t stop the second instruction from proceeding through the pipeline it would end up using a value that is garbage or a leftover from some earlier calculation. This doesn’t happen in the simple pipelined processor described earlier, because reading the registers, computing the result and writing it back all occur in the EX stage. The registers are entirely consistent once the next instruction arrives at the EX stage. It’s only once you start to break the over-full EX stage apart (as almost all modern processors, including the ARM, do) that you need to worry.

> **数据依赖性更为微妙**。假设需要从管道中的下一个指令作为操作数作为操作数中的结果值。第二个指令可能需要在第一个指令完成生成之前的值。如果您不阻止第二个指令通过管道进行操作，则最终将使用垃圾或一些早期计算中剩余的值。这不会在前面描述的简单管道处理器中发生，因为阅读寄存器，计算结果并将其写回去，全部发生在 EX 阶段。一旦下一个指令到达 EX 阶段，寄存器将完全一致。只有您开始打破过度实现的阶段(几乎所有现代处理器，包括 ARM，做)，您需要担心。

> [!note]
> 感觉这本书和另外的那个 1000+ 的计算机架构可以结合起来看
> 相对而言，本书虽然篇幅上少了很多，但是内容和阐述上并不少呀！

Resource conflicts happen when two instructions in the pipeline need to access some CPU resource at the same time. For example, if two instructions in different pipeline stages need to access external memory via the cache system at the same time, one of these instructions must take priority over the other. A trivial example of this can occur between the IF stage reading instructions, and some other pipeline stage (the EX stage in our simple example) reading or writing data. This particular conflict may be partially resolved by splitting the unified level 1 cache into two separate caches: one for data and one for machine instructions. This is called a _modified Harvard architecture_, after Harvard’s early experimental computers that stored and accessed machine instructions and data separately. The ARM11 CPUs incorporate a modified Harvard architecture.

> 当管道中的两个指令同时访问某些 CPU 资源时，**资源冲突**就会发生。例如，如果不同管道阶段中的两个说明需要同时通过缓存系统访问外部内存，则其中一个指令必须优先考虑另一个说明。在 IF 阶段阅读指令和其他一些管道阶段(我们简单示例中的 EX 阶段)阅读或写入数据之间，可能会发生一个微不足道的例子。可以通过将统一级别的 1 个缓存分为两个单独的缓存来部分解决这一特殊冲突：一个用于数据，一个用于机器指令。这被称为 _修改的哈佛架构_，在哈佛的早期实验计算机分别存储和访问机器指令和数据之后。ARM11 CPU 结合了修改后的哈佛建筑。

Detecting and resolving data dependence and resource conflict hazards takes still more transistors on the silicon to solve. The general approach is for the instruction decode logic to identify when a hazard is about to occur in the pipeline; the hardware that performs this check is referred to as an _interlock_. If a fetched instruction represents a hazard of any kind, a bubble is inserted into the pipeline ahead of the problematic instruction. This generates a delay that allows earlier instructions to finish what they’re doing before they conflict with instructions coming up the pipe.

> 检测和解决数据依赖和资源冲突危害需要更多的晶体管解决。一般方法是指导说明逻辑以识别管道中何时发生危害。执行此检查的硬件称为 _interlock_。如果提取的指令代表任何形式的危险，则在有问题的指令之前将气泡插入管道中。这会产生一个延迟，该延迟允许较早的说明在与管道上的说明发生冲突之前完成他们正在做的事情。

### The ARM11 Pipeline

The pipeline in the ARM11 CPU is divided into eight stages, as shown in Figure 4-12. The pipeline isn’t quite as simple as the one shown in [Figure 4-9](#07_9781119183938-ch04.xhtml#c04-fig-0009). In addition to the pipeline being divided into eight different stages, there are three possible paths through the pipeline. Which path the execution takes depends on what type of instruction is executing.

> 如图 4-12 所示，ARM11 CPU 中的管道分为八个阶段。管道不像[图 4-9](%EF%BC%8307_9781119183938-CH04.XHTML%EF%BC%83C04-FIG-0009) 所示的管道那样简单。除了将管道分为八个不同的阶段外，整个管道还有三个可能的路径。执行所采用的路径取决于执行哪种类型的指令。

> ![[FIGURE 4-12:](#07_9781119183938-ch04.xhtml#rc04-fig-0012) The ARM11 pipeline](./media/images/9781119183938-fg0412.png)

The first four stages are identical, regardless of the instruction. However, when the instruction is issued, the decode logic chooses one of the three possible paths. Each category of instructions has its own pipeline path:

> 前四个阶段是相同的，无论说明如何。但是，当发出指令时，解码逻辑选择了三个可能的路径之一。每个指令都有自己的管道路径：

- **Integer execution path:** For most instructions that execute integer operations
- **Multiply-accumulate path:** For integer multiply instructions
- **Load/store path:** For load and store instructions

>

- **整数执行路径：**对于大多数执行整数操作的指令
- \*\*乘数
- 蓄积路径：\*\*用于整数乘数指令
- ** load/store 路径：**用于加载和存储指令

The stages shown in the figure and their abbreviations are:

> 图中所示的阶段及其缩写为：

- **FE1:** The first fetch stage; the address for the instruction is requested and the instruction is received.
- **FE2:** Branch prediction is done in this stage.
- **Decode:** The instruction is decoded.
- **Issue:** The registers are read and the instruction is issued.
- **Shift:** Any required shift operations are done in this stage.
- **ALU:** Any required integer operations are done in the ALU in this stage.
- **Saturate:** Integer results are saturated; that is, forced to fall within integer range.
- **MAC1:** The first stage for execution of multiply instructions.
- **MAC2:** The second stage for execution of multiply instructions.
- **MAC3:** The third stage for execution of multiply instructions.
- **WBex:** Whatever register data was changed by the instruction is written back to the registers. WBex is the last stage on both the integer execution path and the multiply-accumulate path.
- **Address:** Used to generate addresses used by the instruction to access memory.
- **DC1:** The first stage during which the address is processed by the data cache logic.
- **DC2:** The second stage during which the address is processed by the data cache logic.
- **WBls:** The final stage in the load/store path writes back any changes made to memory locations.

>

- ** fe1：**第一个提取阶段；请求该说明的地址并收到指令。
- ** fe2：**分支预测在此阶段进行。
- **解码：**指令已解码。
- **问题：**寄存器已阅读并发出指令。
- **移位：**在此阶段进行任何必需的班次操作。
- ** alu：**在此阶段，在 ALU 中进行任何必需的整数操作。
- **饱和：**整数结果饱和；也就是说，被迫属于整数范围。
- ** mac1：**执行乘法指令的第一阶段。
- ** mac2：**执行乘法指令的第二阶段。
- ** mac3：**执行乘法指令的第三阶段。
- ** WBEX：**通过指令更改的任何注册数据都写回寄存器。WBEX 是整数执行路径和多元蓄电路径的最后阶段。
- **地址：**用于生成指令使用的地址以访问内存。
- ** DC1：**数据缓存逻辑处理地址的第一阶段。
- ** dc2：**第二阶段通过数据缓存逻辑处理地址。
- ** wbls：**负载/商店路径中的最后阶段写回 Mem 位置的任何更改。

Making things yet more complex is the fact that the integer execution path and the multiply-accumulate path are handled by the integer execution unit, and the load/store path is handled by the separate load/store unit. An _execution unit_ is a CPU subsystem that handles the `work` of an instruction—that is, integer maths or logical operations, memory access and so on. If a floating point coprocessor is present in the core, the coprocessor’s own pipeline, not shown here, handles execution once the instruction is issued. (We’ll explain coprocessors in more detail later on, in the section `[Coprocessors](#07_9781119183938-ch04.xhtml#c04-sec-0043).` )

> 使事情变得更加复杂的是，整数执行路径和多重蓄电路径由整数执行单元处理，并且负载/存储路径由单独的负载/存储单元处理。*execution Unit* 是一个处理指令 `工作` 的 CPU 子系统，即整数数学或逻辑操作，内存访问等。如果核心中存在浮点协处理器，则协处理器自己的管道(未显示)在发出指令后处理执行。(我们将在稍后在 ` [合并器](%EF%BC%8307_978111919183938-CH04.XHTML%EF%BC%83C04-SEC-0043)中进行更详细的解释。

### Superscalar Execution

As it turns out, still more performance can be wrung from the pipelining idea. A mechanism called _superscalar execution_ appeared towards the end of the 1980s. A superscalar architecture has an instruction pipeline like the one described in the previous section, as nearly all CPUs do today. However, a superscalar CPU issues more than one instruction for execution at the same time. Once issued, the instructions execute simultaneously. With superscalar CPUs, the execution of instructions goes beyond overlapping, to true parallelism. A superscalar pipeline is shown in Figure 4-13.

> 事实证明，管道构想的想法可能会引起更多的性能。1980 年代末，出现了一种称为 *superscalar execution* 的机制。SuperScalar 体系结构具有前一节中所述的指令管道，就像今天几乎所有 CPU 所做的那样。但是，SuperScalar CPU 同时发出了多个执行指令。发行后，指令同时执行。使用 SuperScalar CPU，指令的执行不仅仅是重叠，而是真正的并行性。超量表管道如图 4-13 所示。

> ![[FIGURE 4-13:](#07_9781119183938-ch04.xhtml#rc04-fig-0013) Superscalar execution](./media/images/9781119183938-fg0413.png)

In a simple case like this, a superscalar CPU fetches two instructions from memory and examines them to determine whether they can be run in parallel. If so, the CPU parcels out execution of both instructions to dual execution units. The execution units are _not_ complete processor cores. They handle the work of the instruction only and specialise in integer maths and logic, floating point maths and vector maths. The CPU strives to keep all the execution units busy as much of the time as possible.

> 在这样的简单情况下，SuperScalar CPU 从内存中获取了两个说明，并检查它们以确定是否可以并行运行。如果是这样，CPU 将两个指令执行到双执行单元。执行单元是 *not* 完整的处理器内核。他们仅处理教学的工作，并专门研究整数数学和逻辑，浮点数学和矢量数学。CPU 努力使所有执行单元尽可能多地忙。

The basic mechanism is the same as with pipelining: the CPU checks for data dependencies in the instruction stream, such as whether an instruction provides a data value to the instruction that follows it. If such a dependency exists, the two instructions cannot be issued at once, and a pipeline stall occurs. For example, if one instruction adds a value to Register 4, and the next instruction in sequence multiplies the contents of Register 4 by still another value, the instructions cannot be issued together to run in parallel because the second instruction depends on data calculated by the first.

> 基本机制与管道上的基本机制相同：CPU 检查指令流中的数据依赖项，例如指令是否为随后的指令提供了数据值。如果存在这样的依赖性，则不能一次发出这两个说明，并且会发生管道失速。例如，如果一项指令添加了寄存器 4 的值，而下一个指令按序列乘以寄存器 4 的内容乘以另一个值，则不能同时发送指令以并行运行，因为第二个指令取决于数据计算得出的数据第一的。

As with pipelining, the compiler that generates program code has the power to look for data dependencies and rearrange instructions so that two consecutive instructions do not depend on one another in ways that would trigger an interlock; that is, a situation where one instruction gets ahead of another on which it relies for data. These optimisations have become less important lately, because recent superscalar CPUs allow _out-of-order_ execution. Such CPUs have the ability to dynamically reorder the incoming instruction stream to maximise the amount of achievable parallelism and minimize data dependencies that cause interlocks.

> 与管道上一样，生成程序代码的编译器有能力查找数据依赖项和重新排列指令，以便两个连续指令不以触发互锁的方式相互依赖。也就是说，一种指令比另一个指令依赖于数据的情况。这些优化最近变得不那么重要，因为最近的超级 cpus 允许 *out-forder* 执行。**这样的 CPU 具有动态重新排序传入指令流的能力，以最大程度地提高可实现的并行性量并最大程度地减少引起互锁的数据依赖性。**

> [!note]
> 这个技术引入实时系统？

Superscalar execution, and particularly out-of-order execution, is expensive in terms of transistor logic. In addition to the burden of providing duplicate execution units, the logic to implement dependency checks becomes increasingly complex. In theory it is possible for a CPU to issue more than four instructions at once, but at around this point designers generally reach a point of diminishing returns.

> 就晶体管逻辑而言，超大标准执行，尤其是排序执行，价格昂贵。除了提供重复执行单元的负担外，实施依赖性检查的逻辑越来越复杂。从理论上讲，CPU 可以一次发出四个以上的说明，但是在这一点上，设计师通常达到回报率降低的点。

The ARM11 microarchitecture does not support superscalar execution. Superscalar capability was introduced into the ARM family with the `Cortex A` family of processors, some of which are capable of issuing four instructions at once. (More on Cortex later in this chapter.)

> ARM11 微体系结构不支持 SuperScalar 执行。SuperScalar 能力被引入了 ` Cortex A` 处理器家族中的 ARM 家族，其中一些能够一次发出四个指示。(在本章后面稍后有关皮质的更多信息。)

### More Parallelism with SIMD

Superscalar execution is difficult to implement but easy to describe: multiple instructions are issued at the same time, and they execute in parallel. Modern CPUs support another type of parallelism: instructions that operate on multiple data items at once. As a class, these are called single-instruction, multiple data (SIMD) instructions. Most computer architectures have their own SIMD instructions, which are generally not identical to or even compatible with those of other architectures.

> 超级执行很难实现，但易于描述：同时发出多个指令，并且它们并行执行。现代 CPU 支持另一种类型的并行性：一次在多个数据项上运行的指令。作为一类，这些称为单个指令，多个数据(SIMD)指令。大多数计算机架构都有自己的 SIMD 说明，通常与其他体系结构不相同甚至兼容。

SIMD is best explained by an example. Ordinary addition instructions in a 32-bit microarchitecture like ARM11 add one 32-bit value to another 32-bit value in a single operation. Other instructions perform subtraction in the same way. Certain common tasks in computing require that a great many additions (or other arithmetic operations) be performed as quickly as possible. Adjusting colour on a display is one such challenge. If you have a 1600-×-1200 pixel display, you have to process almost two million pixels. Each pixel, furthermore, requires three or four additions or subtractions to adjust colour. That’s a lot of maths, even if it’s simple and repetitive maths.

> SIMD 最好用一个示例来解释。像 ARM11 这样的 32 位微体系结构中的普通添加说明将一个 32 位值添加到单个操作中的另一个 32 位值。其他说明以相同的方式执行减法。计算中的某些常见任务要求尽可能快地执行许多添加(或其他算术操作)。在显示屏上调整颜色就是这样的挑战。如果您有 1600-×-1200 像素显示屏，则必须处理近 200 万像素。此外，每个像素都需要三到四个添加或减法来调整颜色。即使它简单而重复的数学，这是很多数学。

With traditional machine instructions, the only way to do all those additions and subtractions is one at a time (see Figure 4-14). Adjusting the whole group of pixels requires a program loop that takes one pass to process each value. (We’ll describe program loops in more detail in [Chapter 5](#08_9781119183938-ch05.xhtml).) Such a loop requires one branch per value, as well as an instruction to load the value and another to write the changed value back.

> 使用传统的机器说明，完成所有这些添加和减法的唯一方法是一次一次(见图 4-14)。调整整个像素组需要一个程序循环，该循环需要一个通过来处理每个值。(我们将在[第 5 章]中更详细地描述程序循环(＃08_978111919183938-CH05.XHTML)。)这样一个循环需要每个值一个分支，以及一个指令加载值，而另一个要编写更改的值背部。
> ![[FIGURE 4-14:](#07_9781119183938-ch04.xhtml#rc04-fig-0014) Processing one value at a time](./media/images/9781119183938-fg0414.png)

There are tricks to minimise the number of branches required in such a loop, but tricks save only so much, and they come at the cost of additional instructions and additional memory. If you have to process two million pixels, it all adds up, and not in a good way.

> 有一些技巧可以最大程度地减少这种循环中所需的分支数量，但是技巧仅节省了很多钱，它们以其他说明和其他内存为代价。如果您必须处理 200 万像素，那么所有这些都会加起来，而且不是很好。

SIMD instructions are designed to do the same work on more than one data value at a time. Whereas regular instructions operate on scalars (single values), we say that SIMD instructions operate on _vectors_. A vector is simply a one-dimensional array of data values arranged such that a given architecture’s SIMD instructions can act on them. Vectors are typically from two to 16 data values in length, with a width (the number of bits in each value) varying from architecture to architecture.

> SIMD 说明旨在一次对多个数据值进行相同的工作。常规说明在标量(单个值)上运行，但我们说 SIMD 指令在 *vectors* 上运行。向量只是一维数据值的一维数组，以使给定体系结构的 SIMD 指令可以对它们作用。向量通常从两个到 16 个数据值长度，宽度(每个值中的位数)因体系结构而异。

In many computer architectures, a single SIMD instruction performs four operations (addition, subtraction multiplication and division) at once, in parallel. In some computer architectures it may be more than four operations, but the principle is the same: a vector of four values is loaded from memory into registers. A SIMD instruction performs an operation on all four values in the vector simultaneously. Then the entire vector is written back to memory. Figure 4-15 illustrates this.

> 在许多计算机架构中，单个 SIMD 指令同时同时执行四个操作(添加，减法和除法)。在某些计算机体系结构中，它可能超过四个操作，但是原理是相同的：四个值的向量从内存中加载到寄存器中。SIMD 指令同时对向量中的所有四个值执行操作。然后，整个向量写回 Mem。图 4-15 说明了这一点。
> ![[FIGURE 4-15:](#07_9781119183938-ch04.xhtml#rc04-fig-0015) How SIMD instructions work](./media/images/9781119183938-fg0415.png)

What would have taken four separate additions or subtractions is now accomplished with only one, saving three clock cycles. Better yet, in most architectures there are associated SIMD instructions that load and save four memory values at once.

> 现在只用一个单独的添加或减法来完成四个单独的添加或减法，从而节省了三个时钟周期。更好的是，在大多数体系结构中，有关联的 SIMD 指令一次加载并保存四个内存值。

Why build SIMD machines instead of increasing the superscalar issue width of the processor and allowing the programmer to stick with instructions that operate on scalars? The key benefit of SIMD is that the cost, in terms of time and energy, of fetching and decoding a SIMD instruction is shared across several computations. Because the programmer explicitly declares that the computations are independent by using a SIMD instruction, there is no need for expensive interlock logic to detect and work around dependencies that now cannot occur.

> 为什么要构建 SIMD 机器，而不是增加处理器的超级标准问题宽度并允许程序员坚持使用标量的指令？SIMD 的关键好处是，在时间和能量方面，获取和解码 SIMD 指令的成本在几个计算中共享。由于程序员明确声明了通过使用 SIMD 指令独立的计算，因此无需昂贵的互锁逻辑来检测和解决现在无法发生的依赖关系。

It’s not immediately obvious to beginners what SIMD instructions are used for but, as it turns out, the mathematics of sound and graphics (especially 3D graphics and video) requires a lot of repetitive maths on long sequences of values. A SIMD instruction can perform mathematical operations on long sequences of values at once. SIMD instructions can radically improve the performance of code that handles tasks such as encoding and decoding sound and video and managing 3D graphics.

> 对于初学者来说，SIMD 指令的目的并不是很明显，但是事实证明，声音和图形的数学(尤其是 3D 图形和视频)需要大量的重复数学，以长期的价值序列。SIMD 指令可以一次对长序列进行数学操作。SIMD 指令可以从根本上提高处理任务的代码性能，例如编码和解码声音和视频以及管理 3D 图形。

The ARM11 core in the original Raspberry Pi supports SIMD instruction execution in a limited way: a 32-bit data word is loaded as always, but the SIMD instructions treat each of the 4 bytes within the word as a separate value. This obviously limits the size of the values that may be processed using SIMD, though a great deal in graphics and audio processing can be done with 8-bit quantities.

> 原始 Raspberry Pi 中的 ARM11 核心以有限的方式支持 SIMD 指令执行：32 位数据单词一如既往地加载，但是 SIMD 指令将单词中的 4 个字节中的每个字节视为单独的值。这显然限制了使用 SIMD 处理的值的大小，尽管可以使用 8 位数量进行图形和音频处理的大量。

In the newer ARM Cortex CPUs, there is a coprocessor called NEON, which provides SIMD instructions that operate on multiple quantities stored in special 128-bit registers. This allows throughput over twice that of the SIMD instructions in the ARMv6 instruction set. You can read more on NEON a little later, in connection with ARM Cortex.

> 在较新的 ARM Cortex CPU 中，有一个名为 NEON 的协处理器，该协助程序提供了 SIMD 指令，该说明以多种数量存储在特殊的 128 位寄存器中。这允许吞吐量超过 ARMV6 指令集中的 SIMD 指令的两倍。您可以稍后再了解与 Arm Cortex 有关的更多信息。

### Endianness

The first mass-market microprocessors were 8-bit units, which operated on data 8 bits (1 byte) at a time. They also read from and wrote to system memory 1 byte at a time. Later CPUs raised this to 16 bits and then 32 bits, with many architectures now reading and writing 64 bits at a time. Accessing multiple bytes from memory in a single read or write raises a non-obvious question: how are those multiple bytes ordered in memory? If a 4-byte or 8-byte quantity is read from memory, how does the CPU interpret those bytes?

> 第一个大众市场微处理器是 8 位单元，一次在数据 8 位(1 个字节)上操作。他们还一次阅读并写入系统内存 1 字节。后来，CPU 将其提高到 16 位，然后将 32 位提高，现在有许多架构一次阅读和编写 64 位。从单个读取或写入中，从内存中访问多个字节会提出一个不太明显的问题：这些多个字节如何在内存中排序？如果从内存中读取 4 字节或 8 字节数量，则 CPU 如何解释这些字节？

This issue is called _endianness_, so named because of a bit of sly satire in Jonathan Swift’s novel _Gulliver’s Travels_, where the Lilliputians argue bitterly about whether to crack a soft-boiled egg on the wide ( `big` ) or narrow ( `small` ) end. It’s an important issue in computer architectures, if not in eggs. During this discussion, refer to Figure 4-16.

> 这个问题称为 *endianness*，因此之所以被命名，是因为在乔纳森·斯威夫特(Jonathan Swift)的小说_gulliver 的旅行中有些狡猾的讽刺，在那里，利利普特人(Lilliputians)在那儿激烈地争论是要在宽( `大` )还是狭窄( `小` )上裂开一个肥大的鸡蛋。) 结尾。这是计算机架构(即使不是鸡蛋)的重要问题。在讨论中，请参阅图 4-16。
> ![[FIGURE 4-16:](#07_9781119183938-ch04.xhtml#rc04-fig-0016) Big-endian vs. little-endian architectures](./media/images/9781119183938-fg0416.png)

[Figure 4-16](#07_9781119183938-ch04.xhtml#c04-fig-0016) shows a short run of computer memory. Each location has an address and stores 1 byte of data. Address and data values are given in hexadecimal form. A modern 32-bit CPU like the ARM11 core reads or writes 4 bytes during every memory access. If those 4 bytes represent a 32-bit number, you need to know the order in which the 4 bytes appear in the number. In a columnar notation (see [Chapter 2](#05_9781119183938-ch02.xhtml) for a recap) the least significant column of a number is by convention shown on the right, and the most significant column is shown on the left. `Most significant` here means `highest value` . The rightmost column in 32-bit binary notation has the value of 2<sup>0</sup>, or 1. The leftmost has a value of 2<sup>31</sup>, or 2,147,483,648. (Refer to [Table 3-1](#06_9781119183938-ch03.xhtml#c03-tbl-0001) in [Chapter 3](#06_9781119183938-ch03.xhtml).) Order matters!

> [图 4-16](%EF%BC%8307_9781119183938-CH04.XHTML%EF%BC%83C04-FIG-0016) 显示了一个简短的计算机存储器。每个位置都有一个地址，并存储 1 个数据字节。地址和数据值以十六进制形式给出。像 ARM11 核心这样的现代 32 位 CPU 在每个内存访问过程中读取或写 4 个字节。如果这些 4 个字节代表一个 32 位编号，则需要知道 4 个字节出现在数字中的顺序。在列表示法(请参阅[第 2 章](%EF%BC%8305_9781119183938-CH02.XHTML)中，有关一个 recap)，有关一个数字的最低列是按右图显示的一个数字的最低列，最显着的列显示在左侧。这里的 `最重要` 是指 `最高价值` 。32 位二进制符号中的最右列的值为 2 <sup> 0 </sup>，或 1。最左边的值为 2 <sup> 31 </sup>，或 2,147,483,648。(请参阅[＃06_9781119183938-CH03.XHTML＃C03-TBL-0001)[＃06_978111919183938-CH03.XHTML-0001)。

In a little-endian architecture, the least significant byte of a multi-byte value is stored at the lowest address of the four in memory. The most significant byte is stored at the highest address of the four. In [Figure 4-16](#07_9781119183938-ch04.xhtml#c04-fig-0016), the data at address 0x10000 is 0xE7. In a little-endian system, the value 0xE7 is interpreted as the least significant byte. In a big-endian system, the value 0xE7 would be the most significant byte. This changes the value of the 32-bit number radically: in a little-endian system, the hexadecimal value 0x00 11 04 E7 is 1,115,367 in decimal. In a big-endian system, the hex number changes to 0xE7 04 11 00, which in decimal form is 3,875,803,392.

> 在小型架构中，多字节值的最低字节存储在四个内存中的最低地址。最重要的字节存储在四个中的最高地址。在[图 4-16](%EF%BC%8307_978111919183938-CH04.XHTML%EF%BC%83C04-FIG-0016) 中，地址 0x10000 的数据为 0xE7。在小型系统中，值 0xE7 被解释为最不重要的字节。在大型系统中，值 0xE7 将是最重要的字节。这从根本上改变了 32 位数的值：在小型系统中，十六进制值 0x00 11 04 E7 在十进制中为 1,115,367。在大型系统中，十六进制的数字更改为 0xE7 04 11 00，小数点为 3,875,803,392。

Although abstruse technical issues favour little-endian architectures over big-endian ones, for the most part little-endian architecture has been a convention. Most recent microprocessor architectures, including Intel’s x86, have been little endian. (Motorola’s 6800 and 68000 and Sun Microsystems’ SPARC are notable exceptions.) Mainframe architectures like IBM’s venerable System 360 are often big endian.

> 尽管抽象的技术问题偏爱小型建筑，而不是大型建筑，但在大多数情况下，小型建筑都是一种惯例。包括英特尔的 X86 在内的最新微处理器体系结构是小的 Endian。(摩托罗拉的 6800 和 68000 和太阳微型系统的 SPARC 是显着的例外。)大型机架构(例如 IBM 的尊贵系统 360)通常是大型末日。

By default, the ARM11 core is little endian. However, ARM architectures since ARMv3 offer an interesting feature: the endianness may be configured as either little or big as needed. This is called _bi-endianness_. Because computer networks are by convention big endian, allowing a CPU to interpret network data as big endian yields performance improvements, because the bytes of a value do not need to be re-ordered by the CPU.

> 默认情况下，ARM11 核心是小的。但是，由于 ARMV3 提供了一个有趣的功能，因此 ARM 体系结构可以根据需要而配置为少或大。这称为 *bi-endianness*。因为计算机网络是由大型恩德尼亚人进行的，因此允许 CPU 将网络数据解释为大元素可以提高性能，因为值的字节不需要由 CPU 重新订购。

The other place endianness matters crucially is in data files. Applications that operate on byte-resolution binary data in memory need to know whether a CPU has written that data to disk in big-endian or little-endian chunks. If a data file is moved to a system using a different endianness, the CPU may load the data in a different order, and an application that accesses the file may not be able to interpret its data correctly.

> 另一个地方的 endianness 在数据文件中至关重要。在内存中使用字节分辨率二进制数据的应用程序需要知道 CPU 是否已将数据写入大型或小型块中的磁盘。如果数据文件使用不同的 endianness 移动到系统，则 CPU 可以按不同的顺序加载数据，并且访问该文件的应用程序可能无法正确解释其数据。

## Rethinking the CPU: CISC vs. RISC

Around 1980, a new concept, which came to be called _reduced instruction set computing_ (RISC), emerged from labs at IBM’s Thomas J. Watson Research Center, the University of California at Berkeley and Stanford University. The results of these research programs would eventually be developed into the popular POWER (Performance Optimization with Enhanced RISC), SPARC (Scalable Processor Architecture) and MIPS (Microprocessor without Interlocked Pipeline Stages) architectures, respectively, and they embodied a radically different vision of how CPUs should be designed compared to the state of the art at the time. The term _complex instruction set computing_ (CISC) was coined retroactively to refer to these prior architectures. The battle between RISC and CISC architectures has been one of the defining features of the computer industry over the last three decades.

> 1980 年左右，一个新概念被称为 *reduced 指导集 Computing*(RISC)，它来自 IBM 的 Thomas J. Watson Research Center，加利福尼亚大学伯克利分校和斯坦福大学的实验室。这些研究计划的结果最终将被发展为流行的能力(通过增强的 RISC 的性能优化)，SPARC(可扩展处理器体系结构)和 MIPS(无连锁管道阶段的微处理器)体系结构，并且它们对如何体现了如何对如何体现出对如何如何体现的愿景。CPU 应与当时的最新技术相比。术语* Complex 指令集 Computing*(CISC)是追溯创造的，以参考这些先前的体系结构。在过去的三十年中，RISC 和 CISC 架构之间的战斗一直是计算机行业的决定性特征之一。

By the mid-1970s, the design of high-performance CPUs for use in minicomputers and mainframes had come to focus on two key goals: increasing code density and bridging the semantic gap with the high-level programming languages of the day. Both of these goals led designers to pack more and more functionality into individual machine instructions. A look at instruction sets from the dawn of computing shows some wild and peculiar examples: one first-generation CPU had an instruction that triggered a camera aimed at an early video display; another had an instruction that raised the protective lid from the attached system printer. And remember, these weren’t library routines or utility programs. These were genuine, wired-into-the-CPU machine instructions.

> 到 1970 年代中期，用于微型计算机和大型机的高性能 CPU 的设计已重点介绍了两个关键目标：增加代码密度并用当天的高级编程语言弥合语义差距。这两个目标都使设计人员可以将越来越多的功能包装到单个机器指令中。查看计算曙光中的指令集显示了一些狂野和特殊的示例：第一代 CPU 的指令触发了针对早期视频显示的相机；另一个指令将保护性盖从附件的打印机提高。请记住，这些不是库例程或实用程序。这些是真正的有线式 CPU 机器说明。

The requirement for increased code density was driven by the high cost and low relative speed of memory. As explained in [Chapter 3](#06_9781119183938-ch03.xhtml), for most of the history of computing, system memory was horribly expensive. When memory was expensive, memory systems were necessarily small. The total physical address space of the DEC PDP-8 minicomputer was only 4,096 bytes. Back when the PDP-8 was designed, this was all the memory that a typical purchaser could afford. Larger programs could be run, but only after operating systems began to implement virtual memory (see [Chapter 3](#06_9781119183938-ch03.xhtml)).

> 增加代码密度的要求是由高成本和低相对速度的驱动。如[第 3 章](%EF%BC%8306_9781119183938-CH03.XHTML)所述，对于大多数计算历史记录，系统内存非常昂贵。当内存昂贵时，内存系统一定很小。DEC PDP-8 微型计算机的总物理地址空间仅为 4,096 个字节。在设计 PDP-8 时，这是典型购买者负担得起的所有 Mem。可以运行较大的程序，但只有在操作系统开始实现虚拟内存之后(请参阅[第 3 章](%EF%BC%8306_9781119183938-CH03.XHTML))。

Under these conditions, there was obviously an advantage in keeping programs physically short. Complex, semantically rich instructions help to reduce instruction count: a snap-the-camera machine instruction requiring 2 bytes in memory could take the place of a snap-the-camera subroutine that might require 50 or 100 bytes in memory. By the mid

- to late-1970s, the availability of high-capacity DRAM chips had reduced the imperative to pursue code density at all costs. (As an aside, it was inexpensive memory, as much as inexpensive CPUs, that made the first personal computers possible: a $100 CPU chip won’t help you much if memory costs $5,000 per kilobyte.)

> 在这些条件下，显然可以使程序保持短缺是有优势的。复杂的，语义上丰富的指令有助于减少指令计数：需要 Mem 中 2 个字节的快照机器指令可能取代可能需要 50 或 100 字节的 snap-ph-semer subroutine。到 1970 年代中期到 1970 年代中期，高容量 DRAM 芯片的可用性已减少了不惜一切代价追求代码密度的当务之急。(顺便说一句，这是便宜的 Mem，虽然廉价的 CPU，这使得第一台个人计算机成为可能：如果内存的价格为每千千万美元，则为 100 美元的 CPU 芯片对您无济于事。)

The term `semantic gap` refers to the difference between the behaviours expressible in high-level languages (nested loops, function calls, multidimensional array indexing) and those provided by the underlying hardware (conditional and unconditional unstructured branches, the ability to load and store from addresses in memory). Microcoding allowed designers to create instructions that directly implemented high-level features at the machine language level, closing the gap. A compiler, or a careful low-level programmer, could achieve significant performance gains by using these instructions, but in practice most compilers chose to ignore them for reasons of simplicity and portability between architectures. A rough 80/20 rule was observed, in which 20% of instructions were used 80% of the time, and many were not used at all. Tantalisingly, the `reduced instruction set` used by compilers bore a close resemblance to the microinstructions provided inside the CPU.

> `语义差距` 一词是指在高级语言中表达的行为之间的差异(嵌套循环，函数呼叫，多维数组索引)与基础硬件(条件和无条件的无结构分支，加载和存储的能力，可以加载和存储的能力)所提供的行为。从内存中的地址)。微编码允许设计人员创建指令，该指令直接在机器语言级别实现高级功能，从而缩小差距。编译器或仔细的低级程序员可以通过使用这些说明获得显着的性能提升，但是实际上，大多数编译器选择出于架构之间的简单性和可移植性的原因而忽略它们。观察到了一个粗略的 80/20 规则，其中有 80％的时间使用了 20％的说明，而许多说明完全没有使用。诱人的是，编译器使用的 `减少指令集` 与 CPU 内部提供的微观建筑非常相似。

The earliest experimental RISC machines exploited this insight by providing only a very small instruction set comprising very simple instructions; they can be thought of as CPUs that simply exposed their microinstructions to the outside world. It takes more RISC instructions to implement a program, but program performance was excellent in comparison with CISC architectures; because RISC instructions ran very quickly, their simple execution made it easier to apply techniques like pipelining, and compilers hadn’t been using the more complex instructions anyway.

> 最早的实验 RISC 机器通过仅提供一个非常简单的说明来利用这种见解。可以将它们视为 CPU，只是将其微观建筑暴露于外界。它需要更多的 RISC 指令来实施程序，但是与 CISC 架构相比，程序性能非常出色。由于 RISC 指令很快运行，因此他们的简单执行使应用程序等技术变得更加容易，而且编译器并未使用更复杂的说明。

One distinguishing feature of RISC CPUs has always been that all or nearly all of their instructions are implemented in hardwired logic. Indeed, today microcode has been banished from the internals of even the main surviving CISC architecture—Intel x86. Since the Netburst microarchitecture was introduced in 2000, Intel processors have operated internally on RISC-like micro-ops, with legacy CISC instructions translated to independently issued micro-ops at the very front of the pipeline.

> RISC CPU 的一个显着特征一直是，其所有或几乎所有指令均以硬线逻辑实现。的确，今天的 Microcode 也被从主要幸存的 CISC 建筑的内部驱逐出境

- Intel X86。自从 2000 年推出了 Netburst 微观结构以来，英特尔处理器已在 RISC 样微型 OPS 内部进行操作，传统的 CISC 说明转换为管道前部的独立发行的微型 OPS。

At the same time RISC processors have added instruction-set features in search of incremental performance and, ironically, code density, to the point that the once-sharp distinction between RISC and CISC has become thoroughly blurred. Much of the original motivation for simplifying instruction sets was motivated by a desire to repurpose limited transistor budgets toward new performance features, such as cache and greatly expanded register sets. As transistor budgets exploded during the 1990s, instruction set expansion became possible again. Today, many RISC architectures (including ARM) have roughly the same number of instructions as their CISC counterparts.

> 同时，RISC 处理器添加了指令集功能，以寻求增量性能，并且具有讽刺意味的是代码密度，以至于 RISC 和 CISC 之间曾经相处的区别已被彻底模糊。简化教学集的许多原始动机都是出于重新利用有限的晶体管预算来推向新的性能功能的渴望，例如缓存和大大扩展的寄存器集。随着晶体管预算在 1990 年代的爆炸式增长，指令集的扩展再次成为可能。如今，许多 RISC 架构(包括 ARM)的说明与 CISC 同行大致相同。

### RISC’s Legacy

Despite the blurring of the distinction between RISC and CISC, it is still possible to identify some key characteristics that the RISC movement brought to the CPU architecture table:

> 尽管 RISC 和 CISC 之间的区别模糊了，但仍然有可能确定 RISC 运动带给 CPU 架构表的一些关键特征：

- Expanded register files
- Load/store architecture
- Orthogonal machine instructions
- Separate caches for instructions and data

>

- 扩展的寄存器文件
- 加载/存储架构
- 正交机器指令
- 指令和数据的单独缓存

There is a fifth RISC characteristic that not everyone understands: RISC was a fresh start. With almost 40 years of experience to draw on, computer scientists reimagined CPU architecture from scratch. Assumptions based on the limitations of 20-year-old technology were cast aside. Requirements to support `legacy` code vanished. Intel’s current x86 architecture still reflects decisions made to allow easy conversion of programs for 1974’s 8080 chip to 1980’s 8086. RISC architectures had no such legacy to support.

> 并非每个人都理解的第五个 RISC 特征：RISC 是一个崭新的开始。有了将近 40 年的经验，计算机科学家从头开始重新构想了 CPU 架构。基于 20 年历史技术的局限性的假设被抛在一边。支持 `遗产` 代码的要求消失了。英特尔目前的 X86 体系结构仍然反映出决定简化 1974 年 8080 芯片到 1980 年 8086 的程序的决策。RISCArchitectures 没有这样的遗产可以支持。

Let’s take a closer look at these characteristics.

> 让我们仔细研究这些特征。

### Expanded Register Files

Taken as a group, a CPU’s registers are called its _register file_ or _register set_. Machine registers are `expensive` in terms of transistor budgets. Early CPUs had very few, and those they had were small. The 8080 had seven 8-bit registers that could be used in ordinary programming. The popular Motorola 6800 and MOS Technology 6502 had only three each. By contrast, the first ARM CPUs had 13 32-bit general-purpose registers, and the later POWER RISC processors had 32.

> 作为一个组，CPU 的寄存器称为其 *register file* 或 *register set*。就晶体管预算而言，机器寄存器 `昂贵` 。早期的 CPU 很少，而且它们很小。8080 有七个 8 位登记册，可用于普通编程。受欢迎的摩托罗拉 6800 和 MOS Technology 6502 各只有三个。相比之下，第一 ARM CPU 有 13 位 32 位的通用登记册，后来的 Power Risc 处理器有 32 个。

Registers are the fastest data storage locations in the entire computer. Reading data from memory takes much more time than processing data in registers. With enough registers to hold operands and intermediate results, a program can `stay out of memory` (and thus stay inside the far faster machinery of the CPU) as much as possible. This increases performance by avoiding round trips to memory (or at least to cache), and helps modern out-of-order superscalar processors to identify opportunities for instruction-level parallelism.

> 寄存器是整个计算机中最快的数据存储位置。从内存中读取数据比处理寄存器中的数据需要更多的时间。有了足够的寄存器来保留操作数和中间结果，程序可以 `远离Mem` (从而在 CPU 的远远速度内部停留在内存中)。通过避免往返内存(或至少要缓存)，这可以提高性能，并帮助现代化的超级标准处理器确定教学级并行性的机会。

### Load/Store Architecture

In most CISC architectures, machine instructions can act directly on data stored in system memory. This was done because CISC architectures are old and generally `register-starved` . A typical CISC ADD instruction can add the contents of a register or an immediate value to a data word in memory:

> 在大多数 CISC 架构中，机器指令可以直接作用于存储在系统内存中的数据。之所以这样做，是因为 CISC 架构是旧的，通常是 `注册饥饿` 。典型的 CISC 添加指令可以将寄存器的内容或直接值添加到内存中的数据字：

```
    ADD [memory address], 8
```

This instruction adds the literal value 8 to the memory location at the address given in the first operand. Instructions like this are slow because they require two memory accesses for a simple addition: one to fetch the original value from memory, and another to write the new value back. In a real-world program, such an addition would be part of a longer sequence of actions. If these calculations could all be done within registers, memory would be accessed much less often. Alas, when all the registers are busy, there’s no alternative.

> 该指令将文字值 8 添加到第一操作数中给出的地址的内存位置。这样的说明很慢，因为它们需要两个内存访问才能进行简单的添加：一个是从内存中获取原始值，另一个要回到新值。在现实世界中，这种添加将成为更长的动作顺序的一部分。如果这些计算都可以在寄存器中完成，则 Mem 的访问频率将少得多。las，当所有寄存器都很忙时，别无选择。

With access to a larger register file, RISC architectures generally remove memory-access powers from most instructions so that they act only on registers. Accessing memory becomes the speciality of a small cadre of machine instructions that do nothing else.

> 通过访问较大的寄存器文件，RISC 体系结构通常从大多数说明中删除内存访问权力，以便它们仅在寄存器上起作用。访问 Mem 成为一小部分机器说明的专长，这些指令无助。

Designing a CPU this way results in a _load/store architecture_. Values are loaded from memory into registers by specialised load instructions, worked on within the registers and then written from the registers back to memory by specialised store instructions. The goal (as with almost everything in modern computer architectures) is to access memory as little as possible and to simplify the internal working of the pipeline.

> 以这种方式设计 CPU 会导致*load/Store Architecture *。值通过专门的加载说明从内存中加载到寄存器中，在寄存器内进行工作，然后通过专门的商店说明从寄存器中写入存储器。目标(与现代计算机体系结构中的几乎所有内容一样)是尽可能少访问内存并简化管道的内部工作。

### Orthogonal Machine Instructions

Most CISC instructions have deep historical roots. As computer architectures evolved across the 1950s and 1960s, new instructions were added to instruction sets in response to new needs. This tended to make CISC instruction sets hodgepodges of multi-byte instructions of several lengths. They were not designed as a group; instead they `just grew` .

> 大多数 CISC 指示具有深厚的历史根源。随着计算机体系结构在 1950 年代和 1960 年代的演变中，为响应新需求而添加了新的说明。这倾向于制作 CISC 指令将多个长度的多字节指令的杂物设置。他们不是被设计为一个小组。相反，他们 `只是成长` 。

The second problem with such ad-hoc instruction sets is that many instructions are special cases, in terms of how they access memory or registers. Early CPUs, for example, had one register called an _accumulator_, which held values acted upon by arithmetic and logical instructions. (The name comes from the fact that some very early computers and electromechanical tabulators accumulated intermediate results in a designated register.) Many early instructions had forms that treated the accumulator as a special case among registers.

> 此类临时指令集的第二个问题是，关于它们如何访问内存或寄存器，许多说明是特殊情况。例如，早期的 CPU 有一个称为 _accumulator_ 的寄存器，该寄存器的值由算术和逻辑指令作用。(这个名称来自以下事实：一些非常早期的计算机和机电制表符在指定的寄存器中积累了中间结果。)许多早期指令的表格将累加器视为寄存器中的特殊情况。

Special cases make decoding and executing instructions more involved and time-consuming than they would be otherwise. So when computer scientists began designing new RISC instructions sets from scratch, they did away with special cases and made all instructions the same length. For 32-bit RISC architectures (including the original Raspberry Pi’s ARM11 CPU) this length is virtually always one 32-bit word.

> 特殊案例使解码和执行说明比其他情况更加涉及和耗时。因此，当计算机科学家们开始从头开始设计新的 RISC 指令集时，他们就消除了特殊情况，并将所有指令的长度相同。对于 32 位 RISC 架构(包括原始 Raspberry Pi 的 ARM11 CPU)，该长度实际上总是一个 32 位单词。

An instruction set designed such that instructions are all the same length and CPU resources are treated without special cases is said to be _orthogonal_. The internal structure of machine instructions is also standardised to simplify instruction decoding, as we’ll explain later on.

> 设计的指令集使指令均为相同的长度，并且在没有特殊情况的情况下处理 CPU 资源是 _ORTHOCONAL_。机器指令的内部结构也被标准化以简化指令解码，正如我们稍后将要解释的那样。

### Separate Caches for Instructions and Data

As explained in [Chapter 2](#05_9781119183938-ch02.xhtml), the earliest computers, like Harvard University’s 1944 Mark I machine, stored machine instructions and data in entirely separate memory systems. John von Neumann pointed out that machine instructions are not physically different from data, and both should reside in a single memory system.

> 如[第 2 章](%EF%BC%8305_9781119183938-CH02.XHTML)所述，最早的计算机，例如哈佛大学的 1944 年 Mark I 机器，在完全独立的存储系统中存储的机器说明和数据。约翰·冯·诺伊曼(John von Neumann)指出，机器指令在物理上与数据没有不同，并且两者都应该存在于单个内存系统中。

The computer scientists who created the early RISC CPUs backed away from von Neumann’s principle a little. They demonstrated that although code and data should be stored in a single memory system, there were performance advantages in having a separate instruction cache and data cache. The StrongARM microarchitecture was the first implementation of the ARM ISA to have separate code and data caches. The contribution of cache to CPU performance is shown by the fact that out of the 2.5 million transistors on the StrongARM silicon die, the designers chose to devote 60% to the two caches. The ARM11 microarchitecture also uses this `modified Harvard architecture` and has separate caches.

> 创建了早期 RISC CPU 的计算机科学家稍微退出了冯·诺伊曼(Von Neumann)的原则。他们证明，尽管代码和数据应存储在单个内存系统中，但具有单独的指令缓存和数据缓存具有性能优势。Strongarm 微体系结构是 ARM ISA 具有单独代码和数据缓存的第一个实现。高速缓存对 CPU 性能的贡献表明，在 Strongarm Silicon 模具上的 250 万晶体管中，设计师选择将 60％用于两个缓存。ARM11 微体系结构还使用了这种 `修改后的哈佛建筑` ，并具有单独的缓存。

The reasons for the improved performance lie in the notion of locality, as explained in [Chapter 3](#06_9781119183938-ch03.xhtml). Machine instructions are generally stored in a separate area of memory from program data. More significantly, instructions in memory are usually accessed in sequence as a program is executed. Data are arranged as blocks of memory words that may be accessed in any order as the program’s needs require. Data access may not be truly random, but it’s rarely sequential. Separate code and data caches allow the use of different replacement policies and potentially cache line sizes (see [Chapter 3](#06_9781119183938-ch03.xhtml)) tailored to the access patterns of each cache.

> 如[第 3 章](%EF%BC%8306_9781119183938-CH03.xhtml)所述，改善性能的原因在于地方的概念。机器说明通常存储在与程序数据的单独内存区域中。更重要的是，在执行程序时，通常会按顺序访问内存中的说明。数据被排列为可根据程序需求的任何顺序访问的内存单词块。数据访问可能不是真正的随机性，但很少是顺序的。单独的代码和数据缓存允许使用不同的替换策略和潜在的缓存线大小(请参阅[[第 3 章](%EF%BC%8306_9781119191919183938-CH03.xHTML))，适用于每个缓存的访问模式。

Not all RISC architectures are the same, of course. Across RISC’s 35-year history, many things have been tried. It’s a measure of the success of RISC design principles that most modern CISC architectures incorporate many RISC characteristics, including the dominant CISC architecture, Intel’s x86.

> 当然，并非所有 RISC 架构都是相同的。在 RISC 的 35 年历史中，已经尝试了许多事情。这是 RISC 设计原则成功的衡量标准，大多数现代的 CISC 架构都包含许多 RISC 特征，包括主导的 CISC 建筑，英特尔的 X86。

The rest of this chapter focuses on a particular family of RISC CPUs: the ARM processors from ARM Holdings PLC, especially the ARM11 processor and the ARM CORTEX processors that followed it.

> 本章的其余部分重点介绍了一个特定的 RISC CPU 家族：Arm Holdings PLC 的 ARM 处理器，尤其是 ARM11 处理器和随后的 ARM Cortex 处理器。

## ARMs from Little Acorns Grow

In early 1981, the British Broadcasting Corporation (BBC) began working on a project to foster computer skills among its audience, especially young people. The Computer Literacy Project required a solid and reasonably inexpensive mass-market computer to serve as a basis for the program. The project put out specs and asked for bids. The only design that met their specifications was the Proton from Acorn Computers, which was based, like the Raspberry Pi Foundation, in Cambridge. The Proton was based on the same 6502 microprocessor used in the popular Apple II machine. After its adoption by the BBC, the Proton became known as the BBC Microcomputer and more than 1.5 million were sold.

> 1981 年初，英国广播公司(BBC)开始从事一个项目，以促进其观众，尤其是年轻人的计算机技能。计算机素养项目需要扎实且相当便宜的大众市场计算机来作为该计划的基础。该项目推出规格并要求出价。符合其规格的唯一设计是来自橡子计算机的质子，该质子像剑桥的 Raspberry Pi Foundation 一样。质子基于流行的 Apple II 机器中使用的 6502 微处理器。在被英国广播公司(BBC)采用后，质子被称为 BBC 微型计算机，售出了超过 150 万。

Once the IBM PC legitimised personal computers for business use, Acorn decided to create a higher-end unit to sell to the office market. It evaluated all the major microprocessors of the time, including the 8086 and the 68000, and found them unsuitable for various reasons. In 1983, Acorn began an ambitious project to design its own microprocessor for use in its high-end systems.

> 一旦 IBM PC 将个人计算机合法化以供业务使用，Acorn 决定创建一个高端单位以出售给办公室市场。它评估了当时的所有主要微处理器，包括 8086 和 68000，并因各种原因发现它们不适合。1983 年，Acorn 开始了一个雄心勃勃的项目，旨在设计自己的微处理器，以便在其高端系统中使用。

A team led by Acorn engineers Sophie Wilson and Steve Furber drew on research that came out of the Berkeley RISC Project. First silicon for the Acorn RISC Machine (ARM) CPU came back in mid-1985. ARM1 was a prototype that was never produced commercially. Production chips appeared in 1986, as the ARM2. ARM2 microprocessors first served as coprocessors in the 6502-based BBC Microcomputer to increase machine performance, particularly in areas like graphics and computer-aided design (CAD).

> 由橡子工程师索菲·威尔逊(Sophie Wilson)和史蒂夫·弗雷伯(Steve Furber)领导的一支团队从伯克利 RISC 项目中脱颖而出。Acorn Risc Machine(ARM)CPU 的第一硅在 1985 年中回来。ARM1 是从未商业生产的原型。生产芯片出现在 1986 年，作为 ARM2。ARM2 微处理器首先在基于 6502 的 BBC 微型计算机中担任协处理器，以提高机器性能，尤其是在图形和计算机辅助设计(CAD)等领域。

The first complete ARM-based microcomputer was released in 1987, as the Acorn Archimedes. The Archimedes included something new for Acorn: Arthur, an operating system with a fully graphical user interface. Arthur was later developed into RISC OS, which still exists.

> 第一个完整的基于 ARM 的微型计算机于 1987 年发布，作为 Acorn Archimedes。Archimedes 包含了针对 Acorn 的新内容：Arthur，这是一个具有完全图形用户界面的操作系统。后来，亚瑟(Arthur)被发展成为 RISC OS，该 OS 仍然存在。

---

> [!NOTE]

RISC OS is available as a free download for the Raspberry Pi. You can learn more about RISC OS (and obtain the release for the Raspberry Pi) at [`https://www.riscosopen.org/wiki/documentation/show/Welcome to RISC OS Pi`](https://www.riscosopen.org/wiki/documentation/show/Welcome).

> RISC OS 可作为 Raspberry Pi 免费下载。您可以在[[https://www.riscosopen.org/wiki/wiki/documentation/show/welcome](https://www.riscosopen.org/wiki/wiki/documentation/show/welcome) to risc os pi`](https：// wwwww。riscosopen.org/wiki/documentation/show/welcome)。

Development of the ARM CPUs was spun off to a separate company in 1990, at which time the ARM acronym changed to Advanced RISC Machine. Advanced RISC Machines became ARM Holdings in 1998.

> ARM CPU 的开发于 1990 年旋转到一家单独的公司，此时，ARM 首字母缩写更改为 Advanced Risc Machine。Advanced Risc 机器于 1998 年成为 Arm Holdings。

### Microarchitectures, Cores and Families

The nomenclature ARM uses for its products can be confusing at times. The instruction set architecture (ISA) of the ARM processors has a version number. A separate version number is given to the ARM microarchitecture. The term _microarchitecture_ refers to the way that a CPU designer implements an instruction set architecture in silicon. Think of it this way: the ISA defines the behaviour of a CPU, and the microarchitecture defines its structure.

> 其产品的命名 ARM 使用有时会令人困惑。ARM 处理器的指令集体系结构(ISA)具有版本号。单独的版本编号给了 ARM 微体系结构。术语 _microArchitecture_ 是指 CPU 设计师在硅中实现指令集体系结构的方式。**这样想：ISA 定义了 CPU 的行为，微体系结构定义了其结构。**

ARM processors are grouped in families, each with its own microarchitecture version number. The first ARM ISA version was ARMv1, used only in the prototype ARM1 processor. The ARMv2 ISA was implemented in the ARM2 and ARM3 families of CPUs. ARMv3 was implemented in the ARM6 and ARM7 families, and so on. The original Raspberry Pi’s CPU belongs to the ARM11 family, which implements the ARMv6 instruction set. Processors within an ARM family generally differ in small ways that reflect emphases rather than significant architectural differences. The ARM11 microarchitecture applies to all four cores in the ARM11 family.

> ARM 处理器分组为家庭，每个家庭都有自己的微体系结构版本编号。第一 ARM ISA 版本是 ARMV1，仅在原型 ARM1 处理器中使用。ARMV2 ISA 是在 CPU 的 ARM2 和 ARM3 家族中实施的。ARMV3 在 ARM6 和 ARM7 家族中实施，依此类推。原始的 Raspberry Pi 的 CPU 属于 ARM11 家族，该家族实现了 ARMV6 指令集。ARM 家族中的处理器通常在反映重点而不是重大建筑差异的小方面有所不同。ARM11 微体系结构适用于 ARM11 家族中的所有四个核心。

You’ll often hear ARM CPUs referred to as `cores` . The word _core_ is not a precise technical term in the computer industry. Most of the time it indicates any large independent component that may exist in a single-chip design containing multiple cores. In the ARM universe, a `core` is more specifically a CPU that may be incorporated into a custom device that includes non-CPU logic like USB and network ports, graphics processors, mass storage controllers, timers, bus controllers and so on. Such a device is called a _system-on-a-chip_ (SoC).

> 您经常会听到被称为 `核心` 的 ARM CPU。_core_ 一词不是计算机行业的精确技术术语。在大多数情况下，它表明在包含多个内核的单芯片设计中可能存在任何大型独立组件。在 ARM Universe 中，`核心` 更具体地是一个 CPU，可以将其纳入自定义设备中，该设备包括非 CPU 逻辑，例如 USB 和网络端口，图形处理器，质量存储控制器，计时器，总线控制器等。这样的设备称为 _system-on-a-chip_(SOC)。

### Selling Licenses Rather Than Chips

The ARM-specific definition of `core` will start to make a little more sense once you understand the radical difference between the business models used by ARM Holdings and Intel. Intel designs and manufactures finished chips, each one in its own plastic or ceramic integrated circuit package, ready to be plugged or soldered into a computer circuit board. ARM Holdings, by contrast, is purely a design firm. Its engineers design CPU cores and other computer logic, and then license the designs to other firms. Firms that license ARM designs may customise them or integrate them with in-house logic to create a finished SoC design. They then take the design to a firm called a _chip foundry_ that manufactures integrated circuits for them.

> 一旦您了解 Arm Holdings 和 Intel 使用的业务模型之间的根本差异，`核心` 的特定于 `核心` 的定义将变得更加有意义。英特尔设计和制造制造芯片，每个芯片，每个芯片都有自己的塑料或陶瓷集成电路套件，准备插入或焊接到计算机电路板中。相比之下，ARM 持有纯粹是一家设计公司。它的工程师设计 CPU 内核和其他计算机逻辑，然后将设计许可给其他公司。许可 ARM 设计的公司可以自定义它们或将其与内部逻辑集成在一起以创建成品 SOC 设计。然后，他们将设计带到了一个名为 _chip Foundry_ 的公司，该公司为其制造集成电路。

As long as the computer industry was dominated by mature and mostly identical laptop and desktop PC designs, Intel’s business model predominated. However, after smartphones and tablet computers entered the mass market, customisation became crucial not only to differentiate products but also to evolve them. Innovation in ARM-powered devices extends all the way down to the CPU silicon. Most licensees use finished and certified ARM cores, but ARM has also licensed its ISA to a number of architecture licensees who then create their own custom cores representing a non-ARM microarchitecture. The earliest example of this is the StrongARM core, which was designed by Digital Equipment Corporation in the 1990s and later sold to Intel as XScale. StrongARM/XScale implements the ARMv4 ISA in a novel microarchitecture; it was the first CPU in the ARM line to incorporate separate instruction and data caches. More recent architecture licensees include Apple, with their Swift cores, and Qualcomm, with their Scorpion and later Krait cores.

> 只要计算机行业以成熟且主要是相同的笔记本电脑和台式 PC 设计为主导，英特尔的业务模型占主导地位。但是，在智能手机和平板电脑进入大众市场之后，定制不仅对区分产品，而且对它们的发展变得至关重要。ARM 动力设备的创新一直延伸至 CPU 硅。大多数被许可人使用完成和认证的 ARM 内核，但 ARM 还将其 ISA 许可给许多建筑许可人，然后创建代表非武器微体系结构的自定义核心。最早的例子是 Strongarm Core，该核心是由数字设备公司在 1990 年代设计的，后来卖给了英特尔作为 Xscale。strongarm/xscale 在新的微体系结构中实现了 ARMV4 ISA；这是 ARM 线中第一个合并单独的指令和数据缓存的 CPU。最新的建筑许可证持有人包括苹果，以及迅速的核心和高通以及后来的克拉特核心。

The Raspberry Pi computers all use SoCs designed by Broadcom. The first generation boards contain a single ARM11 core. The second and third generation boards each contain four Cortex family cores. At this point we’ll turn to a more detailed description of the ARM11 microarchitecture. Later in this chapter, we will explore the Raspberry Pi’s SoC device and how SoCs are designed.

> Raspberry Pi 计算机都使用 Broadcom 设计的 SOC。第一代板包含一个 ARM11 核心。第二代和第三代董事会各有四个皮层家族核心。在这一点上，我们将介绍对 ARM11 微体系结构的更详细的描述。在本章的后面，我们将探索 Raspberry Pi 的 SOC 设备以及如何设计 SOC。

## ARM11

The ARM11 microarchitecture, announced in 2002, was the first, and so far the only, ARM family to implement the ARMv6 ISA. It’s a 32-bit microarchitecture, meaning that all machine instructions are 32 bits wide and that memory is accessed in 32-bit words. Some ARM machine instructions are designed to operate on smaller operands, of which there are two types: 16-bit halfwords and 8-bit bytes.

> ARM11 微体系结构于 2002 年宣布，是第一个也是唯一的 ARM 家族实施 ARMV6 ISA 的家族。这是一个 32 位的微观结构，这意味着所有机器指令均宽 32 位，并且以 32 位单词访问内存。一些 ARM 机器的说明旨在在较小的操作数上操作，其中有两种类型：16 位半词和 8 位字节。

### The ARM Instruction Set

The ARMv6 ISA includes three separate instruction sets: ARM, Jazelle, and Thumb. Of these, the ARM instruction set is the most frequently used.

> ARMV6 ISA 包含三个独立的指令集：ARM，Jazelle 和 Thumb。其中，ARM 指令集是最常用的。

#### ARM

You’ll see an occasional ARM machine instruction in this chapter (and elsewhere in this book, including a complete program in [Chapter 5](#08_9781119183938-ch05.xhtml)) so it would be good to take a quick look at how machine instructions are built. Let’s look at a few examples.

> 您将在本章中看到偶尔的 ARM 机器指令(以及本书的其他地方，包括[第 5 章](%EF%BC%8308_978111919183938-CH05.XHTML)中的完整程序)，因此快速了解机器的方式是很好的建立了说明。让我们看一些例子。

---

> [!NOTE]

We say `built` advisedly, because ARM machine instructions allow various options to make them work in different ways, as needed.

> 我们说 `构建` 建议，因为 ARM 机器指令允许各种选择使它们根据需要以不同的方式工作。

The easiest machine instructions to understand are those that perform arithmetic operations on data. Remember from our earlier discussion that RISC machine instructions don’t access memory directly. All work to be done on data is done with data stored in registers. Consider the `ADD`</code> instruction, which adds the contents of two registers and places the sum in a third register. The general assembly-language form of an `ADD` instruction looks like this:

> 最简单的机器说明是那些对数据进行算术操作的说明。从我们之前的讨论中记住，RISC 机器指令无法直接访问内存。所有要在数据上完成的工作都是使用存储在寄存器中的数据完成的。考虑 `添加` </code>指令，该指令添加了两个寄存器的内容，并将总和放入第三寄存器中。`添加` 指令的大会语言形式如下：

```
    ADD{<condition code>} {S} <Rd>, <Rn>, <Rm>
```

Instructions are summarised this way in most ARM instruction references. The notation works like this:

> 在大多数 ARM 指导参考文献中，以这种方式总结说明。符号这样起作用：

- Anything enclosed by curly brackets (`{}`) is optional. Anything not inside curly brackets is required.
- Anything within angle brackets (`< >`) is a placeholder for a symbol or a value.
- `Rd` means destination register. When an instruction has a destination register operand, the destination operand is the first after the mnemonic. `Rn` and `Rm` name the source register operands. The `m` and `n` don’t stand for anything specific.

>

- 卷曲括号(`{}`)所包含的任何东西都是可选的。需要在卷发支架内部的任何东西。
- 角括号内的任何东西(`<>`)都是符号或值的占位符。
- ` RD` 表示目标寄存器。当指令具有目标寄存器操作数时，目标操作数是助记符之后的第一个。`rn` 和 `rm` 名称源寄存器操作数。``M `和'n` 不代表任何具体的东西。

Nearly all ARM instructions may be executed conditionally. (We cover this in some detail later in this chapter.) The optional `<condition code>` specifies 1 of 15 conditions that must be met before the instruction’s action takes place. If the condition code is not met, the instruction works its way through the pipeline but does not take any other action. If no condition code is specified, the default is `always` , meaning unconditional execution.

> 几乎所有的 ARM 说明都可以有条件执行。(我们在本章稍后详细介绍了这一点。)可选 `<条件代码>` 指定在说明的操作之前必须满足的 15 条条件中的 1 个。如果未满足条件代码，则该指令在管道中运行，但不采取任何其他措施。如果未指定条件代码，则默认值为 `始终` ，表示无条件执行。

The optional `S` suffix directs the `ADD` instruction to modify the condition flags based on the result of the addition; these flags then control any subsequent conditionally executed instructions. Without the `S` suffix, a machine instruction does its work without changing the values of the flags. This means that a series of instructions can perform their work conditionally, based on an initial operation that sets the flags.

> 可选的 ` S` 后缀指示 `` 添加指令''指令根据添加的结果修改条件标志；然后，这些标志控制任何随后的有条件执行的说明。没有 ` S` 后缀，机器指令就可以在不更改标志值的情况下进行工作。这意味着一系列指令可以根据设置标志的初始操作有条件地执行其工作。

The following instruction handles adding the contents of register 1 (R1) to register 2 (R2) and placing the sum in register 5 (R5):

> 以下指令处理添加寄存器 1(r1)的内容以登记 2(r2)，并将总和放入寄存器 5(r5)中：

```
ADD R5, R1, R2
```

To build the instruction such that it only executes if the `Zero` flag is set, you’d add the condition code `EQ` to the mnemonic:

> 要构建指令，以便仅在设置 `零标志时执行执行，就可以将条件代码` eq'添加到 mnemonic：

```
    ADDEQ R5, R1, R2
```

Subtraction works in much the same way. An instruction to subtract R3 from R4 and place the difference in R2 would look like this, assuming the programmer wants the subtraction to set the flags:

> 减法的工作方式几乎相同。从 R4 中减去 R3 并将差异放在 R2 中的指令将看起来像这样，假设程序员希望减法设置标志：

```
    SUBS R2, R4, R3
```

Not all instructions take three operands. The `MOV` instruction copies a value stored in one register to another, or places a literal value into a register:

> 并非所有指示都需要三个操作数。` MOV` 指令将存储在一个寄存器中的值复制到另一个寄存器，或将字面价值放入寄存器中：

```
    MOV R5, R3MOV R5, #42
```

The first instruction copies whatever is in R3 into R5. The second stores the literal value 42 into R5.

> 第一个指令将 R3 中的任何内容复制到 R5 中。第二个将文字值 42 存储到 R5 中。

Although it’s no longer generally available, the _ARM Architecture Reference Manual_ is very useful as an introduction to the several ARM instruction sets. (You can sometimes find available downloads by performing a Google search on the title.) Writing short assembly language programs and then inspecting their execution in a debugger is a good way to see what various instructions do. The GNU Compiler Collection, which is included with the Raspbian operating system, has a very good assembler. [Chapter 5](#08_9781119183938-ch05.xhtml) explains how to assemble and run short assembly language test programs.

> 尽管不再通常可用，但 *ARM 架构参考手册*非常有用，可作为几个 ARM 指令集的介绍。(有时您可以通过对标题进行 Google 搜索来找到可用的下载。)编写简短的汇编语言程序，然后在调试器中检查其执行是一种看待各种说明的好方法。Raspbian 操作系统中包含的 GNU 编译器收集器具有非常好的汇编程序。[第 5 章](%EF%BC%8308_9781119183938-CH05.XHTML)说明了如何组装和运行简短的汇编语言测试程序。

#### Jazelle

The Jazelle instruction set allows an ARM11 core to execute Java bytecodes directly, without software interpretation. ([Chapter 5](#08_9781119183938-ch05.xhtml) explains bytecode languages like Java and Python.) ARM Holdings deprecated Jazelle in 2011, which means that the company will not be evolving the technology any further and recommends that it is not used in new projects.

> Jazelle 指令集允许 ARM11 核心直接执行 Java 字节码，而无需软件解释。([[第 5 章](%EF%BC%8308_9781119183938-CH05.xHTML)解释了诸如 Java 和 Python 之类的字节码语言。新项目。

---

> [!NOTE]

Computer manufacturers sometimes _deprecate_ a feature or a product line once they feel it has reached the end of its useful life. This does not mean that they disable it but rather that they advise strongly against its future use. Many manufacturers add that a deprecated product or feature may well be withdrawn at some time in the future, or that support for it will be eliminated in various ways. Deprecated features and products should not be used in new designs for those reasons.

> 计算机制造商有时 *deprecate* 一旦觉得它已达到其使用寿命的尽头，他们的功能或产品线。这并不意味着他们将其禁用，而是他们强烈建议对未来的使用建议。许多制造商补充说，将来的某个时候很可能会撤回弃用的产品或功能，或者将以各种方式消除对其的支持。出于这些原因，不应在新设计中使用折衷的功能和产品。

#### Thumb

The Thumb instruction set is a 16-bit implementation of the 32-bit ARM instruction set. Thumb instructions are 16 bits wide instead of 32 bits wide. This allows greater _code density_, meaning that more instructions (and thus more functionality) may be stored in a given quantity of memory. Some low-end devices have limited memory, and they access that memory 16 bits at a time over a 16-bit system bus. Thumb instructions are designed to make more efficient use of such a bus. Thumb instructions still process 32-bit quantities in registers. Not all registers are fully available to Thumb instructions, and certain other hardware resources are available in only limited ways.

> Thumb 指令集是 32 位 ARM 指令集的 16 位实现。Thumb 说明为 16 位，而不是 32 位宽。这允许更大的* code 密度*，这意味着可以将更多的指令(以及更多功能)存储在给定数量的内存中。一些低端设备的内存有限，他们一次通过 16 位系统总线访问该内存 16 位。Thumb 说明旨在更有效地利用这种公共汽车。Thumb 说明仍在注册表中处理 32 位数量。并非所有寄存器都可以完全使用 Thumb 说明，并且某些其他硬件资源仅以有限的方式可用。

The Thumb instruction set is interesting for another reason: after Thumb instructions are fetched from memory or cache, they’re expanded to ordinary ARMv6 instructions by dedicated logic inside the CPU. After they enter the instruction pipeline, they’re no longer Thumb instructions at all. Thumb instructions are thus a sort of shorthand that allows more instructions to fit in a given amount of memory. The Thumb instruction set is generally used in programming _embedded systems_, which are devices that incorporate microprocessors and software to do their work but are not general-purpose computers themselves. The line is not sharp: the Raspberry Pi is often used for embedded systems, even though it has enough memory and CPU power to function as a conventional desktop computer.

> Thumb 指令集很有趣，原因是另一个原因：从内存或缓存中获取 Thumb 指令后，它们通过 CPU 内的专用逻辑扩展到普通的 ARMV6 指令。他们输入说明管道后，它们根本不再是 Thumb 说明。因此，Thumb 说明是一种速记，允许更多说明适合给定的 Mem。Thumb 指令集通常用于编程 *embedded Systems*，它们是合并微处理器和软件来完成其工作的设备，但不是通用计算机本身。该线并不清晰：Raspberry Pi 通常用于嵌入式系统，即使它具有足够的内存和 CPU 功率来充当传统的台式计算机。

---

> [!NOTE]

When the ARM11 core is executing Thumb instructions, it’s said to be in the Thumb state. Similarly, the core is in the Jazelle state while executing Jazelle instructions. In virtually all cases, the Raspberry Pi operates in the ARM state, using the full 32-bit ARM instruction set.

> 当 ARM11 核心执行 Thumb 指示时，据说它处于 Thumb 状态。同样，核心在执行 Jazelle 说明时处于 Jazelle 状态。在几乎所有情况下，Raspberry Pi 使用完整的 32 位 ARM 指令集以 ARM 状态运行。

Don’t confuse the processor _state_ with the processor _mode_. Read on.

> 不要将处理器 *state* 与处理器 *mode* 混淆。阅读。

### Processor Modes

Early desktop operating systems did little or nothing to prevent applications from misbehaving. CP/M-80 systems, in fact, had so little memory that much of CP/M-80 basically removed itself from memory after launching an application and then reloaded itself when the application terminated. PC-DOS remained in memory, but Windows was a user interface running over PC-DOS rather than an operating system until Windows NT was first released in 1993. CP/M-80 and PC-DOS are more correctly considered system monitors than operating systems.

> 早期的桌面操作系统几乎没有或什么都没有阻止应用程序表现不佳。实际上，CP/M-80 系统的内存很少，以至于 CP/M-80 的大部分内容基本上在启动应用程序后从内存中删除了自身，然后在应用程序终止时重新加载了自己。PC-DOS 保留在内存中，但是 Windows 是通过 PC-DOS 运行的用户界面，而不是操作系统，直到 Windows NT 于 1993 年首次发布。CP/M-80 和 PC-DOS 比操作系统更正确地考虑了系统监测器。

---

> [!NOTE]

A _monitor_ is system software that loads and runs applications but does little in terms of managing system resources.

> *monitor* 是系统软件，可加载和运行应用程序，但在管理系统资源方面几乎无能为力。

Part of the problem was a shortage of memory, but a greater part was that the CPU chips at the time had no ability to protect system software from application software. In 1985, Intel’s 386 CPUs were the first Intel chips to offer a practical _protected mode_, which provides the operating system kernel with privileged access to system resources denied to applications (which run in real or User mode) and was a prerequisite for implementing a true operating system on Intel processors. All modern CPUs intended for use in general-purpose computers contain logic to manage system resources and prevent applications from interfering with the operating system and other applications.

> 问题的一部分是缺乏内存，但很大程度上是当时的 CPU 芯片没有能力保护系统软件免受应用程序软件的影响。1985 年，英特尔(Intel)的 386 个 CPU 是第一个提供实用 *Protected Mode* 的英特尔芯片，该模式为操作系统内核提供了对应用程序拒绝的系统资源(以真实或用户模式运行)的特权访问权限，并且是实现真实条件的先决条件。英特尔处理器上的操作系统。所有旨在在通用计算机中使用的现代 CPU 都包含逻辑来管理系统资源并防止应用程序干扰操作系统和其他应用程序。

ARM11 processors provide several different modes to support operating system management of user apps and the computer’s hardware. These are summarised in Table 4-1. All but User mode are considered _privileged_ modes, meaning that they have full access to system resources. Supervisor mode is specifically for use by operating system kernels and other protected code connected with operating systems. System mode is basically User mode with full privileges and access to all the hardware. It is not used much, except in low-end embedded work; it’s considered obsolete.

> ARM11 处理器提供了几种不同的模式，以支持用户应用程序和计算机硬件的操作系统管理。这些总结在表 4-1 中。除用户模式以外的所有模式都被视为 *privileged* 模式，这意味着它们可以完全访问系统资源。主管模式专门用于操作系统内核和与操作系统连接的其他受保护的代码。系统模式基本上是用户模式，具有完整的特权，并访问了所有硬件。除了低端嵌入式工作外，它没有太多使用；它被认为是过时的。

[Table 4-1](#07_9781119183938-ch04.xhtml#rc04-tbl-0001) ARM11 Processor Modes

**Mode** **Abbreviation** **Mode bits** **Description** ---------------

- User usr 10000 For user application execution Supervisor svc 10011 For the operating system kernel System Sys 11111 Now obsolete Secure monitor mon 10110 Used in TrustZone applications FIQ fiq 10001 For `fast interrupt` servicing IRQ irq 10010 For general-purpose interrupt servicing Abort abt 10111 For virtual memory and other memory management Undefined und 11011 For software emulation of undefined machine instructions, as in coprocessors or newer ISAs

The FIQ, IRQ, Abort and Undefined modes support interrupts and exceptions. _Interrupts_ are signals from hardware devices outside the CPU indicating that the device requires attention. _Exceptions_ are anomalous events within the CPU that require special handling by the CPU, generally in cooperation with the operating system. These include virtual memory page faults and arithmetic errors like divide-by-zero. We mention these again in connection with registers.

> FIQ，IRQ，中止和未定义模式支持中断和异常。* Interrupts*是来自 CPU 之外硬件设备的信号，表明该设备需要注意。*exceptions* 是 CPU 中的异常事件，通常需要与操作系统合作，需要 CPU 进行特殊处理。这些包括虚拟内存页故障和算术错误，例如按零分割。我们再次提及与登记册有关的这些。

The System Monitor mode is used with an ARMv6 feature called TrustZone, which creates isolated memory regions called _worlds_ and manages data transfers between them. TrustZone is used primarily in content digital rights management (DRM) to prevent programs from `sniffing` decrypted content in memory and writing it out to storage. TrustZone is not implemented in all ARM11 processors, and requires special changes to behaviour of the system data bus used in SoC designs. TrustZone is not available in the BCM2835 SoC in the Raspberry Pi.

> 系统监视器模式与称为 Trustzone 的 ARMV6 功能一起使用，该功能创建了称为 *Worlds* 的隔离内存区域，并管理它们之间的数据传输。Trustzone 主要用于内容数字权利管理(DRM)，以防止程序 `嗅探` Mem 中的内容并将其写入存储。Trustzone 并未在所有 ARM11 处理器中实施，并且需要对 SOC 设计中使用的系统数据总线的行为进行特殊更改。Trustzone 在 Raspberry Pi 的 BCM2835 SOC 中不可用。

ARM’s Supervisor mode is the mode used by the operating system kernel. The kernel and the memory it runs in are often called _kernel space_. When an ARM system is reset, the CPU is placed in Supervisor mode and the kernel begins executing. In Unix/Linux jargon, _userland_ is the memory and software environment where user applications run. Some operating systems place noncritical device drivers in userland, along with software libraries that provide an interface to the OS and certain hardware resources.

> ARM 的主管模式是操作系统内核使用的模式。内核及其运行的内存通常称为 *KERNEL SPACE*。重置 ARM 系统时，将 CPU 放置在主管模式下，内核开始执行。在 Unix/Linux 术语中，*userland* 是运行用户应用程序的内存和软件环境。一些操作系统将非关键设备驱动程序放置在 Userland，以及为操作系统和某些硬件资源提供接口的软件库。

Most of the differences between the several processor modes have to do with the use of the ARM register file. Let’s take a closer look at the ARM family’s register riches.

> 几种处理器模式之间的大多数差异都与使用 ARM 寄存器文件的使用有关。让我们仔细看看 Arm 家族的登记册。

### Modes and Registers

One of the fundamental decisions behind RISC CPU design is to put as many registers as is practical within the CPU. The more registers a CPU has, the less often it has to access instruction operands in memory or save intermediate results out to memory. The more that a CPU can execute its instructions without accessing memory, the faster that execution will be.

> **RISC CPU 设计背后的基本决定之一是放置与 CPU 中尽可能多的登记册**。CPU 的寄存器越多，在内存中访问指令操作数或将中间结果保存到内存中所需的频率就越少。CPU 可以执行其指令而无需访问内存，执行的速度就越快。

Compared to almost any non-RISC ISA, ARMv6 has a lot of registers. All are 32 bits in size. There are 40 registers in all: 33 general-purpose registers plus 7 status registers. Not all of these registers are available at all times in all modes. Furthermore, some of the registers have special functions that place limits on how they may be used.

> 与几乎任何非 RISC ISA 相比，ARMV6 都有很多登记册。所有大小都是 32 位。总共有 40 个登记册：33 个通用注册表加 7 个状态登记册。并非所有这些寄存器始终以所有模式可用。此外，某些寄存器具有特殊功能，可以对它们的使用方式限制。

Untangling ARM register usage requires a chart indicating which registers are available in which modes. Refer to Figure 4-17 during the following discussion.

> 解开 ARM 注册使用情况需要一个图表，指示哪些寄存器可在哪些模式下可用。在以下讨论中，请参阅图 4-17。
> ![[FIGURE 4-17:](#07_9781119183938-ch04.xhtml#rc04-fig-0017) The ARM11 register file](./media/images/9781119183938-fg0417.png)

Of the 16 ARM general-purpose registers, only the first 13 are truly general purpose. Registers R13, R14 and R15 play special roles in program execution. R15 acts as the program counter (PC), which always contains the address of the next instruction to be executed. Unlike some other processor architectures, the ARM program counter may be freely read and written to even in User mode. Simply writing a new address to R15 effectively implements an unconditional branch, but doing so is considered bad programming practice. Hard-coding addresses in software makes it impossible for operating systems to decide where in memory to load and run the code, and such code is very likely to malfunction.

> 在 16 个 ARM 通用登记册中，只有前 13 个是真正的通用登记册。寄存器 R13，R14 和 R15 在程序执行中扮演特殊角色。R15 充当程序计数器(PC)，它始终包含要执行的下一个指令的地址。与其他一些处理器架构不同，ARM 程序计数器可以自由阅读和写入用户模式。简单地为 R15 编写新的地址可以有效地实现无条件的分支，但这样做被认为是不良的编程实践。软件中的硬编码地址使操作系统无法确定内存中加载和运行代码的位置，并且这种代码很可能会出现故障。

R14 is called the _link register_ (LR). The LR is used to execute fast subroutine calls using one of a group of instructions called Branch with Link. When a `BL` or `BLX` instruction is executed, the CPU stores the return address in the LR and then branches to the subroutine address. When the subroutine finishes executing, the return address stored in LR is copied back to the program counter. The program then continues on its main line of execution, having `ducked out` to execute the subroutine.

> R14 称为 *link 寄存器*(LR)。LR 用于使用带有链接的分支的一组指令之一来执行快速子例程调用。执行 `bl'或` blx 指令时，CPU 将返回地址存储在 LR 中，然后分支到子例程地址。当子例程完成执行时，将存储在 LR 中的返回地址复制回程序计数器。然后，该程序继续执行主管，`躲开` 执行子例程。

R13 is by convention used as the stack pointer (SP). The ARM SP works the way SPs work in nearly all CPU architectures. (Refer to [Figure 4-6](#07_9781119183938-ch04.xhtml#c04-fig-0006) and the associated text earlier in this chapter if you don’t understand how stacks work.) Most ARM instructions allow you to use R13 as a general-purpose register, but ARM Holdings has deprecated this use, and for a very good reason: nearly all operating systems make intensive use of the stack, and without extreme care, using SP as a general-purpose register can cause crashes.

> R13 按常规用作堆栈指针(SP)。ARM SP 以 SPS 在几乎所有 CPU 架构中的工作方式工作。(请参阅[图 4-6](%EF%BC%8307_978111919183938-CH04.XHTML%EF%BC%83C04-FIG-0006) 和本章早些时候的关联文本，如果您不了解堆栈的工作原理。)大多数 ARM 说明允许您使用 R13 作为通用登记册，但 ARM HOUPTINGS 已弃用了此用途，这是一个很好的理由：几乎所有操作系统都大量地使用了堆栈，并且在不极大的护理中，使用 SP 作为通用寄存器可能会导致崩溃。

#### Banked Registers

[Figure 4-17](#07_9781119183938-ch04.xhtml#c04-fig-0017) suggests that there are a lot more ARM registers than there actually are. Read the figure carefully: each column represents a processor mode, and beneath the mode is a list of registers available while the CPU is operating in that mode. All modes can access registers R0 to R7, and it’s the _same_ R0 to R7 irrespective of mode. There is not a separate group of registers from R0 to R7 for each mode.

> [图 4-17](%EF%BC%8307_9781119183938-CH04.xHTML%EF%BC%83C04-FIG-0017) 表明，ARM 寄存器比实际的手 ARM 寄存器要多得多。仔细阅读图：每列代表处理器模式，在该模式下，在 CPU 以该模式运行时可用的寄存器列表。所有模式都可以访问 R0 到 R7 的寄存器，并且无论模式如何，它都是 *same* R0 到 R7。对于每种模式，没有 R0 到 R7 的单独寄存器组。

After that it becomes complicated. In Fast Interrupt mode, registers R8 to R14 are private and have their own mode-specific names: R8*fiq, R9_fiq, and so on. Machine instructions that specify one of the R8 to R14 registers while the CPU is in Fast Interrupt mode access registers in Fast Interrupt mode’s private bank. Registers R8_fiq to R14_fiq are _banked registers*. There’s more information about Fast Interrupt mode later in this chapter.

> 之后，它变得复杂。在快速中断模式下，寄存器 R8 至 R14 是私有的，并且具有自己的模式特定名称：R8*FIQ，R9*FIQ 等。当 CPU 处于快速中断模式的私人银行中，将 R8 指定为 R14 寄存器的机器指令将其中一个指定为 R14 寄存器。寄存器 r8*fiq 至 r14_fiq 是\ * banked 寄存器_。在本章后面，还有有关快速中断模式的更多信息。

In [Figure 4-17](#07_9781119183938-ch04.xhtml#c04-fig-0017), all shaded registers are banked registers. Fast Interrupt mode has a lot of them; the other modes have either two or, in the case of User and System modes, none at all.

> 在[图 4-17](%EF%BC%8307_978111919183938-CH04.XHTML%EF%BC%83C04-FIG-0017) 中，所有阴影寄存器均为银行寄存器。快速中断模式有很多。其他模式有两个或在用户和系统模式的情况下，根本没有。
> [!NOTE]
> that the description of processor modes and registers in [Figure 4-17](#07_9781119183938-ch04.xhtml#c04-fig-0017) applies only to ARMv6 and earlier ISAs.

#### The Current Program Status Registers

Most ARM registers are general-purpose, or almost general-purpose. One register is definitely not: the current program status register (CPSR) is a single 32-bit value divided into bits and groups of bits. Each bit or group stores some information about what the CPU is doing (or has recently done) at any particular instant.

> 大多数手 ARM 寄存器都是通用或几乎通用的。一个寄存器绝对不是：当前的程序状态寄存器(CPSR)是一个 32 位值，分为位和一组。每个位或组都存储一些有关 CPU 在任何特定瞬间所做的(或最近完成)的信息。

Figure 4-18 shows what’s inside the CPSR. Explaining all of it in detail is beyond the scope of this book, and in any case much of it is mainly of use to compilers and assemblers who build executable programs. (Read more on this in [Chapter 5](#08_9781119183938-ch05.xhtml).) The shaded areas represent bits that are undefined and reserved for use in newer ARM microarchitectures.

> 图 4-18 显示了 CPSR 内部的内容。详细说明所有内容都超出了本书的范围，在任何情况下，其中大部分主要用于构建可执行程序的编译器和汇编商。(在[第 5 章](%EF%BC%8308_9781119183938-CH05.XHTML)中了解更多信息。)阴影区域表示未定义并保留的位，用于新的手 ARM 微体系结构。
> ![[FIGURE 4-18:](#07_9781119183938-ch04.xhtml#rc04-fig-0018) Inside the current program status register](./media/images/9781119183938-fg0418.png)

The part of the CPSR that sees the most use is the group of five bits called the _condition flags_. Each of the five bits in the group may be tested by conditional branch instructions. The `N`, `Z`, `C`, and `V` bits may also be tested by a conditional execution mechanism that can be used to `turn an instruction off` if one or more of the condition flags match the corresponding flags inside the instruction itself. (More on this in the section entitled `[Conditional Instruction Execution](#07_9781119183938-ch04.xhtml#c04-sec-0042)` .)

> CPSR 的一部分最常使用的是称为 *condition flags* 的五个部分的组。该组中的五个位中的每个位都可以通过有条件的分支指令进行测试。`n`，`z`，`c'和` v `位也可以通过有条件执行机制进行测试，如果一个或多个条件标志匹配相应的标志在说明本身内部。(有关此的更多信息，请在标题为 ` [条件指令执行](%EF%BC%8307_9781119183938-CH04.XHTML%EF%BC%83C04-SEC-0042) ` 的部分中。

- **`N` (Negative) flag:** Set when the result of a calculation is considered negative.
- **`Z` (Zero) flag:** Set when the result operand of an instruction is 0. Because of the way that comparisons are calculated, the `Z` flag is also set when two compared operands are equal.
- **`C` (Carry) flag:** Set when an addition generates a carry or when a subtraction generates a borrow. C is also changed by shift instructions (which shuffle the bits in a 32-bit value left or right) to the value (1 or 0) of the last bit shifted out of the operand.
- **`V` (Overflow) flag:** Set when a signed overflow occurs in the destination operand.
- **`Q` (Saturation) flag:** Used with saturated integer arithmetic instructions to indicate that the result of a saturated addition or subtraction was corrected to place it within the range of the destination operand. Saturated arithmetic is frequently used by digital signal processing (DSP) algorithms and is outside the scope of this book.

>

- **`n`(负)标志：**当计算结果被视为负面时。
- **`z`(零)标志：**指令的结果操作数为 0 时设置。由于计算比较的方式，当比较两个操作数相等时，还设置了 `z` 标志。
- **``c`(携带)标志：**添加产生随身携带或减法产生借用时设置。C 还通过移位指令(将左侧或右侧 32 位值的位的位移)更改为最后一个位从操作数中移出的值(1 或 0)。
- **`v`(溢出)标志：**设置目标操作数中的签名溢出时。
- **`q`(饱和)标志：**与饱和整数算法指令一起使用，以指示校正饱和添加或减法的结果将其置于目标操作数范围内。饱和算术经常由数字信号处理(DSP)算法使用，并且不在本书的范围之外。

With the exception of the `Q` flag, the ARM processor condition flags work very much as condition flags do in other architectures, including Intel’s.

> 除 `Q` 标志外，ARM 处理器条件标志的工作原理与其他体系结构(包括 Intel's)的条件一样非常有效。

The `T` and `J` bits select which of the three ARMv6 instruction sets is active. If the `T` bit is set, the CPU is in the Thumb state. If the `J` bit is set, the CPU is in the Jazelle state. If neither is set, the CPU is in the ARM state.

> `t` 和 `j` 位选择三个 ARMV6 指令集中的哪个处于活动状态。如果设置了 ` t` 位，则 CPU 处于 Thumb 状态。如果设置了 ` J` 位，则 CPU 处于 Jazelle 状态。如果两个都不设置，则 CPU 处于手 ARM 状态。

The CPU mode bits indicate which mode the CPU is currently using. The binary values for each mode are included in [Table 4-1](#07_9781119183938-ch04.xhtml#c04-tbl-0001).

> CPU 模式位指示 CPU 当前正在使用的模式。[表 4-1]中包括每个模式的二进制值(＃07_9781119183938-CH04.XHTML＃C04-TBL-0001)。

Four bits are used as flags indicating a greater than or equal to (`GE`) result after the execution of certain SIMD instructions.

> 在执行某些 SIMD 指令后，将四位用作标志，表示大于或等于(``GE')结果。

The `E` bit specifies the `endianness` of current CPU operations. When set to 1, it indicates little-endian operation. When cleared to 0, it indicates big-endian operations. The `E` bit must be set by two machine instructions specifically for that purpose, `SETEND LE` and `SETEND BE.`

> ` e` 位指定了当前 CPU 操作的 ` Endianness` 。设置为 1 时，它表示很小的操作。当清除为 0 时，它表示大型运营。必须专门为此目的设置两个机器指令 `` 设置 le'''和 ```''''位。

The `A` bit allows system software to discriminate between a virtual memory page fault and an actual external memory error.

> ` A` 允许系统软件区分虚拟内存页面故障和实际外部内存错误。

The `I` bit and `F` bit are interrupt masks. More on this in the next section.

> `` 我的位''f bit 是中断面具。在下一部分中有关此信息的更多信息。

#### Interrupts, Exceptions, Registers and the Vector Table

Understanding banked registers requires an understanding of the nature of interrupts and exceptions. These are events that require CPU attention, irrespective of what the CPU is doing when the event occurs. When a virtual memory page fault occurs, the CPU _must_ handle it to continue running. When the CPU encounters a machine instruction that it doesn’t understand, it must `switch gears` for a moment and figure out what to do next. When one of the computer’s peripherals has data ready or needs data, the CPU must service the request, often within a short time frame if correct operation is to be assured.

> 理解银行寄存器需要了解中断和例外的性质。这些事件需要 CPU 关注，而不论 CPU 发生时所做的事情。当发生虚拟内存页面故障时，CPU *ust* 将其处理以继续运行。当 CPU 遇到无法理解的机器指令时，它必须暂时 `切换齿轮` 并弄清楚下一步该怎么做。当计算机的外围设备中有一个数据或需要数据时，CPU 必须为请求提供服务，如果要确保正确的操作，通常会在短时间内在短时间内。

In every case, when an event happens, the CPU responds by running a special block of code known as a _handler_. Handlers are not part of user applications. They’re typically installed and configured by the operating system. There are several different classes of interrupt and exception, each with its own processor mode and banked registers. When an interrupt or exception occurs, the CPU immediately changes the processor mode, stores the current program counter in the new mode’s banked version of the link register and the CPSR in the new mode’s saved program status register (SPSR), and sets the program counter to one of a small number of addresses within the vector table; the mode and address chosen depends on the type of event that has occurred. The vector table is eight 32-bit words in length and resides either at the very bottom or nearly at the very top of the address map. Each entry is generally a single 32-bit unconditional branch instruction that directs the CPU to the appropriate handler elsewhere in memory (see Figure 4-19).

> 在每种情况下，当事件发生时，CPU 都会通过运行一个称为 *handler* 的特殊代码块来做出响应。处理程序不是用户应用程序的一部分。它们通常由操作系统安装和配置。有几个不同类别的中断和异常，每个类别都有自己的处理器模式和银行寄存器。当发生中断或异常时，CPU 立即更改处理器模式，将当前程序计数器存储在新模式的链接寄存器的银行版本中，而 CPSR 在新模式的保存程序状态寄存器(SPSR)中，并设置了程序计数器到矢量表中的少数地址之一；选择的模式和地址取决于发生的事件类型。矢量表的长度为八个 32 位单词，位于地址映射的最底部或几乎位于地址映射的顶部。每个条目通常是单个 32 位无条件分支指令，将 CPU 引导到内存中其他位置的适当处理程序(请参见图 4-19)。
> ![[FIGURE 4-19:](#07_9781119183938-ch04.xhtml#rc04-fig-0019) The ARM exception vector table](./media/images/9781119183938-fg0419.png)

You can now see the value of the banked registers. Interrupts and exceptions can happen at any time, and the CPU must have room to store the bare minimum amount of state required to resume the user-mode program where it left off. It can’t rely on being able to store the program counter in the user-mode LR, as it would normally do with a branch with link instruction. What if the interrupted program has just made a function call and needs the value in LR to know where to return to? It can’t even rely on being able to push values to the user-mode stack. What if the stack is nearly full, or the program is using R13 as a general-purpose register? The sudden appearance of banked copies of LR (R14) and SP (R13) provides room to store the return address, and a pointer (generally pre-initialised by the operating system) to a stack that is guaranteed to be valid and have enough space.

> **您现在可以看到银行寄存器的价值。中断和例外可能会随时发生，CPU 必须有空间来存储恢复其关闭的用户模式程序所需的最低状态。**它不能依靠能够将程序计数器存储在用户模式 LR 中，因为它通常使用带有链接指令的分支。如果中断的程序刚刚进行了函数调用，并且需要 LR 中的值才能知道返回哪里？它甚至不依赖能够将值推向用户模式堆栈。如果堆栈几乎已满，或者该程序将 R13 用作通用寄存器怎么办？LR(R14)和 SP(R13)的银行副本的突然出现提供了存储返回地址的空间，以及指针(通常由操作系统预先定位)到保证有效并且有足够空间的堆栈中。

The branch from the vector table takes execution into the appropriate handler, where the code does what it has to do to satisfy the exception. Typically the handler will first save some registers to the (known valid) stack to free up some registers with which to work. Once the handler is complete, it must explicitly restore these registers from the stack, and the CPSR from the copy in the SPSR, before returning to User mode and resuming execution at the address stored in the mode’s banked copy of LR.

> 矢量表中的分支将执行人员执行到适当的处理程序中，该代码可以在其中执行以满足异常的需要。通常，处理程序将首先将一些寄存器保存到(已知有效的)堆栈中，以释放一些可以使用的寄存器。处理程序完成后，它必须从堆栈中明确恢复这些寄存器，然后从 SPSR 中的副本中恢复这些寄存器，然后再返回用户模式并恢复在模式的 LR 的存储副本中存储的地址的执行。

### Fast Interrupts

There are two separate types of interrupt, which we’ll call regular (IRQ; from Interrupt Request) and fast (FIQ; from Fast Interrupt Request), corresponding to two physical signals entering the ARM11 from outside SoC, and two entries in the vector table. Fast interrupts have two useful properties that help to minimise interrupt servicing latency compared to regular interrupts.

> **有两种单独类型的中断，我们将称为常规(IRQ；从中断请求)和快速(FIQ；来自快速中断请求)，对应于两个物理信号，从外部 SOC 进入 ARM11，以及向量中的两个条目桌子**。快速中断具有两种有用的属性，可帮助最大程度地减少与常规中断相比的中断服务延迟。

The FIQ vector table entry is located at the end of the table. Although it’s perfectly permissible to insert a branch instruction to a handler in this table entry, as we must do for the IRQ entry and the various exceptions, it is more common to simply append the handler to the table, with the first instruction inside the table itself, so that the flow of control passes smoothly into the handler with no possibility of pipeline stalls.

> FIQ 矢量表条目位于表的末端。尽管完全允许将分支指令插入此表条目中的处理程序，就像我们为 IRQ 条目和各种例外所做的那样，更常见的是简单地将处理程序附加到表格上，并在表中使用第一个指令本身，使控制流平稳地进入处理程序，而没有管道摊位的可能性。

While all other processor modes have only banked copies of SP (R13) and LR (R14), FIQ mode also has banked copies of R8 to R12. FIQ handlers therefore have five dedicated scratch registers that they can use without corrupting the registers of the interrupted program or incurring the time penalty of pushing registers to the stack.

> 虽然所有其他处理器模式仅包含 SP(R13)和 LR(R14)的副本，但 FIQ 模式也将 R8 的副本添加到 R12。因此，FIQ 操作人员有五个专用的刮擦登记册，它们可以使用，而无需破坏中断程序的登记册或会导致将登记簿推入堆栈的时间罚款。

Response to FIQ events is faster and more deterministic than the IRQ case because we minimise memory access. Indeed, if the exception handler code is present in cache (see [Chapter 3](#06_9781119183938-ch03.xhtml)), the exception begins and ends without accessing system memory at all. Under Linux on Raspberry Pi, we use FIQ to service high-frequency interrupts from the USB core, and IRQ to service all other system peripherals.

> **对 FIQ 事件的响应比 IRQ 情况更快，更确定性，因为我们最大程度地减少了内存访问**。实际上，如果缓存中存在异常处理程序代码(请参见[[第 3 章](%EF%BC%8306_9781119183938-CH03.xHTML))，则异常开始和结束，而无需访问系统内存。在 Raspberry Pi 上的 Linux 下，我们使用 FIQ 为 USB 核心的高频中断服务，并为所有其他系统外围设备服务。

### Software Interrupts

One further type of event deserves mention at this point. Unlike all the other interrupts and exceptions, a software interrupt (SWI) doesn’t interrupt what the CPU is doing at some unplanned moment. Instead, it can be seen as a kind of subroutine call that’s used to enter supervisor mode in a carefully managed way, generally for the purpose of communicating with the operating system kernel. The SWI doesn’t include the address of the subroutine in the call; instead, software interrupts are numbered, and the number of the software interrupt is included as an operand to the software interrupt machine instruction, which would be written like this in ARM assembly language:

> 此时，另一种类型的事件值得一提。**与所有其他中断和异常不同，软件中断(SWI)不会中断 CPU 在某些计划外的时刻正在做什么。**取而代之的是，它可以看作是一种以精心管理的方式进入主管模式的子例程呼叫，**通常是为了与操作系统内核进行通信**。SWI 在通话中不包括子例程的地址；取而代之的是，软件中断已编号，并且软件中断的数量作为操作数作为操作数，用于软件中断机器的指令，该指令将以 ARM 组装语言像这样写：

```
    SWI 0x21
```

When an SWI instruction is executed, the CPU executes the branch instruction stored at address 0x0000 0008 in the vector table (refer to [Figure 4-19](#07_9781119183938-ch04.xhtml#c04-fig-0019)). This branch takes execution to the SWI handler. The interrupt number included as the operand to the SWI instruction is generally used by the exception handler to select yet another branch, to the block of code that handles the specific software interrupt given in the operand. There may be dozens or more software interrupts, each with its own number and each with a subhandler corresponding to that number.

> 执行 SWI 指令后，CPU 在矢量表中执行存储在地址 0x0000 0008 的分支指令(请参阅[图 4-19](%EF%BC%8307_9781119183938-CH04.XH04.XHTML%EF%BC%83C04-fig-0019))。该分支将执行人员执行到 SWI 处理程序。异常处理程序通常使用作为操作数作为操作数作为操作数所包含的中断号码，以选择另一个分支，即处理操作数中给出的特定软件中断的代码块。可能会有数十个或更多的软件中断，每个软件都有自己的数字，每个都有与该数字相对应的副教。

The value of SWIs is that they allow user programs to make managed calls into the operating system. As mentioned in [Chapter 8](#11_9781119183938-ch08.xhtml), the operating system kernel comprises code for accessing peripherals, providing a virtual machine abstraction to individual processes and guaranteeing security properties, including isolation between processes. The limitations on what applications can do when in User mode, particularly with respect to configuring the MMU (see [Chapter 3](#06_9781119183938-ch03.xhtml)), underpin the notion of process isolation. An SWI is the only way to switch from User to Supervisor mode; forcing this transition to happen via the vector table prevents applications from running arbitrary code in a privileged mode.

> **SWIs 的价值在于，它们允许用户程序将托管呼叫纳入操作系统。**如[第 8 章](%EF%BC%8311_9781119183938-CH08.XHTML)中提到的，操作系统内核包含用于访问外围设备的代码，向单个流程提供虚拟机抽象并保证安全属性，包括流程之间的隔离。在用户模式下，有关应用程序可以执行的限制，尤其是在配置 MMU 方面(请参阅[第 3 章](%EF%BC%8306_978111919183938-CH03.XHTML))，是过程隔离概念的基础。SWI 是从用户转换为主管模式的唯一方法；通过向量表强迫这种过渡发生，可以防止应用程序在特权模式下运行任意代码。

### Interrupt Priority

So what happens when a second interrupt or exception occurs while an earlier one is still being handled? Handlers are special in a number of ways but they’re still code, and they take time to run. Having an exception occur while an exception handler is running is not only possible but likely. Sorting this out is done in two general ways:

> 那么，当第二次中断或异常仍在处理时，会发生什么呢？处理程序在多种方面很特别，但它们仍然是代码，并且需要时间运行。当异常处理程序运行时发生异常，不仅可能而且可能是可能的。对此进行整理，以两种一般的方式完成：

- Both kinds of interrupt (IRQ and FIQ) may be disabled independently while an exception handler is executing. This is done with two disable bits in the CPSR: F and I. Setting F to 1 disables fast interrupts. Setting I to 1 disables conventional interrupts. Interrupts may be disabled within all or part of an exception handler.
- Each of the various classes of exception has a priority (see Table 4-2). Priorities work like this: a handler for an interrupt or exception of a given priority may be interrupted by one of higher priority, but not by one of lower priority. For example, the handler for the Reset exception is of Priority 0 and may not be interrupted by anything. An IRQ handler may be interrupted by an FIQ exception, but not vice versa.

>

- **在执行异常处理程序时，两种中断(IRQ 和 FIQ)可以独立禁用。**这是通过 CPSR：F 和 I 的两个禁用位完成的。设置 F 到 1 设置 F 禁用快速中断。设置 I 到 1 个禁用常规中断。在异常处理程序的全部或部分中可以禁用中断。
- 各种异常类别都有优先级(请参见表 4-2)。这样的优先级工作：一个用于中断或除外优先级的处理程序可能会被较高的优先级之一中断，而不是优先级之一。例如，重置异常的处理程序是优先级 0，并且可能不会被任何内容中断。IRQ 处理程序可能会因 FIQ 例外而中断，但反之亦然。

[Table 4-2](#07_9781119183938-ch04.xhtml#rc04-tbl-0002) ARM11 Interrupt Priorities

**Exception** **Priority** -----------------------------

- Reset 1 Data abort 2 Fast interrupt (FIQ) 3 Conventional interrupt (IRQ) 4 Prefetch abort 5 Software interrupt 6 Undefined instruction 6

When an interrupt handler begins executing, all interrupts of the same priority are automatically disabled. Thus an IRQ handler cannot be interrupted by another IRQ exception unless the IRQ handler has the intelligence to sort out simultaneous interrupts and re-enables IRQ exceptions.

> **当中断处理程序开始执行时，同一优先级的所有中断都会自动禁用。**因此，除非 IRQ 处理程序具有同时中断和可重复的 IRQ 异常，否则 IRQ 处理程序不能被另一个 IRQ 例外中断。

Interrupts may not be disabled by software running in User mode, because this would undermine the operating system’s ability to schedule other processes. Software interrupts may be issued by userland programs, but because software interrupts have the lowest priority, all other kinds of exceptions may occur during a software interrupt handler, unless interrupts are specifically disabled.

> 在用户模式下运行的软件可能不会禁用中断，因为这会破坏操作系统安排其他流程的能力。软件中断可能是由 Userland 程序发布的，但是由于软件中断的优先级最低，因此在软件中断处理程序期间可能会发生所有其他类型的异常，除非中断专门禁用。

The software interrupt exception has the same priority as the undefined instruction exception because the two cannot occur together. All software interrupts are generated by the SWI instruction, which is present in all ARM processors and is thus always defined.

> 软件中断异常具有与未定义指令异常相同的优先级，因为两者不能一起出现。所有软件中断均由 SWI 指令生成，SWI 指令都存在于所有 ARM 处理器中，因此始终定义。

### Conditional Instruction Execution

In most instruction set architectures, conditional branch instructions are used to alter the flow of program execution. The ARM CPUs have conditional branch instructions, but they also offer something that in many cases is even better: conditional instruction execution. All 32-bit ARM instructions have a 4-bit field inside them expressing condition codes. The ARM architecture provides 15 condition codes, for conditions like equal, not equal, greater than, less than, overflow, and so on. (Four bits are capable of expressing 16 conditions codes, but one of the values is reserved and not used.) The condition code field is evaluated while the instruction is being decoded by the CPU.

> 在大多数指令集架构中，有条件的分支指令用于更改程序执行的流程。ARM CPU 具有有条件的分支说明，但它们在许多情况下还提供了更好的东西：有条件的说明执行。所有 32 位 ARM 指令都有一个 4 位字段，表达了条件代码。ARM 架构提供 15 条条件代码，适用于等相等，不相等，大于，小于溢出等的条件代码。(四个位能够表达 16 个条件代码，但其中一个值保留并未使用。)在 CPU 解码时，评估了条件代码字段。

The codes correspond to various combinations of the four condition flags maintained in the CPSR: `N`, `Z`, `C`, and `V`. If conditional execution is enabled for an instruction then that instruction executes _only_ if its condition code agrees with the current state of the condition flags.

> 代码对应于 CPSR 中维护的四个条件标志的各种组合：`n`，`Z`，`c'和'v`。如果为指令启用了条件执行，则该指令执行 _only_ 如果其条件代码与条件标志的当前状态一致。

> [!NOTE]
> that this is _not_ a bit-by-bit comparison of the condition codes to the four CPSR flags. Each four-bit binary value has an assigned meaning—for example:

- %0000 means that the instruction executes if the `Z` flag is set.
- %0001 means that the instruction executes if the `Z` flag is cleared.
- %1000 means the instruction executes if the `C` flag is set and the `Z` flag is cleared.
- %1100 means that the instruction executes if the `Z` flag is cleared, and the `N` flag is equal to the V flag.

> - ％0000 表示如果设置了 `Z` 标志，则指令执行。
> - ％0001 表示如果清除 `Z` 标志，则执行指令。
> - ％1000 表示指令执行如果设置了 `c` 标志，并且清除 `Z` 标志了。
> - ％1100 表示指令执行如果清除 `z` 标志，`n` 标志等于 v 标志。

One of the codes, %1110, means that the flags will be ignored and that the instruction will always execute. (Recall that the `%` prefix means that the value shown is in binary notation.)

> 其中一个代码为％1110，意味着标志将被忽略，并且指令将始终执行。(回想一下 `％` 前缀表示所示的值是二进制表示法。)

Condition codes are built into machine instructions by the assembler or compiler that creates an executable program. For assembly language, condition codes are specified with a two-character suffix appended to the mnemonic indicating the condition or conditions under which the instruction will execute. For example:

> 条件代码是由创建可执行程序的汇编程序或编译器内置在机器指令中。对于汇编语言，条件代码是用两个字符的后缀指定的，附加到助记符上，指示指示指令执行的条件或条件。例如：

- `MOV R0, #4` No suffix; always executes `MOVEQ R0, #4` Executes if `Z=1` (Equal) `MOVNE R0, #4` Executes if `Z=0` (Not Equal) `MOVMI R0, #4` Executes if `N=1` (Negative) -----------------------------------------------------

All of these instructions copy the value 4 into R0. The first form lacks a suffix, and so it executes unconditionally; that is, always. The second form executes only if the `Z` flag in CPSR is set to 1, indicating that an earlier comparison (or other operation) generated a result of 0; for comparisons, a result of 0 indicates that the two values compared were equal. The third form executes only if an earlier operation cleared the `Z` flag to 0; for comparisons, this means that the values compared were not equal. The fourth form executes only if the `N` flag is set to 1, meaning that a comparison or other operation generated a negative value. There are 15 possible condition codes, including a code meaning `execute always` .

> 所有这些指令将值 4 复制到 R0 中。第一种形式缺少后缀，因此它无条件地执行。也就是说，永远。仅当 CPSR 中的 `Z` 标志设置为 1 时才能执行第二张形式，这表明早期比较(或其他操作)生成了 0 的结果；为了进行比较，0 的结果表明比较的两个值相等。仅当较早的操作将 `Z` 标志清除为 0 时才能执行第三个表单；对于比较，这意味着比较的值不相等。仅当 `n` 标志设置为 1 时才执行第四形式，这意味着比较或其他操作产生了负值。有 15 个可能的条件代码，包括一个代码，含义 `始终执行` 。

Why is conditional execution such a useful feature? Figure 4-20 shows two ways of doing the same thing in ARM assembly language. The algorithm is a simple IF/THEN construct: If R0 = R4, then execute the code in Block A; otherwise, execute the code in Block B. What the code in Block A and Block B actually does is not important for the example, and the instruction boxes in those blocks have been deliberately left blank.

> 为什么有条件执行如此有用？图 4-20 显示了在 ARM 组装语言中执行相同操作的两种方法。该算法是一个简单的算法，如果/然后构造：如果 r0 = r4，则在块 a 中执行代码；否则，在块 B 中执行代码。块 A 和块 B 中的代码实际上对示例并不重要，并且这些块中的指令框已故意留为空白。

> ![[FIGURE 4-20:](#07_9781119183938-ch04.xhtml#rc04-fig-0020) ARM conditional execution](./media/images/9781119183938-fg0420.png)

The first machine instruction is a comparison that checks to see if two registers (R0 and R4) are equal. The `CMP` (compare) instruction does that. If the two registers are found to be equal, `CMP` sets the `Z` flag to 1. If they are not equal, `CMP` sets the Z flag to 0.

> 第一台机器指令是一个比较，检查以查看两个寄存器(R0 和 R4)是否相等。`cmp'(比较)指令这样做。如果发现两个寄存器是相等的，则` cmp `将``z` 标志''设置为 1。如果它们不相等，则 `cmp` 将 z 标志设置为 0。

The traditional way of coding this, in ARM or any other architecture, is on the right. After `CMP`, a conditional branch instruction tests the `Z` flag for inequality using the `NE` (Not Equal) suffix. If the two registers are not equal, execution branches to a location labelled BlockB. If the two registers are equal, the conditional branch lets execution continue into Block A. At the end of Block A, an unconditional branch takes execution to whatever code lies after the IF/THEN construct. Block B begins at the label BlockB, and continues to the end of the IF/THEN construct.

> 对此进行编码的传统方式，在 ARM 或任何其他架构中，是正确的。在 ` CMP` 之后，有条件的分支指令使用 `ne'(非平等)后缀测试` Z` 标志。如果两个寄存器不相等，则执行分支为位于标有块的位置。如果两个寄存器相等，则条件分支让执行继续进入块 A。在块 A 的末尾，无条件分支将执行执行到 IF/then 构造之后的任何代码。B 块 B 从标签块开始，然后继续到 IF/Then 构造的末端。

The sequence of instructions on the left does the very same thing. This time, however, all of the instructions are subject to conditional execution. The instructions in Block A have been set to execute only if the `Z` flag is 1 (condition code set to %0000). The instructions in Block B have been set to execute only if the `Z` flag is 0 (condition code set to %0001). The other flags are not involved in this example. In terms of which blocks execute, you can see that it’s either/or: if Block A is executed, Block B will not be, and vice versa. No branches are required.

> 左侧的指令顺序也做同样的事情。但是，这次所有说明均由有条件执行。仅当 ` z` 标志为 1(条件代码设置为％0000)时，块 A 中的指令已设置为执行。B 块中的指令仅在 `Z` 标志为 0 时都设置为执行(条件代码设置为％0001)。其他标志不涉及此示例。在执行哪些块的情况下，您可以看到它是/或：如果执行块 A，则 B 块 B 将不会，反之亦然。无需分支。

Conditional execution makes two instructions unnecessary: the BNE conditional branch, and the B unconditional branch. That’s valuable all by itself. The real win, however, is that mispredicted branches can disrupt the instruction pipeline and slow down execution. Anything that can be done to avoid branches will speed up execution.

> 条件执行使两个说明不必要：BNE 条件分支和 B 无条件分支。这本身很有价值。然而，真正的胜利是，错误预测的分支机构可以破坏指令管道并放慢执行速度。任何可以避免分支机构的事情都会加快执行力。

It’s important to remember that instructions are not `skipped` when their condition codes are not met. They still move through the pipeline and consume one clock cycle. However, they do no work and change nothing. The benefit of conditional execution derives from the avoidance of branches over small blocks of code, which can cost much more time than reading (but not executing) the block. There is a block size threshold (which varies between microarchitectures) above which the branch implementation of an IF/THEN construct is preferred. This threshold is not large, and in most microarchitectures it’s as little as three or four instructions.

> 重要的是要记住，当未满足其条件代码时，指示不会 `跳过` 。他们仍然在管道中移动并消耗一个时钟周期。但是，他们没有工作，也什么也不改变。有条件执行的好处来自于避免分支在小块上，这比读取(但不能执行)块的时间要多得多。有一个块大小阈值(在微体系之间有所不同)，在该阈值中，首选 if/then 构造的分支实现。这个阈值不大，在大多数微体系结构中，它仅需三到四个说明。

## Coprocessors

There’s nothing new about coprocessors, and they are not specific to the ARM architecture. Understanding how they operate in an ARM11 context does require an understanding of CPU exceptions, so this is a good point to take them up.

> 协作者没有什么新鲜事物，而且不是针对 ARM 建筑的特定问题。了解它们在 ARM11 上下文中的操作确实需要了解 CPU 例外，因此这是吸引它们的好点。

A _coprocessor_ is a separate, specialised execution unit that usually has an instruction set of its own, distinct from that of the CPU. It generally has additional registers to support its machine instructions. Early in microprocessor history, coprocessors were separate chips, connected to the CPU through an external bus. One of the earliest and best-known coprocessors was Intel’s 1980-era 8087, which lived in a separate 40-pin Dual Inline Package (DIP) socket and could be installed by a careful end user. The 8087 provided floating point maths instructions to the integer-only 8086 and 8088. It implemented 60 new instructions and several numeric concepts previously unavailable in microcomputers, like denormals to express underflow values, and the not-a-number (NaN) value to hold the results of undefined operations like divide-by-zero or values outside the domain of real numbers, like imaginary numbers.

> _coprocessor_ 是一个独立的专业执行单元，通常具有其自己的指令集，与 CPU 的指令集不同。它通常有其他寄存器来支持其机器说明。在微处理器历史记录的早期，协处理器是单独的芯片，通过外部总线连接到 CPU。英特尔(Intel)的 1980 年 8087 是最早，最著名的协处理器之一，该公司居住在单独的 40 针双线包装(DIP)插座中，可以由仔细的最终用户安装。8087 向仅整数 8086 和 8088 提供了浮点数学说明。它实施了 60 个新说明和以前在微型计算机中无法使用的几个数字概念，例如表达下流动值的 Denormals，并保持 Not-A-a-number(NAN)值来保持价值(NAN)值未定义的操作的结果，例如划分为零或值之外的值，例如虚构数字。
