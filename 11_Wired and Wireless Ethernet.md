Chapter 7

# Wired and Wireless Ethernet

**FOR A LONG** time, there were so few computers in the world that the benefits of connecting them to one another simply didn’t occur to anyone. In the mainframe era, `data sharing` consisted of printing out reports on huge piles of paper and sending them to whoever needed the data. Early use of data communications was not for networking but for remote access to user timesharing terminals, card/tape readers and printers. (For more on this, see [Chapter 6](#09_9781119183938-ch06.xhtml).) It wasn’t about connecting computers to computers but rather about connecting computers to their peripherals. As currently understood, _networking_ is the practice of transferring data files and commands between otherwise independent computers.

> 很长一段时间以来，世界上的计算机太少了，任何人都没有想到将它们连接起来的好处。在大型机时代，`数据共享` 包括将报告打印在一大堆纸上，然后发送给需要数据的人。早期使用数据通信不是为了联网，而是为了远程访问用户分时终端、读卡器/磁带机和打印机。(有关这方面的更多信息，请参见[第 6 章](#09*9781119183938-ch06.xhtml)。)这不是关于将计算机连接到计算机，而是关于将计算机与外围设备连接。正如目前所理解的，**networking 是在其他独立计算机之间传输数据文件和命令的实践**。

Only after the cost of computers came down due to the introduction of minicomputers did universities and research organisations have a critical mass of `in-house` computers to interconnect, circa 1965. After that, networking technology advanced quickly. The initial focus was on connecting computers at a distance, in separate buildings or even separate research campuses, in what came to be called a _wide-area network_ (WAN). Lawrence Roberts and Thomas Marill did the experimental work on wide-area network hardware at Massachusetts Institute of Technology’s Lincoln Labs that led directly to the seminal research network Advanced Research Projects Agency Network (ARPANET) by 1969. Robert Kahn and Vint Cerf created TCP/IP (Transmission Control Protocol/Internet Protocol) that was perfected on ARPANET by 1983 and later became the foundation of the modern Internet.

> 只有在微型计算机的引入使计算机的成本降低之后，大学和研究机构才有足够数量的 `内部` 计算机进行互连，大约在 1965 年。此后，网络技术迅速发展。最初的重点是在不同的建筑物，甚至是不同的研究校园，在一个被称为广域网(WAN)的地方远程连接计算机。劳伦斯·罗伯茨(Lawrence Roberts)和托马斯·马里尔(Thomas Marill)在麻省理工学院(Massachusetts Institute of Technology)的林肯实验室(Lincoln Labs)进行了广域网硬件的实验工作，到 1969 年，这项工作直接导致了开创性的研究网络高级研究计划机构网络(ARPANET)。Robert Kahn 和 Vint Cerf 创建了 TCP/IP(传输控制协议/互联网协议)，该协议于 1983 年在 ARPANET 上完善，后来成为现代互联网的基础。

In 1971, ALOHAnet was successfully deployed by the University of Hawaii, as a means of linking the university’s computers spread across several islands via radio signals. It was one of the first packet-based networks, and certainly the first wireless network. ALOHAnet introduced the concept of uncoordinated access to a shared medium (in this case, a block of radio spectrum) with support for collision detection, back-off and retransmission; it was one of the inspirations for Ethernet, which was in development about that time and shares these features, which we’ll discuss during the rest of this chapter.

> 1971 年，夏威夷大学成功部署了 ALOHAnet，作为通过无线电信号连接遍布多个岛屿的大学计算机的一种手段。它是第一个基于分组的网络之一，当然也是第一个无线网络。ALOHAnet 引入了对共享媒体(在本例中为无线电频谱块)的非协调访问的概念，支持冲突检测、回退和重传；这是当时正在开发的以太网的灵感之一，它具有这些特性，我们将在本章的其余部分讨论这些特性。

_Local-area networks_ (LANs) came a little later, once multiple computers were deployed in physical proximity within a single building. One of the first operational LANs was the Cambridge Ring, implemented at Cambridge University in 1974 but never commercialised. Xerox Corporation developed what became Ethernet circa 1970 to 1975, published the spec in 1976 and presented Ethernet as a standard in 1980, in cooperation with Digital Equipment Corporation and Intel. In 1983, Ethernet became Institute of Electrical and Electronics Engineers (IEEE) standard 802.3, to tremendous industry enthusiasm. IBM introduced its token ring network architecture in 1985 as a competitor to Ethernet, but the architecture’s proprietary nature prevented it from becoming a wide success.

> \_局域网(LAN)出现的时间稍晚，因为多台计算机被部署在单个建筑物内的物理位置。最早投入运营的局域网之一是剑桥环，于 1974 年在剑桥大学实施，但从未商业化。施乐公司于 1970 年至 1975 年开发了以太网，1976 年发布了规范，1980 年与数字设备公司和英特尔合作将以太网作为标准。1983 年，以太网成为电气和电子工程师协会(IEEE)802.3 标准，引起了业界的极大热情。IBM 于 1985 年推出了其令牌环网络体系结构，作为以太网的竞争对手，但该体系结构的专有性质阻止了它的广泛成功。

Hundreds of network technologies have appeared and vanished since the 1970s. Some were truly minimal: the XModem and Kermit software packages were widely used for transferring files between two microcomputers in the late 1970s and early 1980s, using serial ports. This mechanism required a special serial crossover cable that was often called a _null modem_. The crossover cable connected the serial transmit line of one computer to the serial receive line of the other, allowing direct communication without passing through other communications gear. Computer bulletin-board systems (CBBS) allowed multiple computers to connect to a remote computer via phone lines and modems, allowing text messaging and file transfers. By the late 1990s, the Internet was the dominant WAN, and Ethernet was the dominant LAN.

> 自 20 世纪 70 年代以来，数百种网络技术出现并消失。有些软件确实很小：XModem 和 Kermit 软件包在 20 世纪 70 年代末和 80 年代初被广泛用于使用串行端口在两台微型计算机之间传输文件。这种机制需要一种特殊的串行交叉电缆，通常称为 _null modem_。交叉电缆将一台计算机的串行传输线连接到另一台计算机上的串行接收线，从而允许直接通信而无需通过其他通信设备。计算机公告板系统(CBBS)允许多台计算机通过电话线和调制解调器连接到远程计算机，允许文本消息和文件传输。到 20 世纪 90 年代末，互联网是主导的广域网，以太网是主导的局域网。

## The OSI Reference Model for Networking

Networking can be a complicated business, largely because its job is to bridge a great many different technologies spread across computer categories from hand-held devices to desktop computers to servers. Making sense of it requires a roadmap. Fortunately, we’ve had such a roadmap since the mid-1980s: the _Open System Interconnection_ (OSI) reference model, which became an International Organization for Standardization (ISO) standard in 1984.

> 网络可能是一项复杂的业务，很大程度上是因为它的工作是连接从手持设备到台式计算机再到服务器的各种不同的技术。要理解它需要一个路线图。幸运的是，自 20 世纪 80 年代中期以来，我们就有了这样的路线图：开放式系统互连(OSI)参考模型，该模型于 1984 年成为国际标准化组织(ISO)标准。

---

> [!NOTE]

The abbreviation ISO is not an acronym but an adaptation of a classic Greek term _isos_, which is equal.

> 缩写 ISO 不是首字母缩略词，而是对希腊经典术语 _isos_ 的改编，后者是相等的。

The OSI model is not a specification in the same sense that the IEEE 802.3 Ethernet document is a specification. It’s a way of creating a `big picture` view of the many smaller ideas falling within the larger idea of networking. It’s an educational tool, and also a way to help engineers and programmers stay on the same page when discussing networking technologies. The basic idea is to separate computer networking into conceptual layers, from networking applications at the top (think email clients and web browsers) to copper and fibre-optic cables, radio waves, and their associated electronics at the bottom. The journey of data across a network connection begins at the top, moves downward through the model’s layers to the physical link at the bottom, across the physical link to another computer, and then up through the layers to the top. Figure 7-1 illustrates the OSI reference model.

> OSI 模型与 IEEE 802.3 以太网文档是规范的意义不同。这是一种创建一个 `全局` 视图的方式，可以将许多较小的想法归入网络的大概念中。这是一种教育工具，也是帮助工程师和程序员在讨论网络技术时保持一致的一种方式。基本思想是将计算机网络划分为概念层，从顶层的网络应用程序(如电子邮件客户端和网络浏览器)到底层的铜缆和光纤电缆、无线电波及其相关电子设备。数据通过网络连接的过程从顶部开始，向下通过模型的层移动到底部的物理链路，通过物理链路移动到另一台计算机，然后向上通过层移动到顶部。图 7-1 说明了 OSI 参考模型。

![[FIGURE 7-1:](#10_9781119183938-ch07.xhtml#rc07-fig-0001) The OSI reference model for networking](./media/images/9781119183938-fg0701.png)

---

> [!NOTE]

Because the layers of networking machinery are depicted one atop the other in schematic diagrams of the OSI model, they are often referred to as a _network stack_.

> 因为在 OSI 模型的示意图中，网络机器的层是一层一层地描述的，所以它们通常被称为 _networkstack_。

We’re going to go through the OSI model layer by layer so that you can get a sense for the big picture of networking. This chapter is primarily about wired and wireless Ethernet (both of which are used a great deal with the Raspberry Pi) and so our focus later in the chapter will be on the bottom four layers (called the _transport set_), which encompass Ethernet and two crucial protocols: Transmission Control Protocol (TCP) and Internet Protocol (IP).One way to think of it is that the transport set is about moving data, whereas the top three layers, called the _application set_, are about processing data via networked applications.

> 我们将逐层研究 OSI 模型，以便您了解网络的全貌。本章主要介绍有线和无线以太网(这两种以太网都在 Raspberry Pi 中大量使用)，因此本章后面的重点将放在底层四层(称为 _transport set_)，其中包括以太网和两个关键协议：传输控制协议(TCP)和互联网协议(IP)。一种说法是，传输集是关于移动数据的，而顶层三层(称为应用程序集)是关于通过网络应用程序处理数据的。

Central to the OSI model is the idea of _abstraction_. Each layer conceptually communicates directly with the corresponding layer (its _peer)_ on the other layer of the link, without depending on the exact details of the levels below it; these details are said to be _abstracted away_. So a web browser (in the application layer on your computer) can communicate with a web server (in the application layer on another computer) without caring in detail how the underlying TCP/IP stack provides a reliable channel between the two machines, or whether the physical medium supporting the communication is an Ethernet cable, a Wi-Fi link, a fibre-optic backbone or some combination of the three.

> OSI 模型的核心是抽象思想。每个层在概念上都直接与链路的另一层上的对应层(其\_peer)进行通信，而不依赖于其下面的层的确切细节；据说这些细节被省略了。因此，网络浏览器(在您的计算机上的应用层)可以与网络服务器(在另一台计算机的应用层中)通信，光纤主干或三者的某种组合。

The OSI model has its limits. Not all networking systems map neatly onto its layers, and some networking systems (particularly the Internet suite of protocols) have their own layered reference models that predate the OSI model and span some of its several layers. It is, however, an excellent way to confront the complexities of networking the first time you’re introduced to them.

> OSI 模型有其局限性。并不是所有的网络系统都能很好地映射到其层上，一些网络系统(尤其是互联网协议套件)有自己的分层参考模型，这些模型早于 OSI 模型，并且跨越了其几个层中的一些。然而，当你第一次接触网络时，这是一个很好的方法来应对网络的复杂性。

### The Application Layer

The journey across a network begins when you, the user, launch a network-aware program. That’s what the application layer is about: creating or selecting data for transfer. The computer you’re using is called a _host_, as is the computer on the other end of the line. The program you’re using to communicate across the network is called a _client_. The program at the other end is likely to be a _server_, which is a program that exists purely to send data across a network in response to a request from a client, without human interaction. A server can be thought of as a sort of data robot: your client sends commands or data to the server and the server in turn sends commands and data to your client.

> 当用户启动网络感知程序时，整个网络的旅程就开始了。这就是应用层的作用：创建或选择要传输的数据。您正在使用的计算机被称为 _host_，这一行另一端的计算机也是如此。您用于通过网络进行通信的程序称为 _client_。另一端的程序很可能是 _server_，这是一个程序，它的存在纯粹是为了响应客户端的请求而通过网络发送数据，而无需人工交互。服务器可以被认为是一种数据机器人：客户端向服务器发送命令或数据，服务器反过来向客户端发送命令和数据。

The application layer provides the `human face` of network client programs like email, chat, Usenet, web browsers, FTP, Telnet, and so on. Once the application layer has worked out the commands and data to be sent over the network, and the address of the destination host, these are passed down the stack to the next layer.

> 应用程序层提供了网络客户端程序的 `人脸` ，如电子邮件、聊天、Usenet、web 浏览器、FTP、Telnet 等。一旦应用程序层确定了要通过网络发送的命令和数据以及目标主机的地址，这些命令和数据就会通过堆栈传递到下一层。

### The Presentation Layer

The name of the presentation layer is a little misleading. It has nothing to do with displaying data. It’s really about data conversion, and about how data will be `presented` to the host on the other end of the connection. As we explained in [Chapter 6](#09_9781119183938-ch06.xhtml), there have been numerous character encoding standards, but the three most important are the American Standard for Code Information Interchange (ASCII, used on almost everything today), Unicode (for character sets larger than 256 characters) and Extended Binary Coded Decimal Interchange Code (EBCDIC), which is used only on older `big iron` IBM mainframes. The presentation layer is where encoding differences like that are ironed out. Two other tasks often handled in the presentation layer are encryption and data compression, both of which are optional but these days quite common.

> 表示层的名称有点误导。它与显示数据无关。这实际上是关于数据转换，以及如何将数据 `呈现` 给连接另一端的主机。正如我们在[第 6 章](#09_9781119183938-ch06.xhtml)中所解释的，已经有了许多字符编码标准，但最重要的三个标准是美国代码信息交换标准(ASCII，今天几乎所有东西都使用)、Unicode(用于大于 256 个字符的字符集)和扩展二进制编码十进制交换码(EBCDIC)，它仅用于较旧的 `大熨斗` IBM 大型机。表示层是解决这种编码差异的地方。在表示层中经常处理的另外两个任务是加密和数据压缩，这两个任务都是可选的，但现在很常见。

The presentation layer may translate outgoing data into a specified standard network encoding for transmission; the peer will translate incoming data from the standard encoding into that host’s preferred encoding before passing it up to the application layer. It may add _headers_ to outgoing data before passing it on to the next layer, indicating what encryption or compression has been applied; these are used by the peer to undo the encryption or compression. Headers may be seen as nested envelopes, on each of which is written information relevant to an entity at a particular layer of the stack. Most ISO model layers add one or more headers to the data block passed down from the layer above them. Later on, as the data block passes up the stack on the destination host, the headers are removed in order and interpreted by the peer of the layer that applied them.

> 呈现层可以将输出数据转换为用于传输的指定标准网络编码；对等方将把来自标准编码的传入数据转换成该主机的首选编码，然后再将其传递到应用层。在将输出数据传递到下一层之前，它可能会将 _headers_ 添加到输出数据中，指示应用了什么加密或压缩；对等方使用这些来撤消加密或压缩。标头可以被视为嵌套的信封，每个信封上都写有与堆栈特定层的实体相关的信息。大多数 ISO 模型层将一个或多个标头添加到从其上一层向下传递的数据块中。稍后，当数据块向上传递到目标主机上的堆栈时，标头将按顺序删除，并由应用它们的层的对等方进行解释。

This process, called _data encapsulation_, is shown in Figure 7-2. A Protocol Data Unit (PDU) is a chunk of data handled by a particular layer of the OSI model. For the transport layer, this is called a _segment_. For the network layer, this is called a _packet_. For the data link layer, it’s called a _frame_. (that many people use the terms `packet` and `frame` interchangeably.)

> 这个过程称为*数据封装*，如图 7-2 所示。协议数据单元 (PDU) 是由 OSI 模型的特定层处理的数据块。对于传输层，这称为*段*。对于网络层，这称为*数据包*。对于数据链路层，它被称为 _frame_。(许多人互换使用术语 `数据包` 和 `框架` 。)

![[FIGURE 7-2:](#10_9781119183938-ch07.xhtml#rc07-fig-0002) OSI model data encapsulation](./media/images/9781119183938-fg0702.png)

> [!NOTE]
> that the IP packet and Ethernet frame PDUs are more complex than shown in [Figure 7-2](#10_9781119183938-ch07.xhtml#c07-fig-0002) and have been abbreviated to simplify the diagram. The transport layer segment is shown as a User Datagram Protocol (UDP) PDU, also for simplicity’s sake. As you will see a little later, the transport layer also supports the much more complex TCP PDU. Either a UDP or TCP segment may be processed at the transport layer.
> IP 数据包和以太网帧 PDU 比 [图 7-2](#10_9781119183938-ch07.xhtml#c07-fig-0002) 中显示的更复杂，并且已被缩写以简化图表。传输层段显示为用户数据报协议 (UDP) PDU，也是为了简单起见。稍后您将看到，传输层还支持更复杂的 TCP PDU。可以在传输层处理 UDP 或 TCP 段。

You’ll find it useful to refer to [Figures 7-1](#10_9781119183938-ch07.xhtml#c07-fig-0001) and [7-2](#10_9781119183938-ch07.xhtml#c07-fig-0002) during the detailed discussion of the various OSI layers that follow.

> 在接下来的各种 OSI 层的详细讨论中，您会发现参考[图 7-1](#10_9781119183938-ch07.xhtml#c07-fig-0001) 和[7-2](#10-978111918938-ch07.xhtml#c 07-fig-0002)非常有用。

### The Session Layer

With data in hand from the presentation layer, the session layer opens the actual communication session with the other host. The session layer determines if the other host can in fact be reached. It also determines whether the connection between the two hosts is full duplex or half duplex. _Full duplex_ means that data can pass in both directions simultaneously. _Half duplex_ means that only one end can transmit at a time, while the other end listens for data and waits for the line to `turn around` .

> 由于来自表示层的数据在手，会话层打开与其他主机的实际通信会话。会话层确定是否实际上可以到达其他主机。它还确定两个主机之间的连接是全双工还是半双工*全双工意味着数据可以同时在两个方向上传输*半双工意味着一次只有一端可以传输，而另一端监听数据并等待线路 `掉头` 。

Some network applications can request multiple simultaneous connections to the other host. A web browser, for example, may need an HTML file, a CSS file and perhaps other content files of various sorts in order to render a single web page. The session layer establishes these additional connections and keeps track of what data is moving over which connection. The session layer also provides the highest level of error response, and may attempt to re-establish failed connections automatically.

> 一些网络应用程序可以请求到其他主机的多个同时连接。例如，web 浏览器可能需要 HTML 文件、CSS 文件以及其他各种类型的内容文件来呈现单个网页。会话层建立这些附加连接，并跟踪哪些数据在哪个连接上移动。会话层还提供最高级别的错误响应，并可以尝试自动重新建立失败的连接。

The session layer is the lowest layer in the application set. Many network applications map to all three layers in the application set, in that a single program (like a web browser or an email client) handles data selection/creation, data presentation and session management. When all requested sessions have been established, the application’s work is done. The data is handed down to the transport set, where the focus is less on the data than on getting the data where it needs to go.

> 会话层是应用程序集中的最低层。许多网络应用程序映射到应用程序集中的所有三个层，因为单个程序(如 web 浏览器或电子邮件客户端)处理数据选择/创建、数据呈现和会话管理。建立所有请求的会话后，应用程序的工作就完成了。数据被传递到传输集，在那里，人们关注的不是数据，而是获取数据所需的位置。

### The Transport Layer

On the transmit side, the transport layer’s primary tasks areto take the data handed down from the session layer by one or more processes, optionally divide it into _segments_ that are small enough to handle conveniently (a process called _segmentation_), and queue segments from these processes for transmission over the network (a process called _multiplexing_). At the receive side the transport layer reassembles segments and routes data to the appropriate receiving process.

> 在传输端，传输层的主要任务是通过一个或多个进程获取从会话层传递下来的数据，可选地**将其划分为足够小以方便处理的** segments*(一个称为 *segmentation* 的进程)，以及通过网络传输的来自这些进程的队列段(一个名为*multiplexing 的进程)。在接收端，传输层重新组合段并将数据路由到适当的接收过程。

Transport layer protocols may be categorised as either connection-oriented or connectionless. _Connection-oriented protocols_ provide a reliable, ordered stream of data between two processes, and so must generally provide a mechanism on the receive side to reorder segments that arrive out of order (which can occur if the underlying network routes segments via multiple routes with different latencies) and to detect and request retransmission of segments that have been dropped or corrupted by the underlying network. They may also provide flow-control facilities, which prevent the transmitter from sending data faster than it can be processed by the receiver. _Connectionless protocols_ are generally much simpler, delegating the handling of errors and out-of-order data upward to the application set; often they provide little more than a multiplexing function.

> 传输层协议可分为面向连接或无连接*面向连接的协议*，因此通常必须在接收侧提供一种机制，以重新排序无序到达的段(如果底层网络通过具有不同延迟的多个路由来路由段。它们还可以提供流量控制设施，防止发射机发送数据的速度超过接收机处理数据的速度\_无连接协议通常要简单得多，将错误和无序数据的处理委托给应用程序集；它们通常只提供多路复用功能。

In the modern Internet, the transport layer is implemented by TCP and UDP. TCP is connection-oriented: it divides the incoming stream of data from a process into segments, and attaches to each segment a header containing a sequence number (which is used to reorder segments at the receive end and detect missing segments) and a checksum (which is used to detect corrupted segments). Flow control is provided by using a sliding window scheme: the segment header contains a window field, which allows each end of the connection to specify how much data it can accept. Multiplexing is provided by means of source and destination port fields in the header, which (along with the source address) are used by the receiver to identify the destination process and stream for each incoming segment.

> 在现代互联网中，传输层由 TCP 和 UDP 实现。TCP 是面向连接的：它将来自进程的传入数据流划分为段，并将包含序列号(用于对接收端的段重新排序并检测缺失的段)和校验和(用于检测损坏的段)的标头附加到每个段。流控制是通过使用滑动窗口方案提供的：段头包含一个窗口字段，允许连接的每一端指定它可以接受多少数据。多路复用是通过报头中的源端口字段和目的端口字段提供的，接收器使用这些字段(连同源地址)来识别每个传入段的目的进程和流。

UDP is a much simpler connectionless protocol. Its header contains only the source and destination port fields required for multiplexing, along with a length field and a checksum; corrupted segments are silently discarded in UDP rather than being retransmitted. UDP is commonly used in applications like Voice over Internet Protocol (VoIP) in which occasional dropped segments can be tolerated but latency must be kept to a minimum.

> UDP 是一种简单得多的无连接协议。它的报头只包含多路复用所需的源和目标端口字段，以及长度字段和校验和；损坏的段在 UDP 中被默默丢弃，而不是被重新发送。UDP 通常用于 Internet 协议语音(VoIP)等应用程序中，在这些应用程序中可以容忍偶尔丢弃的段，但必须将延迟保持在最小值。

### The Network Layer

The network layer is primarily concerned with _routing_; that is, determining what path the data will take while it travels to the other host. Although the OSI model diagram in [Figure 7-1](#10_9781119183938-ch07.xhtml#c07-fig-0001) suggests that the data travels directly from the sending host to the receiving host, in WANs (including the Internet) this is not always the case. A network _path_ often includes one or more intermediate `stops` at computers along the way. These _intermediate nodes_ don’t generally unpack or attempt to interpret the data; they simply look at the destination address on each packet and send the packets on their way. The specialised hardware devices that perform this forwarding are called _routers_. Routers contain tables of network addresses and connections called a _routing table_, and can work out the route to the destination host address using the host address and the routing table. Routers are covered in more detail later in this chapter in the `[Routers and the Internet](#10_9781119183938-ch07.xhtml#c07-sec-0019)` section.

> 网络层主要关注 _routing_；也就是说，确定数据在传输到另一个主机时将采用什么路径。尽管[图 7-1](#10*9781119183938-ch07.xhtml#c07-fig-0001) 中的 OSI 模型图表明数据直接从发送主机传输到接收主机，但在广域网(包括互联网)中，情况并非总是如此。网络路径通常包括一个或多个中间 `站点` 。这些中间节点通常不会解包或试图解释数据；他们只需查看每个数据包上的目的地地址，并在途中发送数据包。执行此转发的专用硬件设备称为\_routers*。路由器包含称为*routing table 的网络地址和连接表，并可以使用主机地址和路由表计算到目标主机地址的路由。本章稍后的 `[路由器和互联网](#10_9781119183938-ch07.xhtml#c07-sec-0019)` 部分将更详细地介绍路由器。

In the context of the Internet, the network layer is where the IP does most of its work. IP takes segments passed down from the transport layer and builds them into packets with additional information needed for IP processing (refer to [Figure 7-2](#10_9781119183938-ch07.xhtml#c07-fig-0002)). The IP packet is complex, and its header format is shown in Figure 7-3. Although we can’t explain each of the header fields in detail in this book, here’s a quick summary:

> 在互联网环境中，网络层是 IP 完成大部分工作的地方。IP 获取从传输层传递下来的段，并将其构建为具有 IP 处理所需附加信息的数据包(参见[图 7-2](#10_9781119183938-ch07.xhtml#c07-fig-0002))。IP 数据包很复杂，其报头格式如图 7-3 所示。虽然我们无法在本书中详细解释每个标题字段，但这里有一个简短的总结：

- **Version:** The IP version number—for example, 4 for IPv4 and 6 for IPv6. - **IP header length:** The length of the header in 32-bit words, including options and padding. - **Type of service:** Encodes `quality-of-service` (QoS) values for IP packets. Some packets require special treatment to ensure the quality of the larger data stream. Video, for example, requires that packets be sent in order and with minimum delay (latency) for the highest quality when delivered for display. - **Total packet length:** Specifies the length of the packet in bytes. This length cannot be longer than 65,535 bytes and includes the segment passed down from the transport layer. - **Identification:** A 16-bit value given to every packet belonging to a specific message. It allows the destination host to reassemble a message from packets received out of order or mixed with packets belonging to other messages. - **Flags:** Contains three single-bit control flags that control the splitting of large packets into smaller packets. The first flag is reserved and not used. - **Fragment offset:** Part of a mechanism to identify the order of packets received out of order. - **Time to live (TTL):** Specifies the maximum number of `hops` the packet is allowed to take along its route from the source host to the destination host. Time to live is decremented by one at each hop, and when the value goes to zero the packet is assumed to have `got lost` and is discarded. (> > [!NOTE]

> -**版本：**IP 版本号，例如，IPv4 为 4，IPv6 为 6。-**IP 标头长度：**以 32 位字表示的标头长度，包括选项和填充。-**服务类型：**编码 IP 数据包的 `服务质量` (QoS)值。某些数据包需要特殊处理以确保较大数据流的质量。例如，视频要求按顺序发送数据包，并在传输显示时以最小的延迟(延迟)实现最高质量。-**数据包总长度：**指定数据包的长度(以字节为单位)。此长度不能超过 65535 字节，并且包括从传输层向下传递的段。-**标识：**属于特定消息的每个数据包的 16 位值。它允许目标主机从无序接收或与属于其他消息的数据包混合的数据包中重新组合消息。-**标志：**包含三个单位控制标志，用于控制将大数据包拆分为较小的数据包。保留第一个标志，不使用。-**片段偏移量：**标识无序接收数据包顺序的机制的一部分。-**生存时间(TTL)：**指定允许数据包沿其从源主机到目标主机的路由进行的最大 `跳数` 。生存时间在每一跳减一，当该值变为零时，假设数据包已 `丢失` 并被丢弃。(>>[！注释]

that `TTL` as used here has nothing to do with transistor-transistor logic chips.) - **Protocol:** Contains an 8-bit code specifying the protocol (generally TCP or UDP) that generated the segment handed down from the transport layer. - **Header checksum:** Part of a mechanism that detects corrupted packet headers. This checksum does not include payload data. - **Source IP address:** The 32-bit IP address (that is, its location on the Internet) of the host that generated the packet. We’ll explain IP addresses in more detail in the section `[Names vs. Addresses](#10_9781119183938-ch07.xhtml#c07-sec-0020)` later in this chapter. - **Destination IP address:** The 32-bit IP address of the host to which the packet was sent. - **Options:** A variable-length field that may contain one or more optional subfields used for security, testing and debugging. - **Data:** The payload embedded in the packet. This is generally a segment passed down from the transport layer.

> 这里使用的 `TTL` 与晶体管-晶体管逻辑芯片无关。)-**协议：**包含一个 8 位代码，指定生成传输层传递的段的协议(通常为 TCP 或 UDP)。-**标头校验和：**检测损坏的数据包标头的机制的一部分。此校验和不包括有效负载数据。-**源 IP 地址：**生成数据包的主机的 32 位 IP 地址(即其在 Internet 上的位置)。我们将在本章稍后的 `[名称与地址](#10_9781119183938-ch07.xhtml#c07-sec-0020)` 一节中更详细地解释 IP 地址。-**目标 IP 地址：**数据包发送到的主机的 32 位 IP 地址。-**选项：**一个可变长度字段，可以包含一个或多个用于安全、测试和调试的可选子字段。-**数据：**数据包中嵌入的有效负载。这通常是从传输层向下传递的段。

![[FIGURE 7-3:](#10_9781119183938-ch07.xhtml#rc07-fig-0003) The Internet Protocol (IP) Version 4 (IPv4) header format](./media/images/9781119183938-fg0703.png)

When necessary, the IP can split a segment too large to fit in a single packet into multiple packets. IP doesn’t attempt to keep packets in order or detect errors, both of which are handled by layers above the network layer. Its job is to get packets to the next stop along the route.

> 必要时，IP 可以将一个太大而无法容纳单个数据包的数据段拆分为多个数据包。IP 不试图保持数据包的有序或检测错误，这两者都由网络层之上的层处理。它的任务是把包裹送到路线上的下一站。

### The Data Link Layer

The Internet is not a single network. It’s a network of networks with defined, routable connections between them. Networks can be nested within larger networks to any reasonable level, but at some point there is a _local network_ in which all computers may connect directly to one another without the involvement of a router. The data link layer manages the flow of data over these direct connections, reorganising data coming from higher layers yet again, this time into _frames_ that are of a size and format that the hardware implementing the direct connection can handle.There are many different technologies used in connecting computers on a local network. In the case of technologies that involve communication over a shared medium, a primary function of the data link layer is to arbitrate access to this medium, via a _media access control_ (MAC) scheme. This may involve either centralised coordination or decentralised collision detection and avoidance. As discussed later in this chapter in the section `[Collision Detection and Avoidance](#10_9781119183938-ch07.xhtml#c07-sec-0013)` , modern Ethernet technologies (including Wi-Fi) take the latter approach.

> 互联网不是一个单一的网络。这是一个由网络组成的网络，它们之间有明确的、可路由的连接。网络可以嵌套在更大的网络中，达到任何合理的级别，但在某些情况下，存在一个本地网络，在该网络中，所有计算机都可以直接相互连接，而无需路由器。数据链路层管理这些直接连接上的数据流，再次将来自更高层的数据重新组织为帧，帧的大小和格式是实现直接连接的硬件可以处理的。在连接本地网络上的计算机时，使用了许多不同的技术。在涉及通过共享介质进行通信的技术的情况下，数据链路层的主要功能是通过媒体访问控制(MAC)方案仲裁对该介质的访问。这可能涉及集中协调或分散碰撞检测和避免。如本章后面 `[碰撞检测和避免](#10_9781119183938-ch07.xhtml#c07-sec-0013)` 一节所述，现代以太网技术(包括 Wi-Fi)采用后一种方法。

The data link layer may also provide local flow control, which ensures that frames are not sent so quickly that the destination host’s buffers fill up, and reliable delivery, whereby successfully received frames are acknowledged by the receiver and unacknowledged frames are retained by the transmitter and retransmitted as necessary. Ethernet does not provide either of these services; in the case of protocols that do, it is common to regard the data link layer as comprising an upper _logical link control_ sublayer, where these services reside, and a lower MAC sublayer.

> 数据链路层还可以提供本地流控制，该本地流控制确保帧不会被发送得太快以至于目的地主机的缓冲区被填满，以及可靠的传送，由此成功接收的帧被接收机确认，未确认的帧被发射机保留并在必要时重新发送。以太网不提供这两种服务；在这样的协议的情况下，通常将数据链路层视为包括这些服务所在的上层逻辑链路控制子层和下层 MAC 子层。

### The Physical Layer

The physical layer is where the network connection literally `gets physical` : the frames handed down from the data link layer are received as strings of bits, which are converted to signals in the physical _medium_. This medium is any physical process onto which data may be encoded: electrical pulses on a cable, modulated microwaves, modulated light, whatever.

> 物理层是网络连接真正 `物理化` 的地方：从数据链路层传下来的帧被接收为比特串，这些比特串被转换为物理中间层中的信号。这种介质是可以对数据进行编码的任何物理过程：电缆上的电脉冲、调制微波、调制光等等。

Most of the physical layer’s operation occurs inside electronic circuitry in a computer’s Network Interface Controller (NIC), and varies widely between standards. The transmitter generally adds a _preamble_ and delimiter bits that indicate the beginning and end of the data, and transforms each bit or group of bits in turn into a _symbol_ to transmit over the medium. The receiver uses the preamble and delimiters to detect incoming data, and decodes the symbols to recover the original bits. In choosing what symbols to transmit over the medium we must consider the need for the receiver to recover a clock from the incoming symbol stream; encoding schemes such as Manchester coding and 4B/5B (there’s more on encoding a little later in this chapter in the `[Ethernet Encoding Systems](#10_9781119183938-ch07.xhtml#c07-sec-0014)` section) guarantee that transitions will occur with a certain minimum frequency, regardless of the input data.

> 大多数物理层的操作发生在计算机网络接口控制器(NIC)的电子电路中，并且在不同标准之间有很大的差异。发射机通常会添加一个表示数据开始和结束的可扩展位和定界符位，并将每个位或一组位依次转换为一个符号，以便在媒体上传输。接收机使用前导码和定界符来检测输入数据，并解码符号以恢复原始比特。在选择要在媒体上传输的符号时，我们必须考虑接收机从输入符号流中恢复时钟的需要；曼彻斯特编码和 4B/5B 等编码方案(在本章稍后的 `[以太网编码系统](#10_9781119183938-ch07.xhtml#c07-sec-0014)` 一节中有更多关于编码的内容)保证了无论输入数据如何，转换都将以特定的最小频率发生。

Ethernet spans the data link and physical layers.The Ethernet protocols operate in the data link layer, with a standard interface to any of several Ethernet-specific physical layers, which we’ll discuss in more detail shortly. Wi-Fi is analogous to Ethernet with wireless media, in that it too spans the data link and physical layers of the OSI model, with several variations of the medium access (MAC) mechanism and physical layers. Much of the difference between Ethernet and Wi-Fi physical layers are differences of _modulation_; that is, mechanisms for imposing information on radio-frequency energy. For Ethernet, this radio-frequency energy is conducted through cabling of some sort. For Wi-Fi, the radio-frequency energy is transferred over free space using antennas.

> 以太网跨越数据链路和物理层。以太网协议在数据链路层中运行，具有到若干以太网特定物理层中的任何一个的标准接口，稍后我们将对此进行更详细的讨论。Wi-Fi 类似于具有无线媒体的以太网，因为它也跨越 OSI 模型的数据链路和物理层，具有媒体访问(MAC)机制和物理层的多种变体。以太网和 Wi-Fi 物理层之间的大部分差异是调制的差异；即在射频能量上施加信息的机制。对于以太网，这种射频能量通过某种电缆传输。对于 Wi-Fi，射频能量通过天线在自由空间传输。

## Ethernet

Like so many other things, Ethernet came out of the Xerox PARC labs in Palo Alto, California. Robert Metcalfe and David Boggs first circulated the idea within PARC in May 1973, and by November of that year the technology went online. The Ethernet concept was an outgrowth of PARC’s research into personal computing, and was intended to link PARC’s forward-looking Alto experimental workstations together at a speed of 3 megabits per second (Mbit/s). Metcalfe coined the term `[Ethernet](#10_9781119183938-ch07.xhtml#c07-sec-0010)` as an allusion to the Victorian idea of the _luminiferous aether_, which was a mysterious (and later shown to be non-existent) medium through which light and radio waves passed. Ethernet was introduced as a commercial product in 1980, and in 1983 was standardised as IEEE 802.3.

> 和其他许多东西一样，以太网来自加利福尼亚州帕洛阿尔托的 Xerox PARC 实验室。罗伯特·梅特卡夫(Robert Metcalfe)和大卫·博格斯(David Boggs)于 1973 年 5 月首次在巴黎皇家研究中心(PARC)内传播了这一想法，并于同年 11 月将该技术上线。以太网概念是 PARC 对个人计算研究的产物，旨在以每秒 3 兆比特(Mbit/s)的速度将 PARC 的前瞻性 Alto 实验工作站连接在一起。梅特卡夫创造了 `[以太网](#10_9781119183938-ch07.xhtml#c07-sec-0010)` 一词，以暗示维多利亚时代关于发光以太的想法，发光以太是一种神秘的(后来被证明是不存在的)媒介，光和无线电波通过它。以太网于 1980 年作为商业产品引入，1983 年被标准化为 IEEE 802.3。

### Thicknet and Thinnet

The earliest Ethernet implementations used a fairly stiff 10mm diameter coaxial cable. A workstation or other networked device could be connected only at certain points on the cable. The cable, in fact, bore markings every 2.5 metres to indicate where so-called `vampire taps` could be clamped onto it. The interval was calculated to minimise interference from radio-frequency reflections inside the cable. The thickness and stiffness of the cable prompted the nickname `Thicknet` , even after the formal IEEE designation 10BASE5 was given to the system. A few years later, a variation using thinner coaxial cable was introduced. The cable was only 6mm in diameter, less expensive, and a great deal more flexible. Taps could be placed at any point on the cable. The system came to be called `Thinnet` and bore the designation 10BASE2.

> 最早的以太网实现使用了相当硬的直径为 10mm 的同轴电缆。工作站或其他联网设备只能在电缆上的某些点连接。事实上，电缆每隔 2.5 米就有一个钻孔标记，以指示所谓的 `吸血鬼抽头` 可以夹在电缆上的位置。间隔的计算是为了尽量减少电缆内部射频反射的干扰。电缆的厚度和刚度促使人们有了 `Thicknet` 的绰号，甚至在正式的 IEEE 命名为 10BASE5 之后。几年后，推出了一种使用较薄同轴电缆的变体。这种电缆直径只有 6 毫米，价格更低，而且更加灵活。抽头可以放置在电缆的任何位置。该系统被称为 `Thinnet` ，并被命名为 10BASE2。

The IEEE nomenclature is still used, and it’s worth a short description here. The `10` indicates the maximum speed of data sent across the cable, in megabits. The 10-megabit value was not the design speed of the interface but the highest speed that the cable-based infrastructure could deliver. Early Ethernet implementations operated at less than half that speed. The `BASE` indicates _baseband_ transmission. In baseband transmission, the digital signal on the physical medium is a pattern of actual bits encoded as transitions from 0 volts to some arbitrary line voltage. This is in contrast to _broadband_ transmission (think cable TV), which imposes a signal on a radio-frequency carrier wave using various modulation schemes. In both modes of transmission, data travels at frequencies high enough to be considered RF. The number at the end of the designation (here, 5 or 2) indicates the maximum length of a network segment, in hundreds of metres. In 10BASE2 the `2` is an exaggeration; in practice, the segment length maxes out at 185 metres.

> IEEE 命名法仍在使用，这里值得简短描述。`10` 表示通过电缆发送数据的最大速度，单位为兆位。10 兆比特的价值不是接口的设计速度，而是基于电缆的基础设施能够提供的最高速度。早期的以太网实现的运行速度不到这个速度的一半。`BASE` 表示基带传输。在基带传输中，物理介质上的数字信号是编码为从 0 伏到某个任意线路电压的转换的实际比特的模式。这与宽带传输(比如有线电视)形成对比，后者使用各种调制方案将信号施加到射频载波上。在这两种传输模式中，数据传输的频率都足够高，足以被视为射频。名称末尾的数字(此处为 5 或 2)表示网络段的最大长度，单位为数百米。在 10BASE2 中，`2` 是夸张的；在实践中，该段的最大长度为 185 米。

### The Basic Ethernet Idea

Ethernet has evolved a great deal since its introduction in 1980. To explain its modern form, we have to begin with its original mechanism as implemented in Thicknet and Thinnet. Both forms use coaxial cable to connect some limited number of computers. All computers on the network are _peers_; that is, none have special hardware or software that is not present in all of the others. Any computer on the network can send or receive Ethernet packets to any other computer on the network.

> 自 1980 年推出以来，以太网已经有了很大的发展。要解释它的现代形式，我们必须从 Thicknet 和 Thinnet 中实现的原始机制开始。这两种形式都使用同轴电缆连接有限数量的计算机。网络上的所有计算机都是 _peers_；也就是说，没有一个具有在所有其他系统中不存在的特殊硬件或软件。网络上的任何计算机都可以向网络上的其他任何计算机发送或接收以太网数据包。

Ethernet originated the idea of a MAC address, and every device attached to the cable (which may include printers and other special-purpose devices like file servers) has a unique 48-bit numeric address, generally expressed as six groups of two hexadecimal digits. Any device with a MAC address, whatever its nature, is called a _node_. The MAC address is in fact more of an ID code than a true address. Unlike IP addresses (which are covered a little later in the `[Names vs. Addresses](#10_9781119183938-ch07.xhtml#c07-sec-0020)` section) a MAC address says nothing about _where_ its device is located on the network and is used only to tell nodes apart. As 48 bits can identify 281 _trillion_ different devices, we won’t run out of MAC addresses any time soon. That said, a few duplicates are known to have been issued by mistake, and with some equipment, including the Raspberry Pi, it’s possible to change the MAC address to mimic another device.

> 以太网起源于 MAC 地址的概念，连接到电缆的每个设备(可能包括打印机和其他专用设备，如文件服务器)都有一个唯一的 48 位数字地址，通常表示为六组两个十六进制数字。任何具有 MAC 地址的设备，无论其性质如何，都称为 _node_。MAC 地址实际上更多的是一个 ID 代码而不是一个真实地址。与 IP 地址(稍后将在 `[名称与地址](#10_9781119183938-ch07.xhtml#c07-sec-0020)` 部分中介绍)不同，MAC 地址对其设备位于网络上的位置没有任何说明，仅用于区分节点。由于 48 位可以识别 281 个不同的设备，所以我们不会很快用完 MAC 地址。也就是说，已知有几个复制品是错误发布的，并且使用一些设备，包括树莓派，可以更改 MAC 地址以模仿其他设备。

When the network is quiet, all nodes are `listening` ; that is, their NICs are ready to receive data from the cable. At any time, a node may place a packet on the cable. On baseband technologies like Ethernet, that simply means that the packet’s bits are imposed on the cable as serial changes in voltage levels, one after the other. Each NIC accumulates bits from the cable in a buffer until the complete packet is present. They then strip off the preamble and delimiters and examine the destination MAC address present in the Ethernet frame. If the destination MAC address matches the NIC’s MAC address, the frame is retained. Otherwise, the frame is ignored. See Figure 7-4.

> 当网络安静时，所有节点都在 `倾听` ；也就是说，他们的 NIC 已准备好从电缆接收数据。任何时候，节点都可以在电缆上放置数据包。在以太网等基带技术上，这仅仅意味着数据包的位会随着电压电平的串行变化而一个接一个地施加在电缆上。每个 NIC 将电缆中的位累积到缓冲区中，直到出现完整的数据包。然后，他们去除前导码和定界符，并检查以太网帧中存在的目标 MAC 地址。如果目标 MAC 地址与 NIC 的 MAC 地址匹配，则保留该帧。否则，框架将被忽略。见图 7-4。

![[FIGURE 7-4:](#10_9781119183938-ch07.xhtml#rc07-fig-0004) How Ethernet works](./media/images/9781119183938-fg0704.png)

### Collision Detection and Avoidance

There’s a certain elegance in the original Ethernet idea: _Here’s a packet; if it’s yours, keep it_. However, there was a downside to the early Ethernet’s simplicity: collisions. An Ethernet network has no central controller. Any node may place a packet on the network at any time. The nodes are aware when another node is transmitting, and they wait for the current packet to be sent (plus a short additional time period) before beginning their own transmissions. However, when the network is quiet, nothing prevents two or more nodes from beginning a transmission at the same time. This results in a _packet collision_, which generally means that all packets in the attempt are lost.

> 最初的以太网思想中有一种优雅：这里有一个数据包；如果是你的，就留着吧。然而，早期以太网的简单性有一个缺点：冲突。以太网没有中央控制器。任何节点都可以随时在网络上放置数据包。节点知道另一个节点何时在传输，并且它们在开始自己的传输之前等待发送当前分组(加上一个短的附加时间段)。然而，当网络安静时，没有什么可以阻止两个或多个节点同时开始传输。这会导致\_packet 碰撞，这通常意味着尝试中的所有数据包都会丢失。

Collisions in shared-medium Ethernet are detected in an interesting way: when two pulses from two nodes enter the cable at the same moment, the pulses `add` electrically, and the signal voltage on the cable is higher than during normal network traffic. The NICs monitor the signal voltage while transmitting, and a higher-than-normal voltage indicates a collision.

> 共享介质以太网中的冲突以一种有趣的方式被检测到：当两个节点的两个脉冲同时进入电缆时，脉冲会 `电相加` ，电缆上的信号电压高于正常网络流量。NIC 在传输时监测信号电压，高于正常值的电压表示发生了冲突。

When any transmitting node detects a collision, it ceases to send the current packet and begins sending out a _jam signal_, which is a bit pattern that disrupts the error-detection bits at the end of the frame. Other nodes on the segment will see the packet as damaged and drop it. When the network becomes quiet, those nodes that had collided wait a random period of time called a _backoff period_ (typically only a few microseconds) before attempting to transmit again. The random backoff periods are different for both nodes, making it less likely that the colliding nodes will collide again when they attempt to retransmit their jammed packets.

> 当任何发送节点检测到冲突时，它停止发送当前数据包，并开始发送\_jam 信号，这是一种扰乱帧末尾错误检测位的位模式。该段上的其他节点将看到数据包已损坏并丢弃。当网络变得安静时，发生冲突的节点会等待一段称为\_backoff period 的随机时间(通常只有几微秒)，然后再尝试传输。两个节点的随机退避周期不同，因此当冲突节点尝试重新发送其阻塞的数据包时，它们再次发生冲突的可能性较小。

The backoff period isn’t just a random delay value drawn from a fixed distribution. An algorithm called _truncated binary exponential backoff_ is used to vary the distribution of the backoff period based on collision frequency. An initial collision triggers a random backoff period of either 0 or 1 slot (where a _slot_ is the time normally taken to transmit 512 bits) before attempting retransmission. If packets collide again, a random period of between 0 and 3 slots is used; with each collision the maximum period doubles, until after ten collisions the period is between 0 and 1023 slots in length. The maximum period is then held constant at 1023 slots for a further six collisions, after which the station attempting to transmit stops trying and discards the packet. The overall effect is to slow down network activity during congested periods, `spacing out` retransmitted packets so that the network doesn’t simply grind to a halt in a storm of packet collisions.

> 退避周期不仅仅是从固定分布中得出的随机延迟值。一种称为 `运行的二进制指数回退` 的算法用于根据碰撞频率改变回退周期的分布。在尝试重传之前，初始冲突会触发 0 或 1 个时隙的随机退避周期(其中 _slot_ 是通常传输 512 位所需的时间)。如果分组再次冲突，则使用 0 到 3 个时隙之间的随机周期；每次碰撞时，最大周期加倍，直到十次碰撞后，周期长度在 0 到 1023 个时隙之间。然后，对于另外六次冲突，最大周期保持在 1023 个时隙不变，之后尝试发送的站停止尝试并丢弃分组。总体效果是在拥塞期间减缓网络活动，`间隔` 重新发送的数据包，这样网络就不会在数据包冲突的风暴中陷入停顿。

This protocol is called CSMA/CD, which stands for Carrier Sense Multiple Access with Collision Detection. `Carrier sense` is a bit of a misnomer here. Base band systems like Ethernet have no carrier, which is technically a radio frequency wave on which signals are imposed via modulation. In this case, it only means that nodes on the network have a way to determine when other stations are transmitting.

> 该协议称为 CSMA/CD，它代表带有冲突检测的载波侦听多路访问。`载波感` 在这里有点用词不当。像以太网这样的基带系统没有载波，从技术上讲，载波是一种射频波，信号通过调制施加在载波上。在这种情况下，这仅意味着网络上的节点能够确定其他站点何时在发送。

A network segment containing nodes that may transmit packets that collide is called a _collision domain_. On early Ethernet systems, the entire network was a single collision domain, which meant that throughput degraded as more nodes were added to the network and collisions became more frequent. We’ll return to collision domains a little later, in connection with Ethernet bridges and switches.

> 包含可能传输冲突数据包的节点的网段称为冲突域。在早期的以太网系统中，整个网络是一个单一的冲突域，这意味着随着更多的节点被添加到网络中，冲突变得更加频繁，吞吐量会降低。稍后我们将返回到冲突域，涉及以太网网桥和交换机。

### Ethernet Encoding Systems

Down at the physical level of the OSI model, Ethernet NICs encode the data to be transmitted by imposing a series of voltages on the network medium. The many variations of Ethernet each use a different encoding scheme; here we will briefly describe the schemes used by the 10Mbit standards (10BASE5, 10BASE2 and 10BASE-T), and the dominant 100Mbit (100BASE-TX) and 1Gbit (1000BASE-T) standards.

> 在 OSI 模型的物理层，以太网 NIC 通过在网络介质上施加一系列电压来编码要传输的数据。以太网的许多变体都使用不同的编码方案；这里，我们将简要描述 10Mbit 标准(10BASE5、10BASE2 和 10BASE-T)以及主要的 100Mbit(100BASE-TX)和 1Gbit(1000BASE-T)标准所使用的方案。

The electrical design of Ethernet requires us to choose encodings that have a very small DC component (that is, a long-term average voltage of close to zero), regardless of the data being transmitted. Signals from the NIC are inductively coupled onto the shared medium via transformers, which act as high-pass filters; if a DC component were present then this filtering would distort the signal, making it hard for a receiver to accurately recover the transmitted data. An encoding should also be _self-clocking_, possessing sufficiently frequent level transitions to allow the receiver to infer a clock with which to sample the signal. There are obvious parallels here with the encodings used to store data on magnetic media, which is described in [Chapter 6](#09_9781119183938-ch06.xhtml).

> 以太网的电气设计要求我们选择具有非常小的 DC 分量(即，接近零的长期平均电压)的编码，而不考虑传输的数据。来自 NIC 的信号通过充当高通滤波器的变压器感应耦合到共享介质上；如果存在 DC 分量，则这种滤波将使信号失真，使接收机难以准确地恢复传输的数据。编码也应该是 _self-clocking_，具有足够频繁的电平转换，以允许接收机推断用于采样信号的时钟。这里与用于在磁性介质上存储数据的编码有明显的相似之处，这在[第 6 章](#09_9781119183938-ch06.xhtml)中有所描述。

10BASE5 and 10BASE2 (along with 10BASE-T; see the `[10BASE-T and Twisted Pair Cabling](#10_9781119183938-ch07.xhtml#c07-sec-0016)` section later in this chapter) encode bits via _Manchester encoding_, shown in Figure 7-5. Each data bit is encoded in one clock cycle, with a transition at the centre of the cycle encoding the bit: a transition from negative to positive is considered a 1-bit, and a transition from positive to negative is considered a 0-bit. If necessary, an extra transition is inserted at the start of a cycle, to put the line into the correct state to encode the bit. The arrows in the figure show you which transitions encode data and which directions the transitions take.

> 10BASE5 和 10BASE2(以及 10BASE-T；参见本章后面的 `[10BASE-T 和双绞线布线](#10_9781119183938-ch07.xhtml#c07-sec-0016)` 部分)通过\_Manchester 编码对位进行编码，如图 7-5 所示。每个数据位在一个时钟周期中被编码，在周期的中心有一个转换对该位进行编码：从负到正的转换被认为是 1 位，从正到负的转换被看作是 0 位。如有必要，在循环开始时插入一个额外的转换，以使行进入正确的状态以对位进行编码。图中的箭头显示了哪些转换编码数据，以及转换采用的方向。

![[FIGURE 7-5:](#10_9781119183938-ch07.xhtml#rc07-fig-0005) Manchester encoding](./media/images/9781119183938-fg0705.png)

Manchester encoding trivially meets our requirements for being self-clocking (as every bit has at least one transition) and having 0 DC component (as half of each bit period is spent at each voltage level). These properties come at a price, however: the extra transitions introduced by the encoding increase the bandwidth of the signal to around 20MHz. To go beyond 10 Mbps with affordable cabling, it was necessary to devise more efficient encoding schemes.

> 曼彻斯特编码基本上满足了我们的自时钟(因为每个比特至少有一个转换)和 0 DC 分量(因为每个位周期的一半都在每个电压电平上)的要求。然而，这些特性是有代价的：编码引入的额外跃迁将信号带宽增加到 20MHz 左右。为了通过经济实惠的电缆传输速度超过 10Mbps，有必要设计更高效的编码方案。

One such scheme, used by 100BASE-TX Fast Ethernet,is _4B/5B_, so named because it encodes each four data bits into five bits for transmission. The 5-bit encoded group is called a _symbol_. The encoding is performed using a simple static dictionary, shown in Table 7-1, in which each unique 4-bit group translates to a unique 5-bit symbol. The code used in 4B/5B was designed to provide at least a single level transition for every four bits of data. This ensures that the transmitted bitstream is self-clocking, even in the presence of long strings of 0- or 1-bits.

> 100BASE-TX 快速以太网使用的一种这样的方案是 _4B/5B_，之所以命名是因为它将每四个数据位编码为五个位进行传输。5 位编码组称为 _symbol_。使用表 7-1 所示的简单静态字典进行编码，其中每个唯一的 4 位组转换为唯一的 5 位符号。4B/5B 中使用的代码被设计为每四位数据至少提供一个单级转换。这确保了传输的比特流是自计时的，即使在存在 0 位或 1 位的长串的情况下也是如此。

[Table 7-1](#10_9781119183938-ch07.xhtml#rc07-tbl-0001) 4B/5B Encoding

**Data word** **4B/5B code word** --------------- --------------------- 0 0 0 0 1 1 1 1 0 0 0 0 1 0 1 0 0 1 0 0 1 0 1 0 1 0 0 0 0 1 1 1 0 1 0 1 0 1 0 0 0 1 0 1 0 0 1 0 1 0 1 0 1 1 0 1 1 0 0 1 1 1 0 0 1 1 1 0 1 1 1 1 1 0 0 0 1 0 0 1 0 1 0 0 1 1 0 0 1 1 1 0 1 0 1 0 1 1 0 1 0 1 1 1 0 1 1 1 1 1 0 0 1 1 0 1 0 1 1 0 1 1 1 0 1 1 1 1 1 0 1 1 1 0 0 1 1 1 1 1 1 1 0 1

Given a data rate of 100Mbit/s, applying 4B/5B coding results in a line rate of 125Mbit/s. Rather than transmitting the encoded bits directly, however, 100BASE-TX applies a second encoding technique, borrowed from an earlier standard called FDDI (Fiber Distributed Data Interface, used in fibre-optics connections). This second encoding technical is MLT-3 (multi-level transmit using 3 levels). Given three voltages -V, 0 and +V, MLT-3 encodes a 0-bit by continuing to transmit the current voltage, and a 1-bit by moving to the next voltage in the sequence (0, +V, 0, -V). The maximum fundamental frequency of the resulting signal is 31.25MHz, as it takes a minimum of four bit periods to cycle through the sequence, allowing us to use cost-effective Category 5 cabling, which is covered in more detail shortly. MLT-3 encoding is shown in Figure 7-6.

> 给定 100Mbit/s 的数据速率，应用 4B/5B 编码可获得 125Mbit/s 的线速率。然而，100BASE-TX 并没有直接传输编码比特，而是采用了第二种编码技术，该技术借鉴了早期的 FDDI(光纤分布式数据接口，用于光纤连接)标准。第二种编码技术是 MLT-3(使用 3 级的多级传输)。给定三个电压-V、0 和 +V，MLT-3 通过继续传输当前电压来编码 0 位，通过移动到序列中的下一个电压(0、+V、0、-V)来编码 1 位。产生的信号的最大基频为 31.25MHz，因为在序列中循环至少需要四个比特周期，因此我们可以使用成本效益高的 5 类布线，稍后将对此进行详细介绍。MLT-3 编码如图 7-6 所示。

![[FIGURE 7-6:](#10_9781119183938-ch07.xhtml#rc07-fig-0006) MLT-3 encoding](./media/images/9781119183938-fg0706.png)

While the combination of 4B/5B and MLT-3 coding satisfies the self-clocking requirement, it does not ensure zero DC balance. A partial solution is provided by applying a reversible _scrambling_ procedure to the 4B/5B-encoded bitstream. This involves applying the XOR logical operation between the bitstream and a pseudorandom bit sequence and ensures that, in almost all cases, the MLT-3 output spends 25% of its time in the -V state and 25% in the +V state. Given that the scrambler sequence is known and fixed, it is of course possible to carefully construct a bitstream that cancels out the scrambling, resulting in significant DC bias. Such _killer packets_ may be assumed to be rare in practice; nonetheless, most NICs contain circuitry that will detect and compensate for DC offset if it occurs.

> 虽然 4B/5B 和 MLT-3 编码的组合满足自时钟要求，但它不能确保零 DC 平衡。通过对 4B/5B 编码比特流应用可逆\_。这涉及在比特流和伪随机比特序列之间应用 XOR 逻辑运算，并确保在几乎所有情况下，MLT-3 输出在-V 状态下花费 25% 的时间，在 +V 状态下花费 25% 的时间。由于加扰器序列是已知的且固定的，因此当然可以仔细构造一个抵消加扰的比特流，从而导致显著的 DC 偏置。这种 `杀手包` 在实践中可能是罕见的；尽管如此，大多数 NIC 都包含检测和补偿直流偏移的电路。

100BASE-TX makes use of two pairs of conductors, one carrying data in each direction. Figure 7-7 shows the 100BASE-TX encoding and decoding scheme in its entirety.

> 100BASE-TX 使用两对导线，每个方向一对导线传输数据。图 7-7 显示了整个 100BASE-TX 编码和解码方案。

![[FIGURE 7-7:](#10_9781119183938-ch07.xhtml#rc07-fig-0007) 100Base-TX encoding and decoding](./media/images/9781119183938-fg0707.png)

The 1000BASE-T standard provides data rates of 1 gigabit per second while maintaining the same symbol rate as 100BASE-TX (125Msymbols/s). It accomplishes this by using four pairs of conductors (versus one for 100BASE-TX), and by using a denser 5-level amplitude modulation (versus three levels for 100BASE-TX). There are 5^4 = 625 possible symbols, so the theoretical raw bit rate is 125Msymbols/s log2(625) = 1160 Mbps. The `spare` coding capacity is used to implement a low-density forward error correction scheme known as _trellis coding,_ the exact details of which are beyond the scope of this book. This approach effectively compensates for the increase in raw error rate caused by the denser amplitude modulation.

> 1000BASE-T 标准提供每秒 1 千兆比特的数据速率，同时保持与 100BASE-TX 相同的符号速率(125M 符号/秒)。它通过使用四对导体(100BASE-TX 为一对)和更密集的 5 电平幅度调制(100BASE-T 为三电平)来实现这一点。有 5^4=625 个可能的符号，因此理论上的原始比特率为 125Msymbols/slog2(625)=1160 Mbps。`备用` 编码容量用于实现一种称为\_trellis 编码的低密度前向纠错方案，其确切细节超出了本书的范围。这种方法有效地补偿了由密集幅度调制引起的原始误差率的增加。

In contrast with 100BASE-TX, which implements full-duplex communication using a dedicated pair of conductors for each direction, 1000BASE-T supports simultaneous bidirectional transmission over the same set of conductors. To accomplish this, each receiver subtracts the (known) output of the local transmitter from the voltage observed on the line, leaving only the incoming signal (if any).

> 与 100BASE-TX 相比，1000BASE-T 支持在同一组导线上同时进行双向传输，100BASE-TX 在每个方向上使用一对专用导线实现全双工通信。为了实现这一点，每个接收机从线路上观察到的电压中减去本地发射机的(已知)输出，只留下输入信号(如果有的话)。

### PAM-5 Encoding

After a data stream has been encoded, it must be coupled to the Ethernet medium. This is generally done through small transformers in the NIC. The encoded data stream is a series of digital pulses that exist at one or the other of two voltage levels. When a digital signal is encoded between two voltage levels in this way, it’s called _binary signalling_. Typically, a positive voltage level represents a 1-bit and a negative voltage represents a 0-bit.

> 数据流编码后，必须将其耦合到以太网介质。这通常通过 NIC 中的小型变压器完成。编码数据流是以两个电压电平中的一个或另一个存在的一系列数字脉冲。当数字信号以这种方式在两个电压电平之间编码时，称为二进制信号。典型地，正电压电平表示 1 位，负电压表示 0 位。

Higher data rates, like those of Gigabit Ethernet, require denser encoding. The system widely used today is five-level _pulse amplitude modulation_, abbreviated to PAM-5. PAM-5 encodes 2 bits per pulse by varying the signal voltage over five levels rather than only two. Two of the five levels are positive voltages, two are negative voltages and the fifth is 0 voltage. When information is encoded as a varying voltage level in a signal, it’s called _amplitude modulation_. PAM-5 varies the amplitude of the pulses that make up the encoded data stream, hence the name pulse amplitude modulation. Schemes like this are called _multi-level signalling_, because more than two voltage levels are used to encode data.

> 更高的数据速率，如千兆以太网，需要更密集的编码。目前广泛使用的系统是五电平脉冲幅度调制，简称 PAM-5。PAM-5 通过在五个电平上而不是仅两个电平上改变信号电压来编码每个脉冲 2 位。五个电平中的两个是正电压，两个是负电压，第五个是 0 电压。当信息被编码为信号中变化的电压电平时，称为振幅调制。PAM-5 改变构成编码数据流的脉冲的幅度，因此称为脉冲幅度调制。这样的方案被称为多级信号，因为两个以上的电压电平用于编码数据。

We’ve drawn a PAM-5 data stream in Figure 7-8, which is a graph of pulse amplitude over time. The grey bars are pulses, and the wide black line is the amplitude for the stream of pulses. Each pulse is considered a symbol, because one pulse encodes two bits. The 0V level does not encode any particular value, and its primary purpose is to allow the receiver to extract a clock signal from the data, and to facilitate error correction using a technology called _forward error correction_ (FEC). The details of FEC as used in Gigabit Ethernet are beyond the scope of this book. As a broad overview, though, additional bits are added to a data stream, which allows the receiver to identify and correct a limited number of errors without reversing the line (hence `forward` ) to request retransmission of data. Forward error correction has much in common with error-correcting code (ECC) memory, which is covered in [Chapter 3](#06_9781119183938-ch03.xhtml).

> 我们在图 7-8 中绘制了 PAM-5 数据流，这是脉冲幅度随时间变化的曲线图。灰条是脉冲，宽黑线是脉冲流的振幅。每个脉冲被认为是一个符号，因为一个脉冲编码两个比特。0V 电平不编码任何特定值，其主要目的是允许接收器从数据中提取时钟信号，并使用称为 `向前纠错` (FEC)的技术促进纠错。千兆以太网中使用的 FEC 的细节超出了本书的范围。然而，作为一个广泛的概述，在数据流中添加了额外的比特，这允许接收机识别和纠正有限数量的错误，而无需反转线路(因此 `转发` )以请求重新传输数据。前向纠错与纠错码(ECC)存储器有很多共同之处，这在[第 3 章](#06_9781119183938-ch03.xhtml)中有介绍。

![[FIGURE 7-8:](#10_9781119183938-ch07.xhtml#rc07-fig-0008) PAM-5 encoding](./media/images/9781119183938-fg0708.png)

The actual graph of a PAM-5 waveform is not as `clean` as the graph in [Figure 7-8](#10_9781119183938-ch07.xhtml#c07-fig-0008), especially at gigabit speeds. Noise gets into the waveform, and extracting symbols from the waveform is a serious challenge to the electronics on the receiver side.

> PAM-5 波形的实际图形不像[图 7-8](#10_9781119183938-ch07.xhtml#c07-fig-0008) 中的图形那样 `干净` ，特别是在千兆比特速度下。噪声进入波形，从波形中提取符号对接收器侧的电子设备是一个严重的挑战。

### 10BASE-T and Twisted-Pair Cabling

The early Ethernet implementations based on coaxial cable had a number of problems, collisions being the least of it. 10BASE2, in particular, was vulnerable to mechanical connection issues. Cables had a coaxial connector on each end, and at each node, two cables came together in a coaxial `T` connector; these connectors were inexpensive, and even a comparatively gentle tug on a cable was sometimes enough to interrupt the continuity of the bus. Once the bus had been split in two in this way, radio-frequency signal reflections from the break point would prevent communication even between hosts on the same half. In addition, there were at least twice as many vulnerable connections as there were nodes on the network.

> 早期基于同轴电缆的以太网实现有很多问题，其中冲突最少。特别是 10BASE2，容易受到机械连接问题的影响。电缆的每一端都有一个同轴连接器，在每个节点上，两根电缆连接在一个同轴 `T` 形连接器中；这些连接器价格低廉，即使相对温和地拉动电缆有时也足以中断总线的连续性。一旦总线以这种方式一分为二，来自断点的射频信号反射将阻止同一半主机之间的通信。此外，易受攻击的连接数量至少是网络上节点数量的两倍。

> ===

In the late 1980s a new variation of Ethernet appeared: 10BASE-T. The `T` stood for _twisted pair_, which is a way of wrapping two thin (usually 24-gauge) copper wires around one another to reduce interference from external noises sources. To transmit a bit on a coaxial cable, the transmitting NIC applies a voltage to the centre conductor of the cable, with the outer cable shield acting as the ground return path; this is referred to as _single-ended_ signalling. To do the same on a twisted-pair cable, the transmitting NIC applies two different voltages to the two conductors: zeros and ones are represented by positive and negative _differences_, rather than by absolute voltages, so this is referred to as _differential_ signalling. The receiving NIC can extract the encoded data using a differential amplifier, which converts the voltage difference between its inputs into a single output.

> 20 世纪 80 年代末，以太网出现了一种新的变体：10BASE-T。`T` 代表扭绞对，这是一种将两根细铜线(通常为 24 号)缠绕在一起的方式，以减少来自外部噪声源的干扰。为了在同轴电缆上传输比特，传输 NIC 向电缆的中心导体施加电压，外部电缆屏蔽充当接地返回路径；这被称为英语结束信令。为了在双绞线上实现同样的操作，传输 NIC 向两个导体施加两种不同的电压：0 和 1 由正负差表示，而不是由绝对电压表示，因此这被称为差分信号。接收 NIC 可以使用差分放大器提取编码数据，该放大器将其输入之间的电压差转换为单个输出。

Differential signals travelling over tightly twisted pairs of wires have low electromagnetic emissions (because emissions from one wire will be very nearly cancelled by emissions from the other) and good immunity to interference (because interference will create almost the same voltage change on both wires, without affecting the difference between them). Figure 7-9 illustrates the way differential transmission schemes using balanced lines operate.

> **通过紧密双绞线传输的差分信号具有低电磁辐射(因为一根电线的辐射几乎被另一根电线所抵消)和良好的抗干扰性(因为干扰会在两根电线上产生几乎相同的电压变化，而不会影响它们之间的差异)**。图 7-9 说明了使用平衡线路的差分传输方案的运行方式。

![[FIGURE 7-9:](#10_9781119183938-ch07.xhtml#rc07-fig-0009) Balanced transmission lines for data](./media/images/9781119183938-fg0709.png)

A 10BASE-T cable consists of four twisted pairs in one jacket, terminated in 8-conductor modular plugs. A cable of that construction that has been tested to a transmission speed of 100MHz is considered _Category 5_ (informally `cat 5` ), as defined in the ANSI/EIA-568 cabling standard. Category 5 cables can be used for other sorts of signals, including both audio and video, but Ethernet is now the primary use for Category 5 and its plug-compatible but faster successors, Category 5E and Category 6.

> 10BASE-T 电缆由一个护套中的四个双绞线组成，端接在 8 芯模块插头中。根据 ANSI/EIA-568 布线标准的定义，已测试传输速度为 100MHz 的该结构电缆被视为类别 5\_(非正式地称为 `类别 5` )。第 5 类电缆可用于其他类型的信号，包括音频和视频，但以太网现在是第 5 类及其插头兼容但速度更快的后续产品(第 5E 类和第 6 类)的主要用途。

Why four twisted pairs in one jacket? As described earlier, the dominant Gigabit Ethernet technology, 1000BASE-T, achieves its greater throughput in part by splitting a single data stream into four parallel bidirectional streams, each one with its own twisted pair in a Category 5, 5E, or 6 cable. Slower Ethernet technologies may not use all four pairs, and some, like 10BASE-T, use one unidirectional pair for transmit and one for receive.

> 为什么一件夹克里有四对双绞线？如前所述，占主导地位的千兆以太网技术 1000BASE-T 部分通过将单个数据流分成四个并行的双向流来实现更大的吞吐量，每个双向流在 5、5E 或 6 类电缆中都有自己的双绞线。较慢的以太网技术可能不会使用所有四对，有些技术(如 10BASE-T)使用一对单向传输线和一对单向接收线。

### From Bus Topology to Star Topology

Category 5 cabling was not the only change in going from 10BASE2 to 10BASE-T. 10BASE-T networks are a whole different _shape_. The way that nodes are connected in a network is called the network _topology_. 10BASE5 and 10BASE2 networks used _bus topology_, in which all nodes are simply daisy chained along a single stretch of coaxial cable. By contrast, 10BASE-T networks use _star topology_, in which all nodes connect to a central _network hub_. See Figure 7-10 for a comparison of the two topologies.

> 5 类布线并不是从 10BASE2 到 10BASE-T 的唯一变化。10BASE-T 网络是完全不同的形状。节点在网络中的连接方式称为 network*topology*。10BASE5 和 10BASE2 网络使用了总线拓扑，其中所有节点都简单地沿着一段同轴电缆菊花链连接。相比之下，10BASE-T 网络使用\_star 拓扑结构，其中所有节点都连接到一个中央网络集线器。两种拓扑的比较见图 7-10。

![[FIGURE 7-10:](#10_9781119183938-ch07.xhtml#rc07-fig-0010) Bus topology versus star topology](./media/images/9781119183938-fg0710.png)

The central hub was necessary because 10BASE-T networks use separate differential pairs for transmit and receive. This allowed _full duplex_ operation, by which a node may send and receive data simultaneously. However, it also required that the transmit wires of each node be connected to the receive wires of every other node. This was done at the hub. Early Ethernet hubs were just passive connectors, in which the appropriate wires from each node were connected to the appropriate wires from all the other nodes. Later hubs reduced _crosstalk_ (signal interference between nearby wires due to inductive and capacitive coupling) and _shot noise_ (static from motors, relays and similar electrical equipment) by adding digital amplifiers between each leg of the hub and the central connections. This led to fewer damaged packets and improved overall network throughput. Such active hubs were originally called _repeater hubs_ or _repeaters_ (because the amplifiers took a weak or noisy signal and retransmitted it as a stronger and cleaner signal) but today are known simply as network hubs or Ethernet hubs. Purely passive hubs are no longer used.

> 中央集线器是必要的，因为 10BASE-T 网络使用单独的差分对进行传输和接收。这允许全双工操作，通过该操作，节点可以同时发送和接收数据。然而，它还要求每个节点的发射线连接到每个其他节点的接收线。这是在中心完成的。早期的以太网集线器只是无源连接器，其中来自每个节点的适当导线连接到来自所有其他节点的相应导线。后来的集线器通过在集线器的每个支路和中央连接之间添加数字放大器，减少了串扰(由于电感和电容耦合导致的附近电线之间的信号干扰)和热噪声(来自电机、继电器和类似电气设备的静电)。这减少了损坏的数据包，提高了整体网络吞吐量。这种有源集线器最初被称为 _repeaterhubs_ 或 _repeaters_(因为放大器接收微弱或有噪声的信号，并将其作为更强和更干净的信号重新传输)，但今天被简单地称为网络集线器或以太网集线器。不再使用纯被动集线器。

In truth, hubs aren’t quite as simple as amplifiers that strengthen and `clean up` packets. A hub used as a link between two network segments isolates the segments from one another with respect to cabling disruptions like bad coaxial connectors.

> 事实上，集线器并不像放大器那样简单，可以加强和 `清理` 数据包。用作两个网段之间链路的集线器将网段彼此隔离，以防电缆中断，如同轴连接器损坏。

As good as 10BASE-T cabling and hubs were, the system still connected all nodes to all other nodes as a single collision domain. This meant that packet collisions continued to be an issue with hubs, and collision detection schemes had to be present to manage them.

> 与 10BASE-T 电缆和集线器一样，该系统仍然将所有节点连接到所有其他节点，作为一个冲突域。这意味着数据包冲突仍然是集线器的一个问题，必须有冲突检测方案来管理它们。

> [!NOTE]
> that hubs are layer 1 devices, and at the physical layer what a hub does is mostly amplify and thus `clean up` the signals passing through the hub. To do more than that, you need more than a hub.

### Switched Ethernet

An elegant solution to Ethernet packet collision overhead didn’t appear until 1990. The firm Kalpana (later acquired by Cisco) invented a _switching hub_ for Ethernet networks. Switching hubs occupy the same position in star topology networks as conventional hubs do, in that all nodes on a star network are connected to one port on the switching hub at the network’s centre. However, in contrast to conventional hubs, switching hubs operate at layer 2 on the OSI reference model, having some awareness of the data that is being passed through them.Today, such devices are simply called _network switches_, and Ethernet networks could not be as fast or reliable as they are without them.

> 直到 1990 年，以太网数据包冲突开销才出现了一个优雅的解决方案。Kalpana 公司(后来被思科收购)发明了一种用于以太网的交换集线器。交换集线器在星形拓扑网络中的位置与传统集线器相同，因为星形网络上的所有节点都连接到网络中心交换集线器上的一个端口。然而，与传统集线器不同的是，交换集线器在 OSI 参考模型的第 2 层运行，对通过它们传输的数据有一定的了解。今天，这种设备被简单地称为 _network switches_，如果没有它们，以太网网络就不可能像现在这样快速或可靠。

Network switch technology grew out of an earlier concept called a _network bridge_. The first network bridges were two-port devices that allowed two separate network segments to communicate. The bridge is necessary if the two segments use different technologies (say, 10BASE2 and 10BASE-T) or the same technology operating at different speeds, or if the size of the entire network exceeds the maximum allowable segment size for the technology in question (185m in the case of 10BASE2). A network bridge receives and buffers packets from one segment, and retransmits them on the other when that segment’s medium is quiet; in doing so it prevents the two bridged network segments from becoming a single collision domain. Collisions do not propagate through bridges, allowing each of the two bridged network segments to have more nodes than a single segment could handle.

> 网络交换技术起源于一个早期的概念，称为 `网络桥` 。第一个网桥是允许两个独立网段通信的两个端口设备。如果两个网段使用不同的技术(例如，10BASE2 和 10BASE-T)或相同的技术以不同的速度运行，或者如果整个网络的大小超过了相关技术的最大允许网段大小(10BASE2 为 185m)，则需要网桥。网桥接收并缓冲来自一个段的数据包，并在该段的介质安静时在另一个段上重新发送数据包；这样做可以防止两个桥接的网络段变成单个冲突域。冲突不会通过网桥传播，这使得两个桥接的网段中的每一个都具有比单个网段所能处理的更多的节点。

Very simply put, a network switch creates a momentary dedicated connection between two and only two network nodes. When one node wishes to send a packet to another node connected to a switch, the switch creates the connection for just long enough to allow the packet to pass between them. Because during that brief moment the nodes are on what amounts to an isolated, two-node network, collisions are impossible, and no time or bandwidth is spent on collision detection and retransmission. Other nodes on the network do not see packets passed between the two nodes connected through the switch. Network switches for home use have four, five, or perhaps eight ports. Switches used in corporate environments may have hundreds. Figure 7-11 shows a network switch.

> 简单地说，网络交换机在两个且仅两个网络节点之间创建一个瞬时专用连接。当一个节点希望向连接到交换机的另一个节点发送数据包时，交换机创建连接的时间刚好足够长，以允许数据包在它们之间传递。因为在这一短暂的时刻，节点处于相当于一个孤立的双节点网络上，所以冲突是不可能的，并且没有时间或带宽用于冲突检测和重传。网络上的其他节点看不到通过交换机连接的两个节点之间传递的数据包。家用网络交换机有四个、五个或八个端口。公司环境中使用的交换机可能有数百个。图 7-11 显示了网络交换机。

---

> [!NOTE]

We need to be very clear that [Figure 7-11](#10_9781119183938-ch07.xhtml#c07-fig-0011) is a metaphor: network switches are fully electronic, and there are no mechanical switch contacts inside them. Modern switches are capable of sustaining multiple simultaneous connections between many different pairs of nodes, so that more than a single packet can pass through the switch’s _crossbar_ (the matrix of electrical switching logic that connects ports to one another) at any given time.

> 我们需要非常清楚的是，[图 7-11](#10*9781119183938-ch07.xhtml#c07-fig-0011) 是一个隐喻：网络交换机是完全电子化的，内部没有机械开关触点。现代交换机能够在许多不同的节点对之间保持多个同时连接，因此在任何给定的时间都可以有不止一个数据包通过交换机的 crossbar(将端口彼此连接的电交换逻辑矩阵)。

![[FIGURE 7-11:](#10_9781119183938-ch07.xhtml#rc07-fig-0011) How network switches work](./media/images/9781119183938-fg0711.png)

To do their job, network switches must contain considerably more intelligence than hubs. A switch maintains a table of MAC addresses for all the nodes connected to its ports; using this table, it can instantly associate the MAC address of an incoming packet with an outgoing port and thus make a temporary connection between two hosts. Building and maintaining the table is done in two ways:

> 为了完成其任务，**网络交换机必须包含比集线器多得多的智能。交换机维护连接到其端口的所有节点的 MAC 地址表；使用此表，它可以立即将传入数据包的 MAC 地址与传出端口相关联，从而在两个主机之间建立临时连接**。构建和维护表格有两种方式：

- By broadcasting a packet to the reserved MAC address `FF:FF:FF:FF:FF:FF`, the switch can request that all nodes reachable through the switch’s ports respond with their MAC addresses. Some computers also broadcast their own MAC addresses to the network when they are powered up or rebooted.
- By listening to both the sending and receiving addresses in all packets that it handles, a switch can verify the MAC addresses reachable on any of its ports.

> - 通过将数据包广播到保留的 MAC 地址 `FF:FF:FF:FF:FF:FF `，交换机可以请求通过交换机端口可到达的所有节点用其 MAC 地址进行响应。一些计算机在通电或重新启动时也会向网络广播自己的 MAC 地址。
> - 通过监听它处理的所有数据包中的发送和接收地址，交换机可以验证其任何端口上可访问的 MAC 地址。

The simplest possible switch would buffer incoming packets in memory until it receives an entire packet and verifies that it is complete and not corrupt. Only then does it begin forwarding the packet to the destination host. This is called _store-and-forward_ switching. To improve throughput, a technology called _cut-through_ switching was developed. In cut-through switching, the switch inspects an incoming packet only until it has the complete destination address, at which time (if no other transmission to the destination is in progress) it immediately begins forwarding the packet to the destination host. Without buffering overhead, this gets the packet to the destination in the shortest possible time. However, cut-through switching does not verify that packets are complete, and will forward incomplete or damaged packets. The destination host will detect the damaged packet and discard it. If this happens often enough, the throughput benefits of cut-through switching will be lost.

> 最简单的交换机将在内存中缓冲传入的数据包，直到它接收到一个完整的数据包并验证它是否完整且未损坏。只有这样，它才开始将数据包转发到目标主机。这被称为 `前向切换` 。为了提高吞吐量，开发了一种称为 `直通交换` 的技术。在直通交换中，交换机只检查传入的数据包，直到它具有完整的目的地地址，此时(如果没有向目的地进行其他传输)，它立即开始将数据包转发到目的地主机。在没有缓冲开销的情况下，这将在尽可能短的时间内将数据包发送到目的地。然而，直通切换不会验证数据包是否完整，并且会转发不完整或损坏的数据包。目标主机将检测到损坏的数据包并将其丢弃。如果这种情况经常发生，则直通交换的吞吐量优势将丢失。

Using switches and hubs isn’t an either/or situation. They can be freely mixed in Ethernet networks, as shown in Figure 7-12. In the figure, four nodes are connected directly to the Ethernet switch. A hub connecting three additional nodes is also connected to the switch. The key issue in using hubs is that collisions again become possible on the leg of the network connected by a hub. The highlighting in [Figure 7-12](#10_9781119183938-ch07.xhtml#c07-fig-0012) shows the four-node collision domain within the network. The switch can create a dedicated connection between node 003 and the hub, but the hub connects nodes 004, 005 and 006 in a way such that the switch cannot reach any of the three individually. If nodes 004 and 006 begin transmitting a packet simultaneously, the packets will collide, and all the usual collision overhead will apply.

> 使用交换机和集线器不是非此即彼的情况。它们可以在以太网中自由混合，如图 7-12 所示。在图中，四个节点直接连接到以太网交换机。连接三个附加节点的集线器也连接到交换机。使用集线器的关键问题是，在由集线器连接的网络的支路上再次可能发生冲突。[图 7-12](#10_9781119183938-ch07.xhtml#c07-fig-0012) 中的突出显示显示了网络中的四节点冲突域。交换机可以在节点 003 和集线器之间创建专用连接，但是集线器以这样的方式连接节点 004、005 和 006，使得交换机不能单独到达这三个节点中的任何一个。如果节点 004 和 006 开始同时发送数据包，则数据包将发生冲突，并且将应用所有通常的冲突开销。

![[FIGURE 7-12:](#10_9781119183938-ch07.xhtml#rc07-fig-0012) Mixing switches and hubs](./media/images/9781119183938-fg0712.png)

The situation illustrated in [Figure 7-12](#10_9781119183938-ch07.xhtml#c07-fig-0012) comes up often in wireless networking because wireless access points (APs) are conceptually closer to hubs than to switches.

> [图 7-12](#10_9781119183938-ch07.xhtml#c07-fig-0012) 中所示的情况经常出现在无线网络中，因为无线接入点(AP)在概念上更接近集线器而不是交换机。

> [!note]
> 这里有 AP 的概念？
> Access Point

## Routers and the Internet

One way to think about LANs versus WANs is that LANs are networks of computers, and WANs are networks of networks. It wasn’t that way in the very beginning, when WANs primarily connected large, lonely computers at one company or university with large, lonely computers at other companies and universities. Today, of course, no organisation ever has just one computer, and this is often the case for individuals at home too. No matter how simple or inexpensive, every computer, smartphone or tablet has a network port of some kind, be it wired, wireless or both. With LANs everywhere, the next step is to allow one LAN to network with other LANs. This is what the Internet was designed to do. And although Internet mechanisms go well beyond the stated topic of this chapter (Ethernet) the Internet protocol suite is very much involved in even the smallest local-area network—a network of one device—that connects to the Internet.

> 考虑局域网与广域网的一种方式是，**局域网是计算机网络，广域网是网络网络**。在一开始，当广域网主要将一家公司或大学的大型孤独计算机与其他公司和大学的大型孤立计算机连接起来时，情况并非如此。当然，今天，没有一个组织只有一台电脑，家里的个人也是如此。无论多么简单或廉价，每台电脑、智能手机或平板电脑都有某种网络端口，无论是有线、无线还是两者兼而有之。由于局域网无处不在，下一步是允许一个局域网与其他局域网联网。这就是互联网的设计目的。尽管互联网机制远远超出了本章所述的主题(以太网)，但即使是最小的局域网(由一个设备连接到互联网的网络)，互联网协议套件也非常重要。

### Names vs. Addresses

On a LAN, a node is identified by its MAC address. MAC addresses are (ideally) unique, so theoretically a node should be able to contact another node on the other side of the world by placing the MAC address of the faraway node in a packet. This doesn’t work for an obvious reason: a MAC address contains no information about where its node actually _is_. As a metaphor, think of people at a meeting around a conference table. Everyone can see everyone else around the table, and when anyone talks, everyone can hear. That’s how LANs work. At the same time, other people are sitting around other conference tables in other buildings, talking in the same local way. How can you get two such meetings to talk to one another? If both conference tables have speaker-phones, one table’s phone can call the other, and the two conference tables will be in communication.

> 在 LAN 上，节点由其 MAC 地址标识。MAC 地址(理想情况下)是唯一的，因此理论上，一个节点应该能够通过将远处节点的 MAC 地址放在数据包中来联系世界另一端的另一个节点。这不起作用，原因很明显：MAC 地址不包含其节点实际 _is_ 的位置信息。作为一个比喻，想象一下会议桌旁的人们。每个人都可以看到桌子周围的其他人，当任何人讲话时，每个人都能听到。局域网就是这样工作的。与此同时，其他人坐在其他大楼的其他会议桌旁，用同样的当地方式交谈。你怎么能让两个这样的会议互相交谈呢？如果两张会议桌都有扬声器电话，一张桌子的电话可以呼叫另一张桌子，两张会议桌子将进行通信。

A phone number isn’t just an ID code. A phone number consists of several parts in most nations. In the U.S., this is a country code, an area code, an exchange and a subscriber number. Each level contains information about the physical location of the phone and each level narrows the location down further. For example, a phone might be in the U.S. (North America code +1), in the Colorado Springs metro area (area code 719), in an exchange (674) and at some four-digit subscriber number within that exchange.

> 电话号码不仅仅是身份码。在大多数国家，电话号码由几个部分组成。在美国，这是国家代码、区号、交换机和用户号码。每个级别都包含有关手机物理位置的信息，每个级别都进一步缩小了位置。例如，电话可能位于美国(北美代码 +1)、科罗拉多泉地铁区(区号 719)、交换机(674)以及该交换机内的某个四位数用户号码。

The Internet uses a system very much like this. As we’ve mentioned briefly earlier in the chapter, the collection of rules and techniques that enable packet-based communication over the Internet is called the _Internet Protocol_ (IP). Within the Internet protocol is an addressing scheme based on a type of numeric address called the _IP address_. The IP is intimately connected with a higher-level protocol called _Transmission Control Protocol_ (TCP). If you refer to [Figure 7-1](#10_9781119183938-ch07.xhtml#c07-fig-0001), you see that TCP is immediately above IP on the OSI reference model.

> 互联网使用的系统很像这样。正如我们在本章前面简要提到的，通过 Internet 实现基于分组的通信的规则和技术集合称为 _Internet Protocol_(IP)。在因特网协议中，有一种基于一种称为\_IP 地址的数字地址类型的寻址方案。IP 与称为传输控制协议(TCP)的高级协议紧密相连。如果您参考[图 7-1](#10_9781119183938-ch07.xhtml#c07-fig-0001)，您会看到 OSI 参考模型上的 TCP 正好位于 IP 之上。

The IP is focused on addressing and routing _packets_; the TCP is focused on establishing and maintaining _connections_ between computers so that packets may be transferred. TCP is the Internet’s delivery mechanism: it makes sure that packets actually get where they’re going, and that the order of a stream of packets is preserved as it travels from computer to computer. IP and TCP work together and are rarely used separately. This is why most of the time you’ll see them referred to as TCP/IP.

> **IP 侧重于寻址和路由 _packets_；TCP 专注于建立和维护计算机之间的连接，以便可以传输数据包**。TCP 是互联网的传输机制：它确保数据包真正到达目的地，并且在数据流从计算机传输到计算机时，数据流的顺序保持不变。IP 和 TCP 一起工作，很少单独使用。这就是为什么大多数时候你会看到它们被称为 TCP/IP。

### IP Addresses and TCP Ports

An IP address has two parts. One is the address of a network, and the other is the address of a particular node (in Internet jargon, a _host_) present on that network. Unlike a MAC address, which is more of a name or an ID code, an IP address really is an address, and allows a network appliance called a _router_ to locate a network and a host based on that address.

> IP 地址有两部分。一个是网络的地址，另一个是该网络上存在的特定节点的地址(在互联网术语中，是主机)。与 MAC 地址不同，IP 地址更像是一个名称或 ID 代码，它实际上是一个地址，并允许一个名为 _router_ 的网络设备基于该地址定位网络和主机。

By convention, IP addresses are usually written out this way, as a so-called _dotted quad_:

> 按照惯例，IP 地址通常是这样写的，即所谓的 _dotted quad_：

```
    264.136.8.101`
```

Each group of numbers separated by periods is called an _octet_, which in computer science means an 8-bit quantity. If you’re sharp you may have noticed that 264 is not expressible in 8 bits. That was deliberate. In writing this chapter, we don’t want to use someone’s actual IP address, and the custom in books and papers is to create imaginary addresses for examples by using a value greater than 255 for the first octet.

> 每组由句点分隔的数字称为 _octet_，在计算机科学中，这意味着 8 位的数量。如果你很敏锐，你可能已经注意到 264 不能用 8 位来表达。这是故意的。在撰写本章时，我们不想使用某人的实际 IP 地址，书籍和论文中的习惯是通过对第一个八位字节使用大于 255 的值来创建虚拟地址。

In an IP address, one or more of the higher-order octets contains the network address, and one or more of the lower-order octets contains the host address. In Figure 7-13, on the right is a LAN with four hosts. Between the LAN and the outside world is a router. In this case, the three higher-order octets contain the address of the network. The lowest octet contains the address of a particular host. Given an address like 264.136.8.101, a host anywhere in the world can create a TCP connection with the top computer in [Figure 7-13](#10_9781119183938-ch07.xhtml#c07-fig-0013).

> 在 IP 地址中，一个或多个高阶八位位组包含网络地址，而一个或更多个低阶八位位位组则包含主机地址。在图 7-13 中，右侧是一个具有四个主机的 LAN。局域网和外界之间是一个路由器。在这种情况下，三个高阶八位位组包含网络的地址。最低的八位字节包含特定主机的地址。给定 264.136.8.101 这样的地址，世界上任何地方的主机都可以创建与顶级计算机的 TCP 连接，如图 7-13](#10_9781119183938-ch07.xhtml#c07-fig-0013)所示。

![[FIGURE 7-13:](#10_9781119183938-ch07.xhtml#rc07-fig-0013) The two parts of an IP address](./media/images/9781119183938-fg0713.png)

Larger networks with more than 255 hosts divide the IP address differently, with more octets devoted to the host portion of the address, and fewer to the network portion of the address. The split between the network portion and the host portion of an IP address is specified by a four-octet bit pattern called a _subnetwork mask_. ( `Subnetwork` is often shortened to `subnet` .) The mask is used to separate the two portions of the address for further processing. Where networks are nested one inside another, a separate subnetwork mask (informally called a `subnet mask` ) is used for each of the separate networks.

> 具有 255 个以上主机的较大网络对 IP 地址的划分不同，更多的八位字节用于地址的主机部分，而更少的八位位组用于地址的网络部分。IP 地址的网络部分和主机部分之间的分割由称为 _subnetworkmask_。( `Subnetwork` 通常缩写为 `subnet` 。)掩码用于分隔地址的两部分，以便进一步处理。当网络相互嵌套时，每个单独的网络都使用单独的子网掩码(非正式地称为 `子网掩码` )。

Internet routing is complex, and the details of how routers work internally is beyond the scope of this book. As mentioned earlier in this chapter, they use an internal routing table to look up network addresses to discover how to reach them. An entry in the routing table provides information allowing the router to choose a route by which the destination network may be reached. A given router cannot necessarily access any arbitrary network with one single connection. It may take several sequential connections (called _hops_) to reach a given destination. At the end of each hop there’s another router, and that router forwards the packet to the next router along the route. Eventually the packet arrives at the destination network, and that network’s router forwards the packet to the individual host to which the packet was addressed.

> 互联网路由是复杂的，路由器内部工作的细节超出了本书的范围。正如本章前面提到的，他们使用内部路由表来查找网络地址，以发现如何到达这些地址。路由表中的条目提供允许路由器选择可以到达目的地网络的路由的信息。给定的路由器不一定通过一个连接访问任意网络。可能需要几个连续的连接(称为 _hops_)才能到达给定的目的地。在每一跳的末尾都有另一个路由器，该路由器将数据包转发到路由上的下一个路由器。最终，数据包到达目的地网络，该网络的路由器将数据包转发到数据包寻址的单个主机。

Routers come in many sizes, from a home network router that can fit in the palm of your hand to a cabinet the size of a refrigerator that weighs hundreds of pounds. The routing table in a large router may have hundreds of thousands of entries. The routing table on a home router typically has only one, which contains the address of the home’s ISP’s router. Any packet originating on a home router has only one possible path—through its ISP—to the rest of the Internet. So the home router forwards all packets to the ISP’s much larger and more powerful router, which then selects the next hop on the route.

> 路由器有多种尺寸，从可以放在手掌中的家庭网络路由器到重达数百磅的冰箱大小的机柜。大型路由器中的路由表可能有几十万个条目。家庭路由器上的路由表通常只有一个，其中包含家庭 ISP 路由器的地址。任何源于家庭路由器的数据包只有一条可能的路径通过其 ISP 到达互联网的其他部分。因此，家庭路由器将所有数据包转发给 ISP 更大、更强大的路由器，然后由其选择路由上的下一跳。

The TCP protocol creates connections between two hosts (one or both of which may be servers) using IP addresses. These connections, however, are not simply between computers or other network devices. Connections are actually between two software applications running on those computers. (Refer to [Figure 7-1](#10_9781119183938-ch07.xhtml#c07-fig-0001), and the application set of the OSI reference model.) A web browser on your tablet or computer connects to a web server on a remote host. An email client on your tablet or computer connects to an email server on the remote host. This final piece of routing is accomplished using _port numbers_, which are 16-bit values that (as we saw earlier) are present in every IP packet and allow the network stack on a host to identify which application should receive each packet. We refer to the act of splitting a single stream of incoming packets from the network into multiple streams of packets on the basis of destination port numbers as _demultiplexing_.

> TCP 协议使用 IP 地址在两个主机(其中一个或两个可能是服务器)之间创建连接。然而，这些连接不仅仅是计算机或其他网络设备之间的连接。连接实际上是运行在这些计算机上的两个软件应用程序之间的连接。(参考[图 7-1](#10*9781119183938-ch07.xhtml#c07-fig-0001) 和 OSI 参考模型的应用程序集。)平板电脑或计算机上的 web 浏览器连接到远程主机上的 web 服务器。平板电脑或计算机上的电子邮件客户端连接到远程主机上的电子邮件服务器。这最后一段路由是使用*port numbers *完成的，这是一个 16 位的值(正如我们前面所看到的)，存在于每个 IP 数据包中，并允许主机上的网络堆栈识别哪个应用程序应该接收每个数据包。我们将基于目的端口号将来自网络的单个传入数据包流拆分为多个数据包流的行为称为\_ demultiplexing。

When a client application wants to establish a TCP connection to a server application, it begins by assigning an arbitrary unused local port number to uniquely identify its end of the connection. It then sends a connection request, specifying a destination port number; this is not an arbitrary number but instead is generally one of several _well-known port numbers_, which are associated with a higher-level protocol. HTTP is associated with port 80, email with ports 25 (sending via SMTP) and 110 (receiving via POP), SSL (Secure Sockets Layer) with port 443, FTP (File Transfer Protocol) with port 21, and so on. A server application must `listen` to a port for TCP to make a connection to that port; if there is nobody listening on port 80, for example, there is no web server in operation at the remote host. When a connection is accepted, an arbitrary unused port number is assigned to the server end of the connection; further communication happens via this port number, freeing up the well-known port to accept further incoming connections.

> 当客户端应用程序想要建立到服务器应用程序的 TCP 连接时，首先要分配一个任意的未使用的本地端口号，以唯一标识其连接端。然后，它发送一个连接请求，指定目标端口号；这不是一个任意的数字，而是与更高级别协议相关的几个众所周知的端口号之一。HTTP 与端口 80 相关联，电子邮件与端口 25(通过 SMTP 发送)和 110(通过 POP 接收)相关联，SSL(安全套接字层)与端口 443 相关联，FTP(文件传输协议)与端口 21 相关联，等等；例如，如果没有人在端口 80 上侦听，则远程主机上没有正在运行的 web 服务器。当连接被接受时，将为连接的服务器端分配一个任意未使用的端口号；通过该端口号进行进一步的通信，从而释放已知端口以接受进一步的传入连接。

Routers can block connections that use specific port numbers as a security measure, to prevent remote connections to unauthorised servers. For example, a common way to combat email spam is for hosting services to configure their routers to block port 25, which is assigned to the Simple Mail Transfer Protocol (SMTP). Certain software is difficult to block by port number because the protocols allow the use of any open port via `port discovery` , which basically means that the two hosts attempt a connection on a range of ports until they find one that works. (BitTorrent is a good example of such an adaptable protocol.)

> 路由器可以阻止使用特定端口号作为安全措施的连接，以防止远程连接到未经授权的服务器。例如，打击电子邮件垃圾邮件的一种常见方法是托管服务将其路由器配置为阻止端口 25，该端口分配给简单邮件传输协议(SMTP)。某些软件很难通过端口号阻止，因为协议允许通过 `端口发现` 使用任何开放端口，这基本上意味着两个主机在一系列端口上尝试连接，直到找到一个可以工作的端口。(BitTorrent 就是这样一个可适应协议的好例子。)

Ports are also important in a router-based function called Network Address Translation (NAT), which is covered a little later in the `[Network Address Translation](#10_9781119183938-ch07.xhtml#c07-sec-0023)` section.

> 端口在名为网络地址转换(NAT)的基于路由器的功能中也很重要，稍后将在 `[网络地址转换](#10_9781119183938-ch07.xhtml#c07-sec-0023)` 一节中介绍。

### Local IP Addresses and DHCP

When the architects of the original Internet defined the suite of Internet protocols that include the IP addressing system, they never imagined that the general public would one day be connecting to the Internet by the billions. They also didn’t envision that devices as mundane as telephones, TV sets and even refrigerators would someday want their own IP addresses as well. This has led to a serious problem: there only 4.3 billion possible 32-bit IP addresses, which isn’t nearly enough to give one to every person (or refrigerator) on Earth.

> 当最初互联网的设计者定义了包括 IP 寻址系统在内的一套互联网协议时，他们从未想过，总有一天，公众会连接到数十亿的互联网。他们也没有想到像电话、电视机甚至冰箱这样平凡的设备有朝一日也会想要自己的 IP 地址。这导致了一个严重的问题：只有 43 亿个可能的 32 位 IP 地址，这几乎不足以给地球上的每个人(或冰箱)一个。

Several things are being done to deal with this shortage of IP addresses. The high road is to create a whole new addressing scheme with larger addresses, which is being done in the IPv6 project. (The current 32-bit IP addressing system is called IPv4.) The IPv6 address space is 128 bits wide. This allows it to support up to 2<sup>128</sup> different addresses. That number works out at 3.4 × 10<sup>38</sup>, which dwarfs the total number of stars, planets, moons and asteroids in the observable universe.

> 为了解决 IP 地址短缺的问题，我们正在采取一些措施。当务之急是创建一个具有更大地址的全新寻址方案，这在 IPv6 项目中正在进行。(当前的 32 位 IP 寻址系统称为 IPv4。)IPv6 地址空间为 128 位宽。这允许它支持多达 2 个不同的地址。这个数字是 3.4×10<sup>38</sup>，这使可观测宇宙中恒星、行星、卫星和小行星的总数相形见绌。

At this writing, only about 10% of Internet traffic uses IPv6 addresses.The expectation is that IPv6 will eventually dominate the Internet. In the meantime, the shortage has been ameliorated to some extent by the use of _local IP addresses_. The Internet Assigned Numbers Authority (IANA) has set aside four blocks of IP addresses as local, meaning that they cannot be routed and are basically invisible except within their own local networks. This makes them sound useless, but in fact local IP addresses make it possible to use the TCP/IP-based Internet services within a LAN, where there is no router between any two hosts. Because local IP addresses cannot be seen outside of their local network, there’s no danger in reusing them. Hundreds of millions of people can use the address `192.168.1.100` at the same time. The following are the four blocks of local IP addresses:

> 在本文中，只有约 10% 的互联网流量使用 IPv6 地址。预计 IPv6 最终将主导互联网。同时，本地 IP 地址的使用在一定程度上改善了这种不足。互联网分配号码管理局(IANA)已将四个 IP 地址块作为本地地址，这意味着它们无法路由，并且除了在自己的本地网络中之外，基本上是不可见的。这使得它们听起来毫无用处，但事实上，本地 IP 地址使得在 LAN 中使用基于 TCP/IP 的 Internet 服务成为可能，在 LAN 中，任何两个主机之间都没有路由器。因为本地 IP 地址在本地网络之外看不到，所以重用它们没有危险。数亿人可以同时使用地址 `192.168.1.100` 。以下是四个本地 IP 地址块：

```
    10.0.0.0– 10.255.255.255`
    169.254.0.1 – 169.254.255.254`
    172.16.0.0 – 172.31.255.255`
    192.168.0.0 – 192.268.255.255`
```

Local IP addresses can’t be seen past a router, but in nearly all home networks, the router performs an important service: it distributes local IP addresses to the nodes in its own network. A piece of software called a _Dynamic Host Configuration Protocol_ (DHCP) server runs in the router, and when a node comes online and asks for network configuration, the DHCP server scans the addresses in its local IP address table and sends down a local address that isn’t already being used. A number of other configuration options (including the subnet mask) are sent down at the same time with the local IP address, but they’re beyond the scope of this chapter.

> 路由器无法看到本地 IP 地址，但在几乎所有的家庭网络中，路由器都执行一项重要的服务：它将本地 IP 地址分配给自己网络中的节点。路由器中运行一种叫做动态主机配置协议(DHCP)服务器的软件，当节点联机并请求网络配置时，DHCP 服务器扫描其本地 IP 地址表中的地址，并发送一个尚未使用的本地地址。许多其他配置选项(包括子网掩码)与本地 IP 地址同时发送，但它们超出了本章的范围。

The node making the request gets a _lease_ on the IP address for a limited period of time, often 24 hours. When the lease expires, the address goes back into the free address pool. If a node is still on the network when its IP address lease expires, it simply requests that the lease be renewed. A reasonable expiration period on DHCP leases (24 hours or more) allows nodes to be powered down overnight without losing their leases. The next time a node is powered up, it will still have the same IP address.

> 发出请求的节点在有限的时间内(通常是 24 小时)获得 IP 地址的 _lease_。租约到期后，地址将返回到空闲地址池中。如果某个节点在其 IP 地址租约到期时仍在网络上，它只需请求续订租约即可。DHCP 租约的合理到期期限(24 小时或更长)允许节点在一夜之间断电，而不会丢失其租约。下次节点通电时，它仍然具有相同的 IP 地址。

DHCP isn’t used only for distributing local IP addresses to LANs. Internet service providers (ISPs) run DHCP servers as well, and when a home router connects to its ISP, the ISP’s DHCP server sends down configuration information to the home router, including a _global_ IP address. This address is how your LAN is known to other networks across the Internet.

> DHCP 不仅仅用于向 LAN 分发本地 IP 地址。互联网服务提供商(ISP)也运行 DHCP 服务器，当家庭路由器连接到其 ISP 时，ISP 的 DHCP 服务器会向家庭路由器发送配置信息，包括全局 IP 地址。此地址是 Internet 上其他网络知道您的 LAN 的方式。

An IP address distributed by a DHCP server, whether local or global, is called a _dynamic IP address_. Dynamic IP addresses are used in situations where the address may change without disrupting network operation. Server software that can be accessed from the Internet requires an IP address that doesn’t change. Such an address is a _static IP address_. Internet hosting services that allow you to run your own servers on the Internet are allocated blocks of static IP addresses. When you establish an account with a hosting service, you are provided with a static IP address for your server. That one static IP address is how people and other servers on the Internet can find your server.

> DHCP 服务器(无论是本地还是全局)分发的 IP 地址称为动态 IP 地址。动态 IP 地址用于地址可能发生变化而不中断网络操作的情况。可以从 Internet 访问的服务器软件要求 IP 地址不变。这样的地址是静态 IP 地址\_。允许您在 Internet 上运行自己的服务器的 Internet 托管服务分配了静态 IP 地址块。当您在托管服务中建立帐户时，将为您提供服务器的静态 IP 地址。一个静态 IP 地址是人们和 Internet 上的其他服务器查找您的服务器的方式。

It’s possible to manually assign static local IP addresses to nodes on a LAN. Such addresses are not leased and don’t expire. They are useful for nodes like network printers that are accessed by other network nodes via their IP address. If a network printer’s IP address changes, some nodes on the network may not be able to access it. Most network printers include instructions and sometimes software allowing a static local IP address to be assigned to the printer.

> 可以手动将静态本地 IP 地址分配给 LAN 上的节点。此类地址未出租且不会过期。它们对于其他网络节点通过其 IP 地址访问的网络打印机等节点非常有用。如果网络打印机的 IP 地址发生更改，网络上的某些节点可能无法访问它。大多数网络打印机都包含指令，有时还包含软件，允许将静态本地 IP 地址分配给打印机。

The local IP addresses that begin with 169.254 have a special use: all Windows versions from Windows 2000 onwards implement a service called _Automatic Private IP Addressing_ (APIPA), which provides a local IP address from the 169.254 block any time a DHCP server is not available to provide a local address. A Windows node with an APIPA address can communicate with any other node on its local network segment that has an APIPA address. This allows small numbers of computers to connect through a switch without requiring a router. The more general term for a system that automatically provides local network addresses and other configuration parameters is _zero-configuration networking_. A similar system called Avahi exists for Linux, but Raspbian does not include it by default and it must be installed manually if it is desired. Zero-configuration networking is primarily useful for small networks that have no connection to the Internet and thus no router or DHCP server to handle local segment configuration.

> 以 169.254 开头的本地 IP 地址有一个特殊用途：从 Windows 2000 开始的所有 Windows 版本都实现了名为 _Automatic Private IP Addressing_(APIPA)的服务，该服务在 DHCP 服务器无法提供本地地址时，从 169.254 块提供本地 IP 地址。具有 APIPA 地址的 Windows 节点可以与其本地网段上具有 APIPA 的任何其他节点进行通信。这允许少量计算机通过交换机连接，而不需要路由器。对于自动提供本地网络地址和其他配置参数的系统，更通用的术语是 _zero-configuration networking_。Linux 上有一个类似的系统 Avahi，但 Raspbian 默认不包含它，如果需要，必须手动安装。零配置网络主要用于没有连接到 Internet 的小型网络，因此没有路由器或 DHCP 服务器来处理本地网段配置。

### Network Address Translation

Local IP addresses are invisible to other networks beyond the local router. How, then, can TCP/IP allow nodes with local IP addresses to connect to the Internet? The answer is another software service running on the router: _Network Address Translation_ (NAT). Simply put, NAT translates a non-routable local IP address into a global, routable IP address. In addition, it provides, almost as a by-product, fairly strong protection against unwanted connections from outside the local network. Figure 7-14 is a sketch of a possible home network setup: four computers, a router, and a switch. In many, or even most, cases these days, the router and the switch are combined into a single physical appliance. (They’re broken out here for conceptual clarity.) Each of the network’s four computers has a local, non-routable IP address. NAT is running inside the router. NAT keeps these local IP addresses in a table that it maintains for its own use.

> 本地 IP 地址对于本地路由器之外的其他网络是不可见的。那么，TCP/IP 如何允许具有本地 IP 地址的节点连接到 Internet？答案是路由器上运行的另一个软件服务：_Network Address Translation_(NAT)。简单地说，NAT 将不可路由的本地 IP 地址转换为全局可路由的 IP 地址。此外，它几乎作为一种副产品，提供了相当强大的保护，防止来自本地网络外部的不必要连接。图 7-14 是一个可能的家庭网络设置示意图：四台计算机、一个路由器和一个交换机。如今，在许多情况下，甚至在大多数情况下，路由器和交换机被组合成一个物理设备。(为了概念清晰，这里将它们分开。)网络的四台计算机中的每台都有一个本地的、不可路由的 IP 地址。NAT 正在路由器内部运行。NAT 将这些本地 IP 地址保存在自己维护的表中。

![[FIGURE 7-14:](#10_9781119183938-ch07.xhtml#rc07-fig-0014) How Network Address Translation (NAT) works](./media/images/9781119183938-fg0714.png)

As we explained earlier, the network as a whole has a single public, routable IP address that is the only address for any network node that can be seen by the outside world. This address resides in the network’s router, and for home networks it is generally provided by the ISP’s DHCP server. Local IP addresses are not routable, and to create connections between individual computers on a local network segment and hosts on the other side of the router, the router creates `extended` IP addresses by combining the local IP address assigned to a device on the local network with a TCP port number. Which port number is used isn’t important, as long as it isn’t already used by anything else on that particular network. (There are more than 65,000 different port numbers, so finding a free one on even a modest-sized network is rarely a problem.) NAT stores extended IP addresses for its local nodes in an internal table that acts as a sort of `internal phone book` for devices on the local network segment. This table is not accessible from the Internet. Only NAT can read it or change it. On Linux systems, this process is called _IP masquerading_. In a sense, the router is assigning port numbers as ID codes to the computers on its local network.

> 正如我们前面所解释的，网络作为一个整体具有一个公共的、可路由的 IP 地址，这是外部世界可以看到的任何网络节点的唯一地址。该地址位于网络的路由器中，对于家庭网络，通常由 ISP 的 DHCP 服务器提供。本地 IP 地址是不可路由的，为了在本地网段上的各个计算机和路由器另一侧的主机之间创建连接，路由器通过将分配给本地网络上的设备的本地 IP 地址与 TCP 端口号相结合来创建 `扩展` IP 地址。使用哪个端口号并不重要，只要该特定网络上的任何其他设备都没有使用它。(有超过 65000 个不同的端口号，因此即使在一个中等规模的网络上找到一个空闲的端口号也很少有问题。)NAT 将其本地节点的扩展 IP 地址存储在一个内部表中，该表充当本地网段上设备的一种 `内部电话簿` 。无法从 Internet 访问此表。只有 NAT 才能读取或更改它。在 Linux 系统上，这个过程称为\_IP 伪装。从某种意义上说，路由器正在为其本地网络上的计算机分配端口号作为 ID 码。

When one of the computers inside the network wants to connect (for example) to a web server, NAT takes the web page request and places an extended IP address consisting of the router’s IP address plus the requesting computer’s port number into the request. When the web server establishes a connection, it uses this extended IP address, and not the internal, local IP address of the computer to which it connects. The connection is thus established with the router, _not_ the computer—and the router decides what material delivered from the web server can reach the computer. The web server has no knowledge of the requesting computer beyond its port number, and the port number alone does not allow a connection to a local IP address. Because the address that servers outside the local network must use is created by NAT, the connection must be initiated by NAT, in cooperation with one of the local network nodes. This prevents unsolicited connections from outside the local network.

> 当网络中的一台计算机想要连接(例如)到 web 服务器时，NAT 接受网页请求，并将由路由器的 IP 地址加上请求计算机的端口号组成的扩展 IP 地址放入请求中。当 web 服务器建立连接时，它使用此扩展 IP 地址，而不是所连接计算机的内部本地 IP 地址。因此，与路由器建立了连接，而不是计算机，路由器决定从 web 服务器发送的材料可以到达计算机。除了端口号之外，web 服务器不知道请求的计算机，并且仅端口号不允许连接到本地 IP 地址。因为本地网络外部的服务器必须使用的地址是由 NAT 创建的，所以连接必须由 NAT 发起，并与一个本地网络节点协作。这防止了来自本地网络外部的未经请求的连接。

NAT complicates matters when a user of a computer on a local network wants to run a publicly available server on the computer. Because outside users must be allowed to make a connection to the server, a way for connections initiated outside the network must be provided by the router. This is done through _port forwarding_, in which an outside request for a server connection is forwarded to a local IP address for the computer on which the server is running. NAT ensures that connections are made only to the server, and not to any other software on the computer running the server.

> 当本地网络上的计算机的用户想要在计算机上运行公开可用的服务器时，NAT 使事情变得复杂。因为必须允许外部用户连接到服务器，所以路由器必须提供在网络外部启动连接的方式。这是通过 _port forwarding_ 完成的，其中，服务器连接的外部请求被转发到运行服务器的计算机的本地 IP 地址。NAT 确保只连接到服务器，而不连接到运行服务器的计算机上的任何其他软件。

## Wi-Fi

One of the beauties of the OSI reference model is that it encourages engineers to `layer` their designs for networking hardware and software, with well-defined interfaces between adjacent layers. A non-obvious benefit of this layering is that a layer can be `swapped out` for a different layer without completely disrupting the operation of the stack from the perspective of the application layer.

> OSI 参考模型的一个优点是它鼓励工程师 `分层` 他们的网络硬件和软件设计，并在相邻层之间定义良好的接口。这种分层的一个不明显的好处是，从应用程序层的角度来看，可以将一个层 `交换` 为不同的层，而不会完全中断堆栈的操作。

Much of this layer-swapping has occurred at the bottom, at the data link layer and especially the physical layer. 10BASE2 and 10BASE-T provide two different physical media for the transport of network packets: one is a half-duplex system using coaxial cable, and the other is a full-duplex system using twisted-pair conductors. Both implement Ethernet networking, and from the perspective of the higher layers implementing TCP/IP and network applications, there’s no difference.

> 这种层交换大多发生在底层，数据链路层，尤其是物理层。10BASE2 和 10BASE-T 为网络数据包的传输提供了两种不同的物理介质：一种是使用同轴电缆的半双工系统，另一种是采用双绞线的全双工系统。两者都实现了以太网网络，从实现 TCP/IP 和网络应用程序的更高层的角度来看，没有什么区别。

In the mid-1980s, researchers began to explore the notion of creating Ethernet-like data link and physical layers without wires at all, using radio waves or infrared light. The U.S. Federal Communications Commission, which governs the use of radio communication in the U.S., had opened a number of frequency bands to unlicensed use in 1985. In 1987, NCR created a wireless technology to link its cashier station products. It worked very well, and the firm developed the technology into a commercial product line called WaveLAN, which was placed on the market in 1988. A similar but incompatible system was developed by Canadian firm Telesystems SLW at about the same time, and was eventually spun off as Aironet. Hoping to see its technology incorporated into the IEEE 802 LAN standard, NCR contributed the design to the 802 standards committee in 1990. The IEEE proposed a new standard for wireless Ethernet and called it 802.11. The standard was published in 1997. This original 802.11 spec embraced a number of existing modulation technologies, bit rates and MAC schemes, making it more of a menu than a standard. (For example, it included a physical layer spec for modulated infrared light that never saw broad adoption.) There were so many choices that even products completely compliant with the standard could be incompatible with other compliant products.

> 20 世纪 80 年代中期，研究人员开始探索使用无线电波或红外光创建类似以太网的数据链路和完全没有电线的物理层的概念。管理美国无线电通信使用的美国联邦通信委员会(Federal Communications Commission)于 1985 年开放了多个频段供未经许可使用。1987 年，NCR 创建了一种无线技术来连接其收银台产品。它工作得很好，该公司将这项技术开发成一个名为 WaveLAN 的商业产品线，并于 1988 年推向市场。加拿大 Telesystems SLW 公司大约在同一时间开发了一个类似但不兼容的系统，最终被分拆为 Aironet。NCR 希望将其技术纳入 IEEE 802 LAN 标准，于 1990 年向 802 标准委员会提交了该设计。IEEE 提出了一种新的无线以太网标准，并称之为 802.11。该标准于 1997 年发布。这个最初的 802.11 规范包含了许多现有的调制技术、比特率和 MAC 方案，使其更像是一个菜单而不是标准。(例如，它包括一个从未被广泛采用的调制红外光的物理层规范。)有太多的选择，甚至完全符合该标准的产品也可能与其他符合标准的产品不兼容。

Most wireless networking products that adhere to the 802.11 standard are referred to using the name _Wi-Fi_, from an early play on the term `hi-fi` for audio technology. `[Wi-Fi](#10_9781119183938-ch07.xhtml#c07-sec-0024)` is a trademark owned by a trade group called the Wi-Fi Alliance, and rights to use the term on products are not granted until the products are tested for compliance with the pertinent sections of the IEEE 802.11 standard.

> 大多数符合 802.11 标准的无线网络产品都使用名称 _Wi-Fi_，这是早期关于音频技术的术语 `高保真` 的说法。`[Wi-Fi](#10_9781119183938-ch07.xhtml#c07-sec-0024)` 是一个名为 Wi-Fi 联盟的贸易组织拥有的商标，在产品测试是否符合 IEEE 802.11 标准的相关章节之前，不会授予在产品上使用该术语的权利。

### Standards within Standards

Quite apart from compatibility issues, early 802.11 products billed as `wireless Ethernet` offered bit rates of only 1 Mbps or 2 Mbps. This was far slower than 10 Mbps technologies like 10BASE2 and 10BASE-T, and the 100 Mbps and 1000 Mbps technologies that followed them. In the years after 1997, the IEEE 802.11 committee began work on several addenda to the 802.11 standard, defining new wireless technologies focused on improving throughput:

> 除了兼容性问题，早期的 802.11 产品被称为 `无线以太网` ，其比特率仅为 1Mbps 或 2Mbps。这比 10BASE2 和 10BASE-T 等 10Mbps 技术以及随后的 100Mbps 和 1000Mbps 技术慢得多。在 1997 年之后的几年里，IEEE 802.11 委员会开始了对 802.11 标准的多个附录的工作，定义了专注于提高吞吐量的新无线技术：

- **802.11a:** Operates on the 5GHz band, with a nominal bit rate of 54 Mbps, and a practical throughput of about half that, using TCP. The spec was finalised in 2000. - **802.11b:** Operates on the 2.4GHz band, with a nominal bit rate of 11 Mbps, and a practical TCP throughput of about 6 Mbps. The spec was finalised in 1999. - **802.11g:** Operates on the 2.4GHz band, but uses several technologies originally developed for the 802.11a standard to allow bit rates of up to 54 Mbps. As with 802.11a, practical TCP throughput is less than half that, at about 22 Mbps. The spec was finalised in late 2003. - **802.11n:** Operates on either the 2.4GHz band or the 5GHz band. It achieves much higher throughput than earlier technologies by using twice the channel bandwidth (40MHz) when possible, and multiple antennas with a technology called multiple-input, multiple-output (MIMO). Maximum bit rate can theoretically be as high as 600 Mbps, but the practical bit rate and TCP throughput depend heavily on local channel congestion and rarely top 100 Mbps. The spec was finalised in 2009. - **802.11ac:** Operates only on the 5GHz band. Its technology is an evolutionary extension of 802.11n, and achieves throughput close to 1000BASE-T (gigabit Ethernet) by using additional antennas and `bonding` adjacent 40MHz channels into 80 or 160MHz channels, where local spectrum use allows. The spec was approved at the beginning of 2014, and commercial products began appearing in large numbers later that year.

> -**802.11a:**在 5GHz 频带上运行，标称比特率为 54 Mbps，实际吞吐量约为其一半，使用 TCP。该规范于 2000 年定稿。-**802.11b:**工作在 2.4GHz 频段，标称比特率为 11 Mbps，实际 TCP 吞吐量约为 6 Mbps。该规范于 1999 年定稿。-**802.11g:**在 2.4GHz 频带上运行，但使用了最初为 802.11a 标准开发的几种技术，以允许高达 54 Mbps 的比特率。与 802.11a 一样，实际 TCP 吞吐量不到其一半，大约为 22Mbps。该规范于 2003 年底定稿。-**802.11n:**可在 2.4GHz 频带或 5GHz 频带上工作。它通过在可能的情况下使用两倍的信道带宽(40MHz)，以及使用多输入多输出(MIMO)技术的多天线，实现了比早期技术高得多的吞吐量。理论上，最大比特率可以高达 600Mbps，但实际的比特率和 TCP 吞吐量严重依赖于本地信道拥塞，很少超过 100Mbps。该规范于 2009 年定稿。-**802.11ac:**仅在 5GHz 频带上工作。它的技术是 802.11n 的演进扩展，通过使用额外的天线，并将相邻的 40MHz 信道 `绑定` 到 80 或 160MHz 信道(本地频谱使用允许)，实现了接近 1000BASE-T(千兆以太网)的吞吐量。该规范于 2014 年初获得批准，商业产品在当年晚些时候开始大量出现。

Although the IEEE formally withdraws addenda like these once they have been folded into the larger 802.11 spec and ratified, terms like *Wireless-B*and _Wireless-G_ continue to be used to differentiate products that do not support all available technologies. In practice, nearly all commercial products at this writing support standards b, g, and n on 2.4GHz, with some lines supporting 802.11a on 5GHz as well.

> 尽管 IEEE 在将此类附录纳入更大的 802.11 规范并获得批准后，正式撤回了这些附录，但仍继续使用 _Wireless-B_ 和 _Wireless-G_ 等术语来区分不支持所有可用技术的产品。实际上，几乎所有的商业产品都支持 2.4GHz 的 b、g 和 n 标准，其中一些线路也支持 5GHz 的 802.11a 标准。

Many other addenda to 802.11 have been published and ratified since 1997, generally providing refinements to the primary spec in areas like mobile device roaming, quality of service, bridging networks and security.

> 自 1997 年以来，802.11 的许多其他附录已经发布和批准，通常在移动设备漫游、服务质量、桥接网络和安全等领域对主要规范进行了改进。

### Facing the Real World

Going wireless complicates networking in a number of ways. Wired Ethernet keeps its signal inside a cable of some sort and, beyond certain physical limitations (especially the radius at which an Ethernet cable may be bent), where the cable can go, the signal goes. Wi-Fi uses microwaves travelling freely through the air, in and among buildings and other structures. The problems related to the microwave physical medium fall into several categories:

> 无线化在许多方面使网络变得复杂。有线以太网将其信号保存在某种类型的电缆中，并且在超出某些物理限制(特别是以太网电缆可能弯曲的半径)的情况下，信号会传输到电缆可以到达的位置。Wi-Fi 使用微波在空气中自由传播，在建筑物和其他结构中自由传播。与微波物理介质相关的问题可分为几类：

- Attenuation (reduction of signal strength) due to distance through free space, and the presence of walls and water-rich exterior factors like broadleaf trees, rain or snow - Microwave shadows cast by large metallic objects such as aluminium sides, filing cabinets, refrigerators and industrial equipment - Multipath interference caused by signals taking paths of different lengths from the transmit antenna to the receive antenna, and interfering with one another constructively or destructively at the receive antenna - Channel congestion, which is interference from Wi-Fi signals on the same or adjacent channels - Interference from other technologies using the same frequencies as Wi-Fi, including Bluetooth gear, cordless phones, medical devices, sensor networks and, on some frequencies, amateur radio transceivers - The hidden node problem, in which not all terminals participating in a network can see each other, causing difficulties for MAC

> -由于通过自由空间的距离、墙壁和富含水的外部因素(如阔叶树、雨或雪)的存在而导致的衰减(信号强度的降低)-大型金属物体(如铝边、文件柜、，冰箱和工业设备.从发射天线到接收天线采用不同长度路径并在接收天线处彼此相长或相消干扰的信号引起的多径干扰.信道拥塞，这是来自相同或相邻信道上的 Wi-Fi 信号的干扰-来自使用与 Wi-Fi 相同频率的其他技术的干扰，包括蓝牙设备、无绳电话、医疗设备、传感器网络，以及在某些频率上的业余无线电收发机-隐藏的节点问题，其中不是所有参与网络的终端都可以看到彼此，给 MAC 带来困难

Even along unobstructed paths, microwaves transmitted from an omnidirectional antenna are attenuated by distance according to the inverse square law. When Wi-Fi hardware is used in fixed _point-to-point service_, as in links between buildings, directional antennas may be used to focus microwave energy along the path between a link’s two endpoints. This allows communication across gaps that would be impossible with omnidirectional antennas at the same power level.

> 即使沿着无障碍路径，从全向天线发射的微波也会根据平方反比定律按距离衰减。当 Wi-Fi 硬件用于固定点对点服务时，如在建筑物之间的链路中，定向天线可用于沿链路两端之间的路径聚焦微波能量。这允许在相同功率水平的全向天线不可能跨越间隙进行通信。

Microwaves are electromagnetic radiation, and may be reflected as they travel from transmitter to receiver. Wi-Fi signals bounce off walls, floors, ceilings and large objects, especially objects made of metal. This causes multiple wavefronts to arrive at the receiver along paths of different lengths, and thus at (very) slightly different times. If two or more wavefronts arrive precisely `in phase` they can theoretically boost signal strength at the receive antenna. However, in virtually all cases, the many wavefronts interfere with one another in unpredictable ways, causing _fading_. Even worse, multipath fading effects can be strongly frequency-dependent, causing not just fading but distortion of wideband signals. Figure 7-15 illustrates multipath interference.

> 微波是电磁辐射，当它们从发射器传播到接收器时可能会被反射。Wi-Fi 信号会从墙壁、地板、天花板和大型物体上反弹，尤其是金属物体。这导致多个波前沿着不同长度的路径到达接收器，因此在(非常)稍微不同的时间到达接收器。如果两个或多个波前精确地 `同相` 到达，理论上可以提高接收天线的信号强度。然而，在几乎所有的情况下，许多波前都以不可预测的方式相互干扰，从而导致衰减。更糟糕的是，多径衰落效应可能强烈依赖于频率，不仅会导致宽带信号的衰落，还会导致宽带信号失真。图 7-15 说明了多径干扰。

![[FIGURE 7-15:](#10_9781119183938-ch07.xhtml#rc07-fig-0015) Multipath interference](./media/images/9781119183938-fg0715.png)

In most Wi-Fi gear going back to the original Wireless-B, access points and wireless routers incorporate two antennas to deal with multipath interference. The ideal distance between them is one wavelength, which at 2.4GHz is 12.5cm, or just under five inches. The Wi-Fi receiver continuously samples signals on both antennas, and chooses the stronger of the two. This is called _diversity reception_. Having the antennas one wavelength apart optimises the chances that a usable signal is present on one antenna when the other antenna is subject to multipath interference.

> 在大多数可追溯到原始 Wireless-B 的 Wi-Fi 设备中，接入点和无线路由器结合了两个天线来应对多径干扰。它们之间的理想距离是一个波长，在 2.4GHz 时为 12.5cm，或略低于 5 英寸。Wi-Fi 接收器连续地对两个天线上的信号进行采样，并选择两者中比较强的一个。这称为 `多样性接收` 。当另一个天线受到多径干扰时，使天线间隔一个波长可以优化一个天线上出现可用信号的可能性。

Channel congestion is a consequence of a small number of distinct channels and of the way microwave spectrum space is allocated to those channels. Wi-Fi channels on 2.4GHz are not laid out nose-to-tail across the band, but overlap, as shown in Figure 7-16. Only three non-overlapping channels exist: channels 1, 6 and 11.

> 信道拥塞是少数不同信道以及微波频谱空间分配给这些信道的方式的结果。2.4GHz 频段的 Wi-Fi 信道并非首尾相连，而是重叠，如图 7-16 所示。只有三个不重叠的通道：通道 1、6 和 11。

---

> [!NOTE]

Channels 1, 6 and 11 do not overlap with one another, but _do_ overlap with the channels to either side of them. A strong signal of some sort on channel 5 may make channel 6 unusable, for example.

> 通道 1、6 和 11 彼此不重叠，但\_do 与通道两侧的通道重叠。例如，信道 5 上的某种强信号可能使信道 6 不可用。

![[FIGURE 7-16:](#10_9781119183938-ch07.xhtml#rc07-fig-0016) Wi-Fi frequency allocation on the 2.4GHz ISM band](./media/images/9781119183938-fg0716.png)

In crowded urban areas, interference from Wi-Fi gear on adjacent channels makes selecting a channel for use difficult. There are Wi-Fi survey apps available for mobile devices like tablets and smartphones that sample Wi-Fi signals and plot out their distribution across the 2.4GHz band on graphs. Once a survey app determines where neighbouring Wi-Fi gear is operating on the band, it becomes possible to choose the quietest channel currently available.

> 在拥挤的城市地区，Wi-Fi 设备对相邻频道的干扰使选择频道变得困难。平板电脑和智能手机等移动设备可以使用 Wi-Fi 调查应用程序，这些应用程序可以对 Wi-Fi 信号进行采样，并将其在 2.4GHz 频段的分布绘制在图表上。一旦调查应用程序确定了相邻的 Wi-Fi 设备在频段上的运行位置，就可以选择当前可用的最安静的频道。

Exactly which channels are available is dependent on national radio frequency regulations. In the U.S., only the first 11 channels may be used. Additional channels 12 and 13 are available in many other countries, including the UK. Channel 14 is available only in Japan. France allows only channels 10-13, and Spain only channels 10-11. Channel allocation on the 5GHz band is complex and difficult to summarise. The band is larger and the individual channels wider, so high bit-rate technologies like Wireless-N work best at 5GHz.

> 具体哪些频道可用取决于国家无线电频率法规。在美国，只能使用前 11 个频道。包括英国在内的许多其他国家都有 12 频道和 13 频道。14 频道仅在日本可用。法国只允许 10-13 频道，西班牙只允许 10-11 频道。5GHz 频带上的信道分配非常复杂，难以总结。频带更大，单个信道更宽，因此像 Wireless-N 这样的高比特率技术在 5GHz 下工作得最好。

The 2.4GHz band does not belong to Wi-Fi alone. Its formal name is the industrial, scientific, and medical (ISM) band, and many different classes of devices use it. Interference from such devices is not only possible but likely. The most familiar is the short-range Bluetooth wireless technology. Inexpensive cordless phones use 2.4GHz and are a common source of interference, as are microwave ovens, which may emit enough stray microwave energy to cause frequent frame retransmissions and a visibly slower link. If interference from industrial or medical equipment occurs, Wi-Fi users have no recourse but to relocate their gear to a different channel.

> 2.4GHz 频段不仅仅属于 Wi-Fi。它的正式名称是工业、科学和医疗(ISM)频段，许多不同类别的设备都使用它。来自此类设备的干扰不仅可能而且可能。最熟悉的是短程蓝牙无线技术。廉价的无绳电话使用 2.4GHz，是一个常见的干扰源，微波炉也是如此，它可能会发射出足够的杂散微波能量，导致频繁的帧重传和明显较慢的链路。如果发生来自工业或医疗设备的干扰，Wi-Fi 用户就别无选择，只能将设备转移到不同的频道。

### Wi-Fi Equipment in Use

The simplest way to think of a wireless network is to replace a conventional wired Ethernet hub with a Wi-Fi appliance called a _wireless access point_ (AP.) The network shown in [Figure 7-12](#10_9781119183938-ch07.xhtml#c07-fig-0012) then becomes something very much like Figure 7-17. A Wi-Fi AP _is_ an Ethernet hub, using the Wi-Fi data link and physical layers rather than the data link and physical layer for twisted pair network technologies like 10BASE-T, 100BASE-TX or 1000BASE-T. Nodes (often called _stations_ in technical literature) that connect wirelessly use a type of NIC called a _wireless client adapter_. The term `client` here alludes to a sort of client/server relationship with the access point, which `serves` an Ethernet connection to one or more wireless clients. A wireless client adapter can be an add-on device (as it generally is in desktop computers) or an integral part of a mobile device like a laptop, tablet or smartphone.

> 考虑无线网络最简单的方法是用 Wi-Fi 设备(称为 _wireless access point_(AP))代替传统的有线以太网集线器。如图 7-12](#10_9781119183938-ch07.xhtml#c07-fig-0012)所示的网络与图 7-17 非常相似。Wi-Fi AP 是以太网集线器，使用 Wi-Fi 数据链路和物理层，而不是双绞线网络技术(如 10BASE-T、100BASE-TX 或 1000BASE-T)的数据链路和实体层。无线连接的节点(在技术文献中通常称为 `状态` )使用一种称为 `无线客户端适配器` 的 NIC。这里的术语 `客户端` 指的是与接入点的一种客户端/服务器关系，它 `服务` 到一个或多个无线客户端的以太网连接。无线客户端适配器可以是附加设备(通常在台式计算机中)，也可以是笔记本电脑、平板电脑或智能手机等移动设备的组成部分。

![[FIGURE 7-17:](#10_9781119183938-ch07.xhtml#rc07-fig-0017) A simple wireless network](./media/images/9781119183938-fg0717.png)

All nodes connecting through the access point become part of a single collision domain, because there is no physical mechanism to support Ethernet switching through a wireless access point. Furthermore, like an early 10BASE5 or 10BASE2 network, Wi-Fi networks are half-duplex, with data travelling in only one direction at a time.

> 通过接入点连接的所有节点都成为单个冲突域的一部分，因为没有物理机制支持通过无线接入点进行以太网交换。此外，像早期的 10BASE5 或 10BASE2 网络一样，Wi-Fi 网络是半双工的，数据一次只能在一个方向上传输。

Access points have a number of jobs in a typical Wi-Fi network:

> 在典型的 Wi-Fi 网络中，接入点有许多工作：

- **Broadcasting its presence:** There is a type of 802.11 management frame called a _beacon frame_, which is broadcast periodically to let stations know that the network is there under a particular name and is available for connection. - **Station authentication and encryption:** This happens through Wi-Fi security protocols like EAP, WEP, WPA and WPA-2. Although it is possible to authenticate a station without encrypting subsequent traffic, authentication and encryption are generally handled together. The exceptions are some public hotspots in restaurants and coffee shops, which simply leave the AP open for everyone. This is a security risk, as others in the location can monitor network traffic using `sniffing` utilities. - **Forwarding frames between stations:** All frames travelling between stations associated to an access point travel via the access point, even if the two stations are within range of each other. The access point receives the frame from the sender, and repeats it to the receiver. - **Bridging to the wired portions of the network:** Because an AP connects a hubbed subnetwork to a switched network, it must perform the function of a network bridge. - **Media access control (MAC):** The access point may provide centralised control of media access, explicitly notifying stations when they are free to transmit. Few products implement this _point coordination function_ (PCF), relying instead on a distributed approach, described in the section `[Wi-Fi Distributed Media Access](#10_9781119183938-ch07.xhtml#c07-sec-0029).`

> -**广播其存在：**有一种类型的 802.11 管理帧，称为 _beacon frame_，它定期广播，以让电台知道网络以特定名称存在并可用于连接。-**站点身份验证和加密：**这通过 Wi-Fi 安全协议实现，如 EAP、WEP、WPA 和 WPA-2。虽然可以在不加密后续流量的情况下对站点进行认证，但认证和加密通常是一起处理的。例外的是餐馆和咖啡店的一些公共热点，这只是让美联社对所有人开放。这是一种安全风险，因为该位置的其他人可以使用 `嗅探` 实用程序监视网络流量。-**在站点之间转发帧：**在与接入点相关的站点之间传输的所有帧都通过接入点传输，即使这两个站点在彼此的范围内。接入点从发送方接收帧，并将其重复给接收方。-**桥接到网络的有线部分：**因为 AP 将一个子网络连接到一个交换网络，所以它必须执行网桥的功能。-**媒体访问控制(MAC)：**接入点可以提供媒体访问的集中控制，明确通知站点何时可以自由发送。很少有产品实现此点协调功能(PCF)，而是依赖于分布式方法，如 `[Wi-Fi 分布式媒体访问](#10_9781119183938-ch07.xhtml#c07-sec-0029)` 一节所述

Early in the Wi-Fi era, wireless access points were separate units, intended to be added onto an existing wired network with its own router/switch appliance. Since the mid-2000s, the router/switch and wireless access point have generally been combined into a single appliance that incorporates a network router governing an Internet connection, a wired Ethernet switch with several Category 5 connectors and a wireless access point. This combination appliance is called a _wireless router_. In early days wireless access points and wireless routers had external, `steerable` antennas. Today most wireless devices (whether wireless routers or mobile clients) have antennas hidden inside the device case.

> 在 Wi-Fi 时代早期，无线接入点是单独的单元，旨在通过自己的路由器/交换机设备添加到现有的有线网络中。自 2000 年代中期以来，路由器/交换机和无线接入点通常被合并为一个设备，该设备包括一个管理互联网连接的网络路由器、一个带有多个 5 类连接器的有线以太网交换机和一个无线接入点。这种组合设备称为无线路由器。在早期，无线接入点和无线路由器具有外部 `可操纵` 天线。如今，大多数无线设备(无论是无线路由器还是移动客户端)都将天线隐藏在设备外壳内。

### Infrastructure Networks vs. Ad Hoc Networks

The technical term for the sort of network shown in [Figure 7-14](#10_9781119183938-ch07.xhtml#c07-fig-0014) is _infrastructure network_. The term `infrastructure` is used because such a network is planned and constructed in a particular way, like a highway system.The access point and the stations associated with it form a _Basic Service Set_ (BSS); this is given a distinctive human-readable name, called the _Service Set_ _Identifier_ (SSID), which wireless stations use to locate and connect to the infrastructure network when they come online. Stations may connect to or disconnect from the AP, but the overall shape of the network does not change. In modern infrastructure networks, there is almost always a router associated with one or more access points, providing a connection to larger wired networks or the global Internet.

> 图 7-14](#10*9781119183938-ch07.xhtml#c07-fig-0014)中所示网络类型的技术术语是\_infrastructure network*。使用术语 `基础设施` 是因为这样的网络是以特定的方式规划和建设的，如高速公路系统。接入点和与之相关的站点构成了一个基本服务集(BSS)；这是一个独特的人类可读名称，称为 `服务集标识符` (SSID)，无线站在线时使用该名称定位并连接到基础设施网络。站点可以连接到 AP 或从 AP 断开，但网络的整体形状不会改变。在现代基础设施网络中，几乎总是有一个路由器与一个或多个接入点相关联，提供与更大的有线网络或全球互联网的连接。

From its inception, the 802.11 standard defined another, very different sort of network: the _ad hoc wireless network_. In an ad hoc network, wireless stations connect to one another, without the intermediation of an access point, forming an _Independent Basic Service Set_ (IBSS). This requires that the stations place their Wi-Fi client adapters in ad hoc mode instead of infrastructure mode. `Ad hoc` here indicates that the network is unplanned and assembled when necessary, but it vanishes when the stations disconnect. (Think of a network of laptops convened on a conference table to share documents pertinent to a meeting.) Any station in an ad hoc network may communicate with any other station in the network, just as would be possible in an infrastructure network, but in this case frames travel directly from the sender to the receiver rather than via an access point. See Figure 7-18.

> 802.11 标准从一开始就定义了另一种非常不同的网络：ad hoc 无线网络。在自组织网络中，无线站在没有接入点的情况下相互连接，形成了一个独立的基本服务集(IBSS)。这要求站点将其 Wi-Fi 客户端适配器置于临时模式而不是基础设施模式。这里的 `Ad-hoc` 表示网络是未计划的，并在必要时组装，但当站点断开连接时，它会消失。(想象一下在会议桌上召集的笔记本电脑网络，共享与会议相关的文件。)临时网络中的任何站点都可以与网络中的其他站点进行通信，就像在基础设施网络中一样，但在这种情况下，帧直接从发送方传输到接收方，而不是通过接入点。见图 7-18。

![[FIGURE 7-18:](#10_9781119183938-ch07.xhtml#rc07-fig-0018) An ad hoc wireless network](./media/images/9781119183938-fg0718.png)

Ad hoc networks have some advantages over infrastructure networks. For short-lived networks, they avoid the cost and effort of providing an access point. Also, peak throughput between two stations in a quiet network is doubled, as each frame is transmitted once (from sender to receiver) rather than twice (from sender to access point and from access point to receiver). However, they also suffer from some significant disadvantages:

> 与基础设施网络相比，自组织网络具有一些优势。对于短命网络，它们避免了提供接入点的成本和工作量。此外，安静网络中两个站点之间的峰值吞吐量增加了一倍，因为每个帧传输一次(从发送方到接收方)而不是两次(从接收方到发送方和从接入点到接收方)。然而，它们也有一些明显的缺点：

- All 802.11 wireless networks require that each station maintains an accurate current time, which is used for power management (allowing a station to `go to sleep` for a period when idle) and MAC. In an infrastructure network, each beacon frame transmitted by the access point contains a time, which the other stations in its BSS use to synchronise their clocks. In an ad hoc network this timing synchronisation function (TSF) must instead be implemented in a distributed fashion. Each station periodically attempts to transmit a beacon frame containing its current time; on receiving a beacon frame, a station updates its current time if the time indicated in the beacon frame is later than the current time. This scheme has been shown to scale poorly with the number of stations in the network; beyond a certain limit, contention causes beacons to be lost, and some stations (generally those with the fastest clocks) may become desynchronised from the rest of the network.

> -所有 802.11 无线网络都要求每个站点保持准确的当前时间，该时间用于电源管理(允许站点在空闲时 `休眠` 一段时间)和 MAC。在基础设施网络中，接入点发送的每个信标帧包含一个时间，其 BSS 中的其他站使用该时间来同步其时钟。在自组织网络中，该定时同步功能(TSF)必须以分布式方式实现。每个站周期性地尝试发送包含其当前时间的信标帧；在接收到信标帧时，如果信标帧中指示的时间晚于当前时间，则站更新其当前时间。该方案已被证明与网络中的站点数量相比规模较小；超过一定限制后，争用会导致信标丢失，一些站点(通常是时钟最快的站点)可能会与网络的其他站点失去同步。

- As stations in an ad hoc network must be within radio range of one another to communicate, the maximum separation between stations is roughly half that of an infrastructure network, where a well-placed access point can relay frames between stations on opposite sides of its coverage area. Furthermore, it is often possible to site an access point in an elevated position with good sight lines, extending its footprint.

> -由于自组织网络中的站点必须在彼此的无线电范围内进行通信，因此站点之间的最大间隔大约是基础设施网络的一半，在基础设施网络中，位置良好的接入点可以在其覆盖区域的相对两侧的站点之间中继帧。此外，通常可以在视线良好的高架位置设置接入点，从而扩大其占地面积。

Not all operating systems support ad hoc mode adequately, or at all, even though the client adapter hardware may be fully Wi-Fi compliant.

> 尽管客户端适配器硬件可能完全符合 Wi-Fi，但并非所有操作系统都充分或完全支持临时模式。

### Wi-Fi Distributed Media Access

As noted earlier, very few products implement the centralised PCF scheme for MAC. In the absence of PCF, stations are still able to regulate their access to the medium using the _distributed coordination function_ (DCF). While the DCF has some similarities to the CSMA/CD approach used in wired Ethernet, a key difference is that it is not generally feasible for a station to sense the wireless medium while transmitting, as the relatively strong local transmitted signal will tend to drown out the relatively weak signals from other stations. This precludes conventional collision detection.

> 如前所述，很少有产品实施 MAC 的集中式 PCF 方案。在没有 PCF 的情况下，站点仍然能够使用分配的协调功能\_(DCF)来调节对媒体的访问。虽然 DCF 与有线以太网中使用的 CSMA/CD 方法有一些相似之处，但一个关键的区别在于，站在传输时感知无线介质通常是不可行的，因为相对较强的本地传输信号将倾向于淹没来自其他站的相对较弱的信号。这排除了传统的碰撞检测。

In the absence of reliable collision detection, Wi-Fi networks instead employ _Carrier Sense Multiple Access/Collision Avoidance_ (CSMA/CA), which aims to _avoid_ packet collisions rather than detect them, which works this way: as in CSMA/CD, a station first listens to the channel to detect the signal of another station transmitting. This is called _physical carrier sensing_, because it involves the station actually detecting a signal on the medium. If such a signal is heard, the station wishing to transmit waits for a calculated period of time before listening again. It listens until the channel is clear, and then transmits the packet in its entirety. There is no `after the fact` collision detection, and no jam signal. (A jam signal is impossible because the Wi-Fi radio medium is half-duplex, and stations cannot listen for a jam signal while they are transmitting.)

> 在缺乏可靠的冲突检测的情况下，Wi-Fi 网络转而采用载波侦听多路访问/冲突避免(CSMA/CA)，其目的是避免数据包冲突，而不是检测数据包冲突。这被称为物理载波传感，因为它涉及站实际检测介质上的信号。如果听到这样的信号，则希望发送的站在再次收听之前等待计算的时间段。它监听直到信道畅通，然后完整地传输数据包。没有 `事后` 碰撞检测，也没有堵塞信号。(干扰信号是不可能的，因为 Wi-Fi 无线媒体是半双工的，电台在传输时无法监听干扰信号。)

There are a number of subtleties to the implementation of DCF:

> DCF 的实现有许多微妙之处：

- Rather than transmitting immediately when the medium becomes idle, a station must first wait for a fixed period known as the _distributed inter-frame space_ (DIFS); if the medium remains idle during the DIFS, the station then waits for a further random backoff period before transmitting. The DIFS allows higher-priority traffic, such as PCF frames or acknowledgment frames, preferential access to the medium. As in the case of wired Ethernet, the backoff period reduces the likelihood of two stations that are waiting for the medium to begin transmitting simultaneously, resulting in a collision.

> -不是在媒体空闲时立即发送，而是站必须首先等待一个固定的时间段，即分配的帧间间隔(DIFS)；如果媒体在 DIFS 期间保持空闲，则站在发送之前等待另一个随机退避周期。DIFS 允许更高优先级的业务，例如 PCF 帧或确认帧，优先访问媒体。与有线以太网的情况一样，退避周期减少了两个站点等待媒体同时开始传输的可能性，从而导致冲突。

- The backoff period is chosen randomly to lie within a contention window. Too small a window increases the likelihood that two stations will choose the same backoff value; too large a window degrades efficiency as the medium tends to spend more time idle. The solution is to use a dynamic window, which varies based on how much contention is encountered. Initially a station’s window is set to a fixed minimum value; each unsuccessful transmission doubles the size of the window, up to a fixed maximum value, whereas a successful transmission resets it to the minimum value.

> -退避周期被随机选择以位于竞争窗口内。窗口太小会增加两个站点选择相同退避值的可能性；窗口太大会降低效率，因为介质往往会花费更多的时间空闲。解决方案是使用动态窗口，该窗口根据遇到的争用量而变化。最初，站的窗口设置为固定的最小值；每一次不成功的传输都会使窗口的大小加倍，达到固定的最大值，而成功的传输会将其重置为最小值。

- Because dropped frames are far more frequent in wireless networks than wired ones, 802.11 implements a MAC-level acknowledgement and retransmission protocol. When a station successfully receives a frame, it waits for the _short inter-frame space_ (SIFS, where SIFS is less than DIFS, ensuring priority) and then sends an acknowledgement (ACK) frame. If a transmitting station fails to receive an ACK, it can conclude that a collision, or other interfering event, has occurred, and should then retransmit the frame.

> -由于无线网络中丢失帧的频率远高于有线网络，802.11 实现了 MAC 级别的确认和重传协议。当站点成功接收到帧时，它等待\_short 帧间间隔(SIFS，其中 SIFS 小于 DIFS，确保优先级)，然后发送确认(ACK)帧。如果发射站未能接收到 ACK，它可以断定发生了冲突或其他干扰事件，然后应该重新发送该帧。

Physically sensing the medium consumes power. To mitigate this, 802.11 implements a virtual carrier sensing mechanism: each frame contains a duration field, which allows the transmitter to indicate how long it (and any associated ACK frame) will occupy the medium. When a station receives a packet, even a packet intended for another station, it copies the duration field into a local timer known as the _network allocation vector_ (NAV), and postpones any transmissions until the timer has expired. Stations generally put their radio hardware into a low-power state while waiting.

> 物理感测介质消耗电力。为了缓解这一问题，802.11 实现了一种虚拟载波感知机制：每一帧都包含一个持续时间字段，允许发射机指示它(以及任何相关的 ACK 帧)将占用媒体多长时间。当一个站点接收到一个数据包，甚至是一个发送给另一个站点的数据包时，它将持续时间字段复制到一个称为 _network allocation vector_(NAV)的本地计时器中，并延迟任何传输，直到计时器过期。电台通常在等待时将其无线电硬件置于低功率状态。

### Carrier Sense and the Hidden Node Problem

Both infrastructure and ad hoc Wi-Fi networks have a similar problem: unless every station participating in the network can `hear` every other station, problems arise. The most important of these is the breakdown of the physical and virtual carrier sensing mechanisms described earlier in the section `[Wi-Fi Distributed Media Access](#10_9781119183938-ch07.xhtml#c07-sec-0029).` Such a breakdown leads to an increase in the packet collision rate. See Figure 7-19.

> 基础设施和临时 Wi-Fi 网络都有类似的问题：除非参与网络的每个站点都能 `听到` 其他站点的声音，否则问题就会出现。其中最重要的是前面在 `[Wi-Fi 分布式媒体访问](#10_9781119183938-ch07.xhtml#c07-sec-0029)` 一节中描述的物理和虚拟载波感知机制的故障。这种故障会导致数据包冲突率的增加。见图 7-19。

![[FIGURE 7-19:](#10_9781119183938-ch07.xhtml#rc07-fig-0019) The hidden node problem](./media/images/9781119183938-fg0719.png)

In [Figure 7-19](#10_9781119183938-ch07.xhtml#c07-fig-0019), wireless stations Ted and Alice are both connected to Arda, an AP physically about halfway between them. Ted and Alice are far enough apart so that their radios do not have the range to detect one another’s signals. Physical distance has `hidden` Ted from Alice and vice versa. This is called the _hidden node problem_. When two Wi-Fi nodes are hidden from one another, they cannot avoid transmitting colliding packets because they cannot monitor the channel for one another’s transmissions.

> 在[图 7-19](#10_9781119183938-ch07.xhtml#c07-fig-0019) 中，无线站 Ted 和 Alice 都连接到 Arda，这是一个物理上位于它们中间的 AP。泰德和爱丽丝相距很远，以至于他们的无线电无法探测到对方的信号。物理距离 `隐藏` 了泰德与爱丽丝之间的距离，反之亦然。这称为隐藏节点问题。当两个 Wi-Fi 节点彼此隐藏时，它们无法避免传输冲突的数据包，因为它们无法监控彼此传输的信道。

To address the hidden node problem, the 802.11 standard defines a virtual carrier sensing mechanism called _request to send/clear to send_ (RTS/CTS). Instead of simply listening for a clear channel, a transmitting station first performs a _handshake_ with the intended receiving station by sending it an RTS frame and waiting for a CTS frame in response. Only after this handshake is complete is data transmitted. This greatly mitigates the hidden node problem: in the example, although Alice cannot receive Ted’s RTS frame, she does receive Arda’s CTS response and is able to update her NAV value, which in turn causes her to postpone any future transmissions until Ted has finished.

> 为了解决隐藏节点问题，802.11 标准定义了一种称为 _request To send/clear To send_(RTS/CTS)的虚拟载波感知机制。发送站首先通过发送 RTS 帧并等待 CTS 帧作为响应来与预期接收站执行握手，而不是简单地监听清晰信道。只有在这个握手完成之后，数据才被传输。这大大缓解了隐藏节点问题：在示例中，尽管 Alice 无法接收 Ted 的 RTS 帧，但她确实接收到 Arda 的 CTS 响应，并能够更新她的 NAV 值，这反过来导致她推迟任何未来的传输，直到 Ted 完成。

Here’s how it works, broken out into steps (see Figure 7-20):

> 以下是它的工作原理，分为几个步骤(见图 7-20)：

1. When a station wants to send a packet, it first checks to see that the channel is quiet and waits for the DIFS before sending out an RTS frame. The duration field of the RTS frame is set to the total time required to complete the CTS, data transmission and ACK. 2. All stations that hear the RTS frame copy its duration field to their NAV timers. 3. Assuming that the destination station hears the RTS, it waits for the SIFS and replies with a CTS frame. The duration field of the CTS frame is set to the total time required to complete the data transmission and ACK (a slightly smaller value than in the RTS frame). 4. Some stations may not have heard the original RTS frame due to the hidden-node problem. If those stations hear the CTS frame, they copy its duration field into their NAV timers. 5. After the transmitting station receives CTS, it waits for a SIFS interval and begins sending the data frame proper. 6. When the receiving station has successfully received the data packet, it waits for another SIFS interval and sends an ACK frame back to the sending station. 7. By the time the ACK frame has been sent, all the NAV timers associated with the transaction will have timed out. All stations then wait for a DIFS interval before checking the channel for idleness and beginning the process again.

> 1.当站想要发送分组时，它首先检查信道是否安静，并在发送 RTS 帧之前等待 DIFS。RTS 帧的持续时间字段被设置为完成 CTS、数据传输和 ACK 所需的总时间。2.听到 RTS 帧的所有站将其持续时间字段复制到其 NAV 定时器。3.假设目的站听到 RTS，它等待 SIFS 并用 CTS 帧应答。CTS 帧的持续时间字段被设置为完成数据传输和 ACK 所需的总时间(略小于 RTS 帧中的值)。4.由于隐藏节点问题，一些站可能没有听到原始 RTS 帧。如果这些站听到 CTS 帧，它们将其持续时间字段复制到 NAV 定时器中。5.在发送站接收到 CTS 之后，它等待 SIFS 间隔并开始正确发送数据帧。6.当接收站成功地接收到数据分组时，它等待另一个 SIFS 间隔，并将 ACK 帧发送回发送站。7.当 ACK 帧被发送时，与事务相关联的所有 NAV 定时器都将超时。然后，所有站等待 DIFS 间隔，然后检查信道是否空闲并再次开始该过程。

![[FIGURE 7-20:](#10_9781119183938-ch07.xhtml#rc07-fig-0020) How the DCF coordinates a data packet transfer](./media/images/9781119183938-fg0720.png)

Of course, it’s still possible for two stations that are hidden from each other to send overlapping RTS frames, which will then collide and be dropped. The key benefit of the RTS/CTS protocol is that it reduces the period of vulnerability during which a hidden-node collision can occur from the comparatively long data transmission time to the comparatively short time required to transmit the RTS frame. Because the RTS/CTS handshake introduces a substantial overhead, and because its benefits are most pronounced for longer frames, it is common to apply a size threshold below which frames are transmitted without handshaking.Handshaking is often disabled completely for small networks, especially those with stations at fixed positions.

> 当然，两个相互隐藏的站点仍然有可能发送重叠的 RTS 帧，然后这些帧将发生冲突并被丢弃。RTS/CTS 协议的主要优点在于，它将隐藏节点冲突可能发生的脆弱期从相对长的数据传输时间缩短到传输 RTS 帧所需的相对短的时间。由于 RTS/CTS 握手引入了大量开销，并且其优点对于较长的帧最为明显，因此通常会应用大小阈值，低于该阈值的帧在不进行握手的情况下进行传输。对于小型网络，握手通常被完全禁用，尤其是那些站位于固定位置的网络。

### Fragmentation

Because longer frames have a proportionally higher chance of encountering interference and collisions than shorter frames, Wi-Fi networks provide a configurable option called a _fragmentation threshold_, which specifies the maximum size of frame that may be transmitted in one piece. A frame that is larger than the fragmentation threshold is broken into a numbered series of fragments, which are individually acknowledged and may be individually retransmitted if the acknowledgment does not arrive.

> 由于较长的帧比较短的帧遇到干扰和冲突的几率相对较高，因此 Wi-Fi 网络提供了一个可配置的选项，称为 _fragmentation threshold_，该选项指定了可以在一个帧中传输的最大帧大小。大于碎片阈值的帧被分割成一系列编号的碎片，这些碎片被单独确认，如果确认没有到达，则可以单独重新发送。

Fragments are transmitted on the medium separated by the SIFS, and so will not be interrupted by other DCF-coordinated traffic. The duration field of each transmitted fragmentspecifies the time required to transmit all the remaining fragments, rather than just the current one. When used with RTS/CTS handshaking, the duration field of the RTS frame specifies the total time required to transmit the CTS and all the fragments, so the medium is reserved for the entire duration of the fragmented transmission.

> 片段在由 SIFS 分离的媒体上传输，因此不会被其他 DCF 协调业务中断。每个传输片段的持续时间字段指定传输所有剩余片段所需的时间，而不仅仅是当前片段。当与 RTS/CTS 握手一起使用时，RTS 帧的持续时间字段指定传输 CTS 和所有片段所需的总时间，因此媒体被保留用于片段传输的整个持续时间。

### Amplitude Modulation, Phase Modulation and QAM

Before we discuss the operation of the various 802.11 physical layers, it is helpful to review a few basic radio concepts.

> 在我们讨论各种 802.11 物理层的操作之前，回顾一些基本的无线电概念是很有帮助的。

All radio technologies transmit information over the air by changing or _modulating_ one or more properties of a carrier wave in response to that information. Figure 7-21 illustrates two analogue modulation schemes that you have doubtless encountered in everyday life: amplitude modulation (AM) and frequency modulation (FM). The former holds the frequency of the carrier constant and varies its amplitude; the latter holds the amplitude constant and varies the carrier’s frequency about a central value.

> 所有无线电技术都通过响应于该信息改变或调制载波的一个或多个属性来通过空中传输信息。图 7-21 说明了您在日常生活中无疑遇到的两种模拟调制方案：调幅(AM)和调频(FM)。前者保持载波频率恒定并改变其幅度；后者保持幅度恒定，并围绕中心值改变载波频率。

![[FIGURE 7-21:](#10_9781119183938-ch07.xhtml#rc07-fig-0021) AM and FM analogue modulation](./media/images/9781119183938-fg0721.png)

In contrast with analogue modulation, whose goal is to encode a continuous and continually varying signal, digital modulation schemes transmit a discrete series of symbols (such as, in the simplest case, bits). In the rest of this discussion we are concerned with digital rather than analogue modulation.

> 与模拟调制(其目标是对连续不断变化的信号进行编码)不同，数字调制方案传输一系列离散的符号(例如，在最简单的情况下，比特)。在接下来的讨论中，我们关注的是数字调制而不是模拟调制。

Figure 7-22 illustrates four digital modulation schemes for transmitting binary data. The first two are digital equivalents of our familiar analogue schemes: _binary amplitude-shift keying_ (BASK)—sometimes also referred to as on-off keying (OOK)—transmits a binary 0 by emitting nothing and a binary 1 by emitting the carrier wave; _binary frequency-shift keying_ (BFSK) transmits 0s and 1s by changing the carrier frequency between two defined values. _Binary phase-shift keying_ (BPSK) transmits a binary 0 by emitting the carrier wave and a binary 1 by emitting the carrier wave phase-shifted by 180° (that is, inverted). In practice, _differential BPSK_ (DBPSK) is often used in place of BPSK; this eliminates the requirement for a fixed phase reference, encoding a binary 0 by continuing to transmit the carrier with its current phase and a binary 1 by shifting the current phase by 180°.

> 图 7-22 说明了用于传输二进制数据的四种数字调制方案。前两个是我们熟悉的模拟方案的数字等价物：二进制幅度移位键控(BASK)-有时也称为开-关键控(OOK)-通过不发射任何信号来发送二进制 0，通过发射载波来发送二进制 1 _二进制频移键控(BFSK)通过在两个定义值之间改变载波频率来发送 0 和 1_ 二进制相移键控(BPSK)通过发射载波传输二进制 0，通过发射相移 180°(即反相)的载波传输二进制 1。在实践中，常用差分 BPSK\_(DBPSK)代替 BPSK；这消除了对固定相位参考的要求，通过继续发送具有当前相位的载波来编码二进制 0，通过将当前相位偏移 180° 来编码二进制 1。

![[FIGURE 7-22:](#10_9781119183938-ch07.xhtml#rc07-fig-0022) BASK (OOK), BFSK, BPSK and DBPSK modulation](./media/images/9781119183938-fg0722.png)

The extension from binary to _m_-ary symbols (symbols that can take _m_ values) is straightforward. For mASK we permit _m_ possible amplitudes for the carrier, rather than simply on and off; for mFSK we permit _m_ possible frequencies; and for mPSK we allow phase shifts that are finer than just 180`. If we double _m_ from two to four we can transmit twice as much data over the same channel, as each symbol can represent two bits; doubling _m_ again gives a further 50% increase in capacity, as each symbol can now represent three bits. Ultimately our ability to keep increasing _m_ is limited by noise, which makes it hard for the receiver to accurately discriminate between increasingly finely spaced amplitude levels or frequency or phase shifts. This is in accordance with the Shannon-Hartley theorem, which informally states that the information-carrying capacity of a channel decreases with the signal-to-noise ratio of the channel.

> 从二进制符号到 _m_ 元符号(可以取 _m_ 值的符号)的扩展很简单。对于 mASK，我们允许载波有 _m_ 个可能的振幅，而不是简单地开和关；对于 mFSK，我们允许 _m_ 个可能的频率；对于 mPSK，我们允许比 180 `。如果我们将 _m_ 从 2 倍增加到 4 倍，我们可以在同一信道上传输两倍的数据，因为每个符号可以表示两个比特；将 _m_ 再次加倍，容量将进一步增加 50%，因为每个码元现在可以表示三个比特。最终，我们保持增加 _m_ 的能力受到噪声的限制，这使得接收机很难准确区分日益精细的间隔的幅度电平或频率或相移。这符合香农-哈特利定理，该定理非正式地指出，信道的信息承载能力随着信道的信噪比而降低。

We can, of course, choose to combine amplitude and phase modulation or keying. The resulting modulation scheme is referred to as _quadrature amplitude modulation_ (QAM), because modulating amplitude and phase together is equivalent to modulating the amplitude of two carriers that are 90° degrees out of phase (in quadrature) with each other, and summing the result. A digital QAM scheme is characterised by the set of discrete (phase, amplitude) values used. These are often represented as a _constellation_ (that is, a specific arrangement of values) in the complex plane, as shown in Figure 7-23. In the figure, distance from the origin corresponds to the amplitude, and angular position corresponds to the phase shift. In 16QAM, there are 16 different possible combinations of amplitude and angular position, allowing 16 bits to be encoded by a single pair of phase and amplitude values. QAM systems have to be carefully designed to keep noise immunity high. An engineer will generally attempt to maximise the Euclidean (straight line) distance between any two points in the constellation, maximising the chance that a receiver will be able to identify the intended point in the presence of noise.

> 当然，我们可以选择组合幅度和相位调制或键控。所得到的调制方案称为正交幅度调制(QAM)，因为一起调制幅度和相位相当于调制两个相位相差 90°(正交)的载波的幅度，并将结果相加。数字 QAM 方案的特征在于所使用的一组离散(相位、振幅)值。如图 7-23 所示，这些值通常表示为复平面中的一个 _constellation_(即值的特定排列)。在图中，距原点的距离对应于振幅，角位置对应于相移。在 16QAM 中，振幅和角位置有 16 种不同的可能组合，允许通过一对相位和振幅值对 16 位进行编码。QAM 系统必须精心设计，以保持高抗扰度。工程师通常会尝试最大化星座中任意两点之间的欧几里得(直线)距离，从而最大化接收器在存在噪声时能够识别目标点的可能性。

![[FIGURE 7-23:](#10_9781119183938-ch07.xhtml#rc07-fig-0023) Example constellations](./media/images/9781119183938-fg0723.png)

### Spread-Spectrum Techniques

The 2.4GHz and 5GHz ISM frequency bands used by Wi-Fi represent a particularly challenging environment in which to transmit data. Standards intended for use in these bands must offer some degree of resilience in the face of interference from a variety of sources:

> Wi-Fi 使用的 2.4GHz 和 5GHz ISM 频段代表了传输数据的特别具有挑战性的环境。这些频带中使用的标准必须在面对来自各种来源的干扰时提供一定程度的弹性：

- Other communication technologies that use the band (such as Bluetooth and ZigBee) - Non-communication devices such as microwave ovens - Clients attached to other Wi-Fi networks with overlapping channel assignments, which do not participate in this network’s collision-avoidance regime - Time-delayed reflections of signals (multipath interference; refer to [Figure 7-15](#10_9781119183938-ch07.xhtml#c07-fig-0015))

> -使用该频段的其他通信技术(如蓝牙和 ZigBee)-非通信设备，如微波炉-连接到具有重叠信道分配的其他 Wi-Fi 网络的客户端，不参与该网络的冲突避免机制-信号的时延反射(多径干扰；参见[图 7-15](#10_9781119183938-ch07.xhtml#c07-fig-0015))

Transmitters in the ISM bands are also subject to regulatory limits on the total amount of power that they may radiate in a given frequency window (spectral power density).

> ISM 频带中的发射机还受到其在给定频率窗口(频谱功率密度)中可能辐射的总功率的监管限制。

The Wi-Fi family of standards use a variety of _spread-spectrum_ techniques to address these challenges. As the name suggests, these spread a signal across a wider bandwidth than would otherwise be the case, offering improved resilience to interference (and in particular to narrowband interference that occupies only a small part of the frequency band) and reduced spectral power density. Three distinct techniques have been used:

> Wi-Fi 标准系列使用多种扩频技术来应对这些挑战。顾名思义，它们将信号扩展到比其他情况更宽的带宽上，从而提高了抗干扰能力(尤其是对仅占频带一小部分的窄带干扰)，并降低了频谱功率密度。使用了三种不同的技术：

- **Frequency-hopping spread spectrum (FHSS):** This approach is used only by the original 802.11 standard, at data rates of 1 to 2 Mbps. It uses 2- or 4-level FSK, and `hops` the frequency of the carrier wave to another point in the channel every 400ms, in a sequence that is known to both transmitter and receiver. - **Direct-sequence spread spectrum (DSSS):** This combines the stream of data bits with a faster stream of _chips_. In the case of 802.11b operating at 1 or 2 Mbps, a repeating 11-chip Barker code is combined with each bit. The closely related complementary-code keying scheme is used at higher data rates. - **Orthogonal frequency-division multiplexing (OFDM):** Data is split into many streams, each of which is modulated at a comparatively low rate onto one of many subcarriers spaced across the band. Since 802.11g, all standards have used OFDM, relying on wider bands, denser modulations and spatial diversity (which is described in more detail later in the next section) to deliver higher data rates in low-noise environments.

> -**跳频扩频(FHSS)：**此方法仅由原始 802.11 标准使用，数据速率为 1 至 2Mbps。它使用 2 级或 4 级 FSK，每 400ms 将载波频率 `跳变` 到信道中的另一个点，这是发射机和接收机都知道的序列**直接序列扩频(DSSS)：**这将数据比特流与更快的 _chips_。在 802.11b 以 1 或 2Mbps 操作的情况下，重复的 11 码片巴克码与每个比特组合。紧密相关的互补码键控方案用于更高的数据速率**正交频分复用(OFDM)：**数据被分成多个流，每个流以相对较低的速率调制到跨频带间隔的多个子载波之一上。自 802.11g 以来，所有标准都使用 OFDM，依靠更宽的频带、更密集的调制和空间分集(这将在下一节稍后详细描述)在低噪声环境中提供更高的数据速率。

### Wi-Fi Modulation and Coding in Detail

It’s time to take a look at the DSSS and OFDM modulation schemes used by 802.11b and 802.11g in more detail. Understanding the modulation schemes thoroughly is not necessary to use Wi-Fi, but it is necessary to comprehend the challenges of wireless networking, as compared to conventional wired Ethernet.

> 现在是时候更详细地了解 802.11b 和 802.11g 使用的 DSSS 和 OFDM 调制方案了。彻底理解调制方案对于使用 Wi-Fi 来说不是必要的，但与传统的有线以太网相比，理解无线网络的挑战是必要的。

At a data rate of 1 Mbps, the incoming bits are multiplied by a spreading sequence (in this case the 11-digit Barker code) running at a chipping rate of 11 Mbps; each bit in the source stream now corresponds to 11 bits in the spread stream. The spread stream is used to DBPSK-modulate a carrier wave. To achieve a doubling of throughput to 2 Mbps, DQPSK modulation replaces DBPSK. Figure 7-24 shows these two configurations. The 11-digit Barker code:

> 在 1Mbps 的数据速率下，输入比特乘以以 11Mbps 的码片速率运行的扩展序列(在此情况下为 11 位巴克码)；源流中的每个比特现在对应于扩展流中的 11 比特。扩展流用于 DBPSK 调制载波。为了实现吞吐量翻倍至 2Mbps，DQPSK 调制取代了 DBPSK。图 7-24 显示了这两种配置。11 位巴克码：

```
    +1 -1 +1 +1 -1 +1 +1 +1 -1 -1 -1
```

is used as the spreading sequence. It has extremely low autocorrelation: if you multiply the sequence by a shifted version of itself and sum the products, then for any shift that is not a multiple of 11 you get a maximum sum of between -1 and +1, whereas for a shift that is a multiple of 11, the products clearly sum to +11. For a shift of two, the products would be the following, which yields a sum of -1:

> 被用作扩展序列。它具有极低的自相关：如果你将序列乘以其自身的移位版本，并对乘积求和，那么对于任何不是 11 的倍数的移位，你得到的最大和在-1 和 +1 之间，而对于 11 的倍数移位，乘积的和显然是 +11。对于两次移位，乘积如下，其和为-1：

![[FIGURE 7-24:](#10_9781119183938-ch07.xhtml#rc07-fig-0024) Spread-spectrum transmission at 1 Mbps and 2 Mbps using 11-digit Barker code](./media/images/9781119183938-fg0724.png)

```
    <figure>
      ---- ---- ---- ---- ---- ---- ---- ---- ---- ---- ----   +1   -1   +1   +1   -1   +1   +1   +1   -1   -1   -1   ×    ×    ×    ×    ×    ×    ×    ×    ×    ×    ×   +1   +1   -1   +1   +1   +1   -1   -1   -1   +1   -1   =    =    =    =    =    =    =    =    =    =    =   +1   -1   -1   +1   -1   +1   -1   -1   +1   -1   +1   ---- ---- ---- ---- ---- ---- ---- ---- ---- ---- ----
    </figure>
```

The receiver demodulates the incoming signal, and multiplies the resulting spread stream by the spreading sequence to recover the original data, as shown in Figure 7-25; before doing so, it must synchronise its spreading sequence with that of the transmitter, a task that is simplified by the Barker code’s low autocorrelation. Multiplying by the spreading sequence in the receiver suppresses both inter-symbol interference due to multipath effects (because of the Barker code’s low autocorrelation) and other noise (because it broadens the noise spectrum, allowing it to be rejected by the integrating action of the receiver).

> 接收机解调输入信号，并将产生的扩展流与扩展序列相乘，以恢复原始数据，如图 7-25 所示；在这样做之前，它必须使其扩展序列与发射机的扩展序列同步，这一任务因巴克码的低自相关而简化。接收机中扩展序列的乘法抑制了由于多径效应(因为巴克码的低自相关)和其他噪声(因为它加宽了噪声频谱，允许它被接收机的积分作用所拒绝)引起的符号间干扰。

![[FIGURE 7-25:](#10_9781119183938-ch07.xhtml#rc07-fig-0025) The Direct-Sequence Spread-Spectrum (DSSS) process](./media/images/9781119183938-fg0725.png)

To achieve data rates of 5.5 Mbps and 11 Mbps with the same channel bandwidth, we require an approach with greater spectral efficiency. Complementary codes are sets of codes that, like the Barker code, have low autocorrelation (between a code and a shifted version of itself, as before) and cross-correlation (between codes in the set). Unlike the Barker code, however, the codes used here are polyphase codes: rather than being real numbers drawn from the set {-1, 1}, code values are complex numbers drawn from the set {-1, 1, -j, j}. When used as spreading sequences, they have the same advantages as the Barker code in terms of synchronisation and interference rejection, but as there is more than one code in the set, we are now able to convey additional information through our choice of the code used to spread a given symbol.

> 为了在相同的信道带宽下实现 5.5Mbps 和 11Mbps 的数据速率，我们需要一种具有更高频谱效率的方法。互补码是与巴克码一样具有低自相关(如前所述，在码与移位版本之间)和互相关(集合中的码之间)的码集。然而，与巴克码不同，这里使用的码是多相码：码值不是从集合{-1，1}中提取的实数，而是从集合{-1,1，-j}中提取出的复数。当用作扩频序列时，它们在同步和干扰抑制方面具有与巴克码相同的优点，但由于集合中有不止一个码，我们现在能够通过选择用于扩频给定符号的码来传递附加信息。

To transmit at 11 Mbps, we group the incoming bits into 8-bit bytes. Six bits are used to select one of 64 8-bit complementary codes, and the remaining two bits are used to phase-modulate the entire code. The chipping rate remains 11 Mbps, and as eight bits are transmitted for every eight chips, the data throughput is also 11 Mbps. When transmitting at 5.5 Mbps, the number of codes is reduced to four.

> 为了以 11 Mbps 的速率传输，我们将传入的比特分组为 8 位字节。六位用于选择 64 个 8 位互补码中的一个，其余两位用于对整个码进行相位调制。芯片速率保持为 11 Mbps，每 8 个芯片传输 8 个比特，数据吞吐量也为 11 Mbps。当以 5.5 Mbps 传输时，代码的数量减少到四个。

The 802.11g standard supports data rates of up to 54 Mbps on the 2.4GHz band. To achieve this, it adopts an OFDM modulation scheme first used (on the 5GHz band) by 802.11a. Each 20MHz channel is divided into 52 subchannels; four channels are reserved for pilot signals, and data is modulated onto the remaining 48 subcarriers using 64-QAM (for 52 Mbps and 48 Mbps modes), 16-QAM (for 36 Mbps and 24 Mbps), QPSK (for 18 Mbps and 12 Mbps) or BPSK (for 9 Mbps and 6 Mbps). A symbol is transmitted every 4μs, so the raw throughput in 64QAM mode is given by

> 802.11g 标准支持 2.4GHz 频带上高达 54 Mbps 的数据速率。为了实现这一点，它采用了 802.11a 首次使用的 OFDM 调制方案(在 5GHz 频带上)。每个 20MHz 信道被划分为 52 个子信道；为导频信号保留四个信道，并且使用 64-QAM(对于 52Mbps 和 48Mbps 模式)、16-QAM(用于 36Mbps 和 24Mbps)、QPSK(对于 18Mbps 和 12Mbps)或 BPSK(对于 9Mbps 和 6Mbps)将数据调制到剩余的 48 个子载波上。每 4μs 发送一个符号，因此 64QAM 模式下的原始吞吐量由下式给出

> 48 channels × 250,000 symbols/s × 6 bits/symbol = 72 Mbps

The difference between the raw throughput of 72 Mbps and the actual throughput of 54 Mbps is accounted for by the use of a FEC code with a code rate of 3/4 (that is, four bits are transmitted for every three bits of data). Each 802.11g data rate uses forward error correction, with code rates of 1/2 (for 24 Mbps, 12 Mbps and 6 Mbps), 2/3 (for 48 Mbps) or 3/4 (for 54 Mbps, 36 Mbps, 18 Mbps and 9 Mbps).

> 72Mbps 的原始吞吐量和 54Mbps 的实际吞吐量之间的差异通过使用 3/4 码率的 FEC 码(即，每三位数据传输四位)来解释。每个 802.11g 数据速率使用前向纠错，码率为 1/2(对于 24 Mbps、12 Mbps 和 6 Mbps)、2/3(对于 48 Mbps)或 3/4(对于 54 Mbps、36 Mbps、18 Mbps 和 9 Mbps)。

The OFDM scheme provides resilience both to narrowband interference and to frequency-selective fading; the FEC code allows the receiver to reconstruct a certain amount of missing data from one or more corrupted subcarriers. The relatively slow modulation rate permits the insertion of a guard interval between each symbol, reducing inter-symbol interference.

> OFDM 方案提供了对窄带干扰和频率选择性衰落的弹性；FEC 码允许接收机从一个或多个损坏的副载波重建一定量的丢失数据。相对较慢的调制速率允许在每个符号之间插入保护间隔，从而减少符号间干扰。

### How Wi-Fi Connections Happen

Connecting a Wi-Fi device to a wireless access point is not as simple as it might seem at first. There may be multiple APs and multiple client adapters visible in the same physical location. APs and clients may be scattered across several channels. Not all clients may be authorised to connect to certain APs. At the highest level, resolving such issues is a three-step process:

> 将 Wi-Fi 设备连接到无线接入点并不像最初看起来那么简单。在同一物理位置可能有多个 AP 和多个客户端适配器可见。AP 和客户端可能分散在几个信道上。并非所有客户端都可以被授权连接到某些 AP。在最高级别，解决此类问题需要三个步骤：

1. Client adapters need to determine which APs are available on what channels. This process is called _scanning_. 2. The APs need to be able to determine which clients are theirs, and vice versa. This process is called _authentication_. 3. After authentication, the authenticated client may connect to the AP that authenticated it. This process is called _association_.

> 1.客户端适配器需要确定哪些 AP 在哪些信道上可用。此过程称为 _scanning_。2.AP 需要能够确定哪些客户是他们的，反之亦然。此过程称为 _authentication_。3.认证后，经过认证的客户端可以连接到对其进行认证的 AP。此过程称为 _association_。

Scanning may be active or passive. In _passive scanning_, an AP is configured to periodically broadcast a frame containing its SSID. Client adapters listen for these broadcast frames across all channels and build a list. If they have connected to an AP before, they will choose that AP. If they don’t see an SSID that they’ve connected to before, they will attempt to connect to the AP with the strongest signal. How the connection happens and how the user gets involved are implementation dependent. Most modern Wi-Fi software has a _Connect Automatically?_ dialog that appears on first connection and requires user confirmation before automatic connections can happen in the future. The user of the client adapter’s computer may also be given a chance to choose an AP from the list that the client gathers from broadcast SSID frames.

> 扫描可以是主动或被动的。在 _passive scanning_ 中，AP 被配置为定期广播包含其 SSID 的帧。客户端适配器在所有频道上侦听这些广播帧并构建列表。如果他们以前连接过 AP，他们将选择该 AP。如果他们没有看到以前连接过的 SSID，他们将尝试连接到具有最强信号的 AP。连接的发生方式和用户的参与方式取决于实现。大多数现代 Wi-Fi 软件都有一个*自动连接？*对话框，该对话框出现在第一次连接时，需要用户确认才能在将来进行自动连接。客户端适配器的计算机的用户还可以获得从客户端从广播 SSID 帧收集的列表中选择 AP 的机会。

In _active scanning_, a client adapter sends out a _probe request frame_ to all APs within range. The probe request frame may contain the SSID of a preferred AP, in essence asking, `Are you there, ` blackwave `?` If the `blackwave` AP is out there, it issues a probe response to the client. The probe request frame may alternatively contain a null (empty) SSID field, which amounts to asking, `Who’s out there?` In that case, any AP within range may send a probe response back to the client, which in most cases will choose the AP with the strongest signal.

> 在 _active scanning_ 中，客户端适配器向范围内的所有 AP 发送\_probe 请求帧。探测请求帧可能包含首选 AP 的 SSID，本质上是询问 `你在吗，` blackwave `？` 如果 `blackwave` AP 在那里，它会向客户端发出探测响应。探测请求帧也可以包含空(空)SSID 字段，这相当于询问 `谁在外面？` 在这种情况下，范围内的任何 AP 都可以向客户端发送探测响应，客户端在大多数情况下将选择信号最强的 AP。

Active scanning with a null SSID is done because in some wireless networks, the APs are configured _not_ to broadcast their SSIDs. An active scan is thus the only way for a client to determine what APs are within range. In most home networks and `coffee shop` Wi-Fi providers, the APs broadcast their SSIDs, and passive scanning is sufficient.

> 使用空 SSID 进行主动扫描是因为在某些无线网络中，AP 被配置为不广播其 SSID。因此，主动扫描是客户端确定哪些 AP 在范围内的唯一方法。在大多数家庭网络和 `咖啡店` Wi-Fi 提供商中，AP 广播其 SSID，被动扫描就足够了。

After a client adapter identifies the AP that it wants to connect to, the authentication process determines whether the connection is authorised. There are two types of authentication: open and shared-key. _Open authentication_ does not depend on passwords. The client sends an authentication request frame to the AP. This frame includes the client’s MAC address. An AP may be configured to exclude certain client MAC addresses, or only permit certain client MAC addresses. Depending on how the AP is configured, it either grants or refuses the client’s authentication request. If it refuses, the conversation is over, and the connection does not happen. If the AP grants the request, the process moves on to association.

> 在客户端适配器识别出它想要连接到的 AP 之后，身份验证过程确定该连接是否被授权。有两种类型的身份验证：开放密钥和共享密钥\_开放式身份验证不依赖于密码。客户端向 AP 发送认证请求帧。此帧包括客户端的 MAC 地址。AP 可以被配置为排除某些客户端 MAC 地址，或者仅允许某些客户端 MAC。根据 AP 的配置方式，它会批准或拒绝客户端的身份验证请求。如果拒绝，对话结束，连接不会发生。如果 AP 批准了该请求，则流程继续进行关联。

Authentication by MAC address is done less and less often, because clients transmit their MAC addresses as _cleartext_ (that is, without encryption) and an attacker can compile a list of valid MAC addresses with software that simply monitors the channel. Because many client adapters allow users to change their MAC addresses to arbitrary values, the attacker could then `spoof` a legitimate MAC address and connect to the network.

> 通过 MAC 地址进行身份验证的次数越来越少，因为客户端将其 MAC 地址作为 _cleartext_(即，不加密)传输，攻击者可以使用简单监控信道的软件来编译有效 MAC 地址列表。由于许多客户端适配器允许用户将其 MAC 地址更改为任意值，因此攻击者可以 `欺骗` 合法的 MAC 地址并连接到网络。

_Shared-key authentication_ uses one of several protocols that involve encryption. The most common protocol for small networks today is called WPA-2, which has been mandatory on new-build Wi-Fi gear since 2006. (WPA-2 is covered in more detail in the next section.) Large corporate networks and those with strong security requirements use a separate authentication server (often one called RADIUS) that implements an IEEE authentication standard called 802.1X. Small networks handle shared-key authentication directly between AP and client. A conversation occurs between AP and client, in which the AP and client require one another to complete a cryptographic challenge. If both AP and client possess the same shared key, the challenge can be completed successfully and authentication is granted. Thereafter, all communication between AP and client is encrypted.

> \_共享密钥认证使用涉及加密的几种协议之一。如今，小型网络最常见的协议是 WPA-2，自 2006 年以来，它一直是新建 Wi-Fi 设备的强制性协议。(WPA-2 将在下一节中详细介绍。)大型公司网络和具有强大安全要求的公司网络使用单独的认证服务器(通常称为 RADIUS)，该服务器实现 IEEE 认证标准 802.1X。小型网络直接处理 AP 和客户端之间的共享密钥认证。AP 和客户端之间发生对话，其中 AP 和客户端要求彼此完成加密质询。如果 AP 和客户端都拥有相同的共享密钥，则可以成功完成质询并授予身份验证。此后，AP 和客户端之间的所有通信都被加密。

The final connection step is association. After the AP and client adapter have authenticated one another, the client sends the AP an _association request frame_. If granted, the association process goes to completion, after which the client may obtain network configuration parameters and an IP address through the network’s DHCP server. The AP may still refuse association for other reasons; for example, if the number of clients associated with it has already reached a pre-set maximum value. In most cases, however, the association request is granted, and the client connects.

> 最后一个连接步骤是关联。在 AP 和客户端适配器相互认证之后，客户端向 AP 发送一个 _association 请求帧_。如果被授权，则关联过程进行到完成，之后客户端可以通过网络的 DHCP 服务器获得网络配置参数和 IP 地址。AP 仍然可以基于其他原因拒绝关联；例如，如果与它相关联的客户端的数量已经达到预设的最大值。然而，在大多数情况下，关联请求被批准，客户端连接。

### Wi-Fi Security

There is some inherent security in wired networks: without physical access to a network jack or network equipment, connecting to the network is impossible. Wi-Fi signals can pass through walls and do not limit connections to physical jacks, so security becomes a matter of great importance. The original 802.11 standard specified a simple encryption mechanism called _wired equivalent privacy_ (WEP). A WEP key is a string of hexadecimal digits and not a conventional password. Some Wi-Fi hardware incorporated key generators to convert a human-readable password or passphrase to a hexadecimal WEP key.

> 有线网络有一些固有的安全性：如果没有对网络插孔或网络设备的物理访问，就不可能连接到网络。Wi-Fi 信号可以穿过墙壁，并且不限制与物理插孔的连接，因此安全性变得非常重要。最初的 802.11 标准规定了一种简单的加密机制，称为 _wired equivalent privacy_(WEP)。WEP 密钥是十六进制数字串，而不是常规密码。一些 Wi-Fi 硬件结合了密钥生成器，将人类可读的密码或口令转换为十六进制 WEP 密钥。

In 2001, security researchers found a flaw in WEP’s encryption algorithm that allowed a wireless access point protected by WEP to be cracked after as little as 10 minutes of examining encrypted packets passing over the network. Once the nature of the flaw became generally known, WEP became useless. In 2004, the 802.11 committee ratified addendum 802.11i, which became known as _Wi-Fi Protected Access version 2_, or WPA-2. WPA-2 replaced a short-lived interim solution called WPA, which was not as strong; like WEP, it’s no longer used. WPA-2 uses a 256-bit encryption protocol called the _Advanced Encryption Standard_ (AES). AES is a _block cipher_ that encrypts and decrypts data a block at a time. Older Wi-Fi protocols such as WEP and WPA used _stream ciphers_, which deal with single characters at a time and are much more vulnerable to attack.

> 2001 年，安全研究人员在 WEP 的加密算法中发现了一个漏洞，该漏洞允许 WEP 保护的无线接入点在检查通过网络的加密数据包仅 10 分钟后被破解。一旦缺陷的性质广为人知，WEP 就变得毫无用处。2004 年，802.11 委员会批准了 802.11i 附录，该附录被称为 _Wi-Fi 保护访问版本 2_ 或 WPA-2。WPA-2 取代了一种短期的临时解决方案，称为 WPA，但它并没有那么强大；与 WEP 一样，它不再使用。WPA-2 使用称为高级加密标准(AES)的 256 位加密协议。AES 是一种分块密码，一次对一个数据块进行加密和解密。WEP 和 WPA 等较旧的 Wi-Fi 协议使用流密码，一次只能处理单个字符，更容易受到攻击。

WPA-2 allows for ASCII keyphrases up to 63 characters in length, and if the keyphrase consists of random characters, 20 to 30 characters is generally sufficient for home networks.

> WPA-2 允许 ASCII 密钥短语长度最多为 63 个字符，如果密钥短语由随机字符组成，则家庭网络通常需要 20 到 30 个字符。

> [!NOTE]
> that attackers do not simply transmit passwords to a wireless router one after the other until they find one that works. Instead, a utility called a _packet sniffer_ captures encrypted packets off the air and saves them to disk as files. Then, an _offline brute-force attack_ can be attempted. In this type of attack, dictionaries of ordinary words and commonly used passwords are tried against the encrypted packets stored on an attacker’s computer, using a fast application that can attempt tens of thousands of passwords per second. If the attacker is willing to let the software keep trying for weeks or months, a weak password or a concatenation of common dictionary words could be vulnerable. There is some comfort in the `low-hanging fruit` effect: because some people use short or otherwise weak passwords, attackers are less likely to spend months of time on a brute-force attack against a strong password. That assumes that you are not a corporate or military site storing important information. Few attackers will waste that much time breaking your password just to steal your MP3s.

Not all parts of WPA-2 are as secure as the main encryption algorithm. In 2011, a critical flaw was discovered in a WPA-2 accessory technology called Wi-Fi Protected Setup (WPS) that runs in the firmware of wireless routers and allows easy password distribution for small networks. It was found that the WPS protocol `leaks` portions of a PIN code, and allows a brute-force attack to succeed in as little as two hours. WPS is now considered compromised and security professionals recommend that it be disabled in devices that include it.

> 并非 WPA-2 的所有部分都像主要加密算法那样安全。2011 年，一种名为 Wi-Fi 保护设置(WPS)的 WPA-2 附件技术中发现了一个关键缺陷，该技术在无线路由器的固件中运行，允许在小型网络中轻松分发密码。发现 WPS 协议 `泄露` 了部分 PIN 码，并允许暴力攻击在两小时内成功。WPS 现在被认为受到了危害，安全专家建议在包含 WPS 的设备中禁用 WPS。

On the client side, WPA-2 is implemented as a piece of software called a _supplicant_, which runs on the computer that wants to connect to the network and not in the client adapter itself. For Linux distributions (including Raspbian) the supplicant software is called `wpa_supplicant`, and its configuration file `wpa_supplicant.conf` is located in the folder `/etc/wpa_supplicant`. The supplicant `asks` its chosen AP for authentication, and then engages in the WPA-2 protocol with the AP. Some supplicant implementations include a graphical user interface (GUI) for management, whereas others are command-line based and read keyphrases and other information from an editable configuration file.

> 在客户端，WPA-2 被实现为一个名为 _supplicant_ 的软件，它运行在想要连接到网络的计算机上，而不是在客户端适配器本身中。对于 Linux 发行版(包括 Raspbian)，供应商软件名为 `wpa_supplicant` ，其配置文件 `wpa\usupplicant.conf` 位于文件夹 `/etc/wpa_ssupplicant` 中。请求者 `请求` 其选择的 AP 进行身份验证，然后与 AP 进行 WPA-2 协议。一些请求方实现包括用于管理的图形用户界面(GUI)，而另一些则基于命令行，并从可编辑的配置文件中读取关键短语和其他信息。

### Wi-Fi on the Raspberry Pi

Most models of the Raspberry Pi have a wired Ethernet port that is standard and will work without any tweaking on Linux distributions like Raspbian. (The older Model A boards and the Raspberry Pi Zero do not have Ethernet ports.) If you connect your Raspberry Pi board via cable to your router’s Ethernet port with a running DHCP server, Raspbian requests DHCP configuration, which includes a local IP address. After DHCP has configured Raspbian’s networking parameters, the board should be able to communicate with other nodes on your local network as well as the Internet at large, using its IP address.

> 大多数 Raspberry Pi 型号都有一个标准的有线以太网端口，在像 Raspbian 这样的 Linux 发行版上无需任何调整即可工作。(旧的 A 型板和 Raspberry Pi Zero 没有以太网端口。)如果您通过电缆将 Raspberrry Pi 板连接到路由器的以太网端口，并使用正在运行的 DHCP 服务器，Raspbian 会请求 DHCP 配置，其中包括本地 IP 地址。DHCP 配置 Raspbian 的网络参数后，该板应该能够使用其 IP 地址与本地网络上的其他节点以及整个 Internet 进行通信。

Raspbian (and most Unix-derived operating systems) includes a command-line utility called `ifconfig`, which allows you to display the configuration of your wired Ethernet port. (There is a better configuration utility for Wi-Fi, which we’ll get to shortly.) Simply open a terminal window and execute this command:

> Raspbian(以及大多数 Unix 衍生操作系统)包括一个名为 `ifconfig` 的命令行实用程序，它允许您显示有线以太网端口的配置

```
    ifconfig eth0
```

Here, `eth0` is the default name of the Raspberry Pi’s wired Ethernet port. The utility displays the current status of the port, including its MAC address and IP address. If you’re not using the wired Ethernet port on your Raspberry Pi, it’s a good idea to disable it, especially if you intend to use a Wi-Fi adapter. You disable `eth0` with `ifconfig`:

> 这里，`eth0` 是复盆子 Pi 的有线以太网端口的默认名称。该实用程序显示端口的当前状态，包括其 MAC 地址和 IP 地址。如果你没有使用 Raspberry Pi 上的有线以太网端口，最好禁用它，特别是如果你打算使用 Wi-Fi 适配器。使用 `ifconfig` 禁用 `eth0` ：

```
sudo ifconfig eth0 down
```

> [!NOTE]
> that changing parameters (as distinct from merely displaying them) requires the use of admin privileges, via `sudo`. To enable the port again, enter this command:

```
sudo ifconfig eth0 up
```

Unless you have a Raspberry Pi 3 (which has both Wi-Fi and Bluetooth right on the circuit board), you’ll have to obtain a USB Wi-Fi client adapter. Make sure that your board is running the latest image of Raspbian, which includes most available Wi-Fi drivers and tools. There are extremely compact Wi-Fi client adapters that can be plugged into one of the two on-board USB ports or into a powered USB hub. You can find a list of other tested and known-compatible Wi-Fi client units at [`http://elinux.org/RPi_USB_Wi-Fi_Adapters`](http://elinux.org/RPi_USB_Wi-Fi_Adapters).

> 除非你有 Raspberry Pi 3(电路板上有 Wi-Fi 和蓝牙)，否则你必须获得 USB Wi-Fi 客户端适配器。确保您的董事会正在运行 Raspbian 的最新图像，其中包括大多数可用的 Wi-Fi 驱动程序和工具。有非常紧凑的 Wi-Fi 客户端适配器，可以插入两个板载 USB 端口之一或电源 USB 集线器。您可以在[`http://elinux.org/RPi_USB_Wi-Fi_Adapters`](http://elinux.org/RPi_USB_Wi-Fi_Adapters).

Make sure that your board is running from a robust power source like a powered hub. No matter how compact, a Wi-Fi adapter includes a microwave radio transmitter, and it needs a certain amount of current to do its job. Adding such an adapter to a board that’s close to overloading its power supply is almost guaranteed to make it fail. When choosing a power supply for a Raspberry Pi installation, always err on the side of more current rather than less. Most of the common problems getting a Raspberry Pi system to work stem from inadequate current from the power supply.

> 确保您的电路板运行时使用强大的电源，如电源集线器。无论多紧凑，Wi-Fi 适配器都包括一个微波无线电发射器，它需要一定的电流来完成工作。在接近电源过载的电路板上添加这样的适配器几乎可以保证会导致故障。当为 Raspberry Pi 安装选择电源时，总是错误地选择更多的电流而不是更少的电流。Raspberry Pi 系统的大多数常见问题都源于电源电流不足。

The WPA-2 supplicant that comes preinstalled with Raspbian has a GUI, and if Raspbian has a driver for your client adapter, connecting to your access point can be done entirely using the GUI. Follow these steps:

> Raspbian 预装的 WPA-2 请求程序具有 GUI，如果 Raspbian 为您的客户端适配器提供了驱动程序，则可以完全使用 GUI 连接到您的接入点。遵循以下步骤：

1. Run the supplicant software by launching Wi-Fi Config from the Raspbian desktop. The `wpa_gui` main window is shown in Figure 7-26.

> 1.从 Raspbian 桌面启动 Wi-Fi 配置，运行请求者软件。`wpa_gui` 主窗口如图 7-26 所示。

2. Click the Scan button. The supplicant scans for available APs and displays a list in a new window. See Figure 7-27.

> 2.单击扫描按钮。请求者扫描可用的 AP 并在新窗口中显示列表。见图 7-27。

3. Assuming that one of the listed APs is your own, double-click its line in the `Scan` window. The `NetworkConfig` window opens (see Figure 7-28). If you don’t see your AP listed, your Raspberry Pi may be too far away, or there may be some configuration conflict.

> 3.假设列出的 AP 之一是您自己的，请在 `扫描` 窗口中双击其行。`NetworkConfig` 窗口打开(见图 7-28)。如果你没有看到你的 AP 列表，你的树莓派可能太远了，或者可能有一些配置冲突。

4. Enter your AP’s shared key in the PSK field.

> 4.在 PSK 字段中输入 AP 的共享密钥。

5. Click Add. Assuming you entered the shared key correctly, the supplicant connects to your AP. At that point, the Status tab of the `wpa_gui` main window shows `Completed (Station)` in the Status field.

> 5.单击 `添加` 。假设您正确输入了共享密钥，请求者将连接到您的 AP。此时，`wpa_gui` 主窗口的 `Status` 选项卡在 `Status` 字段中显示 `Completed(Station)` 。

6. Test your new connection by launching Midori and accessing any web page. You can use the `wpa_gui` application for ongoing configuration as well, say if you install a new wireless access point or change your SSID or shared key. For simple status display, another Linux command-line utility provides more information. After you have your Wi-Fi connection established and configured, open a terminal window and enter the following command:

> 6.通过启动 Midori 并访问任何网页来测试您的新连接。您也可以将 `wpa_gui` 应用程序用于正在进行的配置，例如安装新的无线接入点或更改 SSID 或共享密钥。对于简单的状态显示，另一个 Linux 命令行实用程序提供了更多信息。建立并配置 Wi-Fi 连接后，打开终端窗口并输入以下命令：

`iwconfig ![[FIGURE 7-26:](#10_9781119183938-ch07.xhtml#rc07-fig-0026) The ` wpa_gui` main window](./media/images/9781119183938-fg0726.png)

> `iwconfig！[[图 7-26:](#10_9781119183938-ch07.xhtml#rc07-fig-0026) ` wpa_gui'主窗口](./media/images/978111918938-fg0726.png)

![[FIGURE 7-27:](#10_9781119183938-ch07.xhtml#rc07-fig-0027) The `Scan` window](./media/images/9781119183938-fg0727.png)

![[FIGURE 7-28:](#10_9781119183938-ch07.xhtml#rc07-fig-0028) The `Network Config` window](./media/images/9781119183938-fg0728.png)

The utility displays an eight-line text summary including the AP’s SSID, the wireless technology (a/b/g/n), the AP’s MAC address, the current bit rate, indicators for signal level, link quality and cumulative counts for various errors.

> 该实用程序显示八行文本摘要，包括 AP 的 SSID、无线技术(a/b/g/n)、AP 的 MAC 地址、当前比特率、信号电平指示符、链路质量和各种错误的累积计数。

### Even More Networking

Networking is a field that is both broad and deep, and there’s a great deal to learn beyond what we can show in one chapter. Here are some useful topics for independent research:

> 网络是一个既广泛又深入的领域，除了我们可以在一章中展示的内容之外，还有很多东西需要学习。以下是一些对独立研究有用的主题：

- **Samba:** A software package that allows Linux operating systems like Raspbian to transfer files with Windows or other non-Linux operating systems. Samba is free and may be installed without charge from the Raspberry Pi repositories.
- **Ethernet bridges:** Special Ethernet appliances that forward Ethernet frames from one physical medium to another. This is often from Category 5 cabling to Wi-Fi or vice versa, but there are bridges that can implement Ethernet over residential power wiring, and allow a Category 5 connection on both ends. (As a category, this is called _Powerline Networking_, and it’s often used for bringing a network connection to locations in a building where Wi-Fi cannot reach.) With special software, a Raspberry Pi board can be configured to bridge between wired Ethernet and Wi-Fi.
- **Power over Ethernet (PoE):** A technology that uses special adapters to send a modest amount of current through unused twisted pairs in a Category 5 Ethernet cable, or over the signalling conductors if there are no unused pairs available. Because the POE voltage is the same on both pairs of the twisted pair carrying data, the NICs ignore the voltage, which does not interfere with data. Implemented correctly, PoE can allow an Ethernet bridge or even an entire Raspberry Pi computer to be located on a mast or some other location where conventional power isn’t available.

> - **Samba:**允许 Raspbian 等 Linux 操作系统与 Windows 或其他非 Linux 操作系统传输文件的软件包。Samba 是免费的，可以从 Raspberry Pi 存储库免费安装。
> - **以太网网桥：**将以太网帧从一个物理介质转发到另一个物理媒介的特殊以太网设备。这通常是从 5 类布线到 Wi-Fi，反之亦然，但有一些网桥可以在住宅电力布线上实现以太网，并允许在两端进行 5 类连接。(作为一个类别，这被称为 _Powerline Networking_，通常用于将网络连接带到建筑物中 Wi-Fi 无法到达的位置。)通过特殊软件，复盆子 Pi 板可以配置为在有线以太网和 Wi-Fi 之间架起桥梁。
> - **以太网供电(PoE)：**一种使用特殊适配器通过 5 类以太网电缆中未使用的双绞线发送适度电流的技术，如果没有未使用的绞线，则通过信令导线发送适度电流。由于承载数据的双绞线对上的 POE 电压相同，NIC 忽略电压，这不会干扰数据。正确实施后，PoE 可以允许以太网网桥甚至整个 Raspberry Pi 计算机位于桅杆上或其他常规电源不可用的位置。

There are also a great many devices like cameras and sensors that can be attached to a computer network through a Category 5 Ethernet cable. More and more everyday household devices are joining the `Internet of Things` and may be controlled via Wi-Fi from computers of all sorts. Learning Ethernet and TCP/IP thoroughly will allow you to extend your reach anywhere that Ethernet cables—or Wi-Fi microwaves—can reach.

> 还有很多设备，如摄像头和传感器，可以通过 5 类以太网电缆连接到计算机网络。越来越多的日常家用设备正在加入 `物联网` ，并且可以通过各种计算机的 Wi-Fi 进行控制。彻底学习以太网和 TCP/IP 将使您能够在以太网电缆或 Wi-Fi 微波可以到达的任何地方扩展您的访问范围。
