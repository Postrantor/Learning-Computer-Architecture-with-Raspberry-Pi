Chapter 8

> [!note]
> 这一章对操作系统进行较为系统的介绍，操作系统的概念，做了那些事，内核是什么

# Operating Systems

**BEFORE EXPLORING THE** world of operating systems, we should be clear about what they are. Here’s a basic definition from the online version of the _Merriam-Webster_ dictionary, of all places, that hits it better than many computer books: it says an operating system is `the main program in a computer that controls the way the computer works and makes it possible for other programs to function` .

> **在探索操作系统的**世界之前，我们应该清楚它们是什么。这里有一个来自在线版本的《梅里姆-韦伯词典》的基本定义，它比许多计算机书籍都更符合这个定义：它说操作系统是 `计算机中控制计算机工作方式的主要程序，并使其他程序能够运行` 。

We can expand on this definition by saying that the operating system (OS) consists of software that controls the use of computer hardware and software resources, enables user interaction via applications (programs), or gives direct access to various functions outside of applications, such as copying or deleting files, updating the OS itself, and so forth. We understand the OS hides way out of sight but it makes everything the computer does possible. Figure 8-1 shows a basic computer system.

> 我们可以扩展这个定义，说操作系统(OS)由控制计算机硬件和软件资源使用的软件组成，通过应用程序(程序)实现用户交互，或者直接访问应用程序之外的各种功能，例如复制或删除文件、更新 OS 本身等等。我们理解操作系统隐藏在视线之外，但它使计算机所做的一切都成为可能。图 8-1 显示了基本计算机系统。

![[FIGURE 8-1:](#11_9781119183938-ch08.xhtml#rc08-fig-0001) A basic computer system](./media/images/9781119183938-fg0801.png)

This chapter first looks at operating systems in general, including their fascinating history. We explore concepts like time-sharing, in which the OS controls slices of processor time, memory usage, mass storage reads and writes, and all the system’s other facilities and resources to enable multitasking (running more than one application at essentially the same time). Time-sharing also allows multiuser modes in which several users—or even millions (think Google and Facebook as examples)—each run one or more applications simultaneously.

> 本章首先从总体上看操作系统，包括它们迷人的历史。**我们探索了分时等概念，其中操作系统控制处理器时间、内存使用、大容量存储读取和写入以及系统的所有其他设施和资源，以实现多任务处理(基本上同时运行多个应用程序)。时间共享还允许多用户模式，**其中几个用户甚至数百万用户(以谷歌和 Facebook 为例)同时运行一个或多个应用程序。

We also explore kernels in this chapter. The kernel is software that oversees and exerts basic control for a computer’s hardware, memory access, central processing unit (CPU), storage devices and file systems, and all the rest of its resources. The OS’s kernel provides the necessary interface for applications to use the computer’s hardware. Word processing software, web browsers, email clients, media players and so on would be useless if they could not access and save data and perform operations on that data when it became available to the software. The kernel serves as both the heart and the brains of an OS. Through discussions of how the OS manages file systems, working memory and similar resources, you will see how the kernel manages operations in detail.

> **在本章中，我们还将探讨内核。内核是一种软件，它监督并对计算机的硬件、内存访问、中央处理单元(CPU)、存储设备和文件系统以及所有其他资源进行基本控制。操作系统的内核为应用程序使用计算机硬件提供了必要的接口。如果文字处理软件、网络浏览器、电子邮件客户端、媒体播放器等无法访问和保存数据，并且无法在数据对软件可用时对其执行操作，那么这些软件将毫无用处。内核是操作系统的心脏和大脑。通过对 OS 如何管理文件系统、工作内存和类似资源的讨论，您将看到内核如何详细管理操作。**

The `[Enablers and Assistants to the Operating System](#11_9781119183938-ch08.xhtml#c08-sec-0022)` section covers ways in which the OS accesses and/or administers the sharing of CPU time, memory, media access, and all other facets of multitasking/time sharing. It encompasses what is required in the way of interfacing for complete control of the computer’s hardware and software. We examine firmware (small programs usually kept in flash memory or some other permanent storage media) used to boot and enable the kernel for operation, and we also look at device drivers, which give the system access to various hardware peripherals such as keyboards, displays, mice and other pointing devices, and disk drives, USB peripherals of all sorts, printers, scanners and so on.

> `[操作系统的使能器和助手](#11_9781119183938-ch08.xhtml#c08-sec-0022)` 部分介绍了操作系统访问和/或管理 CPU 时间、内存、媒体访问以及多任务/时间共享的所有其他方面的方式。它包含了完全控制计算机硬件和软件所需的接口方式。我们研究了用于引导和启用内核运行的固件(通常保存在闪存或其他永久存储介质中的小程序)，我们还研究了设备驱动程序，这些驱动程序允许系统访问各种硬件外围设备，如键盘、显示器、鼠标和其他定点设备，以及磁盘驱动器、各种 USB 外围设备、打印机、扫描仪等。

---

> [!NOTE]

It’s worth noting here that not all device drivers are firmware; many device drivers reside on the hard drive—or, in the case of the Raspberry Pi, the SD card—and become available as the operating system establishes access to that type of storage.

> **值得注意的是，并非所有设备驱动程序都是固件；许多设备驱动程序驻留在硬盘驱动器上，或者在 Raspberry Pi 的情况下，驻留在 SD 卡上，并且随着操作系统建立对该类型存储的访问而变得可用。**

Finally, getting back to the Raspberry Pi specifically, the last section in this chapter gives an overview of various OSs for the Raspberry Pi (the different flavours of Linux are sometimes called distros, or distributions). It provides sources for OS downloads as well as applications and other software such as utility programs, source code and device drivers. This includes specific considerations of the Raspberry Pi’s computer architecture and its available OSs from various versions of GNU/Linux, such as Debian, to the most popular Raspberry Pi distro, Raspbian Linux (a version of Debian that’s been optimised for the Raspberry Pi). In addition, we look at the new wealth of OSs that has opened up thanks to the new four-core Advanced RISC Machine (ARM) processor in the Raspberry Pi 2 and 3. These include Raspberry Pi–enhanced versions of Ubuntu, Fedora and Gentoo, as well as Windows 10.

> 最后，回到树莓派，本章的最后一节对树莓派的各种操作系统进行了概述(Linux 的不同风格有时被称为发行版或发行版)。它提供 OS 下载源，以及应用程序和其他软件，如实用程序、源代码和设备驱动程序。这包括树莓派的计算机架构及其可用操作系统的具体考虑，从各种版本的 GNU/Linux(如 Debian)到最流行的树莓派发行版树莓 Linux(已针对树莓派优化的 Debian 版本)。此外，我们还将看到由于复盆子 Pi 2 和 3 中新的四核高级 RISC 机器(ARM)处理器而带来的操作系统的新财富。其中包括树莓派——Ubuntu、Fedora 和 Gentoo 的增强版，以及 Windows 10。

## Introduction to Operating Systems

A full understanding of modern-day OSs requires a look at how and why they came about. Significant OSs include Unix and Linux, which have had a profound influence on Windows, the Mac OS, and smartphone OSs of more recent vintage. Like humanity itself, any operating system contains the physical heredity if those that existing before.

> 全面了解现代操作系统需要了解它们是如何产生的以及为什么产生的。重要的操作系统包括 Unix 和 Linux，它们对 Windows、Mac OS 和最近的智能手机操作系统产生了深远的影响。就像人类本身一样，任何操作系统都包含着以前存在的物理遗传。

### History of Operating Systems

Early computers ran one program at a time. Without an OS to parcel out simultaneous tasks, they proceeded from the beginning of a problem to the end. Their utility lay in fast number crunching, far faster than human operators could match even if they were using mechanical calculation machines. In short, although these first computers had rudimentary memory and program control, their design was influenced greatly by what calculators did well—arithmetic. Early computers were basically super calculators. This changed, as we will soon see, with the advent of true operating systems supervising much more powerful uses of computers.

> 早期的计算机每次运行一个程序。如果没有操作系统来划分同时执行的任务，他们会从问题的开始到结束。它们的效用在于快速的数字运算，即使是使用机械计算机器，其运算速度也远超人类操作员。简而言之，尽管这些第一代计算机具有基本的内存和程序控制，但它们的设计受到计算器运算能力的影响很大。早期的计算机基本上是超级计算器。正如我们很快就会看到的那样，随着真正的操作系统的出现，这种情况发生了变化，这些操作系统对计算机的使用进行了更强大的监控。

Although some experts consider the Atanasoff–Berry computer built in 1937 at Iowa State University or the Colossus Mark 1 used at Bletchley Park during World War II to be the first digital electronic computers, ENIAC (which stands for Electronic Numerical Integrator And Computer) is the one that caught the public’s attention. It was secretly built during World War II and announced publicly in 1946.

> 尽管一些专家认为 1937 年在爱荷华州立大学建造的 Atanasoff–Berry 计算机或二战期间在布莱切利公园使用的巨像 Mark 1 是第一台数字电子计算机，但 ENIAC(代表 electronic Numerical Integrator And computer)是引起公众关注的计算机。它是在第二次世界大战期间秘密建造的，并于 1946 年公开宣布。

Newspapers called ENIAC the `Giant Brain` . It could solve a wide range of numerical problems around 1,000 times faster than previous electromechanical computers. Inside the large racks that made up ENIAC were 17,468 vacuum tubes, 7,200 crystal diodes, 1,500 relays, 70,000 resistors, 10,000 capacitors and something like five million hand-solder connections. It weighed about 30 tons and took up 1,800 square feet while consuming 150 kilowatts of power. As shown in Figure 8-2, it was big, and what you see in the figure is only part of the entire thing.

> 报纸称 ENIAC 为 `巨型大脑` 。它可以比以前的机电计算机快 1000 倍左右解决各种数值问题。在组成 ENIAC 的大型机架内，有 17468 个真空管、7200 个晶体二极管、1500 个继电器、70000 个电阻器、10000 个电容器和 500 万个手工焊接接头。它重约 30 吨，占地 1800 平方英尺，耗电 150 千瓦。如图 8-2 所示，它很大，您在图中看到的只是整个事情的一部分。

![Figure courtesy of the United States Army ¶ [FIGURE 8-2:](#11_9781119183938-ch08.xhtml#rc08-fig-0002) ENIAC, 1940s](./media/images/9781119183938-fg0802.png)

#### Mainframes

Huge computers called mainframes proliferated in large companies, universities and government agencies, computerising a variety of applications that had once required rooms full of people doing manual calculating. However, although big computers solved problems, they presented a huge problem.

> 大型公司、大学和政府机构大量使用大型计算机，将各种应用程序计算机化，这些应用程序曾经需要满屋子的人进行人工计算。然而，尽管大型计算机解决了问题，但它们带来了一个巨大的问题。

That difficulty was the linear nature of the early mainframes. The need to manage resources and speed up the process was obvious. Manufacturers started adding libraries of code controlling operations such as input and output functions, which meant programmers no longer had to write often-used routines for every program. Instead, they put a link in the code to call the required library of instructions. Because the code did not execute until the program was actually running the computer, these prepackaged routines were termed runtime libraries.

> 这种困难是早期大型机的线性特性。显然需要管理资源并加快进程。制造商开始添加代码控制操作库，如输入和输出函数，这意味着程序员不再需要为每个程序编写经常使用的例程。相反，他们在代码中添加了一个链接来调用所需的指令库。因为代码直到程序实际运行计算机时才执行，所以这些预先打包的例程被称为运行库。

#### Early Operating Systems

As with many things in computer science history, there is some dispute over what was the first real OS. Some historians say LEO 1 (which stands for Lyons Electronic Office), which was developed in 1950 for the electronic delay storage automatic calculator (EDSAC) computing platform, was the first. However, other sources say the first OS came from General Motors in 1956 and was written for the company’s IBM 704 mainframe. Essentially, all of the early OSs came about from mainframe customers who were trying to answer specific needs in their industry. When new machines were purchased, these systems required rewriting and recompiling for the new machine.

> 与计算机科学史上的许多事情一样，第一个真正的操作系统是什么存在争议。一些历史学家说，LEO 1(代表里昂电子办公室)是第一个，它于 1950 年为电子延迟存储自动计算器(EDSAC)计算平台开发。然而，其他消息人士表示，第一个操作系统是 1956 年通用汽车公司为该公司的 IBM 704 大型机开发的。从本质上讲，所有早期的操作系统都来自大型机客户，他们试图满足其行业的特定需求。当购买新机器时，这些系统需要为新机器重写和重新编译。

By the 1960s, computer manufacturers began attempting to provide OSs for their machines. An example of an early manufacturer OS was OS/360, which consisted of several different versions developed by IBM for their 360 series. Because of differences in hardware and thus performance, OS/360 was more a family of OSs than one unified OS.

> 到了 20 世纪 60 年代，计算机制造商开始尝试为他们的机器提供操作系统。早期制造商操作系统的一个例子是 OS/360，它由 IBM 为其 360 系列开发的几个不同版本组成。由于硬件和性能的差异，OS/360 更像是一个操作系统家族，而不是一个统一的操作系统。

Operating systems, driven by competition to sell mainframes, were becoming more complex and, most importantly, they were becoming more useful. Earlier computers were limited in the tasks they could accomplish, or gave computers flexibility and scope. UNIVAC, Burroughs, GE and others presented their own OSs.

> 在大型机销售竞争的推动下，操作系统变得越来越复杂，最重要的是，它们变得越来越有用。早期的计算机所能完成的任务有限，或者给了计算机灵活性和范围。UNIVAC、Burroughs、GE 和其他公司展示了自己的操作系统。

#### Smaller Computers, Better Operating Systems

The 1970s brought true change to computing. The first indication was the minicomputer, which truly earned its designation as `mini` because it was many times physically smaller than mainframes. No longer were large computer rooms with raised floors (for cables to run underneath) and special cooling systems required. And operators stopped wearing white coats like doctors or research scientists.

> 20 世纪 70 年代给计算带来了真正的变革。第一个迹象是小型计算机，它真正赢得了 `迷你` 的称号，因为它在物理上比大型机小很多倍。不再需要带有活动地板的大型计算机室(用于电缆在下面敷设)和特殊的冷却系统。操作人员不再像医生或研究科学家那样穿白大褂。

Smaller companies could purchase a minicomputer and put it in their offices. The cooling fans on these babies were so loud that a vacant office was often converted into `the computer room` .

> 小公司可以购买一台小型计算机并将其放在办公室。这些婴儿身上的散热风扇太吵了，一间空置的办公室经常被改建成 `电脑室` 。

#### Personal Computers

The personal or microcomputer came about in the late 1970s. Computer usage exploded, and with it came a demand for ease of use. Now just about anyone could have a home computer, a hobby computer or a computer on the desk at work. On this smaller computer architecture (remember the word _micro_), tight control of resources was paramount in avoiding slowdowns and actually getting work done or games played.

> 个人电脑或微型计算机出现于 20 世纪 70 年代末。计算机使用量激增，随之而来的是对易用性的需求。现在几乎每个人都可以在办公桌上放一台家用电脑、一台业余电脑或一台电脑。在这种较小的计算机体系结构(记住 *micro* 这个词)上，严格控制资源对于避免速度减慢和实际完成工作或玩游戏至关重要。

Selling computers to consumers and small businesses called for _features,_ which were both useful and simply imagination-catching things the computer could do (graphics, sound, and so forth). The features required fast advances in operating systems.

> 向消费者和小企业出售计算机需要功能，这些功能既有用，又能捕捉计算机的想象力(图形、声音等)。这些功能需要操作系统的快速发展。

Companies like Commodore, Radio Shack and Apple appeared and, yes, IBM was back with the personal computer (PC) starting in 1982. Soon thereafter, a ton of manufacturers were building IBM clones, PCs that ran the disk operating system (DOS). Figure 8-3 shows IBM’s first PC from 1981.

> 像 Commodore、Radio Shack 和 Apple 这样的公司出现了，是的，IBM 从 1982 年开始重新推出个人电脑(PC)。此后不久，大量制造商开始生产运行磁盘操作系统(DOS)的 IBM 克隆机。图 8-3 显示了 1981 年 IBM 的第一台 PC。

![Photo courtesy of Ruben de Rijcke via Wikimedia Commons ¶ [FIGURE 8-3:](#11_9781119183938-ch08.xhtml#rc08-fig-0003) The first IBM PC, model 5150 with model number 5151 monitor and IBM PC keyboard](./media/images/9781119183938-fg0803.png)

PCs proliferated and all sorts of peripherals—displays, keyboards, printers, game controllers, etc., etc.—were soon hung off them. Operating systems to support all this demand went into massive and continuous development and improvement.

> 个人电脑激增，各种外围设备显示器、键盘、打印机、游戏控制器等很快就被挂上了。支持所有这些需求的操作系统进行了大规模、持续的开发和改进。

Xerox’s famous Palo Alto research centre came up with the computer mouse and a workable graphical user interface (GUI), making WYSIWYG (what you see is what you get) possible. With WYSIWYG, whatever you see on the screen looks the same way when printed or otherwise output. Before the first GUI, as an example, word processing depended upon some sort of mark-up for formatting. You had no idea what the final product would look like until you sent it to the printer. GUI, thus, presented a seminal advance in ease of computing.

> Xerox 著名的 Palo Alto 研究中心推出了计算机鼠标和可操作的图形用户界面(GUI)，使所见即所得成为可能。使用 WYSIWYG，您在屏幕上看到的任何内容在打印或以其他方式输出时看起来都是相同的。例如，在第一个 GUI 之前，文字处理依赖于某种格式化标记。你不知道最终的产品会是什么样子，直到你把它送到打印机。因此，GUI 为计算的易用性带来了开创性的进步。

The OSs on Apple’s Macintosh and Microsoft’s Windows built on Xerox’s start, making the personal computer a great deal more user friendly than the big machines preceding it. This new _ease of use_ resulted in wider acceptance by consumers and rapidly growing small computer sales. Underlying this explosive success were the new microcomputer operating systems enabling anyone who could push a mouse to use computers.

> 苹果的 Macintosh 和微软的 Windows 上的操作系统建立在 Xerox 的基础上，使个人计算机比之前的大型计算机更易于用户使用。这种新的使用环境导致了消费者的广泛接受和小型计算机的快速增长。这一爆炸性成功的基础是新的微型计算机操作系统，它使任何人都可以推鼠标使用计算机。

Today, computers continue decreasing in size, speeding up, getting multicore CPUs and demanding a similar expansion in the power of the OSs running them. This allows OSs to do more things, faster.

> 如今，计算机的尺寸不断减小，速度不断加快，得到了多核 CPU，并要求运行这些 CPU 的操作系统的功率进行类似的扩展。这使得操作系统可以更快地完成更多的任务。

### The Basics of Operating Systems

The major benefits of an operating system include

> 操作系统的主要优点包括

- It gives applications easy but safe access to hardware, `safe` meaning in a manner that performs the desired actions without danger of crashing the system. - It manages sharing of data and security to prevent unauthorised access or any sort of corruption of the data from occurring, all making for more efficient and accurate operation. - It enables use of resources, such as memory, storage, sockets for networking and the Internet.

> -**它使应用程序可以轻松但安全地访问硬件，`安全` 意味着可以执行所需的操作，而不会导致系统崩溃。-它管理数据共享和安全，以防止发生未经授权的访问或任何类型的数据损坏，从而提高操作效率和准确性。-它允许使用资源，如内存、存储、网络和 Internet 的套接字。**

> [!NOTE]
> 我想中间件要做的事情也应该就是这些吧

The first point in this list brings up one of the original problems from the mainframe days. This problem contributed a lot of the impetus for developing some sort of resource management.

> 此列表中的第一点提出了大型机时代的一个原始问题。这个问题为发展某种资源管理提供了很大的动力。

Programmers punched their programs on stacks of paper cards and presented them to a computer operator. The operator fed the cards into a punch reader, and the program—in direct control of the computer hardware, since there was no OS layer—ran until it ended or, horrors, crashed that huge hunk of iron.

> 程序员在一摞纸卡片上打孔，然后把程序交给电脑操作员。操作员将卡片送入打卡机，程序直接控制计算机硬件，因为在结束之前没有操作系统层运行，或者，可怕的是，撞毁了那大块铁。

Scores, or even hundreds, of programmers might be submitting program decks for that mainframe. In effect, during the time his or her program ran, every single programmer totally controlled the machine. If one programmer had an error in a routine requesting a write to the output cardpunch or tape drive, the whole computer could crash, causing damage costing a million dollars or more.

> 数十名甚至数百名程序员可能正在提交该大型机的程序集。实际上，在他或她的程序运行期间，每个程序员都完全控制了机器。如果一个程序员在请求向输出打卡机或磁带机写入数据的例程中出错，整个计算机可能会崩溃，造成损失达一百万美元或更多。

At the very least, loss of time occurred as operators rushed to correct the crash or were even forced to reboot the whole machine. Meanwhile cards piled up on the submission table and other programmers became agitated as they waited in line for the running of their urgent jobs.

> 至少，由于操作人员匆忙纠正故障，甚至被迫重启整个机器，造成了时间损失。与此同时，提交表上堆积着卡片，其他程序员在排队等待紧急工作时变得焦躁不安。

Isolating user programs—applications—from directly commanding hardware or at least controlling their use is the norm today. GUIs incorporated into OSs such as Xerox’s original GUI computers, Apple’s Mac OS (and its newer incarnation OS X), Microsoft Windows, and the many variants of UNIX and Linux (via X Windows) force application compliance. For an application to print, save to disk, read a file and so on requires going through the OS.

> 将用户程序应用程序与直接控制硬件或至少控制其使用隔离是当今的标准。并入操作系统的 GUI，如 Xerox 的原始 GUI 计算机、Apple 的 Mac OS(及其更新版本的 OS X)、Microsoft Windows 以及 UNIX 和 Linux 的许多变体(通过 X Windows)，强制应用程序遵从性。应用程序要打印、保存到磁盘、读取文件等，都需要通过操作系统。

Operating systems today multitask, whether they are managing desktop computers, laptops, smartphones or even huge machines that utilise hundreds or thousands of parallel processors. Multitasking allows the OS to share system resources by slicing CPU time into little chunks allocated to simultaneous users and/or background processes. Multitasking is achieved with interrupts, and most computers today are described as interrupt-driven.

> **如今的操作系统是多任务的，无论是管理台式电脑、笔记本电脑、智能手机，还是使用数百或数千个并行处理器的大型机器。多任务允许操作系统通过将 CPU 时间分成分配给同时用户和/或后台进程的小块来共享系统资源。多任务是通过中断实现的，现在大多数计算机都被描述为中断驱动。**

> [!note]
> 这里对终端的描述不太一样哈！
> 只要是支持多任务的计算机，就是中断驱动的呗？不知道可以这样理解不

#### Interrupts

A computer executes one instruction at a time, one after the other. It will continue running a set of instructions (a program) until it finishes or receives an interrupt signal. Interrupts order the computer’s CPU and other hardware to stop the current operation, run another set of instructions—or two or three—and then return to the program in progress. This allows time slicing to work and is the basis for multitasking.

> 计算机一次执行一条指令，一条接一条。它将继续运行一组指令(程序)，直到它完成或接收到中断信号。中断命令计算机的 CPU 和其他硬件停止当前操作，运行另一组指令或两条或三条指令，然后返回正在进行的程序。这允许时间分割工作，并且是多任务处理的基础。

Interrupts are completed at computer speed, so the user or users normally notice no slowdown in applications as the computer runs other programs, background processes, and the like. The OS accomplishes its `housekeeping` tasks in this manner.

> 中断以计算机速度完成，因此当计算机运行其他程序、后台进程等时，用户通常不会注意到应用程序的速度减慢。操作系统以这种方式完成其 `内务管理` 任务。

Background processes include such mundane tasks as time and date keeping, checking for software upgrades, monitoring for keyboard or other input and so forth. They also enable applications to periodically request service and receive their data. A good example of the latter is an email client looking for and receiving incoming messages.

> 后台处理包括诸如时间和日期保持、检查软件升级、监控键盘或其他输入等日常任务。它们还使应用程序能够定期请求服务并接收数据。后者的一个很好的例子是电子邮件客户端查找和接收传入消息。

The OS contains a scheduling program, the interrupt handler, that runs to track and prioritise interrupts to be executed in the proper sequence. The scheduler lets the OS determine which program gets a slice of runtime next.

> **操作系统包含一个调度程序，即中断处理程序**，它运行来跟踪并优先处理要按正确顺序执行的中断。调度器让操作系统决定下一步哪个程序获得运行时的一部分。

The OS also makes scheduling even more effective by looking for chunks of downtime in which to cram interrupts and to speed multitasking even more. As the words in this paragraph are punched into the word processor, the OS notes and uses any pauses in typing or times when the writer stops to think about what comes next, and it runs slices for scores of other jobs in the queue. Users may dawdle, but the OS always works.

> 该操作系统还通过寻找大量停机时间来填充中断，从而提高多任务处理速度，从而使调度更加有效。当这段文字被输入文字处理器时，操作系统会记录并使用键入过程中的任何停顿，或者当书写者停下来思考下一步会发生什么时，它会为队列中的许多其他作业运行切片。用户可能会磨蹭，但操作系统总是能正常工作。

> [!note]
> 这一章是讲操作系统，那必然绕不开的就是中断

There are three types of interrupts to the OS:

> **操作系统有三种类型的中断：**

1. **Hardware interrupts:** Come from devices connected to the computer, such as disk drives, keyboards, network cards, etc. These interrupts alert the OS to some event, such as a key pressed on a keyboard or the movement of a mouse, or incoming data from a network. They are asking, `What do I do now?` 2. **Software interrupts:** Come from applications requesting an operation they want the OS to do, such as saving a file. 3. **Traps:** Come from the CPU and occur when it detects an error. The CPU essentially informs the OS of the error and asks for a solution.

> 1. **硬件中断：**来自连接到计算机的设备，如磁盘驱动器、键盘、网卡等。这些中断会提醒操作系统某些事件，如键盘上的按键或鼠标的移动，或来自网络的传入数据。他们在问： `我现在该做什么？`
> 2. **软件中断：**来自请求操作系统执行操作的应用程序，例如保存文件。
> 3. **陷阱：**来自 CPU，当它检测到错误时发生。CPU 本质上通知操作系统错误并请求解决方案。

Interrupts also prove useful to users in giving an application a higher priority. That means the OS runs it immediately, slowing the background processes by giving them fewer slices of time. It permits greater efficiency and flexibility.

> 事实证明，中断对于用户赋予应用程序更高的优先级也很有用。这意味着操作系统会立即运行它，从而减少后台进程的时间。它可以提高效率和灵活性。

#### Layers

Distilling an OS to its simplest form, we find four `operating` layers (refer to [Figure 8-1](#11_9781119183938-ch08.xhtml#c08-fig-0001)). For example:

> 将操作系统提炼为最简单的形式，我们可以找到四个 `操作` 层(参见[图 8-1](#11_9781119183938-ch08.xhtml#c08-fig-0001))。例如：

1. Users—mostly human but also robots, machines, programmed switches and more—input data, require steps to be executed, and save data or generate output. 2. The application responds to requests, such as saving a file, by passing it along to the OS. 3. In the layer below the application, the OS instructs the hardware to write the file and relays the result back to the application, which, for example, informs the user of a successful save. Users also may bypass the application level for direct instructions to the OS. There is a sublayer (labelled as Other System Software in [Figure 8-1](#11_9781119183938-ch08.xhtml#c08-fig-0001)) that has software such as drivers, which assist the OS. 4. At the lowest level is the hardware, the physical computer. It follows instructions from the OS and does the tasks requested—copying files, writing to disks, acknowledging interrupts, performing multitasking, etc. To be precise, the kernel performs actions. The OS, as described here, consists of more than just the kernel. You can read more about the kernel later in this chapter in the section, `[The Kernel: The Basic Facilitator of Operating Systems](#11_9781119183938-ch08.xhtml#c08-sec-0014)` .

> 1. 用户主要是人，但也包括机器人、机器、编程开关和更多输入数据，需要执行步骤，并保存数据或生成输出。
> 2. 应用程序通过将文件传递给 OS 来响应请求，例如保存文件。
> 3. 在应用程序下面的层中，OS 指示硬件写入文件，并将结果转发回应用程序，例如，应用程序通知用户成功保存。用户还可以绕过应用程序级别直接向操作系统发出指令。有一个子层(在[图 8-1](#11_9781119183938-ch08.xhtml#c08-fig-0001) 中标记为 `其他系统软件` )，该子层具有驱动程序等软件，可帮助操作系统。
> 4. 最低级别是硬件，即物理计算机。它遵循操作系统的指令，执行复制文件、写入磁盘、确认中断、执行多任务等任务。准确地说，内核执行操作。正如这里所描述的，操作系统不仅仅由内核组成。您可以在本章稍后的 `[内核：操作系统的基本指导者](#11_9781119183938-ch08.xhtml#c08-sec-0014)` 一节中阅读有关内核的更多信息。

The most important of these levels, the kernel and relevant device drivers, make the hardware useful. The OS converts expensive but totally stupid collections of electronic components into a powerful computing system that does the tasks requested of it and accomplishes useful jobs. This all due to the operating system telling these components what to do and when to do it—millions of times each second if needed.

> 这些级别中最重要的是内核和相关的设备驱动程序，使硬件变得有用。该操作系统将昂贵但完全愚蠢的电子组件集合转换为一个强大的计算系统，该系统可以完成所需的任务并完成有用的工作。这一切都是由于操作系统告诉这些组件要做什么和什么时候做，如果需要的话，每秒数百万次。

In short, the user inputs something, such as typing words into word processing software or clicking a menu choice in a spreadsheet. The application decides what to do and requests help from the OS for hardware-required operations.

> 简而言之，用户输入一些东西，例如在文字处理软件中键入单词或单击电子表格中的菜单选项。应用程序决定要做什么，并向操作系统请求硬件所需操作的帮助。

The OS allocates resources for the application’s runtime while using interrupts to cause the hardware to accomplish the desired task, accepting the result and passing it back up to the application—for example, the words typed into a new Facebook post in your browser or the flick of your wrist moving the mouse to make a game character show up on the screen.

> 操作系统为应用程序的运行时分配资源，同时使用中断使硬件完成所需的任务，接受结果并将其传回应用程序。例如，在浏览器中键入新的 Facebook 帖子中的单词，或轻击手腕移动鼠标使游戏角色出现在屏幕上。

Deep down in the kernel, interrupts make these and other actions happen. Pressing a key or moving a mouse triggers hardware interrupts. These interrupts instruct the CPU to read the keystroke or mouse position. For example, when you press A on the keyboard, a hardware interrupt causes the CPU to convert that keystroke and pass it to the current cursor position in the application. Consequently, the letter appears on the screen in the application you’re using and the cursor position moves one character space, ready to make the next input.

> 在内核深处，中断使这些和其他操作发生。按下键或移动鼠标会触发硬件中断。这些中断指示 CPU 读取键击或鼠标位置。例如，当您按下键盘上的 A 时，硬件中断会导致 CPU 转换键击并将其传递到应用程序中的当前光标位置。因此，字母出现在您正在使用的应用程序的屏幕上，光标位置移动一个字符空间，准备进行下一次输入。

Meanwhile, in the spaces of time in between requests from the user and application, the OS does a hundred other things. Remember, OSs are always doing tasks, running processes, verifying that attached peripherals are online and much, much more.

> 同时，在来自用户和应用程序的请求之间的时间间隔内，操作系统还做了许多其他事情。请记住，操作系统总是在执行任务、运行进程、验证连接的外围设备是否在线等等。

#### Computer Architecture

The hardware of a computer—its physical structure, which includes the CPU, related circuitry and attached devices—controls the design of the OS, or the system management software. A computer, in its most basic form, consists of:

> 计算机的硬件—其物理结构，包括 CPU、相关电路和连接的设备—控制操作系统或系统管理软件的设计。计算机最基本的形式包括：

- CPU (one or more and/or multicores) - Working memory, such as random access memory (RAM) - Devices as needed for storage, input and output, etc.

> -CPU(一个或多个和/或多核)-工作存储器，如随机存取存储器(RAM)-存储、输入和输出等所需的设备。

As shown in Figure 8-4, the CPU sends and receives instructions and data to and from the working memory. Devices provide to and accept from the CPU input/output requests, data and interrupts. Some devices also have direct memory access (DMA), which is a feature allowing designated hardware subsystems to access the working memory independently of the CPU.

> 如图 8-4 所示，CPU 向工作存储器发送指令和数据，并从工作存储器接收指令和数据。设备向 CPU 提供和接受输入/输出请求、数据和中断。一些设备还具有直接内存访问(DMA)，这是一种允许指定的硬件子系统独立于 CPU 访问工作内存的功能。

![[FIGURE 8-4:](#11_9781119183938-ch08.xhtml#rc08-fig-0004) Basic computer architecture](./media/images/9781119183938-fg0804.png)

The typical PC motherboard from years past included a CPU, of course, but also usually associated two additional integrated chips to the CPU, referred to as the core logic chipset*.* These two chips were the northbridge (a memory controller hub) and the southbridge (an I/O controller hub). The northbridge assisted the CPU in memory-related operations (reading, writing, etc.), whereas the southbridge handled input and output to and from the various hardware devices and ports in the computer. In short, they managed communications for the CPU.

> **当然，过去几年的典型 PC 主板包括一个 CPU，但通常也会将两个额外的集成芯片与 CPU 相连，称为核心逻辑芯片组\*。这两个芯片分别是北桥(内存控制器集线器)和南桥(I/O 控制器集线器)。北桥协助 CPU 进行与内存相关的操作(读取、写入等)，而南桥处理计算机中各种硬件设备和端口的输入和输出。简而言之，他们管理 CPU 的通信。**

> [!NOTE]
> 这个南桥和北桥的芯片就算是协处理器吗？

As CPU speeds became faster, having these operations in separate chips often caused bottlenecks. The trend in computer architecture moved to including such logic chips with the CPU in a single chip, called a system-on-a-chip (SoC). You can read more about these later in this chapter. The core logic for all Raspberry Pi models reside in their SoCs.

> 随着 CPU 速度变快，将这些操作放在单独的芯片中常常会造成瓶颈。计算机架构的趋势是将这种逻辑芯片与 CPU 集成在一个称为片上系统(SoC)的芯片中。您可以在本章稍后部分阅读有关这些的更多信息。所有树莓派模型的核心逻辑都位于其 SoC 中。

The CPU has no free will. Its marching orders come from the OS. It accepts instructions and executes them, depending on the step received, in four basic ways:

> CPU 没有自由意志。它的行军命令来自操作系统。它接受指令并根据接收的步骤以四种基本方式执行指令：

- **Arithmetic:** Adds, subtracts, multiplies, etc. and sends a result - **Logic:** Processes true, false, and, or, nor operations and sends a result - **IO:** Takes data in from `here` and puts it out to `there` or vice versa - **Control:** Tells devices what to do or enables a function depending on what devices are doing, etc.

> -**算术：**相加、相减、相乘等并发送结果**逻辑：**处理真、假、或或或或运算并发送结果**\*IO:**从 `here` 获取数据并将其输出到 `there` ，反之亦然**控制：**告诉设备要做什么或根据设备正在做什么来启用功能等。

While CPU design has changed and evolved over the past decades, basics of operation remain the same but the physical package is different from those huge old mainframes. CPUs blaze along much, much faster today and physically are a great deal smaller. These take of small, encapsulted packages are typically are called integrated circuits (ICs), usually not a lot different in size from our thumbs.

> 尽管 CPU 的设计在过去几十年中发生了变化和发展，但基本操作保持不变，但物理包与那些巨大的旧大型机不同。如今，CPU 的发展速度越来越快，而且在物理上也要小得多。这些封装的小封装通常被称为集成电路(IC)，通常大小与我们的拇指相差不大。

Additionally, the IC package probably contains other CPUs (called cores and which enable parallel processing), working memory, read only memory, device interfaces and other components of a computer system. These ICs are sometimes called SoCs, and allow sophisticated computers to be built in compact configurations, such as that smartphone in your pocket or purse, or on your belt.

> 此外，IC 封装可能包含其他 CPU(称为内核，支持并行处理)、工作存储器、只读存储器、设备接口和计算机系统的其他组件。这些集成电路有时被称为 SoC，允许将复杂的计算机构建成紧凑的配置，例如口袋、钱包或腰带上的智能手机。

The major components of a CPU are the arithmetic logic unit (ALU), the process registers (small amounts of working memory that supply input and accept output from the ALU) and the control unit, which accepts instructions from the OS. The control unit accomplishes these program steps by directing and coordinating the ALU, process registers and other components.

> CPU 的主要部件是算术逻辑单元(ALU)、处理寄存器(提供输入并接受 ALU 输出的少量工作存储器)和控制单元，后者接受操作系统的指令。控制单元通过指导和协调 ALU、过程寄存器和其他组件来完成这些程序步骤。

Getting into the structure and function of CPUs is beyond the scope of this chapter, so let’s get back on track with our discussion of OSs.

> 深入了解 CPU 的结构和功能超出了本章的范围，因此让我们回到讨论操作系统的轨道上来。

#### The Purpose of Operating Systems

Operating systems in general accomplish four major functions:

> 操作系统通常完成四个主要功能：

- **Process management:** A process is a set of instructions, which you might call a program. When it is running, the process needs certain resources allocated to it and the OS rations out those resources and controls execution of the process.
- **Memory management:** The operating system shares memory between processes, applications and various system needs, allocating memory space as needed for the current jobs. The OS also helps itself constantly to varying amounts of memory needed for performing its job. Being the boss has its benefits.
- **File system management:** Hundreds or thousands of files exist on the storage devices (hard drives mostly) of a computer with much coming and going, especially the many temporary files applications and other processes created in their normal runtimes. The OS keeps track of all the files and does its best to keep the storage medium from being corrupted by all the read and write and list calls whizzing through it.
- **Device management:** This function occurs when the OS uses system calls (a method provided for applications and other processes to interface with the OS to request hardware or other services). This might be providing access to a hard drive or giving runtime to software starting and executing a new process.

> - **流程管理：**流程是一组指令，您可以将其称为程序。当它运行时，进程需要分配给它的某些资源，操作系统分配这些资源并控制进程的执行。
> - **内存管理：**操作系统在进程、应用程序和各种系统需求之间共享内存，根据当前作业的需要分配内存空间。操作系统还不断帮助自己获得执行任务所需的不同内存量。当老板有好处。
> - **文件系统管理：**数百或数千个文件存在于计算机的存储设备(主要是硬盘驱动器)上，来来往往，特别是在正常运行时创建的许多临时文件应用程序和其他进程。操作系统会跟踪所有文件，并尽最大努力防止存储介质被快速通过的所有读写和列表调用损坏。
> - **设备管理：**当操作系统使用系统调用(一种为应用程序和其他进程提供的与操作系统接口以请求硬件或其他服务的方法)时，会出现此功能。这可能是提供对硬盘驱动器的访问，或者为启动和执行新进程的软件提供运行时。

> [!note]
> 操作系统的主要任务
> 这个四个步骤好像很熟悉？在前面介绍 pipeline 的时候也是举例 4 个步骤？！

To accomplish the four general tasks, any OS needs a host of components. We have met some of them already but now’s the time to consider the many parts under the bonnet of any good OS.

> 要完成这四项一般任务，任何操作系统都需要一系列组件。我们已经遇到了其中的一些，但现在是时候考虑任何好的操作系统背后的许多部分了。

#### Operating Systems’ Building Blocks

The building blocks of the OS are the programs, processes, subroutines, libraries and other components that allow the OS to manage the computer.

> 操作系统的构建块是允许操作系统管理计算机的程序、进程、子程序、库和其他组件。

We can break this down into four main areas that, taken together, create a powerful OS:

> 我们可以将其分为四个主要领域，共同创建一个强大的操作系统：

- **Kernel:** This program is the heart of any OS. It forms a bridge between applications and other processes, enabling and controlling the CPU and other hardware doing the actual data processing while managing and allocating the resources of memory, CPU time and everything else required for the desired result. In the next section of this chapter, we look at the kernel in detail. -
- **Networking:** Under control of the kernel is this often complex subsystem with kernel and userspace components, which provides and supports various network protocols and devices, such as Ethernet cards, and makes client/server networking possible. A client is a program that connects with another computer called a server. Most OSs’ networking facilities can run both client and server processes.
- **Security:** Keeping a computer secure in today’s environment of constant probes by those eager to take over the computer’s resources for nefarious purposes, looms large on the must-do list for any OS. The OS needs to be on constant guard and recognise bogus requests, both from outside and internal to the system. The security subsystem provides such services as authentication (usernames and passwords are one), audits, logging, permissions schemes and more.
- **User interface:** The user interface—which is most often visual but is sometime audible or in Braille for the sight impaired—lets the OS communicate results from applications to the user. In addition, the user can request services, such as file directory listings, directly from the OS. The command line—a text interface utilising typed commands—was the rule in early computing. Since Xerox’s development of the GUI and the release of the Mac OS in the early 1980s, most computer OSs today provide GUI capacities.

> - **内核：**此程序是任何操作系统的核心。它在应用程序和其他进程之间形成了一座桥梁，在管理和分配内存资源、CPU 时间和所需结果所需的所有其他资源的同时，启用和控制 CPU 和其他硬件进行实际数据处理。在本章的下一节中，我们将详细介绍内核。
> - **网络：**在内核的控制下，是一个通常具有内核和用户空间组件的复杂子系统，它提供并支持各种网络协议和设备，如以太网卡，并使客户端/服务器网络成为可能。客户端是与另一台称为服务器的计算机连接的程序。大多数操作系统的网络设施可以同时运行客户端和服务器进程。
> - **安全：**在当今的环境中，那些渴望接管计算机资源以达到邪恶目的的人不断地进行调查，确保计算机的安全，这在任何操作系统的必做事项中都显得尤为重要。操作系统需要时刻保持警惕，识别来自系统外部和内部的虚假请求。安全子系统提供身份验证(用户名和密码是一个)、审核、日志记录、权限方案等服务。
> - **用户界面：**用户界面通常是可视的，但有时对视力障碍者来说是可听的或盲文的，可以让操作系统向用户传达应用程序的结果。此外，用户可以直接从 OS 请求服务，例如文件目录列表。命令行——使用键入命令的文本界面——是早期计算中的规则。自从 20 世纪 80 年代早期 Xerox 开发了 GUI 并发布了 Mac OS 以来，如今大多数计算机操作系统都提供了 GUI 功能。

Now that we know about the history and basic parts of the OS, let’s move on to the centre of the OS: the kernel.

> 既然我们已经了解了操作系统的历史和基本部分，那么让我们进入**操作系统的核心：内核。**

## The Kernel: The Basic Facilitator of Operating Systems

Laypersons, encouraged by decades of bad science fiction, often think the CPU is a computer’s `brain` . This is far from the truth. The real boss is the OS kernel, which is software that controls the input/output requests from other software and converts them into data processing instructions that are spoon-fed to the CPU. Figure 8-5 shows how the kernel controls access to the computer’s resources.

> 受几十年糟糕科幻小说的鼓舞，外行通常认为 CPU 是计算机的 `大脑` 。这与事实相去甚远。真正的老板是 OS 内核，它是一种控制来自其他软件的输入/输出请求并将其转换为数据处理指令的软件，这些数据处理指令通过勺子传送给 CPU。图 8-5 显示了内核如何控制对计算机资源的访问。

![[FIGURE 8-5:](#11_9781119183938-ch08.xhtml#rc08-fig-0005) The kernel controls access to and from the computer’s resources.](./media/images/9781119183938-fg0805.png)

The kernel also performs the magic of multitasking. Multitasking occurs when the OS employs interrupts to `slice` CPU time into bits for each running process, which essentially allows scores—or even hundreds—of processes, applications and requests from multiple users to run at the same time. This is aided by the kernel drivers, which are small programs sitting somewhere between the kernel and applications. The kernel drivers sort of act as both a glue that holds together the system operation-wise and a communication enabler that makes sure processes talk with the OS and get controlled by it.

> 内核还具有多任务处理的魔力。当操作系统使用中断将 CPU 时间 `切片` 为每个运行进程的位时，就会出现多任务处理，这基本上允许多个用户同时运行数十个甚至数百个进程、应用程序和请求。内核驱动程序有助于这一点，内核驱动程序是位于内核和应用程序之间的小程序。内核驱动程序有点像是一种粘合剂，它将系统操作方式结合在一起，同时也是一种通信使能器，它确保进程与操作系统对话并受其控制。

Today’s multicore CPUs up the ante, so to speak. Instead of time slicing one CPU, a multicore CPU has several CPUs (the Raspberry Pi 2 has four). Thus tasks can be divided, with parts of the task processing in parallel for greater speed (the big advantage of a multicore CPU). Doing this requires a property in the programming of processes that in modern data processing is termed _concurrency_.

> 可以这么说，今天的多核 CPU 已经大放异彩了。多核 CPU 有几个 CPU(树莓派 2 有四个)，而不是对一个 CPU 进行时间切片。因此，**任务可以被划分，部分任务处理并行以获得更高的速度(多核 CPU 的最大优势)。要做到这一点，需要在进程编程中具有一个在现代数据处理中称为 *concurrency* 的属性。**

Concurrency and parallel processing uses various methods beyond the scope of this book to explain—such as Petri nets, process calculi, the Parallel Random Access Machine model, the Actor model and the Reo Coordination language—in giving the operating system additional scope and power. The result of these methods in processes generated by programs, algorithms and so on, is to break tasks into parts (decomposability), which are acted on simultaneously by the cores (parallelism) and then the results are reconstituted.

> 并发和并行处理使用了超出本书范围的各种方法来解释，例如 Petri 网、过程演算、并行随机访问机模型、Actor 模型和 Reo 协调语言，以赋予操作系统更多的范围和功能。在程序、算法等生成的过程中，这些方法的结果是将任务分解为多个部分(可分解性)，这些部分由内核同时作用(并行性)，然后重新构建结果。

Here’s a simple analogy: you have a stack of four white cards, which you want respectively coloured red, green, blue, and yellow. You could hand the stack of cards to a guy sitting at a table with four markers, and get him to colour each card, one at a time, and stack each one as he finishes it on the other side of the table. It would take a while.

> 这里有一个简单的类比：你有一堆四张白色的卡片，你想要分别涂上红、绿、蓝和黄。你可以把这一叠卡片交给一个坐在桌子旁的人，让他用四个记号笔给每张卡片上色，一次一张，当他在桌子的另一边完成时，把每张卡片叠起来。这需要一段时间。

Alternatively, you could have three guys and a gal at the table. You hand one card to each person. They each colour a card and place it in the stack. Your processing now takes a quarter of the time. That’s a good congruency of parallelism.

> 或者，你可以有三个男人和一个女孩在桌上。你给每个人一张卡片。他们每人给一张卡片上色，然后把它放在卡片叠里。您的处理现在需要四分之一的时间。这是一种很好的一致性。

The OS does tasks like parallel processing while also managing file systems, memory allocation and so on. The Raspberry Pi’s OS kernel provides this multitasking just like on much larger computers. In this section, we also look at the ways in which computer architecture influences kernel design.

> 该操作系统执行并行处理等任务，同时还管理文件系统、内存分配等。Raspberry Pi 的操作系统内核提供这种多任务处理，就像在更大的计算机上一样。在本节中，我们还将探讨计算机体系结构影响内核设计的方式。

An OS kernel consists of a collection of programs (components) grouped into various subsystems, which run processes as needed to fill the various managerial tasks of the OS. The next sections explore the components of modern OSs designed for the architecture of small computers. Or, in the case of the Raspberry Pi, a tiny powerhouse fitting in the palm of your hand.

> 操作系统内核由一组程序(组件)组成，这些程序被分为不同的子系统，这些子系统根据需要运行进程，以完成操作系统的各种管理任务。下一节将探讨为小型计算机架构设计的现代操作系统的组件。或者，在树莓派的例子中，一个小小的发电站就在你的手掌中。

### Operating System Control

We have discussed multitasking several times already, where the OS allocates slices of time to applications and other processes. The result, at computer speed, achieves what appears to be simultaneous execution of many programs. That’s part of program execution.

> 我们已经多次讨论了多任务处理，其中操作系统将时间片段分配给应用程序和其他进程。结果，在计算机速度下，实现了许多程序的同时执行。这是程序执行的一部分。

The OS is made up of many small programs, so it also takes a share of CPU cycles for its own use. These small programs, when running, comprise processes needed by the OS in its ongoing business of managing the computer.

> 操作系统由许多小程序组成，因此它也会占用 CPU 周期的一部分供自己使用。这些小程序在运行时，包括操作系统在其管理计算机的持续业务中所需的过程。

Figure 8-6 shows a screen capture of some of the processes running on a Raspberry Pi 2 Model B after boot-up. The figure shows the command-line interfaces via Secure Shell (SSH) from a Windows computer. The Raspberry Pi’s Raspbian OS, just after booting up, already runs 117 processes.

> 图 8-6 显示了启动后 Raspberry Pi 2 Model B 上运行的一些进程的屏幕截图。该图显示了从 Windows 计算机通过 Secure Shell(SSH)的命令行界面。Raspberry Pi 的 Raspbian OS 在启动后已经运行了 117 个进程。

![[FIGURE 8-6:](#11_9781119183938-ch08.xhtml#rc08-fig-0006) Multitasking allows the running of many tasks.](./media/images/9781119183938-fg0806.png)

A lot of behind-the-scenes activity goes on deep down in the OS of any computer. Some of these processes run permanently after the computer boots. One such process, used in most Linux-based OSs including several available for the Raspberry Pi, is cron. Cron got its name from the word chronological, meaning `in order of time` . When you need a backup of your files every Friday at 3am, cron makes it happen.

> 任何计算机的操作系统都有很多幕后活动。其中一些进程在计算机启动后永久运行。在大多数基于 Linux 的操作系统中使用的一个这样的过程是 cron，其中包括树莓派(Raspberry Pi)的几个操作系统。Cron 的名字来源于单词 chronical，意思是 `按时间顺序` 。当您需要在每周五凌晨 3 点备份文件时，cron 会帮您做到这一点。

Other processes come and go as needed. Computers may look idle when they are not in use but in actuality, scores of little programs are whizzing data around as the OS goes about its duties.

> 其他流程根据需要来来去去。计算机在不使用时可能看起来很空闲，但实际上，随着操作系统执行其任务，许多小程序正在快速传输数据。

### Modes

Walk into any large office building and you will find many places you cannot enter or where entry requires special permission. Such places have locked or guarded doors and sensitive areas protected by carefully controlled access. On a computer, this analogy correlates to file and program permissions. The OS controls which users can access which files and run which programs.

> 走进任何一栋大型办公楼，你都会发现许多你无法进入的地方，或者需要特别许可才能进入的地方。此类场所设有上锁或有人看守的门和敏感区域，并通过仔细控制的通道进行保护。在计算机上，这种类比与文件和程序权限相关。操作系统控制哪些用户可以访问哪些文件和运行哪些程序。

Modes carry security a step further and at a much lower level. They are more like secret vaults in a basement sublevel that’s so secret that no one knows it exists. CPUs today give us several modes of operation. Two of these, supervisor mode and protected mode, facilitate immense power for the OS.

> 模式将安全性提升了一步，而且级别要低得多。它们更像地下室地下室的秘密金库，秘密到无人知晓。今天，CPU 为我们提供了几种操作模式。其中两种模式，监管模式和保护模式，为操作系统提供了巨大的能量。

Operating systems use the all-powerful supervisor mode sparingly. However, one time when the supervisor mode runs without governance from the OS occurs during the boot process. Because it’s not awake yet, the OS has no control. In fact, the initial programs when a computer powers up, like the bootloader routine, must have unfettered access to hardware. The capability of a CPU running in protected mode can be set up only with supervisor mode.

> 操作系统很少使用全功能管理器模式。然而，在引导过程中，有一次在没有来自 OS 的管理的情况下运行管理器模式。因为它还没有醒来，所以操作系统无法控制。事实上，计算机启动时的初始程序，如引导加载程序，必须能够不受限制地访问硬件。在保护模式下运行的 CPU 的功能只能通过监控器模式进行设置。

After the OS comes alive, it places the CPU into protected mode. The protected mode is restricted to a limited set of possible CPU instructions, preventing all programs from mucking about with the hardware. At almost all times, the OS enforces protected mode on applications and even its own processes.

> 操作系统启动后，它将 CPU 置于保护模式。保护模式仅限于有限的 CPU 指令集，防止所有程序干扰硬件。几乎在任何时候，操作系统都会对应用程序甚至其自己的进程强制执行保护模式。

When the OS allows the CPU to run in kernel mode, the steps executed have unlimited direct access to all the hardware. The OS opens this gate wide when certain tasks that need unrestricted access run. Handling how processes write to memory or erase (clean up after itself) are a good example. Both of these types of operation require care. Mess up the working memory, and processes can crash all over the place, which can bring down the computer entirely. Glitch the display even slightly and it blanks or locks, leaving users locked out, unable to use their application.

> **当操作系统允许 CPU 以内核模式运行时，执行的步骤可以无限制地直接访问所有硬件**。当某些需要无限制访问的任务运行时，操作系统会打开此门。处理进程如何写入内存或擦除(自行清理)就是一个很好的例子。这两种操作都需要小心。扰乱工作内存，进程可能到处崩溃，这可能会使计算机完全崩溃。即使稍微闪烁一下屏幕，它也会变为空白或锁定，从而导致用户被锁定，无法使用他们的应用程序。

Of course, applications do often need access to hardware for memory manipulations and updating the screen via its graphic card. The program calls for this by triggering an interrupt, which was discussed earlier in this chapter. The OS kernel takes the CPU out of protected mode for the application while maintaining control over its access.

> 当然，应用程序通常需要访问硬件进行内存操作，并通过图形卡更新屏幕。程序通过触发一个中断来调用它，这在本章前面已经讨论过了。OS 内核使 CPU 退出应用程序的保护模式，同时保持对其访问的控制。

Ah, but what if the application commits an error while in either supervisor mode or protected mode? There are usually CPU `protected mode resource` registers with data the program does not have authority to change. If it tries, the OS uses supervisor mode to prevent a crash, usually by killing the application or other process.

> 啊，但是如果应用程序在监控模式或保护模式下发生错误呢？通常有 CPU `保护模式资源` 寄存器，其中包含程序无权更改的数据。如果尝试了，操作系统将使用监督模式来防止崩溃，通常通过终止应用程序或其他进程。

### Memory Management

One of the kernel’s main functions lies in allocating memory resources. Every one of the processes and programs running in the computer reside in the working memory and use even more of it for manipulating data. The OS performs a complex dance for keeping all these processes from overwriting each other.

> 内核的主要功能之一在于分配内存资源。计算机中运行的每一个进程和程序都驻留在工作内存中，并使用更多的内存来处理数据。操作系统执行复杂的舞蹈，以防止所有这些进程相互覆盖。

Remember those protected mode registers in the CPU that we described in the previous section about modes? This provides one of the several methods by which the kernel limits a memory-hungry process from taking up too many memory locations and possibly causing a crash. Others include memory segmentation and paging—hardware-dependent techniques aiding in memory control and allocation.

> 还记得我们在上一节中描述的 CPU 中的受保护模式寄存器吗？这提供了几种方法中的一种，通过这些方法，内核可以限制内存不足的进程占用太多内存位置，并可能导致崩溃。其他包括内存分割和分页硬件相关技术，这些技术有助于内存控制和分配。

### Virtual Memory

On older submarines with limited space, such as those during World War II, sailors used the `hot bunk` or `hot rack` system. A bed was assigned to more than one sailor, all on different shifts, with one sleeping while the others were on duty — thus allowing the vessel carrying two or three times the crew limited sleeping facilities would otherwise dictate.

> 在空间有限的老式潜艇上，如二战期间的潜艇，水手们使用 `热铺位` 或 `热架` 系统。一张床被分配给一名以上的船员，所有人都在不同的班次，一人睡觉，而其他人在值班，因此这艘船可以承载两三倍于船员有限的睡眠设施。

Virtual memory techniques control which memory locations process access at any given time. Therefore, the kernel uses the same memory address for several processes, just not at exactly the same time. So, under OS control, computers effectively have several times their actual physical memory available to run programs.

> 虚拟内存技术控制在任何给定时间处理访问的内存位置。因此，内核对多个进程使用相同的内存地址，只是不是同时使用。因此，在操作系统的控制下，计算机实际上有几倍于其实际物理内存可用于运行程序。

Often even efficiently employing the same memory addresses for different programs does not meet demand. The kernel then adds more memory space by moving lesser-used memory into a file (called a swap file) on a disk drive. If a process calls for data in memory in the swap file, the kernel brings it back into working memory, moving something else out, if need be.

> 通常，即使对不同的程序有效地使用相同的存储器地址也不能满足需求。然后，内核通过将较少使用的内存移动到磁盘驱动器上的文件(称为交换文件)中来添加更多内存空间。如果进程在交换文件中调用内存中的数据，内核会将其带回工作内存，并在需要时将其他数据移出。

Again, virtual memory techniques cause the working memory to look a lot larger than it really is, to both programs and users.

> 同样，对于程序和用户来说，虚拟内存技术使工作内存看起来比实际大得多。

Another, arguably even more important, use takes care of fragmentation, which means that the OS stores parts of processes and data wherever empty memory locations exist. When a computer is running lots of concurrent processes with data coming and going, expanding and contracting, stuff is soon broken up and stuffed into memory locations all over the place (or fragmented). Virtual memory keeps this reality transparent to programs, and they continue to operate as if all parts were in adjacent memory slots.

> 另一种可能更重要的用法是处理碎片，这意味着操作系统在存在空内存位置的地方存储部分进程和数据。当一台计算机运行大量并发进程，数据来来往往，不断扩展和收缩时，这些数据很快就会被分解，并填充到各地的内存位置(或碎片化)。虚拟内存使这种现实对程序透明，它们继续运行，就像所有部件都在相邻的内存插槽中一样。

Speaking of the kernel doing all these time-slicing and virtual-memory tricks, it’s time we looked at multitasking again.

> 说到内核执行所有这些时间切片和虚拟内存技巧，是时候我们再次研究多任务了。

### Multitasking

In sleight-of-hand tricks with playing cards, one of the basic secrets is a move called the `back palm` . A magician holds a card up to the audience. He makes a motion and it disappears. He shows you the back of his hand, sliding the card into a `front palm` so it remains hidden. Turning his hand around, he produces the card seemingly out of thin air. Or he might start with several cards in his back palm, producing them one at a time in a rain of cards from apparently nowhere. Numerous YouTube videos give tutorials on how this sleight of hand works.

> 在玩纸牌的花招中，一个基本的秘密是一个叫做 `后掌` 的动作。魔术师向观众举起一张卡片。他做了一个动作，它消失了。他向你展示他的手背，将卡片滑入 `前手掌` ，使其保持隐藏状态。他转过身来，似乎凭空拿出了那张卡片。或者，他可能会先在后掌上放几张牌，然后在一大堆显然不知从何而来的牌中一张一张地打出。YouTube 上有很多视频提供了有关这种手法的教程。

If you practice the simple moves and do it fast, it truly looks like magic. That’s how multitasking works. The OS kernel moves program steps and memory allocations in and out of sight so fast it looks like magic. Hundreds of things seem to be happening simultaneously—which, of course, they are.

> 如果你练习简单的动作并快速完成，它看起来真的很神奇。这就是多任务工作的原理。OS 内核将程序步骤和内存分配移入移出视线的速度如此之快，看起来就像是魔术。成百上千的事情似乎同时发生，当然，事实确实如此。

Again, time slicing is the trick. The kernel has a scheduling program that decides the amount of CPU time a program gets as well as its priority. If the CPU has multiple cores, the use of concurrency, as we saw earlier, to achieve parallel processing comes into play as well. With this scheduling program, the kernel controls every process’s ration of CPU time and amount of memory access.

> 同样，**时间切片是诀窍。内核有一个调度程序，它决定程序获得的 CPU 时间及其优先级。如果 CPU 有多个内核，那么使用并发(正如我们前面所看到的)来实现并行处理也会发挥作用。通过这个调度程序，内核控制每个进程的 CPU 时间和内存访问量。**

### Disk Access and File Systems

Just as the kernel controls the amount of memory `real estate` , a process can occupy in working memory, the same holds true for storage. The main method of storage in modern computers is hard disks, either the old spinning disk or solid-state flash memory drives.

> 正如内核控制内存量 `不动产` 一样，进程可以占用工作内存，存储也是如此。现代计算机中的主要存储方法是硬盘，既可以是旧的旋转磁盘，也可以是固态闪存驱动器。

Data is stored on media such as hard drives in files. A computer file holds some similarity (which inspired the name) to paper file folders and their contents. Instead of paper, the information in a computer file consists of binary ones and zeros written magnetically on media such as hard drives or electrically like on SSDs.

> 数据存储在文件中的硬盘等介质上。计算机文件与纸质文件夹及其内容有一定的相似性(这就是它的名字)。计算机文件中的信息由二进制的 1 和 0 组成，它们以磁方式写入硬盘驱动器等介质中，或以电方式写入 SSD 中，而不是纸质文件。

The OS organises the binary information into an array of a manageable format (called a `file` ), allowing the OS to write, retrieve and manage the available space for other files. The scheme used for file manipulation is a file system (an organized collection of many hundreds or thousands of files). The OS then controls finding, reading and writing of these files as required by applications.

> 操作系统将二进制信息组织成可管理格式的数组(称为 `文件` )，允许操作系统写入、检索和管理其他文件的可用空间。用于文件操作的方案是文件系统(数百或数千个文件的有组织的集合)。然后，操作系统根据应用程序的需要控制这些文件的查找、读取和写入。

The old, often-used analogy comparing file systems to a physical office file cabinet has some validity. The file system equals the cabinet. Drawers are directories and file folders are the files. However, to make this analogy hold up for modern file systems, you need a file cabinet that has drawers within drawers. In addition, the filing cabinet would know where each and every file was, what was in it, who had permission to read it, and how much space was left in the cabinet, and the cabinet would do all this while spinning at 7,200 rpm.

> 将文件系统与物理办公室文件柜进行比较是一种古老的、经常使用的类比，这种类比具有一定的有效性。文件系统等于文件柜。抽屉是目录，文件夹是文件。然而，为了使这种类比适用于现代文件系统，您需要一个抽屉内有抽屉的文件柜。此外，文件柜会知道每个文件的位置、里面有什么、谁有权阅读文件以及文件柜中还有多少空间，而文件柜会在以 7200 rpm 的转速旋转时完成所有这些工作。

Numerous types of file system exist. Many of the current OSs can read and manage several types at the same time. For example, when you mount an external drive formatted under Windows to a Linux machine, the OS manages the Windows file system in parallel with the Linux file system.

> 存在多种类型的文件系统。当前的许多操作系统可以同时读取和管理多种类型。例如，当您将在 Windows 下格式化的外部驱动器装载到 Linux 计算机时，操作系统将与 Linux 文件系统并行管理 Windows 文件系统。

### Device Drivers

The usefulness of a computer depends on input of data and output of answers. Fulfilling this need for millions of applications on millions of computers results in millions of peripherals developed and sold. A peripheral can be any hardware device installed in or attached to a computer for the purpose of input and/or output. Printers, speakers, keyboards, various mouse-like pointer devices, external disc drives, keyboards, USB gadgets, and so forth, all fall into the peripheral category.

> 计算机的有用性取决于数据的输入和答案的输出。在数百万台计算机上满足数百万应用程序的需求，结果开发和销售了数百万台外围设备。外围设备可以是安装在计算机中或连接到计算机以用于输入和/或输出的任何硬件设备。打印机、扬声器、键盘、各种类似鼠标的指针设备、外部磁盘驱动器、键盘、USB 小工具等等都属于外围设备。

If an OS contained routines for every possible peripheral that currently exists or will come into existence in the next ten years—even narrowing it down to only those from this country or that—the OS would require a hard drive the size of Wales just to store itself. Drivers are a simple but quite elegant solution to this issue.

> 如果一个操作系统包含当前存在或未来十年内将出现的所有可能外设的例程，甚至将其缩小到仅来自该国的例程，或者该操作系统需要一个威尔士大小的硬盘来存储自己。驱动程序是解决这个问题的简单但相当优雅的解决方案。

Most peripherals have small programs specifically written for an OS; these small programs are called drivers. When installed, a driver shows the OS what the device can do and translates OS instructions for the peripheral, enabling the printer to be a printer, the speaker to play audio files, and so on.

> 大多数外设都有专门为操作系统编写的小程序；这些小程序称为驱动程序。安装后，驱动程序向操作系统显示设备可以执行的操作，并翻译外围设备的操作系统指令，使打印机成为打印机，扬声器播放音频文件，等等。

Now you’ve had a brief introduction to what an OS kernel does and how it does it. Next, we see how the OS enables applications in using hardware resources.

> 现在，您已经简单介绍了 OS 内核的功能以及它是如何实现的。接下来，我们将了解 OS 如何支持应用程序使用硬件资源。

## Enablers and Assistants to the Operating System

The OS uses device drivers to assist with input and output, but other programs assist the OS as well. This section delves into the booting procedure (booting or boot-up occurs when the computer powers up), firmware (hardware-specific programs to assist the OS), and finally more detail about how the OS manages memory and storage.

> 操作系统使用设备驱动程序辅助输入和输出，但其他程序也辅助操作系统。**本节将深入探讨引导过程(计算机通电时启动或启动)、固件(帮助操作系统的硬件特定程序)，以及操作系统如何管理内存和存储的更多细节**。

### Waking Up the OS

Push a computer’s power switch to the On position and it begins waking up (booting). The term booting derives from the old cliché of pulling yourself up by your bootstraps. Bootstrapping, in its original usage, meant someone trying to achieve an impossible task. In the case of a computer, an OS readying a computer for practical use seems impossible because the OS is not even there yet—it’s just on a file on a hard drive or other memory storage device. Something has to wake the boss.

> 将电脑的电源开关推到 `打开` 位置，电脑开始唤醒(启动)。 `引导` 一词源于一句老生常谈的话，那就是靠自己的引导来提升自己。在最初的用法中，引导意味着有人试图完成一项不可能的任务。在计算机的情况下，一个操作系统为计算机准备实际使用似乎是不可能的，因为该操作系统甚至还不存在，它只是在硬盘驱动器或其他内存存储设备上的文件上。一定有什么事情要唤醒老板。

#### Booting in General

In modern computers, the something that wakes the OS consists of a `bootloader` (or `bootstrap loader` ), a small program stored on read-only memory (ROM). The loader runs automatically on power-up, setting up access and providing some bits of necessary data so the OS’s programs get loaded into working memory and executed.

> 在现代计算机中，唤醒操作系统的东西由 `引导加载程序` (或 `引导加载` )组成，这是一个存储在只读存储器(ROM)上的小程序。**加载程序在通电时自动运行**，设置访问并提供一些必要的数据，以便将操作系统的程序加载到工作内存中并执行。

The ROM containing the loader and other information about the computer is often Basic Input/Output System (BIOS). BIOS performs hardware initialisation whenever the computer boots. Newer computers have a replacement for BIOS called Unified Extensible Firmware interface (UEFI). Both BIOS and UEFI are firmware—small programs specific to the hardware and embedded via permanent memory, such as ROM, erasable, reprogrammable read-only memory (EPROM), or flash memory. You can read more about firmware later in this section.

> 包含加载程序和有关计算机的其他信息的 ROM 通常是基本输入/输出系统(BIOS)。每当计算机启动时，BIOS 都会执行硬件初始化。较新的计算机有一种称为统一可扩展固件接口(UEFI)的 BIOS 替代品。BIOS 和 UEFI 都是特定于硬件的固件小程序，并通过永久存储器(如 ROM、可擦除、可编程只读存储器(EPROM)或闪存)嵌入。您可以在本节稍后阅读有关固件的更多信息。

The sequence of booting usually goes something like this:

> **引导的顺序通常如下：**

1. When power is applied to the BIOS or UEFI chip, diagnostics run (to make sure the hardware is okay), components get initialised (for example, disk drives spin up) and the bootstrap program is started. 2. The loader loads the OS into working memory from storage and starts it. 3. The OS creates data structures in working memory, sets needed registers in the CPU and starts a user-level program. From then on, the OS accepts interrupts and the computer is open for business.

> 1.当 BIOS 或 UEFI 芯片通电时，诊断运行(以确保硬件正常)，初始化组件(例如，磁盘驱动器启动)，启动引导程序。2.加载器将操作系统从存储器加载到工作内存中并启动它。操作系统在工作内存中创建数据结构，在 CPU 中设置所需的寄存器，并启动用户级程序。从那时起，操作系统接受中断，计算机开始营业。

These steps outline booting in general terms. Two additional methods of booting, the first more often used, also need mentioning.

> 这些步骤概括介绍了引导。另外两种引导方法，第一种更常用，也需要提及。

#### Second-Stage Boot Loaders

Bootstrap programs have limitations, one of which derives from the relatively small amount of storage space on ROMs. Therefore, when requirements call for a more sophisticated booting process, a two-stage loader provides the solution. It is a simple concept with the following payoffs:

> 引导程序有局限性，其中一个局限性来自 ROM 上相对较少的存储空间。因此，当需求**需要更复杂的引导过程时，两阶段加载程序提供了解决方案**。这是一个简单的概念，有以下好处：

- The limited bootstrap program loads a more advanced `second-stage` loader from disk into working memory. The new loader has additional features and power, resulting in more options. One such is the ability to configure the loader for things like choosing which of two or more OSs to load.

> -有限的引导程序将更高级的 `第二阶段` 加载程序从磁盘加载到工作内存中。新的装载机具有额外的功能和动力，从而提供了更多的选择。其中之一就是能够配置加载器，以便选择加载两个或多个操作系统中的哪一个。

For example, a dual-boot PC that uses this method gives the user the choice of running Windows or a Linux distro. Other choices might be booting into a safe or rescue mode, or even booting into a basic shell provided by the second-stage loader.

> 例如，使用这种方法的双引导 PC 可以让用户选择运行 Windows 或 Linux 发行版。其他选择可能是引导到安全或救援模式，或者甚至引导到第二阶段加载器提供的基本 shell。

A widely used second-stage loader is GRand Unified Bootloader (GNU GRUB), from the GNU Project and the Free Software Foundation. GRUB assists the boot process in most Linux OSs. GRUB includes shell capacity, allowing low-level operations before the OS gets loaded; sometimes this is exceptionally useful in rescuing a system that no longer brings up the OS. To expand on all this, as we’ll see shortly in the Raspberry Pi’s boot sequence, sometimes a third-stage loader gives booting even more power.

> 一个广泛使用的第二阶段加载器是来自 GNU 项目和自由软件基金会的 GRand Unified Bootloader(GNUGRUB)。GRUB 在大多数 Linux 操作系统中协助引导过程。GRUB 包括 shell 容量，允许在加载操作系统之前进行低级操作；有时这在挽救不再启动 OS 的系统时非常有用。为了扩展这一切，正如我们将在 Raspberry Pi 的引导序列中看到的那样，有时第三阶段加载程序会提供更多的引导功能。

- The second-stage loader also facilitates network booting, which is explained in the next section.

> -第二阶段加载器也有助于网络引导，这将在下一节中解释。

#### Network Booting

A second-stage loader, with its larger and more complex program, can include the capacity of booting from a network. This eliminates the need for a hard drive on the local computer, which is handy for small, embedded computers in machinery, appliances and other uses.

> 第二阶段加载程序具有更大、更复杂的程序，可以包括从网络启动的能力。这**消除了本地计算机上对硬盘驱动器的需求**，这对于小型嵌入式计算机在机械、电器和其他用途中非常方便。

In addition, network booting simplifies the job of IT managers responsible for hundreds or thousands of computers in a company. If every computer on the network boots from the same copy of the OS, keeping that one OS updated with all the latest security and other upgrades is a breeze.

> 此外，网络引导简化了负责公司数百或数千台计算机的 IT 经理的工作。如果网络上的每台计算机都是从同一个操作系统的副本启动的，那么用所有最新的安全和其他升级来更新该操作系统是轻而易举的。

In network booting, the second-stage boot loader accesses the OS copy stored on a network drive with simple protocols provided from ROM. It then transfers the necessary parts to the local computer’s working memory for the OS to finish loading itself and start.

> 在网络引导中，第二阶段引导加载程序使用 ROM 提供的简单协议访问存储在网络驱动器上的 OS 副本。然后将必要的部分传输到本地计算机的工作存储器，以便 OS 完成自身加载并启动。

Now, let us get specific with the Raspberry Pi.

> 现在，让我们具体谈谈树莓派。

#### Booting the Raspberry Pi

The computer architecture of a single-board computer like the Raspberry Pi certainly affects its design. However, the boot process still follows the general precepts we have already seen, with some compromises.

> 像树莓派这样的单板计算机的计算机架构肯定会影响其设计。然而，引导过程仍然遵循我们已经看到的一般规则，并有一些妥协。

One compromise—for cost and space reduction—involves not including separate non-volatile memory (ROMs, flash memory, etc.). The Raspberry Pi still needs some sort of bootstrap program, however. The design accomplishes this by using the SoC described earlier in this chapter. The SoC is an integrated circuit, which contains the CPU and other components. One of those `other components` entails a small amount of ROM.

> 降低成本和空间的一个折衷方案是不包括单独的非易失性存储器(ROM、闪存等)。然而，树莓派仍需要某种引导程序。该设计通过使用本章前面描述的 SoC 来实现这一点。SoC 是一个集成电路，包含 CPU 和其他组件。其中一个 `其他组件` 需要少量 ROM。

Many things happen during booting. Figure 8-7 shows a Raspberry Pi 2 booting, and you can see all the processes being set up, configured and tested.

> 在引导过程中会发生很多事情。图 8-7 显示了 Raspberry Pi 2 引导，您可以看到正在设置、配置和测试的所有进程。

![[FIGURE 8-7:](#11_9781119183938-ch08.xhtml#rc08-fig-0007) Detail of Raspberry Pi 2 screen messages during booting](./media/images/9781119183938-fg0807.png)

On the Raspberry Pi 3, we get four cores in the CPUs running at 1.2 Ghz. During normal operation—that is, after the OS has taken charge—the GPU drives the display, if present. However, during booting, it plays another role.

> 在 Raspberry Pi 3 上，我们的 CPU 有四个内核，运行频率为 1.2 Ghz。在正常操作期间，即操作系统充电后，GPU 驱动显示器(如果存在)。然而，在引导过程中，它扮演另一个角色。

The CPUs used on all Raspberry Pi boards are ARM-designed. When powered up, the boot process then begins, and proceeds like this:

> 所有 Raspberry Pi 板上使用的 CPU 都是 ARM 设计的。通电后，启动过程开始，并按如下方式进行：

1. The Raspberry Pi’s design has the GPU on when the board powers up—the ARM core(s) remain off. 2. The GPU executes the first stage boot loader from ROM on the SoC. 3. The first stage reads the SD or (on newer models) the microSD card, and loads `bootcode.bin`, the second-stage boot loader, for whatever OS is on the card, into the L2 cache (caches being areas of very fast memory available to CPUs or, here, the GPU) and executes it. 4. Next, `bootcode.bin` turns on SDRAM (the separate memory chip physically stacked on top of the SoC), loads the third-stage program—`loader.bin`—and starts it. 5. `loader.bin` reads `start.elf,` the GPU’s firmware (which is covered in the next section). 6. `start.elf` reads `config.txt`, `cmdline.txt` and `kernel.img`, and starts the OS (this refers to a Linux-based OS such as Raspbian, and is not necessarily valid for any other type of OS).

> 1.树莓派的设计在板通电时打开 GPU，ARM 内核保持关闭。GPU 从 SoC3 上的 **ROM 执行第一阶段引导加载程序**。第一阶段读取 SD 或(在较新型号上)microSD 卡，并将 `bootcode.bin` (第二阶段引导加载器)加载到二级缓存中(缓存是 CPU 或 GPU 可用的非常快的内存区域)，然后执行它。接下来，`bootcode.bin` 打开 SDRAM(物理上堆叠在 SoC 顶部的独立存储芯片)，加载第三阶段程序 `loader.bin` 并启动它 `loader.bin ` 读取 `start.elf` GPU 的固件(将在下一节中介绍)。6. `start.elf` 读取 `config.txt` 、 `cmdline.txt` 和 `kernel.img` ，并启动操作系统(这是指基于 Linux 的操作系统，如 Raspbian，不一定适用于任何其他类型的操作系统)。

> [!note]
> 系统启动过程

Which OS gets started by this booting procedure runs on your Raspberry Pi when power is applied. There are a growing number of choices. We look at these in the final section of this chapter. Before that, a brief look at firmware will be beneficial.

> 当电源接通时，哪个操作系统通过此引导程序启动，并在 Raspberry Pi 上运行。有越来越多的选择。我们将在本章的最后一节讨论这些问题。在此之前，简单了解一下固件将是有益的。

---

> [!NOTE]

ARM (ARM Holding plc) is a British multinational semiconductor and software company. Its main business consists of researching and designing power-efficient CPUs often used in smartphones, tablets and single-board computers such as the Raspberry Pi. The company licenses its designs to other manufacturers.

> ARM(ARM Holding plc)是一家英国跨国半导体和软件公司。其主要业务包括研究和设计智能手机、平板电脑和单板电脑(如 Raspberry Pi)中常用的节能 CPU。该公司将其设计许可给其他制造商。

### Firmware

Software design for control, monitoring and various types of data manipulation embedded in a device on non-volatile memory (ROM, flash, and so on) is called firmware. Firmware controls or assists in a wide range of devices today. These include phones, cameras, watches, thermostats, refrigerators, stoves and, of course, computers. Almost all digital things have some sort of firmware installed.

> 用于控制、监控和**嵌入非易失性存储器(ROM、闪存等)设备中的各种数据处理的软件设计称为固件**。目前，固件控制或协助各种设备。其中包括手机、相机、手表、恒温器、冰箱、炉灶，当然还有电脑。几乎所有的数字设备都安装了某种固件。

The firmware in some devices has no provision for updates and is truly permanent for the life of the device. It’s hard, for example, to envision upgrading the firmware in a cheap digital watch from the local discount store. It is what it is. Keeping firmware current in other devices, especially computers, is possible and even desirable.

> 某些设备中的固件没有更新规定，并且在设备的使用寿命内是永久的。例如，很难想象从当地折扣店升级廉价数字手表的固件。保持其他设备，尤其是计算机的固件最新是可能的，甚至是可取的。

Upgrading the BIOS or UEFI in a computer sometimes requires a bit of effort. To update it manually, you must find the manufacturer of the software, which resides on an EPROM in your device. Then you secure a utility program that allows you to flash (erase and rewrite) the replacement code onto the EPROM. This process is a pain and creates some danger of erasing the BIOS or UEFI instead of rewriting it. In modern computers and other devices featuring firmware updates, the manufacturers often supply automated procedures for downloading and upgrading.

> 升级计算机中的 BIOS 或 UEFI 有时需要一些努力。要手动更新，您必须找到软件的制造商，该软件位于设备中的 EPROM 上。然后，您可以保护一个实用程序，该程序允许您将替换代码闪存(擦除和重写)到 EPROM 上。这个过程是一个痛苦的过程，并且会产生擦除 BIOS 或 UEFI 而不是重写它的危险。在现代计算机和其他具有固件更新功能的设备中，制造商通常会提供下载和升级的自动化程序。

Many operating systems, including Raspbian, handle the details of application, OS and firmware updates for us. However, you often must manually enter a command for this to occur, instructing the OS to check online software depositories, download the updates available and install those updates. This is something you should do often to maintain the security of you system, apply bug fixes and add new features. If running Raspbian, the most popular Linux OS on the Raspberry Pi, enter the following command on the command line to update:

> 包括 Raspbian 在内的许多操作系统为我们处理应用程序、操作系统和固件更新的详细信息。然而，您通常必须手动输入命令才能执行此操作，指示操作系统检查在线软件存储库，下载可用的更新并安装这些更新。这是您应该经常做的事情，以维护系统的安全性，应用错误修复并添加新功能。如果在 Raspberry Pi 上运行最流行的 Linux 操作系统 Raspbian，请在命令行中输入以下命令进行更新：

```
sudo apt-get update && sudo apt-get upgrade
```

The first half of the preceding command tells the OS to search the appropriate repositories and download updates. The second orders it to install those updates (that is, upgrade the OS).

> 前面命令的前半部分告诉 OS 搜索适当的存储库并下载更新。第二个命令它安装这些更新(即升级操作系统)。

Now, it’s time to examine OS choices for the Raspberry Pi.

> 现在，是时候检查树莓派的操作系统选择了。

## Operating Systems for Raspberry Pi

This section gives an overview of the various OSs for the Raspberry Pi, and includes a look at the wealth of new OSs that have become available thanks to the new four-core ARM processor in the Raspberry Pi 2; these include Raspberry Pi–enhanced versions of Ubuntu, Fedora and Gentoo as well as Windows 10. In other words, any OS that has ARM support works on the Raspberry Pi’s computer architecture.

> 本节概述了复盆子 Pi 的各种操作系统，并介绍了由于复盆子 Pi2 中新的四核 ARM 处理器而可用的新操作系统的数量；其中包括树莓派——Ubuntu、Fedora 和 Gentoo 以及 Windows 10 的增强版。换句话说，任何支持 ARM 的操作系统都可以在树莓派的计算机架构上运行。

The OSs in this section aren’t meant to be a complete list. Instead we’re touching on some of the more interesting OSs. Included are the ones optimised for the Raspberry Pi’s architecture to deliver powerful solutions on this credit-card-sized monster of a minicomputer.

> 本节中的操作系统并不是一个完整的列表。相反，我们将讨论一些更有趣的操作系统。其中包括为 Raspberry Pi 的体系结构进行了优化，以在这台信用卡大小的微型计算机上提供强大的解决方案。

In choosing an OS for the Raspberry Pi, you should consider the solutions you want the board to accomplish. The truly neat thing about the Raspberry Pi is that changing the OS entails simply replacing the SD or microSD card with another one. (Try that with a PC, Mac, or Linux box!) This ease of switching opens up all sorts of possibilities.

> 在为树莓派选择操作系统时，您应该考虑您希望董事会完成的解决方案。Raspberry Pi 真正巧妙的地方在于，改变操作系统需要简单地将 SD 或 microSD 卡更换为另一张。(用 PC、Mac 或 Linux 盒子试试吧！)这种切换的便捷性带来了各种可能性。

### NOOBS

The New Out-Of-Box Software (NOOBS) software package presents a selection of OSs optimised for the Raspberry Pi. You can download them free from the official Raspberry Pi website at [`www.raspberrypi.org/downloads/`](https://www.raspberrypi.org/downloads/) (see Figure 8-8). They also feature third-party OS images—_images_ being a complete file system in the proper format to boot up and run. You may also purchase NOOBS on SD or microSD cards (the newer Model B+ and 2.0, and 3.0 Raspberry Pis use the latter) on the site or from many other vendors.

> 新的开箱即用软件(NOOBS)软件包提供了一系列针对树莓派优化的操作系统。您可以从 Raspberry Pi 官方网站[`www.raspberrypi.org/downloads/`]免费下载它们([https://www.raspberrypi.org/downloads/)](https://www.raspberrypi.org/downloads/))(见图 8-8)。它们还具有第三方操作系统映像——_images_是一个完整的文件系统，格式正确，可以启动和运行。您也可以在网站上或从许多其他供应商处购买 SD 或 microSD 卡上的 NOOBS(较新的型号 B+ 和 2.0，以及 3.0 复盆子 Pis 使用后者)。

![[FIGURE 8-8:](#11_9781119183938-ch08.xhtml#rc08-fig-0008) The Downloads page on the Raspberry Pi site presents a good starting selection of operating systems.](./media/images/9781119183938-fg0808.png)

Running the NOOBS card walks you through setting up an OS. You have six choices:

> 运行 NOOBS 卡可以帮助您完成操作系统的设置。您有六种选择：

- [`Raspbian`](http://raspbian.org/)**:** A port (converted and optimised to run on the Raspberry Pi) of the popular Debian Linux distribution and recommended by the Raspberry Pi Foundation and many thousands of experimenters as the best OS for the Raspberry Pi. The latest version of this Linux distro is Debian 8, `Jessie` . - [`Arch Linux`](http://archlinuxarm.org/platforms/armv6/raspberry-pi)**:** A Raspberry Pi version for Arch Linux designed to run on ARM central processor chips. - [`Pidora`](http://pidora.ca/)**:** A version of Red Hat’s Fedora Linux distribution. Fedora has always been on the cutting edge of Linux (although just remember—sometimes you bleed on the cutting edge). - [`OpenELEC`](http://wiki.openelec.tv/index.php?title=Raspberry_Pi_FAQ)**:** A dedicated media centre distribution designed for playing video and music by the use of a small, dedicated OS that doesn’t hog resources and leaves more memory for showing movies, blasting the latest tunes and so forth. - [`RaspBMC`](http://www.raspbmc.com/)**:** A media centre distribution based on Raspbian that saves resources for serving media files. - **Reduced instruction set computing (RISC) OS:** Created by the team that designed the ARM CPU. It offers fast execution on small hardware and is worth experimenting with.

> -[`树莓`](http://raspbian.org/)**：**受欢迎的 Debian Linux 发行版的一个端口(已转换并优化为在树莓派上运行)，树莓派基金会和数千名实验人员推荐该端口为树莓派的最佳操作系统。这个 Linux 发行版的最新版本是 Debian 8，`Jessie` 。-[`Arch Linux`](http://archlinuxarm.org/platforms/armv6/raspberry-pi)**：**用于 Arch Linux 的 Raspberry Pi 版本，设计用于在 ARM 中央处理器芯片上运行。-[`Pidora`](http://pidora.ca/)**：**Red Hat 的 Fedora Linux 发行版。Fedora 一直处于 Linux 的最前沿(不过请记住，有时你会在最前沿流血)。-[`OpenELEC`](http://wiki.openelec.tv/index.php?title=Raspberry_Pi_FAQ)**：**专用媒体中心发行版，通过使用小型专用操作系统播放视频和音乐，该操作系统不会占用资源，并为放映电影、播放最新音乐等留出更多内存。-[`RaspBMC`](http://www.raspbmc.com/)**：**基于 Raspbian 的媒体中心发行版，可节省服务媒体文件的资源。-**精简指令集计算(RISC)操作系统：**由设计 ARM CPU 的团队创建。它在小型硬件上提供快速执行，值得尝试。

Of the six OSs listed here, Raspbian is the most popular. If you’re used to Debian-type Linux distros (Debian itself, Ubuntu and so on), you’ll be right at home running Raspbian on a Raspberry Pi.

> 在这里列出的六种操作系统中，Raspbian 是最受欢迎的。如果你习惯了 Debian 类型的 Linux 发行版(Debian 本身、Ubuntu 等)，你就可以在家里用复盆子 Pi 运行复盆子了。

### Third-Party Operating Systems

The official Raspberry Pi site includes several third-party images, which are free for download. Images allow you to write an SD or microSD card that installs the OS on your Raspberry Pi. Two of these OSs were discussed in the preceding section—OpenELEC and RISC OS—so we’ll skip those. Of the ones remaining, one may shock you (Windows) and, yes, it’s free:

> Raspberry Pi 官方网站包括几个免费下载的第三方图像。图像允许您编写 SD 或 microSD 卡，将操作系统安装在 Raspberry Pi 上。在前面的 OpenELEC 和 RISC 操作系统部分中讨论了其中两个操作系统，因此我们将跳过这些操作系统。在剩下的几个中，有一个可能会让你震惊(Windows)，是的，它是免费的：

- **Ubuntu MATE:** A Raspberry Pi-optimised version of the popular Ubuntu distro that features the MATE desktop (a desktop environment forked from the now-unmaintained code base of GNOME 2). - **Snappy Ubuntu Core:** A distro that came about as a project for Ubuntu users on smartphones. It supports Docker, which means it is a good platform for cloud applications. - **Windows 10 IoT Core:** The latest version of the often maligned but often indispensible Microsoft OS comes to the Raspberry Pi (requires Raspberry 2.0). IoT refers to the Internet of Things, so this OS lets you develop IoT apps on the Raspberry Pi. - **OSMC:** A free open source media centre `built for the people, by the people` . It’s similar to the proprietary OpenELEC, but it’s free. - **PiNet:** Provides a centralised user accounts and file storage system for a Raspberry Pi classroom.

> -**Ubuntu MATE:**一个流行的 Ubuntu 发行版的树莓派优化版本，其特点是 MATE 桌面(桌面环境源自 GNOME 2 现在未维护的代码库)。-**Snappy Ubuntu Core：**一个面向智能手机上 Ubuntu 用户的发行版。它支持 Docker，这意味着它是一个很好的云应用平台。-**Windows 10 IoT 核心：**树莓派(Raspberry Pi)是最新版本的微软操作系统，经常被人诟病，但往往不可或缺。IoT 指的是物联网，因此该操作系统允许您在树莓派上开发 IoT 应用程序。-**OSMC：**一个 `为人民、为人民而建` 的免费开源媒体中心。它类似于专有的 OpenELEC，但它是免费的。-**PiNet:**为 Raspberry Pi 教室提供集中的用户帐户和文件存储系统。

### Other Available Operating Systems

Other versions of OS distributions for the Raspberry Pi exist. Here’s a smattering of some interesting ones. Most require the Raspberry Pi 2:

> 树莓派还有其他版本的操作系统发行版。这里有一些有趣的例子。大多数需要树莓派 2:

- **Gentoo:** A fast and popular (because of its near-unlimited adaptability) Linux. Look for the Raspberry Pi version on the Gentoo site at [`https://wiki.gentoo.org/wiki/Raspberry_Pi`](https://wiki.gentoo.org/wiki/Raspberry_Pi). - **FreeBSD:** Before Linux there was UNIX, and FreeBSD is still very actively supported (see [`www.FreeBSD.org`](http://www.FreeBSD.org)). It’s been ported to the Raspberry Pi; visit [`https://www.raspberrypi.org/blog/freebsd-is-here/`](https://www.raspberrypi.org/blog/freebsd-is-here/)_._ - **Firefox OS:** Mozilla’s Firefox OS is now on Raspberry Pi. Find additional information at [`https://wiki.mozilla.org/Fxos_on_RaspberryPi`](https://wiki.mozilla.org/Fxos_on_RaspberryPi). - **IPFire:** This OS provides a system featuring an exceptionally strong firewall, which gives protection against intrusion but retains ease of use and has the functionality required for corporate and institutional usage. Visit [`www.ipfire.org/`](http://www.ipfire.org/) to download the ARM version. - **OpenSUSE:** A popular Linux distro, especially in Europe, that now has an ARM version that runs on the Pi. See [`https://en.opensuse.org/HCL:Raspberry_Pi`](https://en.opensuse.org/HCL:Raspberry_Pi). - **Plan 9:** An OS from Bell Labs that’s named after everyone’s favourite so-bad-it’s-good movie, _Plan 9 from Outer Space_. You can find more info and instructions for installing Plan 9 on the Raspberry Pi at [`https://www.raspberrypi.org/forums/viewtopic.php?f=80&t=24480`](https://www.raspberrypi.org/forums/viewtopic.php?f=80&t=24480). - **SliTaz:** An OS touted as a simple and fast Linux OS system that has low resource requirements for servers and desktops. Find the link for the Raspberry Pi version at [`www.slitaz.org/en/`](http://www.slitaz.org/en/). - **Tiny Core:** A simple (limited subset) Linux OS that takes up less memory space and fewer other resources but still provides reasonable computer power. Find downloads and info at [`http://distro.ibiblio.org/tinycorelinux/ports.html`](http://distro.ibiblio.org/tinycorelinux/ports.html).

> -**Gentoo:**一个快速而流行的(因为其几乎无限的适应性)Linux。在 Gentoo 网站上查找 Raspberry Pi 版本[`https://wiki.gentoo.org/wiki/Raspberry_Pi`](https://wiki.gentoo.org/wiki/Raspberry_Pi). - **FreeBSD:**在 Linux 之前有 UNIX，FreeBSD 仍然受到非常积极的支持(请参见[`www.FreeBSD.org`](http://www.FreeBSD.org)). 它被移植到树莓派；访问[`https://www.raspberrypi.org/blog/freebsd-is-here/`](https://www.raspberrypi.org/blog/freebsd-is-here/)_._ - **Firefox 操作系统：**Mozilla 的 Firefox 操作系统现在正在 Raspberry Pi 上运行。有关更多信息，请访问[`https://wiki.mozilla.org/Fxos_on_RaspberryPi`](https://wiki.mozilla.org/Fxos_on_RaspberryPi). - **IPFire:**此操作系统提供了一个具有异常强大防火墙的系统，该系统提供了防入侵保护，但保持了易用性，并具有企业和机构使用所需的功能。访问[`www.ipfire.org/`](http://www.ipfire.org/)下载 ARM 版本。-**OpenSUSE:**一个流行的 Linux 发行版，特别是在欧洲，现在有一个运行在 Pi 上的 ARM 版本。参见[`https://en.opensuse.org/HCL:Raspberry_Pi`](https://en.opensuse.org/HCL:Raspberry_Pi). - **计划 9：**贝尔实验室的一个操作系统，以每个人最喜欢的烂到爆的电影命名，《来自外太空的计划 9》。您可以在以下位置找到有关在树莓派上安装计划 9 的更多信息和说明：[`https://www.raspberrypi.org/forums/viewtopic.php?f=80&t=24480`](https://www.raspberrypi.org/forums/viewtopic.php?f=80&t=24480). - **SliTaz:**一个被吹捧为简单快速的 Linux 操作系统，对服务器和桌面的资源要求很低。找到 Raspberry Pi 版本的链接，网址为[`www.slitaz.org/en/`](http://www.slitaz.org/en/). - **微型内核：**一个简单的(有限的子集)Linux 操作系统，占用更少的内存空间和更少的其他资源，但仍然提供合理的计算机功率。在以下位置查找下载和信息[`http://distro.ibiblio.org/tinycorelinux/ports.html`](http://distro.ibiblio.org/tinycorelinux/ports.html).

An increasing number of other OSs are out there. Googling `operating systems for Raspberry Pi` returns quite a lot of possibilities for you to explore. Again, one of the great advantages of the Raspberry Pi lies in its capacity to change OSs in seconds. Unplug the current SD or microSD card and plug into another card with an entirely different OS. Boot it up and go.

> 还有越来越多的其他操作系统。在谷歌上搜索 `树莓派的操作系统` 会为你带来很多探索的可能性。同样，树莓派的一大优势在于它能够在几秒钟内更换操作系统。拔下当前的 SD 或 microSD 卡，然后插入另一个具有完全不同操作系统的卡。启动它，然后离开。

The only limit to the number of OSs you can have lies in how many SD cards you can afford. Prices on SDs and microSDs continue to drop. It’s pretty darn wonderful.

> 你能拥有的操作系统数量的唯一限制在于你能负担多少 SD 卡。SD 和 microSD 的价格继续下降。这真是太棒了。
