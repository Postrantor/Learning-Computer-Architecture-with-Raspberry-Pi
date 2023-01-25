# Moore’s Law

In 1975, Intel computer engineer Gordon E. Moore observed that the number of transistors on an integrated circuit (IC) doubles every two years. It was just an observation based solely on the history of semiconductor fabrication up to that time, but the remark remained uncannily accurate for literally decades. Although some analysts had long predicted that Moore’s Law would soon run into some fundamental physical limitations, it was not until 2015 that Intel confirmed that progress in shrinking circuit fabrication had slowed down. Moore himself has stated that Moore’s Law would cease to apply by 2025.

> 1975 年，英特尔计算机工程师 Gordon E. Moore 观察到，集成电路(IC)上的晶体管数量每两年翻倍。直到那时，这只是一个仅基于半导体制造历史的观察，但是几十年来，这一说法仍然不准确。尽管一些分析师长期以来一直预测，摩尔的定律很快就会遇到一些基本的身体局限性，但直到 2015 年，英特尔才确认，缩小电路制造的进展已经减慢了。摩尔本人表示，摩尔的法律将于 2025 年不再申请。

Fortunately, the internal bandwidth of SDRAM devices was incredibly high already. Recall that opening a row involves reading tens of thousands of bits simultaneously into temporary storage at the edge of the SDRAM chip. Even with a relatively slow internal speed, say one access every 10 nanoseconds (ns), that’s still a lot of bandwidth, and the results end up held right where you want them, at the edge of the silicon die next to the pads. The only question is how to sensibly interface that data rate to the bus, which may support a transfer every 1ns or less.

> 幸运的是，SDRAM 设备的内部带宽已经非常高。回想一下，打开一排涉及将数万位同时读取到 SDRAM 芯片边缘的临时存储中。即使内部速度相对较慢，也要说，每 10 纳秒(ns)一次访问仍然是很多带宽，并且结果最终在您想要的地方保持在您想要的地方，在硅的边缘处于底座旁边。唯一的问题是如何将数据速率合理地接口到总线，这可能支持每 1ns 或更少的转移。

The solution adopted by DDR, and its successors DDR2 and DDR3, is to require that memory accesses occur as short bursts running from a starting address to some number of adjacent addresses. After the internal logic in the SDRAM has read the first column, subsequent columns from the same row are available for `free` without requiring another time-consuming access to the array. This process is called _prefetching_. (See Figure 3-7.) With 32-bit SDR memory you could efficiently read a single 32-bit word, followed by another 32-bit word from another location in memory, but DDR forces you to take two adjacent 32-bit words, one on the rising edge and one on the falling edge of the clock cycle. DDR2 doubles this requirement to four adjacent words and supports data rates up to 800MHz (or equivalently clock speeds up to 400MHz). DDR3 doubles the requirement again to eight words and supports data rates of 1.6GHz or higher. In each case the faster bus is `fed` from the temporary storage at the edge of the chip, and the increasing minimum burst requirement is an acknowledgement that the array simply isn’t nimble enough to keep up with full-speed demands for random access.

> DDR 及其后继 DDR2 和 DDR3 采用的解决方案是要求内存访问发生，因为短爆发从起始地址运行到一些相邻地址。在 SDRAM 中的内部逻辑读取了第一列之后，同一行的后续列可用于 `免费` ，而无需其他耗时的访问阵列。此过程称为 _prefetching_。(请参见图 3-7。)使用 32 位 SDR 内存，您可以有效地读取一个 32 位单词，然后是内存中另一个位置的另一个 32 位单词，但是 DDR 迫使您拿出两个相邻的 32 位单词，一个在上升边缘，一个在时钟周期的下降边缘上。DDR2 将此要求翻了一番，将四个相邻单词和支持的数据速率支持高达 800MHz(或等效的时钟速度高达 400MHz)。DDR3 再次将需求翻了一番，并支持 1.6GHz 或更高的数据速率。在每种情况下，更快的总线都是从芯片边缘的临时存储中 `馈入` 的，而增加的最小爆发要求是确认该数组根本不足以满足对随机访问的全速需求。

> ![[FIGURE 3-7:](#06_9781119183938-ch03.xhtml#rc03-fig-0007) DDR2 prefetching](./media/images/9781119183938-fg0307.png)

It’s possible, of course, that the CPU does not need those four consecutive data words, but only the first. If the CPU reads a data word from DDR memory at some address and then immediately requests another word from an address somewhere else in memory, the last three data words are still sent over the bus, but are discarded by the memory controller. DDR memory had the ability to terminate a burst early, but this feature was dropped from DDR2 and later generations. This might seem wasteful, except that most of the time the CPU requests memory words in sequence starting at some address. This happens because in modern computers, most reads from system memory are to load cache lines into the CPU’s cache. (You’ll read more on cache later in this chapter.) Sequential reads are the norm, and `random` reads are an increasingly uncommon exception, as CPU cache size increases.

> 当然，CPU 可能不需要这四个连续的数据单词，而是第一个数据。如果 CPU 在某个地址上从 DDR 存储器中读取数据字，然后立即从内存中其他某个地方的地址请求另一个单词，则最后三个数据单词仍在总线上发送，但被内存控制器丢弃。DDR 内存具有尽早终止突发的能力，但是此功能从 DDR2 和后来的世代删除。这似乎很浪费，除了大多数情况下，CPU 从某个地址开始请求 Mem 单词。之所以发生这种情况，是因为在现代计算机中，大多数从系统内存中的读取都是将缓存线加载到 CPU 的缓存中。(您将在本章稍后稍后阅读有关缓存的更多信息。)顺序读取是规范，随着 CPU 缓存大小的增加，`随机` 读取是越来越罕见的例外。

In addition to the protocol changes described earlier, each DDR generation has included changes to the physical signalling scheme aimed at increasing transfer speeds and a reduction in operating voltage, which reduces power draw and waste heat. The improvement is significant: DDR3 memory uses 30 percent less power than DDR2 memory.

> 除了前面描述的协议更改外，每个 DDR 的生成还包括对旨在提高传输速度和降低工作电压的物理信号方案的更改，从而减少了功率吸收和废热。改进很重要：DDR3 存储器的功率比 DDR2 存储器少 30％。

The latest generation of SDRAM appeared in late 2014: DDR4. The operating voltage has been reduced to 1.2V (as compared to 1.5V for DDR3) enabling higher-density modules with greater transfer speeds. The range of operating frequencies increased, to 800 to 1600MHz, compared to 400 to 1067MHz for DDR3. Low-voltage versions of DDR4 memory modules operate at voltages as low as 1.05V, providing even greater power efficiency and lower waste heat. DDR4 SDRAM uses up to 40 percent less power than DDR3 modules. Module density of current devices has increased to 4GB over DDR3’s 1GB.

> 最新一代 SDRAM 出现在 2014 年底：DDR4。工作电压已降低到 1.2V(DDR3 的 1.5V)，使得具有更大传输速度的高密度模块。运行频率的范围增加到 800 至 1600MHz，而 DDR3 的工作频率范围为 400 至 1067MHz。DDR4 存储模块的低压版本的电压低至 1.05V，提供了更高的功率效率和降低的废热。与 DDR3 模块相比，DDR4 SDRAM 的功率少 40％。当前设备的模块密度已在 DDR3 的 1GB 上增加到 4GB。

### Error-Correcting Code (ECC) Memory

If you look at modern DIMMs, particularly those intended for use in servers or other high-reliability applications, you may notice that there are sometimes nine chips on each side. Even if there are only eight chips, there will probably be an empty space with printed circuit pads for a ninth chip. The ninth chip has an optional but very useful function: error correction.

> 如果您查看现代 DIMM，尤其是用于服务器或其他高可靠性应用程序的 DIMM，您可能会注意到每侧有时有 9 个芯片。即使只有八个芯片，也可能会有一个空的空间，上面印有第九芯片的印刷电路垫。第九芯片具有可选但非常有用的功能：误差校正。

When we talk about computer memory, we generally assume that data written into memory will remain there, as written, for as long as the memory system has power. Alas, in reality, bit values in memory sometimes change `on their own` , without warning. Recall that a bit in any DRAM memory chip of any type is really nothing more than a vanishingly small quantity of electrical charge in a minuscule capacitor. Unavoidable leakage causes this charge to lessen and dissipate in a very small amount of time, which is why all DRAM must be refreshed periodically.

> 当我们谈论计算机内存时，我们通常假设写入内存中的数据将如书面保留在那里，只要内存系统具有电源。las，实际上，Mem 中的位价值有时会 `自行` 变化，而无需警告。回想一下，在任何类型的任何 DRAM 内存芯片中，实际上只不过是在微小电容器中消失了少量的电荷。不可避免的泄漏会导致此电荷在很小的时间内减少和消散，这就是为什么必须定期对所有 DRAM 进行刷新的原因。

Unfortunately, this leakage is not the only way that DRAM memory cells discharge. The charge itself is so small that subatomic particles from outside the computer can discharge a memory cell instantly. A fast neutron generated by a cosmic ray striking the memory hardware somewhere can discharge a cell and cause a memory error. This doesn’t happen as often as we once thought (memory cells are small targets and cosmic rays are relatively uncommon) but when it happens, corrupt memory can bring the computer to a halt.

> 不幸的是，这种泄漏并不是造成 Mem 细胞排出的唯一途径。电荷本身是如此之小，以至于来自计算机外部的亚原子颗粒可以立即放电。由宇宙射线撞击内存硬件的宇宙射线生成的快速中子可以放电单元格并导致内存错误。这种情况并不像我们曾经想到的那样频繁(内存单元是小目标，并且宇宙射线相对罕见)，但是当发生这种情况时，损坏的内存会使计算机停止。

A technology called error-correcting code (ECC) memory was developed to prevent memory corruption from background radiation. The mechanism used in modern computer memory, called a Hamming code, was developed in 1950 by Richard Hamming. There are many ways to implement a Hamming code in memory. The scheme used today is capable of detecting two simultaneous `bad bits` in a 64-bit data word. Better still, the system can correct single-bit errors within a 64-bit data word. Because of these two functions, the scheme is called single-error correcting and double-error detecting (SECDED).

> 开发了一种称为错误校正代码(ECC)内存的技术，以防止背景辐射的内存损坏。Richard Hamming 于 1950 年开发了现代计算机存储器中使用的机制，称为锤式代码。有很多方法可以在内存中实现锤式代码。今天使用的计划能够在 64 位数据字中检测两个同时的 `不良位` 。更好的是，系统可以在 64 位数据字中纠正单位错误。由于这两个函数，该方案称为单纠正和双校正检测(secded)。

The mathematics behind SECDED Hamming codes is subtle and beyond the scope of this book. In essence, an additional 8 bits are stored for every 64-bit word in a memory system. This is the purpose of the ninth SDRAM chip on ECC memory DIMMs. Every time a new value is written to a memory location, a new Hamming code for that location is generated and written to the `extra` 8 bits. Every time a memory location is read, the memory controller hardware tests the value read against the Hamming code stored in the extra bits. If the test fails, we know that an error has occurred in that memory location since the Hamming code was last calculated. The computer can then take some sort of action, which may include logging the error, alerting the operating system or, in some cases (for single-bit errors), transparently correcting the error.

> Secded Hamming 代码背后的数学是微妙的，并且超出了本书的范围。从本质上讲，在存储系统中，每 64 位单词都存储了另外的 8 位。这是 ECC 内存 DIMM 上第九 sdram 芯片的目的。每当将新值写入内存位置时，就会生成该位置的新锤码代码并将其写入 `额外` 8 位。每次读取内存位置时，内存控制器硬件都会针对存储在额外位中的锤式代码读取的值读取。如果测试失败，我们知道自上次计算的锤式代码以来，该内存位置发生了错误。然后，计算机可以采取某种操作，其中可能包括记录错误，警告操作系统，或者在某些情况下(对于单位错误)，透明地纠正了错误。

The extra DRAM chip is not free. Also, hardware that generates the codes and performs the tests imposes its own overhead, in the order of 2 percent to 3 percent. In systems where reliability is essential, the cost and overhead are well worth it. Most desktop systems do not support ECC, which is why the DIMMs used in common desktops and laptops do not include the ninth SDRAM chip in each memory rank.

> 额外的 DRAM 芯片不是免费的。同样，生成代码并执行测试的硬件以 2％至 3％的订单施加了自己的开销。在可靠性至关重要的系统中，成本和开销非常值得。大多数台式机系统不支持 ECC，这就是为什么在通用台式机和笔记本电脑中使用的 DIMM 不包括每个内存等级中的第九个 SDRAM 芯片的原因。

## The Raspberry Pi Memory System

The Raspberry Pi board is not an inherently mobile device, but it’s based on parts created for use in smartphones and other portable devices like tablets. Small size and low power are the primary virtues in mobile design. Not many desktop computers can be run from small `wall wart` power adapters but Raspberry Pi can, because of its use of mobile-device parts.

> Raspberry Pi 板不是固有的移动设备，而是基于用于智能手机和其他便携式设备(例如平板电脑)的零件。小尺寸和低功率是移动设计中的主要优点。由于使用移动设备零件，因此不多的台式计算机可以从小型 `壁疣` 电源适配器运行，但是 Raspberry Pi 可以运行。

The original Raspberry Pi Model B’s memory system is a 400MHz LPDDR2 single-chip device containing 512MB of memory. The memory is organised as 128M × 32; that is, 134,217,728 32-bit words, or 4,294,967,296 bits. Internally, the device’s 4 gigabits are divided into 8 banks, each bank containing 512 megabits in a matrix of 16,384 rows, each of which is 4,096 bytes wide. Like all LPDDR2 memory it has a minimum burst size of 4.

> 原始的 Raspberry Pi M 型的内存系统是一个 400MHz LPDDR2 单芯片设备，其中包含 512MB 的内存。内存为 128m×32;也就是说，134,217,728 32 位单词，或 4,294,967,296 位。在内部，该设备的 4 千兆位分为 8 个银行，每个银行中包含 512 兆位的矩阵，矩阵为 16,384 行，每行宽为 4,096 个字节宽。像所有 LPDDR2 内存一样，它的最小突发尺寸为 4。

### Power Reduction Features

The primary way to reduce power consumption on SDRAM chips is to reduce their operating voltage. The low-power LPDDR2 memory chip used in the Raspberry Pi Model B operates at 1.2V, whereas most modern DDR2 DRAM operates at 1.8V. This doesn’t sound like a huge difference, but spread out over time it can have a significant effect on battery life of devices like smartphones and especially tablets.

> 减少 SDRAM 芯片功耗的主要方法是降低其工作电压。Raspberry Pi B 中使用的低功耗 LPDDR2 内存芯片在 1.2V 下运行，而大多数现代的 DDR2 DRAM 在 1.8V 下运行。这听起来并不是很大的差异，但是随着时间的流逝，它会对智能手机和平板电脑等设备的电池寿命产生重大影响。

Other power reduction features of LPDDR2 include the use of single-ended (unterminated) buses, which eliminate the power loss in the termination resistors used by `regular` DDR memory, at the cost of a reduction in achievable bus speed. Another is the provision of a self-refresh mode, which allows the memory controller to delegate the task of refreshing the arrays to the SDRAM itself when the system is idle, in turn allowing the memory controller, CPU and other system components to go into a deep-sleep mode. The memory chips used on Raspberry Pi support temperature-controlled self-refresh. When the temperature of the device falls, charge leaks away less quickly, so the device adjusts its refresh frequency according to the temperature. In normal operation the memory controller on the BCM2835 SoC (system-on-a-chip) performs a similar procedure.

> LPDDR2 的其他功率降低功能包括使用单端(未终止)总线，以消除 `常规` DDR 内存使用的终止电阻器中的功率损失，而降低了可实现的总线速度。另一个是提供自我删除模式的规定，它允许内存控制器在系统空闲时将阵列刷新为 SDRAM 本身的任务，进而允许内存控制器，CPU 和其他系统组件进入一个深睡模式。在 Raspberry PI 上使用的存储芯片支持温度控制的自我复制。当设备的温度下降时，电荷泄漏较快，因此设备根据温度调节其刷新频率。在正常操作中，BCM2835 SOC(芯片系统)上的内存控制器执行类似的过程。

### Ball-Grid Array Packaging

People taking their first look at the early Raspberry Pi boards often wonder where the RAM is. There are only two ICs on the board. One of them, obviously, is the Broadcom BCM2835 SoC. The other is a combination USB and Ethernet controller from SMSC, the LAN9512. So where’s the memory?

> 人们首先看早期的 Raspberry 皮板经常想知道 RAM 在哪里。Board 只有两个 IC。显然，其中之一是 Broadcom BCM2835 SoC。另一个是 SMSC(LAN9512)的组合 USB 和以太网控制器。那么 Mem 在哪里？

If you look carefully at the larger of the two ICs with a magnifying glass, you can see that the chip says Samsung or `Hynix` (or possibly something else) but not Broadcom. So what’s going on? The DRAM chip sits right on top of the Broadcom SoC. In fact, the two are soldered together in a sort of sandwich, with the solder between them. It’s deceptive because both chips are _extremely_ thin. The two-chip stack is only a little more than a millimetre high.

> 如果您用放大镜仔细看两个 IC 中的较大的 IC，则可以看到芯片说三星或 ` hynix` (或其他可能是其他东西)，但不是 Broadcom。发生什么了？**DRAM 芯片位于 Broadcom Soc 的顶部**。实际上，两者是用一种三明治焊一起的，它们之间的焊料。这是欺骗性的，因为两个芯片都是及其薄。两片堆的堆积只不过是高高的毫米。

This trick is made possible by a type of IC packaging called a _ball-grid array_ (BGA). A BGA package has one or more concentric rows of connections on the package face. Some devices (like the BCM2835 itself) have connections on both faces: one face has tiny balls of solder that connect to the circuit board beneath it; the other face has almost equally tiny pads and connects to solder balls on the bottom of the memory chip piggybacked on top of it. Such a piggyback system is called _package-on-package_ and is used on a great many devices where small size is paramount, especially smartphones. During assembly, the two chips are accurately aligned and then the stack is heated to the point where the solder melts, providing a conductive path between the chips. The 512MB memory chip in the first-generation Raspberry Pi has 168 connectors on its lower face; it is the equivalent of a 512MB DIMM in a chip that is smaller than a postage stamp.

> 一种称为 _Ball-Grid Array_ (BGA)的 IC 包装使此技巧成为可能。BGA 软件包在包装面上有一个或多个同心行连接。一些设备(例如 BCM2835 本身)在这两个脸上都有连接：一张脸有很小的焊料球连接到其下方的电路板；另一张脸几乎具有同样的小垫子，并连接到内存芯片底部的焊球球。这样的背包系统称为 _package-on-package_，用于在大尺寸最重要的许多设备上使用，尤其是智能手机。在组装过程中，将两个芯片准确对齐，然后将堆栈加热到焊料融化的点，从而在芯片之间提供导电路径。第一代 Raspberry PI 中的 512MB 内存芯片在其下部有 168 个连接器。它相当于比邮票小的芯片中的 512MB DIMM。

More recent Raspberry Pi boards like the Raspberry Pi Zero and Raspberry Pi 3 have different ICs and still use BGA packaging. However, the RAM IC is not soldered atop the SoC IC; instead it’s soldered to the circuit board itself. The method is still the same: solder balls on the lower surfaces of the ICs are melted to pads on the circuit board.

> 最近的 Raspberry Pi 板(例如 Raspberry Pi Zero 和 Raspberry Pi 3)具有不同的 ICS，并且仍然使用 BGA 包装。但是，RAM IC 并未在 SOC IC 上焊接。相反，它被焊接到电路板本身。该方法仍然是相同的：IC 的下表面上的焊球融化为电路板上的垫子。

As you might imagine, the placing of the solder balls and the alignment of the two chips one atop the other calls for unforgiving precision. The entire business is done with industrial robots, as is the case for almost all other circuit-board level assembly on the Raspberry Pi board.

> 您可能想象的是，将焊球球放置在另一个芯片上，一个芯片在另一个芯片上呼吁寻求宽容的精度。整个业务都是用工业机器人完成的，就像 Raspberry Pi 板上几乎所有其他电路板组件一样。

## Cache

No matter how much faster we make our memory systems, our CPUs just seem to get faster than memory at the same time, and memory never quite catches up. Memory performance has always been a drag on overall system performance. Even with brilliant engineering like source-synchronous clocking and 8-level prefetch buffers, our CPUs always seem to want data faster than memory can provide it. As impressively as memory speed has increased over the last 30 years, system memory speed is not the primary means to speed up the overall interaction between the CPU and its data. That primary means is, and probably always will be, data caching.

> 不管我们制造内存系统的速度快多少，我们的 **CPU 似乎同时变得比内存更快，并且内存永远不会完全赶上**。内存性能一直是整体系统性能的阻碍。即使使用出色的工程，例如源同步时钟和 8 级预摘要缓冲区，我们的 CPU 似乎总是想要比内存更快的数据。随着过去 30 年中 Mem 速度的提高，系统 Mem 速度并不是加快 CPU 及其数据之间整体交互的主要手段。**这种主要手段是，而且可能永远都是数据缓存**。

A data cache is a block of fast memory lying between the CPU and system memory. The advantage of caching is that cache memory is faster—and sometimes spectacularly faster—than system memory. When the CPU first reads a block of data from memory, it is placed in the data cache. The next time the CPU needs to read something from memory, it checks first to see if what it needs is already in cache. If so, you have a cache hit. The CPU then takes the data from the cache and not from system memory. If what the CPU needs is not in cache, you have a cache miss. The requested data is moved from memory into cache and then to the CPU on the good chance that the data just fetched will soon be needed again.

> 数据缓存是 CPU 和系统内存之间的快速内存块。缓存的优点是，缓存内存更快，有时比系统内存更快。当 CPU 首先从内存中读取数据块时，将其放置在数据缓存中。下次 CPU 需要从内存中读取内容时，它首先检查一下它**是否已经需要在缓存中**。如果是这样，您会命中率。然后，CPU 从缓存而不是从系统内存中获取数据。如果 CPU 不需要在缓存中需要什么，则会有一个缓存失误。所请求的数据从内存转移到缓存，然后将其转移到 CPU，这是很快需要再次获取数据的机会。

### Locality of Reference(参考地点)

How often will the CPU find that the data it needs is already in cache? The answer may surprise you: it finds what it needs in cache most of the time. There is a general principle in computer science called _locality of reference_, which states that computer operations tend to cluster together. Locality of reference has three facets:

> CPU 多久发现它所需的数据已经在缓存中了？答案可能会让您感到惊讶：它在大多数时候都会发现其在高速缓存中的需求。计算机科学中有一个一般原则，称为 _参考倾向_，该原理指出**计算机操作倾向于聚集在一起**。参考的局部性有三个方面：

- The same data accessed now will probably be accessed again in the near future.
- Over short spans of time, data accesses (both reads and writes) tend to cluster in the same general area of memory.
- Memory locations tend to be read from or written to in sequential order.

> - 现在访问的相同数据可能会在不久的将来再次访问。
> - 在短时间内，数据访问(读取和写入)倾向于聚集在同一内存区域中。
> - 内存位置往往会从顺序读取或写入。

In essence, when the computer is performing a particular task, its memory accesses are not all over the map. They tend to be mostly side-by-side, in one general area of memory. That being the case, it makes a lot of sense to move the data in the current working area of system memory somewhere closer (in access time) to the CPU. That somewhere is cache.

> 从本质上讲，当计算机执行特定任务时，其内存访问并不是整个地图。它们倾向于在 Mem 的一个一般区域中主要是并排的。在这种情况下，将数据移动到当前系统内存的当前工作区域(在访问时间)距离 CPU 的地方很有意义。那是缓存。

> [!note]
> 这种缓存的技术思想，是否也可以应用与实时性的系统调度？！

### Cache Hierarchy

Modern cache technology takes this to an extreme: it moves the cache all the way onto the same silicon as the CPU itself. Cache memory is our old friend static RAM (SRAM), which is a great deal faster than any generation of DRAM. So, not only is cache physically close to the CPU but it’s also the fastest sort of RAM that we can make.

> 现代缓存技术将其带到了一个极端：它将缓存一直移至与 CPU 本身相同的硅。缓存内存是我们的老朋友 Static Ram(SRAM)，它比任何一代 DRAM 都要快。因此，缓存不仅在物理上靠近 CPU，而且也是我们可以制作的最快的 RAM。

One reason that cache is fast is because it’s small. System memory may be several gigabytes in size. Cache is miniscule by comparison and rarely stores more than 1 megabyte. Smaller is faster because there are fewer address bits to process, and also because it’s easier to determine whether the data that the CPU needs is already in the cache. (More on this challenge a little later.) Make cache memory larger, and cache operations slow down.

> 缓存快速的原因之一是因为它很小。系统内存的大小可能是千兆字节。相比之下，缓存是微小的，很少存储超过 1 兆字节。较小的速度更快，因为要处理的地址位较少，而且还因为确定 CPU 需求是否已经在缓存中的数据更容易。(稍后再进行此挑战。)使高速缓存内存更大，并且缓存操作放慢速度。

What to do? Divide cache into more than one layer and build the layers into a hierarchy. Modern microprocessors have at least two layers of cache, and often three. The first layer, called level 1 (L1) cache, is closest to the CPU. The second layer is level 2 (L2) cache, and so on. L1 cache is faster (and smaller) than L2 cache, which in turn is faster (and smaller) than L3 cache. At the bottom of the cache hierarchy is system memory, which is the largest and also the slowest place to store data that may be directly accessed by the CPU. Of course, data in system memory may also be written out to hard disk or SSD storage, which is still slower and not available by memory address to the CPU (see Figure 3-8).

> 该怎么办？将缓存分为多个一层，然后将图层构建为层次结构。现代微处理器至少有两层缓存，通常三层。第一层称为级别 1(L1)缓存，最接近 CPU。第二层是 2 级(L2)缓存，依此类推。L1 缓存比 L2 缓存更快(且小)，而 L2 缓存又比 L3 缓存更快(且小)。在高速缓存层次结构的底部是系统内存，它是最大，也是存储 CPU 可以直接访问的数据的最慢的位置。当然，系统内存中的数据也可以写入硬盘或 SSD 存储，该存储仍然较慢，并且可通过内存地址提供到 CPU(请参见图 3-8)。

> ![[FIGURE 3-8:](#06_9781119183938-ch03.xhtml#rc03-fig-0008) A multi-level cache](./media/images/9781119183938-fg0308.png)

The number of layers of cache and the size of each layer vary depending on the microprocessor. The Intel Core i7 family has a 32KB L1 cache for each core, a 256 KB L2 cache for each core and a single L3 cache shared among all cores. The L3 cache is between 4MB and 8MB, depending on the microprocessor model. The ARM11 processor in the older Raspberry Pi models contains a pair of 16KB L1 caches: one for instructions and one for data. A 128KB L2 cache is present in the system-on-a-chip silicon surrounding the ARM11 CPU, but with a catch: the L2 cache is shared between the ARM11 CPU and the Video Core IV graphics processor, with the graphics processor given priority. The Raspberry Pi does not incorporate an L3 cache.

> 缓存层的数量和每一层的大小根据微处理器而变化。Intel Core i7 家族为每个核心具有 32KB L1 缓存，每个核心的 256 kb L2 缓存和所有内核中共享的单个 L3 缓存。根据微处理器模型，L3 缓存在 4MB 和 8MB 之间。较旧的 Raspberry Pi 模型中的 ARM11 处理器包含一对 16KB L1 缓存：一个用于指令，一个用于数据。ARM11 CPU 周围的系统芯片硅中存在一个 128KB L2 缓存，但是带有 CATCE：L2 CACHE 在 ARM11 CPU 和视频核心 IV 图形处理器之间共享，并具有优先级的图形处理器。Raspberry Pi 不包含 L3 缓存。

### Cache Lines and Cache Mapping

[Figure 3-8](#06_9781119183938-ch03.xhtml#c03-fig-0008) looks a little like a programming flowchart and you might assume the process is slow, with all those decisions to make. Not so. Determining whether a given run of memory locations is already present in cache is lightning-quick, with dedicated logic built into the CPU’s silicon.

> [图 3-8](%EF%BC%8306_9781119183938-CH03.XHTML%EF%BC%83C03-FIG-0008) 看起来有点像编程流程图，您可能会认为该过程很慢，并且所有这些决定都可以做出。事实并非如此。确定在高速缓存中是否已经存在内存位置的给定运行位置是闪电般的 Quick，其中 CPU 的硅内置了专用逻辑。

There are two general mechanisms for finding out whether a given memory location is present in cache. One depends on calculation and the other depends on searching. Both have serious disadvantages. What most modern computers use is a sort of hybrid of both approaches. Whereas the `pure` approaches are rarely if ever actually implemented in silicon, you need to know how both work in order to understand the hybrid compromise that we do use.

> 有两种通用机制可以找出缓存中是否存在给定的内存位置。一个取决于计算，另一个取决于搜索。两者都有严重的缺点。大多数现代计算机都使用的是两种方法的混合体。尽管 `纯` 方法很少是在硅中实际实施的，但您需要知道两者如何工作，以了解我们确实使用的混合折衷。

First, here’s some general technical background on caching. Caching is never done one data word at a time. In part, the reason for this is to exploit locality of reference, as explained earlier in this section. Caching also interacts well with a memory controller feature explained in detail in the previous section on SDRAM: `burst-mode` logic that can read or write multiple words from system memory in the same amount of time as a single word. Cache is read and (usually) written in fixed-size blocks called cache lines. The size of cache lines may vary, but in modern systems it is usually 32 bytes. This is true of many Intel CPUs, as well as the ARM11 processor in the Raspberry Pi. The number of cache lines capable of being stored in cache is thus the size in bytes of the cache divided by the size in bytes of the cache line. For the Raspberry Pi’s L1 cache, the 16,384 bytes is divided by the 32-byte size of a cache line, giving 512 possible cache lines in L1 cache.

> 首先，这是一些有关缓存的一般技术背景。缓存从未一次完成一个数据字。如本节所述，部分原因是要利用参考的局部性。缓存还与上一节中有关 SDRAM 的部分中详细说明的内存控制器功能进行了很好的交互： ` BUSS-MODE` 逻辑可以在与单个单词相同的时间内从系统存储器中读取或写出多个单词。缓存是读取的，(通常)用称为缓存线的固定尺寸块编写。缓存线的大小可能会有所不同，但是在现代系统中通常是 32 个字节。许多 Intel CPU 以及 Raspberry Pi 中的 ARM11 处理器都是如此。因此，能够存储在缓存中的缓存线的数量是缓存中的字节中的大小除以缓存线的字节大小。对于 Raspberry Pi 的 L1 缓存，16,384 字节除以高速缓存线的 32 字节大小，在 L1 缓存中提供 512 个可能的缓存线。

Cache memory is not simply a run of very fast memory locations inside the CPU. Cache has its own very specific structure. In addition to the 32 bytes of data, each location in cache has an additional field called a _cache tag_, which allows the cache controller to determine where in system memory the cache line came from. There are also two single-bit flags stored in each cache line:

> 缓存内存不仅是 CPU 内部非常快速的内存位置的运行。缓存具有其自己非常具体的结构。除了 32 个数据的数据外，缓存中的每个位置都有一个名为 _cache tag_ 的其他字段，该字段允许缓存控制器确定缓存线中的系统内存中的位置。每个缓存行中还存储了两个单位标志：

- **Valid bit:** Indicates whether valid data is present in that cache line. When cache is initialised, the valid bit for all cache lines is set to false, and it only changes to true when a memory block has been read into the cache line.
- **Dirty bit:** Indicates that some of the data in the cache line has been changed by the CPU and the data needs to be written back to system memory.

>

- **有效位：**指示该缓存线中是否存在有效数据。初始化缓存时，所有缓存线的有效位均设置为 false，只有在 Mem 块已读取到缓存线中时，它才会更改为 true。
- **肮脏位：**指示 CACHE 系中的某些数据已由 CPU 更改，并且需要将数据写回系统内存。

The cache tag is derived from the address in system memory from which the cache line was filled. When a memory address is presented to be read or written, the address is split into three pieces:

> 缓存标签是从填充缓存线的系统内存中的地址派生的。当呈现 Mem 地址读取或书面时，该地址分为三个部分：

- **Cache tag:** Identifies where in memory the cache line came from. These are the highest-order bits from the memory address, and uniquely identify a cache-line-sized and aligned block of system memory. The tag is stored with the cache line itself.
- **Index:** Identifies the cache line where the data from the system memory address would reside if it were present in cache. For a direct-mapped cache (see the next section), the number of bits is the number it takes to specify one cache line from all the lines in cache. For a 512-line direct-mapped cache, it would be 9 bits.
- **Offset:** Specifies which byte within the cache line corresponds to the byte specified by the system memory address that generated the tag. These are the lowest-order bits in the address. The number of bits is the number it takes to specify a byte from all the bytes in a line. In a 32-byte cache line, it would be 5 bits.

>

- **缓存标签：**标识 Mem 中的缓存线的来源。这些是内存地址的最高级位，并独特地识别系统内存的缓存大小和对齐的块。标签与缓存线本身一起存储。
- **索引：**标识缓存线，如果缓存中存在来自系统内存地址的数据将位于其中。对于直接映射的缓存(请参阅下一节)，位数是从缓存中所有线路指定一条缓存线所需的数字。对于 512 行直接映射的缓存，将是 9 位。
- **偏移：**指定缓存线中的字节对应于生成标签的系统内存地址指定的字节。这些是地址中最低的位。位数是从行中的所有字节指定字节所需的数字。在 32 字节的缓存线中，将是 5 位。

The block field and word field are not stored anywhere. They’re used during cache access, but once a data word is read from or written to cache, they’re discarded.

> 块字段和单词字段不会在任何地方存储。它们在缓存访问期间使用，但是一旦读取或写入缓存的数据字，它们就会被丢弃。

The structure of a cache line and how a system memory address is broken down for cache access are shown in Figure 3-9. Some of the details of cache line structure vary depending on system specifics (how large the cache is, how large the cache line is and so on) and the precise mechanism used by the system to manage caching.

> 高速缓存线的结构以及如何分解用于缓存访问的系统内存地址，如图 3-9 所示。缓存线结构的一些细节因系统细节(缓存的大小，高速缓存线等等)以及系统用于管理缓存的精确机制而有所不同。

> ![[FIGURE 3-9:](#06_9781119183938-ch03.xhtml#rc03-fig-0009) Cache line structure](./media/images/9781119183938-fg0309.png)

The lynchpin issue in cache technology is where data from system memory is placed in cache. This is called _cache mapping_ and it determines how the CPU knows whether a requested address is in cache. As the name suggests, cache mapping is about how the position of a cache-line-sized data block in system memory relates to its possible position in cache.

> 缓存技术中的 Lynchpin 问题是将系统存储器数据放在缓存中的地方。这称为 _cache Mapping_，它确定 CPU 如何知道缓存中的请求地址。顾名思义，缓存映射是关于缓存线大小的数据块在系统内存中的位置如何与其在缓存中的可能位置有关。

### Direct Mapping

The oldest and simplest cache mapping technique, and the one that we have been implicitly assuming up to this point, is called _direct mapping_. In simplified terms: the first block of system memory can be stored only in the first cache line in cache; the second block in system memory can be stored only in the second cache line in cache; and so on. There’s a lot more system memory than cache memory, of course, so when cache is full, the correspondence `wraps around` and begins again at the first location in cache.

> 最古老，最简单的高速缓存映射技术，以及我们一直隐含地假设到这一点的技术，称为 _Direct Mapping_。用简化的术语：**系统内存的第一个块只能存储在缓存中的第一个缓存线中；系统内存中的第二个块只能存储在缓存中的第二个缓存线中。**等等。当然，系统内存比缓存内存要多得多，因此，当缓存完整时，通信 `绕开` ，然后在缓存中的第一个位置再次开始。

A visual really helps you understand this, so refer to Figure 3-10 during the following discussion.

> 视觉效果确实可以帮助您理解这一点，因此请参阅以下讨论中的图 3-10。

> ![[FIGURE 3-10:](#06_9781119183938-ch03.xhtml#rc03-fig-0010) Direct cache mapping](./media/images/9781119183938-fg0310.png)

In the simplified direct mapping example depicted in [Figure 3-10](#06_9781119183938-ch03.xhtml#c03-fig-0010), there are eight locations in cache, each of which stores a single cache line. (For simplicity, the cache tags are not shown.) Each cache line holds 8 bytes. The first 24 blocks of system memory are shown. Each block in system memory is the size of a cache line (that is, 8 bytes). As in all caching systems, data is read from or written to system memory in cache-line-sized chunks. The hexadecimal (base 16) numbers over each column of system memory blocks are the byte address of the start of each column. Because each column represents 64 bytes, the address of the second column is 0 + 0x40 (which is 64 in hexadecimal) and the starting address of the third column is 0x40 + 0x40, or 0x80. (128 in decimal notation.)

> 在[图 3-10]中描述的简化直接映射示例中(＃06_9781119183938-CH03.XHTML＃C03-FIG-0010)中，缓存中有八个位置，每个位置都存储一个缓存线。(为简单起见，未显示缓存标签。)每个缓存线均包含 8 个字节。显示了前 24 个系统内存。系统内存中的每个块都是缓存线的大小(即 8 个字节)。与所有缓存系统一样，数据将从缓存线大小的块中从或写入系统内存。系统内存块每一列上的十六进制(基本 16)数字是每列开始的字节地址。因为每列代表 64 个字节，所以第二列的地址为 0 + 0x40(在十六进制中为 64)，第三列的起始地址为 0x40 + 0x40，或 0x80。(十进制符号 128。)

---

> [!NOTE]

Any number you see beginning with `0x` is a _hexadecimal_ number, meaning a number expressed in base 16 rather than our familiar decimal base 10. This is explained in some detail in [Chapter 2](#05_9781119183938-ch02.xhtml). Both Windows and Linux (including Raspbian) include calculator apps that can convert hexadecimal values to decimal and back, and do arithmetic in either number base.

> 您看到以 `0x` 开头的任何数字都是 _hexadecimal_ 编号，这意味着在基本 16 中表示的数字，而不是我们熟悉的小数基碱基 10。这在[第 2 章](%EF%BC%8305_97811191919183938-CH02.XHTML)中进行了一些详细说明。Windows 和 Linux(包括 Raspbian)都包含可以将十六进制值转换为十进制和返回的计算器应用程序，并在任一数字底座中进行算术。

The mapping of system memory blocks to cache lines works like this: block 0 in system memory (starting at address 0x00) is always mapped to cache line 0; block 1 (starting at address 0x08) is always mapped to cache line 1; and so on. This is straightforward until you run out of cache lines (there are only eight lines in cache in the example in [Figure 3-10](#06_9781119183938-ch03.xhtml#c03-fig-0010)). When this happens, the sequence `wraps around` and begins again: block 8 (starting at address 0x40) is mapped to cache line 0, block 9 (starting at address 0x48) is mapped to cache line 1, and so on. This is referred to as modulo _n_ mapping, where _n_ is the number of locations within cache. The location of any given system memory block when mapped to cache will be the memory block number modulo 8.

> 系统内存块到缓存行的映射是这样的：系统内存中的块 0(从地址 0x00 开始)总是映射到缓存行 0；块 1(从地址 0x08 开始)总是映射到缓存行 1；等等。这很简单，直到用完缓存行(在 [图 3-10](#06_9781119183938-ch03.xhtml#c03-fig-0010) 的示例中，缓存中只有八行)。发生这种情况时，序列 `环绕` 并重新开始：块 8(从地址 0x40 开始)映射到缓存行 0，块 9(从地址 0x48 开始)映射到缓存行 1，依此类推。这称为模 _n_ 映射，其中 _n_ 是高速缓存中的位置数。映射到高速缓存时，任何给定系统内存块的位置将是内存块编号模 8。

The term `modulo` means calculating the remainder after division. Primary school children are taught that 64 divided by 10 equals 6 with a remainder of 4. So, 64 modulo 10 is simply 4. If you need to find out which cache line system memory block 21 maps to in our example, calculate 21 modulo 8. The answer is 5 (21 ÷ by 8 = 2 with a remainder 5), and memory block 21 will always map to cache line 5. Count memory blocks in [Figure 3-10](#06_9781119183938-ch03.xhtml#c03-fig-0010) (from 0, of course) to verify that memory block 21 maps to cache line 5.

> 术语 `模` 表示计算除法后的余数。小学生被教导 64 除以 10 等于 6，余数为 4。因此，64 模 10 就是 4。如果您需要在我们的示例中找出系统内存块 21 映射到哪个缓存行，请计算 21 模 8 .答案是 5(21÷8=2 余数 5)，内存块 21 总会映射到缓存行 5。计数内存块在[图 3-10](#06_9781119183938-ch03.xhtml#c03- fig-0010)(当然是从 0 开始)来验证内存块 21 是否映射到高速缓存行 5。

Direct mapping of system memory blocks to cache lines is mathematically precise: a given block of system memory is always stored in the same location in cache. The CPU determines whether the memory address it needs to fetch is in cache by calculating which position in cache that memory block always goes to and then comparing the value in the tag field of the cache tag with the corresponding bits in the system memory address. If it’s a match, you have a cache hit. If it’s not a match, you have a cache miss.

> 直接将系统内存块映射到缓存线上是数学上精确的：给定的系统内存块始终存储在缓存中的同一位置。CPU 通过计算存储器块总是在缓存中的哪个位置，然后将缓存标签标签字段中的值与系统存储器地址中的相应位进行比较，然后将内存块中的哪个位置与系统内存中的值进行比较，则确定是否需要获取内存地址。如果是一场比赛，您将受到缓存的命中。如果不是比赛，您会有一个缓存的错过。

CPUs are extremely good at calculation and comparison, and direct cache mapping is the fastest cache mechanism available. However, there’s a downside in that there’s no flexibility whatsoever in where blocks from system memory are stored in cache. This can become an issue when the CPU is running software performing memory reads that alternate blocks. In the direct mapping example, system memory block 4 maps to the same cache location (cache line 4) as block 12, block 20, and so on, modulo 8. Suppose the software reads an address that falls in block 4; cache line 4 receives the block if it isn’t there already. Then the software may need data from block 12. If block 4 is in cache, block 12 is not, because they always map to the same cache location, so block 12 is loaded, and overwrites (we say `evicts` ) block 4. Soon thereafter, perhaps as a program loop is executed, the software again needs data from block 4, so block 12 must be evicted. If the loop continues in this fashion, there will be thrashing (that is, repeated fetches from system memory) in cache that nullifies any of the speed gains earned by caching. In fact, because of the overhead of the caching mechanism, memory access is slower in a thrashing situation than it would be without any caching at all.

> CPU 非常擅长计算和比较，直接缓存映射是可用的最快缓存机构。但是，有一个缺点，因为在缓存中存储了系统内存块中的任何灵活性。当 CPU 正在运行执行内存读取以交替块的软件时，这可能会成为一个问题。在直接映射示例中，系统内存块 4 映射到与块 12，块 20，等等的同一缓存位置(缓存线 4)，Modulo 8.假设该软件读取一个落在块 4 中的地址；如果还不存在，请缓存线 4 将接收该块。然后，该软件可能需要从块 12 中的数据。如果块 4 在缓存中，则块 12 不是，因为它们始终映射到同一缓存位置，因此块 12 已加载，并且覆盖(我们说 `驱逐` )块 4。此后不久，也许作为执行程序循环，该软件再次需要块 4 的数据，因此必须驱逐块 12。如果循环以这种方式继续进行，则在缓存中将有颤动(即从系统内存中重复获取)，这将无效缓存获得的任何速度增长。实际上，由于缓存机制的开销，在颤抖的情况下，内存访问比根本没有任何缓存的情况要慢。

### Associative Mapping

More flexibility is needed in cache mapping than direct mapping provides. Ideally, you want to have as many of the system memory blocks that software is using available in cache as possible, regardless of the addresses being accessed. If you could load a given block into any available line in cache, you could implement a replacement policy (in essence, deciding which cache line to evict when writing a new memory block to cache) that makes better use of cache space.

> **与直接映射相比，在缓存映射中需要更多的灵活性。**理想情况下，您希望拥有尽可能多的系统内存块，无论访问的地址如何，软件都在缓存中使用。如果您可以将给定的块加载到缓存中的任何可用行中，则可以实现替换策略(本质上，确定在编写新的存储器块时要驱逐哪个缓存线)，以更好地利用缓存空间。

The job of a replacement policy is largely to avoid cache thrashing. That job is surprisingly difficult, and replacement policies are often combinations of algorithms that decide which cache line to evict when a new memory block needs to enter cache. Here are the common replacement policies:

> 替换策略的工作主要是为了避免缓存。这项工作令人惊讶地困难，替换策略通常是算法的组合，这些算法决定了当新的内存块需要输入缓存时要驱逐哪种缓存线。这是常见的替代政策：

- **First in first out (FIFO):** Once cache is full, the first cache line that was written to cache is the one evicted.
- **Least recently used (LRU):** Cache lines are given timestamps, and the system records when a cache line is used. When a new cache line must be written, the one that hasn’t been accessed in the longest time is evicted. Managing the timestamp takes time and is complex.
- **Random:** It sounds counterintuitive, but one of the cheapest (in terms of logic) and most effective replacement policies picks a cache line to evict completely at random. Random eviction makes thrashing unlikely. It’s also not as sensitive as FIFO and LRU to the algorithms used in software.
- **Not most recently used (NMRU):** The line to be evicted is chosen randomly, but this is tweaked so that the most recently used line is remembered and not chosen. This policy is almost as cheap to implement as the random policy and performs slightly better.

> - **首先(FIFO)：**一旦缓存已满，第一个写入缓存的缓存线就是被驱逐的。
> - **最近使用的(LRU)至少：**缓存线被给定时间戳，并且使用缓存线时的系统记录。当必须编写新的缓存线时，最长时间尚未访问的缓存线就被驱逐出境。管理时间戳需要时间，而且很复杂。
> - **随机：**听起来是违反直觉的，但最便宜的(就逻辑而言)和最有效的替换策略选择了一条缓存线以完全随机驱逐。随机驱逐使撞击不可能。对于软件中使用的算法，它也不像 FIFO 和 LRU 那样敏感。
> - **并非最近使用(nmru)：**随机选择要驱逐的行，但要进行调整，以便记住最近使用的行并未选择。该政策的实施几乎与随机策略一样便宜，并且效果稍好。

ARM processors, like the ones in the Raspberry Pi, can use either FIFO or random policies, as set by a configuration bit. In most cases, the replacement policy is random.

> 像 Raspberry Pi 中的 ARM 处理器一样，可以使用配置位设置的 FIFO 或随机策略。在大多数情况下，替代政策是随机的。

The most flexible way to use cache space is to allow placement of a new cache line anywhere in cache, whatever the replacement policy directs. The CPU still needs to be able to decide whether the data it needs is in cache or not and if data blocks can be stored anywhere in cache that decision can no longer be made by a single calculation and comparison. Instead, the CPU must search for a given block in cache.

> 使用缓存空间的最灵活方法是允许在缓存中的任何地方放置新的高速缓存线，无论替换策略指示什么。CPU 仍然需要能够决定是否需要在缓存中所需的数据，并且是否可以将数据块存储在缓存中的任何位置，该决策不能再通过一个计算和比较来做出。相反，CPU 必须在缓存中搜索给定的块。

Compared to calculation and comparison, searching is an extremely compute-intensive process. Searching cache lines one at a time would eat up any possible performance gains. The solution is to use a technology called associative memory. Associative memory, like all memory, stores data in a series of storage locations. What associative memory does not have is a conventional numerical addressing system. Instead, storage locations are addressed by what is stored in them.

> 与计算和比较相比，搜索是一个非常密集的过程。一次搜索缓存线一次会消耗任何可能的性能增长。解决方案是使用一种称为关联内存的技术。与所有内存一样，关联内存将数据存储在一系列存储位置中。关联内存没有的是传统的数值寻址系统。取而代之的是，存储位置由存储在其中的位置解决。

In a fully associative cache, a memory access causes a cache tag to be generated from the system memory address just as before. However, instead of comparing this tag against the corresponding tag for one uniquely specified cache line, in this case the associative memory system compares the generated tag against every tag stored in cache in parallel. If it finds a match, you have a cache hit and the corresponding cache line is given to the CPU. If it doesn’t find a match, it’s a cache miss; a line must be evicted from the cache, as determined by the replacement policy, and the requested system memory block is read into the newly vacated cache line.

> 在完全关联的缓存中，内存访问会像以前一样从系统内存地址生成缓存标签。但是，与其将此标签与一个唯一指定的高速缓存线的相应标签进行比较，不如将关联内存系统比较生成的标签与并行存储在缓存中的每个标签。如果找到匹配项，则会有一个缓存命中，并且将相应的缓存线给予 CPU。如果找不到比赛，那就是缓存的错过。由替换策略确定，必须从高速缓存中驱逐行，并将所需的系统内存块读取到新撤离的缓存线中。

To people who are used to conventional addressing and sequential searches, this sounds a little bit like magic. Alas, although parallel search is fast, associative memory requires a lot of dedicated logic that takes a significant amount of die space on the CPU. For all but the smallest or most performance-critical caches, the pattern-matching logic is too expensive (in transistors, and eventually time delays) to be practical.

> 对于习惯于传统的寻址和顺序搜索的人来说，这听起来有点像魔术。las，尽管并行搜索很快，但关联内存需要大量专用逻辑，这些逻辑在 CPU 上需要大量的模具空间。对于除最小或大多数性能至关重要的缓存以外的所有人，模式匹配的逻辑太昂贵(在晶体管，最终是时间延迟)是实用的。

---

> [!NOTE]

_Die space_ is the area on a silicon chip (called a `die` during the fabrication process) that may be used to fabricate the transistors from which the chip’s digital logic is built. There is only so much area on any given die to `spend` on transistors, so chip designers have to be very careful how they use the space that they have. The trade-off between die space and chip functionality is the oldest single challenge in large-scale chip design.

> _die Space_ 是硅芯片上的区域(在制造过程中称为 `模具` )，可用于制造芯片数字逻辑的晶体管。任何给定的死亡都只能在晶体管上 `花费` ，因此芯片设计师必须非常谨慎地使用他们拥有的空间。模具空间和芯片功能之间的权衡是大规模芯片设计中最古老的单一挑战。

### Set-Associative Cache

At one extreme, then, is the lightning-fast and compact direct cache mapping, which is completely inflexible in terms of where data for a new cache line may be stored. At the other is the completely flexible associative cache mapping, which takes far too much on-chip logic to be implemented. The solution, as with so many difficult choices like this, lies somewhere in the middle.

> 因此，在一个极端情况下，是闪电般的速度和紧凑的直接缓存映射，就新的高速缓存线数据的位置而言，它完全不灵活。另一个是完全灵活的关联缓存映射，它需要太多的芯片逻辑以无法实现。与这样的许多艰难选择一样，解决方案位于中间的某个地方。

This compromise is called _set-associative cache_. A set-associative caching system reorganises cache lines into sets. Each set contains 2, 4, 8 or 16 cache lines, complete with data block and tag. Figure 3-11 shows a simplified diagram of a set-associative cache with four cache lines per set. With four lines per set, a cache is known as a four-way set-associative cache. This is the cache scheme used in the Raspberry Pi, as well as a great many other laptop and desktop computers today.

> 此妥协称为 _SET-缔合性 cache_。设置缔合的缓存系统将缓存线重新组织为集合。每组包含 2、4、8 或 16 个缓存线，并配有数据块和标签。图 3-11 显示了设置缔合性高速缓存的简化图，每组具有四个缓存线。每组有四行，一个缓存称为四向设置缔合缓存。这是 Raspberry Pi 中使用的缓存方案，以及当今许多其他笔记本电脑和台式计算机。

> ![[FIGURE 3-11:](#06_9781119183938-ch03.xhtml#rc03-fig-0011) Set-associative cache mapping](./media/images/9781119183938-fg0311.png)

The memory locations that map to a given set are still determined by direct mapping. This means that the modulo relationship of system memory addresses to cache positions still holds, except that now we have a little flexibility in terms of where we place an incoming block. Recall the example given earlier of an eight-line direct-mapped cache, which blocks 2, 10, 18 and 26 from system memory as they would be blocked under a pure direct-mapping scheme.

> 映射到给定集的内存位置仍由直接映射确定。这意味着系统内存地址与缓存位置的模型关系仍然存在，除了现在，我们在放置传入块方面具有一些灵活性。回想一下八线直接映射缓存的前面示例，该缓存将在系统内存中块 2、10、18 和 26 块，因为它们将在纯直接映射方案下被阻止。

The problem remains, though: there are four system memory blocks stored in cache lines in one set. The computer can easily calculate which set any given memory address would fall into, but it cannot by simple calculation determine which cache line within a given set would contain the requested address. The CPU must search the four cache lines in a set to see which cache line’s tag matches the requested address. Associative memory does this search. This is not a sequential search that looks at each cache tag in turn and stops when it finds a match. Instead, parallel comparators test the bits from the four tags in the cache line against the corresponding bits in the generated tag, all simultaneously. This logic is still complex internally, but because only four locations are being searched it can be done, and done quickly.

> 但是，问题仍然存在：一组中的高速缓存线中有四个系统内存块。计算机可以轻松地计算哪个设置的任何给定内存地址将属于其中，但是不能通过简单的计算确定给定集中的哪个缓存线将包含所请求的地址。CPU 必须在集合中搜索四个缓存线，以查看哪个缓存线的标签与所请求的地址匹配。关联内存进行此搜索。这不是一个顺序搜索，它依次查看每个缓存标签，并在找到匹配项时停止。取而代之的是，并行比较器同时测试了缓存线中四个标签的位与生成标签中的相应位。这种逻辑在内部仍然很复杂，但是由于只搜索了四个位置，因此可以完成并快速完成。

The process works like this: the CPU calculates which set a memory block must be in, from the system memory address. (This is done the same way as in direct cache mapping.) It then submits the address to the associative memory logic, and associative memory either tells the CPU which line in the set contains the requested block (a cache hit) or registers a cache miss. The requested block is then read from system memory and placed in one of the four lines in the set, according to a replacement policy. To summarise: set-associative cache divides a cache into sets, which in the case of the ARM11 used in the Raspberry Pi contain four cache lines. The CPU can determine which set a given address must be in through a direct mapping scheme and then it uses the pattern-matching mechanism of associative memory to go right to the matching cache line within the set—or, if the search fails, register a cache miss.

> 该过程是这样工作的：CPU 计算设置内存块必须从系统内存地址中进行。(这是与直接缓存映射相同的方法。)然后将地址提交给关联内存逻辑，并且关联内存要么告诉集合中的哪一行包含请求的块(缓存 hit)或寄存器寄存器一个缓存错过。然后根据替换策略从系统内存中读取请求的块，并将其放置在集合中的四行之一中。总结一下：集合缔合缓存将缓存分为集合，在 Raspberry Pi 中使用的 ARM11 的情况下，该集合包含四个缓存线。CPU 可以通过直接的映射方案确定必须在哪个设置的地址中进行，然后使用关联内存的模式匹配机制才能直接进入集合中的匹配缓存线 - 或者，如果搜索失败，请注册缓存小姐。

### Writing Cache Back to Memory

Up to this point, we’ve discussed caching as though it were entirely about reading from memory. Of course, what is read is often changed. When the CPU changes a data word somewhere in a cache line, that cache line is marked as `dirty` using a single-bit flag. When a cache line’s dirty bit is set, the line must be written back to the block in memory from which it was originally read. No matter what else happens, system memory blocks and their associated cache lines must be consistent. If changes to cache are not written back to system memory, those changes will be lost if the replacement policy reads in a new block to the same cache line where the changes were made.

> 到目前为止，我们已经讨论了缓存，好像它完全是关于从内存阅读的。当然，读取的内容通常会更改。当 CPU 在缓存线中的某个地方更改数据字时，该缓存线使用单位标志将其标记为 `脏` 。当设置了缓存线的脏位时，必须将线路写回最初读取的内存中的块。无论发生什么情况，系统内存块及其关联的缓存线都必须保持一致。如果没有写回到缓存的更改，则如果替换策略在新的块中读取了进行更改的同一缓存线，则将丢失这些更改。

There are two general approaches to keeping cache and memory consistent. Taken together, these are called _cache write policies_:

> 有两种一般方法可以保持缓存和内存一致。综上所述，这些称为 _cache 写策略_：

- **Write-through:** Means that any time a data word in a cache line is changed by the CPU, the cache line is written to memory immediately. This happens every time the line is written to, even if the writes are all entirely within the same cache line. As expected, there is time wasted writing a single cache line back to memory multiple times, but the CPU’s view of memory is consistent with what is actually in memory; this is important if a peripheral such as a display controller is also accessing this memory.
- **Write-back:** Means that a `dirty` cache line is written back to memory only when the replacement policy has chosen to evict the dirty cache line from cache. Before a new system memory block is loaded into the cache line, the current contents of the line are copied back to its original block in system memory. Write-back avoids a lot of unnecessary system memory writes at the cost of a more relaxed notion of consistency.
- **写入：**意味着 CACHE 行中的数据字在 CPU 上更改时，CACHE 系列都会立即写入内存。每次写入行时，都会发生这种情况，即使写作完全位于同一缓存线上。正如预期的那样，有时间浪费的时间将单个缓存线编写回存储器多次，但是 CPU 的内存视图与内存中的实际内容一致。如果外围设备(例如显示控制器)也访问此内存，这一点很重要。
- **写回信：**意味着只有当替换策略选择从缓存中驱逐肮脏的高速缓存线时，只有在存储器中写回 `肮脏` 的缓存线。在将新的系统内存块加载到缓存线上之前，该行的当前内容已复制回系统内存中的原始块。写下避免了许多不必要的系统 Mem 以更轻松的一致性概念为代价。

## Virtual Memory

Think of computer memory as a sort of pyramid, with the fastest, smallest blocks of memory at the top. These blocks of memory are the CPU’s registers. Below the registers is the larger, slower L1 cache and beneath that, the still larger but still slower L2 cache. Beneath cache is system memory, which is much larger than cache but much slower. Next is the layer beneath system memory: virtual memory.

> 将计算机存储器视为一种金字塔，顶部最快，最小的内存块。这些 Mem 块是 CPU 的寄存器。寄存器下方是较大，较慢的 L1 高速缓存，其下方仍然较大，但 L2 高速缓存仍然较慢。高速缓存是系统内存，它比缓存大得多，但要慢得多。接下来是系统内存下方的层：虚拟内存。

Virtual memory is a technology that can create truly enormous memory systems by allowing mass storage devices like hard disks to extend system memory. In a sense, virtual memory extends the cache hierarchy diagram in [Figure 3-8](#06_9781119183938-ch03.xhtml#c03-fig-0008) past system memory to a layer of storage limited only by the capacity of hard drives.

> **虚拟内存是一项技术，可以通过允许硬盘(例如硬盘)扩展系统内存来创建真正巨大的内存系统。**从某种意义上说，虚拟内存将缓存层次结构图扩展在[图 3-8](%EF%BC%8306_9781119183938-CH03.XHTML%EF%BC%83C03-FIG-0008) 之前，将系统存储器放到仅受硬盘驱动器容量的限制。

Both cache memory and virtual memory came about due to the limitations of RAM: cache because RAM is slow and virtual memory because RAM is scarce. RAM was so bulky and expensive in the mid-1960s that the seminal PDP-8 computer had a 12-bit address space that could address only 4,096 12-bit words of RAM. For machines in that era to support larger programs and multiple concurrent tasks required far larger memory spaces. Virtual memory provided them.

> **缓存内存和虚拟内存都是由于 RAM：缓存的局限性，因为 RAM 缓慢而虚拟内存，因为 RAM 稀缺**。RAM 在 1960 年代中期如此笨重和昂贵，以至于开创性的 PDP-8 计算机具有 12 位地址空间，只能解决 4,096 个 12 位 RAM 的单词。对于那个时代的机器，支持较大的程序和多个并发任务需要更大的内存空间。虚拟内存提供了它们。

Virtual memory is a cooperative venture between the operating system and a hardware memory management unit (MMU) that almost always exists on the same chip as the CPU.

> 虚拟内存是操作系统和硬件内存管理单元(MMU)之间的合作冒险，几乎总是存在于与 CPU 相同的芯片上。

### The Virtual Memory Big Picture

Here’s what happens in virtual memory systems: a process’s virtual address space (its view of memory) is divided into many small sections (often as small as 4KB in size) called _pages_. If sufficient system memory is available then the first time the process accesses an address in a given page, the operating system allocates an unused frame of system memory to back the page (that is, to store the content that the application writes to it). Later you see that the job of the MMU is to keep track of which pages are backed and to transparently route requests from the CPU for data from a page to the appropriate frame.

> 这是虚拟内存系统中发生的情况：一个过程的虚拟地址空间(其内存的视图)分为许多小部分(通常很小的大小为 4KB)，称为 _pages_。如果有足够的系统内存可用，则该进程首次访问给定页面中的地址时，操作系统将分配未使用的系统内存框架以备份页面(即存储应用程序写入的内容)。稍后，您会看到 MMU 的作业是要跟踪哪些页面的备份，并从 CPU 透明地将请求从页面到适当的框架进行数据。

If there’s enough memory for everybody, that’s where the situation stays. However, as more processes are loaded by the operating system, and as those processes begin to access memory, you may reach a point where there are no remaining unused frames to back all of the pages that are in use in the system. In this case, the operating system must evict one or more frames, writing their contents to disk and freeing them up to back some other page. The evicted pages remain stored on disk until they are needed again. Then some other pages are evicted from system memory and the formerly evicted pages are loaded again.

> 如果每个人都有足够的 Mem，那就是情况所在。但是，由于操作系统加载了更多的进程，并且随着这些过程开始访问内存，您可能到达没有剩余的未使用帧来备份系统中使用的所有页面。在这种情况下，操作系统必须驱逐一个或多个帧，将其内容写入磁盘并将其释放到其他页面上。被驱逐的页面保留在磁盘上，直到再次需要。然后，其他一些页面被驱逐从系统内存中驱逐，并再次加载了以前被驱逐的页面。

This mechanism is called _paging._ The area on disk dedicated to storing pages is called a pagefile. A page file may be an actual disk file, or it may be an entire dedicated disk partition that contains nothing other than pages that have been written to disk. The process of writing a page to its page file is informally called swapping out and the space on disk where pages are stored is informally called swap space. In the Raspbian operating system, swap space exists by default in the file `/var/swap`.

> 这种机制称为 _分页_。磁盘上专用于存储页面的区域称为页面文件。一个页面文件可能是一个实际的磁盘文件，或者它可能是一个完整的专用磁盘分区，除了已写入磁盘的页面外什么都不包含。将页面写入其页面文件的过程非正式地称为换出，而存储页面的磁盘空间非正式地称为交换空间。在 Raspbian 操作系统中，交换空间默认存在于文件 `/var/swap` 中。

The net effect of virtual memory management is to give each process the illusion that it has its own private system memory space separate from that of all other processes, with as much memory as it requires.

> 虚拟内存管理的净效应是给每个过程的幻觉，即它具有自己的私人系统内存空间与所有其他过程的私有系统内存空间，并具有尽可能多的内存。

### Mapping Virtual to Physical

Does this sound familiar? It should. Virtual memory is indeed a kind of caching technology, albeit one driven by the need for space rather than speed. The central trick, as with caching mechanisms, is to relate addresses in the larger, virtual memory system to addresses in the smaller physical system memory, and to decide on a policy for evicting pages when system memory is exhausted.

> 这听起来很熟悉吗？它应该。虚拟内存确实是一种缓存技术，尽管它是由对空间而不是速度的需求驱动的。与缓存机制一样，中心窍门是将较大的虚拟内存系统中的地址与较小的物理系统内存中的地址联系起来，并决定在系统内存耗尽时驱逐页面的策略。

When a process is launched, the operating system creates a structure in system memory called a page table, which describes the address space of the new process. Each entry in the table describes one page belonging to the process, including what frame (if any) backs the page in system memory and what operations (for example reading and writing data or fetching instructions) may be performed on the page. If a page has been swapped out, it is marked in the table as invalid (unavailable for any operations). An attempt to access an invalid page results in a page fault, which the operating system must handle.

> 启动过程后，操作系统将在系统内存中创建一个称为页面表的结构，该结构描述了新过程的地址空间。表中的每个条目都描述了属于该过程的一页，包括系统内存中的页面(如果有的话)以及可以在页面上执行哪些操作(例如读取和写入数据或获取指令)。如果将页面互换，则表格在表中标记为无效(对于任何操作都无法使用)。尝试访问无效页面的尝试导致操作系统必须处理的页面故障。

> [!TIP]
> Every time the process uses a memory address—for example, the address of the next machine instruction to be executed—a memory translation operation is performed. The virtual address requested is translated to the corresponding physical address in system memory. This happens in two parts:
> 每次进程使用内存地址时——例如，下一条要执行的机器指令的地址——都会执行一次内存翻译操作。请求的虚拟地址被转换为系统内存中相应的物理地址。这发生在两个部分：

1. The frame containing the physical address is located in memory.
2. The offset into the frame to which the physical address `points` is extracted from the virtual address. This resolves the physical address to a single data word within a frame.

> 1. 包含物理地址的框架位于内存中。
> 2. 从虚拟地址提取物理地址 `点` 的框架的偏移。这将物理地址解析到框架内的单个数据字。

The CPU then accesses the data word at the translated physical address in system memory. Figure 3-12 shows a simplified virtual memory system. The process has been given eight pages of virtual memory. Five of those pages are present in system memory frames. The other three pages have been swapped out to swap space. Each virtual memory page has a corresponding entry in the process page table. The process page table points to frames in physical memory where each process page resides. We summarise the state of the permission bits as a single valid bit, which is set to binary 0 for any process page that is not currently in memory.

> 然后，CPU 在系统内存中的翻译物理地址处访问数据字。图 3-12 显示了简化的虚拟内存系统。该过程已获得八页虚拟内存。这些页面中有五页存在于系统内存框架中。其他三页已交换为交换空间。每个虚拟内存页面都有一个相应的条目在 `进程` 页面表中。过程页面表指向每个进程页面所在的物理内存中的帧。我们将权限位的状态总结为单个有效位，该位设置为当前不在内存中的任何进程页面的二进制文件。

> ![[FIGURE 3-12:](#06_9781119183938-ch03.xhtml#rc03-fig-0012) How virtual memory paging works](./media/images/9781119183938-fg0312.png)

So what happens when the CPU requests an address in process page 3? That page is not in memory and the request triggers a page fault. The memory manager must then bring in page 3 from swap space.

> 那么，当 CPU 在 Process 3 中请求地址时会发生什么？该页面不在内存中，请求会触发页面故障。然后，内存管理器必须从交换空间中引入第 3 页。

> [!NOTE]
> that the process only has five frames in physical memory and those frames are all in use. The memory manager has to make room by evicting one of the in-memory pages to swap space. Only then can the memory manager load page 3 and allow the CPU to continue on. In reality, the operating system generally attempts to schedule another independent process while the input/output (I/O) operations associated with paging occur and may speculatively write to disk pages that it expects to evict soon, thus speeding up the paging-out process.
> 该进程在物理内存中只有五个帧，并且这些帧都在使用中。内存管理器必须通过将内存中的页面之一逐出到交换空间来腾出空间。只有这样，内存管理器才能加载第 3 页并允许 CPU 继续运行。实际上，当与分页相关的输入/输出 (I/O) 操作发生时，操作系统通常会尝试调度另一个独立进程，并且可能会推测性地写入它预计很快就会退出的磁盘页面，从而加快分页过程 .

The decision as to which page to evict to make room for page 3 involves a replacement policy, just as in cache systems, and the policies are often the very same ones. In a LRU policy, it would be the page that had not been used for the longest amount of time.

> 与缓存系统一样，要驱逐出哪个页面腾出空间的页面涉及替换策略，而政策通常是相同的。在 LRU 政策中，这将是最长时间没有使用的页面。

### Memory Management Units: Going Deeper

That’s the view from a height. The key in virtual memory systems is the memory management unit and to understand how MMUs work and what other benefits they bring to a computer, you have to dig a little deeper and see the detailed process of memory access from the eyes of a computer program.

> 从高度来看，这就是景色。**虚拟内存系统中的关键是内存管理单元**，并了解 MMU 的工作方式以及它们带给计算机的其他好处，您必须深入研究，并从计算机程序的眼睛中查看内存访问的详细过程。

Consider a process running on a machine that does not have an MMU. As it executes, it accesses memory to fetch instructions and to read and write data. It takes the addresses that the CPU has generated and use them directly to access memory, so if your program performs a read from address 0, this would automatically read the very first thing contained in the physical SDRAM connected to your CPU chip. Figure 3-13 shows the setup, in which the CPU directly generates physical addresses.

> 考虑在没有 MMU 的计算机上运行的过程。在执行时，它可以访问内存以获取指令并读取和写数据。它需要 CPU 生成的地址并直接使用它们来访问内存，因此，如果您的程序从地址 0 执行读取，则将自动读取与 CPU 芯片连接的物理 SDRAM 中包含的第一件事。图 3-13 显示了设置，其中 CPU 直接生成物理地址。

> ![[FIGURE 3-13:](#06_9781119183938-ch03.xhtml#rc03-fig-0013) Direct use of physical memory addresses](./media/images/9781119183938-fg0313.png)

This is how the earliest single-user computers, early microcomputers and some current embedded systems operate. However, several things are hard to implement in such a setup:

> 这就是最早的单用户计算机，早期微型计算机和一些当前嵌入式系统的方式。但是，在这样的设置中很难实施几件事：

- **Memory protection:** One of the functions of a modern operating system is to isolate processes running in the CPU from one another. In a direct-addressing setup, stability and security suffer, because there is nothing to stop one process from reading from or writing to a section of memory owned by another process.
- **Virtual memory:** You saw in the preceding section that by allowing infrequently used areas of memory to be swapped out to disk, you can support programs that need to work on larger amounts of data than can fit in the machine’s physical memory. In the simple setup (see [Figure 3-13](#06_9781119183938-ch03.xhtml#c03-fig-0013)), there is no mechanism to trap accesses to parts of memory that have been swapped out.
- **Defragmentation:** When a program has been running for a long time, its view of memory often becomes fragmented, with many small memory allocations splitting free space into fragments, none of which may be large enough to support new allocations above a certain size. In this setup there is no way to compact memory to consolidate free space without forcing the application to manage its own memory.
- **内存保护：**现代操作系统的功能之一是隔离 CPU 中运行的过程。在直接编制的设置，稳定性和安全性中，因为没有什么可以阻止一个进程从阅读或写作到另一个过程拥有的一部分内存的一部分。
- **虚拟内存：**您在上一节中看到的，通过允许不经常使用的内存区域将内存的区域换成磁盘，您可以支持需要在机器物理内存中适合大量数据的程序。在简单的设置中(请参见[图 3-13](%EF%BC%8306_9781119183938-CH03.xhtml%EF%BC%83C03-Fig-0013))，没有机制可以将访问到已交换的内存的部分访问。
- **碎片策略：**当程序运行很长时间时，其 Mem 的视图经常变得分散，许多小的内存分配将自由空间分为片段，而这些空间可能没有足够大，可以支持上方的新分配一定尺寸。在此设置中，无需强迫应用程序管理自己的内存即可巩固自由空间。

The solution to all three of these problems is to introduce a layer of remapping between the addresses that are generated by the CPU, which we’ll now refer to as _virtual addresses_, and the physical addresses that reference external memory. The component that performs this remapping is the MMU (see Figure 3-14).

> 解决这三个问题的解决方案是在 CPU 生成的地址之间引入一层重新映射，我们现在将其称为 _virtual addresses_，以及引用外部内存的物理地址。执行此重新映射的组件是 MMU(见图 3-14)。

> ![[FIGURE 3-14:](#06_9781119183938-ch03.xhtml#rc03-fig-0014) An MMU intermediating virtual and physical addresses](./media/images/9781119183938-fg0314.png)

The MMU builds a contiguous virtual address space for the CPU by stitching together noncontiguous pages of physical memory (see Figure 3-15). Different CPUs support various combinations of page sizes; most support 4KB pages and this is the size most commonly used by operating systems like Linux. We assume this page size, and 32-bit virtual and physical addresses, in the following discussion.

> MMU 通过将物理内存的不连续页面缝合在一起，为 CPU 构建一个连续的虚拟地址空间(见图 3-15)。不同的 CPU 支持页面尺寸的各种组合；大多数支持 4KB 页面，这是 Linux 等操作系统最常用的尺寸。在以下讨论中，我们假设此页面大小以及 32 位虚拟和物理地址。

> ![[FIGURE 3-15:](#06_9781119183938-ch03.xhtml#rc03-fig-0015) Stitching the virtual address space together out of 4KB blocks of physical memory](./media/images/9781119183938-fg0315.png)

The MMU dismantles each incoming 32-bit virtual address into a 20-bit page number and a 12-bit (2<sup>12</sup>; that is, 4K) page offset. The page number is looked up in the memory-resident page table, to give a 20-bit frame number and a set of permission bits. If the permission bits indicate that the requested access is valid, the frame number and page offset are re-combined to form the physical address (see Figure 3-16).

> MMU 将每个传入的 32 位虚拟地址拆除为 20 位页码和 12 位(2 <sup> 12 </sup>;即 4K)页面偏移。页码在内存居民页表中查找，以提供 20 位帧号和一组许可位。如果权限位表明请求的访问是有效的，则重新组合帧号和页面偏移以形成物理地址(请参见图 3-16)。

> ![[FIGURE 3-16:](#06_9781119183938-ch03.xhtml#rc03-fig-0016) Converting virtual to physical addresses through lookups in the page table](./media/images/9781119183938-fg0316.png)

This system addresses the three memory challenges described earlier:

> 该系统解决了前面描述的三个内存挑战：

- Fragmentation may be solved trivially by shuffling free pages behind the process’s back. The application doesn’t have to manage its own memory.
- By giving each process a separate table pointing to non-overlapping frames, you can enforce isolation. This requires that the process not be able to write to the page table—a requirement that lies behind the need to create processor privilege levels, which is covered in [Chapter 4](#07_9781119183938-ch04.xhtml). You store the page table in frames that aren’t mapped into the process address space and stop the process from adjusting the page table base pointer.
- Virtual memory can be implemented by marking pages that have been swapped to disk as inaccessible (using the permission bits), catching the page fault that occurs when you access the page, and triggering the paging-in process.

> - 碎片化可以通过将自由页面背后的免费页面改装而成。该应用程序不必管理自己的内存。
> - 通过给每个过程一个单独的表指向非重叠帧，您可以执行隔离。这要求该过程无法写入页面表
> - 这是创建处理器特权级别的需求背后的要求，该级别在[第 4 章](%EF%BC%8307_9781119183938-CH04.XHTML)中涵盖。您将页面表存储在未映射到过程地址空间中的框架中，并阻止该过程调整页面表底座指针。
> - 可以通过标记已互换为无法访问的磁盘的页面来实现虚拟内存(使用权限位)，捕获访问页面时发生的页面故障，并触发分页进程。

### Multi-Level Page Tables and the TLB

Page table entries are usually 4 bytes in size, so your page table will be 2<sup>32</sup> ÷ 2<sup>12</sup> × 4 = 4MB in size. If you require a page table per process (as is required to enforce isolation) this gets expensive, fast. The solution is to implement a multi-level page table. Two-level page tables save space by exploiting the sparseness of process address spaces—very few processes require a full 4GB of virtual address space. In a typical two-level system, the most significant 10 bits of the virtual address are used to select an entry in a first-level page table, which optionally points to a second-level page table that covers 4MB of virtual address space (see Figure 3-17). If there is no valid page in that 4MB window (as shown by an X in the first-level table entry) you may omit the second-level table, saving memory.

> 页面表条目通常为 4 个字节，因此您的页面表格为 2 <sup> 32 </sup>÷2 <sup> 12 </sup>×4 = 4MB 大小。如果您每个过程需要一个页表(按照执行隔离的要求)，这变得昂贵，快速。解决方案是实现多级页面表。两级页面表通过利用过程地址空间的稀疏度来节省空间 - 很少有过程需要完整的 4GB 虚拟地址空间。在典型的两级系统中，使用虚拟地址的最重要的 10 位用于在第一级页表中选择一个条目，该条目可选地指向涵盖虚拟地址空间 4MB 的第二级页面表(请参阅图 3-17)。如果该 4MB 窗口中没有有效的页面(如第一级表条目中的 X 所示)，则可以省略第二级表，保存内存。

> ![[FIGURE 3-17:](#06_9781119183938-ch03.xhtml#rc03-fig-0017) A two-level page table system for translating virtual addresses to physical addresses](./media/images/9781119183938-fg0317.png)

One last thing: with a two-level page table, you now must perform two additional accesses to memory every time you access memory! Have you just crippled your processor by tripling the cost of memory access? Fortunately, you can fix the problem by caching the most recent few translations in a fully or highly associative cache inside the processor, called the translation lookaside buffer (TLB). Due to locality of reference (described earlier in this chapter) and because each TLB entry `covers` 4KB of address space, even a small TLB has an excellent hit rate.

> 最后一件事：**使用两级页面表**，您现在必须在每次访问内存时执行两次对内存的访问！您只是通过将内存访问的成本增加了三倍，使处理器瘫痪了？幸运的是，您可以通过在处理器内的完全或高度关联的缓存中缓存最新的翻译来解决该问题，称为 **Translation LookAside Buffer(TLB)**。由于参考的局部性(本章前面描述)和每个 TLB 条目 `覆盖` 地址空间的 4KB，即使是小型 TLB 也具有出色的命中率。

To avoid contention between accesses to the TLB from instruction fetch and data accesses, the ARM11 core actually has two small micro-TLBs, one associated with the L1 instruction cache and the other associated with the L1 data cache, along with a larger (but still relatively small) central TLB.

> 为了避免通过指令获取和数据访问访问 TLB 之间的争论，ARM11 核心实际上有两个小型 TLB，一个与 L1 指令缓存相关相对较小)中央 TLB。

### The Raspberry Pi Swap Problem

As good as virtual memory sounds, there is a catch: the Raspberry Pi lacks a mass storage device appropriate for swap space. There is no hard drive, as there is on laptops and desktops. SD cards were not designed for use with filesystems that write to `disk` as frequently as Raspbian’s. The flash storage medium in an SD card is composed of memory cells that may be changed only a certain number of times. That number is large but it is still limited, and every time a cell is written to, it’s one step closer to failure. (For more on this, see [Chapter 4](#07_9781119183938-ch04.xhtml).) When physical memory is full, a virtual memory system begins reading and writing to its swap space a lot. To avoid killing the SD card, the Raspbian OS is configured to use swap space only when absolutely necessary. Remember that a single SD card contains not only swap space but also everything else in your Raspberry Pi system, including Raspbian and all of your installed programs and configuration data. If the SD card dies, the system could become corrupt and you would have to rebuild it from scratch on a new card.

> 像虚拟内存的声音一样好，也有一个捕获：Raspberry Pi 缺少适合交换空间的质量存储设备。没有笔记本电脑和台式机上没有硬盘驱动器。SD 卡并非设计用于与 Raspbian 一样频繁地写入 `磁盘` 的文件系统。SD 卡中的闪存存储介质由内存单元组成，这些存储单元可能仅在一定次数中更改。这个数字很大，但仍然有限，每次牢房都写入，它就会更接近故障。(有关更多信息，请参见[第 4 章](%EF%BC%8307_978111919183938-CH04.XHTML)。)当物理内存已满时，虚拟内存系统开始读取和写入其交换空间。为了避免杀死 SD 卡，只有在绝对必要的情况下，Raspbian OS 才能使用交换空间。请记住，单个 SD 卡不仅包含交换空间，还包含 Raspberry Pi 系统中的其他所有内容，包括 Raspbian 和所有已安装程序和配置数据。如果 SD 卡死亡，该系统可能会损坏，您将不得不从头开始重建新卡。

A second, less serious problem is that SD cards are not especially fast, as flash storage devices go. Once Raspbian begins swapping, the performance of the system could slow to a crawl. Think of virtual memory on the Raspberry Pi as a safety mechanism to protect against crashes, and not performance enhancement. If you notice everything getting slow, you know that you’re out of memory and need to start closing programs to make swapping unnecessary.

> 第二个不太严重的问题是，随着闪存存储设备的运行，SD 卡并不是特别快。一旦 Raspbian 开始交换，系统的性能可能会放慢爬网。将 Raspberry Pi 上的虚拟 Mem 视为防止崩溃而不是增强性能的安全机制。如果您注意到一切都变得越来越慢，就会知道自己不在 Mem 中，需要开始关闭程序以使交换不必要。

### Watching Raspberry Pi Virtual Memory

> [!note]
> 虚拟内存监视工具

It’s possible to run a simple memory monitor utility called vmstat (for `virtual memory statistics` ) in a Raspbian terminal window. The vmstat utility summarises the current state of the Raspberry Pi virtual memory system and updates it, either a set number of times or at a set time interval. The vmstat utility is command-line only, and must be run from a terminal window, such as the one displayed by LXTerminal.

> 可以在 Raspbian 终端窗口中运行一个名为 VMSTAT(用于 `虚拟内存统计` )的简单内存监视器实用程序。VMSTAT 实用程序总结了 Raspberry Pi 虚拟内存系统的当前状态，并在设定的时间间隔内对其进行了更新。VMSTAT 实用程序仅是命令行，必须从终端窗口(例如 LXTerminal 显示的窗口)运行。

Open an instance of LXTerminal and type the following command:

```
    vmstat
```

Launched this way, vmstat displays one line of data beneath a two-line column header. This is the state of the virtual memory system at the moment the command was issued. You can repeat the command after an elapsed time interval and limit the number of repeats to a specified count by using two optional parameters:

> 通过这种方式启动，VMSTAT 在两行列标题下显示了一行数据。这是发出命令时虚拟内存系统的状态。您可以在经过的时间间隔后重复该命令，并通过使用两个可选参数将重复次数限制为指定计数：

```
    vmstat [interval] [count]
```

The interval parameter is given in seconds. If you give an interval parameter but not a count parameter, vmstat continues to post an update at each interval as long as you let it run. Output from vmstat may be redirected to a file if you’d like to keep the data for later analysis.

> 间隔参数以秒为单位给出。如果您给出一个间隔参数，而不是计数参数，则只要您让它运行，VMSTAT 就会继续以每个间隔发布更新。如果您想保留数据以备后续分析，则可以将 VMSTAT 的输出重定向到文件。

The meaning of the various columns displayed by vmstat is summarised in Table 3-2.

> 表 3-2 总结了 VMSTAT 显示的各种列的含义。

[Table 3-2](#06_9781119183938-ch03.xhtml#rc03-tbl-0002) vmstat’s Columns

| Column | Meaning                                                                  |
| :-----: | ------------------------------------------------------------------------ |
|   `r`   | The number of processes currently waiting to run                         |
|   `b`   | The number of processes currently  `asleep`                              |
| `swpd` | The number of pages that have been written out to swap space             |
| `free` | The amount of unallocated memory                                         |
| `buff` | The amount of allocated memory in use                                    |
| `cache` | The amount of memory that could be reclaimed for use by swapping         |
|  `si`  | The amount of memory in KB swapped in per second—usually 0              |
|  `so`  | The amount of memory in KB swapped out per second—usually 0             |
|  `bi`  | The number of blocks read from block devices per second                  |
|  `bo`  | The number of blocks written to block devices per second                 |
|  `in`  | The number of system interrupts per second                               |
|  `cs`  | The number of context switches per second                                |
|  `us`  | The percentage of time the CPU is spending on all non-kernel processes   |
|  `sy`  | The percentage of time the CPU is spending on kernel processes           |
|  `id`  | The percentage of time the CPU is idle                                   |
|  `wa`  | The percentage of time the CPU is waiting for I/O operations to complete |

|  栏目  | 含义                                      |
| :-----: | ----------------------------------------- |
|   `r`   | 当前等待运行的进程数                      |
|   `b`   | 当前 `睡眠` 的进程数                      |
| `swpd` | 已写出到交换空间的页数                    |
| `free` | 未分配的内存量                            |
| `buff` | 使用中的已分配内存量                      |
| `cache` | 可以通过交换回收使用的内存量              |
|  `si`  | 每秒换入的内存量(以 KB 为单位)— 通常为 0 |
|  `so`  | 每秒换出的内存量(以 KB 为单位)— 通常为 0 |
|  `bi`  | 每秒从块设备读取的块数                    |
|  `bo`  | 每秒写入块设备的块数                      |
|  `in`  | 每秒系统中断次数                          |
|  `cs`  | 每秒上下文切换次数                        |
|  `us`  | CPU 在所有非内核进程上花费的时间百分比    |
|  `sy`  | CPU 花在内核进程上的时间百分比            |
|  `id`  | CPU 空闲时间的百分比                      |
|  `wa`  | CPU 等待 I/O 操作完成的时间百分比         |

Leave vmstat running while you open and close application windows and watch what happens to the numbers. One thing to keep in mind is that the `bi` and `bo` columns are not dedicated to swap space access. They include it, but they also include ordinary read/write access to the SD card filesystem. This includes logging and web caching, so if you see an uptick in `bi` and `bo` while using a web browser like Midori, remember that network adapters are not block devices and what you’re seeing is ordinary filesystem traffic between the browser and the SD card. The `swpd` column reports total swap space page writes and if it remains at 0, virtual memory has not begun swapping. The `si` and `so` columns report the speed of swap space reads and writes. As with `swapd`, they will usually be zero. If you start to see nonzero values in `si` and `so`, the Raspberry Pi may have begun to thrash. Close some apps and see if the swap traffic goes away.

> 在您打开和关闭应用程序窗口时让 vmstat 保持运行并观察数字的变化。要记住的一件事是 `bi` 和 `bo` 列不专用于交换空间访问。它们包括它，但它们还包括对 SD 卡文件系统的普通读/写访问。这包括日志记录和网络缓存，因此如果您在使用 Midori 等网络浏览器时看到 `bi` 和 `bo` 增加，请记住**网络适配器不是块设备**，您看到的是浏览器之间的普通文件系统流量 和 SD 卡。
> `swpd` 列报告总交换空间页面写入，如果它保持为 0，则虚拟内存尚未开始交换。
> `si` 和 `so` 列报告交换空间读写的速度。与 swapd 一样，它们通常为零。如果您开始在 si 和 so 中看到非零值，Raspberry Pi 可能已经开始抖动。关闭一些应用程序并查看交换流量是否消失。
