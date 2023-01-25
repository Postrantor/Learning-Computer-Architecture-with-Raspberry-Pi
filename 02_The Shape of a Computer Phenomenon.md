Chapter 1

# The Shape of a Computer Phenomenon

**THAT OLD SAYING** about good things coming in small packages describes the Raspberry Pi perfectly. It also highlights an advance in computer architecture—the system-on-a-chip (SoC), a tiny package with a rather large collection of ready-to-use features. The SoC isn’t so new—it’s been around a long time—but the Raspberry Pi’s designers have put it into a small, powerful package that is readily available to students and adults alike. All for a very low price.

> **那句老话**关于小包包装的好东西，完美地描述了 Raspberry Pi。它还突出了计算机体系结构的进步-Any-A-Chip(SOC)，这是一个小包装，具有相当大的现成功能。SOC 并不是那么新，它已经很长时间了 - 但是 Raspberry Pi 的设计师已经将其放入了一个小型，功能强大的包装中，并且很容易为学生和成人提供。所有这些价格都非常低。

A tiny piece of electronics about the size of a credit card, the Raspberry Pi single-board computer packs very respectable computing power into a small space. It provides tons of fun and many, many possibilities for building and controlling all sorts of fascinating gizmos. When something is small, after all, it fits just about anywhere. The Raspberry Pi does things conventional computers just can’t do in terms of both portability and connectivity. Things you will find inspire your creativity—fun things!

> Raspberry Pi 单板计算机包装的一小部分关于信用卡大小的电子设备，将非常可观的计算能力带入一个小空间。它为建造和控制各种引人入胜的小玩意提供了许多乐趣和许多可能性。毕竟，当某物很小时，它几乎适合任何地方。Raspberry Pi 可以在便携性和连接性方面做传统计算机无法做的事情。您会发现的事情激发了您的创造力 - 事物！

What’s not to like? Get ready for some truly exciting computer architecture.

> 不喜欢什么？为一些真正令人兴奋的计算机架构做好准备。

In this chapter introducing the truly phenomenal Raspberry Pi line of computer boards, we look first at the Raspberry Pi’s goals and history. We include the history of the Raspberry Pi’s development and the visionary people at the Raspberry Pi Foundation who dreamed up the concept and achieved the reality, and we look at the advantages this tiny one-board computer has over much larger computers. We then take a tour of the Raspberry Pi board.

> 在本章介绍真正惊人的 Raspberry Pi 电脑板系列中，我们首先要研究 Raspberry Pi 的目标和历史。我们包括 Raspberry Pi 开发的历史以及 Raspberry Pi 基金会的有远见人士，他们梦见了这个概念并实现了现实，我们看一下这台小型单板计算机比更大的计算机具有的优势。然后，我们参观 Raspberry Pi 板。

## Growing Delicious, Juicy Raspberries

As significant advances in computing go, the Raspberry Pi’s primary innovation was the lowering of the entry barrier into the world of embedded Linux. The barrier was twofold—price and complexity. The Raspberry Pi’s low price solved the price problem (cheap is good!) and the SoC reduced circuit complexity rather dramatically, making a much smaller package possible.

> 随着计算领域的重大进步，Raspberry Pi 的主要创新是降低了进入嵌入式 Linux 世界的门槛。障碍是双重的——**价格和复杂性**。Raspberry Pi 的低价解决了价格问题(便宜就是好！)，SoC 显着降低了电路复杂性，使更小的封装成为可能。

The road to the development of the Raspberry Pi originated at a surprising point—through a registered charity in the UK, which continues to operate today.

> Raspberry Pi 的发展之路起源于一个令人惊讶的时刻，这是英国的注册慈善机构，该慈善机构今天继续运作。

The Raspberry Pi Foundation, registered with the Charity Commission for England and Wales, first opened its doors in 2009 in Caldecote, Cambridgeshire. It was founded for the express purpose of promoting the study of computer science in schools. A major impetus for its creation came from a team consisting of Eben Upton, Rob Mullins, Jack Lang and Alan Mycroft. At the University of Cambridge’s Computer Laboratory, they had noted the declining numbers and low-level skills of student applicants. They came to the conclusion that a small, affordable computer was needed to teach basic skills in schools and to instill enthusiasm for computing and programming.

> Raspberry Pi 基金会在英格兰和威尔士慈善委员会注册的 Raspberry Pi 基金会于 2009 年在剑桥郡的 Caldecote 开业。它是为了促进学校计算机科学研究的明确目的而建立的。其创作的主要动力来自一支由 Eben Upton，Rob Mullins，Jack Lang 和 Alan Mycroft 组成的团队。在剑桥大学的计算机实验室中，他们注意到学生申请人的数字和低级技能的下降。他们得出的结论是，需要一台小型，负担得起的计算机来教授学校的基本技能，并灌输对计算和编程的热情。

Major support for the Foundation’s goals came from the University of Cambridge Computer Laboratory and Broadcom, which is the company that manufactures the SoC—the Broadcom 2835 or 2836, depending on the model—that enables the Raspberry Pi’s power and success. Later in this chapter you will read more on that component, which is the heart and soul of the Raspberry Pi.

> 对基金会目标的主要支持来自剑桥大学计算机实验室和 Broadcom，该公司是制造 SOC 的公司 - Broadcom 2835 或 2836，取决于模型，从而使 Raspberry Pi 的力量和成功。在本章的后面，您将阅读有关该组件的更多信息，这是 Raspberry Pi 的心脏和灵魂。

The founders of the Raspberry Pi had identified and acted on the perceived need for a tiny, affordable computer. By 2012, the Model B had been released at a price of about £25. The fact that this represented great value for money was recognised immediately, and first-day sales blasted over 100,000 units. In less than two years of production, more than two million boards were sold.

> Raspberry Pi 的创始人已经确定并采取了对一台微小，负担得起的计算机的需求。到 2012 年，B Model B 的价格约为 25 英镑。这代表物有所值的事实立即得到认可，第一天的销售额超过 100,000 辆。在不到两年的生产中，售出了超过 200 万张董事会。

The Raspberry Pi continued to enjoy good sales and wide acceptance following the highly successful release of the Model B+ (in late 2014). And in 2015, the fast, data-crunching Raspberry Pi 2 Model B with its four-core ARM processor and additional onboard memory sold more than 500,000 units in its first two weeks of release. Most recently, the Raspberry Pi Zero, a complete computer system on a board for £4—yes, £4—was released. It’s an awesome deal if you can get one—the first batch sold out almost immediately.

> 在 Model B+ 非常成功发布之后，Raspberry Pi 继续享受良好的销售和广泛的接受(2014 年底)。在 2015 年，在发行的前两周内，其四核 ARM 处理器和额外的船上存储器的快速，数据处理 Raspberry Pi 2 Model B 售出了 500,000 多个单元。最近，Raspberry Pi Zero 是一个板上的完整计算机系统，价格为 4 英镑，是的，4 英镑。如果您能得到一笔，这是一笔很棒的交易 - 第一批几乎立即售罄。

In 2016, the Raspberry Pi Model 3 Model B arrived. It sports a 1.2GHz 64-bit quad-core ARMv8 CPU, 1 GB RAM, and built-in wireless and Bluetooth! All for the same low price.

> 2016 年，Raspberry Pi 3 型 B 模型 B 到达。它具有 1.2GHz 64 位四核 ARMV8 CPU，1 GB RAM 以及内置的无线和蓝牙！所有这些都以相同的低价。

The original founders of the Raspberry Pi Foundation included:

> Raspberry Pi 基金会的原始创始人包括：

- Eben Upton - Rob Mullins - Jack Lang - Alan Mycroft - Pete Lomas - David Braben

The organisation now consists of two parts:

- Raspberry Pi (Trading) Ltd. performs engineering and sales, with Eben Upton as CEO. - The Raspberry Pi Foundation is the charitable and educational part.

> -Raspberry Pi(Trading)Ltd.与 Eben Upton 担任首席执行官，执行工程和销售。- Raspberry PI 基金会是慈善和教育部分。

The Raspberry Pi Foundation’s website at [`www.raspberrypi.org`](https://www.raspberrypi.org) (see Figure 1-1) presents the impetus that resulted in the Raspberry Pi. This is what they say on the About Us page:

> Raspberry Pi Foundation 的网站 [www.raspberrypi.org`](https://www.raspberrypi.org)(见图 1-1)提出了导致 Raspberry PI 的动力。这就是他们在《关于我们》页面上所说的：

_The idea behind a tiny and affordable computer for kids came in 2006, when Eben Upton, Rob Mullins, Jack Lang and Alan Mycroft, based at the University of Cambridge’s Computer Laboratory, became concerned about the year-on-year decline in the numbers and skills levels of the A Level students applying to read Computer Science. From a situation in the 1990s class=`pagebreak` title=`10`>where most of the kids applying were coming to interview as experienced hobbyist programmers, the landscape in the 2000s was very different; a typical applicant might only have done a little web design._

> _2006 年，剑桥大学计算机实验室的 Eben Upton、Rob Mullins、Jack Lang 和 Alan Mycroft 开始关注儿童使用的小型且负担得起的计算机的想法 申请阅读计算机科学的 A Level 学生的技能水平。与 1990 年代 class=`pagebreak` title=`10`> 的情况相比，大多数申请的孩子都是作为经验丰富的业余程序员来面试的，而 2000 年代的情况则大不相同；一个典型的申请人可能只做了一点网页设计。_

![[FIGURE 1-1:](#04_9781119183938-ch01.xhtml#rc01-fig-0001) The Raspberry Pi official website](./media/images/9781119183938-fg0101.png)

As a result, the founders’ stated goal was `to advance the education of adults and children, particularly in the field of computers, computer science and related subjects` .

> 结果，创始人的陈述目标是 `推进成人和儿童的教育，尤其是在计算机，计算机科学和相关主题领域` 。

Their answer to the problem, of course, was the Raspberry Pi, which was designed to emulate in concept the hands-on appeal of computers from the previous decade (the 1990s). The intention behind the Raspberry Pi was to be a `catalyst` to inspire students by providing affordable, programmable computers everywhere.

> 当然，他们对问题的回答是 Raspberry Pi，该 Raspberry PI 旨在模仿前十年(1990 年代)的计算机动手吸引力。Raspberry PI 背后的意图是成为 `催化剂` ，以通过在各地提供负担得起的可编程计算机来激发学生。

The Raspberry Pi is well on its way to achieving the Foundation’s goal in bettering computer education for students. However, another significant thing has happened; a lot of us older people have found the Raspberry Pi exciting. It’s been adopted by generations of hobbyists, experimenters and many others, which has driven sales into new millions of units.

> Raspberry Pi 正在实现基金会为学生提供计算机教育的目标。但是，发生了另一件重要的事情。我们许多老年人发现 Raspberry Pi 令人兴奋。它已被几代业余爱好者，实验者和许多其他人所采用，这将销售推向了新的数百万单位。

While the sheer compactness of the Raspberry Pi excites, resonates and inspires adults as well as youngsters, what truly prompted its success was its low price and scope of development. Embedded Linux has always been a painful subject to learn, but the Pi makes it simple and inexpensive. Continuing education in computers gets just as big a boost as initial education in schools.

> 尽管 Raspberry Pi 的纯粹紧凑性激发了共鸣并激发了成年人和年轻人的启发，但真正促使其成功的是其低价和发展范围。嵌入的 Linux 一直是一个痛苦的学习学科，但是 PI 使其简单便宜。在计算机上继续教育的助长程度与学校的初始教育一样大。

## System-on-a-Chip

An SoC or system-on-a-chip is an integrated circuit (IC) that has the major components of a computer or any other electronic system on a single chip. The components include a central processing unit (CPU), a graphics processing unit (GPU) and various digital, analogue and mixed signal circuits on just one chip.

> SOC 或 AN-A-CHIP 系统是一个集成电路(IC)，它具有计算机或任何其他电子系统的主要组件。这些组件包括一个中央处理单元(CPU)，图形处理单元(GPU)以及仅在一个芯片上的各种数字，模拟和混合信号电路。

This SoC component makes highly dense computing possible, such as all the power that is shoehorned into the Raspberry Pi. Figure 1-2 shows the Crodcom chip on the Raspberry Pi 2 Model B. It’s a game-changing advance in computer architecture, enabling single-card computers that rival and often exceed the capabilities of machines that are many times their size. [Chapter 8](#11_9781119183938-ch08.xhtml), `Operating Systems` , covers these small but mighty chips in detail.

> 该 SOC 组件使高度密集的计算成为可能，例如将其鞋霍恩(Raspberry pi)带入 Raspberry PI 的所有功率。图 1-2 显示了 Raspberry Pi 2 模型 B 上的 Crodcom 芯片。这是计算机体系结构的改变游戏的进步，使能够竞争并经常超过机器能力的单卡计算机可以超过其尺寸的许多倍。[第 8 章](%EF%BC%8311_9781119183938-CH08.XHTML)，`操作系统` ，详细介绍了这些小而强大的芯片。

> ![[FIGURE 1-2:](#04_9781119183938-ch01.xhtml#rc01-fig-0002) Broadcom chip on the Raspberry Pi 2 Model B](./media/images/9781119183938-fg0102.png)

The Raspberry Pi features chips that are developed and manufactured by Broadcom Limited. Specifically, the older models as well as the latest (the £4 Raspberry Pi Zero) come with the Broadcom BCN2835 and the Raspberry Pi 2 has the Broadcom BCM2836, and the new Model 3 uses the Broadcom BCM2837. The biggest difference between these two SoC ICs is the replacement of the single-core CPU in the BCM2835 with a four-core processor in the BCM2836. Otherwise, they have essentially the same architecture.

> Raspberry Pi 具有由 Broadcom Limited 开发和制造的芯片。具体而言，较旧的型号以及最新型号(4 英镑的 Raspberry Pi Zero)随附 Broadcom BCN2835，Raspberry Pi 2 具有 Broadcom BCM2836，而新的 Model 3 使用 Broadcom BCM2837。这两个 SOC IC 之间的最大区别是在 BCM2836 中替换了 BCM2835 中单核 CPU。否则，它们基本上具有相同的架构。

Here’s a taste of the low-level components, peripherals and protocols provided by the Broadcom SoCs:

> 这是 Broadcom Soc 提供的低级组件，外围设备和协议的味道：

- **CPU:** Performs data processing under control of the operating system (a CPU with a single core on most of the Raspberry Pi models and a CPU with four cores on the Raspberry Pi 2 and Raspberry Pi 3).
- **GPU:** Provides the operating system desktop.
- **Memory:** Permanent memory used as registers for CPU and GPU operation, storage for bootstrap software, the small program which starts the process of loading the operating system and activating it.
- **Timers:** Allow software to be time-dependent for scheduling, synchronising and so on.
- **Interrupt controller:** Interrupts allow the operating system to control all the computer resources, know when the CPU is ready for new instructions and much more (this is covered in [Chapter 8](#11_9781119183938-ch08.xhtml)).
- **General purpose input output (GPIO):** Provides layout and enables control of connections, input, output and alternative modes for the GPIO pins that enable the Raspberry Pi to manage circuits, devices, machines and so on. In short, it turns the Raspberry Pi into an embeddable control system.
- **USB:** Controls the USB services and provides the Universal Serial Bus protocols for input and output, thus allowing peripherals of all types to connect to the Raspberry Pi’s USB receptacles.
- **PCM/I<sup>2</sup>S:** Provides pulse code modulation (PCM, which converts digital sound to analogue sound such as speakers and headphones require) and known as Inter-IC Sound, Integrated Interchip Sound, or IIS, a high-level standard for connecting audio devices).
- **Direct memory access (DMA) controller:** Direct memory access control that allows an input/output device to bypass the CPU and send or receive data directory to the main memory for purposes of speed and efficiency.
- **I<sup>2</sup>C master:** Inter-integrated circuit often employed for connecting lower-speed peripheral chips to control processors and microcontrollers.
- **I<sup>2</sup>C/SPI (Serial Peripheral Interface) slave:** The reverse of the preceding bullet point. Allows outside chips and sensors to control or cause the Raspberry Pi to respond in certain ways; for example, a sensor in a motor detects it’s running hot and the controller chip causes the Raspberry Pi to make a decision on whether to reduce the motor’s speed or stop it.
- **SPI Interface:** Serial interfaces, accessed via the GPIO pins and allowing the daisy chaining of several compatible devices by the use of different chip-select pins.
- **Pulse width modulation (PWM):** A method of generating an analogue waveform from a digital signal.
- **Universal asynchronous receiver/transmitter (UART0, UART1):** Used for serial communication between different devices.

> - ** CPU：**在控制操作系统的控制下执行数据处理(在大多数 Raspberry Pi 模型上具有单个核心的 CPU，以及在 Raspberry Pi 2 和 Raspberry Pi 3 上具有四个内核的 CPU。
> - ** GPU：**提供操作系统桌面。
> - **内存：**永久存储器用作 CPU 和 GPU 操作的寄存器，Bootstrap 软件的存储，这是一个启动加载操作系统和激活其的过程的小程序。
> - **计时器：**允许软件依赖于计划，进行调度，同步等。
> - **中断控制器：**中断允许操作系统控制所有计算机资源，知道 CPU 何时准备好进行新指令等等(这在[第 8 章](#11_978111919183938-CH08.XHTML 中)))))。
> - **通用输入输出(GPIO)：**提供布局，并为 GPIO 引脚提供连接，输入，输出和替代模式，以使 Raspberry Pi 能够管理电路，设备，机器等。简而言之，它将 Raspberry PI 变成可嵌入的控制系统。
> - ** USB：**控制 USB 服务，并为输入和输出提供通用的串行总线协议，从而允许所有类型的外围设备连接到 Raspberry Pi 的 USB 插座。
> - ** PCM/I <SUP> 2 </sup> s：**提供脉冲代码调制(PCM，将数字声音转换为诸如扬声器和耳机的模拟声音)，并称为 Inter-Ic Inter-iC Sound，Integrated Interated Interchip Sound，或 IIS，是连接音频设备的高级标准)。
> - **直接内存访问(DMA)控制器：**直接内存访问控制，允许输入/输出设备绕过 CPU 并将数据目录发送或接收到主要内存，以实现速度和效率。
> - ** i <sup> 2 </sup> C 主：**整合电路通常用于连接下速外围芯片以控制处理器和微控制器。
> - ** i <sup> 2 </sup> c/spi(串行外围界面)从：**前一个子弹点的反面。允许外部芯片和传感器控制或导致 Raspberry Pi 以某些方式做出响应；例如，电动机中的传感器检测到它正在运行，并且控制器芯片使 Raspberry Pi 决定是降低电动机的速度还是停止电动机。
> - ** SPI 接口：**串行接口，通过 GPIO 引脚访问，并通过使用不同的芯片选择引脚允许雏菊链接几个兼容设备。
> - **脉冲宽度调制(PWM)：**一种从数字信号生成模拟波形的方法。
> - **通用异步接收器/发射器(UART0，UART1)：**用于不同设备之间的串行通信。

## An Exciting Credit Card-Sized Computer

Just how powerful is the Raspberry Pi compared to a desktop PC? Certainly, it has far more computational ability, memory and storage than the first personal computers. That said, the Raspberry Pi cannot match the speed, high-end displays, built-in power supplies and hard-drive capacity of the desktop boxes and laptops of today.

> Raspberry PI 与台式 PC 相比有多强大？当然，它比第一台个人计算机具有更多的计算能力，内存和存储。也就是说，Raspberry Pi 无法与当今的台式机箱和笔记本电脑的速度，高端显示器，内置电源以及硬盘驱动能力相匹配。

However, you can easily overcome any disadvantages by hanging the appropriate peripherals on your Raspberry Pi. You can add large hard drives, 42-inch HDMI screens, high-level sound systems and much more. Simply plug your peripherals into the USB receptacles on the board or via other interfaces that are provided, and you’re good to go. Finish it off by clicking an Ethernet cable into the jack on the Raspberry Pi or sliding in a wireless USB dongle, and worldwide connectivity goes live.

> 但是，您可以通过将适当的外围设备悬挂在 Raspberry PI 上来轻松克服任何缺点。您可以添加大型硬盘驱动器，42 英寸的 HDMI 屏幕，高级声音系统等等。只需将外围设备插入板上的 USB 插座或通过提供的其他接口，就可以了。通过将以太网电缆单击到 Raspberry Pi 上的千斤顶或在无线 USB 加密狗中滑动，然后全球连通性将上线。

You can duplicate most features of conventional computers when you attach peripherals to a Raspberry Pi, such as in Figure 1-3, and you also gain some distinct advantages over large computers, including:

> 当您将外围设备附加到 Raspberry PI 时，例如在图 1-3 中，您可以复制传统计算机的大多数功能，并且您还获得了与大型计算机相比的一些不同优势，包括：

- The Raspberry Pi is _really_ cheap—£25 retail or just £4 for the Raspberry Pi Zero. - It’s _really_ small—all models are credit-card sized or smaller. - You can replace the operating system in seconds simply by inserting a new SD or microSD card for almost instant reconfiguration. - The Broadcom SoC gives the Raspberry Pi more interfaces, communications protocols and other features out of the box than conventional computers that sell for many times the price. - The GPIO pins (see Figure 1-4) allow the Raspberry Pi to control real-world devices that have no other method of computer input/output.

> -Raspberry pi 是 *really* 便宜的 - 零售价为 25 英镑，Raspberry pi 零只有 4 英镑。- 它是 *really* 小 - 所有型号都是信用卡尺寸或较小的。- 您可以简单地插入新的 SD 或 microSD 卡以几乎即时重新配置来替换操作系统。- Broadcom SoC 为 Raspberry Pi 提供了更多的接口，通信协议和其他功能，而不是传统的计算机，这些计算机的价格是多倍的价格。- GPIO 引脚(请参见图 1-4)允许 Raspberry Pi 控制没有其他计算机输入/输出方法的现实世界设备。

> ![[FIGURE 1-3:](#04_9781119183938-ch01.xhtml#rc01-fig-0003) Peripherals attached to a Raspberry Pi 2 Model B](./media/images/9781119183938-fg0103.png)

![[FIGURE 1-4:](#04_9781119183938-ch01.xhtml#rc01-fig-0004) GPIO pins enable control of real world devices.](./media/images/9781119183938-fg0104.png)

## What Does the Raspberry Pi Do?

The Raspberry Pi excels as the brains for all sorts of projects. Here are some examples randomly picked from the many thousands of documented projects on the Internet. This list may inspire you in choosing some projects of your own:

> Raspberry Pi 擅长各种项目的大脑。以下是从互联网上成千上万的已记录项目中随机挑选的一些示例。此列表可能会激发您选择自己的一些项目：

- Home automation - Home security - Media centre - Weather station - Wearable computer - Robot controller - Quadcopter (drone) controller - Web server - Email server - GPS tracker - Web camera controller - Coffee maker - Ham radio EchoLink server and JT65 terminal - Electric motor controller - Time-lapse photography manager - Game controller - Bitcoin mining - Automotive onboard computer

> - 家庭自动化 - 家庭安全 - 媒体中心 - 气象站 - 可穿戴计算机 - 机器人控制器 - Quadcopter(无人机)控制器 - Web 服务器 - 电子邮件服务器 - GPS Tracker -Web Camera Controller-咖啡机 - HAM Radio Echolink Server 和 JT65 终端 - 电动机 - 电气电动机控制器 - 延时摄影经理 - 游戏控制器 - 比特币采矿 - 汽车载计算机计算机

This list just scratches the surface of possible uses for the Raspberry Pi. There’s not enough room to list everything you could do, but this book gives you the information you need to come up with your own ideas. Let your own desires, interests and imagination guide you. The Raspberry Pi does the rest.

> 此列表只是刮擦了 Raspberry Pi 可能用途的表面。没有足够的空间列出您可以做的一切，但是这本书为您提供了提出自己想法所需的信息。让您自己的欲望，兴趣和想象力指导您。Raspberry Pi 剩下的。

## Meeting and Greeting the Raspberry Pi Board

This section begins with an introduction to the features, components and layout of the Raspberry Pi board. We show contrasts between the various models but with an emphasis on the Raspberry Pi 2. Reading this section and examining the Raspberry Pi board is like looking at a map before setting off on a journey—it gives you the lay of the land. If you know where the various important parts of the board are and how they work, it makes imagining and creating projects a lot easier because you understand the board better.

> 本节始于 Raspberry Pi 板的功能，组件和布局的介绍。我们显示了各种模型之间的对比，但是重点是 Raspberry Pi 2.阅读本节并检查 Raspberry Pi 板就像在旅途中前往地图一样看地图，它为您提供了土地的范围。如果您知道董事会的各个重要部分以及它们的工作方式，它会使想象力和创建项目变得更加容易，因为您可以更好地了解董事会。

We begin with the Raspberry Pi 2 Model B (there was no Model A in the 2 series or the new 3 series). After introducing you to the Raspberry Pi 2, we’ll look at the other versions, including the Raspberry Pi 3 Model, which includes more processor speed, onboard Wi-Fi and Bluetooth.

> 我们从 Raspberry Pi 2 模型 B 开始(2 系或新 3 系中没有模型 A)。向您介绍 Raspberry Pi 2 后，我们将查看其他版本，包括 Raspberry Pi 3 型号，其中包括更多的处理器速度，Wi-Fi 和蓝牙。

If you want to follow along with your own board, orient it as shown in Figure 1-5, with the two rows of GPIO pins at the upper left.

> 如果您想与自己的木板一起遵循，如图 1-5 所示，将其定向，左上方的两个 GPIO 引脚。

### GPIO Pins

The GPIO pins—the row of pins at the top of the board as it’s oriented in [Figure 1-5](#04_9781119183938-ch01.xhtml#c01-fig-0005)—perform magic in tying the Raspberry Pi to the real world. Through these pins, you program the Raspberry Pi to control all sorts of devices. [Chapter 12](#15_9781119183938-ch12.xhtml), `Input/Output` , looks at programming the Raspberry Pi and helps you understand inputs and outputs and shows methods of controlling various devices. Let’s examine these pins and get an understanding of how simple and powerful they are.

> GPIO 引脚 - [图 1-5](%EF%BC%8304_9781119183938-CH01.XHTML%EF%BC%83c01-fig-0005) 中的板顶部的一行销钉 - 在将 Raspberry Pi 绑在现实世界中，。通过这些引脚，您可以对 Raspberry Pi 进行编程以控制各种设备。[第 12 章](%EF%BC%8315_9781119183938-CH12.XHTML)，`输入/输出` ，着眼于编程 Raspberry Pi，并帮助您了解输入和输出，并显示控制各种设备的方法。让我们检查一下这些引脚，并了解它们的简单和强大程度。

> ![[FIGURE 1-5:](#04_9781119183938-ch01.xhtml#rc01-fig-0005) The Raspberry Pi 2 board with the GPIO pins at the upper left](./media/images/9781119183938-fg0105.png)

Real-world devices—doorbells, light bulbs, model aircraft controls, lawn mowers, robots, thermostats, electric coffeepots and motors of all sorts, to name a few things—cannot normally connect to a computer or follow its orders. Through GPIO, the Raspberry Pi can do neat stuff with these real-world objects! That’s why we’re emphasising the GPIO pins; the pins enable you to do things with the Raspberry Pi that you can’t do with conventional computers.

> 现实世界中的设备 - 户外，灯泡，模型飞机控件，割草机，机器人，恒温器，电动咖啡机和各种电动机，仅举几例，通常连接到计算机或遵循其订单。通过 GPIO，Raspberry Pi 可以使用这些现实世界对象进行整洁的事情！这就是为什么我们强调 GPIO 引脚的原因；这些引脚使您能够使用 Raspberry Pi 做事，而您无法使用传统计算机进行操作。

---

> [!NOTE]

Being able to interface with real-world devices is not a distinction that’s unique to the Raspberry Pi; embedded computers are able to bridge this gap whereas conventional computers can’t.

> 能够与现实世界设备交互并不是 Raspberry Pi 独有的区别。嵌入式计算机能够弥合此差距，而传统计算机则不能。

We have 40 pins—two rows of 20. The bottom row of pins (left to right) consists of odd numbers: 1, 3, 5, 7, 9, 11, 13, 15, 17, 19, 21, 23, 25, 27, 29, 31, 33, 35, 37 and 39. The top are numbered 2, 4, 6, 8, 10, 12, 14, 16, 18, 20, 22, 24, 26, 28, 30, 32, 34, 36, 38 and 40.

> 我们有 40 个销钉 - 两行 20。销钉的底数(从左到右)由奇数组成：1、3、5、7、9、11、13、13、15、17、19、19、21、23、25，27、29、31、33、35、37 和 39，34、36、38 和 40。

These pins are programmable; you can even change the layout of most of the pins! The power pins cannot be rerouted.

> 这些引脚是可编程的；您甚至可以更改大多数引脚的布局！电源别针无法重新路由。

When you add simple external circuits, it becomes possible for the Raspberry Pi to switch all sorts of things on or off. It can also sense input from devices and respond accordingly. Thanks to the Raspberry Pi’s ability to communicate in various ways—such as by wireless, by Bluetooth or on the Internet—inputs and outputs do not even have to be local. With some additional hardware, you can control devices, programs and so forth from anywhere in the world.

> 当您添加简单的外部电路时，Raspberry Pi 可能会打开或关闭各种物体。它还可以从设备中感知输入并做出相应的响应。得益于 Raspberry Pi 以各种方式进行沟通的能力，例如通过无线，蓝牙或互联网上的沟通，投入和输出甚至不必是本地的。有了一些其他硬件，您可以从世界任何地方控制设备，程序等。

---

> [!NOTE]

Read [Chapter 12](#15_9781119183938-ch12.xhtml) to learn about the several modes of operation for GPIO pins. The majority of the pins can be input, output or one of six special modes.

> 阅读[第 12 章](%EF%BC%8315_9781119183938-CH12.XHTML)，以了解 GPIO 引脚的几种操作模式。大多数引脚可以输入，输出或六个特殊模式之一。

### Status LEDs

The status light-emitting diodes (LEDs) are to the lower left of the GPIO pins. These tiny babies put out a good deal of light. On the Raspberry Pi 2, they are labelled (from top to bottom) PWR (power) and ACT (activity); PWR lights red and ACT lights green.

> 状态发光二极管(LED)位于 GPIO 引脚的左下方。这些小婴儿露出了很多光。在 Raspberry PI 2 上，它们被标记(从上到下)PWR(Power)和 ACT(活动)；PWR 灯红色并表现为绿色。

Whenever power is present to the board (that is, a micro USB plug provides 5 volts direct current (VDC) from a USB source or a wall adapter), the PWR light glows red. The ACT LED indicates that a microSD card is available, and only lights up when the Raspberry Pi accesses the card.

> 每当有电源到板上时(即 Micro USB 插头从 USB 源或墙壁适配器提供 5 伏直流(VDC))，PWR 灯光发红。ACT LED 表示可用的 microSD 卡，只有在 Raspberry Pi 访问该卡时才亮起。

The Model B+ has the same arrangement as on the Model B except that the LED status lights are located on the opposite side of the board, and there are five LEDs:

> B+ 的安排与 B 上的布置相同，只是 LED 状态灯位于板的另一侧，并且有五个 LED：

- **ACT** (activity, green): Indicates an SD card is plugged in and accessible
- **PWR** (power, red): Indicates power is present
- **FDX** (full duplex, green): Indicates a full duplex local area network (LAN) is connected
- **LNK** (link, flashing green): Indicates activity is happening on the LAN
- **100** (yellow): Indicates a 100-Mbit/s LAN is connected (as opposed to a 10-Mbit network)

> - ** ACT **(活动，绿色)：指示 SD 卡已插入并可以访问
> - ** PWR **(POWER，RED)：指示电源存在
> - ** FDX **(Full Duplex，Green)：表示连接了完整的双工局部网络(LAN)
> - ** lnk **(链接，闪烁绿色)：指示活动正在局域网上发生
> - ** 100 **(黄色)：指示 100 mbit/s lan 已连接(与 10 毫米网络相反)

With the Model B+, the last three LEDs functions were moved to the Ethernet jack, with the FDX and 100 being combined into one LED. So flashing green on the jack shows network activity on the right LED and either solid green or yellow on the left, showing a 10-Mbits/s (megabits per second) or 100-Mbits/s network connections, respectively.

> 使用 B+ 模型，最后三个 LED 函数被移至以太网插孔，FDX 和 100 个组合成一个 LED。因此，千斤顶上的绿色在右侧显示网络活动，左侧显示固体绿色或黄色，分别显示 10 mbits/s(每秒兆位)或 100 mbits/s 网络连接。

---

> [!NOTE]

All the Raspberry Pi models actually have five status lights; it’s just that on the B+ and Raspberry Pi 2 there are two LEDs (PWR and ACT) on one side of the board, and the network indicators are on the other side as part of the Ethernet jack.

> 所有的 Raspberry Pi 型号实际上都有五个状态灯；只是在 B+ 和 Raspberry Pi 2 上，板的一侧有两个 LED(PWR 和 ACT)，而网络指标则是以太网杰克的一部分。

The status LEDs give you a quick picture of what transpires on your Raspberry Pi board, especially during the boot-up process. It goes like this:

> 状态 LED 可让您快速了解 Raspberry Pi 板上的内容，尤其是在启动过程中。就像这样：

1. When you plug in the microUSB connector (there’s no on/off switch), the PWR LED lights red to show that power is present. The PWR LED stays lit so long as power is flowing to the board. 2. The ACT LED flashes green a couple of times or so, indicating an SD card is present and readable. After boot-up, this green light flashes whenever SD card access occurs. 3. As the powering-up process continues, the green light on the right of the Ethernet jack (Model B+ and later) come on if a network is present. The light flashes whenever there is traffic on the network. The left LED flashes green for a slow network and is solid yellow if you are connected to a 100Mbit/s network.

> 1.当您插入 MicroUSB 连接器(没有开/关开关)时，PWR LED 灯红色以表明存在电源。只要电源流到板上，PWR LED 就会保持点亮。2. ACT LED 闪烁绿色几次左右，表明存在 SD 卡并且可读。启动后，每当出现 SD 卡访问时，此绿灯就会闪烁。3.随着电力上升的过程的继续，如果存在网络，以太网插孔右侧的绿灯(B+ model)会出现。每当网络上有流量时，光线就会闪烁。左 LED 闪烁绿色的速度为缓慢的网络，如果您连接到 100mbit/s 网络，则为纯黄色。

So, at a glance, the status LEDs tell us the board has power, the SD card is working and the network is active.

> 因此，乍一看，状态 LED 告诉我们董事会拥有电源，SD 卡正在工作，网络处于活动状态。

### USB Receptacles

On the right-hand side of the board are the Raspberry PI 2 Model B’s four USB 2.0 ports, as shown in Figure 1-6.

> 板的右侧是 Raspberry Pi 2 M 型的四个 USB 2.0 端口，如图 1-6 所示。

> ![[FIGURE 1-6:](#04_9781119183938-ch01.xhtml#rc01-fig-0006) USB 2.0 ports and Ethernet port](./media/images/9781119183938-fg0106.png)

---

> [!NOTE]

The ports appear in the same way on the Model B+ but the older Model B provides only two USB receptacles.

> 这些端口以相同的方式出现在模型 B+ 上，但较旧的 B 型仅提供了两个 USB 插座。

USB receptacles—or ports, as some people incorrectly call them—allow you to plug in and run a keyboard, mouse and all sorts of other devices—even big hard drives!

> USB 插座(或端口，正如某些人称之为错误的端口 - 允许您插入并运行键盘，鼠标和其他各种设备 - 甚至大型硬盘驱动器！

### Ethernet Connection

All sorts of Raspberry Pi tasks require a connection to both your local network and the Internet itself. Upgrading the operating system and the Raspberry Pi’s firmware requires Internet access. Networking is a necessity for downloading and installing programs, web surfing, using the Raspberry Pi as a media centre to deliver movies to your humungous flat-screen TV and many more reasons.

> 各种 Raspberry Pi 任务都需要与本地网络和 Internet 本身建立连接。升级操作系统和 Raspberry Pi 的固件需要互联网访问。网络是使用 Raspberry Pi 作为媒体中心下载和安装程序，网络冲浪的必要条件，将电影交付给您的巨大平板电视，以及更多原因。

Fortunately, you have two ways of achieving network connectivity with the Raspberry Pi. The first is a wired connection using the Ethernet socket on the lower-right corner (as the board is oriented in [Figure 1-5](#04_9781119183938-ch01.xhtml#c01-fig-0005)). Refer to [Figure 1-6](#04_9781119183938-ch01.xhtml#c01-fig-0006) to see what this socket looks like.

> 幸运的是，您有两种与 Raspberry Pi 实现网络连接的方法。第一个是使用较低角上的以太网套接字的有线连接(因为板在[图 1-5](%EF%BC%8304_9781119183938-CH01.XHTML%EF%BC%83C01-fig-0005) 中定向)。请参阅[图 1-6](%EF%BC%8304_9781119183938-CH01.XHTML%EF%BC%83C01-FIG-0006)，以查看此插座的外观。

The second way of connecting involves the USB receptacles. You can use a wireless USB dongle (a dongle being a plug-in device) or a USB-to-Ethernet adapter. If you use the latter method, you can connect the Raspberry Pi to more than one network. One reason for doing this would be a typical server setup where the Raspberry Pi connects to both the Internet and a more secure local network. Using Raspbian, for example, you can turn your Raspberry Pi into a classic LAMP (standing for Linux, Apache, mySQL, PHP) server. The Raspberry Pi serves up websites with database back ends and so on, just like on much larger servers using the same software.

> 连接的第二种方式涉及 USB 插座。您可以使用无线 USB 加密狗(是插件设备的加密狗)或 USB 到 Eternet 适配器。如果使用后一种方法，则可以将 Raspberry Pi 连接到多个网络。这样做的原因之一将是典型的服务器设置，其中 Raspberry Pi 连接到 Internet 和更安全的本地网络。例如，使用 Raspbian 可以将 Raspberry Pi 变成经典灯(代表 Linux，Apache，MySQL，PHP)服务器。Raspberry Pi 在数据库后端提供了网站，依此类推，就像在更大的服务器上使用同一软件一样。

Using a wireless USB dongle comes in handy if you want your Raspberry Pi to be portable. With an external battery power supply and wireless access, you can carry it anywhere! Or at least anywhere with wireless access, which is true of more and more places these days.

> 如果您希望您的 Raspberry Pi 可移植，使用无线 USB 加密狗会派上用场。借助外部电池电源和无线访问，您可以随身携带它！或至少在无线访问的任何地方，如今，这是越来越多的地方。

### Audio Out

On the bottom of the board is the 3.5 millimetre (mm) audio input/output jack (see Figure 1-7). Here you can plug in headphones, a computer sound card, speakers or anything thing else that takes and plays audio input.

> 板的底部是 3.5 毫米(mm)音频输入/输出插孔(见图 1-7)。在这里，您可以插入耳机，计算机音响卡，扬声器或其他播放音频输入的东西。

---

> [!NOTE]

The Model A and Model B did not have this feature but instead had separate connectors for video and audio.

> 模型 A 和模型 B 没有此功能，而是具有单独的视频和音频连接器。

The plug that goes into the socket on the Raspberry Pi board is a four-pole plug—in this case, a tip with three rings. However, it also accepts and works with a standard three-pole mini plug like those often found on headphones and computer speakers.

> 进入 Raspberry Pi 板上插座的插头是一个四极插头 - 在这种情况下，带有三个环的尖端。但是，它也接受并使用标准的三极迷你插头，就像耳机和计算机扬声器上经常发现的那样。

---

> [!NOTE]

Poles are the tip and rings of conductors. Four-pole had a tip and three rings; three-pole a tip and two rings.

> 两极是导体的尖端和环。四极有尖端和三个戒指；三极的尖端和两个环。

[Figure 1-7](#04_9781119183938-ch01.xhtml#c01-fig-0007) shows how the connector appears on the Model B+ and later, and Figure 1-8 shows the connector’s wiring.

> [图 1-7](%EF%BC%8304_9781119183938-CH01.XHTML%EF%BC%83C01-FIG-0007) 显示了连接器在模型 B+ 和以后如何出现的，并且图 1-8 显示了连接器的接线。

> ![[FIGURE 1-7:](#04_9781119183938-ch01.xhtml#rc01-fig-0007) The audio output socket](./media/images/9781119183938-fg0107.png)

![[FIGURE 1-8:](#04_9781119183938-ch01.xhtml#rc01-fig-0008) Connector for audio socket](./media/images/9781119183938-fg0108.png)

Another of the Raspberry Pi limitations concerns quality of sound. The audio out from this connector is 11-bit (for truly good sounding music you’d want 16-bit). The High-Definition Multimedia Interface (HDMI) connector, which is described later in this chapter, has better audio but, of course, you have to have an HDMI device (like a big-screen TV) that has good speakers attached.

> Raspberry PI 的另一个限制涉及声音质量。该连接器的音频是 11 位(对于您想要 16 位的真正效果音乐)。高清多媒体界面(HDMI)连接器(在本章后面进行描述)具有更好的音频，但是当然，您必须拥有一个具有良好扬声器的 HDMI 设备(如大屏幕电视)。

No worries, folks—like the limitations in Raspberry Pi power, solutions abound. For example, Adafruit sells a USB audio adapter, which works on the Raspberry Pi, for a very low price. It puts out better sound and allows for microphone input as well. This lets you use the Pi as a voice or music recorder or teach it to work via voice commands. Various computer soundboards designed specifically for the Raspberry Pi are also available

> 不用担心，伙计们 - 例如 Raspberry Pi 功率的局限性，解决方案比比皆是。例如，Adafruit 以非常低的价格出售了在 Raspberry Pi 上工作的 USB 音频适配器。它发出更好的声音，并允许麦克风输入。这使您可以将 PI 用作语音或音乐录音机，或者通过语音命令教它来工作。还提供专门为 Raspberry Pi 设计的各种计算机音板

Even better, you can obtain high-quality sound using the I<sup>2</sup>S interface into an external digital-to-analogue convertor (DAC). [Chapter 11](#14_9781119183938-ch11.xhtml), `Audio` , covers all that good stuff.

> 更好的是，您可以使用 i <sup> 2 </sup>的界面获得高质量的声音，以进入外部数字到 Analogue 转换器(DAC)。[第 11 章](%EF%BC%8314_9781119183938-CH11.xhtml)，`音频` ，涵盖了所有好东西。

### Composite Video

Using the same 3.5mm socket described in the last section, old-style composite video is also available.

> 使用上一节中描述的相同的 3.5mm 插座，还提供了旧式复合视频。

When it boots up and finds a composite video device attached, the Raspberry Pi attempts to select the right resolution. Mostly it gives a usable display but sometimes it gets things wrong.

> 当它启动并找到一个复合视频设备时，Raspberry Pi 试图选择正确的分辨率。通常，它给出可用的显示，但有时会遇到错误。

Having video composite output may seem old school in light of the modern era’s profusion of HDMI devices hanging off every wall, but it fits in with the design philosophy Raspberry Pi Foundation co-founder Eben Upton recently described. He said, `It’s a very cheap Linux PC device in the spirit of the 1980s, a device which turns your TV into a computer; plug in to TV, plug a mouse and a keyboard in, give it some power and some kind of storage, an operating system and you’ve got a PC` .

> 鉴于现代对 HDMI 设备的大量悬挂在每堵墙上的大量，它似乎似乎是老式的，但它符合设计理念 Raspberry Pi Foundation 联合创始人 Eben Upton 最近描述的。他说： `这是 1980 年代精神上非常便宜的 Linux PC 设备，该设备将您的电视变成计算机；插入电视，插入鼠标和键盘，给它一些电源和某种存储，操作系统，您有 PC` 。

### CSI Camera Module Connector

Camera modules for the Raspberry Pi give you 5-megapixel stills and 1080 high-definition video for about £16. The Camera Serial Interface (CSI) connector shown in Figure 1-9 (located between the HDMI socket and the 3.5mm audio socket) provides a place to plug the camera module into the Pi.

> Raspberry Pi 的摄像头模块可为您提供 5 百万像素的静止图像和 1080 个高清视频，价格约为 16 英镑。图 1-9 所示的相机串行接口(CSI)连接器(位于 HDMI 插座和 3.5mm 音频套件之间)提供了一个将摄像机模块插入 PI 中的地方。
> ![[FIGURE 1-9:](#04_9781119183938-ch01.xhtml#rc01-fig-0009) CSI and HDMI connectors](./media/images/9781119183938-fg0109.png)

CSI connects the camera module via a 15-conductor flat flex cable. Getting this cable connected and the camera module working is a bit tricky sometimes. You can find a how-to video on the Raspberry Pi website at [`https://www.raspberrypi.org/help/camera-module-setup/`](https://www.raspberrypi.org/help/camera-module-setup/).

> CSI 通过 15 导电机扁平挠性电缆连接摄像头模块。有时将此电缆连接起来，相机模块工作有点棘手。您可以在 Raspberry Pi 网站上找到一个方法视频，网址为[ - 模块设置/)。

However, after the cable sits in the socket properly, the camera works great. You can program it to do all sorts of neat stuff, such as take time-lapse photos and motion-triggered shots or record video footage.

> 但是，在电缆正确放在插座中后，摄像机效果很好。您可以对其进行编程以完成各种整洁的事情，例如拍摄延时照片和运动触发的照片或记录视频录像。

### HDMI

There’s nothing as fine as a nice big display showing the colourful graphical user interface (GUI) of the Raspberry Pi. A display enables you to surf the web, watch videos, play games—all the stuff you expect a computer to do. The best solution for that involves HDMI.

> 没有什么比很好的大型显示器完美无缺，显示了 Raspberry Pi 的彩色图形用户界面(GUI)。显示屏使您能够在网络上浏览，观看视频，玩游戏 - 所有您期望计算机可以做的事情。最佳解决方案涉及 HDMI。

High-Definition Multimedia Interface (HDMI) allows the transfer of video and audio from an HDMI-compliant display controller (in our case, the Raspberry Pi) to compatible computer monitors, projectors, digital TVs or digital audio devices.

> 高清多媒体接口(HDMI)允许从符合 HDMI 的显示器控制器(在我们的情况下为 Raspberry Pi)从兼容计算机监视器，投影仪，数字电视或数字音频设备传输视频和音频。

HDMI’s higher quality provides a marked advantage over composite video (such as what comes out of the audio socket on the Raspberry Pi board). It’s much easier on the eyes and provides higher resolution instead of composite video’s noisy and sometimes distorted video.

> HDMI 的较高质量比复合视频(例如 Raspberry Pi 板上的音频插座出现的内容)提供了明显的优势。它的眼睛更容易，提供更高的分辨率，而不是复合视频的嘈杂，有时甚至是扭曲的视频。

The HDMI connector on the Raspberry Pi Model B is approximately centred on the lower edge of the Raspberry Pi board (as we have it positioned in [Figure 1-5](#04_9781119183938-ch01.xhtml#c01-fig-0005)). See [Figure 1-9](#04_9781119183938-ch01.xhtml#c01-fig-0009) for what it looks like.

> Raspberry Pi B 上的 HDMI 连接器大约集中在 Raspberry Pi 板的下边缘(因为我们将其放在[图 1-5](%EF%BC%8304_9781119183938-CH01.XHTML) 中。请参阅[图 1-9](%EF%BC%8304_9781119183938-CH01.XHTML%EF%BC%83C01-FIG-0009)。

### Micro USB Power

The micro USB power connector is on the bottom left edge of the Raspberry Pi, as shown in Figure 1-10.

> Micro USB 电源连接器位于 Raspberry Pi 的左下边缘，如图 1-10 所示。

> ![[FIGURE 1-10:](#04_9781119183938-ch01.xhtml#rc01-fig-0010) Micro USB connector used for obtaining power](./media/images/9781119183938-fg0110.png)

The micro USB adapter brings power into the Raspberry Pi board. You might know that most smartphones use this connector type, which means you can find usable cables and wall adapters all over the place. (This is one example of how the Raspberry Pi Foundation takes users’ need for inexpensive operation into consideration.)

> Micro USB 适配器将电源带入 Raspberry Pi 板。您可能知道大多数智能手机都使用此连接器类型，这意味着您可以在各处找到可用的电缆和墙壁适配器。(这是 Raspberry Pi Foundation 如何考虑廉价操作的一个例子。)

---

> [!NOTE]

You can also get a mobile version of a micro USB charging cable with an automotive power adaptor so you can power your Raspberry Pi in a car, using the built-in car power socket.

> 您还可以使用汽车电源适配器获得 Micro USB 充电电缆的移动版本，因此您可以使用内置的汽车电源插座在汽车中为 Raspberry Pi 供电。

The micro USB cable supplies 5VDC to the Raspberry Pi at about 1 ampere (1A) of current for the model B. Some recommendations for the B+ mention 1.5A, but if you’re pushing heavy current through the USB ports (remember, four instead of two on the B+ and later), a 2A supply is smarter. For the Raspberry Pi 2, get at least a 2.4A supply.

> Micro USB 电缆在大约 1 安培(1a)电流的电流(1A)的 Raspberry Pi 提供 5 VDC 的电流中提供 B+ 提及 1.5A 的某些建议，但是如果您通过 USB 端口将大电流推到了较重的电流(请记住，四个相对于四个在 B+ 及以后的两个)中，2A 供应更聪明。对于 Raspberry Pi 2，至少获得 2.4A 供应。

Remember, there’s no switch for turning the Raspberry Pi on and off (another saving to keep the price down). You just plug and unplug the micro USB connector. Of course, with a bit of tinkering and soldering, you could add a switch to the power cable easily enough.

> 请记住，没有开关打开和关闭 Raspberry Pi 的切换(另一种节省了价格可以降低价格)。您只需插入并拔下 Micro USB 连接器即可。当然，有了一点修补和焊接，您可以轻松地为电源线添加开关。

### Storage Card

Applying power to the Raspberry Pi causes a bit of computer code stored on the board, the bootloader, to check for the presence of the SD or (in newer Raspberry Pi versions) microSD card in its slot (see Figure 1-11) and look for code on the card telling it how to start and what to load into its RAM. If no card is there or that card has no information on it (because it’s blank or corrupted) the Raspberry Pi does not start. Read more on the boot process in [Chapter 8](#11_9781119183938-ch08.xhtml).

> 将电源应用于 Raspberry PI 会导致板上存储的一些计算机代码，以检查其插槽中的 SD 是否存在 SD 或(在较新的 Raspberry Pi 版本中)microSD 卡(请参见图 1-11)并查看对于卡上的代码，告诉它如何启动以及将什么加载到 RAM 中。如果没有卡或该卡没有有关它的信息(因为它是空白或损坏的)Raspberry Pi 不会启动。在[第 8 章](%EF%BC%8311_9781119183938-CH08.XHTML)中阅读有关引导过程的更多信息。

> ![[FIGURE 1-11:](#04_9781119183938-ch01.xhtml#rc01-fig-0011) The micro SD slot on the bottom side of the Raspberry Pi 2](./media/images/9781119183938-fg0111.png)

---

> [!WARING]

_Do not_ insert or remove an SD card while the Raspberry Pi has power attached. Doing so has a very good chance of corrupting the SD card, causing you to lose the data and programs on it.

> 在 Raspberry PI 具有功率时，请勿插入或卸下 SD 卡。这样做很有可能破坏 SD 卡，从而导致您丢失其上的数据和程序。

The usual minimum size recommended for earlier editions of the Raspberry Pi was 8 gigabytes (8GB), although the original recommendation was 4GB. However, a number of people on the Internet report using 32GB cards, and at least one person even boasted of using a 128GB card. It seems, though, that any card larger than 32GB, under Raspbian at least, requires partitioning (using a software to specially format the SD).

> Raspberry PI 的早期版本建议的通常最小尺寸为 8 千兆字节(8GB)，尽管原始建议是 4GB。但是，互联网上的许多人使用 32GB 卡，至少有一个人甚至吹嘘使用 128GB 卡。但是，似乎至少在 raspbian 下，任何大于 32GB 的卡都需要分区(使用软件以特殊格式化 SD)。

Of course, you can hang just about any size of USB drive from one of the USB receptacles, if you use an external power supply. A terabyte would be a good start. The SD card is still needed to boot.

> 当然，如果您使用外部电源，则几乎可以从一个 USB 插座上悬挂任何大小的 USB 驱动器。Terabyte 将是一个好的开始。仍然需要 SD 卡启动。

### DSI Display Connection

Just right of the SD card slot but on top of the board is the Display Serial Interface (DSI) display connector. The DSI connector’s design accommodates a flat 15-conductor cable that drives liquid crystal display (LCD) screens. Figure 1-12 shows the connector.

> SD 卡插槽的右侧，但在板上的顶部是显示串行接口(DSI)显示连接器。DSI 连接器的设计可容纳一条扁平的 15 导电线，该电缆驱动液晶显示屏(LCD)屏幕。图 1-12 显示了连接器。

> ![[FIGURE 1-12:](#04_9781119183938-ch01.xhtml#rc01-fig-0012) DSI display connection](./media/images/9781119183938-fg0112.png)

### Mounting Holes

It might seem minor, but the Model B+ and later models have four mounting holes—those reinforced holes in the board. The Model B only has two. Mounting holes come in handy when you want to secure the Raspberry Pi inside a box or case with other devices.

> 它似乎很小，但是 B+ 和后来的型号有四个安装孔 - 板上的那些增强孔。B 模型只有两个。当您想将 Raspberry Pi 固定在盒子或其他设备外壳中时，安装孔就会派上用场。

When you add four standoff insulators, you can use these insulted holes for fastening the board with screws to the standoffs to have a nice, safe installation.

> 当您添加四个僵局绝缘子时，您可以使用这些侮辱性孔用螺钉将板固定在僵局中，以进行良好，安全的安装。

### The Chips

There are two large chips situated roughly on the centre of the left of the board (when the board is oriented with the GPIO pins at the top left; see Figure 1-13). The larger one shown is the Broadcom BCM2835 or BCM2836 on the Raspberry Pi 2 or BCM2037 on the Raspberry Pi 3. The other chip provides the Ethernet protocols for networking. You’ll find more information about the what these systems-on-a-chip do in [Chapter 12](#15_9781119183938-ch12.xhtml).

> 板左侧的中央大致有两个大芯片(当板上用 GPIO 引脚定向时，左上方的 GPIO 引脚；请参见图 1-13)。显示的较大的是 Raspberry Pi 2 或 Raspberry Pi 3 上的 BroadCom BCM2835 或 BCM2836。您会在[第 12 章](%EF%BC%8315_9781119183938-CH12.XHTML)中找到有关这些系统中这些系统所做的更多信息。

> ![[FIGURE 1-13:](#04_9781119183938-ch01.xhtml#rc01-fig-0013) The SoC and USB/Ethernet chips](./media/images/9781119183938-fg0113.png)

## The Future

From its inception, the guiding principle of the Raspberry Pi was to enable and revolutionise the teaching of computer science by providing affordable, accessible hardware. It is certainly achieving this goal successfully through the widespread adoption of the Raspberry Pi as a teaching tool in schools worldwide.

> 从成立开始，Raspberry Pi 的指导原则就是通过提供负担得起的可访问的硬件来促进和彻底改变计算机科学的教学。当然，通过将 Raspberry Pi 作为全球学校的教学工具广泛采用，成功实现了这一目标。

The inspiration and excitement young people find, the lessons they learn and the experiments and projects they complete are significant. We are seeing the birth of a new generation of computer experts.

> 年轻人发现的灵感和兴奋，他们学到的教训以及他们完成的实验和项目都很重要。我们看到了新一代计算机专家的诞生。

Something else has also happened. Those of us from prior generations—sometimes called `adults` and sometimes not—discovered the Raspberry Pi. Millions of us enthusiastically explore its incredible power and build various projects using its control functions. We, too, are learning things from this tiny computer, which takes the term `microcomputer` to a much smaller scale than those now-huge old desktops. Consequently, we are setting an example for our children. If adults can have so much fun with the Raspberry Pi, younger people realise they can as well, and so they do.

> 其他事情也发生了。我们这些人来自前几代人(有时被称为 `成年人` ，有时不称为 `成年人` )，发现了 Raspberry Pi。数以百万计的我们热情地探索了其令人难以置信的力量，并使用其控制功能建立了各种项目。我们也在从这台小型计算机中学习东西，该计算机将 `微型计算机` 一词的规模远小得多。因此，我们为孩子们树立榜样。如果成年人可以与 Raspberry Pi 一起玩得很开心，那么年轻人也意识到自己也可以，所以他们也可以。

So the Raspberry Pi not only inspires the younger, student generation; it makes older generations better and more computer literate. That’s quite a gift.

> 因此，Raspberry Pi 不仅激发了年轻的学生一代。它使年龄较大，更具计算机知识。那是一件礼物。

What happens next? The next great movement, already in progress, is the Internet of Things. Using the Raspberry Pi, your refrigerator, your car—just about every device you can think of—can become wireless and be controlled by small, easily embedded computerised controls. More and more people will continue to adopt and adapt the means of making this automation a reality. With every new release, demand grows for the Raspberry Pi and the things it can do.

> 接下来发生什么？下一个伟大的运动已经在进行中，是物联网。使用 Raspberry Pi，您的冰箱，您的汽车(关于您可以想到的每个设备)可以成为无线的，并由小型，易于嵌入的计算机控件控制。越来越多的人将继续采用并适应使这种自动化成为现实的方法。随着每一个新版本，Raspberry Pi 及其可以做的事情都会增长。

In the next few years, computer architecture will continue to shrink while it grows more capable. We yearn for a thumb drive–sized device that has a 24-core CPU running at 15GHz with 10GB of fast memory and a terabyte solid state drive, all on an SoC.

> 在接下来的几年中，计算机架构将继续缩小，而功能越来越强。我们渴望使用 Thumb 驱动器尺寸的设备，该设备的 CPU 在 15GHz 的运行速度为 15GHz，具有 10GB 的快速内存和 Terabyte 固态驱动器，所有这些都在 SOC 上。

We anticipate that such a device will sport a purple Raspberry logo. It won’t be long now. The future rushes toward us.

> 我们预计这样的设备将配备紫色 Raspberry 徽标。现在不久了。未来冲向我们。
