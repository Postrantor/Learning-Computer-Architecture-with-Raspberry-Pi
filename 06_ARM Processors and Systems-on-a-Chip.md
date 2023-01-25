Chapter 4

# ARM Processors and Systems-on-a-Chip

**THIS CHAPTER IS** about central processing units (CPUs), the beating hearts at the centre of all computers. A great deal of what people call `computer architecture` is the inner structure of the CPU. More specifically, this chapter is about the Advanced RISC Machine (ARM) processors, especially the ARM11 microarchitecture used in the original Raspberry Pi.

> **本章是关于中央处理单元(CPU)的**，这是所有计算机中心的跳动心。人们称之为 `计算机架构` 的大量是 CPU 的内部结构。更具体地说，本章是关于高级 RISC 机器(ARM)处理器的，尤其是原始 Raspberry Pi 中使用的 ARM11 微体系结构。

The focus on the ARM11 microprocessor architecture leads to a secondary topic in this chapter: system-on-a-chip (SoC) devices, which include not only an ARM CPU but also a graphics processor, a mass-storage controller for SD card access, a serial port controller and several other subsystems that have often been implemented as separate chips or chip sets outside the CPU.

> 对 ARM11 微处理器体系结构的关注将导致本章中的次要主题：系统启动(SOC)设备，不仅包括 ARM CPU，还包括图形处理器，SD 卡访问的质量存储控制器，一个串行端口控制器和其他几个子系统通常被用作 CPU 之外的单独芯片或芯片集。

## The Incredible Shrinking CPU

Early computers were enormous because they had to be; at first, digital logic was based on high-reliability versions of what were essentially radio tubes, each of which was the size of your thumb. Whole rooms in specially engineered buildings were needed to house, power and cool thousands of radio tubes. Imagine a building the size of a modern server farm—which today would house rack upon rack of multicore blade servers—containing a _single_ CPU.

> 早期的计算机很大，因为它们必须是。起初，数字逻辑是基于基本是无线电管的高可靠性版本，每个逻辑都是 Thumb 的大小。需要专门设计的建筑物中的整个房间来容纳，电源和凉爽的数千个无线电管。想象一下，现代服务器农场的建筑物(如今)将在多层刀片服务器上容纳架子，并使用 _single_ CPU。

The arrival of commercially manufactured transistors in 1955 ushered in the second generation of CPUs. The new developments meant that what had previously filled whole rooms could now be contained in three or four cabinets the size of refrigerators. Transistors were one-hundredth the size of the tubes that they replaced and required one-thousandth of their power. Printed-circuit technology allowed the mass production of computers, albeit for small values of `mass` . IBM had made exactly 19 of their first-generation tube-based 701 systems. Just a few years later, IBM’s transistor-based 1401 sold 10,000 units. The original PDP-8 machines from Digital Equipment Corporation (DEC) were only half the size of a refrigerator and more than 50,000 units were sold.

> 1955 年，商业生产的晶体管的到来迎来了第二代 CPU。新的发展意味着以前填满了整个房间的东西现在可以包含在冰箱大小的三个或四个橱柜中。晶体管是它们所取代的管子的大小的一百分之一，需要千分之一的功率。印刷电路技术允许计算机的质量生产，尽管质量为小值。IBM 恰好制作了其第一代基于试管的 701 个系统中的 19 个。几年后，IBM 的基于晶体管的 1401 售出了 10,000 辆。数字设备公司(DEC)的原始 PDP-8 机器仅是冰箱的一半，售出了超过 50,000 台。

The third generation of computer technology arrived in the mid-1960s with the development of integrated circuits. By placing first a few, and eventually many, transistors on a single silicon chip, movement was allowed in two directions: high-end computers (mainframes) stayed physically large but increased their compute power enormously; and lower-end computers (minicomputers) were smaller in size and their price meant that smaller companies and schools could afford them. By 1970, the PDP-8 CPU cabinet was half a metre wide by not quite a metre long, and only 30cm high. Its peripherals (mechanical printers, tape and disk drives, power supply and so on) made the full system fairly bulky, but the CPU itself could fit on a desktop and was only a little larger than the first personal computers. Across its lifetime, the PDP-8 series sold half a million units.

> 第三代计算机技术随着综合电路的发展而到达 1960 年代中期。通过将几个，最终将许多晶体管放在单个硅芯片上，允许在两个方向上移动：高端计算机(大型机)保持物理较大，但大大增加了其计算功率；低端计算机(微型计算机)的尺寸较小，其价格意味着较小的公司和学校可以负担得起。到 1970 年，PDP-8 CPU 机柜的宽度不超过一米，高 30 厘米。它的外围设备(机械打印机，磁带和磁盘驱动器，电源等)使整个系统相当笨重，但是 CPU 本身可以放在台式机上，并且比第一批个人计算机大一点。PDP-8 系列在其一生中售出了 50 万台。

### Microprocessors

As small as it was, the commercial PDP-8 minicomputer CPU was still spread out across several circuit boards crammed with individual integrated circuits. (A special-purpose single-chip version appeared in the mid-1970s, long after the PDP-8 had begun its fall to obscurity.) Silicon fabrication techniques continued to improve in the late 1960s, driven by the mainframe computer industry’s insatiable demand for solid-state memory chips. By 1970 it was possible to fabricate 2,500 transistors on a single silicon chip. This was enough (barely) to cover all the necessary logic of a simple CPU. A team led by Intel’s Federico Faggin designed the 4004 microprocessor, which became the first commercial mass-produced single-chip CPU.

> 虽然很小，但商业 PDP-8 微型计算机 CPU 仍在挤满了单个集成电路的几个电路板上。(在 PDP-8 开始陷入晦涩之后，在 1970 年代中期出现了一种特殊的单芯片版本。)硅制造技术在 1960 年代后期不断改进，这是由大型计算机行业对不可能的对无限的需求驱动的固态 Mem 芯片。到 1970 年，可以在单个硅芯片上制造 2500 个晶体管。这足以涵盖简单 CPU 的所有必要逻辑。由英特尔的 Federico Faggin 领导的团队设计了 4004 个微处理器，该团队成为第一个商业质量生产的单芯片 CPU。

The 4004 is considered an oddity today because of its 4-bit data word; its primary use was in desktop calculators. Nonetheless, it had the same memory addressing capability (4,096 bytes) as the PDP-8. It was the seed from which Intel grew its CPU empire. The company quickly released the 8008 in 1972 and the 8080 in 1974. The 8080 contained 4,500 transistors, and its design influenced all successful Intel CPUs from then on. In 1974, the 8080 became the heart of what is recognised as the first truly useful personal computer, the Altair 8800.

> 由于其 4 位数据词，今天的 4004 被认为是奇怪的。它的主要用途是在桌面计算器中。尽管如此，它具有与 PDP-8 相同的 Mem 解决功能(4,096 个字节)的相同内存。这是英特尔成长其 CPU 帝国的种子。该公司在 1972 年迅速发布了 8008，并于 1974 年发行了 8080。8080 包含 4,500 个晶体管，其设计从那时起就影响了所有成功的英特尔 CPU。1974 年，8080 成为公认是第一台真正有用的个人计算机 Altair 8800 的核心。

On the heels of the 8080 came dozens of microprocessors, some of which were quite successful: Motorola’s 6800, Zilog’s Z80, RCA’s COSMAC 1802 series (which in a radiation-hardened silicon-on-sapphire variant was used in many spacecraft, including Galileo) and MOS Technology’s 6502, which was used in several very popular personal computers including the Apple II and the original BBC Microcomputer, which led directly to the development of the Acorn ARM processors.

> 在 8080 的紧随其后，有数十个微处理器，其中一些非常成功：摩托罗拉的 6800，Zilog 的 Z80，RCA 的 Cosmac 1802 系列(在包括 Galileo 在内的许多航天器中使用了辐射式硅变体中的辐射式硅变体中)以及 MOS Technology 的 6502，该 6502 在包括 Apple II 和原始 BBC 微型计算机在内的几家非常流行的个人计算机中使用，该计算机直接导致了 Acorn Arm 处理器的开发。

Most of those early microprocessors fell into the shadows of Motorola and Intel before 1980. The 30,000-transistor 8086 (and its budget-priced sibling, the 8088) kicked personal computing into the business world with the IBM PC. The 50,000-transistor 68000 powered the first graphical user interface (GUI) computers, including the Sun and Apollo workstations and later the Apple Lisa and Macintosh. Motorola’s and Intel’s microprocessor architectures were competitors as they evolved, but Motorola’s 68000 architecture had a difficult time competing with Intel CPUs and fell out of use by the mid-1990s. By 2006, Apple Computer was using Intel processors in its Macintosh line, and Intel became the dominant player in personal computing. By 2016, Intel’s Haswell-E CPUs contained 2.6 billion transistors, and the high-end Xeon server chips could have more than two billion. Intel’s `Knight’s Corner` Xeon Phi supercomputer component processor contains an astonishing seven _billion_ transistors.

> 这些早期的微处理器大多数在 1980 年之前就落入了摩托罗拉和英特尔的阴影。30,000 台 8086(及其预算价格定价的兄弟姐妹，8088)使用 IBM PC 启动了个人计算。50,000-Tranistor 68000 为第一个图形用户界面(GUI)计算机提供了动力，包括 Sun 和 Apollo 工作站以及后来的 Apple Lisa 和 Macintosh。摩托罗拉(Motorola)和英特尔(Motorola)的微处理器体系结构是竞争对手的发展，但是摩托罗拉(Motorola)的 68000 建筑很难与英特尔 CPU 竞争，并在 1990 年代中期不使用。到 2006 年，Apple Computer 在其 Macintosh 系列中使用了英特尔处理器，英特尔成为个人计算中的主要参与者。到 2016 年，英特尔的 Haswell-E CPU 拥有 26 亿晶体管，高端 Xeon Server 芯片可能拥有超过 20 亿。英特尔的 `骑士角` Xeon Phi 超级计算机组件处理器包含一个令人惊讶的七个 _BILLIN_ 晶体管。

### Transistor Budgets

These numbers aren’t just mind-blowing. Transistor count has affected the evolution of microprocessor architectures in fundamental ways. For example, any CPU design begins with an engineering study to indicate how large the silicon die will be, and at what size the transistors will be fabricated. This gives a maximum transistor count for the die long before any of the actual die layout has been performed.

> 这些数字不仅令人难以置信。晶体管计数以基本方式影响了微处理器架构的演变。例如，任何 CPU 设计都始于工程研究，以指示硅死亡的大小，以及晶体管将被制造的大小。在执行任何实际模具布局之前，这给了 DIE 的最大晶体管计数。

After the total number of transistors is known, those transistors are parcelled out to the various component functions that make up a CPU: so many transistors go to cache, so many go to the registers, so many go to implementing machine instructions and so on. Subsystem design teams guard these `transistor budgets` as jealously as governments or corporations guard their financial budgets.

> 在知道晶体管的总数之后，这些晶体管被包裹在构成 CPU 的各种组件函数上：如此多的晶体管转到缓存，许多晶体管都进入了寄存器，因此许多晶体管都去实现机器指令等。子系统设计团队像政府或公司一样谨慎地保护这些 `晶体管预算` 。

The eventual CPU design is always a compromise between the features the designers want to `buy` and the limitations of the transistor budget they are given to shop with. If you ask a CPU designer why one particular desirable feature didn’t make it into final silicon, the answer is almost invariably, `We didn’t have the transistor budget for it` .

> 最终的 CPU 设计始终是设计师想要 `购买` 的功能与他们提供的晶体管预算的局限性之间的折衷。如果您询问 CPU 设计师为什么一个特殊理想的功能没有进入最终硅，那么答案几乎总是总是 `我们没有晶体管预算` 。

## Digital Logic Primer

[Chapter 3](#06_9781119183938-ch03.xhtml) explained that computers store data as patterns of binary 1s and 0s, expressed as the presence or absence of a voltage on a wire. A full treatment of digital logic design is beyond the scope of this book, but we review here a few basic concepts that are helpful in understanding the internal workings of CPUs.

> [第 3 章](%EF%BC%8306_9781119183938-CH03.XHTML)解释说，计算机将数据存储为二进制 1 和 0 的模式，以电线上的电压表示为二进制 1 和 0。对数字逻辑设计的完整处理超出了本书的范围，但是我们在这里回顾了一些有助于理解 CPU 的内部工作的基本概念。

### Logic Gates

All computation in digital computers is performed by _logic gates_, which accept one or more binary inputs and generate (usually) one binary output. The four most basic logic gates are NOT, AND, OR, and XOR. These logic gates are shown in Figure 4-1 with their truth tables, which summarise what output value is generated for every possible combination of inputs. Each type of gate is represented by a symbol, which is used in schematic diagrams of multigate logic circuits.

> 数字计算机中的所有计算均由 _logic Gates_ 执行，该 _logic Gates_ 接受一个或多个二进制输入并生成(通常)一个二进制输出。四个最基本的逻辑门不是，或者和 XOR。这些逻辑门与它们的真实表显示在图 4-1 中，总结了对输入的每种可能组合生成的输出值。每种类型的门都由一个符号表示，该符号用于多仪逻辑电路的示意图。

> ![[FIGURE 4-1:](#07_9781119183938-ch04.xhtml#rc04-fig-0001) The four basic logic gates](./media/images/9781119183938-fg0401.png)

A chip designer has access to a cell library with which he or she can construct larger circuits. A modern complementary metal-oxide semiconductor (CMOS) cell library has hundreds of cells computing a range of more complex functions that have several inputs, but at their hearts all of these more complex CMOS functions are constructed using NMOS (N-channel Metal Oxide Semiconductor) transistors and PMOS (P-channel Metal Oxide Semiconductor) transistors. NMOS transistors conduct when their gate input is high (that is, +V, whatever voltage is used in the design) and PMOS transistors conduct when their gate inputs are low, or 0V (often called _ground_). NMOS and PMOS transistors are thus _complementary_ in how they conduct. We can use one NMOS and one PMOS transistor to form the basic CMOS NOT gate (often called an _inverter_), as shown in Figure 4-2.

> 芯片设计师可以使用他或她可以构建更大电路的单元库。现代的互补金属氧化物半导体(CMOS)细胞库具有数百个细胞计算一系列具有多个输入的更复杂函数的单元，但是在他们的心中，所有这些更复杂的 CMOS 函数都是使用 NMOS 构建的(N-Channel Metal Oxine oxinel aciponductor)晶体管和 PMO(P 通道金属氧化物半导体)晶体管。NMOS 晶体管的门输入高(即，+V，设计中使用的任何电压)时会进行操作，而 PMOS 晶体管在门输入较低或 0V(通常称为* ground*)时进行性能。因此，NMOS 和 PMOS 晶体管在其传导方式方面是 *plementary *的。如图 4-2 所示，我们可以使用一个 NMO 和一个 PMOS 晶体管形成基本的 CMOS 而不是门(通常称为 _inverter_)。

> ![[FIGURE 4-2:](#07_9781119183938-ch04.xhtml#rc04-fig-0002) A CMOS NOT gate](./media/images/9781119183938-fg0402.png)

When a high voltage level (binary 1) is placed at the input terminal, the NMOS transistor conducts, pulling the output low (binary 0). When a low voltage level (binary 0) is placed on the input terminal, the PMOS transistor conducts, pulling the output high (binary 1).

> 当将高压水平(二进制 1)放置在输入端子上时，NMOS 晶体管会导电，从而将输出低(二进制 0)拉出。当将低电压水平(二进制 0)放在输入端子上时，PMOS 晶体管会导电，将输出高(二进制 1)拉出。

All logic gates impose a characteristic delay, which is the time required for the output or outputs to respond to a change in one or more of the inputs. If you connect simple gates together in sequence (that is, with the output of one connected to the input of the next) to compute a more complex function, the delay of the composite circuit is given by the sum of the delays on the longest path from an input to an output. This is known as the propagation delay of a logic path.

> 所有逻辑门都施加了一个特征延迟，这是输出或输出响应一个或多个输入的变化所需的时间。如果将简单的门以顺序连接在一起(即，将一个连接到下一个输入的输出连接到下一个输入)以计算一个更复杂的函数，则复合电路的延迟由最长路径上的延迟的总和给出从输入到输出。这被称为逻辑路径的传播延迟。

### Flip-Flops and Sequential Logic

You now know how to build combinatorial functions of arbitrary inputs (that is, functions created by combining simpler logic gates), but to build a computer you need to be able to build systems that have _state_ (memory) and can evolve that state over time. [Chapter 3](#06_9781119183938-ch03.xhtml) mentioned the bi-stable flip-flop as the storage element in simple SRAM (Static Random Access Memory) cells. The D-type flip-flop is the ideal storage element for saving a state inside a computer; see Figure 4-3.

> 现在，您知道如何构建任意输入的组合函数(即通过组合更简单的逻辑门创建的函数)，但是要构建计算机，您需要能够构建具有 _state_(内存)的系统，并且可以随着时间的推移而发展该状态。[第 3 章](%EF%BC%8306_9781119183938-CH03.XHTML)提到了双稳定的触发器作为简单 SRAM(静态随机访问存储器)单元格中的存储元件。D 型触发器是将状态保存在计算机内的理想存储元件。见图 4-3。
> ![[FIGURE 4-3:](#07_9781119183938-ch04.xhtml#rc04-fig-0003) How a D-type flip-flop works](./media/images/9781119183938-fg0403.png)
