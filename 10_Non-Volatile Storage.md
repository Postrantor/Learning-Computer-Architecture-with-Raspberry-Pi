Chapter 6

# Non-Volatile Storage

**NON-VOLATILE DATA STORAGE** has been available since long before anyone ever dreamed about computers. Human memory has a limited lifespan, but spoken language allows information to cross the gap between individuals, allowing that information to live longer than any single person. Human memory, however, is prone to errors and data loss. The development of written language means that information can be placed somewhere independent of human memory, at least as long as there is someone who knows how to interpret the language it’s written in. Books, for example, have been called  `software that runs in the mind` —an apt metaphor. More to the point, books are data storage that serves the human computer inside our skulls. They address permanence and the imprecision of memory. Interpretation is up to us.

> **非易失性数据存储**早在任何人梦想计算机之前就已经存在了。人类的记忆寿命有限，但口语可以让信息跨越个人之间的鸿沟，让信息比任何一个人都长寿。然而，人类的记忆容易出错和数据丢失。书面语言的发展意味着信息可以被放置在独立于人类记忆的地方，至少只要有人知道如何解释它所用的语言。例如，书籍被称为 `在大脑中运行的软件` ，这是一个恰当的比喻。更重要的是，书籍是为我们头骨内的人类计算机服务的数据存储。它们解决了记忆的永久性和不精确性。解释由我们决定。

---

> [!NOTE]

Understanding archaic written languages, and ancient scripts such as Mycenaean Linear A, has been a problem in archaeology. Archaeologists have discovered good examples of characters arranged in groups, which may be words; but sadly, the language they express has been forgotten for at least 3,000 years.

> 理解古代书面语言，以及迈锡尼线性 A 等古代文字，一直是考古学中的一个问题。考古学家发现了成组排列的字符的好例子，可能是单词；但遗憾的是，他们所表达的语言已经被遗忘了至少 3000 年。

This chapter looks at computer data storage that falls outside the computer-memory partnership. (In [Chapter 3](#06_9781119183938-ch03.xhtml), we discussed computer memory in detail.) Data storage outside the CPU and electronic memory is often called _mass storage_ because its capacity far exceeds that of conventional computer memory. A more precise term is non-volatile storage, which expresses the primary value of mass storage: its contents remain intact even when the computer powers down or the storage medium is disconnected from the computer. With the short-lived exceptions of magnetic disk and drum memory and later magnetic core memory, computer main memory has been _volatile_, which means its data vanishes when the power drops or the computer malfunctions in other ways.

> 本章介绍不属于计算机内存伙伴关系的计算机数据存储。(在[第 3 章](#06*9781119183938-ch03.xhtml)中，我们详细讨论了计算机内存。)CPU 和电子存储器之外的数据存储通常被称为 mass storage*，因为它的容量远远超过了传统的计算机存储器。更准确的术语是非易失性存储，它表达了大容量存储的主要价值：即使计算机断电或存储介质与计算机断开连接，其内容也保持完整。除了磁盘和磁鼓存储器以及后来的磁芯存储器这一短暂的例外，计算机主存储器一直是可替换的，这意味着当电源下降或计算机以其他方式发生故障时，其数据将消失。

## Punched Cards and Tape

The earliest mass-storage technologies had a lot in common with books: they were composed of paper. Also, they were developed to serve technologies that were not computers, and not, in fact, electronic at all. In the same ways that computers were built on the shoulders of calculators, paper-based storage drew on early communications and tabulation machinery.

> 最早的海量存储技术与书籍有很多共同之处：它们是由纸张组成的。此外，它们的开发是为了服务于非计算机的技术，事实上，根本不是电子技术。就像计算机建立在计算器的肩膀上一样，纸本存储借鉴了早期的通信和制表机器。

### Punched Cards

Just as writing might be considered  `meaningful ink markings applied to paper` , paper-based mass storage is basically meaningful holes punched in paper or pasteboard. What many call the  `IBM card`  or  `computer punched card`  is older than IBM and much older than computers. Although the idea of a punched card goes back to Charles Babbage, and before him to the Jacquard Loom, widespread use of data stored on punched cards began with Herman Hollerith, who created a card-based system to tabulate data from the American census of 1890. The original Hollerith card placed round holes at standardised locations on the card, for the sake of mechanical tabulators, but the meaning of each hole was defined by whoever was using the cards. The first-generation tabulator machines were purely mechanical and simply counted holes in a given position on the card. Later machines incorporated electromechanical counters that could do limited cross-tabulation on the cards—for example, tabulating how many instances there were of cards containing punches at several specific locations at once. This allowed the Census Bureau to count easily the number of women aged 18 to 35 or the number of men in a household working in agriculture, and so on.

> 正如书写可能被认为是 `应用在纸上的有意义的墨水标记` 一样，纸基大容量存储基本上是在纸或纸板上打孔的有意义孔。许多人所说的 `IBM 卡` 或 `计算机穿孔卡` 比 IBM 更古老，也比计算机更古老。尽管穿孔卡片的概念可以追溯到查尔斯·巴贝奇(Charles Babbage)，在他发明提花织机之前，存储在穿孔卡片上的数据的广泛使用始于赫尔曼·霍勒瑞斯(Herman Hollerith)，他创建了一个基于卡片的系统，将 1890 年美国人口普查的数据制成表格。最初的霍尔瑞斯卡片在卡片上的标准位置放置圆孔，以便于机械制表，但每个孔的含义由使用卡片的人定义。第一代制表机是纯机械的，只需在卡片上的给定位置计算孔数。后来的机器采用了机电计数器，可以在卡片上进行有限的交叉制表，例如，一次在几个特定位置制表有多少张卡片含有冲头。这使得人口普查局可以很容易地统计 18 岁至 35 岁的女性人数或家庭中从事农业工作的男性人数，等等。

The Hollerith technology was wildly successful. Hollerith’s 1896 Tabulating Machine Company later merged with three other similar firms, and under the leadership of Thomas Watson the company became International Business Machines (IBM). The punched card format of 80 columns of 12 rectangular holes on a card measuring 7 ⅜` × 3 ¼` with a cropped corner to define orientation was standardised in 1929; it remained basically the same until the technology went out of broad use in the 1980s. (A picture of a late-era IBM card is shown in the previous chapter, [Figure 5-3](#08_9781119183938-ch05.xhtml#c05-fig-0003).) The meaning of holes adhered to no single standard and remained application-specific for many years. Extended Binary Coded Decimal Interchange Code (EBCDIC), the first strong standard for encoding characters on IBM cards, did not appear until 1964 and was introduced with the System/360 mainframe.

> 霍尔瑞斯技术非常成功。霍尔瑞斯的 1896 年制表机公司后来与其他三家类似公司合并，在托马斯·沃森的领导下，该公司成为国际商业机器公司(IBM)。一张卡片上 80 列 12 个矩形孔的穿孔卡片格式，尺寸为 7⅜1929 年，`×3¼` (带有裁剪角以定义方向)被标准化；直到 20 世纪 80 年代该技术不再广泛使用，它基本保持不变。(上一章[图 5-3](#08_9781119183938-ch05.xhtml#c05-fig-0003) 中显示了一张晚期 IBM 卡的图片。)孔的含义没有遵循单一标准，多年来一直是特定于应用的。扩展二进制编码十进制交换码(EBCDIC)是 IBM 卡上编码字符的第一个强大标准，直到 1964 年才出现，并随 System/360 大型机引入。

### Tape Data Storage

As papermaking technology grew good enough to manufacture continuous lengths of paper tape, inventors began using it for data storage. Scottish inventor Alexander Bain incorporated a crude punched tape system to feed his 1846 experimental  `chemical teletype` , which used an electric current to print marks on chemically treated paper. Although electromechanical teleprinters were used sporadically from the 1850s on, the Teletype machine as we know it today did not really become a force until it was standardised and given a typewriter-style keyboard in the first quarter of the twentieth century. Messages were encoded by punching hole patterns in a length of paper tape, and the tape was queued up to be fed into the telegraph system as time allowed. The first standardised encoding system for teleprinter paper tape was originally devised by Emile Baudot in the 1870s and later adapted for teleprinter use by Donald Murray around 1900. The Baudot-Murray code (generally abbreviated to  `Baudot` ) used combinations of holes in five columns. The 5-bit Baudot code remained the standard for teleprinters for more than 60 years, until the 7-bit American Standard for Code Information Interchange (ASCII) system was introduced in 1963.

> 随着造纸技术发展到足以制造连续长度的纸带，发明者开始将其用于数据存储。苏格兰发明家亚历山大·贝恩(Alexander Bain)在 1846 年的实验 `化学电传打字机` 中使用了一种粗糙的穿孔胶带系统，该系统利用电流在经过化学处理的纸张上打印标记。尽管从 19 世纪 50 年代开始，机电电传打字机零星使用，但我们今天所知的电传打字机直到 20 世纪第一季度被标准化并被赋予打字机式键盘，才真正成为一种力量。信息是通过在一段纸带上打孔来编码的，在时间允许的情况下，纸带被排队送入电报系统。第一个电传打字机纸带的标准化编码系统最初由埃米尔·鲍多(Emile Baudot)在 19 世纪 70 年代设计，后来在 1900 年左右被唐纳德·默里(Donald Murray)改编为电传打字机使用。鲍多·穆雷代码(通常缩写为 `鲍多` )使用五列孔的组合。在 1963 年推出 7 位美国代码信息交换标准(ASCII)系统之前，5 位波特码一直是电传打字机的标准，长达 60 多年。

The use of teleprinter paper tape in computing was almost accidental. The 1930 Model 15 Teletype console was the mainstay of the world’s teleprinter network for almost 30 years. It was rugged and highly configurable, and it could be operated by someone who hadn’t had extensive training. However, it had serious shortcomings: the machine’s 5-bit Baudot code could only express 60 different values in two groups of 30, which were selected by two shift codes. This was enough to express upper-case characters, numeric digits and common punctuation, plus a handful of control codes like bell and carriage return. Lower-case characters did not become possible on teleprinter hardware until the mid-1960s.

> 在计算机中使用电传打字机纸带几乎是偶然的。1930 年的 15 型电传打字机控制台是近 30 年来世界电传打字机网络的中流砥柱。它坚固耐用，高度可配置，可以由没有受过广泛培训的人操作。然而，它有严重的缺点：该机器的 5 位 Baudot 代码只能在两组 30 个值中表达 60 个不同的值，这些值由两个移位码选择。这足以表达大写字符、数字和常用标点符号，再加上一些控制代码，如铃和回车。直到 20 世纪 60 年代中期，小写字符才在电传打印机硬件上成为可能。

A committee was convened by the American Standards Association in 1960 to establish a modernised standard for communications data encoding. Among other goals, the X3.2 committee wanted to expand encoding to allow lower-case characters and more punctuation. This required at least 7 bits, and when the ASCII standard was released in 1964, it was a 7-bit code. Eight-row paper tape systems were being deployed at that time, which allowed ASCII encoding plus a single parity bit on each row to help detect characters that had been garbled in transmission. The ASCII character codes are shown in Figure 6-1. Each entry in the chart shows the character plus its hexadecimal and decimal numeric equivalents.

> 1960 年，美国标准协会召集了一个委员会，以建立一个现代化的通信数据编码标准。除其他目标外，X3.2 委员会希望扩展编码，以允许小写字符和更多标点符号。这至少需要 7 位，当 1964 年 ASCII 标准发布时，它是一个 7 位代码。当时正在部署八行纸带系统，该系统允许 ASCII 编码加上每行一个奇偶校验位，以帮助检测传输中出现的乱码字符。ASCII 字符代码如图 6-1 所示。图表中的每个条目都显示该字符及其十六进制和十进制等效数字。

![[FIGURE 6-1:](#09_9781119183938-ch06.xhtml#rc06-fig-0001) ASCII character encoding](./media/images/9781119183938-fg0601.png)

Eight-row tape allowed something else: binary encoding of 8-bit quantities. Minicomputer manufacturers designed their interfaces to allow the use of inexpensive Teletype consoles like the mid-1960s Model 33 ASR. They were mass-produced and thus much less expensive than IBM’s computer line printers. In addition to acting as operator consoles, the Model 33 eight-row tape punches and readers could store and read binary data, one byte per row. Given the high cost of IBM’s magnetic tape systems (more on this shortly), the use of paper tape in minicomputer shops was a natural, and it continued until minicomputers themselves passed out of broad use in the 1980s. A sample of 8-bit paper tape is shown in Figure 6-2.

> 八行磁带允许其他东西：8 位量的二进制编码。微型计算机制造商设计了他们的接口，以允许使用廉价的 Teletype 控制台，如 20 世纪 60 年代中期的 33 型 ASR。它们是大规模生产的，因此比 IBM 的计算机行式打印机便宜得多。除了充当操作员控制台外，33 型八行磁带打孔器和读取器还可以存储和读取二进制数据，每行一个字节。考虑到 IBM 磁带系统的高成本(稍后将详细介绍)，在小型计算机商店使用纸带是很自然的，并且一直持续到 1980 年代小型计算机本身不再广泛使用。8 位纸带样本如图 6-2 所示。

![[FIGURE 6-2:](#09_9781119183938-ch06.xhtml#rc06-fig-0002) 8-bit paper tape](./media/images/9781119183938-fg0602.png)

Late in the paper tape era, tapes made of Mylar became available, which made the tape much more resistant to wear and damage. Using any sort of punched tape for archiving was a slow process, but it was by far the least expensive archiving technology available for small systems until the advent of floppy diskettes.

> 在纸带时代后期，由聚酯薄膜制成的胶带变得可用，这使得胶带更耐磨损。使用任何类型的穿孔磁带进行归档都是一个缓慢的过程，但在软盘出现之前，这是迄今为止用于小型系统的最便宜的归档技术。

One of the key attributes of both punched card and paper tape storage is that it was purely _sequential_. Cards ran through the reader one at a time, in order. Data was read from the tape, one 5- or 8-bit row at a time. It was not just sequential, it was sequential in one direction: forward. Theoretically paper tape could be run backwards through a reader, but in practice commercial tape readers ran tape in only one direction. This meant that random access to data on cards or tape was simply impossible. Something approaching tape random access became possible only when IBM developed 9-track bidirectional magnetic tape decks in 1964. After that innovation appeared, paper tape’s days were numbered, and it was increasingly confined to low-end minicomputers like those from Digital Equipment Corporation.

> 穿孔卡片和纸带存储的一个关键特性是它是纯顺序存储的。卡片按顺序一张一张地通过读卡器。从磁带读取数据，每次读取一行 5 或 8 位数据。这不仅仅是顺序的，而是一个方向的顺序：向前。从理论上讲，纸带可以通过读出器向后运行，但实际上商业磁带读出器只能在一个方向上运行磁带。这意味着随机访问卡或磁带上的数据是不可能的。只有在 1964 年 IBM 开发了 9 轨双向磁带组时，接近磁带随机存取的技术才成为可能。这一创新出现后，纸带的日子屈指可数，它越来越局限于低端小型计算机，如数字设备公司的小型计算机。

### The Dawn of Magnetic Storage

Paper tape is important in the history of computing mostly because it brought the ASCII character encoding system out of telecommunications and made it the standard in non-mainframe computing. As mainframes themselves were traded in for server farms, ASCII eventually dominated the computer industry from top to bottom.

> 纸带在计算历史上很重要，主要是因为它将 ASCII 字符编码系统从电信中带出来，并使其成为非大型机计算的标准。随着大型机本身被换成服务器场，ASCII 最终从上到下统治了计算机行业。

Paper tape was nowhere near the most popular tape storage ever created. In 1953, IBM introduced its vacuum-tube 701 series of mainframe computers. Mass storage for the 701 series consisted of IBM punched cards and a new technology for IBM: magnetic tape. The 727 tape drive was not the first magnetic tape deck (Univac had one by 1951) but it was the drive that brought magnetic tape storage into the mainstream. A single 2,400ft reel of ½` cellulose acetate (later Mylar) tape could hold roughly 6 megabytes (MB) and transfer data from tape to the central processing unit (CPU) at a speed of 15,000 characters per second. The 727’s successor, the IBM 729, could store 11MB on a similar reel and had a peak transfer rate of 90,000 characters per second. By the end of the mainframe magnetic tape era, the typical IBM magnetic tape deck could write 140MB on a 2,400ft reel, and transfer data at 1,250,000 8-bit characters or binary bytes per second.

> 纸带远不是有史以来最流行的磁带存储。1953 年，IBM 推出了其真空管 701 系列大型计算机。701 系列的大容量存储包括 IBM 穿孔卡和 IBM 的一项新技术：磁带。727 磁带机不是第一个磁带机(Univac 在 1951 年就有了一个)，但它是将磁带存储带入主流的磁带机。一卷 2400 英尺的 ½ 英寸醋酸纤维素(后来的聚酯薄膜)磁带可以容纳大约 6 兆字节(MB)的数据，并将数据从磁带传输到中央处理单元(CPU)以每秒 15000 个字符的速度。727 的继任者 IBM 729 可以在类似的卷盘上存储 11MB，峰值传输速率为每秒 90000 个字符。到大型机磁带时代结束时，典型的 IBM 磁带组可以在 2400 英尺的卷盘上写入 140MB，并以每秒 125000 个 8 位字符或二进制字节的速度传输数据。

After the introduction of IBM’s System/360 in 1964, tapes stored data on 9-track reels, with 8 data bits written in parallel across eight of the tracks and a parity bit in the ninth track for checking data integrity. The System/360 line also introduced the EBCDIC character-encoding standard, which IBM had created in 1963 to bring order to character encoding across its very broad product line. EBCDIC was an 8-bit standard that could express 256 different characters. It included lower-case characters from the outset, as well as a significant number of unassigned codes that were used in local applications for non-English characters and special-purpose symbols. These local variations made EBCDIC harder to use than 7-bit ASCII, and although EBCDIC was a universal encoding standard on IBM hardware until nearly the end of the mainframe era, ASCII eventually replaced it, even on IBM hardware. The general problem of non-English character encoding was eventually solved by the Unicode system, which established standards for expressing more than 100,000 distinct characters (at the time of writing) using both 8-bit and 16-bit encodings.

> 1964 年 IBM 推出 System/360 后，磁带将数据存储在 9 个磁道的磁带盘上，其中 8 个数据位并行写入 8 个磁道，第 9 个磁道中有一个奇偶校验位用于检查数据完整性。System/360 系列还引入了 EBCDIC 字符编码标准，IBM 于 1963 年创建了该标准，以在其非常广泛的产品线中为字符编码带来秩序。EBCDIC 是一种 8 位标准，可以表示 256 个不同的字符。它从一开始就包括小写字符，以及大量未分配的代码，这些代码在本地应用程序中用于非英语字符和特殊用途符号。这些局部变化使得 EBCDIC 比 7 位 ASCII 更难使用，尽管直到大型机时代接近尾声，EBCDIC 还是 IBM 硬件上的通用编码标准，但 ASCII 最终取代了它，甚至在 IBM 硬件上也是如此。非英语字符编码的一般问题最终由 Unicode 系统解决，该系统建立了使用 8 位和 16 位编码来表示超过 100000 个不同字符(在编写时)的标准。

Magnetic tape outlasted mainframes and remains in limited use to this day. Early low-end microcomputers used off-the-shelf consumer audio cassette decks for non-volatile storage of programs and data. Even after floppy diskettes became common, audio cassettes were used for archival backup due to their low cost. Information was typically encoded using a simple modulation scheme such as frequency-shift keying (FSK), in which zeros and ones are sent as pure tones of different frequencies, and an ordinary 90-minute cassette could contain about 650 kilobytes (KB) per side.

> 磁带的使用寿命超过了大型机，直到今天仍然有限。早期的低端微型计算机使用现成的消费级音频盒式磁带，用于程序和数据的非易失性存储。即使在软盘变得普遍之后，由于成本低廉，盒式磁带也被用于存档备份。信息通常使用简单的调制方案进行编码，如频移键控(FSK)，其中零和一作为不同频率的纯音发送，普通的 90 分钟盒式磁带每边可容纳约 650 千字节(KB)。

Since the 1980s, nearly all magnetic tape-based mass storage systems have used tape completely enclosed in cartridges. This eliminates any need for the user to hand-thread the tape, and allows the rapid removal and replacement of one tape data set with another by unskilled operators. High-capacity tape cartridges are still in use for archival backup, although cloud-based backup on remote servers is gradually replacing tape as the primary commercial archiving technology, with tape surviving mostly on  `legacy`  (older) hardware.

> 自 20 世纪 80 年代以来，几乎所有基于磁带的大容量存储系统都使用完全封装在盒式磁带中的磁带。这消除了用户手动穿带的任何需要，并允许不熟练的操作员快速移除和替换一个磁带数据集。高容量盒式磁带仍在用于归档备份，尽管远程服务器上基于云的备份正逐渐取代磁带成为主要的商业归档技术，磁带主要依靠 `传统` (较旧)硬件生存。

Let’s take a much closer look at how magnetic recording works.

> 让我们更仔细地看看磁记录是如何工作的。

## Magnetic Recording and Encoding Schemes

Digital magnetic tape technology was adapted from analog audio tape systems perfected by German firms (especially BASF) before and during World War II. The fundamental mechanism is the same irrespective of the shape of the underlying storage medium. In truth, it hasn’t changed radically since IBM’s early magnetic tape systems.

> 数字磁带技术是从德国公司(尤其是巴斯夫公司)在第二次世界大战之前和期间完善的模拟音频磁带系统改编而来的。无论底层存储介质的形状如何，基本机制都是相同的。事实上，自 IBM 早期的磁带系统以来，它并没有发生根本性的变化。

In simple terms, it works like this: a very small electromagnet with a microscopic gap between its poles is positioned above a moving magnetic medium, such that the gap is closest to the medium. The electromagnet is called a _head._ Early systems used the same coil and core for both reading and writing. Modern systems use separate heads for reading and writing, but they’re mounted together and move together.

> 简单来说，它的工作原理是这样的：一个极间有微小间隙的非常小的电磁体位于一个移动的磁性介质上方，这样间隙就最接近介质。电磁铁称为磁头早期的系统使用相同的线圈和磁芯进行读写。现代系统使用单独的读写头，但它们安装在一起并一起移动。

For many years the separate read heads were smaller versions of the inductive write heads, but still used the same basic electromagnet-centred design. In the early 1990s, IBM created magnetoresistive (MR) read heads, which were smaller and more sensitive than was possible with inductive read heads. MR heads use a minute length of magnetoresistive material, which changes its resistance in response to changes in the magnetic flux beneath it. MR heads are much more sensitive than inductive heads, which makes it possible for the variations in magnetisation of the magnetic medium to be smaller, allowing more bits to be recorded in the same area. In 2000, IBM took MR head technology further still, using a related physical effect called giant magnetoresistance (GMR) to increase head sensitivity significantly over that of MR heads. GMR read heads and perpendicular write heads together triggered the explosion in hard drive capacity that today gives us multi-terabyte storage on a single drive.

> 多年来，单独的读磁头都是感应式写磁头的较小版本，但仍然使用相同的基本电磁铁中心设计。在 20 世纪 90 年代初，IBM 创造了磁阻(MR)读头，它比感应读头更小、更灵敏。MR 磁头使用微小长度的磁阻材料，该材料会根据其下方磁通量的变化而改变其电阻。MR 磁头比感应磁头灵敏得多，这使得磁介质的磁化变化可以更小，从而允许在同一区域记录更多的比特。2000 年，IBM 进一步采用了 MR 磁头技术，使用了一种称为巨磁阻(GMR)的相关物理效应，大大提高了磁头的灵敏度。GMR 读磁头和垂直写磁头一起引发了硬盘容量的爆炸，如今，我们可以在单个驱动器上存储数 TB 的数据。

The magnetic coating applied to tape or disk platters consists of minute grains of some magnetic material. Early tape and disk systems used red iron oxide; later systems used chromium oxide. Modern hard drives use exotic cobalt-nickel alloys. Even though the grains are roughly spherical, each can act as a separate magnet, complete with distinct north and south magnetic poles. Recording data involves aligning the magnetisation of a number of adjacent grains to form a single _magnetic domain_. This magnetisation is accomplished by sending a controlled electric current through the write head. The direction of alignment of the domains that pass under the head’s gap depends on the direction of an electric current through the head’s write coil.

> 磁带或磁盘上的磁性涂层由一些磁性材料的微小颗粒组成。早期的磁带和磁盘系统使用红色氧化铁；后来的系统使用氧化铬。现代硬盘驱动器使用了奇特的钴镍合金。尽管这些颗粒大致呈球形，但每个颗粒都可以作为一个单独的磁体，具有不同的南北磁极。记录数据涉及将多个相邻晶粒的磁化对准以形成单个磁畴。这种磁化是通过向写入头发送受控电流来实现的。通过磁头间隙下方的磁畴的排列方向取决于通过磁头写入线圈的电流方向。

### Flux Transitions

The boundary between two magnetic domains is referred to as a _flux transition_. It turns out that the read head, whether of a conventional inductive design, or using MR or GMR, can more accurately sense the magnetic field associated with a flux transition than the field associated with the domains themselves. Rather than using the domains to directly represent binary data (with one orientation representing a 0-bit, and the opposite orientation a 1-bit), the control electronics use an encoding scheme to impose a pattern of flux transitions on the medium to represent the data. Numerous schemes have been used over the history of magnetic recording; the trend has been towards more sophisticated schemes that make more efficient use of the medium (that is, they require fewer flux transitions on average to represent each bit). As well as representing the data, a scheme must generally meet two further criteria, regardless of the data written:

> 两个磁畴之间的边界称为_flux 跃迁。事实证明，无论是传统的感应设计，还是使用 MR 或 GMR，读磁头都可以比与磁畴本身相关的磁场更准确地感测与磁通转变相关的磁场。与使用域直接表示二进制数据(其中一个方向表示 0 位，而相反的方向表示 1 位)不同，控制电子设备使用编码方案在介质上施加通量转换模式以表示数据。在磁记录的历史上使用了许多方案；趋势是更复杂的方案，更有效地利用介质(即，它们平均需要更少的通量转换来表示每个比特)。除了表示数据外，方案通常还必须满足两个进一步的标准，无论写入的数据是什么：

- **Timing recovery:** The pattern written to the medium must contain reasonably frequent flux transitions to allow the control electronics to synchronise the position of the head. - **Low digital sum:** There should be an approximately equal number of domains of each orientation, so that the medium as a whole has no magnetic field.

> -**定时恢复：**写入介质的模式必须包含合理频繁的通量转换，以允许控制电子设备同步磁头的位置。-**低数字和：**每个方向的磁畴数量应该大致相等，这样整个介质就没有磁场。

One of the simplest (and earliest) encoding schemes is _frequency modulation_ (FM), in which the difference between a 0-bit and a 1-bit is in the frequency with which flux transitions appear on the magnetic medium, as shown in Figure 6-3. A _bit cell_ is a region on the medium in which a single bit is encoded. Bit cells are all the same physical length. A bit cell with a single flux transition at the beginning is interpreted as a 0-bit. A bit cell with a flux transition at the beginning and another in the middle is interpreted as a 1-bit.

> 最简单(也是最早的)编码方案之一是频率调制(FM)，其中 0 位和 1 位之间的差异在于磁介质上出现磁通转变的频率，如图 6-3 所示。*bit cell* 是媒体上编码单个位的区域。位单元都具有相同的物理长度。开始时具有单个通量转变的位单元被解释为 0 位。一个位单元在开始处具有通量转换，而另一个位于中间，则被解释为 1 位。

![[FIGURE 6-3:](#09_9781119183938-ch06.xhtml#rc06-fig-0003) Magnetic recording of data bits](./media/images/9781119183938-fg0603.png)

FM encoding wastes space on the magnetic medium because it requires room for two flux reversals per bit. Modern encoding techniques make much better use of space through mechanisms like run-length limited (RLL) coding; these encoding schemes process several input bits at once and are thereby able to reduce the average number of flux reversals per bit while still meeting timing and digital sum requirements.

> FM 编码浪费了磁介质上的空间，因为它需要每比特两次磁通反转的空间。现代编码技术通过诸如游程长度限制(RLL)编码等机制更好地利用空间；这些编码方案一次处理几个输入比特，从而能够减少每比特的平均通量反转次数。

Pay close attention to the direction of the arrows in [Figure 6-3](#09_9781119183938-ch06.xhtml#c06-fig-0003). After a flux transition, the magnetic orientation of the medium doesn’t change until the next flux transition. The actual direction of magnetic orientation doesn’t matter, as you can see if you compare the direction shown in the several regions expressing 0-bits. What matters is how many orientation changes (that is, flux reversals) occur per bit cell.

> 密切注意[图 6-3](#09_9781119183938-ch06.xhtml#c06-fig-0003) 中箭头的方向。在通量转换之后，介质的磁性方向直到下一次通量转换时才改变。磁取向的实际方向无关紧要，因为如果你比较几个表示 0 位的区域中显示的方向，就会发现。重要的是每个位单元发生多少方向变化(即通量反转)。

### Perpendicular Recording

The mechanism shown in [Figure 6-3](#09_9781119183938-ch06.xhtml#c06-fig-0003) is called _longitudinal recording_. This means that the magnetic domains in the medium are magnetised in a direction parallel to the moving magnetic medium. Key to longitudinal recording is the position of the read/write head over the moving medium. The two poles of the head and the gap between them are parallel to the medium, resulting in parallel orientation of the magnetic domains within the grains.

> [图 6-3](#09_9781119183938-ch06.xhtml#c06-fig-0003) 中所示的机制称为纵向记录。这意味着介质中的磁畴在与移动的磁性介质平行的方向上被磁化。纵向记录的关键是读/写头在移动介质上的位置。磁头的两极和它们之间的间隙平行于介质，导致晶粒内磁畴的平行取向。

Longitudinal recording techniques used in hard drives began to reach density limits in the late 1990s. The orientation of a magnetic domain can spontaneously flip due to thermal effects, with the result that magnetic recordings tend to degrade over time; this process is semi-affectionately known as  `bit rot` . The stability of a domain is strongly influenced by its size, and by the coercivity of the storage medium. As longitudinal recording grew denser, the typical lifetime of the magnetic domain orientation in the medium grew shorter until error rates made the technology unworkable.

> 20 世纪 90 年代末，硬盘驱动器中使用的纵向记录技术开始达到密度极限。磁畴的取向会由于热效应而自发翻转，结果是磁记录会随着时间的推移而退化；这个过程被半亲切地称为 `比特腐烂` 。畴的稳定性受到其大小和存储介质的矫顽力的强烈影响。随着纵向记录越来越密集，介质中磁畴取向的典型寿命也越来越短，直到错误率使该技术变得不可行。

---

> [!NOTE]

Not all magnetised materials are equally good at keeping their magnetism. The degree to which a magnetised material can resist demagnetisation is called its _coercivity_. Materials with high coercivity are difficult to demagnetise, and are used for permanent magnets. Materials with low coercivity can be magnetised and demagnetised with relative ease. Low-coercivity materials are used in magnetic storage media like magnetic tapes and disks, where bits are encoded as magnetic regions that may be changed as data is written and rewritten.

> 并非所有的磁性材料都能同样保持磁性。磁化材料能抵抗去磁化的程度称为其*磁性*。具有高矫顽力的材料很难退磁，用于永磁体。具有低矫顽力的材料可以相对容易地磁化和去磁化。低矫顽力材料用于磁带和磁盘等磁存储介质，其中位被编码为磁性区域，随着数据的写入和重写，磁性区域可能会发生变化。

The solution appeared in the mid-2000s when perpendicular recording was developed. Magnetising the grains in a direction perpendicular to the plane of the drive platter, as opposed to in the plane for longitudinal recording, delivered improved long-term stability. This in turn permitted a further increase in density. Two innovations made this possible:

> 解决方案出现在 2000 年代中期，当时开发了垂直记录。在垂直于驱动盘平面的方向上磁化颗粒，而不是在纵向记录平面上磁化，可提高长期稳定性。这反过来又允许密度进一步增加。两项创新使这成为可能：

- The write head was redesigned so that the magnetic lines of force were concentrated at one of the head’s magnetic poles and spread out at the opposite magnetic pole. The flux density at the narrow pole was concentrated enough to cause flux transitions, whereas the same flux at the wide pole was not. Only one pole was effective, and for that reason the head came to be called a monopole. The high field strength near the monopole allows the use of a magnetic medium with higher coercivity, which directly increased domain stability.

> -重新设计了写头，使磁力线集中在写头的一个磁极上，并分散在相反的磁极上。窄极处的通量密度集中到足以引起通量跃迁，而宽极处的相同通量则没有。只有一个磁极有效，因此头部被称为单极。单极附近的高场强允许使用具有更高矫顽力的磁性介质，这直接增加了畴稳定性。

- To draw the magnetic flux down from the write head in a vertical direction, a magnetic layer was deposited on the hard drive platter beneath the magnetic medium. The material in this layer was engineered to easily conduct magnetic flux without becoming magnetised. It pulls the flux down from the narrow pole and conducts it beneath the magnetic medium until the wide pole draws it back up into the head.

> -为了在垂直方向上从写头向下吸引磁通量，在磁介质下方的硬盘驱动器盘片上沉积了一层磁层。该层中的材料被设计为易于传导磁通量而不会被磁化。它将磁通量从窄极向下拉，并在磁介质下方传导，直到宽极将其拉回头部。

Figure 6-4 illustrates this scheme, which is called _perpendicular recording_. The mechanism is rarely used in tape storage because the mechanical instability of tape makes the desired densities difficult to attain. The huge density increases in hard drives in the last five years are almost entirely due to the change from longitudinal to perpendicular recording. Without it, today’s inexpensive multi-terabyte drives would be impossible.

> 图 6-4 说明了这个方案，称为 *perpendical recording*。这种机制很少用于磁带存储，因为磁带的机械不稳定性使得难以达到所需的密度。在过去五年中，硬盘密度的巨大增长几乎完全是由于从纵向记录到垂直记录的变化。如果没有它，今天廉价的多 TB 驱动器将是不可能的。

![[FIGURE 6-4:](#09_9781119183938-ch06.xhtml#rc06-fig-0004) Perpendicular recording](./media/images/9781119183938-fg0604.png)

## Magnetic Disk Storage

The first rotating magnetic disk storage was non-volatile but it was not mass storage; it was main memory, and the short-lived successor of the short-lived magnetic drum. (See [Chapter 3](#06_9781119183938-ch03.xhtml) for more on early magnetic disk and drum memory.) Magnetic disks were not used for mass storage until IBM’s Model 305 Random Access Memory Accounting Machine (RAMAC) was introduced in 1956. The key difference between early head-per-track rotating disk main memory and RAMAC’s disk storage was that RAMAC’s drive used multiple platters and moving read/write heads. The unit stored about 5MB on fifty 24-inch magnetic platters. Access time was between 600 and 750 milliseconds. The disk unit alone weighed about a metric tonne and had to be moved by forklift.

> 第一个旋转磁盘存储是非易失性的，但它不是大容量存储；它是主存储器，也是短命磁鼓的短命继任者。(请参阅[第 3 章](#06_9781119183938-ch03.xhtml)了解早期磁盘和磁鼓存储器的更多信息。)直到 1956 年 IBM 的 305 型随机存取存储器记帐机(RAMAC)问世，磁盘才被用于大容量存储。早期的每磁道磁头旋转磁盘主存储器和 RAMAC 的磁盘存储之间的关键区别在于，RAMAC 的驱动器使用多个盘片和移动读/写磁头。该单元在 50 个 24 英寸磁盘上存储了大约 5MB。访问时间在 600 到 750 毫秒之间。仅磁盘单元就重约一公吨，必须用叉车搬运。

The great challenge with early hard drive technology was that the platters were not sealed, and even with aggressive air filtering, smoke and dust particles got between the platters and the read/write heads and caused disk crashes. The amount of space between the heads and the platters had to be larger than the size of typical dust particles, which limited the density of storage on the platters. In 1973, the IBM 3340 Winchester drive subsystem introduced a sealed disk mechanism in which the read/write heads, positioner arms and servos, and the platters themselves, were a fully enclosed unit. This reduced head crashes and allowed other economies that assumed a clean operating environment. Heads could be moved closer to the platter surfaces, and used aerodynamic principles (flying heads) to maintain a specified distance from the platters with great precision.

> 早期硬盘技术面临的最大挑战是盘片没有密封，即使采用了积极的空气过滤，烟雾和灰尘颗粒也会进入盘片和读/写磁头之间，导致磁盘崩溃。头部和盘片之间的空间必须大于典型灰尘颗粒的大小，这限制了盘片上的存储密度。1973 年，IBM 3340 温彻斯特驱动器子系统引入了一种密封磁盘机制，其中读/写头、定位器臂和伺服机构以及盘片本身都是一个完全封闭的单元。这减少了头部碰撞，并允许其他经济体假设清洁的运营环境。头部可以移动得更靠近盘片表面，并使用空气动力学原理(飞行头部)以极高的精度保持与盘片的特定距离。

Hard drives were too expensive for use on desktop computers until Alan Shugart’s company Seagate Technology introduced the ST-506 5 ½` hard drive in 1980. It stored 5MB and was deliberately made to be the same physical size as full-height 5 ¼` floppy drives so it could fit in personal computer floppy drive bays. It originally cost £1,000. Mass production, and the entry of other firms into the market, caused prices to drop rapidly during the 1980s.

> 在 1980 年 Alan Shugart 的公司 Seagate Technology 推出 ST-506 5½` 硬盘之前，硬盘驱动器对于台式计算机来说太贵了。它存储了 5MB 的容量，并特意制作成与全高 5¼ 英寸软盘驱动器相同的物理尺寸，以便可以安装在个人电脑软盘驱动器托架中。最初售价为 1000 英镑。大规模生产和其他公司进入市场，导致价格在 20 世纪 80 年代迅速下降。

### Cylinders, Tracks and Sectors

From the time that hard drives came out of the labs, their lowest level of organisation was basically the same: platter surfaces are divided by magnetic markers into concentric tracks, and the tracks are further divided into a number of _sectors_, which are separated by equally spaced empty areas called _gaps_ (see Figure 6-5). The sector is the basic unit of storage. Until very recently, a hard drive sector held 512 data bytes. In today’s terabyte-capacity hard drives, using such small sectors wastes drive space. Since 2012, most new hard drive designs use a standard called Advanced Format, which increases sector size to 4,096 data bytes.

> 从硬盘从实验室出来时起，它们的最低组织水平基本相同：磁盘表面由磁性标记划分为同心轨道，轨道进一步划分为多个系数，这些系数由称为 *gaps* 的等间距空白区域分隔(见图 6-5)。扇区是存储的基本单位。直到最近，一个硬盘驱动器扇区存储 512 个数据字节。在当今 TB 容量的硬盘驱动器中，使用这样的小扇区会浪费驱动器空间。自 2012 年以来，大多数新的硬盘驱动器设计都使用一种称为 `高级格式` 的标准，将扇区大小增加到 4096 个数据字节。

![[FIGURE 6-5:](#09_9781119183938-ch06.xhtml#rc06-fig-0005) Disk tracks and sectors](./media/images/9781119183938-fg0605.png)

A sector contains more than data bytes alone. Sectors are divided into fields:

> 一个扇区仅包含的数据字节数就超过了。部门分为以下领域：

- **Sync field:** Marks the beginning of a sector and also acts as a timing marker that allows drive electronics to make sure that the read/write heads are synchronised to the platter. - **Address mark field:** Contains the sector’s number, its position on the disk and some status information. - **Data field:** Contains the sector’s actual data. As mentioned earlier, this is generally either 512 bytes or 4,096 bytes. - **Error Correction Code (ECC) field:** Contains about 50 bytes of parity information on a 512-byte sector for error detection and correction. (See [Chapter 3](#06_9781119183938-ch03.xhtml) for more about ECC technology.)

> -**同步字段：**标记扇区的开始，也用作定时标记，允许驱动电子设备确保读/写磁头与盘片同步。-**地址标记字段：**包含扇区的编号、其在磁盘上的位置和一些状态信息。-**数据字段：**包含扇区的实际数据。如前所述，通常为 512 字节或 4096 字节。-**纠错码(ECC)字段：**包含 512 字节扇区上大约 50 字节的奇偶校验信息，用于错误检测和纠正。(有关 ECC 技术的更多信息，请参见[第 3 章](#06_9781119183938-ch03.xhtml)。)

The Advanced Format consolidates eight 512-byte sectors into a single 4,096 sector, and saves about 10 percent of disk space by consolidating eight gaps, sync fields and address fields into one. The ECC field must be larger for error handling on longer sectors. However, the ECC field for an Advanced Format sector is only twice the length of the ECC field for a 512 byte sector, rather than eight times the length, so space gains can be made there as well.

> 高级格式将八个 512 字节扇区合并为一个 4096 扇区，通过将八个间隙、同步字段和地址字段合并为一，节省了大约 10% 的磁盘空间。对于较长扇区上的错误处理，ECC 字段必须更大。然而，高级格式扇区的 ECC 字段的长度仅为 512 字节扇区 ECC 字段长度的两倍，而不是长度的八倍，因此也可以获得空间增益。

The geometry of track and sector organisation leads to an interesting problem: the sectors towards the rim of drive platter in [Figure 6-5](#09_9781119183938-ch06.xhtml#c06-fig-0005) are physically larger than sectors closer to the hub, and yet store the same number of bytes. The innermost tracks are created to be as dense (in terms of bits per unit of linear distance) as the magnetic recording technology allows, which means that the outer tracks are not as dense as they could be. A technique called _zone bit recording_ divides a platter’s tracks into zones and places more sectors in zones closer to the rim. This keeps the number of bits per linear unit roughly constant from the hub to the rim and allows the disk to store considerably more data.

> 轨道和扇区组织的几何结构导致了一个有趣的问题：[图 6-5](#09*9781119183938-ch06.xhtml#c06-fig-0005) 中朝向驱动盘边缘的扇区在物理上大于靠近轮毂的扇区，但存储的字节数相同。最里面的磁道被创建为磁记录技术所允许的密度(以每单位线性距离的比特数表示)，这意味着外部磁道没有可能的密度。一种称为_zone bit recording*的技术将盘片的磁道划分为区域，并将更多扇区放置在更靠近边缘的区域中。这使每个线性单元从轮毂到边缘的位数大致保持恒定，并允许磁盘存储更多的数据。

From the beginning of the personal computer hard drive era, drives incorporated more than one platter, and used both sides of all platters in the drive. Each side of each platter has its own read and write heads. A single actuator arm moves all heads across all platters at once. At any given time, all heads access the same track on their respective platters. The set of all tracks that lie under the heads at any given time is called a _cylinder_. Early hard drive controllers specified the location of data on the drive in terms of cylinder number, head number (to indicate a particular side of one particular platter) and sector number. This system, called _cylinder-head-sector_ (CHS), worked well until drive capacity increased to the point where the number of heads, cylinders or sectors could not be expressed in the number of bits that a computer’s Basic Input/Output System (BIOS) allocated to them. As drive controller intelligence moved from external controllers to integrated (on-drive) controllers, a new system called _logical block addressing_ (LBA) was used to locate data within a drive. In a drive equipped with LBA (as all drives have been since 1996), sectors are identified as logical blocks, each with a single logical block number counted from 0. The on-drive controller translates between the LBA and whatever combination of cylinders, tracks and sectors that the drive contains. Neither the BIOS nor the operating system (OS) is explicitly aware of the internal arrangement of any given drive. However, logical blocks are in general numbered in the same physical order as they exist on the disk. Some OS disk access scheduling algorithms make use of this fact to ensure efficient use of the disk.

> 从个人电脑硬盘时代开始，硬盘包含了不止一个盘片，并在硬盘中使用了所有盘片的两侧。每个盘片的每一面都有自己的读写头。单个致动器臂一次将所有磁头移动到所有盘片上。在任何给定的时间，所有磁头都可以访问各自盘片上的相同磁道。在任何给定时间位于头部下方的所有轨迹的集合称为*柱面*。早期的硬盘驱动器控制器根据柱面号、磁头号(表示一个特定盘片的特定侧)和扇区号指定了数据在驱动器上的位置。这个名为 *cyllinder-head-sector*(CHS)的系统工作得很好，直到驱动器容量增加到无法用计算机的基本输入/输出系统(BIOS)分配给它们的位数来表示磁头、柱面或扇区的数量为止。随着驱动器控制器智能从外部控制器转移到集成(驱动器上)控制器，一种称为逻辑块寻址(LBA)的新系统被用于定位驱动器内的数据。在配备 LBA 的驱动器中(自 1996 年以来，所有驱动器都是如此)，扇区被标识为逻辑块，每个扇区都有一个从 0 开始计数的逻辑块编号。驱动器上的控制器在 LBA 和驱动器包含的柱面、磁道和扇区的任何组合之间转换。BIOS 和操作系统(OS)都不清楚任何给定驱动器的内部布置。但是，逻辑块通常按照磁盘上存在的物理顺序进行编号。一些操作系统磁盘访问调度算法利用这一事实来确保磁盘的有效使用。

### Low-Level Formatting

Before a hard drive can be used, magnetic markers defining tracks and sectors must be laid down on all its platter surfaces. This process is called _low-level formatting_. The broader term  `formatting`  really encompasses three things, all of which must be done before a drive can be put into service:

> 在使用硬盘驱动器之前，必须在其所有盘片表面上放置定义磁道和扇区的磁性标记。此过程称为 *low-level formatting*。更广泛的术语 `格式化` 实际上包含三件事，所有这些都必须在驱动器投入使用之前完成：

- **Low-level formatting:** Defines the actual physical tracks and sectors on disk platters. - **Partitioning:** Divides a drive into separate logical regions, each of which can operate independently of all the others, almost as though all partitions were separate hard drives. - **High-level formatting:** Sets up a mechanism for organising a drive’s sectors into folders and files. This is done according to the requirements of OS components called _file systems_.

> -**低级格式化：**定义磁盘盘片上的实际物理磁道和扇区。-**分区：**将一个驱动器划分为独立的逻辑区域，每个逻辑区域可以独立于其他所有区域运行，几乎就像所有分区都是独立的硬盘驱动器一样。-**高级格式化：**设置将驱动器扇区组织到文件夹和文件中的机制。这是根据名为 *file systems* 的操作系统组件的要求完成的。

---

> [!NOTE]

Read more about partitioning and high-level formatting later in this chapter in the  `[Partitions and File Systems](#09_9781119183938-ch06.xhtml#c06-sec-0014)`  section.

> 在本章稍后的 `[分区和文件系统](#09_9781119183938-ch06.xhtml#c06-sec-0014)` 部分中，了解有关分区和高级格式化的更多信息。

Until about the mid-1990s, low-level formatting was done after a hard drive was physically installed inside the end user’s computer. The formatting was accomplished either by a separate software utility or by routines in the machine’s BIOS. As the density of hard drive recording increased, the precision of the sync markers (also called _servo markers_, because they were used in a servo feedback system controlling head position) became difficult for the drive’s physical mechanisms to achieve. To achieve the precision that drive reliability required, manufacturers began performing low-level formatting on drive platters before they were installed in the drive. This is handled with a machine called a _servo writer_, which is capable of higher precision than the drive’s inexpensive arm and head positioning system.

> 直到大约 20 世纪 90 年代中期，在最终用户的计算机中物理安装了硬盘后，才进行了低级格式化。格式化由单独的软件实用程序或机器 BIOS 中的例程完成。随着硬盘记录密度的增加，同步标记(也称为 *servo 标记，因为它们用于控制磁头位置的伺服反馈系统)的精度对于硬盘的物理机制来说变得难以实现。为了达到驱动器可靠性所需的精度，制造商在将驱动器盘片安装到驱动器之前，就开始对其进行低级别格式化。这是用一台名为_servo writer* 的机器来处理的，它比驱动器廉价的手臂和头部定位系统具有更高的精度。

In current drives, low-level formatting cannot be completed after the drive is assembled. Manufacturers have recognised a need for repurposing drives and have provided users with utilities to perform drive reinitialisation. The utilities do two major things:

> 在当前的驱动器中，在组装驱动器后无法完成低级格式化。制造商已经认识到需要重新调整驱动器的用途，并为用户提供了执行驱动器重新初始化的实用程序。公用事业主要做两件事：

- The drive’s platter surfaces are scanned for sectors that cannot be read from or written to. Such bad sectors are marked so that they will not be used after reinitialisation. - All data stored on the drive is overwritten with some binary pattern, which may be one or more bytes in length. This removes user data, as well as partitions and file systems, and basically returns the drive to the empty state it had when it was first installed.

> -驱动器的盘片表面会扫描无法读取或写入的扇区。这些坏扇区会被标记，以便在重新初始化后不会被使用。-存储在驱动器上的所有数据都会被某种二进制模式覆盖，其长度可能为一个或多个字节。这将删除用户数据、分区和文件系统，并基本上将驱动器恢复到首次安装时的空状态。

There is some question as to whether data can be recovered from a drive after reinitialisation. If the utility really does write a pattern over every byte in every sector (and especially if it does this more than once) it becomes extremely difficult to recover data. To save time, some reinitialisation utilities eliminate partitions and file systems but do not try to overwrite every sector. In many cases there is a separate utility or menu option called secure erase that must be executed separately and might take many hours to wipe a drive with a capacity beyond one terabyte.

> 在重新初始化后，是否可以从驱动器恢复数据存在一些问题。如果实用程序真的在每个扇区的每个字节上写一个模式(尤其是如果它不止一次这样做)，那么恢复数据就变得非常困难。为了节省时间，一些重新初始化实用程序消除了分区和文件系统，但不尝试覆盖每个扇区。在许多情况下，有一个单独的实用程序或菜单选项称为安全擦除，必须单独执行，擦除容量超过 1TB 的驱动器可能需要几个小时。

Because magnetic recording basically uses analog magnetic marks to encode digital data, it may be possible to dismantle a drive and examine the platters using special equipment that detects traces of older recording around the edges of new recording. Such traces are called _data remanence_. The limited precision of the drive’s head-positioning mechanism makes this possible. In applications where data simply cannot be allowed to remain on a drive, such as in the military, the drive itself is physically destroyed, generally by dismantling the drive and grinding the coating off the platters or shattering platters made of glass. Ordinary users can achieve levels of security suitable for home use by hitting a drive several times with a 10-kilo sledgehammer.

> 由于磁记录基本上使用模拟磁标记对数字数据进行编码，因此可以拆卸驱动器并使用特殊设备检查盘片，该设备可以检测新记录边缘周围的旧记录痕迹。这样的记录道称为*数据剩余*。驱动器头部定位机构的有限精度使这成为可能。在数据根本无法保留在驱动器上的应用中，例如在军事中，驱动器本身会被物理破坏，通常是通过拆卸驱动器并研磨盘片上的涂层或粉碎玻璃制成的盘片。普通用户可以用 10 公斤的大锤敲击驱动器几次，从而达到适合家庭使用的安全级别。

### Interfaces and Controllers

Alan Shugart’s seminal ST-506 drive was  `dumb` ; its electronics could only move the heads to a requested position and impose or recover data bits using the heads. The intelligence was all in its external controller board, which was installed on the computer’s expansion bus and connected to the drive with three separate cables: drive control, drive data and power. The controller accepted requests from the OS for a particular sector, and translated those requests into head motion commands that the drive could execute directly. This ST-506 interface and its higher-performance successor, ST-412, dominated small computer systems until the late 1980s.

> 艾伦·舒加特(Alan Shugart)开创性的 ST-506 驾驶 `愚蠢` ；其电子设备只能将磁头移动到所请求的位置，并使用磁头施加或恢复数据位。智能都在其外部控制器板中，该板安装在计算机的扩展总线上，并通过三根独立的电缆连接到驱动器：驱动器控制、驱动器数据和电源。控制器接受 OS 对特定扇区的请求，并将这些请求转换为驱动器可以直接执行的头部运动命令。这种 ST-506 接口及其更高性能的后继产品 ST-412 一直主导着小型计算机系统，直到 20 世纪 80 年代末。

The evolution of hard drive storage involved more than packing ever-denser data storage onto the platters. A good bit of it lay in migrating disk control from the external controller board into the disk drive itself. In the 1980s, the Small Computer Systems Interface (SCSI) provided a high-speed interface to arbitrary storage devices, which could include tape, disk, optical disk or almost anything else that stored data. SCSI moved some intelligence to the storage device, largely with the goal of masking the details of the physical storage technology from the computer. SCSI devices were more expensive than ST-412 devices, and when the lower-cost Integrated Drive Electronics (IDE) disk drives appeared in 1986, they quickly became the standard in low-cost personal computing. The IDE interface moved nearly all controller intelligence into the drive’s on-board electronics, and the external interface board was just that: a way to bridge a computer’s expansion bus to the drive’s integrated controller. When the IDE interface was standardised by ANSI in 1994, it became known as the AT Attachment (ATA) interface, and later as PATA (for Parallel ATA) to distinguish it from the Serial ATA (SATA) interface, which was introduced in 2003. The ATA interface uses a single cable, which carries 16 data lines and all necessary control lines.

> 硬盘存储的发展不仅仅是将越来越密集的数据存储打包到磁盘上。其中很好的一点在于将磁盘控制从外部控制器板迁移到磁盘驱动器本身。20 世纪 80 年代，小型计算机系统接口(SCSI)为任意存储设备提供了高速接口，这些设备可以包括磁带、磁盘、光盘或几乎任何其他存储数据的设备。SCSI 将一些智能转移到存储设备上，主要目的是从计算机中隐藏物理存储技术的细节。SCSI 设备比 ST-412 设备更昂贵，当 1986 年出现成本更低的集成驱动器电子(IDE)磁盘驱动器时，它们很快成为低成本个人计算的标准。IDE 接口将几乎所有的控制器智能移动到驱动器的板载电子设备中，而外部接口板就是这样：一种将计算机扩展总线连接到驱动器集成控制器的方法。当 IDE 接口在 1994 年被 ANSI 标准化时，它被称为 AT 附件(ATA)接口，后来被称为 PATA(并行 ATA)，以区别于 2003 年引入的串行 ATA(SATA)接口。ATA 接口使用一根电缆，它承载 16 条数据线和所有必要的控制线。

As described earlier, LBA hides the details of internal drive organisation from the computer and its OS. However, the size of the LBA block numbers was limited by the number of bits allocated to them. The earliest IDE block numbers were 22 bits in size, which (with industry standard 512-byte sectors as blocks) could specify only 2GB of storage. The ATA standard increased the block numbers to 28 bits, which allowed 137GB of storage. It was not until the arrival of the ATA version 6 specification in 2001 that block numbers were allocated 48 bits, allowing 144 petabytes of storage. (A petabyte is 1,000 terabytes.)

> 如前所述，LBA 对计算机及其操作系统隐藏了内部驱动器组织的详细信息。然而，LBA 块号的大小受到分配给它们的位数的限制。最早的 IDE 块号大小为 22 位，(使用行业标准的 512 字节扇区作为块)只能指定 2GB 的存储空间。ATA 标准将块数增加到 28 位，从而允许 137GB 的存储空间。直到 2001 年 ATA 版本 6 规范发布，数据块编号才被分配为 48 位，允许 144 PB 的存储容量。(PB 是 1000 TB。)

By the end of the 1990s, ATA throughput was beginning to push the physical limits of the connection between computer and drive. In 2003, a new drive interface standard was published: Serial ATA (SATA). Most of the innovation lay in the physical interface between computer and drive. In SATA, data passes serially over two sets of two shielded conductors, rather than in parallel across 16 unshielded cable conductors, as in PATA.

> 到 20 世纪 90 年代末，ATA 吞吐量开始突破计算机和驱动器之间连接的物理限制。2003 年，发布了一个新的驱动器接口标准：串行 ATA(SATA)。大部分创新在于计算机和驱动器之间的物理接口。在 SATA 中，数据通过两组双屏蔽导线串行传输，而不是像 PATA 那样通过 16 个非屏蔽电缆导线并行传输。

The most significant difference between PATA and SATA lies all the way at the bottom, in the electrical interface between the controller and the host. PATA uses _single-ended signalling_, which means that each data path travels over a single wire, encoded as a varying voltage referenced against a common ground. Each of PATA’s 16 data lines has its own wire on the interconnect cable, as do the various control signals. Single-ended signalling has been used widely in low-speed parallel and serial connections since the days of telegraphy. The RS232 interface uses single-ended signalling, as does VGA video, PS/2 mouse and keyboard connections, and so on.

> PATA 和 SATA 之间最显著的区别在于控制器和主机之间的电气接口。PATA 使用单端信号，这意味着每条数据路径都在一根导线上传输，编码为参考公共接地的变化电压。PATA 的 16 条数据线中的每一条都在互连电缆上有自己的导线，以及各种控制信号。自电报时代以来，单端信令已广泛用于低速并行和串行连接。RS232 接口使用单端信令，VGA 视频、PS/2 鼠标和键盘连接等也是如此。

The problem with single-ended signalling is that crosstalk from other signal lines or external electrical interference can corrupt data passing over the link. A technique called _differential signalling_ was developed to address the interference issue. In differential signalling, each data path requires two wires, and a signal is encoded as the difference between the voltage levels on the two wires. Because the two wires are physically adjacent, and often twisted together, interference tends to affect both at once, changing their voltage levels relative to ground but preserving the difference. A circuit called a _differential amplifier_ at the receiver detects the difference in voltage between the two signal wires and outputs a clean signal irrespective of random voltage changes common to both wires. Differential signalling allows the use of lower voltage swings, and higher clock speeds, than single-ended signalling, while still providing adequate noise immunity.

> 单端信令的问题是来自其他信号线的串扰或外部电干扰会破坏通过链路的数据。为了解决干扰问题，开发了一种称为差分信号的技术。在差分信令中，每条数据路径需要两根导线，信号被编码为两根导线上的电压电平之差。由于这两条电线在物理上相邻，并且经常扭绞在一起，因此干扰往往会同时影响这两条线，从而改变它们相对于地的电压电平，但保留了电压差。接收器处的一个称为差分放大器的电路检测两条信号线之间的电压差，并输出一个干净的信号，而不考虑两条线共同的随机电压变化。差分信号允许使用比单端信号更低的电压波动和更高的时钟速度，同时仍然提供足够的抗噪声能力。

PATA uses a 3.3V or 5V swing, and a typical clock speed of 33MHz for a throughput of 133 megabytes per second (MB/s). SATA incorporates differential signalling with a nominal swing of only 250mV and an effective clock rate (for SATA 3.0) of up to 3GHz for a throughput of around 600MB/s.

> PATA 使用 3.3V 或 5V 摆动，典型的时钟速度为 33MHz，吞吐量为每秒 133 兆字节(MB/s)。SATA 采用差分信号，标称摆幅仅为 250mV，有效时钟速率(对于 SATA 3.0)高达 3GHz，吞吐量约为 600MB/s。

SATA offers a degree of backward compatibility with PATA drives by using the ATA command set, albeit over a radically different electrical interface. SATA also introduced _hot swapping_, which is the ability to disconnect and replace a drive without powering-down or rebooting the computer. This can be done without fear of damaging the drive; however, the OS must be capable of ensuring that the drive can be removed without corrupting its buffers and configuration data, as well as detecting a new drive inserted in the place of the old.

> SATA 通过使用 ATA 命令集提供了与 PATA 驱动器的一定程度的向后兼容性，尽管通过完全不同的电气接口。SATA 还引入了热插拔，这是一种无需关闭或重新启动计算机即可断开和更换驱动器的能力。这样做无需担心损坏驱动器；然而，操作系统必须能够确保驱动器可以在不损坏其缓冲区和配置数据的情况下被移除，以及检测到新驱动器插入旧驱动器的位置。

The Raspberry Pi uses a Secure Digital (SD) format flash card for its primary non-volatile storage, and does not include a drive interface for SATA. Disk drives may be connected to the Raspberry Pi using one of the board’s USB ports, which are described in detail in [Chapter 12](#15_9781119183938-ch12.xhtml). You can read about flash storage technology and SD cards later in this chapter.

> 复盆子 Pi 使用安全数字(SD)格式闪存卡作为其主要非易失性存储，不包括 SATA 驱动器接口。磁盘驱动器可以使用板上的一个 USB 端口连接到 Raspberry Pi，详见[第 12 章](#15_9781119183938-ch12.xhtml)。您可以在本章后面阅读闪存技术和 SD 卡。

### Floppy Disk Drives

Rotating disk drives with removable media far predate microcomputers. IBM, again, spearheaded the technology, introducing the first removable hard disk pack for the Model 1401 mainframe in 1962. The seminal 1973 Xerox Alto workstation foreshadowed the use of removable magnetic disk storage on desktop personal computers by incorporating a 2.5MB single-platter disk cartridge in every unit. IBM developed an 8 `(200 millimetre) read-only removable drive unit with flexible media in 1971, originally to store microcode that had to be loaded each time certain System/370 mainframe models were powered up. This flexible ` memory disk `  remained a mainframe technology until 1972, when Alan Shugart left IBM for Memorex, which created the first inexpensive read/write flexible-medium drive—the Memorex 650. Shugart later formed Shugart Associates to create a small business computer, an effort hampered by the sheer size of the Memorex-style 8` drives to be manufactured for it. Shugart developed the far less bulky 5 ¼`version of the technology to serve the emerging microcomputer market, and while the business computer never left its labs, the firm quickly became the leader in flexible-medium magnetic storage. The term ` floppy `was coined in the trade press in about 1970, and was used because the magnetic medium was a coating on thin circular Mylar sheet rather than a rigid platter. The Mylar sheet was informally called a` cookie` . The formal term for the cookie mounted inside a protective sleeve was _diskette_.

> 带有可移动介质的旋转磁盘驱动器远远早于微型计算机。IBM 再次引领了这项技术，于 1962 年为 1401 型主机推出了第一个可移动硬盘包。1973 年的 Xerox Alto 工作站开创性地预示了台式个人计算机上可移动磁盘存储的使用，它在每个单元中安装了一个 2.5MB 的单盘盒式磁盘。1971 年，IBM 开发了一种带有柔性介质的 8 英寸(200 毫米)只读可移动驱动器单元，最初用于存储每当某些 System/370 大型机型号通电时必须加载的微码直到 1972 年，Alan Shugart 离开 IBM 进入 Memorex，该公司创造了第一个廉价的读/写柔性介质驱动器 Memorex 650。Shugart 后来成立了 Shugart Associates，创建了一台小型商用计算机，这一努力受到为其制造的 Memorex 型 8 `驱动器的巨大尺寸的阻碍。Shugart 开发了体积小得多的 5¼` 版本的技术，以服务于新兴的微型计算机市场，尽管商用计算机从未离开过实验室，该公司很快成为柔性介质磁存储领域的领导者。`软盘` 一词在 1970 年左右由商业出版社创造，之所以使用，是因为磁性介质是薄圆形聚酯薄膜片上的涂层，而不是刚性盘片。聚酯薄膜被非正式地称为 `饼干` 。装在保护套内的饼干的正式名称是 *diskette*。

Early floppy-disk technologies had an interesting way of marking the positions of storage sectors on the flexible medium: equally spaced holes were punched in the cookie near the hub, and each of these sector holes marked the beginning of a new sector. One additional hole was punched in the cookie halfway between two of the sector holes. This was the track index hole, which told the floppy drive the angular position at which the first sector in each track began. A scheme depending on holes for sector positioning was called _hard sectoring_ because track and sector positions were dictated by physical holes and could not be changed. Later generations of floppy technology were _soft sectored_, meaning that the sector positions were defined by magnetic markers written to the cookie by the drive heads, as with hard drives. Soft sectoring allowed the density of the diskette to be changed (and thus its capacity) without physical changes to the medium.

> 早期的软盘技术有一种有趣的方式来标记柔性介质上存储扇区的位置：在中心附近的饼干上打出等间距的孔，每个扇区孔都标志着一个新扇区的开始。在两个扇形孔中间的饼干上又打了一个孔。这是磁道索引孔，它告诉软盘驱动器每个磁道中第一个扇区开始的角度位置。一种依靠孔进行扇区定位的方案被称为 `硬扇区` ，因为轨道和扇区位置由物理孔决定，不能改变。后来的几代软盘技术是软扇区技术，这意味着扇区位置是由磁头写入 cookie 的磁性标记来定义的，就像硬盘一样。软分区允许磁盘的密度改变(从而改变其容量)，而无需对介质进行物理改变。

Several higher-capacity variations on the floppy disk concept saw broad use from the late 1980s to the early 2000s, including the Iomega Bernoulli Box (10MB) and zip drives (100 and 250MB) and the Compaq SuperDisk drives (120 and 240MB), which would also read conventional 1.44 MB 3 ½`diskettes. Inexpensive CD-ROM drives made the floppy disk less necessary during the late 1990s, and once CD-ROM drives became read/write instead of read-only, the floppy diskette was on its way out. It is no coincidence that floppy disk drives pretty much vanished from consumer-class PCs entirely about the time that USB 2.0 flash-based thumb drives became reliable and inexpensive. The flash storage medium used in thumb drives is smaller, faster, and longer lived, as described in more detail in the ` [Flash Storage](#09_9781119183938-ch06.xhtml#c06-sec-0023)`  section later in this chapter.

> 从 20 世纪 80 年代末到 2000 年代初，软盘概念上的几个更高容量变体得到了广泛的应用，包括 Iomega Bernoulli Box(10MB)和 zip 驱动器(100 和 250MB)以及 Compaq SuperDisk 驱动器(120 和 240MB)，也可以读取传统的 1.44 MB 3½ `软盘。在 20 世纪 90 年代末，廉价的 CD-ROM 驱动器使软盘变得不那么必要，而一旦 CD-ROM 驱动器变成读/写而不是只读，软盘就要过时了。软盘驱动器在消费级 PC 上完全消失的时间与基于 USB 2.0 闪存的拇指驱动器变得可靠和廉价的时间并不巧合如本章后面的 ` [闪存](#09_9781119183938-ch06.xhtml#c06-sec-0023) ` 一节所述，拇指驱动器中使用的 rage 介质更小、更快、寿命更长。

## Partitions and File Systems

The process called _partitioning_ divides a physical drive unit into multiple logical units called partitions. Operating systems regard each partition as a separate logical device; a common application of partitioning is to support simultaneous installation of multiple operating systems on a single physical storage device, with each operating system’s root file system occupying a separate partition. Much of the technology and terminology around partitioning dates back to the dawn of the PC era, and was introduced in PC DOS 2.0 to support the first consumer-class hard drives for the IBM PC/XT.

> 名为 *partitioning* 的过程将物理驱动器单元划分为多个称为分区的逻辑单元。操作系统将每个分区视为单独的逻辑设备；分区的一个常见应用是支持在单个物理存储设备上同时安装多个操作系统，每个操作系统的根文件系统占用一个单独的分区。关于分区的许多技术和术语可以追溯到 PC 时代的早期，并在 PC DOS 2.0 中引入，以支持 IBM PC/XT 的第一个消费级硬盘。

At the lowest level, a partition is simply a range of contiguous sectors on a physical drive. How partitions are created and managed is heavily dependent on the overall architecture of the computer (for example, Wintel versus Mac versus Unix) as well as the OS doing the creating and managing. There can be large differences among versions of the same OS: Windows Vista and its successors handle partitioning in a way that is very different from (and incompatible with) Windows 9x, 2000 and XP. What we describe here is a high-level simplification of disk organisation that leaves out many of these details.

> 在最低级别，分区只是物理驱动器上的一系列连续扇区。分区的创建和管理方式在很大程度上取决于计算机的整体架构(例如，Wintel 与 Mac 与 Unix)以及创建和管理分区的操作系统。同一操作系统的版本之间可能存在很大的差异：Windows Vista 及其后续版本处理分区的方式与 Windows 9x、2000 和 XP 非常不同(并且不兼容)。我们在这里描述的是磁盘组织的高级简化，省略了许多这些细节。

### Primary Partitions and Extended Partitions

The first sector on a partitioned device contains the master boot record (MBR). The MBR contains a short piece of executable code known as a _bootloader_—which on IBM PC-compatible machines is responsible for loading the OS kernel into random access memory (RAM)—and a table of partition descriptors called the _partition table_. The default number of entries in the table is four. (Certain third-party partitioners/boot managers can increase this to as many as 16, at the cost of rendering the partitioning scheme as a whole incompatible with conventional MBRs.) Each of these four entries describes a _primary partition_ and contains the following information:

> 分区设备上的第一个扇区包含主引导记录(MBR)。MBR 包含一小段名为 *bootloader* 的可执行代码，在 IBM PC 兼容机器上，它负责将 OS 内核加载到随机存取存储器(RAM)中，以及一个名为 *partition table* 的分区描述符表。表中的默认条目数为 4。(某些第三方分区器/引导管理器可以将其增加到 16 个，代价是将分区方案作为一个整体与传统的 MBR 不兼容。)这四个条目中的每一个都描述了一个*主分区*，并包含以下信息：

- A status code indicating whether the partition is active (bootable.) This value is used to select the boot partition in the absence of a boot utility like the one built into Windows, or grub for Linux - The starting LBA sector number of the partition - The length of the partition, in sectors - The location of the first and last sectors of the partition expressed as Cylinder-Head-Sector (CHS) numbers - The partition ID code, which in most cases specifies which file system the partition was formatted for, and what special attributes the partition may have.

> -一个状态代码，指示分区是否处于活动状态(可启动)。该值用于在没有启动实用程序(如内置在 Windows 中的启动实用程序)的情况下选择启动分区，或用于 Linux 的 grub-分区的起始 LBA 扇区号-分区的长度，in sectors(扇区)—分区的第一个和最后一个扇区的位置，表示为气缸盖扇区(CHS)编号—分区 ID 代码，在大多数情况下，该代码指定分区的格式化文件系统，以及分区可能具有的特殊属性。

Figure 6-6 illustrates the MBR and partition table.

> 图 6-6 显示了 MBR 和分区表。

![[FIGURE 6-6:](#09_9781119183938-ch06.xhtml#rc06-fig-0006) The master boot record (MBR) and partition table](./media/images/9781119183938-fg0606.png)

The limit of four primary partitions is arbitrary and came about in the effort to provide both a minimal bootloader and partition definition data in a single 512-byte sector. Demand for greater flexibility in partitioning led to the development of the extended partition concept in the mid-1980s. An _extended partition_ is a primary partition modified to allow it to act as a sort of partition container. Only one of the four primary partitions may be used as an extended partition. Within the sectors allocated to an extended partition, multiple logical partitions may be allocated. Each logical partition has an extended boot record (EBR) that defines its size, type and start/end sector addresses. There is no master table of logical partition descriptors, and thus no arbitrary limit on the number of logical partitions that may be defined. Instead of a table, each individual EBR contains a sector address field that points to the next EBR within the extended partition. The EBRs are thus arranged in a structure called a _linked list_, with each entry in the list pointing to the next. The pointer field is zero-filled to indicate the last EBR in the list.

> 四个主分区的限制是任意的，这是为了在单个 512 字节扇区中同时提供最小的引导加载程序和分区定义数据。对分区更大灵活性的需求导致了 1980 年代中期扩展分区概念的发展。扩展分区(_extended partition_)是一个经过修改的主分区，允许它充当一种分区容器。四个主分区中只有一个可用作扩展分区。在分配给扩展分区的扇区内，可以分配多个逻辑分区。每个逻辑分区都有一个扩展引导记录(EBR)，用于定义其大小、类型和开始/结束扇区地址。没有逻辑分区描述符的主表，因此对可以定义的逻辑分区的数量没有任意限制。每个 EBR 都包含一个扇区地址字段，该字段指向扩展分区中的下一个 EBR，而不是表。因此，EBR 被安排在一个名为 *linked list* 的结构中，列表中的每个条目都指向下一个条目。指针字段为零填充，以指示列表中的最后一个 EBR。

### File Systems and High-Level Formatting

A logical partition on a hard drive is nothing more than a block of sectors offering undifferentiated storage space. Operating systems require components called _file systems_ to organise and manage a partition’s sectors in a useful way. Provided a logical partition follows the rules laid out in the file system specification, different operating systems with potentially different implementations of the file system software will be able to read and write to the partition interchangeably.

> 硬盘上的逻辑分区只不过是提供无差别存储空间的扇区块。操作系统需要名为 *file systems* 的组件以有用的方式组织和管理分区的扇区。如果逻辑分区遵循文件系统规范中规定的规则，则具有潜在不同文件系统软件实现的不同操作系统将能够互换地读取和写入分区。

Nearly all file systems organise mass storage volumes as _files_ (blocks of storage containing data) and _directories_, which are hierarchical structures acting as indexes for both files and child directories. (Directories are called _folders_ in some operating systems.) Internally, file systems are implemented as tables associating file and directory names with blocks of storage space to contain the file contents, and with file metadata. These blocks are contiguous groups of sectors called clusters or allocation units. How file system tables are structured and organised differs by file system, but at some level nearly all file systems consist of tables linked to other tables in data structures called _trees_. (For more on this, see [Chapter 8](#11_9781119183938-ch08.xhtml).)

> 几乎所有文件系统都将大容量存储卷组织为 *files*(包含数据的存储块)和 *directorys*，这是一种分层结构，用作文件和子目录的索引。(在某些操作系统中，目录被称为 *folders*。)在内部，文件系统被实现为将文件名和目录名与存储空间块(用于包含文件内容)以及文件元数据相关联的表。这些块是称为簇或分配单元的连续扇区组。文件系统表的结构和组织方式因文件系统而异，但在某种程度上，几乎所有的文件系统都由链接到数据结构中的其他表(称为 *trees*)的表组成。(有关详细信息，请参阅[第 8 章](#11_9781119183938-ch08.xhtml)。)

Disk partitions are generally created with a specific file system in mind, and the partitioning tool lays out the foundation of that file system during the partitioning process. This is why you’ll see partitions referred to specifically as New Technology File System (NTFS) partitions or ext4 partitions or any of the many different file systems available on desktop computers. ( `ext4`  is not an acronym and simply means the fourth generation of the Linux extended file system.) During the process of high-level formatting, an empty file system of the appropriate sort is written to the partition. High-level formatting is a fast process that generally replaces a populated directory tree with an empty root directory entry, within which new files and directories may be created. In most cases the underlying data, and large parts of the file system tables, are not overwritten, so utilities exist that can recover most or all of a file system after its volume has been high-level formatted.

> 磁盘分区通常是在考虑特定文件系统的情况下创建的，分区工具在分区过程中为该文件系统奠定了基础。这就是为什么您会看到专门称为新技术文件系统(NTFS)分区或 ext4 分区或桌面计算机上可用的许多不同文件系统的原因。( `ext4` 不是首字母缩略词，只是指第四代 Linux 扩展文件系统。)在高级格式化过程中，会将一个适当类型的空文件系统写入分区。高级格式化是一个快速的过程，它通常用空的根目录条目替换填充的目录树，可以在其中创建新的文件和目录。在大多数情况下，底层数据和文件系统表的大部分都不会被覆盖，因此存在一些实用程序，可以在卷被高级格式化后恢复大部分或全部文件系统。

High-level formatting may also include options to scan a volume for bad sectors, or for overwriting data with zeros or bit patterns for security reasons. Such operations make the high-level formatting process considerably more time-consuming.

> 高级格式化还可能包括扫描卷以查找坏扇区的选项，或出于安全原因用零或位模式覆盖数据的选项。这样的操作使得高级格式化过程更加耗时。

### The Future: GUID Partition Tables (GPTs)

The basic mechanism behind FAT has been with us since the DOS era in the early 1980s. It’s been enhanced and extended many times, but it still has a number of serious and probably unfixable problems. The three most serious issues are these:

> 自 20 世纪 80 年代早期 DOS 时代以来，FAT 背后的基本机制一直伴随着我们。它已经被增强和扩展了很多次，但它仍然存在一些严重的、可能无法解决的问题。三个最严重的问题是：

- The MBR exists at only one place on a disk, and if the sole copy of the MBR is damaged or overwritten, the contents of the entire disk may be lost. - MBR-based systems cannot handle drives with more than 2 terabytes capacity. With 3TB and 4TB drives now common and reasonably inexpensive, this significantly limits the storage that may be installed on one PC. - MBR is arbitrarily limited to four primary partitions. Getting past this limit requires creating an extended partition with logical partitions inside it, which is an awkward workaround for a problem that shouldn’t have existed to begin with.

> -MBR 仅存在于磁盘上的一个位置，如果 MBR 的唯一副本被损坏或覆盖，则整个磁盘的内容可能会丢失。-基于 MBR 的系统无法处理容量超过 2 TB 的驱动器。由于 3TB 和 4TB 驱动器现在普遍且价格合理，这大大限制了可以安装在一台 PC 上的存储空间—MBR 被任意限制为四个主分区。要超过这个限制，需要创建一个内部有逻辑分区的扩展分区，这对于一个本不应该存在的问题来说是一个尴尬的解决方法。

In the last few years, an entirely new drive organization technology has come on the scene: _GUID partition tables_ (GPTs.) GUID means _globally unique identifier_, and it means that literally: a GPT partition is assigned a 122-bit value generated at random that is almost guaranteed to be unique. There are 2<sup>122</sup> or 3.5 × 10<sup>36</sup> possible GUID values, so with good random number generators the likelihood of duplicate GUIDs is almost nil.

> 在过去几年中，一种全新的驱动器组织技术出现了：_GUID 分区表(GPT)。GUID 表示全局唯一标识符，字面意思是：GPT 分区被分配了一个随机生成的 122 位值，几乎保证是唯一的。有 2<sup>122</sup>或 3.5×10<sup>36</sup>可能的 GUID 值，因此使用好的随机数生成器，重复 GUID 的可能性几乎为零。

The number of partitions GPT supports is basically unlimited, and whatever limits exist are limits of the OS. Windows, for example, only supports 128 GPT partitions because it only allocates 128 partition entries. Also, limits on drive size are for all practical purposes gone. A drive may be up to 8 zebibytes, which is 9.4 × 10<sup>21</sup> bytes. Drives of this size will not be arriving any time soon.

> GPT 支持的分区数量基本上是无限的，无论存在什么限制，都是操作系统的限制。例如，Windows 只支持 128 个 GPT 分区，因为它只分配 128 个分区条目。此外，所有实际用途的驱动器大小限制都已取消。一个驱动器最多可以有 8 个字节，即 9.4×10<sup>21</sup>字节。这种大小的驱动器将不会很快到达。

GPT finesses the danger of damaging the MBR by creating multiple instances of its partition tables and other crucial data scattered across the drive, and if the primary instance is damaged, GPT can repair it using another instance elsewhere on the drive. GPT stores its data with CRC (cyclic redundancy check) values to assist in reconstructing any damaged data.

> GPT 通过创建其分区表的多个实例和分散在驱动器上的其他关键数据，巧妙地消除了损坏 MBR 的危险。如果主实例损坏，GPT 可以使用驱动器上其他位置的另一个实例来修复它。GPT 使用 CRC(循环冗余检查)值存储数据，以帮助重建任何损坏的数据。

Against the possibility that  `legacy`  tools assuming the presence of an MBR partition may overwrite essential GPT data, GPT provides a feature called a  `protective MBR` , which is an MBR describing the entire drive as a single partition. The protective MBR is not intended for ordinary use. Legacy tools that access the protective MBR may not work in all details, but at very least the tools will not assume a missing or corrupt MBR and write a new one that corrupts GPT data.

> 与假设存在 MBR 分区的 `遗留` 工具可能会覆盖基本 GPT 数据的可能性相反，GPT 提供了一种称为 `保护性 MBR` 的功能，即将整个驱动器描述为单个分区的 MBR。保护性 MBR 不适用于普通用途。访问保护性 MBR 的传统工具可能在所有细节上都不起作用，但至少这些工具不会假设 MBR 丢失或损坏，并编写一个损坏 GPT 数据的新 MBR。

Describing GPT operation in detail is beyond the scope of this book. For more on the topic, see [`https://en.wikipedia.org/wiki/GUID_Partition_Table`](https://en.wikipedia.org/wiki/GUID_Partition_Table).

> 详细描述 GPT 操作超出了本书的范围。有关该主题的更多信息，请参见[`https://en.wikipedia.org/wiki/GUID_Partition_Table`](https://en.wikipedia.org/wiki/GUID_Partition_Table).

### Partitions on the Raspberry Pi SD Card

While most of the preceding discussion of the history of partitioning has centred on rotating magnetic media, more modern solid-state storage technologies such as SD cards and USB flash drives have inherited the same approach to dividing a bulk physical medium into logical partitions composed of individually addressable sectors. An SD card containing the Raspbian OS is typically divided into two partitions. One, the _boot partition_, is only 60MB. It must be formatted specifically for a virtual file allocation table (FAT) file system (either FAT16 or FAT32) and contains only the code and data necessary to initialise the graphics processing unit (GPU), and bring the OS kernel into memory and run it. The other partition, usually called the _root partition_, contains the rest of the OS and all of your files, and at time of writing is formatted with the ext4 Linux file system. Raspbian does not use a separate swap partition, but instead swaps to a file located in the root file system. Swapping is to be avoided at (nearly) all costs on the Raspberry Pi, as discussed towards the end of [Chapter 3](#06_9781119183938-ch03.xhtml).

> 虽然前面关于分区历史的大部分讨论都集中在旋转磁介质上，但更现代的固态存储技术(如 SD 卡和 USB 闪存驱动器)继承了将大量物理介质划分为由单独可寻址扇区组成的逻辑分区的相同方法。包含 Raspbian OS 的 SD 卡通常分为两个分区。一个是_boot 分区，只有 60MB。它必须专门针对虚拟文件分配表(FAT)文件系统(FAT16 或 FAT32)进行格式化，并且只包含初始化图形处理单元(GPU)、将 OS 内核放入内存并运行所需的代码和数据。另一个分区通常称为_root 分区，包含 OS 的其余部分和所有文件，并且在写入时用 ext4 Linux 文件系统格式化。Raspbian 不使用单独的交换分区，而是交换到位于根文件系统中的文件。如[第 3 章](#06_9781119183938-ch03.xhtml)末尾所述，在树莓皮上(几乎)不惜一切代价避免交换。

The Raspberry Pi’s boot sequence is a little different from desktop and laptop systems. The BCM2835 boot ROM contains a small piece of code that runs on the VPU (video processing unit) a proprietary reduced instruction set computer (RISC) core that forms part of the GPU. The boot ROM loads a first-stage boot loader with the filename `bootcode.bin`</code> from the FAT boot partition, which in turn loads the main firmware file `start.elf`. Finally, `start.elf` reads an OS kernel from the file `kernel.img` (for armv6 CPUs) or `kernel7.img` (for armv7 and armv8 CPUs) into the start of memory and releases the ARM (Advanced RISC Machine) CPU from reset, which in turn loads the OS proper. Which kernel file the bootloader reads depends on which board you have: the first-generation Raspberry Pi boards have armv6 CPUs and require the `kernel.img` file. The Raspberry Pi 2 and after use `kernel7.img`.

> 树莓派的启动顺序与台式机和笔记本电脑系统略有不同。BCM2835 引导 ROM 包含一小段代码，该代码在 VPU(视频处理单元)上运行，VPU 是一个专有的精简指令集计算机(RISC)内核，构成 GPU 的一部分。引导 ROM 从 FAT 引导分区加载文件名为 `bootcode.bin` </code>的第一阶段引导加载程序，然后加载主固件文件 `start.elf` 。最后，`start.eelf` 从文件 `kernel.img` (对于 armv6 CPU)或 `kernel7.img` (对于 armv7 和 armv8 CPU)读取 OS 内核到内存的起始位置，这又加载 OS 本身。引导加载程序读取的内核文件取决于您拥有的板：第一代 Raspberry Pi 板具有 armv6 CPU，需要 `kernel.img` 文件。树莓派 2 和使用后的 `kernel7.img` 。

---

> [!NOTE]

The Raspberry Pi 3 incorporates a 64-bit armv8 Cortex A-53 CPU, but a separate 64-bit OS kernel does not exist at this writing. The Raspberry Pi 3 uses `kernel7.img` and runs in 32-bit mode. The Raspberry Pi foundation chose the Cortex A-53 because it runs very well in 32-bit mode, while having 64-bit features that may be exploited in the future.

> 复盆子 Pi 3 集成了 64 位 armv8 Cortex a-53 CPU，但在本文中不存在单独的 64 位 OS 内核。复盆子 Pi 3 使用 `kernel7.img` ，以 32 位模式运行。树莓派基金会选择 Cortex A-53，因为它在 32 位模式下运行非常好，同时具有 64 位功能，将来可能会被利用。

Since mid-2013, the Raspberry Pi Foundation has provided a utility to make installation of a bootable OS a great deal easier. The system is called the New Out-of-Box Software (NOOBS), and you may downloaded it without charge from the Foundation’s download page at [`www.raspberrypi.org/downloads`](http://www.raspberrypi.org/downloads).

> 自 2013 年年中以来，树莓派基金会提供了一个实用程序，使可启动操作系统的安装变得更加容易。该系统被称为新开箱即用软件(NOOBS)，您可以从基金会的下载页面[`www.raspberrypi.org/downloads`]免费下载([http://www.raspberrypi.org/downloads)](http://www.raspberrypi.org/downloads)).

A full install of NOOBS requires a minimum of 4GB of SD card space. When you boot the Raspberry Pi for the first time, NOOBS displays a menu of several operating systems and asks which ones you want to install. It then installs your chosen operating system, either from the network or from an image file on the SD card, and allows you to select which of the installed operating systems to boot. NOOBS remains available at boot time, allowing you to repair an existing install or install additional operating systems and edit their configuration files.

> 完整安装 NOOBS 至少需要 4GB 的 SD 卡空间。当你第一次启动树莓派时，NOOBS 会显示一个包含多个操作系统的菜单，并询问你要安装哪些操作系统。然后，它从网络或 SD 卡上的映像文件安装您选择的操作系统，并允许您选择要启动的已安装操作系统。NOOBS 在启动时仍然可用，允许您修复现有安装或安装其他操作系统并编辑其配置文件。

For more on Raspberry Pi operating systems and operating systems generally, see [Chapter 8](#11_9781119183938-ch08.xhtml).

> 有关 Raspberry Pi 操作系统和一般操作系统的更多信息，请参阅[第 8 章](#11_9781119183938-ch08.xhtml)。

## Optical Discs

Although optical mass-storage technology was first successfully demonstrated around 1960, the goal was video recording rather than data recording. High-end consumer video players using the 30cm analog LaserDisc format appeared in 1978, and while there were some adaptations for computer data storage, none were successful due to high costs and the sheer bulk of the individual discs, which weighed almost 400 grams. It wasn’t until the fully digital audio CD format appeared in the early 1980s that inexpensive digital optical storage became possible.

> 尽管光学大容量存储技术在 1960 年左右首次成功演示，但其目标是视频记录而非数据记录。1978 年出现了使用 30 厘米模拟激光光盘格式的高端消费型视频播放器，尽管对计算机数据存储进行了一些调整，但由于成本高昂和单个光盘的体积巨大，几乎重达 400 克，因此没有一个成功。直到 20 世纪 80 年代初出现了全数字音频 CD 格式，廉价的数字光盘存储才成为可能。

Most read-only optical disc technologies work like this: digital information is imposed as patterns of microscopic pits pressed into a disc of polycarbonate plastic along a spiral track, beginning at the hub of the disc and running towards the outer edge. After pressing, the polycarbonate disc is coated with an extremely thin layer of aluminium metal, and then enclosed in transparent acrylic. A beam from a laser diode follows the spiral track, and a photodiode interprets laser light reflected from the disc. The pits—and the flat regions that separate them, called _lands_—are of variable length. Pits have a depth equal to one quarter of the laser’s wavelength, such that light reflected from the bottom of a pit is 180° out of phase with light reflected from the surrounding surface, and destructively interferes with it, resulting in a dimmer reflection from pits than from lands. The spiral track reflects the origins of optical storage as a sound and video technology because those are purely serial in nature. (Further back, it echoes vinyl sound recordings, which encoded sound as analog  `waviness`  along a spiral track pressed into soft plastic.)

> 大多数只读光盘技术的工作原理都是这样的：数字信息是以微小凹坑的形式施加的，这些凹坑沿着螺旋轨道压入聚碳酸酯塑料盘中，从盘的中心开始，向外缘延伸。压制后，聚碳酸酯盘涂上一层极薄的铝金属，然后封装在透明丙烯酸树脂中。来自激光二极管的光束沿着螺旋轨道行进，光电二极管解释从光盘反射的激光。坑和分隔它们的平坦区域，称为 `陆地` ，其长度是可变的。凹坑的深度等于激光波长的四分之一，因此，从凹坑底部反射的光与从周围表面反射的光相差 180°，并对其进行破坏性干扰，导致凹坑反射比地面反射更暗。螺旋轨道反映了光存储作为声音和视频技术的起源，因为它们本质上是纯串行的。(再往前看，它与黑胶唱片相呼应，黑胶唱片将声音编码为模拟 `波纹` ，沿着压在软塑料中的螺旋轨道。)

As with hard disk storage, it turns out to be easier to detect transitions between pits and lands than it is to detect the features themselves. Rather than using pits to represent binary 0s and lands to represent binary 1s, the CD standard instead encodes a binary 1 as a change from pit to land or vice versa, and a binary 0 as a continuation of the current pit or land for a short distance. See Figure 6-7 for an example. A further layer of RLL coding, known as _eight-to-fourteen modulation_ (EFM) is applied to assist in timing recovery and to maintain a small overall digital sum (the number of binary 1s minus the number of binary 0s).

> 与硬盘存储一样，事实证明，检测凹坑和平台之间的过渡比检测特征本身更容易。CD 标准不使用凹坑表示二进制 0，而使用台面表示二进制 1，而是将二进制 1 编码为凹坑到台面的变化，反之亦然，将二进制 0 编码为当前凹坑或台面的短距离延续。示例见图 6-7。另一层 RLL 编码，称为 `八分之一到四分之一调制` (EFM)，用于帮助定时恢复并保持较小的总数字和(二进制 1 的数量减去二进制 0 的数量)。

---

> [!NOTE]

A _photodiode_ is a special semiconductor junction diode (a two-element semiconductor device) formulated so that the junction is sensitive to light. When a light photon strikes the junction, an electron/hole pair is created and swept out of an area of the diode to either side of the junction, called the _depletion region_. This causes a small current to flow, proportional to the intensity of the light striking the junction. Photodiodes are used to detect light and changes in light striking the photodiode.

> 光电二极管是一种特殊的半导体结二极管(一种双元件半导体器件)，其结构使结对光敏感。当一个光光子击中结时，一个电子/空穴对被产生，并从二极管的一个区域扫到结的任一侧，称为*耗尽区*。这会导致一个小电流流动，与照射到结点的光的强度成正比。光电二极管用于检测光和撞击光电二极管的光的变化。

![[FIGURE 6-7:](#09_9781119183938-ch06.xhtml#rc06-fig-0007) Optical disk operation](./media/images/9781119183938-fg0607.png)

The optical system in nearly all optical drives depends on a device called a _beam splitter_. This is a small prism of glass or plastic with a partially reflective layer imposed within it along a 45-degree angle. (They are typically made by gluing two prisms together along the 45-degree line.) The intense beam from the laser goes through the reflective layer in a straight line towards the disc. When the beam strikes the disc and is reflected back, part of the reflective light is turned aside by the beam splitter and strikes a photosensor, usually a photodiode. A sense amplifier connected to the photosensor detects the difference in intensity of the light reflected from pits compared to lands, and converts those differences into digital pulses. The pulses are  `cleaned up`  to remove noise, and then they are interpreted as 1s and 0s by the drive electronics.

> 几乎所有光驱中的光学系统都依赖于一种叫做分束器的设备。这是一个由玻璃或塑料制成的小棱镜，其中沿 45 度角施加了部分反射层。(它们通常是通过沿着 45 度线将两个棱镜粘在一起而制成的。)来自激光的强光束以直线穿过反射层，射向光盘。当光束撞击光盘并被反射回来时，部分反射光被分束器转向一边，并撞击光电传感器，通常是光电二极管。连接到光电传感器的感测放大器检测从凹坑反射的光与平台反射的光的强度差异，并将这些差异转换为数字脉冲。脉冲被 `清理` 以去除噪声，然后它们被驱动电子设备解释为 1 和 0。

The bane of optical discs (especially those designed to be handled a lot and not always with sufficient care) is scratching. The CD standard specifies an error correcting code (ECC) scheme based on Reed-Solomon codes, which adds a degree of redundancy to the stored bit stream. This means that multiple copies of data bits are stored in more than one physical area of the disc. The redundant data allows the decoder to reconstruct small amounts of data that had been obscured by scratches. Because scratches tend to destroy many adjacent bits of data at once, data from several nearby regions of the stream are interleaved on the disc, and de-interleaved during playback. This process spreads damage more thinly across a larger stretch of bit stream, reducing the likelihood that it will overwhelm the error-correcting capabilities of the Reed-Solomon code. Reed-Solomon itself involves heavy-duty maths that are beyond the scope of this book, but the Wikipedia entry may be helpful:

> 光盘(尤其是那些需要大量处理但并不总是足够小心的光盘)的危害是刮擦。CD 标准规定了基于 Reed-Solomon 码的纠错码(ECC)方案，该方案为存储的比特流增加了一定程度的冗余。这意味着数据位的多个副本存储在磁盘的多个物理区域中。冗余数据允许解码器重建少量被划痕遮挡的数据。由于划痕往往会同时破坏许多相邻的数据位，因此来自流的几个相邻区域的数据会在光盘上交错，并在播放过程中进行解交错。这一过程在更大范围的比特流上更稀疏地传播损害，从而降低了它将压倒里德-所罗门码纠错能力的可能性。Reed Solomon 本身涉及的是超出本书范围的繁重数学，但维基百科条目可能会有所帮助：

[`https://en.wikipedia.org/wiki/Reed%E2%80%93Solomon_error_correction`](https://en.wikipedia.org/wiki/Reed%E2%80%93Solomon_error_correction)

> [`https://en.wikipedia.org/wiki/Reed%E2%80%93Solomon_error_correction`](https://en.wikipedia.org/wiki/Reed%E2%80%93Solomon_error_correction)

### CD-Derived Formats

There are several different kinds of audio-CD-derived optical disc in use today, in the same 12cm format. All have a maximum capacity of roughly 700MB:

> 现在有几种不同种类的音频 CD 衍生光盘在使用，格式相同，为 12cm。它们的最大容量约为 700MB：

- **CD-ROM:** This is the format described earlier. The pits are pressed into the polycarbonate disc at manufacture and cannot be changed. - **CD-R:** This is a one-time recordable format (in other words, write once). A layer of photosensitive dye is deposited on the plastic disc over the reflective layer. When the disc is being written to, the laser emits strong pulses that permanently change the reflectivity of the dye in spots that are the same size as pits in a non-recordable CD-ROM. When the disc is being read, the laser emits a weaker beam that does not affect the dye layer’s properties. The spots on the dye layer are interpreted as pits. The undisturbed dye layer reflects light the same way as the lands do in a CD-ROM. - **CD-RW:** This format is rewriteable. The dye layer is replaced with a reflective layer of exotic metallic alloy containing indium, tellurium and silver. The alloy is designed to exhibit a phase change when heated by high-intensity laser light. A phase change is a rearrangement of the molecules in a material such that they have different physical properties, such as ice melting into water, or water boiling to produce steam. In this case, the phase change is from a reflective polycrystalline phase to a less-reflective amorphous (glassy) phase. Because the phase affects the reflectivity of the metal, it can be read in the same way as changes in the CD-R dye layer can be read. However, the phase change is not permanent, and can be reversed by using a less intense beam. (The discs are read with an even less intense beam that does not affect the phase of the alloy at all.) The disc may thus be written and rewritten by changing the beam power according to the patterns of 1s and 0s that must be imposed on the disc.

> -**CD-ROM：**这是前面描述的格式。凹坑在制造时被压入聚碳酸酯盘中，无法更换。-**CD-R:**这是一种一次性可记录格式(换句话说，只写一次)。感光染料层沉积在反射层上方的塑料盘上。当光盘被写入时，激光会发出强烈的脉冲，这些脉冲会永久性地改变染料的反射率，其大小与不可记录光盘中的凹坑大小相同。当读取光盘时，激光发出的光束较弱，不会影响染料层的特性。染料层上的斑点被解释为凹坑。未受干扰的染料层反射光的方式与 CD-ROM 中的土地反射光的方法相同。-**CD-RW:**此格式可重写。染料层被包含铟、碲和银的外来金属合金的反射层代替。该合金被设计成在被高强度激光加热时呈现相变。相变是材料中分子的重新排列，使它们具有不同的物理性质，如冰融化成水，或水沸腾产生蒸汽。在这种情况下，相变是从反射性多晶相到反射性较低的非晶(玻璃状)相。由于相位影响金属的反射率，因此可以以与读取 CD-R 染料层变化相同的方式读取。然而，相位变化不是永久的，可以通过使用强度较小的光束来逆转。(用强度更小的光束读取光盘，该光束完全不会影响合金的相。)因此，可以根据光盘上必须施加的 1 和 0 模式改变光束功率来写入和重写光盘。

The CD-ROM format is a strong standard and, theoretically, discs written to the CD-R or CD-RW format can be read on any CD-ROM compatible drive. In practice, there are sometimes compatibility issues, especially with older drives that were manufactured before the writeable/rewriteable standards were published.

> CD-ROM 格式是一种强大的标准，理论上，写入 CD-R 或 CD-RW 格式的光盘可以在任何 CD-ROM 兼容的驱动器上读取。实际上，有时会出现兼容性问题，尤其是在可写/可重写标准发布之前制造的旧驱动器。

### DVD-Derived Formats

After DVD video became a successful consumer format in about 1995, the format was adapted for computer use as non-volatile storage. In broad terms, the technology works the same way as the earlier CD formats: data is encoded as a pattern of pits or lands on a polycarbonate disc. The dimensions of the spiral track, pits and lands are much smaller than those used in the CD format, and the capacity of DVD-derived formats is much higher. At very minimum, DVD-derived formats can store 4.7GB. Newer formats can store much more. Making the pits and lands smaller is a function of the wavelength of the laser light used to read and write them. At the microscopic scale used to encode data on a disc, shorter wavelengths mean sharper images when the tracks are scanned and the laser light reflected from the pits and lands. Shorter wavelengths mean bluer light. Over the years, the light used in laser imaging has gone from infrared to red to blue. The trademark Blu-ray was coined to reflect the blue light required to encode video at higher resolutions.

> 大约在 1995 年，DVD 视频成为一种成功的消费格式后，该格式被改编为计算机使用的非易失性存储。从广义上讲，该技术的工作方式与早期的 CD 格式相同：数据被编码为聚碳酸酯光盘上的凹坑或凹坑图案。螺旋轨道、凹坑和平台的尺寸比 CD 格式中使用的尺寸小得多，DVD 衍生格式的容量也大得多。DVD 衍生格式至少可以存储 4.7GB。较新的格式可以存储更多。使凹坑和平台变小是用于读取和写入凹坑和平台的激光波长的函数。在用于对光盘上的数据进行编码的微观尺度上，当轨道被扫描并且激光从凹坑和平台反射时，更短的波长意味着更清晰的图像。波长越短意味着光越蓝。多年来，激光成像中使用的光已经从红外到红色到蓝色。蓝光的商标是为了反射蓝光，以更高的分辨率编码视频。

Laser colour aside, the biggest technical advance in DVD data storage over CD storage is the ability to create dual-layer discs, which existed in DVD video formats almost from the beginning. This is accomplished by coating the first layer of pits and lands with a transparent lacquer and then bonding on a second transparent plastic layer into which digital data has been pressed before assembly. The second data layer is coated with an extremely thin layer of gold. The gold layer is so thin that it’s semi-transparent, and laser light of sufficient intensity passes right through it and is reflected strongly enough from the inner layer to be readable.

> 撇开激光颜色不谈，DVD 数据存储比 CD 存储的最大技术进步是制作双层光盘的能力，这几乎从一开始就存在于 DVD 视频格式中。这是通过用透明漆涂覆第一层凹坑和焊盘，然后在组装前将数字数据压入的第二透明塑料层上粘合来实现的。第二数据层涂覆有极薄的金层。金层如此之薄，以至于它是半透明的，足够强度的激光正好穿过它，并且从内层反射得足够强烈，因此可读。

When a dual-layer DVD is detected, the DVD reader head changes its optical focus to read either the inner or the outer layer as desired. Whichever layer is not in focus  `blurs out`  and does not interfere with reading the layer that is in focus.

> 当检测到双层 DVD 时，DVD 读取器头会根据需要改变其光学焦点以读取内层或外层。无论哪个层不在焦点上，都会 `模糊` ，并且不会干扰读取焦点上的层。

Dual-layer data discs do not hold twice the amount of data as a single-layer disc. There is a certain amount of overhead required to make the dual-layer technology reliable, and so a dual-layer data disc loses about 10 percent of its capacity over two single-layer discs.

> 双层数据光盘的数据量不是单层光盘的两倍。要使双层技术可靠，需要一定的开销，因此，与两个单层磁盘相比，双层数据磁盘的容量损失了大约 10%。

Unlike CD-ROM, there are a number of incompatible refinements on the basic DVD-ROM format. A format war emerged between two competing writeable optical disc standards consortia in the early 2000s. The two groups presented their incompatible standards to the industry as DVD-R and DVD+R. (Both standards were later enhanced to be rewritable.) There are some technical advantages to DVD+R, particularly in terms of reliability and error correction, but today there is still no recognised winner of the war. As with CD-ROM, writeable and rewriteable DVD technology uses photochemical dye and metallic phase change layers to allow changes after manufacture.

> 与 CD-ROM 不同，DVD-ROM 基本格式有许多不兼容的改进。2000 年代初，两个竞争的可写光盘标准联盟之间爆发了一场格式大战。这两个小组向业界提出了不兼容的标准，即 DVD-R 和 DVD+R。(这两种标准后来都被增强为可重写。)DVD+R 有一些技术优势，特别是在可靠性和纠错方面，但今天仍然没有公认的战争赢家。与 CD-ROM 一样，可写和可重写 DVD 技术使用光化学染料和金属相变层，以允许制造后发生变化。

Unlike magnetic hard drives, optical discs are not generally partitioned into logical drives. Optical discs have their own, industry-standard file system specification called ISO 9660. The spec lays out how an optical disc is to be read, written and managed in detail. The goal is to allow the optical disc to be a universal interchange medium. If an operating system implements ISO 9660 fully, it is capable of reading from and (where appropriate) writing to any standard optical disc.

> 与磁硬盘驱动器不同，光盘通常不分区为逻辑驱动器。光盘有自己的行业标准文件系统规范，称为 ISO9660。该规范详细说明了如何读取、写入和管理光盘。目标是使光盘成为通用交换介质。如果操作系统完全实现 ISO 9660，则它能够读取和(在适当的情况下)写入任何标准光盘。

## Ramdisks

When the IBM PC was first released in 1981, IBM did something a little out of character: it published the full assembly language source code of the machine’s Basic Input/Output System (BIOS) in a technical manual. The BIOS in those days controlled just about every interaction between the CPU and peripherals like the keyboard, the text display, printers and disk drives. Having the source code allowed third-party vendors to quickly develop and release add-in products for the machine, which did a great deal to make it the _de facto_ standard in desktop computing within a few years of its release.

> 当 1981 年 IBM PC 首次发布时，IBM 做了一些有点与众不同的事情：它在技术手册中发布了机器基本输入/输出系统(BIOS)的完整汇编语言源代码。当年的 BIOS 几乎控制着 CPU 与键盘、文本显示器、打印机和磁盘驱动器等外围设备之间的每一次交互。有了源代码，第三方供应商可以快速开发和发布该机器的插件产品，这在发布后的几年内使其成为桌面计算的事实标准。

Not all the add-ins were hardware. By 1982, programmers had written software that allowed the PC to treat a region of system RAM as a PC DOS disk drive. This was called a _ramdisk_, or _RAM drive_. Early ramdisks did not provide a great deal of storage space—typically 64K, out of what might have been 256K or 512K of total memory—but their speed was startling, especially since the standard of performance for the IBM PC at that time was the 360K floppy disk drive. Ramdisks could be three orders of magnitude faster than a floppy drive, and 100 times faster than early 10MB hard drives, for which the  `breakthrough price`  in 1983 was $1,000.

> 并非所有的插件都是硬件。到 1982 年，程序员编写了软件，允许 PC 将系统 RAM 的一个区域视为 PC DOS 磁盘驱动器。这被称为 *ramdisk* 或_RAM 驱动器。早期的 ramdisk 没有提供大量的存储空间，通常是 64K，而总内存可能是 256K 或 512K，但它们的速度惊人，特别是因为当时 IBM PC 的性能标准是 360K 软盘驱动器。Ramdisk 可能比软盘快三个数量级，比早期的 10MB 硬盘快 100 倍，1983 年的 `突破价格` 为 1000 美元。

Device drivers did not exist for DOS PCs. A technology called _terminate and stay resident_ (TSR) software allowed ramdisks and many other devices to be accessed by way of standard ROM BIOS calls. A TSR loaded itself alongside DOS in memory, and then  `hooked`  one or more of the BIOS calls by writing its own address into DOS’s table of interrupt vectors at the bottom of memory. When DOS used BIOS to access a disk volume, the ramdisk TSR could choose to intercept the call and then use its own functions to manage the transfer of data to and from the ramdisk’s region of memory.

> DOS PC 上不存在设备驱动程序。一种名为 `终止并驻留` (TSR)软件的技术允许通过标准 ROM BIOS 调用来访问 RAM 磁盘和许多其他设备。TSR 将自己与 DOS 一起加载到内存中，然后通过将自己的地址写入内存底部的 DOS 中断向量表中来 `钩住` 一个或多个 BIOS 调用。当 DOS 使用 BIOS 访问磁盘卷时，ramdisk TSR 可以选择拦截调用，然后使用自己的功能来管理与 ramdisk 内存区域之间的数据传输。

Ramdisks were volatile, of course, and were not used for long-term data storage. They solved the problem of saving out intermediate files during complex builds of software under development. As explained in [Chapter 5](#08_9781119183938-ch05.xhtml), native-code compilers operate in several passes, and each pass can generate its own separate temporary files. This took significant time, especially when the only mass storage on the machine was one or two floppy disk drives. Configuring a compiler to write its temporary files to a ramdisk could cut the total build time by 75 percent or more.

> 当然，Ramdisk 是易失性的，不用于长期数据存储。他们解决了在开发中的软件的复杂构建过程中保存中间文件的问题。如[第 5 章](#08_9781119183938-ch05.xhtml)所述，本机代码编译器在多个过程中运行，每个过程都可以生成自己单独的临时文件。这需要很长时间，特别是当机器上唯一的大容量存储是一个或两个软盘驱动器时。配置编译器将其临时文件写入 ramdisk 可以将总构建时间减少 75% 或更多。

As the PC hardware standard matured and RAM grew cheaper, ramdisks were developed using add-in memory beyond the PC’s hard limit of 640K. In addition to temporary files, loadable sections of large applications called _overlays_ were often copied to ramdisk when the application was run. Instead of grinding the floppy drives every time a new feature set was selected, an overlay stored on a ramdisk was just  `there` .

> 随着 PC 硬件标准的成熟和 RAM 的价格越来越便宜，Ramdisk 的开发使用了超出 PC 640K 硬盘限制的附加内存。除了临时文件外，大型应用程序的可加载部分(称为 *overlays*)通常在应用程序运行时复制到 ramdisk。而不是每次选择一个新的功能集时都研磨软盘驱动器，存储在 ramdisk 上的覆盖层就在 `那里` 。

The death of floppy drives, along with the arrival of technologies like page caching and virtual memory, which blur the distinction between data held in computer memory and mass storage, greatly reduced the need for explicitly declared ramdisks by the mid-1990s. Ramdisks are still used, especially by live distributions of Unix-derived operating systems. In a live distribution, the OS boots into memory from a CD or DVD optical disc, without being installed on the underlying machine’s hard drives. Writeable files are typically stored in ramdisks. Some live distributions can optionally store configuration information on a local hard drive, if the user desires it. This makes a live installation’s configuration  `persistent`  from one run to another. Otherwise, everything associated with the live OS vanishes from memory when the computer is shut down.

> 软盘驱动器的消亡，以及页面缓存和虚拟内存等技术的出现，模糊了计算机内存和大容量存储之间的区别，到 1990 年代中期，对明确声明的 RAM 磁盘的需求大大减少。Ramdisk 仍在使用，特别是 Unix 衍生操作系统的实时发行版。在实时发行版中，操作系统从 CD 或 DVD 光盘引导到内存中，而无需安装在底层机器的硬盘上。可写文件通常存储在 ramdisk 中。如果用户需要，一些实时发行版可以选择将配置信息存储在本地硬盘上。这使得实时安装的配置从一次运行到另一次运行 `持久` 。否则，当计算机关闭时，与实时操作系统相关的所有内容都会从内存中消失。

In modern Linux systems, including Raspbian, there are two common ramdisk file systems: ramfs and tmpfs. The older ramfs file system does not allow the user to set a maximum amount of memory to be devoted to ramdisk storage: an application writing to a ramfs ramdisk can in theory exhaust the machine’s entire supply of physical memory. In contrast, tmpfs partitions can be limited to a set amount of memory and can utilise swap space under memory pressure (albeit at a performance cost). For this reason, tmpfs has largely replaced ramfs.

> 在包括 Raspbian 在内的现代 Linux 系统中，有两种常见的 ramdisk 文件系统：ramfs 和 tmpfs。较旧的 ramfs 文件系统不允许用户设置用于 ramdisk 存储的最大内存量：理论上，向 ramfs ramdisk 写入应用程序会耗尽机器的全部物理内存。相比之下，tmpfs 分区可以被限制在一个设定的内存量内，并且可以在内存压力下利用交换空间(尽管要付出性能代价)。因此，tmpfs 在很大程度上取代了 ramfs。

## Flash Storage

Perhaps the single most important advance in non-volatile storage in the last 30 years has been the development of reliable, low-cost flash memory. Flash was invented in the early 1980s by engineers at Toshiba, particularly Dr Fujio Masuoka. After the first detailed presentation of the technology in 1984, it took until 1988 for Intel to field the first commercial chips. In its early days, flash was used as a storage medium for configuration data and BIOS code and firmware in computers; it was also used in consumer electronics like set-top boxes and home broadband routers. Eventually flash became cheap enough to use in mass-storage devices. These fall into four general categories: flash cards (SD, MMC, memory stick, compact flash); USB thumb drives; embedded flash (eMMC, UFS); and flash-based solid-state drives (SSDs) that are designed to replace conventional hard drives.

> 在过去的 30 年中，非易失性存储器中最重要的进步可能是开发了可靠、低成本的闪存。Flash 是由东芝的工程师，特别是藤尾真冈博士在 20 世纪 80 年代初发明的。在 1984 年首次详细介绍该技术之后，直到 1988 年，英特尔才推出了第一批商用芯片。在早期，闪存被用作计算机中配置数据、BIOS 代码和固件的存储介质；它还用于机顶盒和家庭宽带路由器等消费电子产品。最终，闪存变得足够便宜，可以用于大容量存储设备。它们分为四大类：闪存卡(SD、MMC、记忆棒、紧凑型闪存)；USB 拇指驱动器；嵌入式闪存(eMMC、UFS)；以及设计用于替代传统硬盘驱动器的基于闪存的固态驱动器(SSD)。

Flash devices have broad structural similarities to dynamic random access memory (DRAM); the description of DRAM in [Chapter 3](#06_9781119183938-ch03.xhtml) will help you during the following discussion of flash technology.

> 闪存器件与动态随机存取存储器(DRAM)具有广泛的结构相似性；[第 3 章](#06_9781119183938-ch03.xhtml)中对 DRAM 的描述将在以下闪存技术的讨论中对您有所帮助。

### ROMs, PROMs and EPROMs

Flash is a species of non-volatile semiconductor memory, but it is not the first by any means. Mask-programmable _read-only memory_ (ROM) chips, which have data permanently recorded in them during manufacture, have existed since the beginning of the semiconductor memory era. Data in a mask-programmable ROM is encoded onto the chip by adjusting one or more photolithographic masks to selectively disconnect or modify the switching behaviour of the chip’s individual transistors, which are arranged in a cell matrix similar to that used on SRAM and DRAM chips (see [Chapter 3](#06_9781119183938-ch03.xhtml)). _Programmable ROM_ (PROM) chips allow data to be recorded once (and permanently) onto the chip after manufacture, generally by using a high-current pulse to melt or otherwise open fuses in the cell matrix.

> 闪存是一种非易失性半导体存储器，但无论如何它不是第一种。掩模可编程只读存储器(ROM)芯片自半导体存储器时代开始就已经存在，这些芯片在制造过程中会永久记录数据。通过调整一个或多个光刻掩模以选择性地断开或修改芯片的单个晶体管的开关行为，将掩模可编程 ROM 中的数据编码到芯片上，可编程 ROM_(PROM)芯片允许在制造后将数据一次性(永久)记录到芯片上，通常通过使用高电流脉冲熔化或以其他方式断开单元矩阵中的熔丝。

The direct ancestor of flash memory is _erasable PROM_ (EPROM), which was invented in 1972. Data stored in an EPROM device may be erased by exposure to ultraviolet (UV) light. Data is stored as charge levels in special floating-gate metal-oxide-semiconductor field-effect transistors (MOSFETs) at each node in the memory cell matrix. The entire EPROM may be erased at once by exposure to intense UV light through a small quartz window in the device package. (Quartz passes UV, whereas ordinary glass does not.) Energetic UV photons create ionisation in the silicon dioxide insulating layer that traps charge in the floating gate MOSFETs, allowing it to leak away to ground. If shielded from light, an EPROM retains its data for at least 20, and as many as 40, years, and it may be erased hundreds of times. Erasing via UV does cause cumulative damage in the insulating layer such that thousands of erase cycles renders a cell unusable, an effect that looms large in flash memory systems.

> 闪存的直接祖先是 1972 年发明的可擦除 PROM_(EPROM)。存储在 EPROM 设备中的数据可以通过暴露于紫外线(UV)来擦除。数据作为电荷电平存储在存储单元矩阵中每个节点处的特殊浮栅金属氧化物半导体场效应晶体管(MOSFET)中。整个 EPROM 可以通过器件封装中的一个小石英窗暴露在强烈的紫外线下，立即擦除。(石英能通过紫外线，而普通玻璃不能。)高能紫外线光子在二氧化硅绝缘层中产生电离，将电荷捕获在浮栅 MOSFET 中，使其泄漏到地面。如果遮光，EPROM 的数据至少可以保存 20 年，甚至 40 年，而且可能会被擦除数百次。通过 UV 擦除确实会在绝缘层中造成累积损伤，因此数千次擦除周期会导致单元不可用，这一影响在闪存系统中非常明显。

### Flash as EEPROM

Towards the end of the 1970s, various approaches were tried to make EPROM devices erasable without requiring many minutes under a UV light source to do so. As a category, these devices are called _electrically erasable PROM_ (EEPROM). As with EPROM, all EEPROM devices store data as levels of electrical charge on a floating MOSFET gate. Bits are erased by removing charge from the gate. Flash is technically an EEPROM technology, one that was designed at the outset to be both fast and scalable. Like most EEPROM technologies, it can be erased selectively; that is, portions of a device’s data may be retained while other portions are erased. Today, it is by far the most successful EEPROM technology ever developed.

> 在 20 世纪 70 年代末，人们尝试了各种方法使 EPROM 器件可擦除，而无需在紫外线光源下几分钟。作为一个类别，这些器件被称为电可擦除 PROM_(EEPROM)。与 EPROM 一样，所有 EEPROM 器件都将数据存储为浮动 MOSFET 栅极上的电荷水平。通过从栅极移除电荷来擦除位。从技术上讲，闪存是一种 EEPROM 技术，一开始就被设计为既快速又可扩展。与大多数 EEPROM 技术一样，它可以被选择性地擦除；也就是说，可以保留设备数据的部分而擦除其他部分。今天，它是迄今为止开发的最成功的 EEPROM 技术。

Like most forms of semiconductor memory, flash is based on individual memory cells in an addressable matrix. The fundamental flash cell is based on the floating-gate MOSFET. Figure 6-8 shows a cross-section of a flash cell and the floating-gate MOSFET symbol.

> 与大多数形式的半导体存储器一样，闪存基于可寻址矩阵中的单个存储单元。基本闪存单元基于浮栅 MOSFET。图 6-8 显示了闪存单元和浮栅 MOSFET 符号的横截面。

![[FIGURE 6-8:](#09_9781119183938-ch06.xhtml#rc06-fig-0008) A flash cell](./media/images/9781119183938-fg0608.png)

As mentioned in the digital logic primer in [Chapter 4](#07_9781119183938-ch04.xhtml), a MOSFET controls a flow of current by creating a temporary conductive channel between its source and drain terminals under the control of a voltage applied to the its gate terminal. The voltage at which the MOSFET begins to conduct is referred to as the _threshold voltage_, V<sub>th</sub>.

> 如[第 4 章](#07*9781119183938-ch04.xhtml)中的数字逻辑入门中所述，MOSFET 通过在施加到其栅极端子的电压的控制下在其源极端子和漏极端子之间创建临时导电沟道来控制电流的流动。MOSFET 开始导通的电压称为阈值电压*，V<sub>th</sub>。

In addition to the regular control gate, floating-gate transistors have a second gate electrode, located between the control gate and the channel, which is not connected to the rest of the electronics in the chip; instead, it is enclosed in a layer of insulating material like silicon dioxide. This floating gate may be given a charge by applying a high voltage to the control gate, while placing a voltage across the channel. The voltage across the channel accelerates electrons to the point where they have enough energy (that is, they are  `hot`  enough) to cross the silicon dioxide insulator separating the floating gate from the channel, imparting a charge to the gate; this process is referred to as _hot carrier injection_ (HCI). The presence or absence of charge on the floating gate affects the threshold voltage of the transistor; by setting the control gate to a voltage close to V<sub>th</sub> and measuring the current flowing in the channel it is possible to measure the charge on the floating gate to a high level of accuracy.

> 除了常规控制栅极之外，浮栅晶体管还具有第二栅电极，位于控制栅极和沟道之间，不与芯片中的其他电子器件连接；相反，它被封装在一层像二氧化硅一样的绝缘材料中。通过向控制栅极施加高电压，同时在沟道两端施加电压，可以给该浮置栅极充电。沟道两端的电压将电子加速到具有足够能量(即，它们足够 `热` )的点，以穿过将浮栅与沟道分隔开的二氧化硅绝缘体，向栅极施加电荷；该过程被称为热载流子注入(HCI)。浮置栅极上电荷的存在或不存在影响晶体管的阈值电压；通过将控制栅极设置为接近 V<sub>th</sub>的电压并测量在沟道中流动的电流，可以高精度地测量浮置栅极上的电荷。

Charge placed on the floating gate through HCI may be removed by applying a large negative voltage to the control gate. This creates a strong electric field that encourages Fowler-Nordheim tunnelling of  `cold`  electrons across the barrier between the channel and the floating gate. After a level of charge has been set on the floating gate, the insulating layer surrounding the gate will keep the charge in place on the gate for a remarkably long time. Some research indicates that this retention time could be as much as 100 years under ideal conditions.

> 通过向控制栅极施加大的负电压，可以去除通过 HCI 放置在浮置栅极上的电荷。这产生了一个强大的电场，鼓励 Fowler-Nordheim 隧穿 `冷` 电子穿过沟道和浮栅之间的势垒。在浮置栅极上设置了电荷水平之后，围绕栅极的绝缘层将在栅极上保持电荷相当长的时间。一些研究表明，在理想条件下，这种保留时间可能长达 100 年。

---

> [!NOTE]

When subjected to a sufficiently intense electric field, certain metals will emit low-energy ( `cold` ) electrons. This is called _field emission_. These electrons can tunnel through an insulating layer via quantum effects described by physicists Ralph Fowler and Lothar Nordheim in the late 1920s. This is one type of _quantum tunnelling_, and among the first to be described in detail.

> 当受到足够强的电场时，某些金属会发射低能( `冷` )电子。这称为 *field emission*。这些电子可以通过物理学家拉尔夫·福勒(Ralph Fowler)和洛塔尔·诺德海姆(Lothar Nordheim)在 20 世纪 20 年代末描述的量子效应隧穿绝缘层。这是量子隧穿的一种类型，也是最早被详细描述的类型之一。

Like EPROM and earlier generations of EEPROM cells, flash memory cells have a limitation that is not present in SRAM or DRAM memory cells: flash cells may be written to and/or erased only a certain number of times. HCI causes cumulative damage to the insulating barriers that isolate the floating gate. After a certain number of write/erase cycles, electrons become trapped in the barriers, and there is no effective way to remove them. These trapped electrons give the barriers an unwanted charge that interferes with the measurement of the charge level on the floating gate. At some point the measurable difference between charge and lack of charge (the _threshold window_) disappears, and the cell can no longer be accurately read. The number of times that a cell may be written to is a factor called _endurance_. The endurance of flash cells varies widely depending on the size of the cells, the number of bits stored per cell, and the materials from which the cells are manufactured. Currently, flash endurance ranges from about 1,000 to about 100,000 write/erase cycles.

> 与 EPROM 和早期的 EEPROM 单元一样，闪存单元具有 SRAM 或 DRAM 存储单元中不存在的限制：闪存单元只能写入和/或擦除一定次数。HCI 对隔离浮栅的绝缘栅造成累积损坏。在一定数量的写入/擦除周期之后，电子被困在势垒中，并且没有有效的方法去除它们。这些被捕获的电子给势垒一个不需要的电荷，它会干扰浮栅上电荷水平的测量。在某一点上，电荷和缺乏电荷之间的可测量差异(阈值窗口)消失了，并且不再能够准确读取单元。单元可以写入的次数是一个称为 *endurance* 的因素。闪存单元的耐久性取决于单元的大小、每个单元存储的位数以及制造单元的材料。目前，闪存耐久性的范围从大约 1000 到大约 100000 个写入/擦除周期。

### Single-Level vs. Multi-Level Storage

SRAM encodes data in flip-flops, which have only two possible logic states, and can therefore encode only a single bit. DRAM stores data as charge in microscopic capacitors attached to MOSFET transistors. (See [Chapter 3](#06_9781119183938-ch03.xhtml) for a detailed description of DRAM operation.) The charge leaks away quickly, so the actual voltage on the capacitor varies across the time between refresh cycles. The best that we can do is test to see whether a DRAM cell’s capacitor is charged or not charged. Again, those two states encode only one bit.

> SRAM 在触发器中编码数据，触发器只有两种可能的逻辑状态，因此只能编码单个位。DRAM 将数据作为电荷存储在连接到 MOSFET 晶体管的微型电容器中。(有关 DRAM 操作的详细说明，请参见[第 3 章](#06_9781119183938-ch03.xhtml)。)电荷很快泄漏，因此电容器上的实际电压在刷新周期之间的时间内变化。我们能做的最好的是测试 DRAM 单元的电容器是否充电。同样，这两种状态只编码一位。

Flash, like DRAM, stores data as charge in a cell. Unlike DRAM, flash can keep a charge in a cell almost unchanged for many years. We can not only detect whether the charge exists in the cell but also, by careful measurement of the effect of the floating gate on the transistor threshold voltage, measure that charge with considerable accuracy.

> 闪存和 DRAM 一样，将数据作为电荷存储在一个单元中。与 DRAM 不同，闪存可以使电池中的电荷在许多年内几乎保持不变。我们不仅可以检测电池中是否存在电荷，而且通过仔细测量浮栅对晶体管阈值电压的影响，可以相当准确地测量电荷。

Being able to measure the charge level in the floating gate allows something very useful: the ability to store multiple bits in a single flash cell. Figure 6-9 shows how this is done. A flash cell that stores only one bit is called a _single-level cell_ (SLC). In an SLC, there are only two possible voltage levels. This makes the cell a binary device, which can store either a 0-bit or a 1-bit. If you set up a flash device to store four different voltages in a cell, that cell can encode two bits. If you set up a flash device to store eight different voltages in a cell, the cell can encode three bits.

> 能够测量浮置栅极中的电荷水平允许一些非常有用的东西：在单个闪存单元中存储多个位的能力。图 6-9 显示了这是如何完成的。只存储一个位的闪存单元称为半字节级单元(SLC)。在 SLC 中，只有两种可能的电压电平。这使得单元成为二进制设备，可以存储 0 位或 1 位。如果您设置一个闪存设备来在一个单元中存储四个不同的电压，那么该单元可以编码两位。如果您设置一个闪存设备，在一个单元中存储八个不同的电压，那么该单元可以编码三位。

![[FIGURE 6-9:](#09_9781119183938-ch06.xhtml#rc06-fig-0009) Single-level and multi-level flash encoding](./media/images/9781119183938-fg0609.png)

Strictly speaking, any flash cell that stores more than one bit is called a _multi-level cell_ (MLC). At this writing, the most that commercial flash devices can store in a single cell is four bits.

> 严格地说，任何存储多于一位的闪存单元都称为*多级单元*(MLC)。在本文中，商用闪存设备在单个单元中最多可以存储四位。

There’s a downside to packing more bits into a single cell. In general, the maximum charge level that may be placed on a device’s floating gates is limited by other factors and cannot be arbitrarily increased. This means that the difference between charge levels in multi-level devices becomes smaller as the number of bits per cell increases (refer to [Figure 6-9](#09_9781119183938-ch06.xhtml#c06-fig-0009)). The smaller this difference in voltage is, the more difficult it is to measure, and the more likely it is that there will be both read and write errors. Multi-level cells are more vulnerable to stray charge trapped in the insulating barriers, because stray charge makes the gate charge more difficult to measure. This means that the endurance of MLCs is lower than that of SLCs.

> 将更多比特打包到单个单元中有一个缺点。通常，可以放置在器件的浮栅上的最大电荷水平受到其他因素的限制，并且不能任意增加。这意味着，随着每个单元位数的增加，多级器件中电荷电平之间的差异会变小(参见[图 6-9](#09_9781119183938-ch06.xhtml#c06-fig-0009))。电压差异越小，测量越困难，越有可能出现读写错误。多层电池更容易受到绝缘势垒中捕获的杂散电荷的影响，因为杂散电荷使栅极电荷更难测量。这意味着 MLC 的耐久性低于 SLC。

There are techniques to minimise the effects of cell failures, which we’ll return to in the  `[Wear Levelling and the Flash Translation Layer](#09_9781119183938-ch06.xhtml#c06-sec-0028)`  section.

> 有一些技术可以将单元故障的影响降到最低，我们将在 `[磨损水平化和闪存转换层](#09_9781119183938-ch06.xhtml#c06-sec-0028)` 部分返回。

### NOR vs. NAND Flash

In general, the individual cells in flash devices all work the same way. How the cells are arranged and interconnected on the silicon of a flash storage chip dictates to some extent how that chip is used. There are currently two very different architectures by which flash cells are combined into storage arrays:

> 通常，闪存设备中的各个单元都以相同的方式工作。这些单元在闪存芯片的硅上如何排列和互连，在一定程度上决定了该芯片的使用方式。目前有两种非常不同的架构，闪存单元通过这两种架构组合成存储阵列：

- **NOR (Not-OR) flash:** May be written and read down to the resolution of a single machine word, much as DRAM is. NOR is slower to write and erase than NAND flash and is less dense, but is faster to read. It can support in-place execution of code (that is, without first copying it to RAM) and is commonly used for storing firmware in embedded devices. - **NAND (Not-AND) flash:** Accessed in larger pages of 512 to 4,096 bytes. Pages are combined into blocks of typically 16KB or more. NAND flash is read and written in pages, but erased only in blocks. NAND is faster to write and erase than NOR flash; it’s also more dense but is slower to read. In-place execution of code is not generally possible due to the lack of support for rapid random access to the array.

> -**NOR(非或)闪存：**可以写入和读取到单个机器字的分辨率，就像 DRAM 一样。NOR 写入和擦除速度比 NAND 闪存慢，密度低，但读取速度更快。它可以支持代码的就地执行(即，无需先将其复制到 RAM)，通常用于在嵌入式设备中存储固件。-**NAND(非与)闪存：**以 512 到 4096 字节的较大页面访问。页面被组合成通常 16KB 或更大的块。NAND 闪存以页为单位进行读写，但仅以块为单位进行擦除。NAND 写入和擦除速度比 NOR 闪存快；它的密度也更高，但阅读速度较慢。由于缺乏对阵列快速随机访问的支持，代码的就地执行通常是不可能的。

A NOR flash array is shown in Figure 6-10.

> NOR 闪存阵列如图 6-10 所示。

> [!NOTE]
> the resemblance to DRAM, as shown in [Figure 3-4](#06_9781119183938-ch03.xhtml#c03-fig-0004) from [Chapter 3](#06_9781119183938-ch03.xhtml). A single cell is present at the intersection of each bit line and row line. The term NOR is borrowed from digital logic and the basic operation of NOR gates: a single input to a NOR word line produces an inverted (opposite logic level) output on a bit line.

![[FIGURE 6-10:](#09_9781119183938-ch06.xhtml#rc06-fig-0010) A NOR flash array](./media/images/9781119183938-fg0610.png)

NAND flash was designed to act as mass storage rather than non-volatile RAM. To be cost-effective there must be a great many cells in a storage array. In a NAND array, cells are not addressed singly but in groups of 32 or 64 cells connected in series, as shown in Figure 6-11. Such groups are called _strings_. An entire string is connected to or disconnected from a bit line at once by transistor switches at the beginning and end of the string. This resembles the input circuit of a NAND gate, which has several inputs, all of which must be raised to a logic 1 level to produce a logic 0 level on the output.

> NAND 闪存被设计为充当大容量存储器而非非易失性 RAM。为了经济高效，存储阵列中必须有大量单元。在 NAND 阵列中，单元不是单独寻址的，而是串联连接的 32 或 64 个单元的组，如图 6-11 所示。这样的组称为 *strings*。通过在串的开始和结束处的晶体管开关，一次将整个串连接到位线或从位线断开。这类似于 NAND 门的输入电路，它有多个输入，所有输入都必须提升到逻辑 1 电平，才能在输出端产生逻辑 0 电平。

![[FIGURE 6-11:](#09_9781119183938-ch06.xhtml#rc06-fig-0011) A NAND cell string](./media/images/9781119183938-fg0611.png)

NAND arrays can be denser than NOR arrays because placing multiple cells in series greatly reduces the overhead inherent in connecting individual flash cells to word lines and bit lines. Think of it as less  `wiring`  on the chip surface, allowing the space saved to be used to fabricate additional cells.

> NAND 阵列可以比 NOR 阵列更密集，因为将多个单元串联放置大大减少了将单个闪存单元连接到字线和位线所固有的开销。将其视为芯片表面上更少的 `布线` ，允许节省的空间用于制造额外的电池。

One way to think of the difference between NOR and NAND flash is to see NAND cell strings as occupying the positions that single flash cells occupy in a NOR array. Having multiple cells in a string requires an additional level of addressing, as shown in Figure 6-12. Because they’re connected in series, the cells in a NAND string cannot be programmed together. Instead, an array’s decoding circuitry treats each corresponding bit in a large number of strings (anywhere from 512 to 4,096) as a unit called a _page_. A NAND page is the smallest unit that may be read from or written to in a single operation.

> 考虑 NOR 和 NAND 闪存之间差异的一种方式是将 NAND 单元串视为占据 NOR 阵列中单个闪存单元所占据的位置。在一个字符串中有多个单元格需要额外的寻址级别，如图 6-12 所示。因为它们是串联的，NAND 串中的单元不能一起编程。相反，阵列的解码电路将大量字符串(从 512 到 4096)中的每个对应位视为一个称为 *page* 的单元。NAND 页是可以在单个操作中读取或写入的最小单元。

![[FIGURE 6-12:](#09_9781119183938-ch06.xhtml#rc06-fig-0012) NAND strings, pages and blocks](./media/images/9781119183938-fg0612.png)

Taken together, all the cell strings that span a page are called a _block_. Depending on the number of cells in a string and the number of strings in a page, a NAND block may run from 16KB to 128KB in size. The number of blocks in a NAND array varies widely and is generally from 2,048 and up.

> 总之，跨越一个页面的所有单元格字符串都称为 *block*。根据字符串中的单元数和页面中的字符串数，NAND 块的大小可以从 16KB 到 128KB。NAND 阵列中的块数变化很大，通常为 2048 个以上。

Reading a single cell out of a string of cells in a NAND array requires that the entire series string conduct current; otherwise, there would be no way to test the state of any individual cell. A read operation involves first applying to the control gates of all the MOSFETs, except the one to be read, a voltage that is sufficient to drive the MOSFETs into full conduction, irrespective of the charge state of their floating gates. This essentially takes them out of the circuit as data storage devices and makes them serve temporarily as simple electrical conductors. After the rest of the string has been made to conduct, a near-threshold voltage is applied to the gate of the MOSFET to be read: its conduction, and therefore the conduction of the string as a whole, is then determined by the charge on its floating gate. Depending on the current flowing through the string, the cell is interpreted as a 0-bit or a 1-bit.

> 从 NAND 阵列中的单元串中读取单个单元需要整个串联串传导电流；否则，将无法测试任何单个细胞的状态。读取操作包括首先向除要读取的 MOSFET 之外的所有 MOSFET 的控制栅极施加足以驱动 MOSFET 完全导通的电压，而不管其浮置栅极的充电状态如何。这基本上将它们作为数据存储设备从电路中取出，并使它们暂时充当简单的电导体。在使串的其余部分导通之后，一个接近阈值的电压被施加到要读取的 MOSFET 的栅极：其导通，因此串作为一个整体的导通，然后由其浮置栅极上的电荷决定。根据流经串的电流，单元被解释为 0 位或 1 位。

Not all of the cells in a flash array are used for storing data. A certain number are used for ECC error detection and correction. Some are also set aside as spare cells, to be used by the flash translation layer in bad block management, as described in the next section.

> 并非闪存阵列中的所有单元都用于存储数据。一定数量用于 ECC 错误检测和纠正。如下一节所述，一些还被作为备用单元，供闪存转换层在坏块管理中使用。

One other characteristic of flash memory bears on the difference between NOR and NAND: the process for erasing bits is electrically different from the process for writing new bits. Erasing sets all bits in the erased area to 1, and 1-bits are not written to cells except as part of the erase process. When new data is written to flash cells, only the 0-bits in the data are actually written. Whatever bits in the new data are to be 1-bits are simply left alone. This makes flash memory erase-before-write, meaning that every write operation must be preceded by an erase operation, which provides the 1-bits over which 0-bits may be written. A block is the smallest unit of NAND storage that may be erased in one operation. Because NOR must be able to read and write data at the machine word size (anywhere from 8 bits to 64 bits) the machine word is the smallest erasable unit. This allows execute in place (XIP) but also makes writing to NOR arrays slower per byte than NAND.

> 快闪存储器的另一个特点与 NOR 和 NAND 之间的区别有关：擦除位的过程与写入新位的过程在电学上不同。擦除将擦除区域中的所有位设置为 1，除作为擦除过程的一部分外，1 位不写入单元。当新数据写入闪存单元时，只有数据中的 0 位被实际写入。新数据中的任何位都是 1 位，只需单独保留。这使得闪存在写入之前进行擦除，这意味着每次写入操作之前都必须进行擦除操作，擦除操作提供 1 位，0 位可以写入。块是可以在一次操作中擦除的 NAND 存储的最小单位。因为 NOR 必须能够读取和写入机器字大小(从 8 位到 64 位)的数据，所以机器字是最小的可擦除单元。这允许就地执行(XIP)，但也使写入 NOR 阵列的速度比 NAND 每字节慢。

### Wear Levelling and the Flash Translation Layer

The big problem with flash is endurance: cells can only undergo so many erase/rewrite cycles before the floating gate insulation degrades and the cells become unusable. The number of erase/rewrite cycles for TLC NAND can be as low as 1,000 before problems appear. Endurance issues of this sort don’t exist with conventional hard drives, and so traditional file systems make no effort to limit the number of writes to a particular sector on a particular hard drive platter.

> 闪存的最大问题是耐久性：在浮栅绝缘退化和单元变得不可用之前，单元只能经历如此多的擦除/重写周期。在出现问题之前，TLC NAND 的擦除/重写周期数可以低至 1000。传统硬盘驱动器不存在这种持久性问题，因此传统文件系统不努力限制对特定硬盘驱动器盘片上特定扇区的写入次数。

Clearly, there must be some sort of mechanism for preventing any single block of flash cells from approaching that endurance limit too quickly and for removing unusable blocks from a flash device’s active capacity. Such a mechanism is called a _flash translation layer_ (FTL) because it interposes itself between a file system and the  `raw`  flash storage array, accepting hard-disk style commands using LBAs from the file system and translating them to one or more accesses into the flash array. Unlike LBAs in a hard drive, an LBA refers to no fixed location in a flash array. The FTL keeps a mapping table that indicates where an LBA as understood by the file system is currently located in the array. As you’ll soon see, this location bounces around inside the flash array quite a bit.

> 显然，必须有某种机制来防止闪存单元的任何单个块过快接近该耐久极限，并从闪存设备的活动容量中移除不可用的块。这种机制被称为_flash 转换层(FTL)，因为它将自己插入文件系统和 `原始` 闪存阵列之间，使用 LBA 从文件系统接受硬盘式命令，并将其转换为对闪存阵列的一次或多次访问。与硬盘驱动器中的 LBA 不同，LBA 指的是闪存阵列中没有固定的位置。FTL 保留一个映射表，该表指示文件系统所理解的 LBA 当前位于阵列中的位置。正如你很快就会看到的，这个位置在闪存阵列中有很大的反弹。

Beyond keeping track of where file system data is stored in an array, an FTL has three significant jobs that may be better categorised as maintenance:

> 除了跟踪文件系统数据存储在阵列中的位置之外，FTL 还有三项重要工作，可以更好地归类为维护：

- **Wear levelling:** Keeps track of the number of times that a given flash block has been rewritten and writes new data to blocks that have been used the least - **Garbage collection:** Blocks marked as available are reclaimed and put back into the pool of available blocks - **Bad-block management:** Identifies bad blocks, removes them from use and substitutes spare blocks to keep the array at its nominal capacity

> -**磨损均衡：**跟踪给定闪存块被重写的次数，并将新数据写入使用最少的块-**垃圾收集：**标记为可用的块被回收并放回可用块池-**坏块管理：**标识坏块，将其从使用中删除，并替换备用块以保持阵列的标称容量

Wear levelling is the FTL’s most important job. There are a number of ways to handle it. The most common uses a _block aging table_ (BAT) to count how many times a given block has undergone an erase/write cycle. New data written to the array is stored in blocks that have seen the least use. This is called _dynamic wear levelling_.

> 磨损调平是 FTL 最重要的工作。有许多方法可以处理它。最常见的方法是使用_block 老化表(BAT)来计算给定块经历擦除/写入周期的次数。写入阵列的新数据存储在使用最少的块中。这称为动态磨损水平。

Inherent in the way that computers are used is the fact that some sorts of data change far more often than others. Configuration data changes less often than records in a database, for example. Through a process called _static_ or _global wear levelling_, the FTL determines which data changes least often and relocates it to flash blocks that are approaching their endurance limits. Because this data changes rarely, such  `old`  blocks can remain in use longer than they would if wear levelling were strictly dynamic.

> 计算机使用方式的内在特点是，某些类型的数据比其他类型的数据变化更频繁。例如，配置数据的更改频率低于数据库中的记录。通过一个称为 `静态` 或 `全局磨损水平` 的过程，FTL 确定哪些数据变化最不频繁，并将其重新定位到接近其耐久极限的闪存块。由于这些数据很少发生变化，因此这种 `旧` 块的使用时间可能比磨损均衡严格动态时更长。

When a flash device is brand new, its write policy is simple: write data to a block that’s never been written to before. Remember that flash cells must be erased before they’re written, and that erasing a flash block is time-consuming compared to writing new data, by a factor as high as 100. Because all blocks come pre-erased in a new device, this means that performance is very snappy at first. After all blocks have been written to at least once, the FTL must begin erasing blocks to prepare them for writing, and performance may decline.

> 当闪存设备是全新的时，它的写入策略很简单：将数据写入以前从未写入过的块。请记住，闪存单元在写入之前必须被擦除，擦除闪存块与写入新数据相比耗时高达 100 倍。因为在新设备中，所有块都是预先擦除的，这意味着最初的性能非常快。在所有块至少被写入一次后，FTL 必须开始擦除块以准备写入，性能可能会下降。

This effect is worse than it seems at first glance. Writing data to a NAND flash array is done at a page level, but there are many pages in a block, and an entire block must be erased before any one of its pages can be rewritten. For this reason, flash does not allow data to be rewritten  `in place` . To change one page in a block, the modified page is written to a page that has not been written to since erasure. This may be in the same block, if erased space is still available, or it may be in another block entirely. The original page is then marked as invalid. If no erased space is available, the FTL may first have to erase a block that contains no  `fresh`  (that is, valid) data. Writing new data to a single page may mean subjecting more pages than one to an erase/write operation. This is called _write amplification_, and it increases wear on the flash array. Keeping write amplification to a minimum is an important priority in any FTL.

> 这种效果比乍一看更糟糕。将数据写入 NAND 闪存阵列是在页面级别完成的，但一个块中有许多页面，必须擦除整个块，然后才能重写其任何一个页面。因此，flash 不允许 `就地` 重写数据。要更改块中的一个页面，修改后的页面将被写入自擦除后未写入的页面。如果擦除的空间仍然可用，这可能在同一块中，也可能完全在另一块中。然后将原始页面标记为无效。如果没有可用的擦除空间，FTL 可能必须首先擦除不包含 `新` (即有效)数据的块。将新数据写入单个页面可能意味着对多于一页的页面进行擦除/写入操作。这被称为 `写入放大` ，它会增加闪存阵列的磨损。在任何 FTL 中，将写放大保持在最小值是一个重要的优先事项。

To help with wear levelling, when a device is manufactured a certain number of blocks are set aside and are not counted towards the device’s marked capacity. This is called _overprovisioning_. Some of these  `extra`  blocks are later used to replace blocks that fail over time. Most are used as a sort of on-chip cache of free blocks to keep write amplification down. The percentage of overprovisioning varies widely by device and manufacturer but may be as much as 150 percent of the device’s marked capacity. Overprovisioning adds to the device’s cost but extends its useful life.

> 为了有助于磨损平衡，在制造设备时，会留出一定数量的块，不计入设备的标记容量。这称为 *overprovisioning*。这些 `额外` 块中的一些稍后用于替换随时间推移而失效的块。大多数都被用作一种空闲块的片上缓存，以降低写放大率。过度调配的百分比因设备和制造商而异，但可能高达设备标记容量的 150%。过度配置增加了设备的成本，但延长了其使用寿命。

### Garbage Collection and TRIM

An FTL generally has a background task that gathers  `live`  pages from blocks that contain one or more invalid pages, and consolidates them on fresh blocks. Blocks that no longer contain live pages may be marked for later erasure. This process is called _garbage collection_, and it is roughly analogous to defragmenting a hard drive. The garbage collection process may also erase blocks with no live data to increase available blocks for new page writes. Erasing is time-intensive, so the FTL performs block erasures during  `quiet time`  when the device is not busy with read or write requests from the OS.

> FTL 通常有一个后台任务，它从包含一个或多个无效页面的块中收集 `活动` 页面，并将它们合并到新的块中。不再包含活动页面的块可能会标记为稍后擦除。这个过程称为 *garbagecollection*，大致类似于对硬盘进行碎片整理。垃圾收集过程还可以擦除没有实时数据的块，以增加新页面写入的可用块。擦除是时间密集型的，因此 FTL 在设备不忙于操作系统的读写请求的 `安静时间` 执行块擦除。

There is a problem with garbage collection: the FTL only marks a page as invalid after the OS rewrites the LBA that maps to the page. When a file is deleted (and trash emptied) at the OS level, its LBAs are marked as available by the OS. Until fairly recently, the OS had no way to tell the FTL which pages mapped to a deleted file and could therefore be erased and reused at any time. In the late 2000s, the TRIM command was added to the SATA command set. (TRIM is not an acronym, but SATA commands are traditionally given in uppercase.) TRIM is available only to flash devices on a SATA interface, which typically means solid-state drives. (USB thumb drives and SD cards do not support TRIM.) When the OS deletes a file, it issues a TRIM command to the SSD, which includes the LBAs of all sectors belonging to the deleted file. The SSD’s FTL can then mark all flash blocks mapping to those LBAs as available for erasure and reuse.

> 垃圾收集存在一个问题：FTL 仅在 OS 重写映射到页面的 LBA 后将页面标记为无效。当文件在 OS 级别被删除(并清空垃圾箱)时，其 LBA 将被 OS 标记为可用。直到最近，操作系统还无法告诉 FTL 哪些页面映射到已删除的文件，因此可以随时擦除和重用。2000 年代后期，TRIM 命令被添加到 SATA 命令集。(TRIM 不是首字母缩略词，但 SATA 命令通常以大写字母给出。)TRIM 仅适用于 SATA 接口上的闪存设备，通常指固态驱动器。(USB 拇指驱动器和 SD 卡不支持 TRIM。)当 OS 删除文件时，它会向 SSD 发出 TRIM 命令，其中包括属于已删除文件的所有扇区的 LBA。然后，SSD 的 FTL 可以将映射到这些 LBA 的所有闪存块标记为可擦除和重用。

A common misperception is that TRIM is a command telling the flash array,  `Erase these LBAs right now` . It is not. TRIM simply tells the FTL which file system LBAs have been deleted, and the blocks mapping to those LBAs may be erased whenever the garbage collection code has time. Some very recent flash devices include a separate command called secure TRIM, which suspends other flash array activity until all pages marked for erasure are actually erased.

> 一个常见的误解是 TRIM 是一个命令，告诉闪存阵列 `立即擦除这些 LBA` 。事实并非如此。TRIM 只需告诉 FTL 哪些文件系统 LBA 已被删除，只要垃圾收集代码有时间，映射到这些 LBA 的块就会被擦除。一些最新的闪存设备包括一个名为 secure TRIM 的单独命令，该命令将暂停其他闪存阵列活动，直到所有标记为擦除的页面被实际擦除。

A significant number of blocks in a flash chip are unusable at the time of manufacture due to minute physical flaws that appear during masking and etching, and these blocks are marked as bad during unit testing. For the same reasons, some usable blocks have higher or lower endurance than others, and a few will fail over time during ordinary use. The FTL notes which blocks generate ECC errors (see [Chapter 3](#06_9781119183938-ch03.xhtml) for a brief explanation of ECC) and beyond a threshold number of such errors marks them as unusable. To keep the capacity of the device from gradually shrinking, blocks originally allocated as spares via overprovisioning are added to the available block pool.

> 由于掩模和蚀刻过程中出现的微小物理缺陷，闪存芯片中的大量块在制造时无法使用，并且这些块在单元测试期间被标记为坏块。出于同样的原因，一些可用的块具有比其他块更高或更低的耐久性，并且一些块在正常使用期间会随着时间而失效。FTL 注意到哪些块会生成 ECC 错误(请参见[第 3 章](#06_9781119183938-ch03.xhtml)以了解 ECC 的简要解释)，并且超过阈值数量的此类错误将其标记为不可用。为了防止设备的容量逐渐缩小，通过过度调配将最初分配为备用的块添加到可用块池中。

The FTL software runs on a special-purpose microcontroller often based on an ARM CPU. Until very recently, the controller chip and the NAND flash storage array chip had each been separate dies in their own IC packages. The two ICs were, integrated with each other at the circuit-board level. NAND arrays and their controllers are now integrated in a single IC package, even though each remains on a separate die. The significant differences between fabrication processes for flash and for microcontroller chips will keep the two from sharing a single die for the foreseeable future.

> FTL 软件在通常基于 ARM CPU 的专用微控制器上运行。直到最近，控制器芯片和 NAND 闪存阵列芯片都是各自的 IC 封装中的独立管芯。这两个 IC 在电路板级别彼此集成。NAND 阵列及其控制器现在集成在单个 IC 封装中，尽管每个都保留在单独的管芯上。闪存和微控制器芯片的制造工艺之间的显著差异将在可预见的未来阻止两者共享一个管芯。

> [!NOTE]
> that there isn’t always a separate CPU for the flash controller software. The cheapest portable music players are essentially USB thumb drives with a two-line LCD display, a headphone jack and a couple of buttons. To reduce cost, the audio codecs and UI manager on such devices often run on the same silicon as the flash controller software, so that the FTL is simply one component of a simple real-time OS, complete with a display and input buttons.

### SD Cards

Until fairly recently, flash-based SATA solid-state drives were still a little exotic, but consumer-class flash storage has been on the market since the Compact Flash (CF) card was introduced in 1994. Early CF cards used NOR flash, but changed to the denser NAND flash in response to market demand for higher capacities. The Multimedia Card (MMC) format appeared in 1997, and was less than half the size of CF, at only 24mm × 32mm. In 1999 the SD card added various digital rights management (DRM) features to the basic MMC spec and soon became the dominant card-based removable storage format. SD cards are the same width and height as MMC, but they’re 1mm thicker. An MMC will plug into an SD card slot, but not vice versa.

> 直到最近，基于闪存的 SATA 固态驱动器仍然有点陌生，但自 1994 年推出紧凑型闪存(CF)卡以来，消费级闪存一直在市场上。早期的 CF 卡使用 NOR 闪存，但为了响应市场对更高容量的需求，改为更密集的 NAND 闪存。多媒体卡(MMC)格式出现于 1997 年，其尺寸不到 CF 的一半，只有 24mm×32mm。1999 年，SD 卡在基本 MMC 规范中添加了各种数字版权管理(DRM)功能，并很快成为主要的基于卡的可移动存储格式。SD 卡的宽度和高度与 MMC 相同，但厚度为 1mm。MMC 将插入 SD 卡插槽，但反之亦然。

IBM introduced the USB thumb drive in 2000, which allowed removable flash storage to be used in desktop and laptop computers without flash card slots. Even the earliest thumb drives had capacities several times that of 3.5` floppy diskettes, and floppy disk drives began vanishing from desktop computers at about that time.

> IBM 在 2000 年推出了 USB 拇指驱动器，允许在没有闪存卡插槽的台式机和笔记本电脑中使用可移动闪存。即使是最早的拇指驱动器，其容量也是 3.5 英寸软盘的几倍，大约在那时，软盘驱动器开始从台式计算机中消失。

The Raspberry Pi uses the SD card format for its primary non-volatile storage, including both software and data. The SD format has seen three generations:

> 复盆子 Pi 使用 SD 卡格式作为主要非易失性存储，包括软件和数据。SD 格式经历了三代：

- **Secure Digital standard capacity (SDSC):** Stores from 8MB to 2GB - **Secure Digital high capacity (SDHC):** Stores from 4GB to 32GB - **Secure Digital extended capacity (SDXC):** Stores from 64GB to 2TB

> -**安全数字标准容量(SDSC)：**从 8MB 存储到 2GB-**安全数字高容量(SDHC)：**存储从 4GB 存储到 32GB-**安全数据扩展容量(SDXC)：**将 64GB 存储到 2TB

The generations are backward compatible, meaning that SDHC and SDXC card slots accept and read earlier generations of cards. SDXC cards are usually sold preformatted with the exFAT (extended file allocation table) file system, which allows a higher card capacity than FAT32 without the additional overhead of the NTFS file system. ExFAT is Microsoft proprietary and support under Linux (including Raspbian) is still limited due to patent issues. The Raspberry Pi bootloader cannot boot from an exFAT card, so SDXC cards must be reformatted to FAT32 before use with the Raspberry Pi.

> 这两代卡是向后兼容的，这意味着 SDHC 和 SDXC 卡槽接受并读取前几代卡。SDXC 卡通常以预先格式化的 exFAT(扩展文件分配表)文件系统出售，该文件系统允许比 FAT32 更高的卡容量，而无需 NTFS 文件系统的额外开销。ExFAT 是微软的专利，由于专利问题，Linux(包括 Raspbian)下的支持仍然有限。Raspberry Pi 引导加载程序无法从 exFAT 卡启动，因此 SDXC 卡在与 Raspberrry Pi 一起使用之前必须重新格式化为 FAT32。

Some SD cards are faster than others. There are several speed classes, where the class number denotes the approximate sustained sequential transfer speed in MB per second. For example, a class 4 card transfers data at 4MB/second, and a class 10 card transfers data at 10 MB/second. A 2009 enhancement to the SD card spec adds ultra-high speed (UHS) formats that change both the card’s electrical interface and the controller interface to obtain speeds as high as 100MB/second. UHS cards work in conventional SD interfaces, but are no faster than the older interface allows.

> 有些 SD 卡比其他 SD 卡更快。有几个速度等级，其中等级编号表示以每秒 MB 为单位的近似持续顺序传输速度。例如，4 类卡以 4MB/秒的速度传输数据，10 类卡以 10MB/秒速度传输数据。2009 年对 SD 卡规范的一项增强增加了超高速(UHS)格式，可以改变 SD 卡的电气接口和控制器接口，以获得高达 100MB/秒的速度。UHS 卡在传统的 SD 接口中工作，但速度不比旧接口允许的速度快。

The use of speed class numbers suggests that SD card speed is a simple business, but in truth speed depends heavily on how the card is being used. The vast majority of SD cards are used in devices like digital cameras or music players, in which sequential read and write speed is the primary determinant of performance; for these applications, a speed class value may be enough. In contrast, a general-purpose OS like Raspbian tends to perform frequent smaller reads and writes to non-contiguous areas of the card; in this case, random-access performance becomes the controlling factor, and random access is where SD cards do least well because of the inescapable read-modify-erase-write cycle dictated by the flash technology. If a class 10 card isn’t optimised for many relatively small read and write operations, a card with a lower speed class but better random-access performance may perform noticeably better with the Raspberry Pi. This is where the design of the SD card controller comes into play: careful use of buffering minimises the number of reads and writes actually made to the flash array, which in turn improves performance on random access. Unfortunately, there’s no standard metric for random performance printed on SD cards. Benchmark roundups published for groups of specific cards may be helpful. You can see a good example at [`http://thewirecutter.com/reviews/best-sd-card/`](http://thewirecutter.com/reviews/best-sd-card/).

> 速度等级数字的使用表明 SD 卡速度是一项简单的业务，但事实上，速度在很大程度上取决于卡的使用方式。绝大多数 SD 卡用于数码相机或音乐播放器等设备，其中顺序读写速度是性能的主要决定因素；对于这些应用，速度等级值可能就足够了。相反，像 Raspbian 这样的通用操作系统倾向于频繁地对卡的非连续区域执行较小的读写操作；在这种情况下，随机存取性能成为控制因素，而随机存取是 SD 卡表现最差的地方，因为闪存技术规定了不可避免的读-修改-擦除-写入周期。如果 10 级卡没有针对许多相对较小的读写操作进行优化，则速度等级较低但随机访问性能更好的卡在树莓派上的性能可能会明显更好。这就是 SD 卡控制器的设计发挥作用的地方：谨慎使用缓冲区可最大限度地减少对闪存阵列的实际读写次数，从而提高随机访问性能。不幸的是，SD 卡上没有随机性能的标准度量。为特定卡片组发布的基准汇总可能会有所帮助。你可以在[`http://thewirecutter.com/reviews/best-sd-card/`](http://thewirecutter.com/reviews/best-sd-card/).

Also

> 而且

> [!NOTE]
> that  `fake`  SD cards are relatively common; for example, a fake card marked as 32GB might contain only 2 useful GB of storage. Buying from trusted retailers who will honour returns is the best way to avoid this problem.

The current SD card interface bus is 4 bits wide. Early cards used a slower single-bit bus, and so later generations allow the host processor to communicate with the card at startup across the 1-bit bus until the host identifies the card and determines its generation, bus width and feature set. After initialisation, the host uses the full bus width available. The startup protocol also allows the host to determine the card’s capacity, speed and features unavailable in the basic SD standard.

> 当前 SD 卡接口总线为 4 位宽。早期的卡使用较慢的单位总线，因此后来的几代允许主机处理器在启动时通过 1 位总线与卡通信，直到主机识别卡并确定其版本、总线宽度和功能集。初始化后，主机使用可用的全部总线宽度。启动协议还允许主机确定卡的容量、速度和基本 SD 标准中不可用的功能。

The host controls the card using a command set, just as in a hard drive or SSD. The SD command set is adapted from the earlier MMC command set. The differences are primarily associated with the SD standard’s DRM security mechanisms.

> 主机使用命令集控制卡，就像在硬盘驱动器或 SSD 中一样。SD 命令集改编自先前的 MMC 命令集。这些差异主要与 SD 标准的 DRM 安全机制有关。

### eMMC

Not all flash storage needs to be removable, or even separate from the circuit board on which the rest of a device like a smartphone or tablet is assembled. There is a class of ICs defined in a standard called _embedded MMC_ (eMMC), which is designed to be soldered to a circuit board using a ball-grid array (BGA) package. ([Chapter 3](#06_9781119183938-ch03.xhtml) describes BGAs in connection with Raspberry Pi memory chips.) The flash controller and NAND flash arrays are on separate dies but enclosed in the same package, using a technology called _multi-chip packaging_ (MCP).

> 并非所有的闪存都需要是可移动的，甚至不需要与组装智能手机或平板电脑等其他设备的电路板分离。标准中定义了一类集成电路，称为嵌入式 MMC(eMMC)，该集成电路设计为使用球栅阵列(BGA)封装焊接到电路板上。([第 3 章](#06_9781119183938-ch03.xhtml)描述了与 Raspberry Pi 存储芯片相关的 BGA。)闪存控制器和 NAND 闪存阵列位于不同的裸片上，但封装在同一个封装中，使用的技术称为多芯片封装(MCP)。

The eMMC interface is an expansion of the original MMC interface. The bus is 8 bits wide, and adds flash-specific SATA commands to the MMC command set. These include TRIM, secure TRIM and secure erase. Secure erase erases the entire NAND array in an unrecoverable fashion, and is said to return the eMMC device to its original out-of-the-box state in terms of data. It does not reverse reduced endurance due to earlier use.

> eMMC 接口是原始 MMC 接口的扩展。该总线为 8 位宽，并将闪存专用 SATA 命令添加到 MMC 命令集。这些包括 TRIM、安全 TRIM 和安全擦除。安全擦除以不可恢复的方式擦除整个 NAND 阵列，据说可以将 eMMC 设备恢复到其原始的开箱即用状态。它不会逆转由于早期使用而降低的耐久性。

Because eMMC storage is often the only non-volatile storage integral to a device like a smartphone or tablet, the current eMMC standard (v5.1) specifies two different boot partitions plus an additional partition called the _replay-protected memory block_ (RPMB) that contains DRM-related code and decryption keys. These partitions are actually imposed on the flash array at manufacture and are roughly equivalent to a factory low-level format on a conventional hard drive. The remaining storage in the eMMC device is considered user space and may contain up to four general-purpose partitions for user data.

> 由于 eMMC 存储通常是智能手机或平板电脑等设备的唯一非易失性存储，因此当前的 eMMC 标准(v5.1)指定了两个不同的启动分区，外加一个名为 *replay-protected memory block*(RPMB)的附加分区，其中包含 DRM 相关代码和解密密钥。这些分区实际上是在制造时强加在闪存阵列上的，大致相当于传统硬盘上的工厂低级格式。eMMC 设备中的剩余存储被视为用户空间，最多可包含四个用于用户数据的通用分区。

Most eMMC devices use either MLC or TLC encoding for enhanced density; MLC is more common in devices targeted at industrial applications (which require long-term reliability but are less cost-sensitive), and TLC in consumer applications (where the reverse applies). The eMMC standard provides for enhanced areas that use single-level cell (SLC) encoding for better reliability, at the cost of lower density. By default, the boot partitions and RPMB are enhanced areas. Sections of user space may optionally be specified as enhanced areas. Establishment of enhanced areas in the flash array may be done only once and may not be undone during the life of the array. The operation is generally performed by the manufacturer of the electronics into which the eMMC is integrated, during assembly and installation of the OS.

> 大多数 eMMC 设备使用 MLC 或 TLC 编码以增强密度；MLC 在针对工业应用的设备中更为常见(这些设备需要长期可靠性，但对成本不太敏感)，而 TLC 在消费者应用中更为普遍(反之亦然)。eMMC 标准以较低的密度为代价，提供了使用单级单元(SLC)编码以提高可靠性的增强区域。默认情况下，引导分区和 RPMB 是增强区域。用户空间的部分可以可选地指定为增强区域。闪存阵列中增强区域的建立可以只进行一次，并且在阵列的寿命期间不能撤消。操作通常由 eMMC 集成的电子设备制造商在操作系统的组装和安装过程中执行。

A standard released in 2012 called Universal Flash Storage (UFS) may replace eMMC in coming years. UFS incorporates a new standard called M-PHY for the electrical connection with the host processor, and the SCSI architectural model for logical communication with the OS and applications. UFS allows delivery of an SSD in a single IC package that may be soldered to a circuit board. The first UFS devices appeared in early 2015, and at this writing have capacities as high as 256GB.

> 2012 年发布的通用闪存(UFS)标准可能会在未来几年取代 eMMC。UFS 采用了一种称为 M-PHY 的新标准，用于与主机处理器的电气连接，以及用于与操作系统和应用程序进行逻辑通信的 SCSI 体系结构模型。UFS 允许在单个 IC 封装中交付 SSD，该封装可以焊接到电路板上。第一批 UFS 设备出现在 2015 年初，目前的容量高达 256GB。

### The Future of Non-Volatile Storage

At this writing, flash has no serious competition in the area of non-volatile semiconductor memory. Flash-based solid-state drives are coming into their own, with 2TB units now widely available. They’re still expensive (roughly £500) but if history is any guide, that price will come down quickly in the near future. 512GB SDXC flash cards are on the market, and the SDXC format can embrace cards with as much as 2TB of capacity. Unfortunately, the same physical and economic challenges that face manufacturers of digital logic devices also impose limits on the achievable density of planar (2-D) flash-based storage, and these limits are now in sight. As we approach the 10 nanometre (nm) process node (the next level of ever-smaller semiconductor fabrication technology) it becomes harder to reliably manufacture the well-insulated floating gate structures on which flash depends, and capital investment in new fabrication facilities becomes harder to justify.

> 在本文中，flash 在非易失性半导体存储器领域没有严重的竞争。基于闪存的固态驱动器正在发展壮大，2TB 单元现已广泛提供。它们仍然很贵(大约 500 英镑)，但如果历史可以作为指导，价格将在不久的将来迅速下降。市场上有 512GB SDXC 闪存卡，SDXC 格式可以容纳容量高达 2TB 的卡。不幸的是，数字逻辑设备制造商面临的同样的物理和经济挑战也对基于平面(2-D)闪存的存储的可实现密度施加了限制，这些限制现在已经出现。随着我们接近 10 纳米(nm)工艺节点(更小的半导体制造技术的下一个级别)，可靠地制造闪存所依赖的良好绝缘浮栅结构变得越来越困难，对新制造设施的资本投资也越来越难以证明。

To get past such limitations, much research is currently being done on 3-D fabrication, which allows the manufacture of NAND flash cell arrays in which cell strings are arranged vertically rather than in the horizontal dimension of a planar chip. Greater densities thus become possible without reducing the fabrication process size. The first commercial products using 3-D NAND flash are now on the market, and their density will only improve as the techniques are perfected. One caveat is that because 3-D fabrication requires more process steps, it is unlikely to yield the dramatic reductions in cost-per-bit that have historically been provided by moving to new process nodes.

> 为了克服这些限制，目前正在对 3D 制造进行大量研究，这允许制造 NAND 闪存单元阵列，其中单元串垂直排列，而不是平面芯片的水平维度。因此，在不减小制造工艺尺寸的情况下，更高的密度成为可能。第一批使用 3-D NAND 闪存的商业产品现已上市，随着技术的完善，它们的密度只会提高。一个警告是，由于 3D 制造需要更多的工艺步骤，因此不太可能像以往那样通过移动到新的工艺节点来大幅降低每比特的成本。

Another promising new technology is resistive RAM (RRAM or ReRAM), an EEPROM mechanism that does away with floating-gate cells entirely. RRAM stores data in cells containing a substance that changes resistance when a sufficiently high voltage is applied across it. Commercial devices are still a few years off, but early indications are that it may permit smaller cell sizes and lower read/write latency than flash.

> 另一项有前途的新技术是电阻 RAM(RRAM 或 ReRAM)，这是一种 EEPROM 机制，可以完全去除浮栅单元。RRAM 将数据存储在含有一种物质的单元中，当在其上施加足够高的电压时，该物质会改变电阻。商用设备还有几年的时间，但早期迹象表明，它可能允许比闪存更小的单元大小和更低的读/写延迟。

The overall trend is clear: spinning disks are losing ground, and no-moving-parts solid-state storage is gaining. The trend is being driven to some extent by the parallel increase in the popularity of hand-held computers and the resolution of video. The breathtaking quality of emerging ultra-high definition (UHD) TV content comes at a steep storage cost: a 100-minute movie occupies 15GB of space. A fair number of those will fit on a 1TB hard drive. But once the OS and apps claim their space, not even one will fit on a low-end 16GB tablet. Current SSD and eMMC standards allow for 2TB flash devices. Silicon fabrication is moving relentlessly in that direction, and within a decade spinning disks may seem as archaic as paper tape does today.

> 总体趋势很明显：旋转磁盘正在失去优势，没有移动部件固态存储正在增长。这一趋势在某种程度上是由手持电脑的普及和视频分辨率的提高所推动的。新兴超高清(UHD)电视内容的惊人质量需要高昂的存储成本：一部 100 分钟的电影占用 15GB 的空间。其中相当一部分可以安装在 1TB 硬盘上。但一旦操作系统和应用程序占据了自己的空间，就连一个都无法安装在低端 16GB 平板电脑上。当前的 SSD 和 eMMC 标准允许 2TB 闪存设备。硅制造业正朝着这个方向无情地发展，在十年内，旋转磁盘可能会像今天的纸带一样过时。
