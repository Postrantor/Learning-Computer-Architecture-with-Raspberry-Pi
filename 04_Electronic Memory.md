Chapter 3

# Electronic Memory

**COMPUTING AS WE** know it today is a wild dance between the central processing unit (CPU) and memory. Instructions in memory are fetched, and the CPU executes them. In executing instructions, the CPU reads data from memory, changes it and then writes it back. Data and instructions that are used a lot are pulled in closer, via cache. Data and instructions that aren’t needed for the time being are swapped out of virtual memory onto disk.

> **我们**今天知道的计算是中央处理单元(CPU)和内存之间的一种狂野舞蹈。获取内存中的说明，CPU 执行它们。在执行指令时，CPU 从内存中读取数据，对其进行更改，然后将其写回。使用大量的数据和说明通过缓存更近地拉开。暂时不需要的数据和说明将虚拟内存中换成磁盘。

To understand this dance you need an understanding of both the CPU and memory. Which, then, to study first? In most cases, the CPU is considered the star of the show and always begins the parade. That’s a mistake. There are multitudes of CPU designs out there, all of them different and all stuffed to the gills with tricks to make their own parts of the dance move more quickly. Memory, on the other hand, is a simpler and less diverse technology. Its moves in the dance are fairly simple: store data from the CPU and hand it back when requested, as quickly as possible. To a great extent, memory dictates the speed at which the dance proceeds. The designs of our CPUs are heavily influenced by the speed limitations of system memory.

> 要了解此舞蹈，您需要了解 CPU 和 Mem。那么，首先学习哪个呢？在大多数情况下，CPU 被认为是演出的明星，并且总是开始游行。这是一个错误。那里有许多 CPU 设计，所有这些设计都不同，所有这些设计都在 ills 上塞满了，以使自己的舞蹈的部分更快地移动。另一方面，Mem 是一项更简单，较少的技术。它在舞蹈中的动作非常简单：从 CPU 中存储数据，并在要求时尽快将其交给。在很大程度上，Mem 决定了舞蹈的速度。我们 CPU 的设计受到系统内存速度限制的严重影响。

That being the case, it makes sense to study memory first. If you understand memory technology thoroughly, you’re halfway to understanding anything else in a modern computer system.

> 就是这样，首先研究 Mem 是很有意义的。如果您彻底了解内存技术，那么您就是了解现代计算机系统中其他任何内容的一半。

## There Was Memory Before There Were Computers

For a long time, computers were really special-purpose haywire calculators. What passed for programs were lashed up by hand with switches and jumper wires representing 1s and 0s. Then John von Neumann and others proposed that programs be stored as digital patterns on the machine, right in with the data that the programs were written to process. The first generation of these stored-program computers used single-bit storage circuits (colloquially called _flip-flops_) constructed from vacuum tubes to store programs and data. Imagine for a moment storing a 1 or a 0 in something the size of your fist! Apart from being enormous, hot and power-hungry, vacuum tube data storage was _volatile_—when the computer was powered down, the electronic states of the vacuum tubes vanished as the tubes went dark.

> 很长一段时间以来，计算机确实是专用的干草计算器。通过代表 1s 和 0s 的开关和跳线电线将程序通过的内容用手猛烈抨击。然后，约翰·冯·诺伊曼(John von Neumann)和其他人提出，将程序存储在机器上，并与程序编写用于处理的数据有关。这些存储程序计算机的第一代使用了单位存储电路(通俗称为 *Flip-Flops*)，该电路从真空管构建的构建来存储程序和数据。想象一下，在拳头大小的东西中存储 1 或 0 的时间！除了巨大的，热和渴望的功率外，真空管数据存储还* Volatile *-当计算机电源电源时，真空管的电子状态随着管变暗而消失了。

To keep programs and data permanently, vacuum-tube data was written to strips of paper tape or cardboard Hollerith punch cards. (Hollerith cards were used in mechanical tabulation of census data. They predate digital computers by 50 years.) The machines to read tape or cards into a computer were electromechanical and very slow. Sending intermediate results out to electromechanical paper storage was even slower and wasted most of the speed that electronic computing offered. A better way to record code on data than punching holes in pulped trees was desperately needed.

> 为了永久保留程序和数据，真空管数据写入纸带或纸板 Hollerith 打孔卡的条带。(Hollerith 卡用于人口普查数据的机械制表。它们早于 50 年的数字计算机。)将磁带或卡片读取到计算机的机器是机电且非常慢的。将中间结果发送到机电纸存储的情况甚至更慢，并浪费了电子计算提供的大部分速度。迫切需要一种比在纸浆中打孔孔的更好的方法来记录数据的代码。

## Rotating Magnetic Memory

In those early, crazy days of computing, many things were tried. Mercury-based delay-line memory units stored bits as mechanical pulses—sound waves, basically—travelling through linear columns of mercury in sealed tubes. Like modern dynamic computer memory, delay-line memory had to be refreshed every time a bit (encoded as a pulse) arrived at the far end of the tube. Strings of pulses representing code and data marched endlessly through the mercury, read and written by quartz piezoelectric crystals as needed. Mercury memory systems were huge, hot, heavy and full of toxic heavy metal. They were also very touchy to adjust and keep in operation.

> 在那些疯狂的计算日子里，尝试了许多事情。基于汞的延迟线 Mem 单元将其存储为机械脉冲(基本上是波浪)，基本上是在密封管中穿过汞的线性柱。就像现代动态计算机内存一样，每次稍微(编码为脉冲编码)到达管的尽头时，都必须刷新延迟线内存。代表代码和数据的脉冲串通过汞无休止地进军，根据需要由石英压电晶体读取和编写。汞 Mem 系统巨大，热，重，充满有毒的重金属。他们也非常敏感，可以进行调整和保持运行。

Another early memory storage scheme encoded bits as dots of light on the surface of a cathode-ray tube (CRT) with long-persistence phosphor, much like the tubes used in early radar displays. The dots, once written, would linger in the phosphor for a few seconds and could be read by a plate placed against the face of the tube. As with delay-line memory, CRT memory had to be refreshed periodically. Nonetheless, each of the tubes could store 1,024 bits in a fraction of the space required by delay-line storage. Known as Williams tubes, these were used as memory in the famous IBM 701 commercial computers, introduced in 1952. They were the first widely used _random-access memory_ (RAM)—so-called because bits could be accessed at any time from anywhere on the face of the tube. The term _RAM_ is still used today, even though we’ve mostly forgotten that there was ever any other kind of computer memory. The preferred term is read/write memory, but terms like _RAM_, _SRAM_, _DRAM_ and _SDRAM_ are so universally used that we use them in this book.

> 另一种早期的存储器存储方案编码了钻头，作为带有长渗透磷光器的阴极射线管(CRT)表面上的光点，就像早期雷达显示器中使用的管一样。这些点一旦写成，就会在磷光器中徘徊几秒钟，可以通过放在管子的脸上的盘子来读取。与延迟内存一样，必须定期对 CRT 内存进行刷新。尽管如此，每个管子都可以将 1,024 位存储在延迟线存储所需的空间的一小部分中。它们被称为威廉姆斯管，在 1952 年引入的著名的 IBM 701 商业计算机中被用作内存管子的脸。即使我们大多忘记了还有其他任何类型的计算机内存，*ram* 一词仍在今天使用。首选的术语是读/写内存的，但是像 *ram*，_sram_，*dram* 和 *sdram* 之类的术语是如此普遍地使用，以至于我们在本书中使用它们。

Both of these memory technologies, like vacuum-tube memory, were volatile. A memory technology that would retain its data even when the computer was powered down would make many things easier, and new things would be possible. Encoding information as tiny regions of magnetic alignment on a moving magnetic surface dates back to the early 1930s. The Germans invented magnetic sound recording, which wrote sound waveforms to spools of plastic tape coated with iron-oxide powder. By 1950, this technology had been adapted to store digital data instead of audio waveforms, and it was incorporated in the legendary UNIVAC machine to replace paper tape and Hollerith cards.

> 这两种 Mem 技术，例如真空管 Mem，都是挥发性的。即使关闭计算机，也可以保留其数据的内存技术将使许多事情变得更加容易，而新事物将成为可能。将信息编码为移动磁表面上磁对齐的微小区域的历史可以追溯到 1930 年代初。德国人发明了磁性录音，该磁性录音写在涂有铁氧化粉末的塑料胶带的线轴上。到 1950 年，这项技术已经适应了存储数字数据而不是音频波形，并且已将其纳入传奇的 Univac 机器中，以替换纸带和 Hollerith 卡。

Magnetic tape was a faster storage medium than paper tape and cards, and it had the advantage of being rewritable. After a hole was punched in paper tape, the hole was permanent. However, magnetic pulses on tape could be written and erased again and again. Unfortunately, tape was still too slow to be used as computer system memory.

> 磁带是比纸带和卡更快的存储介质，它具有重写的优势。用纸带打孔后，孔是永久的。但是，胶带上的磁性脉冲可以一次又一次地写入和擦除。不幸的是，磁带仍然太慢，无法用作计算机系统内存。

The solution was again invented by the Germans: a metal drum the size of a small wastepaper basket, coated with iron oxide powder, spun on its axis as quickly as the motor and bearing technology of the time would allow. Tiny magnetic sensor heads were attached to the drum’s housing, with each head aligned over a separate narrow `stripe` on the drum’s surface. The magnetic heads could write bits to a track by passing electrical pulses through the heads. A pulse aligned the magnetic poles of oxide particles on the drum surface, creating a tiny magnetised region. This magnetic region would induce a tiny current in the same head when it passed beneath the head. A bit was encoded as a 1 or a 0 by the presence or absence of magnetic alignment in a small region of oxide.

> 该解决方案再次由德国人发明：一个金属鼓与一个小废纸篮的大小，涂有铁氧化铁粉末，其轴上旋转，就像电动机的电动机和轴承技术一样快。将小磁性传感器头连接到鼓的外壳上，每个头部都在鼓表面上的单独的窄 `条纹` 对齐。磁头可以通过将电脉冲通过头部传递到轨道上。脉冲将氧化物颗粒的磁极对齐在鼓表面，形成一个微小的磁化区域。当该磁性区域在头部下方时会诱导同一头部的微小电流。通过在氧化物的一小区域中存在或不存在磁比对，将钻头编码为 1 或 0。

In a way similar to delay-line memory, bits written onto tracks circled endlessly beneath the read/write heads as the drum rotated. The bits could only be read or written sequentially. If a value written onto a drum track was needed by the computer, the computer had to wait until that value came around again in order to read it. This slowed access down, but the drums were being spun very quickly. Access was thus faster than any earlier memory technology except for electronic flip-flops inside the CPU itself.

> 以类似于延迟线 Mem 的方式，在鼓旋转时，将其写在读/写头下面的曲目上。这些位只能依次读取或书写。如果计算机需要写入鼓轨道上的值，计算机必须等到该值再次出现才能阅读。这减慢了访问，但是鼓很快就被旋转了。因此，除了 CPU 本身内部的电子触发器外，访问速度比任何早期的内存技术都要快。

Programmers learned how to finesse the sequential delays inherent in drum memory by synchronising their programs to the rotation of the drum. The programs knew when a particular sequence of values would appear under the heads, and did other things during the latency period. This sounds foolish today but in 1953 it was a mainstream technique and made drum memory the fastest computer memory technology available.

> 程序员学会了如何通过将其程序同步到鼓的旋转来技巧延迟。这些程序知道何时会出现特定的值序列，并在延迟期间做其他事情。今天这听起来很愚蠢，但是在 1953 年，这是一种主流技术，使鼓内 Mem 成为最快的计算机 Mem 技术。

One final advance in rotating magnetic memory foreshadowed modern hard-drive technology: _fixed-head magnetic memory_, which consisted of a magnetic disk with concentric tracks, each track aligned with its own stationary magnetic read/write head. Disks could be spun much faster than drums, so although a drum could hold more code and data, a disk could provide access more quickly. Apart from the shape of the storage medium, magnetic disk memory and drum memory were the same. Magnetic disk storage units of this sort were used as fast `swap memory` for virtual memory systems until the early 1970s, when moving-head magnetic disk units replaced them.

> 旋转磁性 Mem 预示的最后一个进步预示了现代的硬盘驱动技术：_固定头磁性内存_，由带有同心轨道的磁盘组成，每个轨道都与自己的固定磁性读/写入头对齐。磁盘的旋转速度可能要比鼓快得多，因此，尽管鼓可以容纳更多的代码和数据，但磁盘可以更快地提供访问。除了存储介质的形状外，磁盘内存和鼓内存是相同的。直到 1970 年代初，当移动头磁盘单元更换它们时，这种磁盘存储单元被用作虚拟内存系统的快速 `交换内存` 。

## Magnetic Core Memory

Moving parts can be bad news, and parts moving very quickly can be very bad news. Rotating magnetic memory was loud and prone to vibration. Worse, if a drum or bearing failed, the device would generally destroy itself beyond repair. So the world was ready for fast computer memory without moving parts. In 1955 it arrived. Unlike earlier memory technologies, magnetic core memory is still used in certain `legacy` (that is, ancient) computers and a small number of industrial process controllers.

> 活动部件可能是个坏消息，并且零件很快移动可能是个坏消息。旋转的磁 Mem 很大，容易振动。更糟糕的是，如果鼓或轴承失败，则该设备通常会破坏自身。因此，世界已经准备好无动作零件的快速计算机内存。1955 年到达。与早期的 Mem 技术不同，磁芯 Mem 仍然用于某些 `遗产` (即古代)计算机和少量工业过程控制器中。

Magnetic core memory systems use tiny _toroidal_ (ring-shaped) magnetic beads called _cores._ The cores are made of an exotic iron oxide with high _remanance_ (the ability to retain a magnetic field over time) and low _coercitivity_ (the energy required to change the magnetic field). One core is capable of storing 1 bit. The state of any given bit is represented not by the presence or absence of a magnetic field but by its orientation. A core’s magnetic field can exist in two different orientations, which by convention are called clockwise and counterclockwise. The state of a bit is changed by `flipping` its core’s magnetic field from clockwise to counterclockwise, or vice versa.

> 磁芯存储系统使用微小的 *toroidal*(环形)磁珠称为_cores。磁场)。一个核心能够存储 1 位。任何给定位的状态不是由磁场的存在或不存在而表示的，而是由其方向表示。核心的磁场可以以两种不同的方向存在，按照惯例将其称为顺时针和逆时针。通过将其核心的磁场从顺时针旋转到逆时针，反之亦然，反之亦然。

The toroidal cores are woven into a rectangular matrix of very fine wire supported by a sheet of circuit board material. Each assembly is called a _plane_. Four wires pass through the centre hole of every core (see Figure 3-1):

> 将环芯编织成一个非常细线的矩形基质，该基质由一张电路板材料支撑。每个组件称为 *plane*。四根电线穿过每个核心的中心孔(见图 3-1)：

- An _x_ wire, which provides one dimension to select a core from a plane - A _y_ wire, which provides the second dimension to select a core from a plane - A sense wire, which allows the system to read the magnetic state of a core - An inhibit wire, which allows the system to set the state of a core

> - *x* 线，它提供了一个维度来从平面中选择芯 - *y* 线，该线提供了第二个维度，从平面中选择芯子 - 感官线，这使系统能够读取芯的磁状态 - 抑制线，允许系统设置核心状态

> ![[FIGURE 3-1:](#06_9781119183938-ch03.xhtml#rc03-fig-0001) The structure of a core memory plane](./media/images/9781119183938-fg0301.png)

In [Figure 3-1](#06_9781119183938-ch03.xhtml#c03-fig-0001), the cores are shown edge-on. By sending carefully controlled electric currents through the four wires in various combinations, the magnetic field orientation in selected cores may be sensed or changed. Cores may be selected singly and at random as the computer requires. Like the earlier Williams tubes, magnetic core memory is random-access memory. It’s also non-volatile, and the cores retain their magnetic fields (and thus their data) when the computer is powered down.

> 在[图 3-1](%EF%BC%8306_9781119183938-CH03.XHTML%EF%BC%83C03-FIG-0001) 中，显示了核心。通过以各种组合将小心控制的电流通过四根电线发送，可以感觉到或更改所选芯中的磁场方向。可以根据计算机需要单独选择核心。像较早的威廉姆斯管一样，磁芯内存是随机访问的内存。它也是非易失性的，当计算机电源电源电源时，核心保留了磁场(以及它们的数据)。

### How Core Memory Works

Electrical conductors generate magnetic fields when current passes through them. The strength of this magnetic field is proportional to the strength of the current. If a wire running through the centre hole of a core generates a sufficiently strong magnetic field, the magnetic field in the core aligns itself with the direction of the current flowing through the wire.

> 当电流通过它们时，电导体会产生磁场。该磁场的强度与电流强度成正比。如果通过芯的中心孔延伸的电线会产生一个足够强的磁场，则芯中的磁场与电流流过电线的方向对齐。

The _x_ and _y_ wires are used to select one core from the grid of cores in a plane, just as _x_ and _y_ values select one point in a Cartesian plane from geometry. A current is passed through the _x_ and _y_ wires that both pass through the core to be selected. Each of the two wires carries enough current to generate half of the magnetic field required to flip the core. Thus, the core through which both wires pass is given enough of a magnetic pulse to change its orientation. The direction of the current passing through the _x_ and _y_ wires determines the orientation. Passing the current one way imposes a 0-state on the core. Passing the current the other way imposes a 1-state on the core.

> *x* 和 *y* 电线用于从平面中的内核网格中选择一个核心，就像 *x* 和 *y* 值从几何学中选择笛卡尔平面中的一个点一样。电流通过 *x* 和 *y* 电线，两者都穿过要选择的核心。两条电线中的每根电流都足以生成翻转芯所需的一半磁场。因此，两根电线通过的核心被给予足够的磁性脉冲来改变其方向。通过 *x* 和 *y* 电线的电流的方向决定了方向。通过当前的一种方式，将 0 状态施加在核心上。以另一种方式将电流传递给核心上。

This sounds simpler than it is. The problem is that the computer must read a core before writing to it. And reading the core involves an attempt to write to it. The process of reading a core is easier to follow as a list of steps:

> 这听起来比现在简单。问题在于计算机必须在写入核心之前读取核心。阅读核心涉及尝试写信。阅读核心的过程更容易作为步骤列表：

1. The computer attempts to force the state of the selected core to a 0-state by sending current of the appropriate direction to the _x_ and _y_ wires that intersect at the core of interest. 2. If the selected core was already at the 0-state, nothing happens. 3. If the selected core was originally in the 1-state, the core state changes to 0. The state change induces a small current in the sense wire. The presence of a current on the sense wire tells the computer that the bit had originally been a 1-bit.

> 1.计算机试图通过将适当方向的电流发送到相交的 *x* 和 *y* 电线，以将所选核心的状态迫使 0 状态。2.如果选定的核心已经在 0 状态，则什么也不会发生。3.如果选定的核心最初是在 1 状态中的，则核心状态变为 0。状态变化在感觉线上会引起小电流。感觉线上的电流的存在告诉计算机最初是 1 位。

The computer now knows whether the core was set to 1 or to 0. Alas, reading the state of a core is like holding a match to your sweater to see if it’s made of a flammable fabric. If the sweater catches fire, the material is flammable—and now there’s a big hole in your sweater. By reading a core’s state, the core is forced to 0. This kind of operation is called a _destructive read_. To retain the value that the core had originally expressed requires that the state read must be written back to the core.

> 现在，计算机知道核心是设置为 1 还是为 0。如果毛衣着火，则材料是易燃的，现在您的毛衣里有一个大洞。通过读取核心的状态，核心被迫为 0。这种操作称为 *Destructive read*。要保留核心最初表示的价值，要求必须将状态读取回到核心。

Here’s how writing to a core is done:

> 以下是写作核心的方式：

1. The computer attempts to read the core’s state. This forces the core to the 0-state. Whatever state had been present before is discarded by the circuitry. 2. To write a 1-bit, current of the proper direction is sent through the _x_ and _y_ wires that intersect at the core. The core’s state changes to 1. 3. To write a 0-bit, the same current is sent through the same _x_ and _y_ wires. However, this time, an identical current is sent through the inhibit wire. This creates a magnetic field that bucks (cancels) the field created by the _x_ and _y_ wires. The inhibit wire prevents (inhibits) the change to a 1-bit. Because the bit was originally a 0 bit, the 0-state remains unchanged.

> 1.计算机试图阅读核心状态。这迫使核心进入 0 状态。以前存在的任何状态都被电路丢弃。2.要编写一个 1 位，通过 *x* 和 *y* _*芯上的电线发送了正确的方向的电流。核心的状态更改为 1。3。要编写 0 位，相同的电流是通过相同的_x* 和 *y* 电线发送的。但是，这一次，通过抑制线发送相同的电流。这会创建一个磁场，该磁场(取消)由 *x* 和 *y* 电线创建的字段。抑制线阻止(抑制)变为 1 位。因为该位最初是 0 位，所以 0 状态保持不变。

It sounds a little crazy today, but it does work: to read a bit from a core, you must read it and then write it back. To write a bit to a core, you must first clear the core to 0 by reading it and then either write (1) or inhibit a write (0) by using the inhibit wire.

> 今天听起来有些疯狂，但确实有效：要从核心中读取一点，您必须阅读它然后写回去。要将一点写入核心，您必须首先通过读取核心，然后通过使用抑制线来抑制(1)或抑制写入(1)。

### Memory Access Time

We’ve gone on about the internals of core memory at some length to make a point: electronic memory is governed by physics that may be a lot more subtle and complex than you expect. At some level, even digital devices operate by analogue physics. This complexity governs the all-important factor of memory access time. Reading memory takes time. Writing to memory takes time. From a height, progress towards increasing the speed of computers is the struggle to make memory fast enough not to slow the CPU to a crawl.

> 我们已经详细介绍了核心 Mem 的内部，以提出一个观点：电子 Mem 受物理的控制，这些物理可能比您预期的要更加微妙和复杂。在某种程度上，即使是数字设备也由模拟物理运行。这种复杂性控制着内存访问时间的最重要因素。阅读 Mem 需要时间。写入 Mem 需要时间。从高度来看，提高计算机速度的进展是使 Mem 足够快的努力，而不是减速 CPU 到爬网。

Core memory was the fastest sort of memory in existence when it was introduced, and it swept drum and fixed-head disk memory into the sea. (Disk memory evolved into hard disk mass storage as we know it today through the use of movable read/write heads.) Early core memory had an access time of 6 microseconds (μ), which fell to 600 ns nanoseconds (ns; here, 0.1 microsecond) when the technology was mature in the mid-1970s. This was comparable to the purely electronic memory in very early personal computers like the Altair and Apple II.

> 核心内存是引入时存在的最快 Mem，它将鼓和固定头磁盘存储在海中。(磁盘内存演变成硬盘质量存储，正如我们今天通过使用可移动的读取头所知道的那样。)早期核心内存的访问时间为 6 微秒(μ)，该时间跌至 600 ns nanseconds(ns; ns;在这里；0.1 微秒时)当该技术在 1970 年代中期成熟时。这与非常早期的个人计算机(如 Altair 和 Apple II)中的纯电子 Mem 相媲美。

Core memory was fast for its day, but it was difficult to manufacture and very expensive. This is why it was used in mainframe computers and later minicomputers, but never to any extent in personal computers. By the mid-1970s something else had appeared to change the nature of computing even more than core memory did.

> 核心 Mem 日期很快，但是制造很难且非常昂贵。这就是为什么在大型计算机和后来的微型计算机中使用的原因，但在个人计算机中从未使用过。到 1970 年代中期，其他一些事情似乎比核心内存更改了计算的性质。

## Static Random Access Memory (SRAM)

You might wonder where transistors enter our story. Computer memory built from discrete (individual) transistors did exist, but it was bulkier and more expensive than magnetic core memory. It was also volatile. Although discrete transistor flip-flop memory was faster than core memory, its disadvantages kept it from being a broad commercial success.

> 您可能想知道晶体管在哪里进入我们的故事。由离散(单个)晶体管构建的计算机内存确实存在，但比磁芯内存更笨重，更昂贵。这也是波动的。尽管离散的晶体管触发器 Mem 比核心 Mem 更快，但其缺点使其无法取得广泛的商业成功。

Besides, in the late 1950s, engineers did the obvious and began placing multiple transistors on a single tiny chip of silicon. Texas Instruments (TI) engineer Jack Kilby added resistors to the same wafers, allowing all the necessary elements of computer logic gates to be integrated on one silicon wafer. The _integrated circuit_ (IC) was born. The famous 7400-series of transistor-transistor logic (TTL) devices was introduced in 1966 and they were used to build new generations of computers that were faster and more compact than ever before.

> 此外，在 1950 年代后期，工程师做了显而易见的事情，并开始将多个晶体管放在一个硅的一小块芯片上。德州仪器(TI)工程师杰克·基尔比(Jack Kilby)在同一晶片中增加了电阻，使计算机逻辑门的所有必要元素都可以集成在一个硅晶圆上。_集成电路_(IC)诞生了。1966 年推出了著名的 7400 系列晶体管传播逻辑(TTL)设备，它们被用来构建比以往更快，更紧凑的新一代计算机。

Although TTL computer memory appeared along with gates and counters, it was not until 1969 that Intel’s TTL 64-bit 3101 chip became the first commercial IC computer memory device. Intel’s 256-bit 1101, introduced only a few months later, was slower but contained more bits and was less expensive. The 1101’s use of metal-oxide semiconductor (MOS) technology was a watershed. MOS transistors are field-effect devices, in which electron flow is controlled by electric fields, as in vacuum tubes, whereas TTL chips use the older bipolar junction transistor (BJT) technology. BJTs operate by using small current flows to control larger current flows, with total current flows many times that of MOS transistors. MOS techniques could put many more transistors on a single chip while reducing power dissipation and waste heat. Except in very specialised applications, MOS soon drove TTL out of the memory market.

> 尽管 TTL 计算机存储器与门和计数器一起出现，但直到 1969 年，英特尔的 TTL 64 位 3101 芯片才成为第一个商业 IC 计算机存储器设备。仅几个月后推出的英特尔的 256 位 1101 较慢，但含量较慢，但更便宜。1101 使用金属氧化物半导体(MOS)技术是一个分水岭。MOS 晶体管是现场效应的设备，其中电子流由电场控制，如真空管中，而 TTL 芯片使用较旧的双极连接晶体管(BJT)技术。BJTS 通过使用小电流流以控制较大的电流流，而总电流流量多次，而 MOS 晶体管的总流量很多倍。MOS 技术可以将更多的晶体管放在单个芯片上，同时减少功率耗散和废热。除了在非常专业的应用程序中，MOS 很快将 TTL 赶出了 Mem 市场。

The 1101 and 3101 were static random access memory (SRAM) devices. They were random-access because a single bit could be accessed `at random` without any need to wait on sequential access or sift through other bits. They were static because bits written to the chips would remain in their written state as long as the chips had power—even if the computer’s clock was slowed or stopped. Both chips have now been obsolete for decades, but apart from packing more bits into a package, today’s SRAM chips work in very much the same way.

> 1101 和 3101 是静态随机访问存储器(SRAM)设备。它们是随机访问的，因为可以 `随机` 访问一个位，而无需等待顺序访问或通过其他位进行筛选。它们是静态的，因为只要芯片具有力量，即使计算机的时钟放慢或停止，只要芯片具有力量，写在芯片上的碎屑就会保持其书面状态。几十年来，这两个芯片已经过时了，但是除了将更多的碎屑包装到包装中外，今天的 SRAM 芯片的工作方式非常相同。

The basic logic element in SRAM chips is the flip-flop. A flip-flop is a logic circuit with an output that can be in one of two states, and that can be switched from one state to the other by a pulse or voltage change on an input. It will hold that state until another pulse switches it to its opposite state, or until power is removed from the circuit. Because it has two states, and because binary digits have two possible values, a flip-flop can `remember` a single bit.

> SRAM 芯片中的基本逻辑元素是触发器。触发器是一个逻辑电路，其输出可以在两种状态之一中，并且可以通过输入上的脉冲或电压变化从一个状态切换到另一个状态。它将保持该状态，直到另一个脉冲将其切换到相反的状态，或直到将电源从电路中删除为止。因为它具有两个状态，并且由于二进制数字具有两个可能的值，因此触发器可以 `记住` 一个位。

SRAM bits are stored in _cells_, each of which is basically a flip-flop circuit. SRAM cells require at least four transistors. To improve speed and reliability, some designs use six transistors, at the cost of additional complexity and a smaller number of bits stored per device.

> SRAM 位存储在 *cells* 中，每个 sram 位基本上都是触发器电路。SRAM 细胞至少需要四个晶体管。为了提高速度和可靠性，一些设计使用六个晶体管，以额外的复杂性和较少数量的每台设备存储的位。

Technology has moved on quite a bit since SRAM was introduced. Except in very specialised applications that require the shortest possible access times, SRAM has been replaced by DRAM, as we’ll explain shortly. But first, let’s look at what SRAM and DRAM have in common: memory addressing.

> 自引入 SRAM 以来，技术已经发展了很多。除了需要最短的访问时间的非常专业的应用程序中，SRAM 已被 DRAM 取代，正如我们将不久解释的那样。但是首先，让我们看看 SRAM 和 DRAM 的共同点：Mem 地址。

---

> [!NOTE]

Read more about DRAM later in this chapter in the `[Dynamic Random Access Memory (DRAM)](#06_9781119183938-ch03.xhtml#c03-sec-0010)` section.

> 在本章 ` [动态随机访问存储器(DRAM)](%EF%BC%8306_9781119183938-CH03.XHTML%EF%BC%83C03-SEC-0010)中，请阅读有关 DRAM 的更多信息。

## Address Lines and Data Lines

As we saw with core memory, putting multiple bits in a memory device requires some way of selecting bits within the device to read or write. Core memory uses an _x/y_ addressing scheme very much like a Cartesian plane in geometry to select one core from all the cores in a core memory plane. Inside an SRAM or DRAM chip, memory cells are arranged in a matrix, and they’re selected using a system of _x/y_ addressing. Computers don’t locate cells in a memory system through _x/y_ coordinates. Additional circuitry is needed to convert a binary memory address to a pair of _x/y_ values that select one cell from the many.

> 正如我们在核心内存中看到的那样，将多个位放入存储器设备中需要某种方式来在设备中选择读取或写入的位。核心内存使用 *x/y* 地址方案非常像几何形状中的笛卡尔平面，从核心内存平面中的所有内核中选择一个核心。在 SRAM 或 DRAM 芯片中，内存单元格在矩阵中排列，并使用 *x/y* 地址的系统选择它们。计算机不会通过 *x/y* 坐标在存储系统中定位单元格。需要其他电路将二进制内存地址转换为一对 *x/y* 值，从许多人中选择一个单元格。

The job of this circuitry is called _memory addressing_. Think of a computer memory system as a black box. On one side is a group of wires called address lines. On the other side is a group of wires called _data lines_. The number of wires in each group varies, depending on how much memory the system contains and how it’s organised. The address lines are used to select which memory location is to be read or written to. The data lines carry data either out of the system, when a value is read, or into the system, when a value is written. There are also a smaller number of wires called _control lines_. These have various functions, the most important of which is to specify whether a selected memory location is to be read from or written to.

> 该电路的作业称为* memory propstressing*。将计算机存储系统视为黑匣子。一侧是一组称为地址线的电线。另一侧是一组称为*data Lines *的电线。每个组中的电线数量各不相同，具体取决于系统所包含的内存和组织方式。地址行用于选择要读取或写入哪个内存位置。当值编写值时，数据线将数据带出系统，读取值或进入系统时。也有少量称为* Control Lines *的电线。这些功能各种功能，其中最重要的是指定是否要从或写入选定的内存位置。

In reality, although memory systems may consist of a single memory chip (as the Raspberry Pi’s does—more on that later) memory systems are generally put together from smaller units, either chips or groups of chips mounted on small circuit boards.

> 实际上，尽管内存系统可能由单个内存芯片组成(如 Raspberry Pi 所做的那样，稍后再使用)内存系统通常是从较小的单元，芯片或安装在小电路板上的芯片组组成的。

The best way to begin is to look at a very simple memory chip and how it works internally. The chip shown in Figure 3-2 doesn’t actually exist, but the general principles apply to nearly all memory chips of whatever size.

> 最好的开始方法是查看一个非常简单的内存芯片及其内部工作方式。图 3-2 中所示的芯片实际上并不存在，但是一般原理几乎适用于所有大小的所有存储芯片。

> ![[FIGURE 3-2:](#06_9781119183938-ch03.xhtml#rc03-fig-0002) How a memory chip addresses cells](./media/images/9781119183938-fg0302.png)

At the heart of the chip are 64 memory cells, arranged in a matrix of eight cells by eight cells. Each cell holds a single binary digit, which may be either a 1 or a 0. There are six address lines on the chip. Six is enough, because a six-digit binary number can express 64 different values, from 0 to 63.

> 芯片的核心是 64 个 Mem 细胞，在八个细胞的八个细胞基质中排列。每个单元都容纳一个二进制数字，可能是 1 或 0。芯片上有六个地址线。六个就足够了，因为六位数的二进制数可以从 0 到 63 表示 64 个不同的值。

Inside the chip are two decoders. A decoder is a logic element that accepts a binary number as an input value and uses it to select one, and only one, of several output lines. There is one output line for every binary value that the input lines can express. In our example, each decoder accepts a 3-bit binary number and selects one of eight output lines. A 3-bit binary number can express eight values, from 0 to 7. The decoder’s output lines are numbered 0 to 7. Put the binary value 101 (equivalent to 5 in our everyday decimal notation) on the input lines, and output line 5 is selected. (In [Figure 3-2](#06_9781119183938-ch03.xhtml#c03-fig-0002), this is shown for the _y_ decoder.)

> 芯片内有两个解码器。解码器是一个逻辑元素，它接受二进制数字作为输入值，并使用它来选择几个输出线中的一个，也只有一个。对于输入线可以表达的每个二进制值都有一个输出线。在我们的示例中，每个解码器都接受 3 位二进制数，并选择八个输出线之一。一个 3 位二进制数可以从 0 到 7 表示八个值。解码器的输出线编号为 0 到 7。将二进制值 101(等于我们的日常小数符号中的 5)放在输入线上，然后输出线 5 选择。(在[图 3-2]中(＃06*978111919183938-CH03.xhtml＃C03-FIG-0002)，这是_Y* 解码器显示的。)

Each of the two decoders handles one of the two axes (_x_ and _y_) in the matrix. The 6-bit binary address is split into two 3-bit parts. One 3-bit value is applied to the _x_ decoder and the other to the _y_ decoder. The cell at their _x,y_ intersection is the cell selected for reading or writing. The state of the read/write control line determines whether the selected cell will be read from or written to. When the control line is set to 0, a read is performed and whatever value is stored in the selected cell is placed on the data line. When the control line is set to 1, a write is performed and whatever value is on the data line is written to the selected cell.

> 两个解码器中的每一个都处理矩阵中的两个轴(*x* 和 *y*)之一。6 位二进制地址分为两个 3 位零件。一个 3 位值应用于 *x* 解码器，另一个将一个值应用于 *y* 解码器。_x 的单元格是选择用于读取或写作的单元格。读/写控制线的状态确定是从或写入所选单元格。当将控制线设置为 0 时，执行读取，并且在所选单元格中存储的任何值都放在数据线上。当将控制线设置为 1 时，将执行写入，并且数据线上的任何值都写入所选单元格。

## Combining Memory Chips into Memory Systems

The imaginary memory chip in [Figure 3-2](#06_9781119183938-ch03.xhtml#c03-fig-0002) can store and retrieve 1 bit at a time. Since the 1972 appearance of Intel’s ground-breaking 8008 CPU, however, computers use at least 8 bits at a time. Pulling an 8-bit byte out of a memory chip with a single data line can be done, but it would require eight memory-read operations to gather the whole 8 bits. A memory system like that would reduce the speed of any CPU to a crawl.

> [图 3-2]中的假想内存芯片(＃06_9781119183938-CH03.xHTML＃C03-FIG-0002)一次可以存储和检索 1 位。但是，自 1972 年出现英特尔开创性的 8008 CPU 以来，计算机一次至少使用 8 位。可以完成使用单个数据线的 Mem 芯片中的 8 位字节，但需要八个内存阅读操作才能收集整个 8 位。这样的内存系统将使任何 CPU 的速度降低到爬网的速度。

One common solution is to distribute 8 bits of data across eight physically separate chips. Figure 3-3 shows how this is done. This time, the scenario is real. The memory chips are the classic 2102 device, which was manufactured by several firms and was very popular in the 1970s. Each 2102 chip stores 1,024 bits. The 2102’s 10 address lines are connected in parallel, so all 10 address lines connect to all eight chips. An address placed on the address lines will select the corresponding bit in each chip. That bit will be delivered to each chip’s data pin. Because the chips work in parallel, a full 8-bit byte will be available on the row of 10 data pins with only one read from memory.

> 一种常见的解决方案是在八个物理分开的芯片上分配 8 位数据。图 3-3 显示了如何完成的。这次，情况是真实的。存储芯片是经典的 2102 设备，该设备由多家公司制造，在 1970 年代非常受欢迎。每个 2102 芯片存储 1,024 位。2102 的 10 条地址线并行连接，因此所有 10 条地址线都连接到所有八个芯片。地址线上放置的地址将选择每个芯片中的相应位。该位将传递到每个芯片的数据引脚。由于芯片并行工作，因此将在 10 个数据引脚的行上提供一个完整的 8 位字节，只有一个从内存中读取。
> ![[FIGURE 3-3:](#06_9781119183938-ch03.xhtml#rc03-fig-0003) A 1,024 × 8 memory system](./media/images/9781119183938-fg0303.png)

In [Figure 3-3](#06_9781119183938-ch03.xhtml#c03-fig-0003), eight chips, each containing 1,024 bits, are combined into the equivalent of a single memory chip holding 8,192 bits. But more to the point, the arrangement of bits in the memory system shown is 1,024 × 8, and not 8,192 × 1. A full 8-bit byte can be written to the memory bank with a single memory access—and read back just as quickly.

> 在[图 3-3](%EF%BC%8306_978111919183938-CH03.xhtml%EF%BC%83C03-Fig-0003) 中，将八个芯片组合为八个芯片，其中包含 1,024 位，相当于单个存储器芯片，持有 8,192 位。但更重要的是，所示的内存系统中位的排列为 1,024×8，而不是 8,192×1。可以将完整的 8 位字节写入带有单个内存访问的内存库，并回读书。迅速地。

> [!NOTE]
> that the memory system has 10 address lines. To access a single byte from among the 1,024, the value placed on the address bus must be able to express values from 0 to 1,023 in binary. 1,023 in binary is 1111111111. Ten binary digits require 10 address bus lines.

A group of digital lines connecting a memory system of any kind to a computer is called a _bus_. The 10 address lines in [Figure 3-3](#06_9781119183938-ch03.xhtml#c03-fig-0003), taken together, form the address bus. The eight data lines form the data bus. However many control lines the memory system may have (the number’s not important in this example) together make up the control bus.

> 将任何类型的内存系统连接到计算机的数字线路都称为 *bus*。[图 3-3]中的 10 行(＃06_9781119183938-CH03.XHTML＃C03-FIG-0003)一起形成地址总线。八个数据线构成数据总线。然而，许多控制线内存系统可能具有(在此示例中的数字并不重要)在一起组成控制总线。

The old 2102 chip was organised as 1,024 × 1 bit. This was a common organisation for a long time, but it was far from the only one. For example, there are SRAM chips that are organised in many other ways, from 256 × 4 in ancient times, to 1,031,072 × 16 today. (There are much larger memory chips in modern systems, but they’re all DRAM, which we get to shortly.)

> 旧的 2102 芯片组织为 1,024×1 位。这是一个很长一段时间的共同组织，但远非唯一的组织。例如，从古代的 256×4 到今天的 1,031,072×16，还有许多其他方式组织的 SRAM 芯片。(现代系统中有更大的内存芯片，但它们都是 DRAM，我们很快就可以了。)

The number of storage locations in a memory chip or system is called its _depth_. The number of bits at each storage location is a memory chip’s or system’s _width._ The size of a memory chip or system is the number of bits (not bytes!) that it contains. This is defined as the depth times the width.

> 内存芯片或系统中存储位置的数量称为其 *depth*。每个存储位置的位数是一个内存芯片或系统的_width。这被定义为宽度的深度时间。

Some examples:

- The old 2102 chip has a depth of 1,024 and a width of 1. Its size is 1,024 bits. - The old 6116 chip has a depth of 2,048 and a width of 8. Its size is 16,384 bits. - The modern Cypress 62167 chip has a depth of 1,048,580 and a width of 16. Its size is 16,777,280 bits.

> - 旧的 2102 芯片的深度为 1,024，宽度为 1。其尺寸为 1,024 位。- 旧的 6116 芯片的深度为 2,048，宽度为 8。其尺寸为 16,384 位。- 现代柏树 62167 芯片的深度为 1,048,580，宽度为 16。它的尺寸为 16,777,280 位。

The literal numbers describing a chip’s size become ungainly beyond a certain point. Powers of 2 do not convert to round numbers in decimal notation. In talking about memory chips and systems, we use shortcuts, as shown in Table 3-1.

> 描述芯片尺寸的文字数字变得毫无范围。2 的功率不会以十进制表示法转换为圆数。在谈论内存芯片和系统时，我们使用快捷方式，如表 3-1 所示。

[Table 3-1](#06_9781119183938-ch03.xhtml#rc03-tbl-0001) Conventional Terms for Powers of 2

---------------- --------------- ------ 2<sup>10</sup> 1,024 1K 2<sup>11</sup> 2,048 2K 2<sup>12</sup> 4,096 4K 2<sup>13</sup> 8,192 8K 2<sup>14</sup> 16,384 16K 2<sup>15</sup> 32,768 32K 2<sup>16</sup> 65,536 64K 2<sup>17</sup> 131,072 128K 2<sup>18</sup> 262,144 256K 2<sup>19</sup> 524,288 512K 2<sup>20</sup> 1,048,576 1M 2<sup>21</sup> 2,097,152 2M 2<sup>22</sup> 4,194,304 4M 2<sup>23</sup> 8,388,608 8M 2<sup>24</sup> 16,777,216 16M 2<sup>25</sup> 33,554,432 32M 2<sup>26</sup> 67,108,864 64M 2<sup>27</sup> 134,217,728 128M 2<sup>28</sup> 268,436,480 256M 2<sup>29</sup> 536,870,912 512M 2<sup>30</sup> 1,073,745,824 1G 2<sup>31</sup> 2,147,483,648 2G 2<sup>32</sup> 4,294,967,296 4G ---------------- --------------- ------

In recent years, there’s been an effort to distinguish these shortcuts (which refer to powers of 2) from the equivalent ISO prefixes (which refer to powers of 10) by introducing new shortcuts and prefixes. One kibibyte (1KiB) is the precise quantity 1,024 bytes, formerly referred to as a kilobyte (KB); under this scheme a kilobyte is now 1,000 bytes, just as a kilogram is 1,000 grams. Likewise, 1 mebibyte (1MiB) is the precise quantity 1,048,576 bytes and 1 gibibyte is the precise quantity 1,073,745,824 bytes. The new terms were defined in IEEE standard 1541, released in 2002. They are not widely used at this writing, but it’s worthwhile to keep them in mind, especially when reading the scientific and engineering literature.

> 近年来，通过引入新的快捷方式和前缀来区分这些快捷方式(指 2 的功能)与等效的 ISO 前缀(指 10 的权力)(指 10 的权力)。一个 kibibyte(1KiB)是精确的数量 1,024 字节，以前称为千字节(KB)；在此方案下，千字节现在为 1,000 个字节，就像一公斤为 1,000 克一样。同样，1 Mebibyte(1MIB)是精确的数量 1,048,576 字节，而 1 个 Gibibyte 是精确的数量 1,073,745,824 字节。新术语是在 2002 年发布的 IEEE 标准 1541 中定义的。在撰写本文中，它们并未广泛使用，但值得牢记它们，尤其是在阅读科学和工程文献时。

## Dynamic Random Access Memory (DRAM)

Each SRAM memory cell is a complete flip-flop circuit that, at a minimum, consists of four transistors. SRAM is fast, certainly the fastest mass-market memory technology ever devised. It’s still in use, when speed is required above all else. (We talk about how speed affects computer memory systems later in this chapter.) SRAM has two major disadvantages:

> 每个 SRAM 存储器单元是一个完整的触发器电路，至少由四个晶体管组成。SRAM 快速，当然是有史以来最快的大众市场 Mem 技术。当需要速度时，它仍在使用中。(我们讨论了速度在本章后面后期如何影响计算机内存系统。)SRAM 有两个主要缺点：

- It’s big, in terms of space per bit on a silicon chip. - It doesn’t shrink well, at least past a certain point.

> - 在硅芯片上的每位空间方面，它很大。- 它的收缩不好，至少超过了一定程度。

These limitations keep SRAM at a certain size and a certain cost per bit. This was recognised by researchers early on. In 1968, IBM fellow Robert H. Dennard proposed a radically different memory technology that did away with flip-flop data storage altogether. His memory technology stored bits as the presence or the absence of charge in a miniscule capacitor. The presence of charge represented a binary 1 and the absence of charge represented a binary 0. (This assignment of meaning is arbitrary and could be the reverse, as long the memory chip presents the proper voltage levels on its data lines.)

> 这些限制使 SRAM 保持一定尺寸和每位一定的成本。早期研究人员认可了这一点。1968 年，IBM 研究员罗伯特·H·丹纳德(Robert H. Dennard)提出了一种完全不同的 Mem 技术，该技术**完全消除了触发器数据存储**。他的 Mem 技术将位置为微小电容器中的存在或不存在电荷。电荷的存在代表二进制 1，而没有电荷代表二进制 0。(这种含义的分配是任意的，可能是相反的，只要内存芯片在其数据线上显示了适当的电压水平。)

A Dennard memory cell consists of only one transistor and one capacitor. Even with early fabrication technologies, this was less than half as large as an SRAM cell. Dennard also had a hunch that this technology could be scaled far more easily than SRAM. He meant that the physics of a Dennard cell would allow future fabrication technology to shrink individual cells far beyond what was possible with SRAM. He was right, to an extent that no one, not even Dennard himself, could have predicted in 1968.

> Dennard 存储单元仅由一个晶体管和一个电容器组成。即使有了早期制造技术，它的大小不如 SRAM 单元。丹纳德(Dennard)也有一个预感，该技术比 SRAM 更容易缩放。他的意思是，丹纳德细胞的物理学将使未来的制造技术能够缩小单个细胞的远远超出 SRAM 的可能性。在某种程度上，他是对的，在某种程度上，没有人，甚至没有丹纳德本人，在 1968 年可以预测。

With metal-oxide-semiconductor (MOS) transistors designed specifically for memory cell use, Dennard’s memory cells used far less power and generated far less waste heat. (This also helped with scaling—more bits could be placed on a single chip without fear of the chip `cooking` itself with its own heat.)

> 丹纳德的 Mem 细胞使用专门为 Mem 细胞使用的金属氧化物 - 气管导向器(MOS)晶体管，使用的功率要少得多，而产生的废物却少得多。(这也有助于缩放 - 可以将更多的碎屑放在单个芯片上，而不必担心会有自己的热量 `烹饪` 本身。)

The trade-off lay in the physics of charge stored in a capacitor: even in the best and purest silicon chip capacitors, over time a stored charge leaks away. Large capacitors can store so much charge that they can be used as batteries sometimes. The microscopic capacitors in Dennard’s scheme were so small that their charge leaked away in mere hundredths of a second. As with the ancient mercury delay-line memory systems, capacitor-based memory has to be refreshed (read and then rewritten) periodically. Thus, this memory technology is dynamic and goes by the name _dynamic random access memory_ (DRAM).

> 权衡取决于电容器中存储的电荷物理学：即使是最纯净，最纯净的硅芯片电容器，随着时间的推移，存储的电荷泄漏也会泄漏。大型电容器可以存储如此多的充电，有时可以用作电池。丹纳德方案中的微观电容器非常小，以至于他们的电荷仅在仅一秒钟内泄漏出来。与古老的水星延迟内存系统一样，基于电容器的内存必须定期刷新(然后读取并重写)。因此，此内存技术是动态的，并按名称 *DYNAMIC 随机访问 Mem*(DRAM)进行。

### How DRAM Works

Like both core memory and SRAM, DRAM memory chips are based on two-dimensional arrays of memory cells. Cells are addressed by _x_ and _y_ coordinates, using address decoders (look back at [Figure 3-2](#06_9781119183938-ch03.xhtml#c03-fig-0002)). Each individual cell consists of a single MOS transistor and a single capacitor, as shown in Figure 3-4. The three connections to the transistor are well known to electronics hobbyists: the gate is an electrical switch toggle that either connects the source to the drain or insulates them from each other. (The source and the drain are different in minor ways that do not affect this description.)

> 像核心内存和 SRAM 一样，DRAM 内存芯片也基于内存单元的二维阵列。单元格由 *x* 和 *y* 坐标解决，使用地址解码器(回顾[图 3-2](%EF%BC%8306_9781119183938-CH03.XHTML%EF%BC%83C03-fig-0002))。每个单独的单元由单个 MOS 晶体管和一个电容器组成，如图 3-4 所示。与晶体管的三个连接是电子业余爱好者的众所周知的：门是电气开关切换，可以将源连接到排水管或彼此绝缘。(来源和排水都以不影响此描述的较小方式不同。)

> ![[FIGURE 3-4:](#06_9781119183938-ch03.xhtml#rc03-fig-0004) DRAM cells](./media/images/9781119183938-fg0304.png)

[Figure 3-4](#06_9781119183938-ch03.xhtml#c03-fig-0004) shows four DRAM cells within a matrix of identical cells that may number into the billions. Cells are organised into rows and columns. A row (the horizontal dimension in [Figure 3-4](#06_9781119183938-ch03.xhtml#c03-fig-0004)) is linked by a common connection to all cell transistor gates called a _word line._ The word line is used to select one row from all rows in the memory chip. It `flips the switch` of all the MOS transistors in a row at once, causing them to either conduct or not conduct. Cells in each column are linked by a common connection to all transistor drain leads, called a _bit line._ At the end of each column’s bit line is a sense amplifier, which allows an almost unimaginably small unit of charge to be reliably interpreted as a 1 or a 0. In very general terms, the word lines are used to select cells and the bit lines are used to read and write data in cells.

> [图 3-4](%EF%BC%8306_9781119183938-CH03.XHTML%EF%BC%83C03-FIG-0004) 在相同细胞的基质中显示了四个 DRAM 单元，这些细胞可能会数到十亿个。细胞被组织成行和色谱柱。一行([图 3-4]中的水平尺寸(＃06_978111919183938-CH03.XHTML＃c03-fig-0004))与所有单元晶体管闸门的通用连接链接从内存芯片中的所有行中选择一行。它立即 `翻转所有MOS晶体管的开关` ，导致它们进行或不进行。每列中的单元格通过与所有晶体管排水管的共同连接链接，称为_bit Line。1 或 a0。在非常一般的术语中，单词线用于选择单元格，并且位线用于在单元格中读取和写入数据。

An MOS transistor is a solid-state switch. When the transistor is switched on, the capacitor is electrically connected to the bit line. When a cell’s transistor is switched off, the capacitor is isolated and charge (or lack of charge) is retained inside the capacitor. The charge leaks away in a fraction of a second unless the cell is refreshed. (More on that shortly.) The general idea is to select a cell and either read the state of its charge or write a charge state to the cell depending on whether a 1 or a 0 is to be written. This is not done individually, but in almost all cases to an entire row of cells at once.

> MOS 晶体管是固态开关。当打开晶体管时，电容器将电连接到位线。关闭电池的晶体管时，电容器是隔离的，并且电荷保留在电容器内部。除非细胞刷新，否则电荷在一秒钟的一秒钟内泄漏。(详细介绍这一点。)一般想法是选择一个单元格，要么根据要编写 1 还是 0 来读取其充电状态，要么将电荷状态写入单元格。这不是单独进行的，而是在几乎所有情况下都能一次完成整个单元。

DRAM operation has a familiar resemblance to the operation of core memory. DRAM, like core memory, uses destructive reads: the physics of reading the charge from the cell destroys the charge, which then has to be written back in a refresh operation. There are crucial differences; unlike core memory, which is static, DRAM needs to be refreshed regularly whether it is read or not.

> DRAM 操作与核心内存的操作有熟悉的相似之处。DRAM 与核心内存一样，使用破坏性读取：从单元中读取电荷的物理学会破坏电荷，然后必须在刷新操作中写回电荷。存在关键差异；与静态的核心内存不同，无论是否被读取，都需要定期刷新 DRAM。

These steps outline how a bit is read from a DRAM cell:

> 这些步骤概述了如何从 DRAM 单元中读取一些部分：

1. The cell’s bit line must be given an initial voltage (a precharge) that places it precisely halfway between a full charge on the capacitor and complete discharge. 2. When the precharge is complete, the precharge circuitry is disconnected and the bit line is switched to the sense amplifier. 3. The cell’s word line is selected. This turns on the MOS transistor of the selected cell (as well as all the other cells in the row) and connects the capacitor to the bit line. 4. The capacitor’s charge state affects the voltage on the bit line. If the capacitor has been charged, the bit line’s voltage goes up slightly. (Very slightly!) If the capacitor has been discharged, the bit’s line’s voltage goes down slightly. This change in voltage is exceptionally small and could amount to the difference of only one million electrons. 5. The sense amplifier converts this tiny change in voltage to a digital state of either 1 or 0. 6. The read operation destroys charge in the capacitor of the selected cell and all the other cells in the row. The state that was read must then be refreshed and written back to all cells in the row.

> 1.必须给电池线线的初始电压(预计)，该电压将其精确地置于电容器上的充满电和完全放电之间。2.预集完成后，将断开前电路，并将位线切换为感官放大器。3.选择了单元的单词行。这打开了所选单元的 MOS 晶体管(以及行中的所有其他单元格)，并将电容器连接到位线。4.电容器的电荷状态会影响位线上的电压。如果电容器充电，则位线的电压略有上升。(非常稍微！)如果电容器已排放，则位的电压略有下降。电压的这种变化非常小，可能只有一百万个电子的差异。5.感官放大器将电压的这种微小变化转换为 1 或 0 的数字状态。
> 6。读取操作破坏了所选电池电容器和行中所有其他单元的电荷。然后必须刷新被读取的状态并将其写回该行中的所有单元格。

Writing to a DRAM cell is done this way:

> 写入 DRAM 单元格是这样完成的：

1. The cell’s bit line is given a voltage corresponding to the value to be written to the cell. Typically, a 1-bit is represented by full voltage and a 0-bit by no voltage. 2. The cell’s word line is selected. This turns on the MOS transistor and allows the voltage applied to the bit line to pass into the cell’s capacitor.

> 1.给出了单元格线的电压，该电压与要写入单元格的值相对应。通常，一个 1 位由全电压表示，不电压为 0 位。2.选择了单元的单词线。这打开了 MOS 晶体管，并允许将电压施加到位线，以传递到单元的电容器中。

> [!NOTE]
> that DRAM cells are not accessed one at a time. Because they share a word line, an entire row of cells is accessed at once. We talk about `opening` a row (reading the values from an entire row of cells into temporary storage at the edge of the SDRAM chip) and `closing` a row (writing back any changes from the temporary storage to the cells themselves). (More on SDRAM later.) This sounds like it might be a waste of time, but in modern computers, system memory is almost always read and written in chunks called _cache lines,_ which are maintained in fast memory stores called _cache,_ as we explain later in this chapter.
> 一次不会访问一个 DRAM 单元。因为它们共享一条字线，所以会同时访问整行单元格。我们讨论 `打开` 一行(将整行单元格的值读入 SDRAM 芯片边缘的临时存储)和 `关闭` 一行(将临时存储中的任何更改写回单元格本身)。(稍后将详细介绍 SDRAM。)这听起来可能是在浪费时间，但在现代计算机中，系统内存几乎总是以称为*缓存线*的块进行读写，这些块在称为*缓存的快速内存存储中维护，*作为 我们将在本章后面解释。

A row is refreshed under two circumstances:

> 在两种情况下，一排被刷新：

- Any time a cell in that row is read - Every 5 to 50 milliseconds, to prevent electron leakage from destroying cell data

> - 任何时候读取该行中的单元格 - 每 5 至 50 毫秒，以防止电子泄漏破坏细胞数据

Rows are refreshed simply by reading the state of the cells in the row and then immediately writing it back to the cells. This reading and writing is not done through the CPU, or in fact with any involvement of the CPU at all. A separate subsystem called a _memory controller_ handles the refresh operation and a great many other housekeeping details that allow the CPU to access memory with as little delay as possible. Taken together, the memory controller and the DRAM chips that it manages are called a memory system.

> 简单地通过阅读行中的单元格，然后立即将其写回单元格，将行刷新。这种阅读和写作不是通过 CPU 或 CPU 的任何参与来完成的。一个称为 *memory Controller* 的单独子系统处理刷新操作，以及许多其他家务详细信息，允许 CPU 尽可能少地访问内存。综上所述，内存控制器和它管理的 DRAM 芯片称为内存系统。

The speed with which data moves between memory systems and the CPU can dominate the overall performance of the entire computer. Memory system performance is a complex business, with two different metrics that are often in tension with one another:

> 数据在内存系统和 CPU 之间移动的速度可以主导整个计算机的整体性能。内存系统性能是一项复杂的业务，具有两个不同的指标，它们通常彼此紧张：

- **Access time:** The time it takes between the moment a memory access is requested by the CPU and the time the access is completed - **Bandwidth:** The amount of data transferred to or from memory per unit time

> - **访问时间：**在 CPU 请求内存访问的那一刻与访问完成的时间 - **带宽的时间：**

Much of the rest of this chapter addresses issues related to improving the effective access time and bandwidth experienced by the CPU when accessing memory.

> 本章的其余大部分内容涉及与改善 CPU 访问内存时经历的有效访问时间和带宽有关的问题。

### Synchronous vs. Asynchronous DRAM

DRAM has dominated computer memory systems since 1980 or so, and dominates them to this day. Quite apart from scaling (that is, making DRAM cells smaller), DRAM has been improved in many ways. Perhaps the most dramatic improvement was the move to synchronous DRAM (SDRAM) in the late 1990s.

> 自 1980 年左右以来，DRAM 一直主导计算机存储系统，并将其主导到今天。除了缩放(即使 DRAM 细胞变小)以外，DRAM 在许多方面得到了改善。也许最引人注目的改进是 1990 年代后期转向同步 DRAM(SDRAM)。

Prior to that time, all DRAM was asynchronous. The operation of asynchronous DRAM is managed directly from the memory controller. The controller can open a row by presenting a row address on the unidirectional data bus and bringing the row address strobe (RAS) command line low; having done so, it can read or write cells within the open row by presenting a column address and bringing the column address strobe (CAS) command line low. A bidirectional data bus is used to transfer data to or from the DRAM; the direction of travel is determined by the write enable (WE) and output enable (OE) command lines. An asynchronous DRAM device starts performing an operation as soon as it detects an RAS or CAS transition, but requires a finite amount of time (called _latency_) to perform each operation. The device’s datasheet will typically contain timing parameters indicating how long (in nanoseconds) we must wait between, for example, opening a row and starting an access to a column in that row (the RAS to CAS latency), or starting a read access to a column and expecting to receive valid data on the data bus (the CAS to valid data out latency, or just CAS latency). The memory controller must be programmed with these timing parameters for memory operations to occur reliably.

> 在此之前，所有 DRAM 都是异步的。异步 DRAM 的操作直接从内存控制器管理。控制器可以通过在单向数据总线上显示行地址并将行地址弹声(RAS)命令行低点打开行。这样做之后，它可以通过呈现一个列地址并将列地址 strobe(cas)命令行低点读取或写入单元格。双向数据总线用于将数据传输到 DRAM 或从 DRAM 传输；旅行方向由写入启用(WE)和输出启用(OE)命令行确定。异步 DRAM 设备一旦检测到 RAS 或 CAS 转换，就会开始执行操作，但需要有限的时间(称为 *latency*)才能执行每个操作。设备的数据表通常包含定时参数，指示我们必须在之间进行多长时间(在纳秒中)等待，例如，开设一行并启动对该行中的列访问(RAS 到 CAS 延迟)，或启动读取访问访问权限的访问一列并希望接收有关数据总线的有效数据(CAS 以有效数据延迟或仅 CAS 延迟)。内存控制器必须使用这些定时参数编程，以使内存操作可靠。

A critical disadvantage of asynchronous DRAM is that it is only possible to perform one memory access operation at a time. While we’re waiting for a row to open, the data bus is completely idle, `wasting` potential throughput. Fast page mode (FPM) DRAM, which became popular around 1995, mitigates this problem to some degree by allowing a burst of multiple accesses to an open row (multiple CAS transitions per RAS transition), but inefficiency remains when switching between rows.

> 异步 DRAM 的一个关键缺点是只能一次执行一个内存访问操作。当我们等待一行打开时，数据总线完全闲置，`浪费` 潜在的吞吐量。快速页面模式(FPM)DRAM 在 1995 年左右变得流行，通过允许多次访问开放行(每个 RAS 过渡)多次访问来减轻此问题，但是在行之间切换时，效率低下。

The eventual solution to the wasted throughput problem was the introduction of SDRAM. The key innovation in SDRAM is the splitting of the DRAM cell matrix into multiple independent banks, which can be thought of almost as separate asynchronous DRAMs. Fine-grained control of these banks is delegated to logic inside the SDRAM itself, running off a clock (and therefore `synchronous` ) generated by the memory controller. The memory controller passes commands to the logic inside the SDRAM using a unidirectional control bus*,* which takes the place of the address bus and control signals used by asynchronous DRAM. By maintaining a short queue of upcoming memory access requests from the CPU and other bus master peripherals, the memory controller is able to schedule the commands that it issues so as to hide the latency of precharge and row-open operations, potentially keeping the data bus completely busy. For example, while receiving the results of a multi-cycle burst read from an address in bank 0, the controller might issue a command to open a row in bank 1 and then a command to close the current row in bank 2, precharging that bank so that it is ready for a future row-open command. This technique of overlapping operations on multiple banks is referred to as _pipelining_ and it’s the main contributor to the improved performance of SDRAM over asynchronous DRAM.

> 浪费吞吐量问题的最终解决方案是引入 SDRAM。**SDRAM 的关键创新是将 DRAM 细胞基质分解为多个独立的银行，这几乎可以视为单独的异步 DRAM。**对这些银行的细粒度控制被委派给 SDRAM 本身内部的逻辑，从内存控制器生成的时钟(因此 `同步` )。内存控制器使用单向控制总线**将命令传递到 SDRAM 内部的逻辑，该**取代了异步 DRAM 使用的地址总线和控制信号。通过维护 CPU 和其他总线大师外围设备的即将到来的内存访问请求的简短队列，内存控制器能够安排其发出的命令，以隐藏 PRECHARGE 和 ROW-OPEN 操作的延迟，并有可能保持数据总线完全忙。例如，当收到从银行 0 地址读取多周期爆发的结果时，控制器可能会发出命令以在银行 1 中打开一行，然后在银行 2 中关闭当前行，并预先进行该银行因此，它可以准备好进行未来的行命令。这种在多个银行重叠操作的技术称为 *PIPELINGING*，这是 SDRAM 在异步 DRAM 上改善性能的主要因素。

To gain more flexibility in how it pipelines memory operations, the memory controller may, under some circumstances, choose to reorder the requests in its queue. There is generally a signalling scheme between the CPU and the memory controller to help the controller understand which accesses can be reordered safely. The controller typically also reorders requests to group multiple reads and writes together, minimising the number of bus turnarounds, where the direction of flow on the data bus changes, necessitating a small amount of dead time.

> 为了获得更大的灵活性，它如何管道内存操作，在某些情况下，内存控制器可以选择在其队列中重新排序请求。通常，CPU 和内存控制器之间有一个信号传导方案，以帮助控制器了解哪些访问可以安全地重新排序。控制器通常还会要求将多个读取和写入一起分组，从而最大程度地减少总线周转数，在此过程中，数据总线上的流动方向发生变化，需要少量的停留时间。

Operations on the individual banks inside the SDRAM device have characteristic latencies, just as with asynchronous DRAM. Once again, these timing parameters are typically specified in the datasheet for the device; in the case of SDRAM they’re generally specified as a number of clock cycles at the device’s maximum supported clock frequency, rather than directly in nanoseconds. The memory controller programs these parameters into the SDRAM’s internal logic at boot-up time, and relies on them to know how many cycles to wait between issuing commands on the bus and receiving data.

> SDRAM 设备内部单个银行的操作具有特征性的潜伏期，就像异步 DRAM 一样。再次，这些定时参数通常在设备的数据表中指定。在 SDRAM 的情况下，通常将其指定为设备最大支撑时钟频率的许多时钟循环，而不是直接在纳秒中。内存控制器在引导时间将这些参数编程到 SDRAM 的内部逻辑中，并依靠它们知道在总线上发出命令和接收数据之间等待多少个周期。

### SDRAM Columns, Rows, Banks, Ranks and DIMMs

In the previous section you saw that an SDRAM device is composed internally of a collection of equal-sized independent banks. Each bank is structured as a matrix of a number of rows, and the bits in each row are grouped into columns of a specific width. A row in a modern SDRAM chip contains tens of thousands of bits, and a column is typically 8, 16 or 32 bits wide. A row and a column address together specify a starting point within the bank’s grid of memory cells and the cells beginning at that starting point are read and written as a unit, out to the width of the column.

> 在上一节中，您看到 SDRAM 设备由一组等同于独立银行的集合组成。每个银行的结构为许多行的矩阵，每行中的位分为特定宽度的列。现代 SDRAM 芯片中的一排包含数万位，一列通常为 8、16 或 32 位。一个行和一个列地址一起指定了存储单元格中的一个起点，而从该起点开始的单元开始并写入单位，将其写入列的宽度。

Typically there are 2, 4 or 8 banks on each chip. The banks themselves may be of different sizes for different chips. A common 128MB SDRAM memory chip contains 8 banks, each of which contains 16,384 rows of 1,024 columns of 8 bits. The total number of bits in the chip is thus 8 banks × 16,384 rows × 1,024 columns × 8 bits per column = 1,073,745,824 bits. It’s called a 128MB chip because 1,073,745,824 bits divided by 8 bits per byte is 134,217,728 bytes. (Refer to [Table 3-1](#06_9781119183938-ch03.xhtml#c03-tbl-0001) to see why that number is considered to be 128MB.)

> 通常，每个芯片上有 2、4 或 8 个银行。银行本身对于不同的芯片可能不同。一个常见的 128MB SDRAM 存储器芯片包含 8 个银行，每个银行包含 16,384 行 1,024 列 8 位。因此，芯片中的位总数为 8 个银行 ×16,384 行 ×1,024 列 ×8 位，每列= 1,073,745,824 位。它称为 128MB 芯片，因为 1,073,745,824 位除以 8 个字节为 134,217,728 字节。(请参阅[表 3-1](%EF%BC%8306_9781119183938-CH03.XHTML%EF%BC%83C03-TBL-0001)，了解为什么该数字被认为是 128MB。)

SDRAM chips are organised as they are as a consequence of how the chips themselves are combined into memory systems. For desktop and conventional laptop computers, multiple chips are assembled onto small `stick` printed circuit modules. Until the late 1990s these were single in-line memory modules (SIMMs) because the corresponding edge connector contacts on both sides of the printed circuit board were identical and tied together. (It does not mean, as some think, that memory chips are present on only one side of the module!) SIMMs can transfer 32 bits to or from the data bus at one time.

> SDRAM 芯片是组织的，因为它们是如何将芯片本身合并到存储系统中的结果。对于台式机和常规笔记本电脑，将多个芯片组装到小 `棒` 印刷电路模块上。直到 1990 年代后期，这些都是单个内存模块(SIMM)，因为印刷电路板两侧的相应边缘连接器触点是相同的并绑在一起的。(正如某些人认为的那样，这并不意味着模块的一侧仅存在内存芯片！)SIMMS 可以一次转移 32 位往返数据总线。

Having the same signals on both sides of the edge connectors on SIMMs limits the number of electrical connections that can be made between the SIMM and the data bus. A SIMM typically has 72 connectors on its edge. Making the two sides of the edge connector independent at least doubles the number of connections that can be made between a module and the data bus. With this change, modules became dual in-line memory modules (DIMMs), which have dominated desktop and laptop memory systems since 2000 or so. DIMMs typically have 168 or more separate connectors, and transfer 64 bits to or from the data bus at once.

> 在 SIMMS 上的边缘连接器的两侧具有相同的信号，限制了 SIMM 和数据总线之间可以制作的电气连接的数量。SIMM 通常在其边缘有 72 个连接器。使边缘连接器的两个侧面独立至少翻了一番，可以使模块和数据总线之间可以进行的连接数量增加一倍。通过此更改，模块成为双线内存模块(DIMM)，自 2000 年左右以来一直主导台式机和笔记本电脑内存系统。DIMM 通常具有 168 个或更多单独的连接器，并立即将 64 位转移到数据总线。

For physical compactness, many laptops and netbooks use a different, smaller type of DIMM module called a small outline DIMM (SODIMM). Seventy-two-pin SODIMMs are 32 bits wide and 144-pin SODIMMs are 64 bits wide.

> 为了进行物理紧凑，许多笔记本电脑和上网本都使用不同类型的 DIMM 模块，称为小型轮廓 DIMM(SODIMM)。72 pin sodimms 宽 32 位，144 针 sodimms 宽 64 位。

On a modern DIMM, each side of the module is a separate bus-addressable memory block called a _rank_. A rank is defined as a group of memory chips sharing the same chip-select control line. A rank’s chips thus appear on the data bus together. Each chip within the rank contributes 8 bits to the 64 bits that the rank reads or writes at once.

> 在现代 DIMM 上，模块的每一侧都是一个单独的 Bus-Address-Address-Address 内存块，称为 *rank*。等级定义为一组内存芯片，共享相同的芯片选择控制线。因此，等级的芯片一起出现在数据总线上。等级内的每个芯片对等级读或写入的 64 位贡献了 8 位。

Figure 3-5 shows how a typical DIMM is organised. Precise numbers aren’t stated because different modules are built from SDRAM chips of different sizes and different internal organisation.

> 图 3-5 显示了如何组织典型的 DIMM。没有说明精确数字，因为不同的模块是由不同大小和不同内部组织的 SDRAM 芯片构建的。

> ![[FIGURE 3-5:](#06_9781119183938-ch03.xhtml#rc03-fig-0005) How a typical DDR SDRAM DIMM is organised](./media/images/9781119183938-fg0305.png)

### DDR, DDR2 DDR3 and DDR4 SDRAM

The first generation of ordinary SDRAM is today referred to as _single data rate_ (SDR) SDRAM. The term only became necessary in the late 1990s, when improvements to SDRAM technology gave us _double data rate_ (DDR) SDRAM. SDR SDRAM is called `single data rate` because it can transfer a single data word per clock cycle. The size of the data word depends on the design of a specific memory system (specifically the number of wires in the data bus linking the memory controller to the SDRAM). In most modern desktops and laptops, it’s 64 bits. In the early Raspberry Pi models, it’s 32 bits. For the Raspberry Pi 3, it’s 64 bits.

> 普通 SDRAM 的第一代被称为 *single 数据速率*(SDR)SDRAM。该术语仅在 1990 年代后期才有必要，当时 SDRAM 技术的改进为我们提供了*双数据速率*(DDR)SDRAM。SDR SDRAM 被称为 `单数据速率` ，因为它可以每个时钟周期传输单个数据字。数据字的大小取决于特定内存系统的设计(特别是将存储器控制器链接到 SDRAM 的数据总线中的电线数)。在大多数现代台式机和笔记本电脑中，它是 64 位。在早期的 Raspberry Pi 型号中，它是 32 位。对于 Raspberry Pi 3，它是 64 位。

In DDR SDRAM, two memory transfers occur for each clock cycle. In SDR technology, a memory transfer happens on the rising edge of each clock cycle. In DDR, memory transfers happen on both the rising edge and the falling edge of each clock cycle, essentially doubling the rate at which memory transfers happen. This is called _double pumping_. See Figure 3-6.

> 在 DDR SDRAM 中，每个时钟周期都会发生两个内存传输。在 SDR 技术中，每个时钟周期的上升边缘都会发生内存传递。在 DDR 中，内存传输都发生在每个时钟周期的上升边缘和下降边缘上，从本质上讲是内存传输发生的速率的一倍。这称为_双泵。见图 3-6。
> ![[FIGURE 3-6:](#06_9781119183938-ch03.xhtml#rc03-fig-0006) SDR vs. DDR timing](./media/images/9781119183938-fg0306.png)

Increasing the memory transfer rate by increasing the clock rate causes various electrical problems. Higher clock rates for anything increase power usage and waste heat. Reliably driving a high-speed clock across a board introduces challenging signal integrity issues for chip and PCB designers; sooner or later you reach a limit in terms of edge rate; that is, the number of times a wire can change from 0 to 1 or 1 to 0 in a second. In an SDR system, the clock changes twice per cycle (from 0 to 1 and back again), whereas no data line changes more rapidly than once per cycle; in such a system you hit the wall on clock edge rate before data edge rate. By allowing the data lines to change twice per cycle, DDR signalling makes the most of a given technology’s capabilities.

> 通过增加时钟速率来提高 Mem 转移率会导致各种电气问题。任何事物的时钟速率都会增加功率使用和废热。可靠地驾驶高速时钟跨板引入了芯片和 PCB 设计师的挑战性信号完整性问题；迟早您在边缘利率方面达到极限；也就是说，一秒钟内电线可以从 0 到 1 或 1 变为 0 的次数。在 SDR 系统中，时钟每周周期的变化两次(从 0 到 1 又一次)，而没有数据线的变化速度比每个周期更快。在这样的系统中，您在数据边缘速率之前按时钟边缘速率击中墙。通过允许数据线更改每个周期两次，DDR 信号传导充分利用了给定技术的功能。

At around the time of the introduction of DDR SDRAM, the internal speed at which SDRAM devices operated (as distinct from the external interface speed) stopped increasing significantly. Why? Well, the speed at which you can read a row of cells from the array is dominated by signal propagation time, which is determined by wire length and the time required for the sense amplifiers to detect the faint charge on the bit lines. Successive generations of SDRAM devices pack more storage into the same area, instead of getting smaller, and the charges stored on the capacitors in the array become smaller and harder to detect. As a result, process shrinkage, which has done so much to sustain Moore’s Law for logic devices, has had little effect on the internal speed of SDRAM.

> 在引入 DDR SDRAM 时，SDRAM 设备操作(与外部接口速度不同)的内部速度显着增加。为什么？好吧，您可以从数组中读取一排单元的速度由信号传播时间主导，该信号传播时间由电线长度和感觉放大器在位线上检测微弱电荷所需的时间确定。连续的几代 SDRAM 设备将更多的存储空间包含到同一区域，而不是变小，并且存储在阵列中的电容器上的电荷变得更小，难以检测。结果，为维持摩尔的逻辑设备定律所做的很多工作，对 SDRAM 的内部速度几乎没有影响。
