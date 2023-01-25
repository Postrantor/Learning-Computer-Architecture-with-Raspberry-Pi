Chapter 12

# Input/Output

**WHEN WE DISTIL** computerised data processing down to its very essence, we require only two things of our computers—_input_ and _output_, or _I/O_. You put data and commands in, and you receive processed data out. It’s a simple enough concept, but more than 70 years of electronic computers and the allied development of a veritable galaxy of peripheral devices make it more complicated.

> **当我们蒸馏**计算机数据处理至其本质上时，我们仅需要计算机的两件事- _input_ 和 _Output_ 或 _i/o_。您将数据和命令放入其中，然后收到已处理的数据。这是一个足够简单的概念，但是超过 70 年的电子计算机以及名副其实的外围设备银河系的盟军开发使其更加复杂。

This chapter attempts to demystify this complexity via an overview of I/O and the computer architecture behind it. Of course, there’s special emphasis on the Raspberry Pi, with an eye to some practical uses.

> 本章试图通过 I/O 及其背后的计算机体系结构的概述来揭开这种复杂性。当然，特别强调了 Raspberry Pi，并着眼于某些实际用途。

We begin with a short history of interfaces and their related protocols. Next, we examine various I/O schemes involving UARTs, USB, SCSI, IDE/PATA, SATA, IIS, IIC, SPI, GPIO and others. Yes, that is a double handful of acronyms, but most of them provide rather elegant solutions to specific I/O needs that we define and explain in this chapter.

> 我们从界面及其相关协议的简短历史开始。接下来，我们检查涉及 UARTS，USB，SCSI，IDE/PATA，SATA，IIS，IIC，SPI，GPIO 等的各种 I/O 方案。是的，这是少数缩写词，但是其中大多数为我们在本章中定义和解释的特定 I/O 需求提供了相当优雅的解决方案。

The chapter concludes with a Raspberry Pi-specific section on using general purpose input output (GPIO). The two rows of GPIO pins on all the Raspberry Pi models differentiate them from most computers. Using these programmable inputs and outputs allow this credit-card-sized board (even smaller in the case of the Raspberry Pi Zero) to control everything from a tiny blinking LED light to massive electric motors drawing thousands of watts of power.

> 本章以有关使用通用输入输出(GPIO)的 Raspberry Pi 特定部分结束。所有 Raspberry Pi 模型上的两行 GPIO 引脚都将它们与大多数计算机区分开。使用这些可编程的输入和输出，可以通过信用卡大小的板(在 Raspberry Pi Zero 的情况下更小)来控制所有内容，从微小的闪烁 LED 灯到巨大的电动机，绘制数千瓦电源。

So, let us meet those cybernetic brothers: input and output.

## Introducing Input/Output

Computing devices have been around for a lot longer than many people realise. The abacus—that simple adding and subtracting instrument that uses beads strung on wires—most likely originated in Babylon in the mists of history, several centuries BC. The famous Antikythera device discovered in an ancient shipwreck appears to be a mechanism for predicting the movement of stars and planets, dating from about the first century BC. Tools like these work differently from modern computers, but they both take input and produce output.

> 计算设备的存在比许多人意识到的要长得多。算盘

- 简单的添加和减法仪器，使用珠子串在电线上
- 最有可能起源于公元前几个世纪的历史雾中的巴比伦。在古老的沉船中发现的著名的反京都装置似乎是预测恒星和行星运动的机制，可追溯到公元前一世纪。像这样的工具的工作方式与现代计算机不同，但它们都采用输入并产生输出。

The advent of modern I/O took place much more recently, and began with a mouse.

> 现代 I/O 的出现最近发生了，从鼠标开始。

Early computing focused on things the computer was good at, essentially arithmetic calculations and data processing. However, for computers to become the universal helpmates they are today, better methods of input and output were needed. Punched cards and magnetic tape were slow. The advent of terminals where the operator typed text on a keyboard and the computer returned words on a screen was an improvement but it was still cumbersome, even after the keyboard became attached to the computer.

> 早期计算集中在计算机擅长的事物上，本质上是算术计算和数据处理。但是，要使计算机成为当今的通用帮助者，需要更好的输入和输出方法。打孔卡和磁带速度很慢。终端的出现，操作员在键盘上键入文本和屏幕上的计算机返回单词是一个改进，但即使键盘已连接到计算机之后，它仍然很麻烦。

Computers and people needed a better interface. In addition, computers needed to talk with other computers (network) and exchange various forms of data at great speeds _accurately_. Therefore, a proliferation of I/O hardware methods and communications protocols was developed. Those things are the basic subject matter of this chapter, but first we must consider the computer/human interface.

> 计算机和人员需要一个更好的界面。此外，计算机需要与其他计算机(网络)交谈，并以极高的速度交换各种形式的数据。因此，开发了 I/O 硬件方法和通信协议的扩散。这些事情是本章的基本主题，但首先我们必须考虑计算机/人类界面。

Two inventions changed the face (literally) of the computer: the graphical user interface (GUI) and the now ubiquitous mouse. Which came first? Somewhat surprisingly, it was the mouse, and it was a military secret!

> 两个发明改变了计算机的面部(字面意思)：图形用户界面(GUI)和现在无处不在的鼠标。哪个是第一个？令人惊讶的是，这是老鼠，这是一个军事秘密！

#### The Mouse

A _mouse_ is a computer peripheral that detects two-dimensional motion on a flat surface and converts it into the movement of a cursor (an arrow or other graphic on a computer’s screen). Clicking the mouse’s button or buttons results in various commands transmitted to the computer.

> *mouse* 是计算机外围设备，可检测平坦表面上的二维运动，并将其转换为光标的运动(箭头或计算机屏幕上的其他图形)。单击鼠标的按钮或按钮会导致各种传输到计算机的命令。

Early mice used a small rubberised ball to sense motion. Most mice today employ use LED light sources and an array of photo sensors. Many now are also wireless, eliminating the cord coming out of the back like a real mouse’s tail (the source of the device’s name).

> 早期的小鼠使用一个小的橡胶球来感知运动。今天，大多数老鼠都使用 LED 光源和一系列照片传感器。现在，许多人也是无线的，消除了像真实鼠标的尾巴一样(设备名称的来源)，从背面弹出。

Douglas Engelbart and his team at the Stanford Research Institute developed and named the original mouse in the 1960s (see Figure 12-1). Engelbart did much more than just make today’s many varieties of mice possible, but he’s a hero to all of us who make our daily bread by moving a mouse around on our desk.

> 道格拉斯·恩格巴特(Douglas Engelbart)和他在斯坦福大学研究所(Stanford Research Institute)的团队在 1960 年代开发并命名了原始鼠标(见图 12-1)。恩格巴特(Engelbart)所做的不仅仅是使当今的许多老鼠成为可能，但他是我们所有人的英雄，他们通过在办公桌上移动鼠标来制作我们的日常面包。

![[FIGURE 12-1:](#15_9781119183938-ch12.xhtml#rc12-fig-0001) Xerox Star 8010, commercial GUI](./media/images/9781119183938-fg1201.png)

If the mouse is such a great idea, why wasn’t it invented sooner? Well, like many great concepts, precursors to the mouse did exist. In 1941, Ralph Benjamin developed a trackball to control a fire-control radar plotting system for the Royal Navy. The fire-control system originally used a joystick device and analog computers in calculating the future position of aircraft for targeting. Benjamin decided a better input method was required and invented a trackball, which he called a `roller ball` . In the 1950s, the Royal Canadian Navy controlled digital computer systems with trackballs. Both of these uses fell under the cloak of military secrecy and didn’t spread to the larger computing world.

> 如果鼠标是一个好主意，为什么不早点发明？好吧，就像许多伟大的概念一样，鼠标的前体确实存在。1941 年，拉尔夫·本杰明(Ralph Benjamin)开发了一个轨迹球，以控制皇家海军的火力控制雷达绘图系统。火力控制系统最初使用操纵杆设备和模拟计算机来计算飞机的未来位置。本杰明决定需要一种更好的输入方法，并发明了一个轨迹球，他称之为 `滚子` 。在 1950 年代，加拿大皇家海军控制的数字计算机系统带有轨迹球。这两种用途都属于军事保密斗篷，并没有传播到更大的计算世界。

So, Doug Engelbart independently invented the mouse. Sadly, he never received a cent in royalties, but we all owe him our thanks for his immense contribution to computer I/O. With Engelbart’s invention, we now had a means of pointing, and computers needed something to make pointing useful. Enter the GUI.

> 因此，道格·恩格巴特(Doug Engelbart)独立发明了鼠标。可悲的是，他从未获得过特许权使用费，但我们所有人都感谢他对计算机 I/O 的巨大贡献。有了 Engelbart 的发明，我们现在有了一种指向的方法，计算机需要一些东西才能使指向有用。输入 GUI。

#### The Graphical User Interface

A graphical user interface (GUI, pronounced `gooey` ) lets us interact with computers and other devices by the use of text, icons and other visual indicators. The older text-only displays often required the typing of long, counter-intuitive commands as opposed to the faster and easier GUI solution of pointing and clicking.

> 图形用户界面(GUI，发音为 `Gooey`)使我们可以通过使用文本，图标和其他视觉指示器与计算机和其他设备进行交互。较旧的仅文本显示通常需要键入长，反直觉的命令，而不是指向和单击的更快，更容易的 GUI 解决方案。

Doug Engelbart made another contribution. This time, it was his turn to provide us with the precursor to something, in this case text-based hyperlinks/hypertext (_a la_ the Internet) that could be clicked on using a mouse (which, thanks to him, already existed) making the link do something, like take you to another screen or perform a command.

> 道格·恩格巴特(Doug Engelbart)做出了另一项贡献。这次，轮到他为我们提供了某种东西的先驱，在这种情况下，基于文本的超链接/超文本(_a la_ the Internet)可以单击使用鼠标(感谢他，已经存在)该链接做点什么，例如带您到另一个屏幕或执行命令。

From there, Palo Alto Research Center (PARC, owned by Xerox) and Alan Kay, one of the key researchers at PARC, moved computers past text-based hyperlinks and into the world of GUIs. In 1973, the Xerox Alto computer was released. It was the first computer to use a GUI as its main interface, and it accepted input from both the keyboard and a pointing device. This GUI, called the PARC user interface, had elements that are familiar to us today—windows, menus, buttons and check boxes.

> 从那里开始，帕洛阿尔托研究中心(PARC，由 Xerox 拥有)和 PARC 的主要研究人员之一艾伦·凯(Alan Kay)将计算机超越了基于文本的超链接并进入了 GUIS 世界。1973 年，Xerox Alto 计算机发布。它是第一台使用 GUI 作为其主接口的计算机，并且接受了键盘和指向设备的输入。这个称为 PARC 用户界面的 GUI 今天有我们熟悉的元素

- 窗口，菜单，按钮和复选框。

---

> [!NOTE]

The first GUI didn’t include icons. Icons came along later thanks to one of Alan Kay’s team, David Smith.

> 第一个 GUI 不包括图标。由于艾伦·凯(Alan Kay)的一支团队戴维·史密斯(David Smith)，偶像出现了。

It took several years for GUIs to become available on the market. The first commercial release of a computer with a GUI was the Xerox Star 8010 in 1981 (see [Figure 12-1](#15_9781119183938-ch12.xhtml#c12-fig-0001)). In 1983, Apple got into the game and produced the first Apple with a GUI, the Lisa. Lisa was not an outright success, but it did introduce a menu bar and windows controls, which are things we take for granted in today’s GUIs.

> Guis 花了几年的时间才能在市场上使用。带有 GUI 的计算机的第一个商业发行版是 1981 年的 Xerox Star 8010(见[图 12-1](%EF%BC%8315_978111919183938-CH12.XHTML%EF%BC%83C12-FIG-0001)。1983 年，苹果参加了比赛，并制作了第一个带有 GUI，Lisa 的苹果。丽莎并不是一个完全成功的成功，但它确实引入了菜单栏和 Windows 控件，这是我们在今天的 Guis 中理所当然的事情。

Then, in 1984, Apple released the Macintosh computer, which was _truly_ the game changer for GUIs. Given the success of the Mac, several other computer manufacturers and software companies were looking at GUI. Atari and Commodore joined their ranks in 1985, and Microsoft pushed out Windows 1.0 later that same year. No one’s looked back since.

> 然后，在 1984 年，苹果发布了 Macintosh 计算机，该计算机是 Guis 的游戏改变者。鉴于 Mac 的成功，其他几家计算机制造商和软件公司正在研究 GUI。Atari 和 Commodore 在 1985 年加入了他们的队伍，Microsoft 于同年晚些时候将 Windows 1.0 推出。从那以后没有人回头。

Today, most operating systems—Windows, Linux, Mac, Android, iOS, you name it—sport GUIs as their primary interface with humans. Advantages of GUIs include:

> 如今，大多数操作系统(Windows，Linux，Mac，Android，iOS，You Nive You)是他们与人类的主要接口。GUI 的优势包括：

- They’re easy to use, especially for newcomers to computing.
- What you see is what you get (WYSIWYG, pronounced `wizzywig` ), meaning that what you see on the screen is exactly how the printed product will look.
- They usually provide Help facilities.
- They can be used without long strings of commands. You just point to a menu and click to see a list of possible commands.

>

- 它们易于使用，尤其是对于新手进行计算。- 您看到的是您得到的(Wysiwyg，发音为 `Wizzywig` )，这意味着您在屏幕上看到的恰恰是印刷产品的外观。- 他们通常提供帮助设施。- 可以在没有长命令的情况下使用它们。您只需指向菜单，然后单击以查看可能的命令列表。

---

> [!NOTE]
> Server installations worldwide still use commands typed at the command line, and those commands are exceptionally useful and worth learning.
> 全球服务器安装仍使用命令行中键入的命令，这些命令非常有用且值得学习。

- They offer simple ways of moving data between applications, such as drag and drop or copy and paste.
- They allow photos and other graphics to be easily manipulated.

>

- 他们提供了在应用程序之间移动数据的简单方法，例如拖放或复制和粘贴。- 它们允许照片和其他图形轻松操纵。

Of course, like anything, GUIs also have disadvantages:

> 当然，像任何事物一样，Guis 也有缺点：

- They require more RAM (working memory).
- They take up more space on hard drives or other permanent storage, such as the Raspberry Pi’s microSD.
- They require more overheads for software developers to create them.

>

- 他们需要更多的 RAM(工作 Mem)。- 他们在硬盘驱动器或其他永久存储(例如 Raspberry Pi 的 MicroSD)上占用了更多空间。- 他们需要更多的开销供软件开发人员创建它们。

GUIs dominate computer operating systems and have made it easier for humans to interact with computers. Yet computers talk not only to us but also to all sorts of devices, both locally and over networks. So let’s look at some very important types of I/O and the computer architecture supporting them.

> GUIS 主导了计算机操作系统，并使人类更容易与计算机互动。然而，计算机不仅与我们交谈，而且在本地和网络上都与各种设备进行交谈。因此，让我们看一下一些非常重要的 I/O 类型以及支持它们的计算机架构。

## I/O Enablers

The concept of computer I/O devices, also called computer _peripherals_, consists of devices that accept data input, output processed data, or perform both in and out functions.

> 计算机 I/O 设备的概念，也称为计算机 *Peripherals*，由接受数据输入，输出处理的数据或执行内外功能的设备组成。

Here’s a simplification of how I/O devices work. They include _sensors_, which are often some sort of device that detects and responds to input from the physical environment. Sensors detect motion, temperature, changes in air or gas pressure and so on, and the sensors feed data or instructions to a computer for processing, storing or initiating a command. The computer may then (if required) present the results to a human or to a machine it controls. Basically, one or both of the following functions occur:

> 这是 I/O 设备如何工作的简化。它们包括 *sensors*，通常是某种设备，可以检测并响应物理环境的输入。传感器检测运动，温度，空气或气压的变化等等，传感器将数据或说明馈送到计算机以处理，存储或启动命令。然后，计算机可以(如果需要)将结果呈现给人类或它控制的机器。基本上，出现以下一个或两个功能：

- **Input:** The device converts analog or digital data and instructions, sending an electrical signal in binary format (1s and 0s, digital format) to the computer.
- **Output:** The computer sends digital signals back to the device, which converts those signals into whatever format the device understands.

>

- **输入：**设备将模拟或数字数据和说明转换，以二进制格式(1s 和 0s，数字格式)发送电信到计算机。- **输出：**计算机将数字信号发送回设备，该信号将这些信号转换为设备所理解的任何格式。

Table 12-1 lists some examples of I/O devices.

**Input** **Output** **Input/Output** ------------------------------------------------------------------------ --------------------------------------------------------------------------------------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------- A mouse inputs signals from its movement on a two-dimensional surface. Printers print pages sent from the computer. A network card makes possible continuous communication with other computers on the network as well as on the Internet. Keyboards report keys pressed. Displays show a GUI with windows, menus, buttons, the mouse’s moving cursor and so on. Disk drives store and retrieve data via a Serial AT Attachment (SATA) or other type of interface. Motion sensors report true or false that a motion has occurred. On the detection of motion in a secure area, the computer causes a siren to sound and/or alerts a designated human guard. USB peripherals send status and receive commands from the operating system assisted by the driver program for that device.

The next sections examine some specific ways I/O happens.

### Universal Serial Bus

Universal Serial Bus (USB) is a method of both input and output. Where the Raspberry Pi is concerned, it is not by accident that the newer models boast four USB plugs (see Figure 12-2) because USB has become indispensable. You’ll find four ports a bare minimum for many projects.

> 通用串行总线(USB)是输入和输出的一种方法。在 Raspberry PI 涉及的地方，较新的型号拥有四个 USB 插头并不是偶然的(见图 12-2)，因为 USB 变得必不可少。对于许多项目，您会发现四个端口的最低限度。

![[FIGURE 12-2:](#15_9781119183938-ch12.xhtml#rc12-fig-0002) The four USB receptacles on the Raspberry Pi 2](./media/images/9781119183938-fg1202.png)

USB allows easy and convenient connection of all sorts of devices, including keyboards, mice and other pointing devices, portable hard drives and thumb drives, network adapters, microphones, CD and DVD drives and much, much more. Even smartphones and game consoles include USB plugs these days.

> USB 允许各种设备的便捷连接，包括键盘，鼠标和其他指向设备，便携式硬盘驱动器和 Thumb 驱动器，网络适配器，麦克风，CD 和 DVD 驱动器等等。如今，即使是智能手机和游戏机也包括 USB 插头。

We begin with some history of USB and its evolution through the various versions (1.0, 1.1, 2.0, 3.0 and 3.1) and then we then offer some detail on the versatility of USB for the Raspberry Pi.

> 我们从 USB 的一些历史及其通过各种版本(1.0、1.1、2.0、3.0 和 3.1)的演变开始，然后我们提供有关 Raspberry Pi 的 USB 多功能性的一些细节。

#### History of USB

Beginning in the early 1980s, the explosive popularisation of personal computing meant a vast proliferation of peripherals was developed for this lucrative market. This often created a rat’s nest of cables and power supplies behind computers and spilling off the desk and onto the floor.

> 从 1980 年代初开始，个人计算的爆炸性普及意味着这个有利可图的市场开发了大量的外围物质。这通常会在计算机后面产生大鼠的电缆和电源巢，并从桌子上溢出并溅到地板上。

USB came about to standardise and eliminate much of this clutter. USB replaced and/or consolidated many earlier types of interface. Parallel ports, serial ports and many separate power supplies landed in the dustbin of computer history, thanks to USB plugs, power and other standards.

> USB 开始标准化和消除大部分混乱。USB 替换和/或合并了许多早期类型的接口。借助 USB 插头，电源和其他标准，平行端口，串行端口和许多计算机历史记录垃圾箱中的电源。

USB, as an industry standard, was first released in the mid-1990s. The standard specifies the necessary cables, connectors, communications protocols and the power supply between computers and peripheral devices. All of the preceding specifications enable USB to be implemented by many manufacturers and work interchangeably.

> 作为行业标准，USB 于 1990 年代中期首次发行。该标准指定必要的电缆，连接器，通信协议以及计算机和外围设备之间的电源。所有上述规格都使 USB 能够由许多制造商实施，并可以互换工作。

Originally, a consortium of seven companies—Compaq, DEC, IBM, Intel, Microsoft, NEC and Nortel—pushed the development of USB. Today, the developers and maintainers of the USB standard (the current version is version 3.1) form the USB Implementers Forum, which is a non-profit organisation.

> 最初是由七家公司组成的联盟，即 Compaq，DEC，IBM，Intel，Microsoft，NEC 和 Nortel，都推出了 USB 的开发。如今，USB 标准的开发人员和维护者(当前版本是版本 3.1)形成了 USB 实施者论坛，该论坛是一个非营利组织。

#### Versions of USB

There have been three releases of USB standards:

- **USB 1.x:** USB 1.0 was the first release in 1996. It provided specified data rates of 1.5 Mbit/s (megabits per second, low bandwidth, low speed) and 12 Mbit/s at full bandwidth (also referred to as `full speed` ). USB 1.1 followed in 1998 and corrected problems that had become apparent in 1.0, especially in hubs.

>

- ** USB 1.x：** USB 1.0 是 1996 年的第一个发行版。它提供了 1.5 mbit/s 的指定数据速率(每秒兆位，低带宽，低速)和 12 mbit/s，在全带宽处(也称为 `全速` )。USB 1.1 在 1998 年紧随其后，并纠正了 1.0 中显而易见的问题，尤其是在集线器中。

In addition to fixing problems, USB 1.1 became widely accepted and implemented by computer manufacturers, leading to `legacy-free` PCs. A _legacy-free PC_ is one in which the floppy drive controller, parallel printer port, RS-232 serial port, game ports and Industry Standard Architecture (ISA) expansion bus were all replaced by USB ports. This enabled the building of simpler PCs and contributed to driving prices down, a major impact of USB.

> 除了解决问题外，USB 1.1 还被计算机制造商广泛接受和实施，导致 `无遗产` PC。*无质量 PC* 是软盘驱动器控制器，平行打印机端口，RS-232 串行端口，游戏端口和行业标准架构(ISA)扩展总线都被 USB 端口所取代。这使得构建了更简单的 PC，并促进了 USB 的重大影响。

- **USB 2.0:** This version arrived in 2001. It features a higher data transfer rate of 480 Mbit/s, which is 40 times faster than version 1.1.

>

- ** USB 2.0：**此版本于 2001 年到达。它具有 480 mbit/s 的较高数据传输速率，比版本 1.1 快 40 倍。
- **USB 3.0:** In 2008 the USB standard got another huge speed increase, this time up to 5 Gbit/s (gigabits per second—that’s fast). This version of the standard also had lower power consumption and increased power output, and it was backward compatible with USB 2.0. The first computers and other devices with actual 3.0 ports, called SuperSpeed ports, came out in 2010. If you see a USB port on your computer with a small SS over it and a blue plastic guide inside, it’s a USB 3.0 port. Of course, if it is labelled `USB 3.0` , that’s a pretty good indicator as well. December 2014 saw the approval of USB 3.1 standards with increased speed, this time a blistering 10 Gbit/s.

>

- ** USB 3.0：**在 2008 年，USB 标准又增加了巨大的速度，这次最高为 5 Gbit/s(每秒千兆位
- 快速)。该版本的标准还具有较低的功耗和增加的功率输出，并且与 USB 2.0 兼容。首批具有实际 3.0 端口的计算机和其他设备，称为 SuperSpeed 端口，在 2010 年发布。如果您在计算机上看到一个 USB 端口，上面有一个小 SS，则内部有一个蓝色的塑料指南，则是 USB 3.0 端口。当然，如果标记为 ` USB 3.0` ，那也是一个很好的指标。2014 年 12 月，速度提高了 USB 3.1 标准的批准，这次是 10 Gbit/s 的起泡。

#### USB Architecture

USB design includes a host controller that allows for numerous USB ports with multiple devices attached in a tiered star topology. Star networks (see Figure 12-3) are one of the most common arrangements, in which a central computer or hub controls communication with the devices around it. It is a client-server set up. This configuration’s advantages emphasise reliability; if one client or connection drops out, the other connections are not affected.

> USB 设计包括一个主机控制器，允许许多 USB 端口，其中具有分层星拓扑中的多个设备。星际网络(见图 12-3)是最常见的安排之一，其中中央计算机或枢纽控制与周围设备的通信。它是一个客户服务器设置。这种配置的优势强调可靠性；如果一个客户端或连接退出，则另一个连接不会受到影响。

![[FIGURE 12-3:](#15_9781119183938-ch12.xhtml#rc12-fig-0003) Star configuration](./media/images/9781119183938-fg1203.png)

Adding to the flexibility of the network topology is the fact that any physical USB device may have subdevices, which makes it possible for one device to have several functions. For example, a webcam with a built-in microphone has a video device function and an audio function. We call these _composite_ devices (that is, they’re composed of more than one function).

> 除网络拓扑的灵活性外，任何物理 USB 设备都可能具有子设备，这使一个设备具有多个功能。例如，具有内置麦克风的网络摄像头具有视频设备功能和音频功能。我们称这些 _composite_ 设备(也就是说，它们由多个函数组成)。

The USB standard also includes _device classes,_ which are software drivers for class codes and give the USB host the ability to connect easily to the various classes of devices supported. This gives the host the ability to recognise devices from different manufacturers so long as those devices provide the standard device codes.

> USB 标准还包括 _device classes_ ，是类代码的软件驱动程序，并使 USB 主机能够轻松连接到所支持的各种设备。只要这些设备提供标准设备代码，这使主机能够识别不同制造商的设备。

Device classes include:

- **Audio:** Speaker, microphone, sound card, MIDI
- **Communications:** Modem, network adapter, Wi-Fi, RS232 serial adapter
- **Human interface:** Mouse, keyboard, joystick, trackball
- **Image:** Webcam, scanner
- **Printer:** Laser printer, inkjet, and CNC (Computer Numerical Control) using in automating machinery.
- **Mass storage:** USB flash drive, memory card reader, digital audio player digital camera, external hard drive
- **USB hub:** Controls connected USB devices that are connected to the hub
- **Video:** Webcam, surveillance cameras, consumer and professional video cameras and so on

>

- **音频：**扬声器，麦克风，声卡，MIDI
- **通信：**调制解调器，网络适配器，Wi -Fi，RS232 串行适配器
- **人界面：**鼠标，键盘，操纵杆，轨迹球
- **图像：**网络摄像头，扫描仪
- **打印机：**使用自动化机械中的激光打印机，喷墨和 CNC(计算机数值控制)。- **质量存储：** USB 闪存驱动器，存储卡读取器，数字音频播放器数码相机，外部硬盘驱动器
- **USB 集线器：**控制连接的连接到集线器的 USB 设备
- **视频：**网络摄像头，监视摄像头，消费者和专业摄像机等等

In addition, there are other classes such as those for personal healthcare devices, compliance testing devices, smartcard readers, fingerprint readers and test measurements.

> 此外，还有其他类别的类别，例如个人医疗保健设备，合规性测试设备，智能卡读取器，指纹读取器和测试测量。

On the Raspberry Pi boards are two large surface mount chips. The largest is the Broadcom SoC 2835 on the first models and 2836 with four-core central processing unit (CPU) on the Raspberry Pi 2 and the new Raspberry Pi 3. The second, somewhat smaller chip is a SMSC LAN9512 USB hub and Ethernet controller. This latter chip handles the USB and networking services.

> Raspberry PI 板上是两个大型表面安装芯片。最大的是第一批型号的 Broadcom Soc 2835，在 Raspberry Pi 2 和新的 Raspberry Pi 3 上带有四核中央加工单元(CPU)2836，第二个较小的芯片是 SMSC LAN9512 USB Hub 和以太网控制器。后一个芯片处理 USB 和网络服务。

### USB Powered Hubs

USB ports allow you to plug in and running a keyboard, a mouse and all sorts of other devices, including big hard drives. However, as we touched on in the introduction to this chapter, onboard USB also has current limits. In the case of the Model B, it should only be used for low-power devices.

> USB 端口使您可以插入并运行键盘，鼠标和其他各种设备，包括大型硬盘驱动器。但是，正如我们在本章介绍中谈到的那样，机载 USB 也有当前的限制。对于模型 B，仅应用于低功率设备。

---

> [!WARING]
> When you exceed the power limits of the on-board USB, bad things happen, such as possible damage to components. Consider adding a powered USB hub for high current requirements.
> 当您超过车载 USB 的功率限制时，会发生坏事，例如对组件的可能损坏。考虑为高电流需求添加动力 USB 集线器。

If you’ve used the Model B, the lack of enough USB ports (the official name is `receptacle` ) is probably aggravating. After you plug in a keyboard and a mouse, you are stuck—there’s no more room at the inn. In addition, if you use the wrong mouse or keyboard—that is, those with high current drain—it could cause the board’s power supply to shut down.

> 如果您使用过 Model B，缺乏足够的 USB 端口（官方名称是 `receptacle` ）可能会加剧这种情况。 插入键盘和鼠标后，您被卡住了——旅馆里没有更多空间了。 此外，如果您使用了错误的鼠标或键盘——即那些电流消耗大的鼠标或键盘——可能会导致开发板的电源关闭。

#### USB Power

The USB 1.x and 2.0 specifications approved by the USB Implementers Forum allow for 5 volts direct current (VDC) from USB hubs on one wire for powering USB-connected devices. The variance in voltage is limited to a range of 4.75 VDC to 5.25 VDC. In USB 3.0, the variance increases to 4.25 VDC to 5.25 VDC.

> USB 实施程序论坛批准的 USB 1.x 和 2.0 规格允许从 USB 集线器上使用一条电线上的 USB 集线器进行 5 伏直流(VDC)，用于为 USB 连接的设备供电。电压的差异限制为 4.75 VDC 至 5.25 VDC 的范围。在 USB 3.0 中，差异增加到 4.25 VDC 至 5.25 VDC。

As we have mentioned, the Raspberry Pi Model B current is limited compared to later models. The newer `+` models have proper USB power handling. A hub before 2.0 allocates a maximum of five unit loads (500 milliamperes \[mA]) to a connected device or 750mA under USB 3.0. Slightly complicating these current limits, two types of devices exist: low power and high power. A low power device can draw at most only one unit load. A high power device usually operates as a low power one but can request more current and get it if available at the time from the hub.

> 正如我们已经提到的，与后来的型号相比，Raspberry PI B 电流受到限制。较新的 `+` 型号具有适当的 USB 功率处理。2.0 之前的枢纽最多分配给连接的设备或 USB 3.0 下的连接设备或 750mA 的五个单位载荷(500 毫亚[ma ])。有两种类型的设备存在略微复杂化的这些限制：低功率和高功率。低功率设备最多只能绘制一个单位负载。高功率设备通常作为低功率运行，但可以要求更多的电流并在当时从集线器上获得。

---

> [!NOTE]

The current sourcing abilities of almost all USB ports differ from what the specs mention. The specs state, for instance, that without negotiation, a USB 2.0 device is allocated only 100mA (with negotiation up to 500mA). Negotiation for additional power comes through the Power Delivery protocols interfaced through a bidirectional data channel to control the power supply.

> 当前几乎所有 USB 端口的采购能力与规格提及的不同。例如，规格指出，如果不进行协商，USB 2.0 设备仅分配 100mA(谈判高达 500mA)。通过双向数据渠道连接的电力传递协议来控制额外功率，以控制电源。

The reality is most boards/power supplies ignore this spec and source whatever 5V VDC is available in the system. Devices such as high-speed external hard drives may require _more_ power than is available via the Raspberry Pi’s USB receptacles. In such cases, the device may have a Y-cable with two USB plugs. Connecting to two USB receptacles, in the USB specs at least, raises the maximum current load to 1 amp for USB 2.0 and earlier versions or 1.5 amp for USB 3.0.

> 现实是大多数董事会/电源供应忽略此规范，并源于系统中可用的 5V VDC。高速外部硬盘驱动器之类的设备可能需要_多功能功率，而不是通过 Raspberry Pi 的 USB 插座提供的设备。在这种情况下，该设备可能具有带有两个 USB 插头的 Y-Cable。至少在 USB 规格中连接到两个 USB 插座，将最大电流负载提高到 USB 2.0 和更早版本的 1 AMP 或 USB 3.0 的 1.5 amp。

Of course, the hub must be able to supply this amount of current. Using the USB controller on a Raspberry Pi, you _do not_ have unlimited load. The solution involves adding an external hub with its own power supply and greater current-supplying capacity than the Raspberry Pi by itself.

> 当然，集线器必须能够提供这一数量的电流。在 Raspberry Pi 上使用 USB 控制器，您* to not*有无限的负载。该解决方案涉及与 Raspberry Pi 本身添加具有自身电源和更大的电流供应能力的外部枢纽。

#### Rapsberry Pi USB Power Solution

The Model B+ and the Raspberry Pi 2 come with four USB ports! Now, don’t do a happy dance across the room just yet. Although having four USB ports instead of two does add flexibility and offers more current, there are still limitations. A good powered USB hub, like the one shown in Figure 12-4, is a way to work around those limitations.

> B+ 和 Raspberry Pi 2 配备了四个 USB 端口！现在，不要在整个房间里做一个快乐的舞蹈。尽管拥有四个 USB 端口而不是两个端口确实增加了灵活性并提供了更多的最新性，但仍然存在局限性。像图 12-4 中所示的那样，一个良好的功率 USB 集线器是解决这些限制的一种方法。

![[FIGURE 12-4:](#15_9781119183938-ch12.xhtml#rc12-fig-0004) A USB powered hub](./media/images/9781119183938-fg1204.png)

Such hubs usually have seven or more ports and receive power through a wall plug. Thus, you get power to run hard drives and other juice-hungry devices without overtaxing your Raspberry Pi board’s limited resources.

> 这样的枢纽通常具有七个或更多端口，并通过墙壁插头接收电源。因此，您将获得运行硬盘驱动器和其他饮用果汁设备的力量，而不会超过 Raspberry Pi 板的有限资源。

---

> [!NOTE]

Be sure to choose a powered USB hub that supports the Raspberry Pi. Do an Internet search for `powered USB hub` for lists of manufacturers and model numbers.

> 确保选择支持 Raspberry Pi 的动力 USB 集线器。在互联网上搜索 `动力USB集线器` 以获取制造商和型号的列表。

### Ethernet

_Ethernet_ in general consists of several computer-networking technologies. First introduced in 1980 and standardised in 1983 as IEEE 802.3, its development has been continuous since that time. Speeds have increased from 2.94 Mbit/s to 100 Gbit/s (gigabytes per second). By 2017, a speed of 400 Gbit/s is planned.

> _Ethernet_ 通常由几种计算机网络技术组成。自 1980 年首次推出，并于 1983 年标准化为 IEEE 802.3，自那时以来一直是连续的。速度已从 2.94 mbit/s 增加到 100 Gbit/s(每秒千兆字节)。到 2017 年，计划 400 GBIT/S 的速度。

Networks enabled by Ethernet stream data in short pieces called `frames` . A frame includes source addresses (where it comes from) and destination addresses (where it’s going). Error-checking data causes the frame to be discarded if it arrives corrupted. In the case of a corrupted frame, a resend request can be triggered so that no data is lost.

> 通过以太网流数据启用的网络，以 `帧` 为单位。框架包括源地址(来自哪里)和目标地址(即将到达的地方)。错误检查数据会导致框架损坏，将其丢弃。在损坏的框架的情况下，可以触发重新启动请求，以免丢失数据。

#### Network Configurations

Similar to the way USB hubs control devices in a star configuration, networks (which were first to use the star topology) have clients connected to a hub. Hubs may be `bridged` (a connection made to another star configuration) to add more networks, both local and remote. The result is a vast collection of interconnected networks, which we call the Internet.

> 类似于 USB 集线器在 Star 配置中控制设备的方式，网络(首先使用 Star Toupology)将客户端连接到集线器。轮毂可能被 `桥接` (与另一种星形配置建立的连接)，以添加更多本地和远程网络。结果是大量相互联系的网络，我们称之为 Internet。

#### Raspberry Pi Networking

There are two ways to achieve network connectivity with the Raspberry Pi. The first is a wired connection that uses the Ethernet socket on the Raspberry Pi (excluding the Raspberry Pi Zero, which does not have an Ethernet socket). Figure 12-5 shows the socket, which accepts a standard network cable plug. The Ethernet port on the Raspberry Pi supports connections of 100 megabits per second (Mbit/s).

> 有两种方法可以实现与 Raspberry Pi 的网络连接。第一个是有线连接，该连接使用了 Raspberry Pi 上的以太网插座(不包括 Raspberry Pi Zero，它没有以太网插座)。图 12-5 显示了插座，该插座接受标准网络电缆插头。Raspberry Pi 上的以太网端口支持每秒 100 兆位的连接(MBIT/s)。

![[FIGURE 12-5:](#15_9781119183938-ch12.xhtml#rc12-fig-0005) Ethernet port on the Raspberry Pi 2 Model B](./media/images/9781119183938-fg1205.png)

The second way of connecting to the network involves the USB ports. You can use a wireless USB dongle (a dongle is a plug-in device) or a USB-to-Ethernet adapter. The USB wireless device allows easy connection to Wi-Fi networks in the area, and the USB-to-Ethernet effects a physical connection by providing a socket for a standard Ethernet cable.

> 连接到网络的第二种方法涉及 USB 端口。您可以使用无线 USB 加密狗(加密狗是插件设备)或 USB 到 Eternet 适配器。USB 无线设备可以轻松连接到该区域的 Wi-Fi 网络，并且通过为标准以太网电缆提供插座，**USB 到 Enternet 效应物理连接**。

A wireless dongle is handy if you want your Raspberry Pi to be portable. With an external battery power supply and wireless access, you can carry it anywhere! That is, you can carry it anywhere with wireless access, which is true for more and more places these days.

> 如果您希望您的 Raspberry Pi 便携式，则无线加密狗非常方便。借助外部电池电源和无线访问，您可以随身携带它！也就是说，您可以随身携带无线访问，这对于如今越来越多的地方都是如此。

All sorts of tasks require a connection to both your local network and the Internet. Upgrading the operating system and the Raspberry Pi’s firmware require Internet access, unless you decide to swap out the SD card as an alternative. Downloading and installing programs, web surfing, using the Raspberry Pi as a media centre to deliver movies to your flat-screen TV and many other tasks make networking a necessity.

> 各种任务都需要与本地网络和 Internet 进行连接。升级操作系统和 Raspberry Pi 的固件需要互联网访问，除非您决定将 SD 卡交换为替代方案。下载和安装程序，网络冲浪，使用 Raspberry Pi 作为媒体中心，将电影传递给您的平板电视，以及许多其他任务使网络成为必要。

### Universal Asynchronous Receiver/Transmitters

Universal asynchronous receiver/transmitters (UARTs) use a set of registers to accept and output data. Older UARTs could translate data between parallel and serial formats, but modern UARTs do not have this capacity. The personal computers of yesteryear used to have serial ports as a standard feature. The now ancient (in computer years) RS-232 serial format (which ran these ports) is implemented via a UART. Serial ports such as these can still be found on various industrial instruments.

> 通用异步接收器/发射器(UARTS)使用一组寄存器接受和输出数据。较旧的 UART 可以在平行和串行格式之间转换数据，但是现代 UART 没有这种能力。过去的个人计算机曾经以串行端口为标准功能。现在古老的(计算机年)RS-232 串行格式(运行这些端口)是通过 UART 实施的。诸如此类的串行端口仍然可以在各种工业仪器上找到。

The UART works by breaking down bytes of data into their individual bits and sending those serially (one after the other). At the destination, the receiving UART reassembles the bytes. The advantage of serial transmission over parallel transmission lies in its cost; just a single wire is required. The Broadcom SoC on the Raspberry Pi has two UARTs.

> UART 通过将数据字节分解为其单个位并串行发送(一个接一个)来工作。在目的地，接收 UART 重新组合字节。串行传输比平行传输的优点在于其成本；仅需要一根电线。Raspberry Pi 上的 Broadcom Soc 有两个 UART。

A common use for UARTs is in microcontrollers, and the Raspberry Pi excels as a control device. The Raspberry Pi’s onboard UART comes inside the Broadcom SoC containing the CPU (or CPUs), graphics processing units (GPUs) and all those other goodies. It’s accessed and is programmable using the GPIO’s pin 9 (transmit) and pin 10 (receive).

> UARTS 的常见用途是在微控制器中，Raspberry Pi 擅长作为对照设备。Raspberry Pi 的板载 UART 位于包含 CPU(或 CPU)，图形处理单元(GPU)和所有其他这些好处的 Broadcom SoC 内部。它可以使用 GPIO 的引脚 9(传输)和引脚 10(接收)访问并可以编程。

Read more on the GPIO in the last section of this chapter.

> 在本章的最后一部分中阅读有关 GPIO 的更多信息。

### Small Computer Systems Interface

Small Computer Systems Interface (SCSI) provides standards for moving data to and from computers and peripherals, especially hard drives (although it’s also good for scanners and other devices). SCSI has been around since the early 1980s and was once the gold standard of hard drive interfacing.

> 小型计算机系统接口(SCSI)提供了从计算机和外围设备(尤其是硬盘驱动器)移动数据的标准(尽管它也适合扫描仪和其他设备)。SCSI 自 1980 年代初以来就一直存在，曾经是硬盘接口的黄金标准。

SCSI transfers data in parallel. To use it with a Raspberry Pi, such as by adding a SCSI drive, is possible via USB but a serial-to-parallel adapter cable is required. Such adapter cables cost about £15 and are readily available from major online computer parts retailers.

> SCSI 并行传输数据。与 Raspberry Pi 一起使用，例如通过 USB 添加 SCSI 驱动器，但是需要使用串行到并行的适配器电缆。此类适配器电缆的价格约为 15 英镑，可从主要的在线计算机零件零售商处获得。

---

> [!NOTE]
> SCSI is very much on the way out, and it’s unlikely that you’ll find a use for it.
> SCSI 非常出路，您不太可能找到使用它。

### Parallel ATA

The Parallel Advanced Technology Attachment (PATA) standard is also known by several names:

> 平行的高级技术附件(PATA)标准也以几个名称知道：

- Integrated Drive Electronics (IDE)
- Extended Integrated Drive Electronics (EIDE)
- Ultra Advanced Technology Attachment (Ultra ATA)

>

- 集成驱动电子(IDE)
- 扩展集成驱动电子(EIDE)
- 超级高级技术附件(Ultra ATA)

No matter what you call it, PATA is an interface standard for connecting and passing data to and from hard disks, floppy disk drives and optical disc drives in computers. It has gone through many incremental developments and, like SCSI, it has been superseded by other standards. (See the next section on SATA.)

> 无论您称之为什么，PATA 都是用于连接和传递硬盘，软盘驱动器和计算机中光盘驱动器的数据的接口标准。它经历了许多增量发展，像 SCSI 一样，它已被其他标准所取代。(请参阅 SATA 上的下一部分。)

PATA cables have one significant limitation: they can be no longer than 18 inches. Because of this restriction, their primary use was as interfaces inside computer cases. Because PATA cables were the least-expensive solution for passing data to and from hard drives especially during the late 1980s to early 1990s, they were widely used.

> PATA 电缆有一个重要的限制：它们的不超过 18 英寸。由于这种限制，它们的主要用途是作为计算机案例中的接口。由于 PATA 电缆是传递与硬盘驱动器的数据和从 1980 年代末至 1990 年代初传递数据最低的解决方案，因此它们被广泛使用。

If you have old PATA drives that you’d like to hang off your Raspberry Pi board, you can use a conversion cable to make the connection. The cables aren’t expensive—less than £15 for a set of conversion cables that will handle IDE/PATA and/or SATA.

> 如果您想挂在 Raspberry PI 板上的旧 PATA 驱动器，则可以使用转换电缆来建立连接。电缆不昂贵，一组可以处理 IDE/PATA 和/或 SATA 的转换电缆的售价不到 15 英镑。

---

> [!NOTE]
> Remember that any time you add something to the Raspberry Pi that draws the type of current a hard drive does, you should use a powered USB hub as discussed earlier.
> 请记住，每当您在 Raspberry Pi 中添加一些绘制硬盘驱动器的当前类型的东西时，您都应使用前面讨论的动力 USB 集线器。

### Serial Advanced Technology Attachment

Serial Advanced Technology Attachment (SATA) devices communicate over a serial cable using two pairs of conductors. Its primary use connects computers and other devices to hard disk and optical drives. Two important advantages of SATA over SCSI and PATA are that it is speedier and uses less wiring, especially in the case of the older IDE interfaces.

> 串行高级技术附件(SATA)设备使用两对导体通过串行电缆进行通信。它的主要用途将计算机和其他设备连接到硬盘和光盘驱动器。SATA 比 SCSI 和 PATA 的两个重要优点是，它更快，使用较少的接线，尤其是在较旧的 IDE 接口的情况下。

In the late 1980s and 1990s, drives were installed in PCs with flat, grey, multi-conductor ribbon cables. The cables usually sported a red stripe on one side so people would know which way they plugged into the ribbon connector (to avoid possible damage to hardware). Because the data interchange was parallel, such cables required many conductors. SATA has replaced PATA in consumer and most business devices. However, some industrial and other uses of embedded flash memory still use the older PATA interfaces.

> 在 1980 年代后期和 1990 年代后期，驱动器安装在带有平坦的灰色，多杆丝带电缆的 PC 中。电缆通常在一侧具有红色条纹，因此人们会知道他们将其插入色带连接器的方式(以避免对硬件的损坏)。由于数据互换是平行的，因此此类电缆需要许多导体。SATA 在消费者和大多数业务设备中取代了 PATA。但是，嵌入式闪存的某些工业和其他用途仍然使用旧的 PATA 接口。

The current version of SATA, Revision 3.2, features communication speeds of 16 Gbit/s and actual data transfer of 1969 MB/s. As mentioned earlier, several inexpensive adapters exist for converting SATA drives to USB, which makes it possible to connect SATA devices to the Raspberry Pi via its USB receptacles. Here’s another reminder that you should use a powered hub to make sure the drive gets adequate power and to reduce the chance of causing damage to the Raspberry Pi due to current overload.

> 当前版本的 SATA 修订版 3.2 具有 16 Gbit/s 的通信速度和 1969 MB/s 的实际数据传输。如前所述，存在几个廉价的适配器，用于将 SATA 驱动器转换为 USB，这使得可以通过其 USB 插座将 SATA 设备连接到 Raspberry Pi。这是另一个提醒，您应该使用动力枢纽来确保驱动器获得足够的功率，并减少由于当前过载而造成覆盖物 PI 损坏的机会。

### RS-232 Serial

RS-232—a long-time standard for the serial transmission of data—was _the_ standard and common on many personal computers in the 1980s and 1990s. Before PCs, RS-232 provided communications with terminals like the ones used to control mainframes and minicomputers.

> RS-232(数据串行数据的长期标准)是 *THE* 标准，并且在 1980 年代和 1990 年代的许多个人计算机上都是常见的。在 PCS 之前，RS-232 提供了与用于控制大型机和微型计算机的终端的通信。

All sorts of other peripherals once connected via RS-232 serial ports—printers, mice and other pointing devices, modems and more. However, RS-232 had some disadvantages:

> 各种其他外围设备曾经通过 RS-232 串行端口连接，即打印机，鼠标和其他指向设备，调制解调器等。但是，RS-232 有一些缺点：

- Variations in voltage due to long cables and mismatched transceivers
- Speed limitations
- Large, bulky connectors

>

- 由于长电缆和不匹配的收发器而导致的电压变化
- 速度限制
- 较大，笨重的连接器

USB came along in large part to cure these three disadvantages. RS-232 is still around, however, as connectors with industrial machines, as control ports in large networking devices and on various scientific instruments.

> USB 在很大程度上是为了治愈这三个缺点。但是，RS-232 仍然是与工业机器的连接器，作为大型网络设备和各种科学仪器的控制端口。

---

> [!NOTE]

TTL (Transistor-Transistor Logic) level serial is what almost everyone uses these days. It’s sometimes mistakenly referred to as RS2232.

> ttl(晶体管横向器逻辑)级别串行几乎是每个人几乎每个人都使用的。**有时会错误地称为 RS2232**。

### High Definition Media Interface

High Definition Multimedia Interface (HDMI) allows the transfer of video and audio from an HDMI-compliant display controller (think Raspberry Pi here) to compatible computer monitors, projectors, digital TVs or digital audio devices.

> 高清多媒体接口(HDMI)允许将视频和音频从符合 HDMI 的显示控制器(在此处考虑 Raspberry Pi)转移到兼容的计算机显示器，投影仪，数字电视或数字音频设备。

HDMI’s high quality provides a marked advantage over composite video (such as what comes out of the composite video connector on the Raspberry Pi board). HDMI provides higher resolution instead of composite video’s noisy and sometimes distorted picture.

> HDMI 的高质量比复合视频(例如 Raspberry Pi 板上的复合视频连接器出现的内容)提供了明显的优势。HDMI 提供了更高的分辨率，而不是复合视频的嘈杂，有时是扭曲的图片。

Most TVs sold today include HDMI input ports, as do higher-end video monitors. If you don’t have a TV that has an HDMI port, no problem. Here are two solutions for getting HDMI into non-HDMI devices:

> 今天出售的大多数电视都包括 HDMI 输入端口，以及高端视频监视器。如果您没有具有 HDMI 端口的电视，那就没问题。这是将 HDMI 进入非 HDMI 设备的两种解决方案：

- **Digital Video Interface (DVI):** You’ll find computer monitors with DVI inputs more common than ones accepting HDMI. Just search online retailers for `hdmi to dvi` and you’ll find several solutions (cables and adapter plugs) in the £4 to £7 range.
- **Video Graphics Array** (**VGA):** Most common of all are VGA monitors. A search for `hdmi female to vga male` will get you the right adapter in the £4 to £7 range. This is an active conversion; there is actually some circuitry inside the adapter cable that converts digital signals to analog. In the case of HDMI to DVI, it’s just a remapping of digital signals; HDMI to VGA is more complicated and not as robust.

>

- **数字视频接口(DVI)：**您会发现具有 DVI 输入的计算机监视器比接受 HDMI 更常见。只需在线零售商搜索 ` HDMI到DVI` ，您就会在 4 到 7 英镑的价格中找到几个解决方案(电缆和适配器插头)。
- **视频图形阵列(VGA)：**最常见的是 VGA 监视器。搜索 `HDMI母口到VGA公口` 将为您提供 4 至 7 英镑范围内的正确适配器。这是一个主动转换；适配器电缆内实际上有一些电路将数字信号转换为模拟。对于 HDMI 到 DVI，它只是数字信号的重新映射；HDMI 到 VGA 更为复杂，并且不那么强大。

It is important to know that HDMI-to-HDMI connections include _both_ video and audio. For connections converting HDMI to DVI or VGA, you will find only video goes through the connection. Your options for audio include a separate audio cable from the audio out port of the Raspberry Pi. Alternatively, some adapters have audio ports. You still need to run an audio cable from the converter’s connector to the audio input on the monitor or to separate speakers. However, connecting the cable to the HDMI output of the Raspberry Pi gives better quality. This is the easy way to do it.

> 重要的是要知道 HDMI 到 HDMI 连接包括 *BOTH* 视频和音频。对于将 HDMI 转换为 DVI 或 VGA 的连接，您会发现仅视频通过该连接。您的音频选项包括来自 Raspberry Pi 的音频端口的单独音频电缆。另外，某些适配器具有音频端口。您仍然需要从转换器的连接器到显示器上的音频输入或单独的扬声器运行音频电缆。但是，将电缆连接到 Raspberry Pi 的 HDMI 输出可提供更好的质量。这是这样做的简单方法。

### IIS

Inter-IC Sound (IIS), a communications protocol for carrying digital audio signals, is a type of serial bus interface standard that connects digital audio devices together. (You can read more about IIS in [Chapter 11](#14_9781119183938-ch11.xhtml).) This protocol came from the Dutch technology giant Philips in 1986 as an internal feature of its CD players. The last revision happened in 1996 but this does not hamper its utility.

> Inter-IC Sound(IIS)是一种用于携带数字音频信号的通信协议，是将数字音频设备连接在一起的一种串行总线接口标准。(您可以在[第 11 章]中阅读有关 IIS 的更多信息(＃14_978111919183938-CH11.xhtml)。)该协议来自 1986 年的荷兰技术巨头飞利浦，作为其 CD 参与者的内部功能。最后一次修订发生在 1996 年，但这并没有妨碍其效用。

The following are some choices for good audio from the Raspberry Pi. Which is the correct answer?

> 以下是 Raspberry Pi 的良好音频选择。哪个是正确的答案？

1. Use audio output from the 3.5mm audio jack, which comes from Pulse Wave Modulation (PWM) in converting from digital to analog. It’s limited to about 11 bits, a rate causing some to turn up their noses (or ears) at it.
2. HDMI, which is supposedly `high definition` .
3. USB.
4. Hook a good digital audio converter (DAC) with IIS directly to the Raspberry Pi.

> 1. 使用来自 3.5mm 音频插孔的音频输出，该音频插孔来自脉冲波调制(PWM)，从数字转换为模拟。它限于大约 11 位，这使一些速率导致一些鼻子(或耳朵)。
> 2. HDMI，据说是 `高清` 。
> 3. USB。
> 4. 将良好的数字音频转换器(DAC)与 IIS 直接钩到 Raspberry Pi 上。

The answer, of course is `D` .

> 答案当然是 ` D` 。

However, where do you hook it? There’s no discrete connector plug for IIS on the Raspberry Pi board. Instead, you use the GPIO pins, and you can do that the hard way or the easy way.

> 但是，您在哪里挂上它？Raspberry Pi 板上的 IIS 没有离散的连接器插头。取而代之的是，您使用 GPIO 引脚，并且可以以难以做的方式或简单的方式来完成。

The hard way is by using jumper cables to directly access the needed GPIO pins. Four give you access to the IIS interface on the Broadcom SoC chip that has the CPU, GPU and so on.

> 困难的方法是使用跳线电缆直接访问所需的 GPIO 引脚。四个让您访问具有 CPU，GPU 等的 Broadcom Soc 芯片上的 IIS 接口。

The easy way is by purchasing one of the DAC units mentioned at the end of [Chapter 11](#14_9781119183938-ch11.xhtml). They simply plug onto the GPIO pins and piggyback the Raspberry Pi board, providing a short, noise-free connection with that golden quality sound.

> 简单的方法是购买[第 11 章]末尾提到的 DAC 单元之一(＃14_9781119183938-CH11.xhtml)。他们只需插入 GPIO 引脚，然后将 Raspberry Pi 板袋装出来，提供了与金色质量的声音相关的短而无噪音的连接。

Some configuration is required to turn on and set up the IIS interface. One method is to use Python on Raspbian or a similar Linux-based operating system on the Raspberry Pi. You’ll find a good deal of help on the web for achieving great sound from your Raspberry Pi on the Internet. You can search `raspberry pi sound` for tips and devices.

> 需要一些配置才能打开并设置 IIS 接口。一种方法是在 Raspbian 上使用 Python 或 Raspberry Pi 上的类似基于 Linux 的操作系统。您会在网络上找到很多帮助，以在互联网上从 Raspberry Pi 中获得出色的声音。您可以搜索 ` Raspberry Pi Sound` 以获取技巧和设备。

### IIC

The IIC (Inter-Integrated Circuit) communications protocol also comes from Philips. IIC is a communications bus, providing communications between chips on a printed circuit board. One of its prime uses on the Raspberry Pi board and elsewhere lies in connecting sensors.

> IIC(集成电路间)通信协议也来自飞利浦。IIC 是一辆通信总线，可在印刷电路板上提供芯片之间的通信。它在 Raspberry Pi 板和其他地方的主要用途之一在于连接传感器。

IIC is not initialised when the Raspberry Pi first comes out of the box. You have to tell the Raspberry Pi to use it. You accomplish this under the Raspbian OS (and other operating systems) with the `raspi-config` command in the terminal. On the command line, type

> IIC 当 Raspberry Pi 首先出现时，不会初始化 C。您必须告诉 Raspberry Pi 使用它。您可以在终端中使用 `raspi-config` 命令的 Raspbian OS(和其他操作系统)下完成此操作。在命令行上，键入

```
sudo raspi-config
```

Use the down arrow key to select 9 Advanced Options and press the Enter key. On the next screen, select A7 I2C to toggle the automatic loading of I2C on or off. (See Figure 12-6.) A reboot is required each time for the new state to take effect.

> 使用向下箭头键选择 9 个高级选项，然后按 Enter 键。在下一个屏幕上，选择 A7 I2C 以切换 I2C 打开或关闭的自动加载。(请参见图 12-6。)每次需要重新启动才能生效。

![[FIGURE 12-6:](#15_9781119183938-ch12.xhtml#rc12-fig-0006) Enabling IIC on Raspberry Pi using `raspi-config`](./media/images/9781119183938-fg1206.png)

As with most interfaces related to the GPIO pins, many of which enable connection to services on the Broadcom SoC, some programming is required. The steps in shell scripts or Python (one of the favoured methods of GPIO-programmed control) are beyond the scope of this book, but there are many examples on the web. You can search for `raspberry pi gpio python scripts` .

> 与 GPIO 引脚相关的大多数接口(其中许多接口都可以与 Broadcom SoC 上的服务连接)，需要进行一些编程。Shell Scripts 或 Python(GPIO Programmed Control 的最喜欢的方法之一)中的步骤超出了本书的范围，但是网络上有很多示例。您可以搜索 ` Raspberry Pi Gpio Python脚本` 。

### Raspberry Pi Display, Camera Interface and JTAG

Before we get to GPIO, we have two more interfaces to mention. These two interfaces connect with ribbon cable connectors:

> 在进入 GPIO 之前，我们还有两个接口要提及。这两个接口与色带电缆连接器连接：

- **Camera Serial Interface (CSI)** (the MIPI CSI-2 standard): This interface allows the connection of a camera. Cameras for the Raspberry Pi are available. It is sometimes a bit irksome to connect the ribbon cable just right, but once things are hooked up properly you can program the Raspberry Pi to do all sorts of neat stuff with digital photography and video. Camera boards/modules cost about £25, so experimenting is possible at a reasonable cost.
- **Display Serial Interface (DSI):** This interface enables you to connect small displays to the Raspberry Pi board. This makes the Raspberry Pi, along with a battery power source, truly portable. A simple LED device costs about £9 whereas the official Raspberry Pi 7-inch touchscreen LCD monitor costs £65.

>

- **相机串行接口(CSI)**(MIPI CSI-2 标准)：此接口允许相机的连接。可用于 Raspberry PI 的摄像机。有时候，正确连接缎带电缆有点令人讨厌，但是一旦正确连接到东西，您可以编程 Raspberry Pi，以使用数字摄影和视频来完成各种整洁的事情。相机板/模块的价格约为 25 英镑，因此可以以合理的成本进行实验。
- **显示串行接口(DSI)：**此接口使您可以将小显示器连接到 Raspberry Pi 板。这使得 Raspberry Pi 以及电池电源真正便携。一个简单的 LED 设备的价格约为 9 英镑，而官方 Raspberry Pi 7 英寸触摸屏 LCD 显示器的价格为 65 英镑。

---

> [!NOTE]

The JTAG Header for debugging was on the older Raspberry Pi boards but isn’t on the Raspberry Pi 2. JTAG provides facilities for debugging using techniques such as stepping through code and using break points (stopping at various places in the code). JTAG on newer boards is available via GPIO pins.

> 用于调试的 JTAG 标题是在较旧的 Raspberry Pi 板上，但不在 Raspberry Pi 2 上。JTAG 提供了使用诸如逐步浏览代码和使用断点(在代码中的各个位置停止)等技术进行调试的设施。可以通过 GPIO 引脚获得新板上的 JTAG。

## Raspberry Pi GPIO

The general purpose input output (GPIO) performs magic in tying the Raspberry Pi to the real world. Through these pins, the Raspberry Pi is programmed to control microcontrollers and real-world devices—such as doorbells, light bulbs, model aircraft controls, lawn mowers, robots, thermostats, electric coffeepots, motors of all sorts—that normally cannot connect to a computer or follow its orders.

> 通用输入输出(GPIO)在将 Raspberry Pi 绑定到现实世界中表现出魔力。通过这些引脚，对 Raspberry PI 进行了编程，以控制微控制器和现实世界设备，例如门铃，灯泡，模型飞机控制，割草机，机器人，恒温器，电动咖啡机，电动机，各种各样的电动机，通常无法连接到一个连接到计算机或遵循其订单。

We start by exploring the truly exciting wonders of GPIO control with the original Model B (as opposed to the current Raspberry Pi 3). The Model B (see Figure 12-7) has fewer GPIO pins than the two next releases—the Model B+ and Raspberry Pi 2. The extra pins on those versions work the same but give added capacity—but let’s keep it simple for the moment. The pin assignments for the first 26 pins remain the same on all models of the Raspberry Pi.

> 首先，使用原始 M 型 B 探索 GPIO 控制的真正令人兴奋的奇观(与当前的 Raspberry Pi 3 相反)。模型 B(见图 12-7)的 GPIO 引脚少于接下来的两个发行版-B+ 和 Raspberry Pi 2.这些版本上的额外引脚的工作原理相同，但可以增加容量，但现在让我们保持简单。在 Raspberry Pi 的所有型号上，前 26 个引脚的销分配保持不变。

![[FIGURE 12-7:](#15_9781119183938-ch12.xhtml#rc12-fig-0007) GPIO pins on Raspberry Pi 2](./media/images/9781119183938-fg1207.png)

### GPIO Overview and the Broadcom SoC

The key to making the Raspberry Pi possible at such an incredibly low price is the Broadcom system-on-a-chip (SoC). As previously mentioned, in this one chip live CPU(s), GPUs and various interfaces, including UART, IIC, SPI (Serial Peripheral Interface) and so forth. The GPIO pins allow us to program these interfaces and also do much more.

> 使 Raspberry PI 以如此低的价格成为可能的关键是 Broadcom on-A-Chip(SOC)。如前所述，在此芯片实时 CPU(S)，GPU 和各种接口，包括 UART，IIC，SPI(串行外围界面)等。GPIO 引脚使我们能够对这些接口进行编程，并做更多的事情。

The GPIO pins (P1 on the Raspberry Pi boards—either 26 on earlier models or 40 on the newer ones) allow configuration (that is, they are _programmable_) in several ways, such as:

> GPIO 引脚(Raspberry Pi 板上的 P1(在较早的型号上是 26 个)或较新的型号 40)允许以几种方式(即它们是 *programbable*)的配置，例如：

- General-purpose input
- General-purpose output
- Up to six alternative settings, depending on the pin

>

- 通用输入
- 通用输出
- 最多六个替代设置，具体取决于引脚

The following items apply to most pins, but some are used as positive voltage sources or grounds:

> 以下项目适用于大多数引脚，但有些则用作正电压来源或理由：

- **Power-on states:** GPIOs (depending on the operating system and firmware in use) reset to general-purpose inputs when the board is rebooted.
- **Interrupts:** Each pin is programmable to generate an interrupt to the Broadcom’s CPUs/GPUs. These interrupts can be configured as:
  - Level-sensitive
  - Rising/falling edge
  - Asynchronous rising/falling edge.
- **Alternative functions:** As mentioned earlier, almost all of the GPIO pins have alternative functions in addition to simple switching operations. These involve direct connections (through the pins) to Broadcom IoC. The peripherals in the SoC, such as the UART and IIC buses, can be programmable to at least three sets of pins.

>

- **电动状态：** GPIO(根据操作系统和使用中的固件)重置在重新启动板时通用输入。
- **中断：**每个引脚都可以编程，以生成 Broadcom CPU/GPU 的中断。这些中断可以被配置为：
  - 级别敏感
  - 上升/下降边缘
  - 异步上升/下降边缘。
- **替代功能：**如前所述，除了简单的切换操作外，几乎所有 GPIO 引脚都具有替代功能。这些涉及与 Broadcom IOC 的直接连接(通过引脚)。SOC 中的外围设备，例如 UART 和 IIC 总线，可以至少为至少三组引脚编程。

---

> [!NOTE]

For more information on connecting to these low-level peripherals, visit [`http://elinux.org/RPi_Low-level_peripherals`](http://elinux.org/RPi_Low-level_peripherals).

> 有关连接到这些低级外围设备的更多信息，请访问[[http://elinux.org/rpi_low-levle-level_peripherals`]](http://elinux.org/rpi_low-levle-level_peripherals%60%5D)(

#### GPIO Header 1

GPIO 1 refers to the P1 connector on Raspberry Pi boards—either the 26 pins on Model A and Model Bs or the 40 pins on the B+, Raspberry Pi 2 Model B and the new Raspberry Pi Zero.

> GPIO 1 指的是 Raspberry Pi 板上的 P1 连接器 A 和 BS 模型 BS 上的 26 个引脚或 B+，Raspberry Pi 2 型号 B 和新的 Raspberry Pi 零上的 40 个引脚。

#### GPIO Header 5

GPIO 5 provides additional GPIO connections on the Model A and Model B via the P5 header. This header does not have pins, so any connection to it has to be soldered to the board. From the Model B+ on, additional pins added to the P1 header replace the P5 header.

> GPIO 5 通过 P5 标头在模型 A 和模型 B 上提供了其他 GPIO 连接。该标头没有引脚，因此必须将其连接到板上。从模型 B+ 开启，添加到 P1 标头的其他引脚替换了 P5 标头。

### Meeting the GPIO

The GPIO performs magic in tying the Raspberry Pi to the real world. Through these pins, you can program the Raspberry Pi to control all sorts of real-world devices. First, we’ll examine these pins and understand just how simple and powerful they are. Then we’ll look at programming the Raspberry Pi to understand inputs, outputs and control devices.

> GPIO 在将 Raspberry Pi 绑定到现实世界时表现出魔力。通过这些引脚，您可以对 Raspberry Pi 进行编程以控制各种现实世界设备。首先，我们将检查这些引脚，并了解它们的简单和强大。然后，我们将研究对 Raspberry Pi 进行编程以了解输入，输出和控制设备。

#### Pin Layout

Figure 12-8 shows the GPIO pins on the Model B.

![[FIGURE 12-8:](#15_9781119183938-ch12.xhtml#rc12-fig-0008) Close-up of the Raspberry Pi Model B’s 26 GPIO pins](./media/images/9781119183938-fg1208.png)

There are 26 pins—two rows of 13 each. The bottom row pins (left to right) consist of odd numbers: 1, 3, 5, 7, 9, 11, 13, 15, 17, 19, 21, 23 and 25. The top row pins (left to right) are even numbered: 2, 4, 6, 8, 10, 12, 14, 16, 18, 20, 22, 24 and 26.

The pins, when set as outputs, act like switches and provide power, enabling the Raspberry Pi to interact with other devices and—in some cases—supply the electricity those devices need to run. Later in this chapter is an example of using the Raspberry Pi to flash some lights.

> 引脚将其设置为输出时，就像开关一样，使 Raspberry Pi 与其他设备进行交互，并且在某些情况下供应这些设备需要运行的电力。本章的后期是使用 Raspberry Pi 闪烁一些灯的一个示例。

The IO in GPIO stands for input/output. When you have a device connected to the Raspberry Pi and flip an external switch or, more likely, some electrical or mechanical gizmo opens or closes, that’s _input_. It’s a changed condition causing a program running on the Raspberry Pi to respond with some sort of action.

> GPIO 中的 IO 代表输入/输出。当您将设备连接到 Raspberry Pi 并翻转外部开关，或者更有可能打开或关闭某些电气或机械 Gizmo，那就是 _input_。这是一个变化的条件，导致在 Raspberry Pi 上运行的程序以某种操作做出响应。

Here’s an example of both input and output. You build a home security project using a Raspberry Pi. Someone opens an outside door. A wireless magnetic switch closes. The Raspberry Pi picks up the signal and closes a circuit, causing a chime to go off during the day or a siren at night. The door switch changes state from closed to open when it detects the door is ajar. A program on the Raspberry Pi outputs a switch closing, which causes the chime or siren to sound. Both tasks are accomplished through connections to GPIO pins—two different circuits were completed.

> 这是输入和输出的示例。您使用 Raspberry Pi 构建家庭安全项目。有人打开外门。无线磁开关关闭。Raspberry Pi 拾取了信号并关闭电路，导致白天或晚上发出警笛声。当门开关检测到门是 Ajar 时，门开关从闭合状态变为打开状态。Raspberry Pi 上的程序输出了一个开关关闭，这会导致铃声或警报声发出声音。这两个任务都是通过与 GPIO 引脚的连接完成的，两个不同的电路已经完成。

---

> [!NOTE]

Thanks to the Raspberry Pi’s ability to communicate in various ways—such as by wireless, Bluetooth or the Internet—inputs and outputs do not even have to be local. Devices and programs can be controlled from anywhere in the world!

> 得益于 Raspberry Pi 以各种方式(例如通过无线，蓝牙或互联网)进行交流的能力，甚至不必是本地的。可以从世界任何地方控制设备和程序！

Circuits closing and opening describe electronic control. See the `[Circuits](#15_9781119183938-ch12.xhtml#c12-fea-0001)` sidebar for additional explanation of circuits.

> 电路关闭和开放描述电子控制。有关电路的其他说明，请参见 ` [电路](＃15_978111919183938-CH12.XHTML＃C12-FEA-0001)` 侧边栏。
