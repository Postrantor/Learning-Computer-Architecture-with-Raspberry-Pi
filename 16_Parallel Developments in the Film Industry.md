> [!NOTE]
> 文章中简单提及到了集中技术，如共享内存，DMA，PCIE
> 主要是对图形技术进行了较为系统深刻的讨论

# Parallel Developments in the Film Industry

The need for computer generated images (CGI) drove the film industry to pioneer techniques that underpin modern 3D graphics hardware, from the GRAphics Symbiosis System (GRASS)-based transformations used to model the Death Star for the 1977 release of _Star Wars_, to the 15 minutes of computer-generated animation employing depth-cueing for 1984’s _Tron_, to the 1993 full photorealism of the dinosaurs in _Jurassic Park_. Similar developments for industrial applications were equally groundbreaking; Alan Sutcliffe’s demonstrations of wireframe terrain models using hidden line removal occurred as early as 1979, and Evans and Sutherland’s Picture System series and flight simulators, which employed depth cueing, were capable of manipulating large wireframe models in real time. These technological developments predated their use in gaming and in the personal computer by nearly 15 years, and as such their contribution to 3D graphics standards was hugely significant.

> 对计算机生成图像(CGI)的需求推动了电影业成为支撑现代 3D 图形硬件的先锋技术，从 1977 年发行的《星际大战》中用于模拟死亡之星的基于 graphics 共生系统(GRASS)的转换，到 1984 年的《龙》中使用深度提示的 15 分钟计算机生成动画，到 1993 年侏罗纪公园恐龙的完整照片。工业应用的类似发展同样具有开创性；Alan Sutcliffe 早在 1979 年就演示了使用隐藏线移除的线框地形模型，Evans 和 Sutherland 的 Picture System 系列和飞行模拟器采用了深度提示，能够实时操纵大型线框模型。这些技术的发展比它们在游戏和个人电脑中的使用早了近 15 年，因此它们对 3D 图形标准的贡献是巨大的。

Following are brief descriptions of graphics technologies either attributed to or made famous by the film industry:

> 以下简要介绍了电影行业的图形技术：

- _GRASS_ is a programming language designed to create 2D vector graphics animations, allowing scaling, rotation, translation and colour changes over time. It was first developed by Tom DeFanti in 1974 and was most famously used to rotate and scale the Death Star in the attack sequences of _Star Wars_.

> -*GRASS* 是一种编程语言，旨在创建 2D 矢量图形动画，允许缩放、旋转、平移和颜色随时间变化。它最早由汤姆·德凡蒂于 1974 年开发，最著名的是在星际大战的攻击序列中旋转和缩放死星。

- _Hidden line removal_ is an optimisation of wireframe modelling where edges and lines that lie behind other visible surfaces are not drawn. The general principle is to avoid drawing what the eye cannot see, as this is wasteful in terms of performance and power. (A _wireframe_ is a skeletal shape containing none of the detail of the object it represents.)

> -*隐藏线移除*是线框建模的一种优化，其中不绘制位于其他可见曲面后面的边和线。一般原则是避免画眼睛看不到的东西，因为这在性能和功率方面是浪费的。(*wireframe* 是一个骨架形状，不包含它所代表的对象的任何细节。)

- _Depth-cueing_ is the process by which the eye is given the perception of depth in a scene. The eye makes use of many `cues` or `hints` to place objects within a three-dimensional world. These include _perspective_ (distant objects are smaller than near ones), _occlusion_ (distant objects are blocked from view by near ones) and _distance fog_ (distant objects are duller and more blurred due to light scattering by the atmosphere). _Tron_ employed the most primitive form of distance fog, whereby distant objects were gradually mixed with black to fade them out as they moved away from the scene—so the phrase was coined `if in doubt, black it out!`

> -深度感知是眼睛在场景中感知深度的过程。眼睛利用许多 `线索` 或 `暗示` 将物体放置在三维世界中。这些包括*透视(远物体比近物体小)、*遮挡(远物体被近物体挡住视线)和*静止雾(远物体由于大气的光散射而变得更暗、更模糊)\_Tron*使用了最原始的距离雾形式，通过这种方式，远处的物体逐渐与黑色混合，以在它们离开场景时使其淡出，因此该短语被创造为 `如果有疑问，请将其黑掉！`

Apart from custom-built and hugely expensive hardware that was largely tied to research—graphics and computer animation had been confined to complex algorithms written for general-purpose processors, with, at best, simple video address generators that performed some form of translation between the CPU and the display. It was inevitable that hardware acceleration would follow in order to support the growing processing demands of increasingly complex graphics.

> 除了定制的、非常昂贵的硬件，这些硬件主要与研究图形和计算机动画有关，它们仅限于为通用处理器编写的复杂算法，充其量只有简单的视频地址生成器，在 CPU 和显示器之间执行某种形式的转换。为了支持日益复杂的图形处理需求，硬件加速是不可避免的。

In 1979, Jim Clark, an associate professor of electrical engineering at Stanford University, California, developed what he called a geometry engine, which was the foundation of modern hardware to accelerate 3D modelling. This engine transformed objects from representations in standalone models to a position and orientation on a computer screen. The lighting and shading steps were still handled by the main processor. Clark anticipated commercial success for the engine and formed Silicon Graphics Inc. (SGI) in 1982. The company was instrumental in bringing 3D computer graphics to the mass market.

> 1979 年，加州斯坦福大学电气工程副教授吉姆·克拉克开发了他所称的几何引擎，这是现代硬件加速 3D 建模的基础。该引擎将对象从独立模型中的表示转换为计算机屏幕上的位置和方向。照明和着色步骤仍然由主处理器处理。克拉克预计该引擎将取得商业成功，并于 1982 年成立了 Silicon Graphics Inc.(SGI)。该公司在将 3D 计算机图形推向大众市场方面发挥了重要作用。

Around the same time, the home PC market began in earnest with the hugely successful IBM PC and the Apple II, both of which came with graphics cards that supported colour displays. This captured the minds of families and businesses alike, and the first computer with a graphical user interface followed with the Apple Macintosh in 1984. The many competing platforms thrust computing and gaming into the limelight via aggressive advertising campaigns, and this pushed the graphics industry forward still further. Popular cross-platform games such as _Elite_ started to make use of wireframe models and techniques such as hidden line removal; another game, _Alpha Waves,_ provided the first fully immersive 3D experience for gamers, with interaction of 3D objects in a simple 3D world. High-performing 3D graphics would soon become a requirement of personal computers.

> 大约在同一时间，家用 PC 市场开始认真发展，IBM PC 和 Apple II 取得了巨大成功，它们都配备了支持彩色显示器的图形卡。这引起了家庭和企业的注意，1984 年，第一台带有图形用户界面的电脑推出了苹果 Macintosh。许多竞争平台通过积极的广告宣传将计算和游戏推向了聚光灯下，这推动了图形行业的进一步发展。流行的跨平台游戏，如 *Elite* 开始使用线框模型和隐藏线移除等技术；另一款游戏《阿尔法波浪》(\_Alpha Waves)为玩家提供了第一次完全沉浸式的 3D 体验，在一个简单的 3D 世界中交互 3D 对象。高性能 3D 图形将很快成为个人计算机的需求。

Meanwhile, SGI began the development of products for high-performance graphics terminals, beginning with their customised Integrated Raster Imaging System (IRIS) hardware, which could be attached to a general-purpose computer. Developers were exposed to this hardware via SGI’s proprietary application programming interface (API) called the IRIS graphics language (IRIS GL), which was mainly geared toward the provision of efficient floating point mathematics (used to represent an object’s shape by specifying its vertices in three-dimensional space; see the `[Geometry Specification and Attributes](#13_9781119183938-ch10.xhtml#c10-sec-0010)` section later in this chapter) via Clark’s geometry engine. The follow-up IRIS 2000 series formed part of fully functional UNIX workstations, but as systems evolved to accelerate 3D rendering, as well as geometry processing, it became clear that across the host of PCs and consumer devices a standard API was required for cross-platform support. In addition, companies such as IBM and Sun Microsystems were planning releases of 3D hardware that competed directly with IRIS, and so SGI sought to consolidate its market share by releasing a derivation of IRIS GL called OpenGL, which was the first API for 2D and 3D graphics that was not manufacturer-specific. OpenGL allowed developers access to all hardware platforms that supported it, and, critically, any unsupported hardware feature could be offloaded to software running on the main processor.

> 与此同时，SGI 开始为高性能图形终端开发产品，首先是定制的集成光栅成像系统(IRIS)硬件，该硬件可以连接到通用计算机。开发人员通过 SGI 的专有应用编程接口(API)(称为 IRIS 图形语言(IRIS GL))接触到该硬件，这主要是为了通过 Clark 的几何引擎提供有效的浮点数学(用于通过指定三维空间中的顶点来表示对象的形状；参见本章后面的 `[几何规范和属性](#13_9781119183938-ch10.xhtml#c10-sec-0010)` 部分)。后续的 IRIS 2000 系列构成了功能齐全的 UNIX 工作站的一部分，但随着系统的发展，以加速 3D 渲染和几何处理，很明显，在主机 PC 和消费设备上，跨平台支持需要标准 API。此外，IBM 和 Sun Microsystems 等公司正在计划发布与 IRIS 直接竞争的 3D 硬件，因此 SGI 试图通过发布名为 OpenGL 的 IRIS GL 衍生产品来巩固其市场份额，OpenGL 是第一个非制造商专用的 2D 和 3D 图形 API。OpenGL 允许开发人员访问所有支持它的硬件平台，关键是，任何不支持的硬件功能都可以卸载到主处理器上运行的软件上。

---

> [!NOTE]

UNIX is a widely used multitasking, multiuser operating system. For additional information about operating systems, see [Chapter 8](#11_9781119183938-ch08.xhtml).

> UNIX 是一种广泛使用的多任务、多用户操作系统。有关操作系统的更多信息，请参阅[第 8 章](#11_9781119183938-ch08.xhtml)。

### Two Competing Standards

It is here that we move away from graphics hardware to discuss the development of features through graphics standards. With the release of OpenGL 1.0 in 1992, SGI gained the support of various companies, including Apple, ATI, Sun Microsystems and, initially, Microsoft. To ensure the promotion and development of the open standard, SGI led the formation of the Architecture Review Board (ARB) later that year, and so numerous revisions of OpenGL followed. OpenGL 1.0 introduced the concept of model-space geometry, transformation to screen space, colour and depth information, textures, lighting and materials. Its aim was to provide an abstraction layer above the underlying hardware so that developers could port (transfer) their applications to various platforms without having to rewrite their code. Although well supported, this approach came at a performance cost, and early hardware platforms struggled as a result.

> 正是在这里，我们不再讨论图形硬件，而是讨论通过图形标准开发功能。随着 1992 年 OpenGL1.0 的发布，SGI 获得了多家公司的支持，包括苹果、ATI、Sun Microsystems 和最初的微软。为了确保开放标准的推广和发展，SGI 在当年晚些时候领导了架构审查委员会(ARB)的成立，随后对 OpenGL 进行了大量修订。OpenGL1.0 引入了模型空间几何、屏幕空间转换、颜色和深度信息、纹理、照明和材质的概念。其目的是在底层硬件之上提供一个抽象层，以便开发人员可以将其应用程序移植(传输)到各种平台，而无需重写代码。虽然这种方法得到了很好的支持，但它的性能是有代价的，因此早期的硬件平台很难做到这一点。

An _abstraction layer_ is used in programming to hide implementation details such that the same code can be used multiple times or on multiple platforms. For example, suppose you made a list of jobs for somebody to do in a day, one of which was washing your clothes. The output from this task would be a clean set of clothes. Sure, you might set some quality guarantees such that nothing is shrunk or the colours don’t run, but at this level you don’t care _how_ the washing is done. Moreover, you could pass the same list to somebody else (subject to the same guarantees) and they could achieve the same result. The mechanics of which machine is used, which cleaning agents, how the clothes are dried and which garments are mixed with others are unimportant details. This is a level of abstraction.

> 抽象层在编程中用于隐藏实现细节，以便同一代码可以多次使用或在多个平台上使用。例如，假设你列了一份清单，列出了某人一天要做的工作，其中一项是洗衣服。这项任务的输出将是一套干净的衣服。当然，你可以设置一些质量保证，这样就不会缩水或者颜色不会褪色，但在这个级别上，你不在乎洗得怎么样。此外，您可以将相同的列表传递给其他人(受到相同的保证)，他们可以获得相同的结果。使用哪台机器、哪种清洁剂、衣服是如何干燥的以及哪些衣服与其他衣物混合的机械原理都是不重要的细节。这是一个抽象级别。

Early in 1993, Microsoft exited the OpenGL working group; in a bid to be competitive in the market, Microsoft bought a company called RenderMorphics to work on 3D graphics for Windows 95. RenderMorphics had developed an API in the field of CAD and medical imaging, and in 1995 Microsoft released the first versions of its own Direct3D API based on the RenderMorphics software: Direct X 2.0 and Direct X 3.0. Whilst developers appreciated the direct control of hardware that the immediate mode provided, it was hard to program, which led to calls for OpenGL to be adopted as the one true standard. In addition, a company called 3Dfx was developing a proprietary API (called Glide) for its Voodoo hardware, and the huge performance advantages of this approach brought the company some success. However, even 3Dfx was forced to adopt a subset of OpenGL features (Mini GL) in 1996 when a company called id Software released _Quake_ and included a Windows port targeting OpenGL.

> 1993 年初，微软退出了 OpenGL 工作组；为了在市场上具有竞争力，微软收购了一家名为 RenderMorphics 的公司，为 Windows 95 开发 3D 图形。RenderMorphics 在 CAD 和医学成像领域开发了一个 API，1995 年，微软基于 RenderMorphocs 软件发布了自己的 Direct3D API 的第一个版本：Direct X 2.0 和 Direct X 3.0。虽然开发人员欣赏即时模式提供的硬件直接控制，但编程很难，这导致了 OpenGL 被采用为一个真正的标准的呼声。此外，一家名为 3Dfx 的公司正在为其 Voodoo 硬件开发专有 API(名为 Glide)，这种方法的巨大性能优势为该公司带来了一些成功。然而，1996 年，当一家名为 id Software 的公司发布了 *Quake* 并包含了一个针对 OpenGL 的 Windows 端口时，即使是 3Dfx 也被迫采用了 OpenGL 功能的子集(Mini-GL)。

---

> [!NOTE]

_Immediate mode_ is a rendering style for graphic library APIs that allows for the direct display of graphics objects to the screen.

> \_即时模式是图形库 API 的一种渲染样式，允许将图形对象直接显示在屏幕上。

As processing capabilities improved, proprietary APIs declined in favour of the flexibility provided by Direct 3D and cross-platform support provided by OpenGL. An intense battle ensued. Although OpenGL was the favoured API of many hardware vendors, Direct3D 4 was to prove revolutionary because it allowed rendering to arbitrary surfaces that could be used in subsequent rendering passes. OpenGL had to be extended to provide such a mechanism. Similar advances followed, most notably with the move to programmable processing steps from the old fixed-function pipeline. This led to the first major revision of OpenGL, and although both APIs have since remained independent, feature sets have remained broadly similar between the two standards. However, OpenGL remains the only cross-platform graphics API supported by various operating systems such as Linux, Android and iOS. By contrast, Direct3D is purely targeted at Microsoft Windows. In 2003 OpenGL ES 1.0—a derivative of OpenGL 1.3—was released to target embedded devices (the ES suffix stands for embedded systems). This release was in direct response to the proliferation of smartphones, tablets and mobile platforms. OpenGL ES 1.0 has since undergone several major revisions.

> 随着处理能力的提高，专有 API 越来越倾向于 Direct 3D 提供的灵活性和 OpenGL 提供的跨平台支持。随后发生了一场激烈的战斗。尽管 OpenGL 是许多硬件供应商青睐的 API，但 Direct3D 4 被证明是革命性的，因为它允许渲染到可以在后续渲染过程中使用的任意曲面。OpenGL 必须被扩展以提供这样的机制。类似的进步随之而来，最引人注目的是从旧的固定功能流水线转移到可编程处理步骤。这导致了 OpenGL 的第一次主要修订，尽管两个 API 自此保持独立，但两个标准之间的功能集仍然大致相似。然而，OpenGL 仍然是各种操作系统(如 Linux、Android 和 iOS)支持的唯一跨平台图形 API。相比之下，Direct3D 完全针对 Microsoft Windows。2003 年，OpenGL ES 1.0(OpenGL 1.3 的衍生版本)发布到目标嵌入式设备(ES 后缀代表嵌入式系统)。此次发布是对智能手机、平板电脑和移动平台激增的直接回应。OpenGL ES 1.0 此后经历了几次重大修订。

---

> [!NOTE]

A _fixed-function hardware pipeline_ is a collection of processing stages, each of which is tightly mapped to a dedicated set of logic gates (building blocks of a digital circuit). A _programmable hardware pipeline_ is a more loosely defined general-purpose platform on which the same functionality can be achieved with much more flexibility and, unfortunately, a potential degradation of performance. The programming interface is conceptually more complex (as a program needs to be written to perform each task rather than directly calling a specific hardware function), but the scope to achieve more sophisticated techniques means that programmable pipelines now underpin all modern graphics processors.

> 固定功能硬件流水线是处理级的集合，每个处理级都紧密映射到一组专用逻辑门(数字电路的构建块)。可编程硬件流水线是一种定义更为宽松的通用平台，在该平台上，可以以更大的灵活性实现相同的功能，不幸的是，性能可能会降低。编程接口在概念上更复杂(因为需要编写程序来执行每个任务，而不是直接调用特定的硬件功能)，但实现更复杂技术的范围意味着可编程管道现在支持所有现代图形处理器。

Before you move on to looking at OpenGL in more detail, we should mention NVIDIA, the company that first coined the phrase `graphics processing unit` (GPU). This term is widely used to describe the single-chip processor dedicated to geometry processing, transform and lighting, texture mapping and shading. NVIDIA first used the term in 1999 for the release of its GeForce 256 core and the first Direct3D 7-compliant hardware accelerator. The Raspberry Pi contains Broadcom’s VideoCoreIV GPU.

> 在您进一步详细了解 OpenGL 之前，我们应该提到 NVIDIA，这家公司最先创造了 `图形处理单元` (GPU)这一短语。该术语广泛用于描述专用于几何处理、变换和照明、纹理映射和着色的单芯片处理器。NVIDIA 于 1999 年首次使用该术语发布其 GeForce 256 内核和第一个符合 Direct3D 7 的硬件加速器。复盆子 Pi 包含 Broadcom 的 VideoCoreIV GPU。

## The OpenGL Graphics Pipeline

This section delves deeper into the OpenGL graphics pipeline. All modern computer hardware—from desktop PCs to smartphones—contains some form of GPU specifically designed to accelerate all but the simplest of 3D graphics tasks. We will take a look at the principal stages of the classical graphics pipeline and understand the key concepts before moving on to how modern GPUs accelerate these steps.

> 本节将深入研究 OpenGL 图形管道。从台式 PC 到智能手机的所有现代计算机硬件都包含某种形式的 GPU，专门用于加速除最简单的 3D 图形任务外的所有任务。我们将看一看经典图形流水线的主要阶段，并在了解现代 GPU 如何加速这些步骤之前了解关键概念。

OpenGL neither requires that any features be accelerated by special hardware nor specifies any minimum performance targets; it merely sets out requirements that any implementation must meet to comply with the specification. It would therefore be perfectly acceptable, though perhaps undesirable, for the API to be implemented entirely in software running on a general purpose CPU. It is also important to recognise that OpenGL dictates only 3D rendering and not how input data is passed to the pipeline or how these images are to be displayed on screen.

> OpenGL 既不要求通过特殊硬件加速任何功能，也不指定任何最低性能目标；它仅仅列出了任何实现都必须满足的要求，以符合规范。因此，完全在通用 CPU 上运行的软件中实现 API 是完全可以接受的，尽管可能是不希望的。同样重要的是要认识到 OpenGL 只规定了 3D 渲染，而不是如何将输入数据传递到管道或如何在屏幕上显示这些图像。

OpenGL is a huge topic in its own right, worthy of several textbooks. As we touch on the basics of the graphics pipeline we will refer to OpenGL ES versions to demonstrate how the standard has evolved to improve flexibility for developers, and in turn has placed greater demands on the hardware itself. For reference, the Raspberry Pi GPU supports both OpenGL ES 1.1 and OpenGL ES 2.0 standards.

> OpenGL 本身就是一个巨大的主题，值得几本教科书。当我们触及图形管道的基础知识时，我们将参考 OpenGL ES 版本，以演示该标准如何演变以提高开发人员的灵活性，进而对硬件本身提出了更高的要求。作为参考，树莓派 GPU 支持 OpenGL ES 1.1 和 OpenGL ES 2.0 标准。

Figure 10-3 illustrates a high-level view of a graphics pipeline broken down into the following four stages:

> 图 10-3 显示了图形管道的高级视图，分为以下四个阶段：

1. **Vertex processing:** Vertices are placed to define the position and shape of an object. 2. **Rasterization:** Primitives (connected vertices) are converted into fragments with each fragment containing the data necessary to generate one pixel of a primitive. 3. **Fragment processing:** Fragments undergo a series of operations, including texturing and blending in preparation of converting them into coloured pixels. 4. **Output merging:** Fragments of primitives in three-dimensional space are combined to render a three-dimensional objects on a two-dimensional screen. For example, if a portion of one object is behind another in three-dimensional space, the pixels of that portion of the object in back will be hidden behind the pixels of the object in front.

> 1.**顶点处理：**放置顶点以定义对象的位置和形状。2.**光栅化：**图元(连接的顶点)被转换为片段，每个片段包含生成图元的一个像素所需的数据。3.**片段处理：**片段经过一系列操作，包括纹理和混合，以准备将其转换为彩色像素。4.**输出合并：**将三维空间中的图元片段组合在一起，以在二维屏幕上渲染三维对象。例如，如果一个对象的一部分在三维空间中位于另一个对象之后，则位于后面的对象的该部分的像素将隐藏在位于前面的对象的像素之后。

![[FIGURE 10-3:](#13_9781119183938-ch10.xhtml#rc10-fig-0003) A simple graphics pipeline diagram](./media/images/9781119183938-fg1003.png)

Because the process is linear it is described as a pipeline: data passes through successive stages, where each stage can start only after the previous one has completed. However, many stages may be simultaneously active as the pipeline queues up processing steps in preparation for when the next stage can accept its data. Consider Figure 10-4 in which we represent three stages of cleaning: washing, drying and ironing. We could perform washing and then drying and then ironing for each load, but this only achieves a throughput (one complete cleaning cycle) of one load for every three processes. Given that washing, drying and ironing can be performed in parallel, we can start the next wash load as soon as the previous load is being dried. The same is true of the subsequent drying and ironing steps. Apart from the initial time taken to fill the pipeline (that is, to get to the point in time when washing, drying and ironing are all active), throughput is now one load for every process.

> 因为这个过程是线性的，所以它被描述为一个流水线：数据通过连续的阶段，每个阶段只能在前一个阶段完成后才开始。然而，当管道排队处理步骤以准备下一阶段何时可以接受其数据时，许多阶段可能同时处于活动状态。考虑图 10-4，其中我们表示了三个清洁阶段：洗涤、干燥和熨烫。我们可以对每个负载进行清洗、干燥和熨烫，但这只能实现每三个过程一次负载的吞吐量(一个完整的清洁周期)。考虑到洗涤、烘干和熨烫可以并行进行，我们可以在前一个衣物烘干后立即开始下一个洗涤衣物。随后的干燥和熨烫步骤也是如此。除了填充管道所需的初始时间(即，到达洗涤、干燥和熨烫都处于活动状态的时间点)外，吞吐量现在是每个流程的一个负载。

![[FIGURE 10-4:](#13_9781119183938-ch10.xhtml#rc10-fig-0004) Visual metaphor of a pipeline, where several steps can be performed in parallel to improve computational efficiency.](./media/images/9781119183938-fg1004.png)

### Geometry Specification and Attributes

Objects in OpenGL ES are composed of points, lines and triangles. Complex shapes are created from these basic building blocks, or _primitives_. The inputs to OpenGL ES are the (three-dimensional) coordinates of the vertices of these building blocks; a point has one vertex, a line has two vertices, and a triangle has three vertices. As described later in this section, vertices may also have other data attached to them apart from their position in the modelview-space. The data associated with each vertex are known as _attributes_.

> OpenGL ES 中的对象由点、线和三角形组成。复杂的形状是由这些基本构建块(或*基本*)创建的。OpenGL ES 的输入是这些构建块顶点的(三维)坐标；一个点有一个顶点，一条线有两个顶点，而一个三角形有三个顶点。如本节稍后所述，除了顶点在模型视图空间中的位置之外，顶点还可以附加其他数据。与每个顶点关联的数据称为 *attributes*。

Three coordinates are required to describe the position of a vertex in a three-dimensional world: x, y and z (see Figure 10-5). These coordinates are grouped as three-component vectors. In the absence of any transformation the default orientation of the coordinate axes are such that x and y represent the horizontal and vertical screen axes, and z the axis perpendicular to the screen. The default range of these axes is from -1 to +1. Any shape that lies inside the cube defined by these axes is projected onto the two-dimensional viewing surface (that is, the screen). If a shape has coordinates that lie outside of this range, it is clipped and may be removed from the scene entirely, as it will not be visible.

> 需要三个坐标来描述顶点在三维世界中的位置：x、y 和 z(见图 10-5)。这些坐标分为三个分量向量。在没有任何变换的情况下，坐标轴的默认方向为 x 和 y 表示水平和垂直屏幕轴，z 表示垂直于屏幕的轴。这些轴的默认范围为-1 到 +1。位于由这些轴定义的立方体内部的任何形状都投影到二维观察表面(即屏幕)上。如果图形的坐标位于该范围之外，则会对其进行剪裁，并可能会将其从场景中完全删除，因为它将不可见。

![[FIGURE 10-5:](#13_9781119183938-ch10.xhtml#rc10-fig-0005) Vertices plotted with x, y, z coordinates can define three-dimensional shapes.](./media/images/9781119183938-fg1005.png)

OpenGL ES supports seven primitives that may be used to construct more complex shapes. These primitives are shown in Figure 10-6:

> OpenGLES 支持七个图元，可用于构建更复杂的形状。这些图元如图 10-6 所示：

- A point is a single vertex with a default size of one pixel. The user may change the size of a point primitive.

> -点是默认大小为一个像素的单个顶点。用户可以更改点图元的大小。

- A line is defined by two connected vertices.

> -直线由两个相连的顶点定义。

- A line strip is formed by connecting three or more vertices without connecting the first and last vertices, thus forming an open shape.

> -通过连接三个或多个顶点而不连接第一个和最后一个顶点来形成线条，从而形成开放形状。

- A line loop is a line strip with the first and last vertices connected to form a closed shape.

> -线环是一条线带，第一个顶点和最后一个顶点连接在一起形成闭合形状。

- A triangle is formed by connecting three vertices.

> -三角形由三个顶点连接而成。

- A triangle strip is formed where three vertices are used to describe an initial triangle, and each successive vertex forms a new triangle using two previous vertices and the new vertex.

> -三角形条带是在使用三个顶点来描述初始三角形的情况下形成的，每个连续的顶点使用两个先前的顶点和新的顶点形成一个新的三角形。

- A triangle fan is similar to a triangle strip except that each triangle has the initial vertex in common.

> -三角形扇与三角形条相似，只是每个三角形都有共同的初始顶点。

![[FIGURE 10-6:](#13_9781119183938-ch10.xhtml#rc10-fig-0006) Open GL primitive types](./media/images/9781119183938-fg1006.png)

All shapes in OpenGL ES are constructed from these primitive types, with the type specified as an input by the developer. The default format for these coordinates is 32-bit floating point (a format that provides a wide dynamic range of values to support precise positioning) but again, the user may specify different a data type.

> OpenGLES 中的所有形状都是由这些基本类型构造而成的，其类型由开发人员指定为输入。这些坐标的默认格式是 32 位浮点(一种提供宽动态范围值以支持精确定位的格式)，但用户可以指定不同的数据类型。

In addition to position, other per-input-vertex data may be specified by the user. This is data that will be used in subsequent 3D rendering steps and may include colour, normal vectors (used in lighting calculations) and coordinates of textures (used in texturing). Colour is assigned to each vertex in OpenGL ES. When different colours are set for different vertices, the pipeline automatically blends them for screen pixels that lie inside the shape. Colours are specified with up to four components: red, green, blue and, optionally, alpha, which is used to represent the transparency of the colour. When multiple objects overlay one pixel in a scene, the relative depth of these objects and the alpha colour components determine how colours must be blended to give the illusion of transparency.

> 除了位置之外，用户还可以指定其他每输入顶点数据。这是将在后续 3D 渲染步骤中使用的数据，可能包括颜色、法线向量(用于照明计算)和纹理坐标(用于纹理)。在 OpenGLES 中，颜色被分配给每个顶点。当为不同的顶点设置不同的颜色时，管道会自动为位于形状内部的屏幕像素混合这些颜色。颜色最多由四种成分指定：红色、绿色、蓝色和可选的 alpha，用于表示颜色的透明度。当多个对象覆盖场景中的一个像素时，这些对象的相对深度和 alpha 颜色分量决定了必须如何混合颜色才能产生透明度错觉。

---

> [!NOTE]

A _normal vector_ (or _normal_) represents a direction that is perpendicular to the surface of an object.

> _normal 向量_(或 *normal*)表示垂直于对象表面的方向。

The definition of additional attributes is well-defined in OpenGL ES 1.1 as it only exposes a fixed function rendering pipeline. Because the OpenGL ES 2.0 pipeline is flexible, these other attributes are essentially any data that may or may not be used by any processing step later in the pipeline. You can read more about how this data may be used in later sections of this chapter.

> OpenGLES1.1 中定义了附加属性，因为它只公开了一个固定的函数渲染管道。因为 OpenGL ES 2.0 管道是灵活的，所以这些其他属性基本上是管道中稍后任何处理步骤可能使用或不使用的任何数据。您可以在本章后面的章节中详细了解如何使用这些数据。

### Geometry Transformation

Transformations in computer graphics are essentially changes to the coordinate system in which each object exists. Whilst the inputs to OpenGL ES are the abstract object coordinates specific to each component of the scene, each object undergoes several transformations that may change its appearance or remove it entirely from the `screen` . Hardware implementations handle most of the mathematics behind the scenes, but it pays to understand this concept in order to make sense of why GPUs have been designed in such a way to aid the transformation process.

> 计算机图形中的变换本质上是对每个对象所在的坐标系的改变。虽然 OpenGL ES 的输入是特定于场景每个组件的抽象对象坐标，但每个对象都会经历多次变换，这些变换可能会改变其外观或将其从 `屏幕` 中完全移除。硬件实现在幕后处理大部分数学问题，但理解这一概念有助于理解为什么 GPU 以这种方式设计来帮助转换过程。

---

> [!NOTE]

We talk about the `screen` here, but the output of rendering need not necessarily end up on the display. Many applications process a scene multiple times before outputting an image to the screen; each intermediate processing step (or render) will not necessarily be visible to the user.

> 我们在这里讨论 `屏幕` ，但渲染的输出不一定会在显示器上结束。许多应用程序在将图像输出到屏幕之前多次处理场景；每个中间处理步骤(或渲染)不一定对用户可见。

#### Transformation Types

The first vertex processing step is the modelling transformation, which positions and sizes the object in the context of the overall scene. The system of world coordinates is used to define the relative positions of these objects in the 3D world that is being created. Following this, a second transformation occurs to account for what the observer of the scene can actually see. Only the view of the world from the perspective of the observer is what is rendered to the screen. This is the system of _eye coordinates_, having undergone what is termed as the viewing transformation. In practice, OpenGL ES does not separate these two transforms, as it is impossible to distinguish between the two from the output of these two stages. For example, imagine a scene of a woman walking her dog, where the dog is directly in front of the woman. In the next frame, the dog is to the left of the woman. Has this resulted from the dog moving to the (stationary) woman’s left (a modelling transformation of the dog), or from the woman moving to the right of the dog (a viewing transformation from the woman)? The difference is purely conceptual, and so OpenGL ES makes no attempt to distinguish between the two; there is only one modelview transformation (see Figure 10-7).

> 第一个顶点处理步骤是建模转换，它在整个场景的上下文中定位和调整对象的大小。世界坐标系用于定义这些对象在正在创建的 3D 世界中的相对位置。随后，发生第二次变换，以说明场景的观察者实际可以看到什么。只有观察者视角下的世界观才是呈现在屏幕上的。这是一个 `眼坐标` 系统，经历了所谓的观察变换。在实践中，OpenGLES 不会分离这两个变换，因为无法从这两个阶段的输出中区分这两个。例如，想象一个女人遛狗的场景，狗就在女人的正前方。在下一帧中，狗在女人的左边。这是因为狗移到(静止的)女人的左边(狗的造型转变)，还是因为女人移到狗的右边(女人的视角转变)？这种区别纯粹是概念性的，因此 OpenGLES 没有试图区分两者；只有一个模型视图转换(见图 10-7)。

![[FIGURE 10-7:](#13_9781119183938-ch10.xhtml#rc10-fig-0007) OpenGL ES uses a single modelview for modelling and viewing transformations.](./media/images/9781119183938-fg1007.png)

OpenGL ES supports three basic modelview transformations: translation, scaling and rotation:

> OpenGL ES 支持三种基本模型视图转换：平移、缩放和旋转：

- Translation simply adds an offset to each component of the position vector, thereby moving it within the new coordinate system. For example, for an offset of `(-off_x, +off_y, +off_z)`, a vector `(x, y, z)` would become `(x-off_x, y+off_y, z+off_z)`. On its own, it does not change the size of the overall object.

> -平移只是向位置向量的每个分量添加一个偏移，从而在新的坐标系中移动它。例如，对于偏移量 `(-off_x，+off_y，+off_xz)` ，矢量 `(x，y，z)` 将变为 `(x-off_x，y+off_y，z+off_z)` 。它本身不会改变整个对象的大小。

- Scaling multiplies each component of the position vector by a scale factor, thereby resizing the overall object. For example, for a scale factor of `(sf_x, sf_y, sf_z)`, a vector `(x, y, z)` would become `(sf_x*x, sf_y*y, sf_z*z)`.

> -缩放将位置向量的每个分量乘以缩放因子，从而调整整个对象的大小。例如，对于比例因子 `(sf_x，sf_y，sf_z)` ，矢量 `(x，y，z)` 将变为 `(sf-x*x，sf_y*y，sf_6*z)` 。

- Rotation requires a bit more understanding of three-dimensional coordinate systems. Whereas rotation in two dimensions occurs around a point, in three dimensions this must happen around an axis. Once this axis is defined, a convention must then be used to define whether clockwise or anticlockwise rotation occurs for positive values of rotation around this axis. OpenGL ES uses a right-handed coordinate system so the right-hand rule applies: curling the fingers of your right hand as you point your thumb in the air shows you the direction of positive rotation around an axis pointing in the direction of your thumb. For example, an axis defined by the vector `(dx, dy, dz)` with respect to the origin (where at least one of `dx, dy` or `dz` are non-zero) defines an axis about which each vertex can be rotated by a user-defined angle (which we call θ `)`. (See Figure 10-8.)

> -旋转需要对三维坐标系有更多的理解。二维旋转是围绕一个点发生的，而三维旋转则必须围绕一个轴发生。一旦定义了该轴，则必须使用约定来定义围绕该轴旋转的正值是顺时针旋转还是逆时针旋转。OpenGLES 使用右手坐标系，因此右手法则适用：当您将拇指指向空中时，将右手手指卷曲，可以显示围绕指向拇指方向的轴的正旋转方向。例如，由向量 `(dx，dy，dz)` 相对于原点定义的轴(其中 `dx，dy'或 ` dz ` 中的至少一个是非零的)定义了一个轴，每个顶点可以围绕该轴旋转一个用户定义的角度(我们称之为θ` )。(见图 10-8。)

![[FIGURE 10-8:](#13_9781119183938-ch10.xhtml#rc10-fig-0008) Rotation is defined by the axis around which objects rotate and the angle of rotation.](./media/images/9781119183938-fg1008.png)

OpenGL ES 1.1 provides a fixed set of functions to describe these various transformations, namely `glTranslate`</code>, `glScale` and `glRotate`, whereas OpenGL ES 2.0 hands much more control to the developer by providing programmable stages in which to process geometry.

> OpenGL ES 1.1 提供了一组固定的函数来描述这些不同的转换，即 `glTranslate` </code>、 `glScale` 和 `glRotate` ，而 OpenGL ES 2.0 通过提供处理几何图形的可编程阶段，将更多的控制权交给了开发人员。

After positioning objects within this imaginary 3D world, the view of this world needs to be projected onto a two-dimensional viewing surface, for which there are two more stages of transformation. The projection transformation first converts from eye coordinates to clip coordinates, and this is necessary for two reasons:

> 在这个虚拟的 3D 世界中定位对象之后，需要将这个世界的视图投影到二维观察表面上，对于这个观察表面，还有两个转换阶段。投影变换首先将眼睛坐标转换为剪辑坐标，这有两个原因：

- The observer cannot see the entire three-dimensional world, so the limits within which this 2D scene is viewed (the viewport) must be bound to the set of objects rendered to the display.

> -观察者无法看到整个三维世界，因此查看该 2D 场景的范围(视口)必须绑定到渲染到显示器的对象集。

- The observer can see objects only within a certain range of distances, so limits must be placed on the depths of transformed components.

> -观察者只能在一定距离范围内看到物体，因此必须对变换组件的深度进行限制。

Objects that lie outside of these ranges are said to be `clipped,` hence the term _clip coordinates_. Rather than a 2D rectangle within which a scene must be displayed, a viewing volume defines the observable region, accounting for the relative depths of objects in the scene.

> 位于这些范围之外的对象被称为 `剪裁` ，因此术语 `剪裁坐标` 。查看体积定义了可观察区域，而不是必须在其中显示场景的 2D 矩形，它考虑了场景中对象的相对深度。

In theory, this viewing volume might resemble an infinitely `deep` rectangle, with a cross-section equal to the 2D window through which the scene is viewed; in practice the viewing volume does not resemble such a window, for two reasons:

> 理论上，这个观看体积可能类似于一个无限 `深` 的矩形，其横截面等于观看场景的 2D 窗口；实际上，由于两个原因，观看体积不类似于这样的窗口：

- Perspective: objects further from the observer appear smaller.

> -透视：离观察者更远的对象看起来更小。

- The field-of-view extends as distance from the observer increases.

> -随着距离观察者的距离增加，视野也会扩大。

All lifelike images are processed using perspective projection to account for distance from the viewer. Perspective projection would imply an infinitely deep pyramidal viewing volume extending from the observer. However, because it would be impossible to store an infinite range of depth values, the regions of this pyramid within which objects can be observed are limited. In effect, the viewing volume is a truncated pyramid, as shown in Figure 10-9. This is also known as the frustrum, and is discussed later in this chapter.

> 所有逼真的图像都使用透视投影进行处理，以说明与观众的距离。透视投影将意味着从观察者处延伸出无限深的金字塔形观看体积。然而，由于不可能存储无限范围的深度值，因此可以观察到物体的金字塔区域是有限的。实际上，观看体积是一个截锥，如图 10-9 所示。这也称为截头体，本章稍后将对此进行讨论。

![[FIGURE 10-9:](#13_9781119183938-ch10.xhtml#rc10-fig-0009) OpenGL ES viewing volume, or frustrum. In addition to the viewport boundaries, near and far clip planes must be supplied to fully define the set of valid clip coordinates as a result of the projection transformation. (Clip planes pass through the frustrum; anything closer to the viewport than the near clip plane or farther than the far clip plane are cut out of the scene.)](./media/images/9781119183938-fg1009.png)

The final transformation is to convert the 2D clip coordinates to a set of coordinates scaled to the device on which the scene is being displayed (such as a rectangle of pixels on a screen). The viewport transformation performs this step and is the final stage of vertex processing.

> 最后的转换是将 2D 剪辑坐标转换为一组坐标，该坐标根据显示场景的设备进行缩放(例如屏幕上的像素矩形)。视口变换执行此步骤，是顶点处理的最后阶段。

#### The Maths behind Transformations: Transformation Matrices

Now that you have a general understanding of the geometry transformations in the coordinate plane, you are ready to look more closely at the mathematics involved in performing transformations. As stated earlier, the position of vertices in a 3D coordinate space are represented in Cartesian form by a three-component vector, where the magnitude of each component represents the distance of the point from the origin in the x, y and z dimensions respectively. For now we represent each vertex by a triple of numbers in the form `(x,y,z)`.

> 现在您已经对坐标平面中的几何变换有了大致的了解，您可以更仔细地研究执行变换所涉及的数学。如前所述，三维坐标空间中顶点的位置以笛卡尔形式由三分量向量表示，其中每个分量的大小分别表示点在 x、y 和 z 维度上与原点的距离。现在我们用 `(x，y，z)` 形式的三位数表示每个顶点。

A transformation results in some change in a graphical object, such as its position (translation), its size (scaling) or its angle relative to a rotational axis. (rotation). To perform such transformations, the object’s vertices must be moved in the coordinate plane in a certain direction and magnitude. To determine the new location of a vertex, mathematical operations are performed on the vertex’s x, y and z values. Matrices facilitate these mathematical operations.

> 变换会导致图形对象发生某些变化，例如其位置(平移)、大小(缩放)或相对于旋转轴的角度。(旋转)。要执行此类变换，必须在坐标平面中以特定方向和大小移动对象的顶点。为了确定顶点的新位置，对顶点的 x、y 和 z 值执行数学运算。矩阵便于这些数学运算。

Matrices are rectangular arrays of numbers and are used to represent the modelview transformations described earlier. They are used to pre-multiply each vector by per-component factors to compute an output vector of the same dimension. To be able to multiply two matrices, the number of columns in the first matrix must equal the number of rows in the second matrix. To multiply two matrices, you multiply each value in the first row of the first matrix by its corresponding value in the first column of the second matrix and then sum the results. This is repeated for all rows and columns as shown:

> 矩阵是数字的矩形数组，用于表示前面描述的模型视图转换。它们用于将每个向量预先乘以每个分量因子，以计算相同维度的输出向量。为了能够将两个矩阵相乘，第一个矩阵的列数必须等于第二个矩阵的行数。要将两个矩阵相乘，请将第一个矩阵第一行中的每个值乘以第二个矩阵第一列中的相应值，然后对结果求和。对所有行和列重复此操作，如下所示：

![images](./media/images/eq10001.png)

Following is an example of how multiplying matrices is used to scale a three-dimensional vector by each of the scale factors `sf_x, sf_y` and `sf_z`:

> 以下是如何使用乘法矩阵来按比例因子 `sf_x、sf_y` 和 `sf_z` 中的每一个缩放三维向量的示例：

![images](./media/images/eq10002.png)

The most powerful feature of using matrices is that multiple transformations can be combined by multiplying matrices. This allows all stages of vertex processing to be reduced to a single matrix multiplication, thus making the whole process more efficient and amenable to dedicated hardware processing.

> 使用矩阵最强大的特点是可以通过相乘矩阵来组合多个变换。这使得顶点处理的所有阶段都可以简化为单个矩阵乘法，从而使整个过程更加高效，并易于专用硬件处理。

---

> [!NOTE]

Although the matrix examples show a 3×3 matrix that corresponds to the three axes, x, y and z, you will commonly see a 4×4 matrix. The fourth column accounts for the origin (the point at which the three axes intersect). This fourth column enables you to change the position of the coordinate origin, which is required to perform a translation.

> 尽管矩阵示例显示了一个与 x、y 和 z 三个轴相对应的 3×3 矩阵，但通常会看到一个 4×4 矩阵。第四列说明原点(三个轴相交的点)。第四列允许您更改执行平移所需的坐标原点的位置。

### Lighting and Materials

Lighting and materials contribute directly to the realism of objects displayed in the scene, and this is one area that has undergone significant changes through major revisions of OpenGL ES. This section touches on basic lighting concepts as seen in OpenGL ES 1.1.

> 照明和材质直接有助于场景中显示的对象的真实感，这是通过 OpenGL ES 的主要修订而发生了重大变化的一个领域。本节将介绍 OpenGL ES 1.1 中的基本照明概念。

> [!NOTE]
> that for OpenGL ES 2.0 onwards, the lighting system (together with the geometric transformation stage discussed in the last section) was replaced by an entirely programmable pipeline allowing for more customization. Previously, only a limited set of fixed-function calls were made available to the application developer.

The interaction of light with objects and their materials is key to the way an observer perceives the world. A mirror looks shiny because it reflects a lot of light; a wool sweater looks fluffy because it absorbs more light and produces diffuse reflections according to the surface contours of the material. For our constructed 3D world to appear lifelike, these effects must be modelled in ways that fit with the properties expected of objects we see every day.

> 光与物体及其材料的相互作用是观察者感知世界的方式的关键。镜子看起来很亮，因为它反射了很多光；羊毛衫看起来很蓬松，因为它吸收更多的光，并根据材料的表面轮廓产生漫反射。为了让我们构建的 3D 世界看起来栩栩如生，这些效果必须以符合我们每天看到的物体预期属性的方式进行建模。

> [!NOTE]
> that lighting is computed per vertex for an object, the properties of which are then interpolated over the entire primitive like other vertex attributes.

OpenGL ES defines a series of properties that must be defined for the light sources and the objects placed in the scene. Two types of reflection are defined: specular reflection and diffuse reflection (see Figure 10-10).

> OpenGL ES 定义了一系列必须为场景中放置的光源和对象定义的属性。定义了两种类型的反射：镜面反射和漫反射(见图 10-10)。

- **Specular reflection:** The rays of light are reflected almost entirely in one direction by a surface, such that the observer views regions that are highly coloured according to the observer’s precise position. A real-world example would be the glare of sunlight from a mirror. This is easily avoided by moving slightly to one side. Areas of an object that are intensely lit in this way are called specular highlights.

> -**镜面反射：**光线几乎完全被一个表面在一个方向上反射，因此观察者可以根据观察者的准确位置观察到颜色很高的区域。现实世界中的一个例子是来自镜子的强光。这很容易通过稍微向一侧移动来避免。以这种方式强烈照明的对象区域称为镜面反射高光。

- **Diffuse reflection:** The propensity of a material to scatter light in all directions, such that it appears fuzzy and dull. The observer views contributions of colour from the whole surface.

> -**漫反射：**材料向各个方向散射光线的倾向，使其显得模糊和沉闷。观察者从整个表面观察颜色的贡献。

![[FIGURE 10-10:](#13_9781119183938-ch10.xhtml#rc10-fig-0010) Specular versus diffuse reflection](./media/images/9781119183938-fg1010.png)

These properties together govern how shiny a material appears. OpenGL ES defines a specular colour and a diffuse colour for an object, together with two additional colours. The ambient colour is the colour an object reflects when illuminated by indirect light, and the emission colour is the `glow` emitted from the object without any external illumination.

> 这些特性共同决定了材质的光泽。OpenGL ES 为对象定义了镜面反射颜色和漫反射颜色，以及两种附加颜色。环境色是物体被间接光照射时反射的颜色，发射色是物体在没有任何外部照明的情况下发出的 `辉光` 。

In addition to the properties of a surface, the colour of an object depends on the angle at which light is emitted or reflected. A flat-shaded curved surface appears to vary in colour, according to the angle at which light is reflected from it. OpenGL ES captures this information by way of a normal vector, which represents a direction perpendicular to an object’s surface. In fact, normal vectors are defined for each vertex, much like colour and texture coordinates, and are transformed and interpolated for a primitive like any other vertex attribute. This is because although a triangle is planar, this may be shaped around a curved surface and so the normal vector gradually changes over the length and breadth of the primitive. As the normal vector varies, the resultant calculations that use this vary, which affects the computed colour we would naturally expect to see. One further detail about normal vectors is the direction in which they point: the direction of a normal vector is governed by whether the primitive is front-facing or back-facing. A front-facing primitive forms the side of an object that faces the viewer so that the normal vector points towards the viewer. A back-facing primitive has a normal vector that points away from the viewer, as its surface points away from them. The way a primitive faces is captured in the geometry specification stage by way of a winding order of vertices. By default, vertices defined in an anticlockwise order form a front-facing primitive, and those defined in a clockwise order form a back-facing primitive. Figure 10-11 shows an example of the winding order for front-facing and back-facing primitives.

> 除了表面的特性外，物体的颜色还取决于光发射或反射的角度。平面阴影曲面的颜色似乎会根据光线反射的角度而变化。OpenGL ES 通过法向量(表示垂直于对象表面的方向)来捕捉这些信息。事实上，法线向量是为每个顶点定义的，很像颜色和纹理坐标，并且像任何其他顶点属性一样为基本体进行变换和插值。这是因为虽然三角形是平面的，但它可能是围绕曲面形成的，因此法向量会随着基本体的长度和宽度逐渐变化。随着法向量的变化，使用该法向量的结果计算也会发生变化，这会影响我们自然期望看到的计算颜色。关于法向量的另一个细节是它们指向的方向：法向量的方向取决于基本体是正面还是背面。面向前的基本体形成对象面向观察者的一侧，以便法线向量指向观察者。面向后的基本体具有一个法向量，该法向量指向远离观察者的方向，因为其曲面指向远离它们的方向。在几何体规范阶段，通过顶点的缠绕顺序捕获基本体面的方式。默认情况下，按逆时针顺序定义的顶点形成面向前的基本体，而按顺时针方向定义的顶点则形成面向后的基本体。图 10-11 显示了前向和后向原语的缠绕顺序示例。

![[FIGURE 10-11:](#13_9781119183938-ch10.xhtml#rc10-fig-0011) The triangle on the left shows an anticlockwise winding order. Under the standard convention, this would be a forward-facing primitive. The triangle on the right shows a clockwise winding order, which would be a back-facing primitive.](./media/images/9781119183938-fg1011.png)

---

> [!NOTE]

The actual surfaces, especially of CAD models coming from a non-uniform rational basis spline (NURBS) translation, are only approximated by the vertices and triangles in OpenGL. It is the interpolation of the reflections between vertices that gives the model the smooth continuous appearance rather than the tell-tale tessellation (tiling of a surface with geometric shapes) that gives away images as computer generated rather than natural. (NURBS is a mathematical model for generating curves and surfaces.)

> 实际曲面，尤其是来自非均匀有理基样条线(NURBS)平移的 CAD 模型，仅由 OpenGL 中的顶点和三角形近似。正是顶点之间反射的插值为模型提供了平滑的连续外观，而不是以计算机生成的图像而非自然的方式提供图像的信号镶嵌(以几何形状平铺曲面)。(NURBS 是用于生成曲线和曲面的数学模型。)

With the material and light source properties defined, a set of lighting calculations are performed to derive each vertex colour. Essentially vertex colour is formed from the ambient and emission colours of the material, plus a set of contributions per light source in the scene. These contributions are scaled in intensity according to the direction of the surface with respect to the light source (using the normal vector), the position of the viewer with respect to the surface (for specular contributions) and the distance of the light source and viewer from the surface. For the latter, imagine that the influence of a light is essentially a cone of energy spreading out from the source, such that the relative intensity of light follows the familiar inverse square law, becoming less intense at the edges of the cone’s base. Vertex colour is modified still further by the spectacular colour of the material and the light source, the angle between the reflected ray and the viewer, and the shininess of the material, with shinier materials decreasing the amount of visible light as this angle increases. Diffuse contributions are derived from the diffuse colour components in a similar way, except that the angle between the source ray and surface normal is used; as a result surfaces that are parallel to the source ray do not appear lit.

> 定义了材质和光源特性后，将执行一组照明计算以导出每个顶点颜色。基本上，顶点颜色由材质的环境色和发射色以及场景中每个光源的一组贡献组成。这些贡献是根据表面相对于光源的方向(使用法向量)、观察者相对于表面的位置(对于镜面贡献)以及光源和观察者与表面的距离按强度缩放的。对于后者，想象一下，光的影响本质上是一个从光源向外扩散的能量锥，因此光的相对强度遵循熟悉的平方反比定律，在锥的底部边缘变得不那么强烈。顶点颜色通过材料和光源的壮观颜色、反射光线和观察者之间的角度以及材料的光泽度进一步修改，随着角度的增加，更亮的材料会减少可见光量。漫射贡献以类似的方式从漫射颜色分量导出，不同的是使用了源光线和表面法线之间的角度；因此，平行于源射线的表面不会发光。

Because the colour of a vertex is the sum of contributions from all light sources, their combined intensity can easily result in the loss of all colour detail in the scene. This is similar to the concept of a photograph being overexposed. Lighting levels must be carefully tuned to achieve the desired output.

> 因为顶点的颜色是所有光源的贡献之和，所以它们的组合强度很容易导致场景中所有颜色细节的丢失。这类似于照片过度曝光的概念。必须仔细调整照明水平，以达到所需的输出。

As we explained earlier, for versions of OpenGL ES 2.0 and later, the process of transformation and lighting were made much more flexible. They are now known as _vertex shading_, and they’re entirely programmable by the user. Programs specified in an OpenGL ES–specific shader language called GL Shader Language (GLSL) are submitted to the implementation to perform these transformations, and where hardware is provided this may take the form of a GLSL-specific processor where GLSL programs are compiled as needed to perform all the computation required.

> 正如我们前面所解释的，对于 OpenGLES2.0 和更高版本，转换和照明的过程变得更加灵活。它们现在被称为 *vertex shading*，完全可以由用户编程。在 OpenGL ES 特定着色器语言(称为 GL 着色器语言(GLSL))中指定的程序将提交给实现以执行这些转换，如果提供了硬件，则可以采用 GLSL 特定处理器的形式，GLSL 程序将根据需要编译以执行所需的所有计算。

### Primitive Assembly and Rasterisation

Up to this point an application-supplied list of vertex attributes has been transformed into a new list of attributes, converted to the coordinate system of the intended display device. However, these vertices must be used to construct the shapes as we see them on screen. Preparing shapes for display is a two-step process:

> 至此，应用程序提供的顶点属性列表已转换为新的属性列表，并转换为预期显示设备的坐标系。然而，这些顶点必须用于构建我们在屏幕上看到的形状。准备要显示的形状需要两个步骤：

1. **Primitive assembly:** Vertices for each shape are grouped allowing the pipeline to compute how all shapes are to appear in the final output image. 2. **Rasterisation:** Shapes are converted to collections of pixels to be displayed on screen or processed in further rendering steps (see Figure 10-12).

> 1.**图元集合：**对每个形状的顶点进行分组，允许管道计算所有形状在最终输出图像中的显示方式。2.**渲染：**形状被转换为要在屏幕上显示或在进一步渲染步骤中处理的像素集合(见图 10-12)。

During rasterization, all pixels lying inside the boundaries of the shape must be shaded using the data associated with its vertices; those outside should be left unchanged. After these pixels are determined, the attributes associated with each vertex must be interpolated so that each included pixel inherits a weighted average of those belonging to the primitive, depending on its distance from the corners. Attributes such as colour, normal vectors (used in lighting) and texture coordinates may all be interpolated in this way in preparation for per-pixel processing (known as fragment shading in OpenGL ES 2.0). Because these values vary across the shape, at the input to the fragment shading step these are known as _varyings_.

> 在光栅化过程中，位于形状边界内的所有像素必须使用与其顶点关联的数据进行着色；外面的应该保持不变。确定这些像素后，必须对与每个顶点关联的属性进行插值，以便每个包含的像素继承属于基本体的像素的加权平均值，具体取决于其与角点的距离。颜色、法向量(用于照明)和纹理坐标等属性都可以以这种方式进行插值，以准备进行逐像素处理(在 OpenGL ES 2.0 中称为片段着色)。由于这些值在形状上有所不同，因此在片段着色步骤的输入处，这些值被称为 *varyings*。

![[FIGURE 10-12:](#13_9781119183938-ch10.xhtml#rc10-fig-0012) Rasterisation. The crosses indicate primitive samples that will be shaded during fragment processing.](./media/images/9781119183938-fg1012.png)

Although the rasterisation process is largely hidden from and invisible to an OpenGL ES user, it is helpful to know how this step works. Imagine that the _output frame-buffer_, a part of random access memory (RAM) containing a bitmap with a complete frame of data, is divided into a grid of squares representing each of the pixels to be displayed on screen. Coverage of a pixel by a primitive is determined by one or more sample points within the `square` that the pixel represents. When more than one sample point is used per pixel, it’s called multi-sampling and this may be used to improve the output image quality. When multi-sampling is not enabled, a single sample point at the centre of the pixel is used to represent its exact position. If two primitives share an edge through a particular pixel, this must only result in a single output fragment. A set of rules—called _tie break rules_—determine which primitive is chosen in various cases. These rules ensure consistency in the rasterisation process*.* Also

> 尽管光栅化过程在很大程度上对 OpenGLES 用户是隐藏的和不可见的，但了解这一步骤的工作原理很有帮助。想象一下，输出帧缓冲区是随机存取存储器(RAM)的一部分，包含一个完整数据帧的位图，它被分成一个正方形网格，表示屏幕上显示的每个像素。图元对像素的覆盖率由像素表示的 `正方形` 内的一个或多个采样点确定。当每个像素使用多个采样点时，称为多采样，这可用于提高输出图像质量。当未启用多重采样时，像素中心的单个采样点用于表示其准确位置。如果两个基本体通过一个特定像素共享一条边，那么这只能产生一个输出片段。一组名为 *tie-break-rules* 的规则决定在各种情况下选择哪个原语。这些规则确保光栅化过程的一致性*。*此外

> [!NOTE]
> that an included pixel at this stage is called a _fragment_ because it contains more than just colour information; texture coordinates, depth and stencil information are also associated with each frame-buffer location.

If multi-sampling is enabled each pixel may have many sample points, allowing for partial coverage to be represented in the frame-buffer. The single coverage value per pixel contains 1 bit per sample point. The colour and texture coordinates for all samples can be the same, but depth and stencil information are stored per sample. In this way, edge anti-aliasing (smoothing jagged edges) may be achieved without compromising performance, as colour computation (including texture sampling) need only be performed per-pixel. The output pixel is simply an average of the number of included sample points.

> 如果启用多采样，则每个像素可能具有多个采样点，从而允许在帧缓冲区中表示部分覆盖。每个像素的单个覆盖值包含每个采样点 1 位。所有样本的颜色和纹理坐标可以相同，但每个样本都存储了深度和模板信息。通过这种方式，可以在不影响性能的情况下实现边缘抗锯齿(平滑锯齿边缘)，因为颜色计算(包括纹理采样)只需要每个像素执行。输出像素只是包含的采样点数量的平均值。

Having decided which pixels are covered by a particular primitive, it is necessary to compute all the attributes associated with these pixels (known as fragments) from the vertex attributes for the entire primitive. This is done using interpolation and the barycentric coordinates (see Figure 10-13) of each of the primitive’s vertices. By determining the distance of each fragment from the vertices, simple linear interpolation is used to compute colour and texture coordinates, together with any other per-vertex attributes necessary for pixel processing. There is one problem, however. Linear interpolation in device coordinates, post perspective-projection, does not compute consistent results because perspective projection in itself is not a linear transformation. This is where `w` comes in. By dividing each vertex attribute by its respective `w` term, interpolating the `1/w` term and then dividing each interpolated attribute by this interpolated `1/w` perspective-correct interpolation is achieved.

> 在确定特定图元覆盖哪些像素后，有必要从整个图元的顶点属性中计算与这些像素相关的所有属性(称为片段)。这是使用插值和每个基本体顶点的重心坐标(见图 10-13)完成的。通过确定每个片段与顶点的距离，简单的线性插值用于计算颜色和纹理坐标，以及像素处理所需的任何其他逐顶点属性。然而，有一个问题。设备坐标中的线性插值(透视投影后)无法计算一致的结果，因为透视投影本身不是线性变换。这就是 `w` 的含义。通过将每个顶点属性除以其各自的 `w` 项，对 `1/w` 项进行插值，然后将每个插值属性除以该插值的 `1/w’透视正确插值，即可实现。

Barycentric coordinates represent the position of a point inside an object relative to the influence of the object’s vertices. This is usually thought of in terms of the size of mass placed at each vertex such that the point lies at the centre of mass for the overall object. For triangles, this can be visualized more easily using areas rather than masses. In [Figure 10-13](#13_9781119183938-ch10.xhtml#c10-fig-0013), the barycentric coordinates of a general point P, inside a triangle ABC, represent the relative ratios of the areas of PBC, PCA and PAB, respectively. By definition, the coordinates of point P add up to one. This makes varyings interpolation easy as the computed output is simply the sum of each vertex attribute multiplied by its barycentric coordinate component. Perspective-correct computation must include 1/w interpolation, which must be divided through once each sample varying has been determined.

> 重心坐标表示对象内点相对于对象顶点影响的位置。这通常是根据放置在每个顶点的质量大小来考虑的，以使该点位于整个对象的质量中心。对于三角形，这可以使用面积而不是质量更容易地可视化。在[图 10-13](#13_9781119183938-ch10.xhtml#c10-fig-0013) 中，三角形 ABC 内一般点 P 的重心坐标分别表示 PBC、PCA 和 PAB 面积的相对比率。根据定义，点 P 的坐标加起来等于 1。这使得变分插值变得容易，因为计算的输出只是每个顶点属性的和乘以其重心坐标分量。透视正确计算必须包括 1/w 插值，一旦确定了每个样本的变化，就必须将其除以。

![[FIGURE 10-13:](#13_9781119183938-ch10.xhtml#rc10-fig-0013) Barycentric coordinates represent the sizes of mass placed at an object’s corners such that the point lies at the centre of mass for the overall object.](./media/images/9781119183938-fg1013.png)

### Pixel Processing (Fragment Shading)

Fragments that are determined to be inside the primitive and have all their interpolated varyings computed are ready for per-pixel processing. However, fragments may still be invisible as they may lie behind other shapes that also overlap the same fragment location; they are said to be _occluded_. Transparency may also mean that the colour value associated with the fragment is not the final colour written to the frame-buffer; it must be blended with the object behind it as this colour is, in part, also visible to the viewer. Such decisions are handled by a series of tests to influence the resultant operation to the frame-buffer. In OpenGL ES 1.1, sample data computation is limited to a series of fixed-function operations, whereas in OpenGL ES 2.0 general purpose fragment shading gives the application writer much more freedom to compute the colour, depth and stencil values associated with each fragment. We focus first on OpenGL ES 1.1 functionality.

> 确定位于原始体内部并计算了所有插值变量的片段已准备好进行每像素处理。然而，碎片可能仍然是不可见的，因为它们可能位于其他形状后面，这些形状也与相同的碎片位置重叠；据说他们被掩盖了。透明度还可以意味着与片段相关联的颜色值不是写入帧缓冲器的最终颜色；它必须与它后面的物体混合，因为这种颜色在一定程度上也对观众可见。这样的决定由一系列测试来处理，以影响帧缓冲器的结果操作。在 OpenGL ES 1.1 中，样本数据计算仅限于一系列固定的函数操作，而在 OpenGL ES 2.0 中，通用片段着色为应用程序编写者提供了更大的自由度来计算与每个片段相关的颜色、深度和模板值。我们首先关注 OpenGL ES 1.1 功能。

Fragments that exit the rasterisation pipeline first make use of any textures that are bound to them. This will be described in more detail in the next section, but essentially a map of a texture stored in memory may be applied directly or used to modify the colour of a fragment sample. Texturing may be used in various ways to achieve lifelike visualisations at low computational cost. OpenGL ES 1.1’s fixed function pipeline then applies a colour sum stage, where a secondary colour may be added to the fragment colour or used to modify the texture colour further (for specular highlights, for example). The final stage in fragment processing is to apply fog*,* which is used to reduce the visibility of objects that are further away from the viewer so that as objects approach the far clip plane, they tend to fade.

> 退出光栅化管道的碎片首先使用绑定到它们的任何纹理。这将在下一节中更详细地描述，但本质上存储在存储器中的纹理图可以直接应用或用于修改碎片样本的颜色。纹理可以以各种方式使用，以低计算成本实现逼真的可视化。OpenGL ES 1.1 的固定功能管道随后应用颜色和阶段，在该阶段中，可以向碎片颜色添加第二颜色，或用于进一步修改纹理颜色(例如，对于镜面高光)。片段处理的最后一个阶段是应用雾*，*，该雾用于降低距离观看者更远的对象的可见性，以便当对象接近远剪辑平面时，它们趋于褪色。

Before we deal with how these colour values are updated for a given sample location, we should mention that it is the depth and stencil data that influence whether this colour is even updated at all. The scene depicts objects in three dimensions, so it follows that parts of objects, or even whole objects, may lie behind others and may not be visible in the frame-buffer. One technique for handling this, called the _painter’s algorithm_, might be to change the order of primitives to be drawn from back to front, allowing those in the foreground to be rendered later and thus appear first. However, not only does the painter’s algorithm fail when different parts of objects intersect and overlap in different portions of the image, but every time the viewing position changes this order would need to be recomputed.

> 在我们讨论如何为给定的样本位置更新这些颜色值之前，我们应该提到，影响这种颜色是否更新的是深度和模板数据。该场景以三维方式描述对象，因此，部分对象甚至整个对象可能位于其他对象之后，在帧缓冲区中可能不可见。处理这一问题的一种技术，称为\_painter 算法，可能是改变从后到前绘制图元的顺序，从而允许稍后渲染前景中的图元，从而使其先出现。然而，不仅当对象的不同部分在图像的不同部分相交和重叠时，画家的算法会失败，而且每次观看位置改变时，都需要重新计算这个顺序。

Instead, OpenGL ES uses a depth buffer to store the position of each visible frame-buffer sample in the scene. For each primitive, the depth of a sample to be updated is compared with that in the frame-buffer; if it is occluded, the colour value is not updated; otherwise, the colour is written to the frame-buffer and the depth value is also updated. There is one further wrinkle with this technique. Following transformation and rasterisation it is possible that two primitives lie in the same plane, but the interpolation of depth is not consistently computed. This can lead to depth fighting, where pixels of one object can `bleed` into those of another co-planar object, which is particularly obvious during animation where the transformations are likely to change subtly from frame to frame. OpenGL ES provides a mechanism called _polygon offset_ to set displacements of primitives based on their slope and/or bias. However, care from the application writer together with consistent varyings interpolation can ensure that these effects are minimised.

> 相反，OpenGL ES 使用深度缓冲区来存储场景中每个可见帧缓冲区样本的位置。对于每个基元，将要更新的样本的深度与帧缓冲区中的深度进行比较；如果被遮挡，则不更新颜色值；否则，颜色被写入帧缓冲器，并且深度值也被更新。这项技术还有一个问题。在变换和光栅化之后，两个基本体可能位于同一平面中，但深度的插值计算不一致。这可能会导致深度冲突，其中一个对象的像素会 `渗入` 到另一个共面对象的像素中，这在动画过程中尤为明显，在动画中，变换可能会在帧与帧之间发生微妙变化。OpenGL ES 提供了一种称为 *polygon offset* 的机制，用于根据基本体的斜率和/或偏移设置基本体的位移。然而，应用程序编写者的谨慎以及一致的变量插值可以确保这些影响最小化。

The depth test is one example of a fragment test—an operation that may be used to control the update of a sample in the final frame-buffer. There are other tests, but the general principle is to perform a comparison of a computed value against the existing value in the frame-buffer; based on the outcome the value may be updated or not.

> 深度测试是片段测试的一个示例，该操作可用于控制最终帧缓冲器中样本的更新。还有其他测试，但一般原则是将计算值与帧缓冲区中的现有值进行比较；基于结果，可以更新或不更新该值。

Other fragment tests include the alpha test and the stencil test. The alpha test performs the fragment test on the alpha channel of a given sample, and depending on the test result may be used to discard portions of a primitive pixel by pixel. The stencil test may also be used to eliminate fragments based on a comparison of a reference value and a stored frame-buffer value. However, it may also modify the contents of the stencil buffer for a sample, depending on the outcome of the depth and stencil tests.

> 其他片段测试包括 alpha 测试和模板测试。阿尔法测试在给定样本的阿尔法通道上执行片段测试，根据测试结果，可以逐个像素地丢弃原始像素的部分。模板测试还可用于基于参考值和存储的帧缓冲值的比较来消除片段。然而，它也可以根据深度和模板测试的结果修改样本的模板缓冲区的内容。

Following the fragment tests, the final colour in the frame-buffer may be replaced directly or modified further according to the configuration specified by the user. Blending is one of these stages, which derives an output pixel colour as a linear combination of the sample and existing frame-buffer colours. Blend factors are individually applied to the source (sample) and destination (frame-buffer) colours before addition or subtraction to form the new colour to be written to the frame-buffer.

> 在片段测试之后，可以根据用户指定的配置直接替换或进一步修改帧缓冲器中的最终颜色。混合是其中一个阶段，它将输出像素颜色作为样本和现有帧缓冲颜色的线性组合。混合因子在加法或减法之前分别应用于源(样本)和目标(帧缓冲区)颜色，以形成要写入帧缓冲区的新颜色。

In addition to blending, a set of logical operations is available to the user. These provide a set of bitwise operations that can be used to modify the frame-buffer contents using source and destination colours. Each operation is separately applied to each colour component and can be disabled to allow the sample colour to be written straight to the frame-buffer.

> 除了混合，用户还可以使用一组逻辑操作。它们提供了一组按位操作，可用于使用源和目标颜色修改帧缓冲区内容。每个操作分别应用于每个颜色分量，并且可以禁用，以允许将样本颜色直接写入帧缓冲区。

Again, OpenGL ES 2.0 completely transformed the fragment processing pipeline by providing a general-purpose platform on which processing could be performed on each sample. An additional set of GLSL functions completely replace the fixed-function texture environment, colour sum and fog components of the pipeline. For hardware implementations these GLSL functions are again compiled as needed to run on custom shader processor cores, part of the process now called _fragment shading._

> 同样，OpenGLES2.0 通过提供一个通用平台，可以对每个样本进行处理，从而彻底改变了碎片处理管道。一组额外的 GLSL 功能完全取代了管道的固定功能纹理环境、颜色和雾分量。对于硬件实现，这些 GLSL 函数会根据需要再次编译，以在自定义着色器处理器内核上运行，这是现在称为 *fragment 着色的过程的一部分*

### Texturing

Texture mapping is a fundamental resource used extensively to compute the colours of rendered surfaces, either directly from an image in memory or via additional processing that may depend on image or geometry data. With texture mapping, coordinates of vertices are matched up with coordinates of a texture. The functionality available to the OpenGL ES programmer has improved dramatically over the years, but the fundamental concepts remain the same.

> 纹理映射是广泛用于计算渲染表面颜色的基本资源，无论是直接从内存中的图像还是通过可能依赖于图像或几何数据的附加处理。通过纹理映射，顶点的坐标与纹理的坐标相匹配。多年来，OpenGLES 程序员可用的功能得到了显著改进，但基本概念保持不变。

A _texture_ is a digital image stored in memory. It can be sampled as part of fragment processing in order to derive a colour for each sample or each pixel to be written to the frame-buffer. In its simplest form, texturing is a computationally cheap way of adding detail to the surface of an object. Consider rendering a three-dimensional model of a brick-built house. The walls could be constructed brick by brick, each brick transformed and lit individually, together with its surrounding mortar. The quality of the resulting scene would be high, but this would be at the expense of complex geometry and a high number of calculations to be computed as the scene is animated. The wall itself is a complete entity; each brick does not move in relation to the others. All that is required is a repeatable pattern of bricks and mortar to be pasted onto a model of a complete wall. This is where texturing comes in. An image of bricks and mortar is stored in memory, and as pixels are rendered across a primitive spanning the whole wall they simply sample the next colour stored in memory. In effect, the image stored in memory is copied to the surface of the object in the frame-buffer. As the wall is transformed in the scene, this image may need to be scaled and filtered, but this is all possible via texture mapping. Textures may be used to colour objects, to apply effects to existing object surfaces or purely as a general source of data to the more recent OpenGL ES 2.0 fragment shaders.

> 文本是存储在内存中的数字图像。它可以作为片段处理的一部分进行采样，以便导出要写入帧缓冲器的每个样本或每个像素的颜色。在其最简单的形式中，纹理是一种计算成本低廉的向对象表面添加细节的方法。考虑渲染砖砌房屋的三维模型。这些墙可以一砖一砖地建造，每一块砖都经过改造，并与周围的砂浆一起单独点燃。生成的场景的质量会很高，但这将以复杂的几何体和场景动画时要计算的大量计算为代价。墙本身是一个完整的实体；每一块砖都不会相对于其他砖移动。所需要的只是一种可重复的砖块和砂浆图案，以粘贴到完整的墙壁模型上。这就是纹理的来源。砖块和灰泥的图像被存储在内存中，当像素在整个墙壁上渲染时，他们只需对存储在内存的下一种颜色进行采样。实际上，存储在内存中的图像被复制到帧缓冲区中对象的表面。在场景中变换墙时，可能需要缩放和过滤此图像，但这都可以通过纹理映射实现。纹理可用于为对象着色，将效果应用于现有对象曲面，或纯粹作为最新 OpenGL ES 2.0 片段着色器的通用数据源。

Textures are stored in memory as rectangular arrays of image data in much the same way as image data is stored in the frame-buffer. Each element is known as a _texel_. Originally, the dimensions of textures were restricted to power-of-two sizes (for example, 32, 64 or 2*<sup>n</sup>* texels in width/height) to simplify the sampling calculations, but in OpenGL ES 2.0 these restrictions have been lifted. Texture images are referenced via texture coordinates—per-vertex attributes that detail where in each dimension to sample the texture. The whole texture can be referenced by a coordinate in the range \[0,1]; individual texels may be accessed by multiplying the coordinates by the appropriate dimensions of the image. If the coordinates lie outside the range \[0,1] one of several things may happen. If wrapping is enabled, the texture may repeat (by ignoring the whole part of the coordinate and sampling using the fractional part), or it may be clamped so that the outermost texel is sampled (clamp-to-edge) or a border texel is sampled (clamp-to-border). This is configurable by the application writer, depending on the desired output.

> 纹理作为图像数据的矩形阵列存储在存储器中，其方式与图像数据存储在帧缓冲区中的方式大致相同。每个元素都称为 *texel*。最初，纹理的尺寸被限制为两个大小的幂(例如，32、64 或 2*<sup>n</sup>*纹素的宽度/高度)，以简化采样计算，但在 OpenGL ES 2.0 中，这些限制已被取消。纹理图像通过每个顶点的纹理坐标属性进行引用，这些属性详细说明了每个维度中采样纹理的位置。整个纹理可以由\[0,1]范围内的坐标引用；可以通过将坐标乘以图像的适当尺寸来访问各个纹素。如果坐标位于\[0,1]范围之外，可能会发生以下情况之一。如果启用了包裹，纹理可以重复(通过忽略坐标的整个部分并使用分数部分进行采样)，或者可以对其进行钳制，以便对最外层的纹素进行采样(钳制到边缘)或对边界纹素进行抽样(钳制边界)。这可由应用程序编写器根据所需的输出进行配置。

The sampling of textures may also vary depending on the specified filtering mode. Texture coordinates specify an exact location at which to sample the image stored in memory, but this is highly unlikely to fall in the centre of a specific texel. If nearest filtering is selected, the nearest texel to the sampling point is chosen, which is cheap and simple to implement. A more precise result may be obtained (in two dimensions) by choosing the four texels that are nearest to the sampling point and taking a weighted average of these according to the distance of the sampling point from each of them. This is known as _bilinear filtering_ because a simple 2×2 box filter is used to derive the appropriate texel colour, as shown in Figure 10-14.

> 纹理的采样也可能根据指定的过滤模式而变化。纹理坐标指定了对存储在内存中的图像进行采样的准确位置，但这极不可能落在特定纹素的中心。如果选择最近滤波，则选择离采样点最近的纹素，这既便宜又简单。通过选择最接近采样点的四个纹素，并根据采样点与它们中的每一个的距离对这些纹素进行加权平均，可以获得更精确的结果(在二维中)。这被称为 *bilinear filtering*，因为使用了一个简单的 2×2 方框滤波器来导出适当的纹素颜色，如图 10-14 所示。

![[FIGURE 10-14:](#13_9781119183938-ch10.xhtml#rc10-fig-0014) The dark grey dot indicates the sample position against the texture in memory. If nearest filtering is selected, texel A will be chosen. If bilinear filtering is selected, the colour data from texels A, B, C and D will be blended together linearly, using the fractional distances α and β.](./media/images/9781119183938-fg1014.png)

Texture images may be applied to objects that are large and close to the viewer or small objects that are much further away. The texel sampling rate for distant objects can cause noticeable visual artefacts (distortions): two adjacent screen pixels of an object far in the distance may correspond to texels spaced a long way apart in the same texture. Simply applying bilinear filtering for successive pixels can result in a huge loss of detail and undesirable moiré patterns. The correct process would be to compute the average of all the texels surrounding each sample point such that successive samples capture all the image data. At full resolution this could result in averaging hundreds of texels at huge computational cost. The solution is called _mipmapping_. Mipmaps are a sequence of precomputed down-filtered textures stored with the original image. Each mipmap is half the width and half the height of the previous image. (See Figure 10-15.) A complete set of mipmaps is computed, right down to an image of just 1×1 texel. The cost of storing a full set of quarter-size images is 33%, but the improved quality in texturing and reduction in filtering computation more than makes up for this.

> 纹理图像可以应用于距离观察者较近的较大对象或距离观察者远得多的较小对象。远处物体的纹素采样率会导致明显的视觉伪影(失真)：远处物体的两个相邻屏幕像素可能对应于同一纹理中相隔很远的纹素。简单地对连续像素应用双线性滤波会导致细节的巨大损失和不期望的莫尔图案。正确的过程将是计算围绕每个采样点的所有纹素的平均值，使得连续采样捕获所有图像数据。在全分辨率下，这可能会导致以巨大的计算成本平均数百个纹素。该解决方案称为 *mipmapping*。Mipmaps 是与原始图像一起存储的预先计算的向下过滤纹理序列。每个 mipmap 的宽度和高度是前一图像的一半。(见图 10-15)计算出一组完整的 mipmap，精确到 1×1 纹素的图像。存储全套四分之一大小的图像的成本为 33%，但纹理质量的提高和过滤计算的减少远远弥补了这一点。

![[FIGURE 10-15:](#13_9781119183938-ch10.xhtml#rc10-fig-0015) A collection of mipmaps, each half the width and half the height of the previous level.](./media/images/9781119183938-fg1015.png)

To take advantage of mipmaps, it is necessary to compute a suitable size at which to sample the texture. This is known as the correct _level-of-detail_ (_LOD_)_._ The most detailed image is level 0; as the level increases the image size shrinks and less detail is visible. To work out a suitable LOD, we pick adjacent screen space pixels of a primitive and compute the spacing of their texture coordinates in each dimension.

> 为了利用 mipmaps，需要计算一个合适的大小，以便对纹理进行采样。这被称为正确的细节级别*(\_LOD*)*。*最详细的图像为 0 级；随着级别的增加，图像大小会缩小，可见的细节也会减少。为了计算出一个合适的 LOD，我们选取一个基本体的相邻屏幕空间像素，并计算它们在每个维度上的纹理坐标的间距。

> [!NOTE]
> that these texture coordinates have been interpolated from the original texture coordinates of the constituent vertices. The LOD is then increased until the spacing of texels most closely matches the spacing of adjacent pixels. As each level increases, adjacent texels contain information from all of the pixels of the original image through successive averaging, thereby reducing the likelihood of visual artefacts. Bilinear filtering can now be performed at the chosen LOD.

However, bilinear filtering also has its limitations. Transitions in LOD as an object moves away from the viewer can lead to obvious changes in the sharpness of the sampled image. This is alleviated by a method called _trilinear filtering_. Instead of choosing the LOD that most closely matches the pixel spacing, we choose the levels directly below and directly above the optimal spacing, perform a bilinear filter at each level and then blend these two results. This ensures smooth transitions between chosen mipmaps.

> 然而，双线性滤波也有其局限性。当对象远离观察者时，LOD 中的变换会导致采样图像的锐度发生明显变化。这可以通过名为 *trilinear filtering* 的方法来缓解。我们不选择与像素间距最接近的 LOD，而是选择最佳间距正下方和正上方的级别，在每个级别执行双线性滤波，然后混合这两个结果。这确保了所选 mipmap 之间的平滑过渡。

So far we have described the texturing process for simple two-dimensional lookups. Using the texture coordinates for a pixel and its neighbours, we choose an appropriate LOD, from which sample points are derived for texels that must be fetched from the image stored in memory. Once fetched, they may be blended according to the filtering mode specified by the user.

> 到目前为止，我们已经描述了用于简单二维查找的纹理化过程。使用像素及其相邻像素的纹理坐标，我们选择适当的 LOD，从中导出必须从存储在内存中的图像中提取的纹理像素的采样点。一旦获取，它们可以根据用户指定的过滤模式进行混合。

OpenGL ES 2.0 also adds support for cube-map textures. A cube map is six-sided block with a different image of the same scene on each side (face). The cube structure is especially useful for creating light and reflection maps that are applied to surfaces to control their brightness. Three texture coordinates (`s`, `t` and `r`) are used to describe a normalised vector pointing from the cube’s centre towards a particular face. The magnitude of the largest component is used to select a face, with the remaining two coordinates used to reference a sample point in the desired 2D image. Although the edges (or seams) of the cube faces can result in undesirable visual effects, the computational efficiency of building reflection and complex light maps have cemented cube-mapping as a valuable tool for developers.

> OpenGL ES 2.0 还增加了对立方体贴图纹理的支持。立方体贴图是六面块，每面都有相同场景的不同图像。立方体结构对于创建应用于曲面以控制其亮度的光和反射贴图特别有用。三个纹理坐标( `s` 、 `t` 和 `r` )用于描述从立方体中心指向特定面的归一化矢量。最大分量的大小用于选择面，其余两个坐标用于参考所需 2D 图像中的采样点。尽管立方体表面的边缘(或接缝)可能会产生不理想的视觉效果，但建筑反射和复杂光照贴图的计算效率使立方体贴图成为开发人员的宝贵工具。

In OpenGL ES 1.1, when the fetch and filtering of texels is complete, this data is supplied to the fragment processing pipeline by way of a texture environment. In this final step the (untextured) fragment colour is combined with the filtered texel value and an optional environment colour according to one of a set of fixed-function combination functions. These range from modulation of the existing fragment colour to an alpha blended value or complete replacement with the textured colour.

> 在 OpenGL ES 1.1 中，当提取和过滤纹素完成时，这些数据通过纹理环境提供给片段处理管道。在该最后步骤中，根据一组固定函数组合函数中的一个，将(未纹理化的)片段颜色与过滤的纹素值和可选的环境颜色组合。这些范围从现有碎片颜色的调制到阿尔法混合值或完全替换为纹理颜色。

> [!NOTE]
> that OpenGL ES 1.1 also permits multi-texturing, where more than one texture can be independently sampled and used to compute the output colour for a given fragment. Although these texture pipelines are conceptually separate, the combination of textured colours is performed in ascending order of texture units under one texture environment. However, the limited number of units, together with the inability to move data between texture stages, forces a multi-pass approach to achieve complex texturing effects.

In OpenGL ES 2.0 there is full flexibility in the combination of textured colours through the generic fragment shading pipeline. Texture units are accessed via fragment shaders and texture results are combined as part of the user-defined program supplied by the developer.

> 在 OpenGL ES 2.0 中，通过通用片段着色管道，纹理颜色的组合具有充分的灵活性。通过片段着色器访问纹理单元，并将纹理结果作为开发人员提供的用户定义程序的一部分进行组合。

## Modern Graphics Hardware

Now that you have an understanding of the OpenGL ES graphics pipeline, you’re in a position to see how various stages are candidates for specialised hardware acceleration. In order for hardware acceleration to be possible, a layer of software must exist between the standard OpenGL ES API and the GPU; this is called the _driver_, and it runs on the main CPU. In addition to implementing features on the CPU, which aren’t accelerated by graphics hardware, the driver interprets API calls and translates them into a set of controls that are used to configure and initiate the GPU to perform rendering. Vertex-attribute buffers, textures and programs must be derived and positioned in memory, where they are accessible to the graphics core before any instruction is given to begin processing.

> 现在，您已经了解了 OpenGLES 图形管道，您可以看到各个阶段是如何适合专门硬件加速的。为了实现硬件加速，标准 OpenGL ES API 和 GPU 之间必须存在一层软件；这叫做 *driver*，它在主 CPU 上运行。除了在 CPU 上实现图形硬件无法加速的功能外，驱动程序还解释 API 调用并将其转换为一组控件，用于配置和启动 GPU 以执行渲染。顶点属性缓冲区、纹理和程序必须导出并放置在内存中，在发出任何开始处理的指令之前，图形核心可以在内存中访问它们。

As with features at the API level there are competing requirements in terms of performance and cost that drive the decision to offload functionality to specialised hardware, but OpenGL ES is specified loosely enough to allow implementers some freedom to choose different approaches.

> 与 API 级别的功能一样，在性能和成本方面存在竞争性要求，这促使决定将功能卸载到专用硬件，但 OpenGLES 的规定足够宽松，允许实现者自由选择不同的方法。

At the end of this section we review in more detail Raspberry Pi’s graphics hardware: the VideoCore IV GPU.

> 在本节末尾，我们将更详细地回顾 Raspberry Pi 的图形硬件：VideoCore IV GPU。

### Tiled Rendering

One of the key questions facing graphics hardware architects is how to deal with the immense amount of data transferred to and from memory. Considering the frame-buffer traffic alone, rendering to a 1080p resolution, 4× multi-sampled buffer with 32 bits of colour and 32 bits of depth-stencil data constitutes approximately 64 megabytes (MB) of data. Updating this buffer at 60 frames per second (smooth user-interface transitions demand such a frame rate) requires a bandwidth to main memory of more than 3.6 gigabytes per second (GB/s). However, this assumes that each and every fragment sample is rendered only once. Transparent objects or occluded objects that can’t be discarded earlier in the pipeline mean that even for 2× overdraw (that is, each sample is rendered twice per frame), it would be necessary to read each sample from memory once and write to each sample twice. The required bandwidth would exceed 10GB/s without accounting for reading of the vertex attributes and textures necessary to compute the desired fragment data.

> 图形硬件架构师面临的一个关键问题是如何处理大量的数据传输到内存和从内存传输数据。仅考虑帧缓冲区流量，渲染到 1080p 分辨率，具有 32 位颜色和 32 位深度模板数据的 4× 多采样缓冲区构成了大约 64 兆字节(MB)的数据。以每秒 60 帧的速度更新此缓冲区(平滑的用户界面转换需要这样的帧速率)需要主存储器的带宽超过每秒 3.6 千兆字节(GB/s)。然而，这假设每个片段样本只渲染一次。不能在管道中较早丢弃的透明对象或遮挡对象意味着即使是 2× 透支(即，每个样本每帧渲染两次)，也需要从内存中读取每个样本一次，并向每个样本写入两次。所需带宽将超过 10GB/s，而不考虑计算所需片段数据所需的顶点属性和纹理的读取。

Immediate mode renderers store frame-buffer data in off-chip memory (memory that’s not built into the processor), such that as each draw call (request to the GPU to render an image) is processed, the colour, depth and stencil data is immediately updated. In order for this to be efficient, a huge _bandwidth_ between graphics hardware (GPU) and graphics memory must be provided, which is expensive in terms of cost and power. In the PC and console domain, graphics cards contain large configurations of dedicated dynamic random access memory (DRAM), with up to 8GB of addressable memory accessible at up to 32GB/s. Such configurations are impractical for mobile devices, however. To cope with reduced bandwidth and a smaller power envelope, _tile-based rendering_ was devised.

> 即时模式渲染器将帧缓冲区数据存储在片外存储器(未内置在处理器中的存储器)中，以便在处理每个绘制调用(请求 GPU 渲染图像)时，立即更新颜色、深度和模板数据。为了提高效率，必须在图形硬件(GPU)和图形内存之间提供巨大的带宽，这在成本和功耗方面都很昂贵。在 PC 和控制台领域，图形卡包含大量配置的专用动态随机存取存储器(DRAM)，可访问的可寻址存储器高达 8GB，速度可达 32GB/s。然而，这种配置对于移动设备是不切实际的。为了应对带宽减少和功率包络较小的问题，设计了基于文件的渲染。

---

> [!NOTE]

Bandwidth is the capacity of a link through which information is provided.

> 带宽是提供信息的链路的容量。

Tiled renderers divide the output frame-buffer into an array of squares or rectangles (called tiles), each containing a subset of the pixels to be rendered for the scene. Tiles are typically small (approximately 16×16 or 32×32 pixels) and need not be square. Each tile is then rendered separately but only once for all primitives that contribute to that particular portion of the image. To do this the GPU must first work out which primitives contribute to each tile in the image. This process is known as _tile binning_ (see Figure 10-16). The hardware calculates the position of each primitive in device coordinates, and if any part lies within a tile boundary it is appended to the list of primitives to be rendered for that tile. Rendering then proceeds tile-by-tile, focusing only on the geometry that contributes to the output image for that tile. The immediate bandwidth can be provided by local on-chip memory and the main frame-buffer need only be written to once, reducing the power associated with accessing off-chip DRAM.

> 平铺渲染器将输出帧缓冲区划分为一个正方形或矩形阵列(称为平铺)，每个都包含要为场景渲染的像素子集。平铺通常很小(大约 16×16 或 32×32 像素)，不需要是正方形。然后，每个平铺都会单独渲染，但对于所有有助于图像特定部分的基本体，只渲染一次。要做到这一点，GPU 必须首先确定哪些图元对图像中的每个平铺有贡献。这个过程被称为 *tile binning*(见图 10-16)。硬件计算每个图元在设备坐标中的位置，如果任何部分位于平铺边界内，则将其附加到要为该平铺渲染的图元列表中。然后，渲染逐块进行，只关注对该块的输出图像有贡献的几何体。直接带宽可以由本地片上存储器提供，并且主帧缓冲器只需要写入一次，从而减少了与访问片外 DRAM 相关的功率。

![[FIGURE 10-16:](#13_9781119183938-ch10.xhtml#rc10-fig-0016) Tile binning. The set of primitives that overlap each tile is recorded in memory. Rendering is processed on a tile-by-tile basis for each overlapping primitive.](./media/images/9781119183938-fg1016.png)

The amount of processing performed during the binning step may also vary between architectures. By sorting incoming primitives from front to back it is also possible to remove occluded objects entirely from the rendering step, thus saving further processing power and memory bandwidth later in the pipeline. This technique is known as _tile-based deferred rendering_. Other similar techniques are described in the next section.

> 在装仓步骤期间执行的处理量也可以在架构之间变化。通过从前到后对传入的图元进行排序，还可以从渲染步骤中完全移除被遮挡的对象，从而在稍后的管道中进一步节省处理能力和内存带宽。这种技术称为基于文件的延迟渲染。下一节将介绍其他类似的技术。

### Geometry Rejection

In additional to the large amount of data associated with 3D rendering, the increased complexity of geometry meshes, lighting and fragment processing means that the computation required for each output pixel can limit the achievable frame-rates for modern applications. It is therefore highly advantageous to discard objects that are invisible to the viewer as early as possible in the pipeline. Rejection of objects is achieved through a selection process commonly referred to as culling.

> 除了与 3D 渲染相关的大量数据之外，几何网格、照明和碎片处理的复杂性增加意味着每个输出像素所需的计算可能会限制现代应用的可实现帧速率。因此，在管道中尽早丢弃观众看不见的对象是非常有利的。通过通常称为剔除的选择过程实现对象的剔除。

One of the key requirements of a modern hardware GPU is to accelerate the lighting and transformation parts of the pipeline efficiently, which is done using a process known as _vertex shading_ in OpenGL ES 2.0. To achieve this, primitive data in the form of vertex references must be supplied to the hardware, together with the addresses in memory of the attributes associated with these vertices. These must be processed to determine the position of an object in the scene; for tiled renderers this is essential for tile binning. A dedicated memory fetch engine accumulates these attributes, which may be spread across more than one array structure in memory depending on how these have been set up via the OpenGL ES API.

> 现代硬件 GPU 的关键要求之一是高效地加速管道的照明和转换部分，这是使用 OpenGL ES 2.0 中的 *vertex shading* 过程完成的。为了实现这一点，必须向硬件提供顶点引用形式的原始数据，以及与这些顶点相关的属性的内存地址。必须对这些进行处理，以确定场景中对象的位置；对于平铺渲染器，这对于平铺分格至关重要。专用内存获取引擎会累积这些属性，这些属性可能会分布在内存中的多个数组结构中，具体取决于如何通过 OpenGL ES API 设置这些属性。

> [!NOTE]
> that some form of caching is probably sensible at this stage; depending on the order of vertex references and primitive type, some reuse of vertex attributes is expected as they are likely to be referenced more than once in the primitive stream. The references themselves follow a convention to specify whether the surface is facing towards or away from the viewer. If an anticlockwise winding order is used to define front facing polygons then any primitive that has been specified with clockwise-ordered vertices in screen space may not be visible. This information is particularly useful for opaque objects where the back-facing primitives are occluded by the front-facing ones. The hardware can spot this by computing the surface normal vector of the primitive and working out its direction with respect to the position of the viewer. If the shape faces away from the viewer it may be discarded from the pipeline; this is known as back-face culling. By doing this, the rasterisation and fragment processing steps are avoided, which improves performance without having any effect on the output image.

There are also other ways in which invisible geometry may be discarded. Recall the viewing volume mentioned earlier; this is the three-dimensional region that is visible to the observer and is approximated by a truncated pyramid known as the frustrum, which determines which objects are included and which are cut out of a scene*.* Objects that undergo geometric transformations may end up completely outside of the frustrum and can be discarded entirely prior to rasterisation.

> 还有其他方式可以丢弃不可见的几何体。回想前面提到的观看量；这是观察者可见的三维区域，由一个被称为截头体的截头棱锥近似，它决定了哪些对象被包括在场景中，哪些对象被从场景中切割出来。\*经过几何变换的对象最终可能完全位于截头体之外，并且可以在光栅化之前完全丢弃。

> [!NOTE]
> that objects may also lie so far into the distance that they do not influence the colour of any pixels, despite lying inside the far clip plane.

Of course, objects may lie only partially outside of the viewing volume. In this case only the visible portions of the primitive should be rendered and the rest discarded. This process is known as _clipping_. When a primitive is clipped it cannot be represented as a triangle by the original vertices. One or two new triangles may be required (see Figure 10-17), with two new vertices containing attributes interpolated from the original unclipped primitive. These are fed into the pipeline in place of the original primitive so that the rasteriser need only fill visible samples in preparation for fragment processing. Care must be taken to ensure that the varyings are consistent along the newly created edge.

> 当然，对象可能仅部分位于查看体积之外。在这种情况下，只应渲染基本体的可见部分，其余部分将被丢弃。此过程称为 *clipping*。剪裁基本体时，原始顶点不能将其表示为三角形。可能需要一个或两个新三角形(参见图 10-17)，其中两个新顶点包含从原始未修剪的基本体插入的属性。这些数据被输入到管道中以代替原始原始数据，因此光栅化器只需填充可见样本即可进行碎片处理。必须小心确保沿新创建的边缘的变化一致。

![[FIGURE 10-17:](#13_9781119183938-ch10.xhtml#rc10-fig-0017) The top image shows a triangle that lies partially outside of the viewing volume. Clipping creates two new vertices on the frustrum boundary, and one triangle now becomes two.](./media/images/9781119183938-fg1017.png)

Rasterisation is largely a fixed-function task, which lends itself to dedicated hardware acceleration of vector arithmetic to compute the included pixels for primitives being passed through the pipeline. Following transformation, the depth value associated with each vertex is interpolated as the polygon is rasterised, thus providing a per-sample value for the position of the primitive in the scene. Samples that lie behind other opaque objects can be discarded as they will not be visible, but it’s desirable to reject these prior to fragment processing to reduce memory traffic and improve performance. As long as fragment processing does not update the depth of the sample, and the existing object in the scene is opaque, samples may be discarded early if their depth value is smaller than that of the sample currently occupying the frame-buffer; this is known as _early depth rejection_ or _early-z._ There is an obvious latency (delay) issue here; the depth buffer may yet be updated by fragments already being processed in the hardware pipeline, but these are known to lie closer to the viewer than the existing sample. Anything that lies behind the existing sample is safely rejected, but reducing the time between the early depth test and the depth update improves the efficacy of early-z.

> 光栅化在很大程度上是一项固定的功能任务，这使得它可以通过专用的硬件加速矢量运算来计算通过管道的基元所包含的像素。变换之后，与每个顶点相关联的深度值将在多边形光栅化时进行插值，从而为场景中基本体的位置提供每个采样值。位于其他不透明对象后面的样本可以被丢弃，因为它们将不可见，但最好在碎片处理之前拒绝这些样本，以减少内存流量并提高性能。只要片段处理不更新样本的深度，并且场景中的现有对象是不透明的，如果样本的深度值小于当前占用帧缓冲区的样本的深度的值，则可以提前丢弃样本；这被称为早期深度抑制或早期 z 这里有一个明显的延迟问题；深度缓冲区还可以由已经在硬件流水线中处理的片段来更新，但是已知这些片段比现有样本更靠近观众。现有样本后面的任何内容都会被安全地拒绝，但缩短早期深度测试和深度更新之间的时间可以提高早期 z 的效率。

> [!NOTE]
> that implementations may choose to perform the early-z test using bounded objects to improve rejection throughput at the expense of accuracy. Some hardware architectures make use of a multi-pass approach where the depth component of all samples for all primitives is computed before any fragment processing takes place. The second pass then only processes fragments for the nearest pixels, reducing the workload significantly. This technique is known as _deferred rendering._

### Shading

As we’ve already discussed, OpenGL ES 2.0 introduced much more flexible transform, lighting and pixel processing pipelines with the introduction of programmable vertex and fragment shaders. These programs are designed to run on general purpose processors, derived from the native GL shading language (GLSL). Hardware implementations of the OpenGL ES 2.0 pipeline typically contain custom digital signal processors (DSPs), which are closely coupled to the pipeline functions that give or receive (source or sink) data from these stages. Vertex shaders receive vertex positions and properties, known as attributes, and a set of matrix multiplication coefficients and lighting model constants, known as _uniforms_. They output interpolants used later in fragment shading, known as _varyings_. Fragment shaders receive varyings and via built-in texture lookup functions can access textures in memory, outputting colour, depth and stencil data to the frame-buffer. Since both shader types are derived from the same underlying language, they can be targeted at the same DSP allowing for dynamic partitioning of shading resources across different workloads. This is known as _unified shader architecture_ and is common to many GPU shader processors. The lack of required integer support also means that these DSPs, at least initially, are hardened single precision floating-point processors, highly optimised for vector and matrix operations whilst remaining small and low power.

> 正如我们已经讨论过的，OpenGLES2.0 通过引入可编程顶点和片段着色器，引入了更灵活的变换、照明和像素处理管道。这些程序设计为在通用处理器上运行，源于本地 GL 着色语言(GLSL)。OpenGL ES 2.0 管道的硬件实现通常包含自定义数字信号处理器(DSP)，这些处理器与从这些阶段提供或接收(源或接收)数据的管道功能紧密耦合。顶点着色器接收顶点位置和属性(称为属性)以及一组矩阵乘法系数和照明模型常数(称为 *uniforms*)。它们输出稍后在片段着色中使用的插值，称为 *varyings*。片段着色器接收变量，并通过内置的纹理查找函数访问内存中的纹理，将颜色、深度和模板数据输出到帧缓冲区。由于这两种着色器类型都源自相同的底层语言，因此它们可以针对同一 DSP，允许在不同工作负载之间动态划分着色资源。这被称为 `统一着色器架构` (_unified shader architecture_)，对于许多 GPU 着色器处理器来说都很常见。缺乏所需的整数支持也意味着这些 DSP 至少在最初是经过强化的单精度浮点处理器，在保持小功率和低功耗的同时，对矢量和矩阵运算进行了高度优化。

Perhaps the most distinctive property of graphics processing, and specifically shading, is the way in which many operations can be performed in parallel. Vertex shaders run independently for each vertex, and fragment shaders run independently for each sample, which has led to highly parallelised architectures where the same operation is applied to many different inputs at the same time. These are known as single-instruction, multiple data (SIMD) architectures. For every element (that is, a vertex or a fragment sample), these SIMD DSPs possess a huge amount of compute capability for relatively modest instruction bandwidths because the same instruction can be executed many times across different data. It is for this reason that GPUs have become highly desirable platforms for non-graphics related computation, as you will see later in this chapter.

> 也许图形处理(特别是着色)最独特的特性是可以并行执行许多操作的方式。顶点着色器为每个顶点独立运行，片段着色器为每个样本独立运行，这导致了高度并行化的体系结构，其中相同的操作同时应用于许多不同的输入。这些被称为单指令多数据(SIMD)架构。对于每一个元素(即顶点或片段样本)，这些 SIMD DSP 对于相对适中的指令带宽都具有大量的计算能力，因为同一条指令可以在不同的数据上执行多次。正是出于这个原因，GPU 已经成为非图形相关计算的理想平台，正如您将在本章后面看到的。

Given the highly parallel nature of shading, the performance bottlenecks are frequently the result of accesses to shared resources, such as special functions or textures in memory. Multithreading is used to hide the latency associated with such accesses, so when a program stalls on an access, a task switch ensures that another program can make progress, thus hiding the latency. Take a look at the example in Figure 10-18.

> 考虑到着色的高度并行性，性能瓶颈通常是对共享资源(如内存中的特殊函数或纹理)的访问造成的。多线程用于隐藏与此类访问相关的延迟，因此当一个程序在访问时暂停时，任务开关可确保另一个程序能够取得进展，从而隐藏延迟。看看图 10-18 中的示例。

> [!NOTE]
> how thread 0 issues a texture request midway through the program. Once the request is issued, we switch to thread 1 to make use of the processor while thread 0 is stalled, only to return either when thread 1 stalls or ends. When we return to thread 0 the texture access has completed and the latency has been `hidden` . It is common for shader processors to have many more than two threads, trading off complexity with enough parallelism to keep the processor cores busy. Similarly, given the very high number of samples involved in fragment shading there are typically many instances of these SIMD processor cores, all operating simultaneously. The Raspberry Pi GPU has 12 shader processor cores in total; typical PC graphics cards have many hundreds of cores.

![[FIGURE 10-18:](#13_9781119183938-ch10.xhtml#rc10-fig-0018) A threaded shader is divided into two sections (X and Y), which can take turns processing data in order to reduce or hide latency issues related to the need to access the same data for different processes.](./media/images/9781119183938-fg1018.png)

### Caching

Graphics processing is a memory-intensive task that involves frequently moving large amounts of data into and out of memory. Memory resources are further strained by fluctuating demand and limited bandwidth (restrictions inherent in the pipeline through which data travels in and out of memory). Modern GPUs make extensive use of a hierarchy of caches to meet the immediate bandwidth requirements at the lowest level, whilst providing enough local memory so that the stress on the main system memory is reduced. Due to multithreaded shaders and highly parallel architectures, GPUs are fairly tolerant to high system-memory latencies.

> 图形处理是一项内存密集型任务，涉及频繁地将大量数据移入和移出内存。波动的需求和有限的带宽(数据进出内存的管道中固有的限制)使内存资源进一步紧张。现代 GPU 广泛使用缓存层次结构，以满足最低级别的即时带宽需求，同时提供足够的本地内存，从而减轻了对主系统内存的压力。由于多线程着色器和高度并行的体系结构，GPU 对高系统内存延迟相当宽容。

A fully hardware-accelerated OpenGL ES pipeline must read from and write to various data streams during each frame. Many of these streams are backed by a cache in hardware. Vertex positions and properties must be fetched from main memory into the core, and depending on the order in which primitives have been specified these may be reused as the primitive stream is processed. For OpenGL ES 2.0 cores, transformation and lighting are performed through vertex shading, requiring program instructions and uniforms to be fetched from main memory. The SIMD nature of these programs makes caching of this data extremely worthwhile.

> 一个完全硬件加速的 OpenGLES 管道必须在每帧期间读取和写入各种数据流。其中许多流都由硬件中的缓存支持。顶点位置和属性必须从主内存中提取到内核中，并且根据原语的指定顺序，这些属性可以在处理原语流时重用。对于 OpenGLES2.0 内核，转换和照明是通过顶点着色执行的，需要从主内存中获取程序指令和制服。这些程序的 SIMD 特性使得缓存这些数据非常有价值。

The extensive use of textures during fragment processing and its inherent nature as a shading bottleneck mean that sizing and tuning texture caching is also critical to the performance of the system. Textures (and even regions of textures) are likely to have only a finite context, which is very much dependent on the locality of specific objects in the scene. For example, when rendering the wall of a house it is highly likely that, given the correct LOD selection, adjacent frame-buffer samples will correspond to adjacent texture samples. For this reason hardware designers commonly optimise the efficiency of 2D access patterns or create 2D blocks of data to map to consecutive addresses in memory. This improves texture cache efficiency and thus reduces the impact on system memory bandwidth, and therefore power.

> 碎片处理过程中大量使用纹理及其作为着色瓶颈的固有特性意味着调整和调整纹理缓存对系统性能也至关重要。纹理(甚至纹理区域)可能只有有限的上下文，这在很大程度上取决于场景中特定对象的位置。例如，当渲染房屋的墙时，给定正确的 LOD 选择，相邻的帧缓冲区采样很可能与相邻的纹理采样相对应。出于这个原因，硬件设计者通常优化 2D 访问模式的效率或创建 2D 数据块以映射到存储器中的连续地址。这提高了纹理缓存效率，从而减少了对系统内存带宽的影响，从而降低了功耗。

Immediate mode renderers may also implement a cache between the frame-buffer and main memory, again to reduce the load on the main memory system. However, due to the increasing resolution of images and colour depths this caching has become less effective; it is more common to dedicate many megabytes of local frame-buffer memory to facilitate these architectures. Various seventh-generation consoles, such as the Xbox 360 and Playstation 3, use embedded DRAM for this purpose.

> 即时模式渲染器还可以在帧缓冲区和主存储器之间实现缓存，以再次减少主存储器系统上的负载。然而，由于图像分辨率和颜色深度的增加，这种缓存变得不那么有效；更常见的是，将许多兆字节的本地帧缓冲存储器专用于这些架构。各种第七代游戏机，如 Xbox 360 和 Playstation 3，都使用嵌入式 DRAM。

### Raspberry Pi GPU

The Raspberry Pi is built on Broadcom’s BCM2835 application processor (BCM2836 for Raspberry Pi 2), which both contain the VideoCore IV GPU—a highly optimised hardware graphics engine for embedded systems. This GPU supports hardware acceleration of OpenGL ES 1.1 and OpenGL ES 2.0, and makes use of various techniques and optimisations discussed earlier in this section.

> 复盆子 Pi 基于 Broadcom 的 BCM2835 应用处理器(复盆子 Pi2 的 BCM2836)，这两个处理器都包含 VideoCore IV GPU，这是一个高度优化的嵌入式系统硬件图形引擎。该 GPU 支持 OpenGL ES 1.1 和 OpenGL ES 2.0 的硬件加速，并利用本节前面讨论的各种技术和优化。

The VideoCore IV GPU (also known as V3D) is split into a single _core_ module (single processing entity), comprised of the main vertex and primitive pipeline, rasteriser and tile memory, together with a number of compute units called slices, which contain up to four custom 32-bit floating point processors, caches, a special functions unit and up to two dedicated texture fetch and filtering engines. BCM2835 and BCM2836 contain a V3D with three of these slices, each containing four floating point shader processors and two texture units.

> VideoCore IV GPU(也称为 V3D)被拆分为单个 *core* 模块(单个处理实体)，由主顶点和基本流水线、光栅化器和平铺存储器以及多个称为切片的计算单元组成，一个特殊功能单元和多达两个专用纹理提取和过滤引擎。BCM2835 和 BCM2836 包含一个 V3D，其中包含三个切片，每个切片包含四个浮点着色器处理器和两个纹理单元。

Also

> 而且

> [!NOTE]
> that VideoCore IV is a tile-based renderer with deferred vertex shading, which means that full vertex shading only takes place per-tile after binning has occurred. In fact, in order to work out which primitives lie in each tile, a streamlined vertex shader is used to compute just the position of the transformed vertices. This information, along with the other vertex attributes, is then recomputed during rendering in the subsequent pass, minimising the amount of data stored to (and loaded from) memory. This position-only computation during binning is called _coordinate shading_. The front end of the hardware is divided into two distinct pipelines (perhaps confusingly called _threads_): one for binning and one for rendering. To keep things simple we will describe the binning pipeline followed by the rendering pipeline, but these are capable of running simultaneously and dynamically sharing the resources available to them throughout the graphics core.

The Control List Executor (CLE) is the entry point to the hardware, and it fetches the list of control items from memory that is required to configure the core. It dispatches this configuration information to other hardware blocks within the GPU, ensuring that every state set up via the OpenGL ES API is reflected in the hardware processes that follow.

> 控制列表执行器(CLE)是硬件的入口点，它从内存中获取配置内核所需的控制项列表。它将此配置信息分派给 GPU 内的其他硬件块，确保通过 OpenGL ES API 设置的每个状态都反映在随后的硬件进程中。

> [!NOTE]
> the distinction between control items and instructions; for clarity, the information used to configure the GPU pipeline as a whole is communicated through control items, whereas information compiled from GLSL shaders and used in vertex and fragment shading is composed of instructions.

The first few hardware modules in the binning pipeline are concerned with loading vertex attributes from memory in preparation for coordinate shading. References to vertex attributes are fed to the hardware via the CLE in the form of a list of indices—essentially pointers to attributes within the set of arrays set up via the OpenGL ES driver. These indices are fed to the Vertex Cache Manager (VCM), which, in conjunction with the Vertex Cache Direct Memory Access engine (VCD), fetches the vertex attributes from GPU memory and stores them in the Vertex Pipeline Memory (VPM). The VCM caches these pointers to vertex attributes because vertices are often reused in triangle strips and fans, and this caching reduces the number of accesses to the same vertex information in GPU memory, which therefore reduces power and memory bandwidth requirements. The VCM also gathers the vertex attributes into SIMD batches for shading on the custom shader processor (known as the Quad Processing Unit or QPU).

> 装箱管道中的前几个硬件模块与从内存中加载顶点属性以准备坐标着色有关。顶点属性的引用通过 CLE 以索引列表的形式提供给硬件，索引列表本质上指向通过 OpenGL ES 驱动程序设置的数组集合中的属性。这些索引被馈送到顶点缓存管理器(VCM)，该管理器与顶点缓存直接内存访问引擎(VCD)一起从 GPU 内存中获取顶点属性，并将其存储在顶点管道内存(VPM)中。VCM 缓存这些指向顶点属性的指针，因为顶点通常在三角形条带和风扇中重复使用，这种缓存减少了对 GPU 内存中相同顶点信息的访问次数，从而降低了功率和内存带宽要求。VCM 还将顶点属性收集到 SIMD 批次中，以便在自定义着色器处理器(称为四元处理单元或 QPU)上进行着色。

> [!NOTE]
> that the same coordinate shader may be run many times for different vertices, hence the ability to group the vertex data into batches that share a single instruction stream. We will cover the QPU in more detail later. The VPM is a 12 kilobyte (KB) block of on-chip SRAM, which can be accessed in two dimensions. All the information associated with a *vert*ex is stored *vert*ically in a single column, such that a batch is stored as a series of VPM columns. Individual attributes, such as an individual colour component or texture coordinate, can be accessed via a specific _row_ of the memory. This is particularly helpful during coordinate and vertex shading, which computes per-attribute data across the whole SIMD batch of vertices.

After all vertex attributes are present in the VPM, coordinate shading can commence. Coordinate shading is performed on one of the QPUs and is initiated via the QPU Scheduler (QPS), which assumes control of all shading tasks, ensuring a fair distribution of coordinate, vertex and fragment shaders across all available processors (remember that binning and rendering can occur in parallel). The driver is responsible for compiling and linking shader programs to be run on the QPU; locations of the specific instructions and data for the coordinate shader associated with this batch are provided via the CLE. Coordinate shading computes the transformed position of the batch of vertices, which are then used to work out which tiles each primitive intersects. This vertex information is stored in another area (or segment) of the VPM, which can be accessed directly by the Primitive Tile Binner (PTB). The PTB is responsible for tile binning, essentially generating a list of configuration data and primitives that must be processed when rendering each tile. Because it has access to the position data it also performs the first stage of clipping, removing primitives that are completely outside the viewing volume and generating new vertices for primitives that intersect the clip boundaries. The PTB stores tile lists to GPU memory, which contain per-tile control items and primitives that can be read directly by the rendering thread of the CLE. Once this data has been written to memory, rendering can begin for each tile in turn; the core may also begin binning for the next frame simultaneously.

> 在 VPM 中出现所有顶点属性后，可以开始坐标着色。坐标着色在其中一个 QPU 上执行，并通过 QPU 调度器(QPS)启动，QPU 调度器负责控制所有着色任务，确保坐标、顶点和碎片着色器在所有可用处理器上的公平分布(请记住，装箱和渲染可以并行进行)。驱动程序负责编译和链接要在 QPU 上运行的着色器程序；通过 CLE 提供与该批次相关联的坐标着色器的特定指令和数据的位置。坐标着色计算一批顶点的变换位置，然后使用这些顶点计算每个基本体相交的平铺。该顶点信息存储在 VPM 的另一个区域(或段)中，该区域可以直接由原始平铺 Binner(PTB)访问。PTB 负责瓦片分格，本质上生成在渲染每个瓦片时必须处理的配置数据和原语的列表。因为它可以访问位置数据，所以它还执行第一阶段的剪裁，移除完全位于查看体积之外的图元，并为与剪裁边界相交的图元生成新顶点。PTB 将平铺列表存储到 GPU 内存中，其中包含可由 CLE 的渲染线程直接读取的每平铺控制项和原语。一旦将这些数据写入内存，就可以依次为每个平铺开始渲染；核心也可以同时开始下一帧的装箱。

The first stages of the rendering pipeline operate very much like binning. The CLE has a separate hardware thread to process the per-tile control list and fetch the indices for the set of primitives that lie in each tile. Vertex attribute data is refetched from memory via a separate VCM and the single, shared VCD. When all vertex attributes (now including all the vertex data and not just the position components) have been fetched into the VPM, the QPS schedules vertex shading on one of the 12 available QPUs. Vertex shading computes the transformed vertex positions and other attributes, including texture coordinates and lighting, storing this data in a separate VPM segment. However, instead of the PTB, the Primitive Setup Engine (PSE) reads this shaded vertex data from the VPM and begins primitive assembly. Using the indices fetched by the CLE and the associated vertex data in the VPM, the PSE computes the equations for the edges of each input primitive, as well as the plane equations necessary for later interpolation steps. If necessary the PSE also performs the second stage of clipping by fetching the PTB-generated vertices that have been clamped to the viewing volume and preparing associated attributes for subsequent interpolation. The Front-End Pipe (FEP) performs rasterisation, generating a series of 2×2 fragments (or quads) that relate to pixels within the frame-buffer that are covered by the primitive. Quads are chosen to simplify the LOD calculations that may be necessary for texturing during the subsequent fragment shading step. The FEP also stores the depth of each fragment in a buffer so that any later rasterised primitive whose fragments lie behind another visible object may be discarded early in the pipeline. This saves needless computation during fragment shading, and therefore improves performance and saves power.

> 渲染管道的第一阶段的操作非常类似于装箱。CLE 有一个单独的硬件线程来处理每个瓦片控制列表，并获取每个瓦片中的一组基元的索引。顶点属性数据通过单独的 VCM 和单个共享 VCD 从存储器中重新提取。当所有顶点属性(现在包括所有顶点数据，而不仅仅是位置组件)都已提取到 VPM 中时，QPS 会在 12 个可用 QPU 之一上安排顶点着色。顶点着色计算变换的顶点位置和其他属性，包括纹理坐标和照明，将这些数据存储在单独的 VPM 段中。但是，图元设置引擎(PSE)从 VPM 读取此着色顶点数据并开始图元装配，而不是 PTB。使用 CLE 获取的索引和 VPM 中的相关顶点数据，PSE 计算每个输入图元的边的方程，以及后续插值步骤所需的平面方程。如果需要，PSE 还通过获取 PTB 生成的顶点(这些顶点已被夹持到查看体积)并准备相关属性以用于后续插值来执行第二阶段的剪裁。前端管道(FEP)执行光栅化，生成一系列 2×2 片段(或四边形)，这些片段与基本体覆盖的帧缓冲区内的像素相关。选择四边形以简化 LOD 计算，这可能是后续片段着色步骤中纹理化所必需的。FEP 还将每个片段的深度存储在缓冲区中，以便可以在管道中早期丢弃其片段位于另一个可见对象后面的任何稍后光栅化的基元。这在片段着色期间节省了不必要的计算，因此提高了性能并节省了电力。

Quads are gathered into SIMD-sized batches for fragment shading, whilst their positions with respect to the original primitive vertices are used to compute the interpolated attributes or varyings, ready for use by the fragment shader. This is done by the Varyings Interpolator (VRI), one of which exists for each slice, shared between four QPUs. Once a batch is ready to be shaded, the QPS allocates a QPU on which to process the samples. The fragment shader itself is a collection of instructions and data compiled and linked by the driver and placed in GPU memory; the locations of these are again made available to the QPU via the CLE.

> 四边形被收集到 SIMD 大小的批次中进行碎片着色，而它们相对于原始基本体顶点的位置用于计算插值属性或变量，以供碎片着色器使用。这是由可变插值器(VRI)完成的，每个切片都有一个插值器，在四个 QPU 之间共享。一旦批次准备好着色，QPS 将分配一个 QPU 来处理样本。片段着色器本身是由驱动程序编译和链接并放置在 GPU 内存中的指令和数据的集合；这些位置再次通过 CLE 提供给 QPU。

> [!NOTE]
> also that the fragment shader may be threaded; that is to say it may be run in parallel (but not simultaneously with) another fragment shader on the same QPU. As we discussed earlier, this allows the latency of accesses to memory to be hidden and improves utilisation of the processors.

Fragment shading essentially computes the colour (and optionally depth and stencil) components for each sample in the frame-buffer. Each shader may access a shared special functions unit (SFU) for complex mathematical expressions such as logarithms, exponents and reciprocals, together with a specialised texture and memory fetch unit (TMU) for retrieving and filtering texture data.

> 片段着色基本上计算帧缓冲区中每个样本的颜色(以及可选的深度和模板)分量。每个着色器可以访问用于复杂数学表达式(如对数、指数和倒数)的共享特殊函数单元(SFU)，以及用于检索和过滤纹理数据的专用纹理和内存提取单元(TMU)。

Once complete, the fragment information is written to the tile buffer (TLB), which tests each fragment and performs additional operations prior to updating the sample data. Here, the sample data may be discarded or used to modify the existing frame-buffer contents according to the depth and stencil tests. After all the primitives for the tile are processed and fragment shading is complete, the full tile is flushed to GPU memory. Multisampled outputs simply average the four samples together per output-pixel, which is done seamlessly as the tile data is written to main memory. Tiles are 64×64 pixels in size on the Raspberry Pi (32×32 pixels in multisample mode). After the tile has been flushed, the next tile is processed.

> 一旦完成，片段信息就被写入到平铺缓冲区(TLB)，该缓冲区测试每个片段，并在更新样本数据之前执行附加操作。这里，可以丢弃样本数据，或者根据深度和模板测试来修改现有的帧缓冲区内容。处理完平铺的所有基本体并完成碎片着色后，将整个平铺刷新到 GPU 内存中。多采样输出简单地将每个输出像素的四个采样相加平均，这在将平铺数据写入主存储器时无缝完成。复盆子 Pi 上的平铺大小为 64×64 像素(多采样模式下为 32×32 像素)。刷新平铺后，将处理下一个平铺。

> [!NOTE]
> that when transparent objects are rendered on top of one another the order in which fragments are shaded affects the blended output colour; a hardware scoreboard (SCB) is used to ensure fragments that are being shaded in parallel update the TLB in their specified order.

At the heart of both vertex and fragment processing on VideoCore IV’s GPU is the Quad Processing Unit or QPU. This is a multithreaded, 16-way SIMD, 32-bit floating point processor with a customised instruction set for graphics programs. The QPU is physically a four-way SIMD (hence the term quad), designed so that it operates on 2×2 fragments simultaneously and performs the same instruction over four successive clock cycles, thus appearing to the programmer as a 16-way SIMD engine. This allows floating point arithmetic to be performed over multiple cycles, thereby reducing power consumption. Each QPU possesses 32 general purpose registers, which may be split between two threads for fragment shading where latency tolerance is specifically desired. The QPU also has access to a number of closely coupled hardware peripherals, such as the single, shared SFU and VRI units, together with a TMU for every two QPUs. Specific instructions are used to access these units, and results from these peripherals are mapped into two of five temporary working registers (accumulators), which are also shared between threads. There are two ALU pipelines (one for addition and one for multiplication), so that in total, the VideoCore IV GPU can process 24 billion floating point operations per second (24 GFLOPs). It is this immense compute power that software developers want to unlock by way of APIs dedicated to general-purpose computing, such as OpenCL.

> VideoCore IV 的 GPU 上顶点和片段处理的核心是四重处理单元(Quad processing Unit，简称 QPU)。这是一个多线程、16 路 SIMD、32 位浮点处理器，具有用于图形程序的自定义指令集。QPU 在物理上是一个四路 SIMD(因此称为 quad)，其设计可同时对 2×2 个片段进行操作，并在四个连续的时钟周期内执行相同的指令，因此在程序员看来是一个 16 路 SIMD 引擎。这允许在多个周期内执行浮点运算，从而降低功耗。每个 QPU 拥有 32 个通用寄存器，这些寄存器可以在两个线程之间分割，以便在特别需要延迟容差的情况下进行片段着色。QPU 还可以访问多个紧密耦合的硬件外围设备，例如单个共享 SFU 和 VRI 单元，以及每两个 QPU 一个 TMU。特定指令用于访问这些单元，这些外围设备的结果被映射到五个临时工作寄存器(累加器)中的两个，这些寄存器也在线程之间共享。有两条 ALU 管道(一条用于加法，一条用于乘法)，因此 VideoCore IV GPU 每秒可以处理 240 亿次浮点运算(24 GFLOP)。软件开发人员希望通过专用于通用计算的 API(如 OpenCL)来释放这种巨大的计算能力。

The general philosophy behind the VideoCore IV architecture is to offload as much as possible from software and minimise the interaction between the driver and the hardware itself. As a result, interfaces to the rest of the chip infrastructure are limited to a simple programming interface to communicate with the core, a memory access interface to read from and write to GPU memory, and an interrupt for notifying the CPU when binning and rendering jobs are complete. The extensive use of parallelism and low-power techniques mean that the V3D is a highly efficient GPU for mobile devices, proving very effective in accelerating the OpenGL ES pipeline and bringing high-quality GUIs and immersive gaming to embedded systems.

> VideoCore IV 架构背后的总体理念是尽可能从软件中卸载，并将驱动程序和硬件本身之间的交互降至最低。因此，与芯片基础设施其余部分的接口仅限于与内核通信的简单编程接口、从 GPU 内存读取和写入的内存访问接口，以及用于在装箱和渲染作业完成时通知 CPU 的中断。并行性和低功耗技术的广泛使用意味着 V3D 是一款适用于移动设备的高效 GPU，在加速 OpenGL ES 流水线和为嵌入式系统带来高质量 GUI 和沉浸式游戏方面非常有效。

## Open VG

Until now we have focused on OpenGL and the dawn of specialised hardware to accelerate 3D graphics rendering. However, efficient implementation of 2D graphics is also highly desirable. The advent of web browsing has increased the importance of scalable font rendering such that a user can pan and zoom page content at little or no performance cost. Similarly, being able to cheaply compute smooth curves and edges is necessary in a wide array of applications, such as the display of maps and navigation aids in modern smartphones or more directly in graphic design software. A separate open standard was devised for vector graphics, principally aimed at achieving cross-vendor support for exactly these cases: Open Vector Graphics (Open VG). The Raspberry Pi GPU supports OpenVG 1.1.

> 到目前为止，我们一直专注于 OpenGL 和加速 3D 图形渲染的专业硬件。然而，2D 图形的有效实现也是非常期望的。web 浏览的出现增加了可缩放字体渲染的重要性，使得用户可以以很少或没有性能成本来平移和缩放页面内容。类似地，能够廉价地计算平滑曲线和边缘对于广泛的应用来说是必要的，例如在现代智能手机中显示地图和导航设备，或者更直接地在图形设计软件中。为矢量图形设计了一个单独的开放标准，主要目的是实现对以下情况的跨供应商支持：开放矢量图形(OpenVG)。树莓派 GPU 支持 OpenVG 1.1。

Vector graphics is built upon several key concepts: paths, stroking and filling. A path is comprised of one or more line segments, connected by two or more anchor points. These line segments need not be straight. Curved segments may join two points, described by mathematical equations and the path’s associated control points (see Figure 10-19). These curved segments are known as Bézier curves and are named after the French mathematician Pierre Bézier. The areas between curves may be filled with flat-shaded or gradient colour. Open paths consist of start and end points that don’t meet; closed paths join start and end points together. Path definitions include jumps between points, quadratic and cubic equations to join points and methods to obtain the interpolated position along a path, a path bounding box or a tangent to the path at a particular location.

> 矢量图形建立在几个关键概念之上：路径、划动和填充。路径由一条或多条线段组成，由两个或多个锚点连接。这些线段不必是直线。曲线段可以连接两个点，由数学方程和路径的相关控制点描述(见图 10-19)。这些曲线段被称为 Bézier 曲线，以法国数学家皮埃尔·Bézier 的名字命名。曲线之间的区域可以用平面着色或渐变色填充。开放路径由不相交的起点和终点组成；闭合路径将起点和终点连接在一起。路径定义包括点之间的跳跃、连接点的二次方程和三次方程以及沿路径、路径边界框或特定位置的路径切线获得插值位置的方法。

![[FIGURE 10-19:](#13_9781119183938-ch10.xhtml#rc10-fig-0019) In OpenVG shapes are constructed from points linked by paths described by Bézier curves.](./media/images/9781119183938-fg1019.png)

Stroking is the process by which outlines are defined around the path, such as the line width, joining style at the corner of two edges (such as a bevel*,* round or mitre) and the end caps of all lines. These outlines, coupled with the path definitions form objects that are ready to be transformed and rasterised in a similar way to OpenGL ES. However, the purpose of rasterisation is to compute a filtered alpha value for each pixel depending on the coverage of the surrounding geometry. This effectively provides a weighting factor for the subsequent paint stages. The geometry may be windowed using clip rectangles prior to painting, to limit the regions over which colour is applied. This may be further modified by a per-pixel mask, much like the stencil buffer in OpenGL ES, via a series of fixed-function operations such as explicit clearing or adding to or subtracting from application-supplied values.

> 描边是在路径周围定义轮廓的过程，例如线宽、两条边的拐角处的连接样式(例如倒角*、*圆角或斜接)以及所有线的端盖。这些轮廓，加上路径定义，形成了可以以与 OpenGL ES 类似的方式进行变换和光栅化的对象。但是，光栅化的目的是根据周围几何体的覆盖范围，计算每个像素的过滤 alpha 值。这有效地为后续绘制阶段提供了权重因子。在绘制之前，可以使用裁剪矩形对几何图形进行窗口化，以限制应用颜色的区域。这可以通过一系列固定的函数操作(如显式清除或添加应用程序提供的值或从应用程序提供值中减去值)，通过每像素掩码(很像 OpenGL ES 中的模板缓冲区)进行进一步修改。

Painting is the process by which colour is applied to the geometry, either via flat shading, linear gradients or radial gradients, or by sampling and tiling an image from memory. Blending the painted colour values with the output of rasterisation results in a per-pixel colour to be output to the frame-buffer. Filling is the application of paint to any area within a path.

> 绘画是将颜色应用于几何体的过程，可以通过平面着色、线性渐变或径向渐变，也可以通过从内存中采样和平铺图像。将绘制的颜色值与光栅化的输出相混合，将产生要输出到帧缓冲区的每像素颜色。填充是指在路径内的任何区域涂抹油漆。

> [!NOTE]
> that stroking and filling may both incur painting; these are done via separate objects in separate processing steps.

OpenVG was defined with hardware acceleration in mind, together with an API that resembled OpenGL ES. Although completely separate, the similarities mean that the same hardware (with a few simple additions) can be repurposed to support OpenVG. The OpenVG driver must first assemble a list of OpenVG-specific control items to configure the GPU via the existing CLE. The Bézier curve for each path segment is split into a series of straight-line sections using a QPU program generated by the driver. In doing this, the geometry regions that are required to be painted are then covered by a series of triangles in a fan with one common, central vertex. The vertices of these triangles are stored in the VPM.

> OpenVG 的定义考虑到了硬件加速，以及一个类似于 OpenGLES 的 API。虽然完全不同，但这些相似之处意味着相同的硬件(有一些简单的添加)可以重新调整用途以支持 OpenVG。OpenVG 驱动程序必须首先汇编 OpenVG 特定控制项列表，以通过现有 CLE 配置 GPU。使用驾驶员生成的 QPU 程序，将每个路径段的 Bézier 曲线分割成一系列直线段。在这样做的过程中，需要绘制的几何区域将被一系列三角形覆盖，这些三角形位于一个具有一个公共中心顶点的扇形中。这些三角形的顶点存储在 VPM 中。

> [!NOTE]
> that tile binning is still applicable—having computed the position of each triangle, the set of these primitives covering each tile is stored so that rendering can proceed on per-tile basis.

Rendering is performed as a second step, with the set of transformed vertices processed as a triangle fan by the rasteriser. However, depending on the path, multiple triangles may overlay each other indicating whether the pixel lies inside or outside the fill region. A compressed coverage buffer accumulates the count at each pixel location, thereby providing a mask of which fragments must be shaded during painting. This coverage accumulation pipe (CAP) is only present for OpenVG use. Painting and frame-buffer modifications are mapped to the fragment shading process of OpenGL ES 2.0, which provides sufficient flexibility to achieve all required colour effects. One aspect of this, the tiling of image data within a fill region, is supported via an additional child image mode in the TMU. This allows the user to supply an arbitrary window within a texture from which to sample in memory.

> 渲染是作为第二步执行的，光栅化器将变换后的顶点集处理为三角形扇形。然而，取决于路径，多个三角形可以彼此重叠，指示像素是位于填充区域内部还是外部。压缩覆盖缓冲区累积每个像素位置的计数，从而提供了在绘制期间必须对碎片进行着色的遮罩。此覆盖累积管道(CAP)仅用于 OpenVG。绘画和帧缓冲区修改被映射到 OpenGLES2.0 的片段着色过程，这提供了足够的灵活性以实现所有所需的颜色效果。其中的一个方面是通过 TMU 中的附加子图像模式支持在填充区域内平铺图像数据。这允许用户在纹理中提供任意窗口，以便在内存中进行采样。

OpenVG is able to be supported with little additional hardware cost due to the flexibility of the hardware architecture required to support OpenGL ES 2.0. Although OpenVG is not as popular as it once was, it remains a good example of how thoughtful architecture can provide a valuable platform for functionality beyond the primary requirements, something that we also find with the advent of general purpose computing on GPUs, discussed next.

> 由于支持 OpenGL ES 2.0 所需的硬件架构的灵活性，OpenVG 能够在几乎不增加硬件成本的情况下得到支持。尽管 OpenVG 不像以前那样受欢迎，但它仍然是一个很好的例子，说明了深思熟虑的体系结构可以为基本需求之外的功能提供一个有价值的平台，而随着 GPU 上通用计算的出现，我们也发现了这一点，下面将对此进行讨论。

## General Purpose GPUs

As the demands of graphics APIs have increased, GPU hardware architectures have evolved to provide large numbers of general purpose processors on which to perform vertex and fragment shading in parallel. This has resulted in huge floating-point computation potential, which application developers and researchers want to utilise for non-graphics functionality. The Raspberry Pi GPU, with 12 QPUs and 3 SFUs, provides a compute platform of up to 27 billion floating point operations per second. PC graphics cards contain GPUs with hundreds of shader processors and more than 1 teraflop (1 trillion floating point operations per second) of 32-bit floating point performance. Such computation is already used for complex physics simulations and to implement high-quality image processing algorithms on platforms that don’t already contain specialised hardware for this purpose.

> 随着图形 API 需求的增加，GPU 硬件架构已经演变为提供大量通用处理器，在这些处理器上并行执行顶点和片段着色。这就产生了巨大的浮点计算潜力，应用程序开发人员和研究人员希望将其用于非图形功能。Raspberry Pi GPU 具有 12 个 QPU 和 3 个 SFU，提供每秒高达 270 亿次浮点运算的计算平台。PC 图形卡包含 GPU，具有数百个着色器处理器和超过 1 万亿次浮点运算(每秒 1 万亿次)的 32 位浮点性能。这种计算已经用于复杂的物理模拟，并在尚未包含专用硬件的平台上实现高质量的图像处理算法。

### Heterogeneous Architectures

To leverage the available compute power, system architectures must be designed to make offloading tasks to the GPU simple. Architectures that aim to make use of compute elements beyond just the CPU (most commonly the CPU and GPU together) are known as _heterogeneous architectures_. The aim of these systems is to ensure the passing of data between the CPU and GPU is efficient, usually via shared memory.

> 为了利用可用的计算能力，系统架构必须设计为使将任务卸载到 GPU 变得简单。旨在利用 CPU 以外的计算元素(最常见的是 CPU 和 GPU)的体系结构被称为 `永恒体系结构` 。这些系统的目的是确保 CPU 和 GPU 之间的数据传递是有效的，**通常通过共享内存**。

Traditional computer architectures require an algorithm designer to set up data structures in CPU memory (accessible only by the CPU) and copy them to a region of memory accessible only by the GPU. The GPU operates on the data and writes the results back to GPU memory. These results are then copied from GPU memory back to CPU memory for the program to continue. The problem with this is that complex algorithms with large data sets require a lot of data to be moved around, which is prohibitively slow and expensive in terms of memory bandwidth and power.

> 传统的计算机体系结构要求算法设计者在 CPU 存储器(仅可由 CPU 访问)中设置数据结构，并将其复制到仅可由 GPU 访问的存储器区域。GPU 对数据进行操作，并将结果写入 GPU 内存。然后将这些结果从 GPU 内存复制回 CPU 内存，以便程序继续。这方面的问题是，具有大数据集的复杂算法需要移动大量数据，这在内存带宽和功耗方面速度慢得令人望而却步，而且成本高昂。

A far better solution is to allow the CPU and GPU access to a shared region of memory so that copying of data is no longer required. A couple of features are required to make this realisable. The first is virtual memory. Virtual memory is a technique whereby the locations of data structures referenced by processing units are translated before being used to access the physical locations in the memory itself. As a result, the address space in which the CPU or GPU operates does not directly correspond to the address space of the data structures in memory. This address translation is performed by a memory management unit (MMU)_._ The CPU and GPU address virtual memory and each MMU maps virtual memory addresses to physical addresses in main memory. Conceptually, blocks of memory may be shared by providing the same MMU mappings to the CPU and GPU. Pointers to memory are effectively passed between units rather than the data itself. The second feature is memory coherence. Although the CPU and GPU may be given the same view of main memory, each contains a hierarchy of caches to take advantage of data reuse. If both have a copy of the same data in their local caches and one of them updates the data, how does the other unit know to update their copy? Either a hardware broadcast must be sent to all users to inform them that the data must be refetched from main memory (thus guaranteeing coherence in the system), or the developer must track buffer usage and explicitly flush caches that contain stale copies of the data. Both issues are non-trivial to solve.

> 更好的解决方案是允许 CPU 和 GPU 访问共享内存区域，这样就不再需要复制数据。要实现这一点，需要几个功能。第一个是虚拟内存。虚拟存储器是一种技术，通过该技术，处理单元引用的数据结构的位置在用于访问存储器本身中的物理位置之前被转换。结果，CPU 或 GPU 在其中操作的地址空间不直接对应于存储器中的数据结构的地址空间。该地址转换由存储器管理单元(MMU)执行 CPU 和 GPU 地址虚拟内存和每个 MMU 将虚拟内存地址映射到主内存中的物理地址。概念上，可以通过向 CPU 和 GPU 提供相同的 MMU 映射来共享存储器块。**指向内存的指针有效地在单元之间传递，而不是数据本身。**第二个特点是记忆连贯性。尽管 CPU 和 GPU 可能被赋予相同的主内存视图，但每个都包含一个缓存层次结构，以利用数据重用。如果两个单元的本地缓存中都有相同数据的副本，并且其中一个单元更新了数据，那么另一个单元如何知道更新其副本？要么必须向所有用户发送硬件广播，通知他们必须从主存储器重新提取数据(从而保证系统的一致性)，要么开发人员必须跟踪缓冲区使用情况，并明确清除包含过时数据副本的缓存。这两个问题都很难解决。

Now that the CPU and GPU share access to the same memory, we must decide what tasks to offload and how these should be managed. Shader processors are designed with parallelism in mind, so it is common for software to split computation into independent groups, allowing them to run simultaneously. Groups of work are usually sized to match the SIMD width of each shader core to make full use of the parallelism on offer. Image processing naturally lends itself to GPU acceleration as filter kernels must operate on many pixels simultaneously; these kernels benefit greatly from the texture caching hardware used in graphics, as each image sample may be used by multiple kernels at the same time. However, it is not always possible to dispatch groups of work where each element is independent. It may be necessary to ensure that all elements of a group have completed before beginning the next stage of a program. Synchronisation primitives are provided to handle this very case. A barrier is a point in a program that all elements must reach before execution is allowed to continue. This may be achieved in many ways, but dedicated hardware to handle these cases is becoming increasingly common to reduce overhead of the driver software.

> 现在 CPU 和 GPU 共享对同一内存的访问，我们必须决定卸载哪些任务以及如何管理这些任务。着色器处理器的设计考虑到了并行性，因此软件通常将计算分成独立的组，允许它们同时运行。工作组的大小通常与每个着色器核心的 SIMD 宽度相匹配，以充分利用提供的并行性。图像处理自然有助于 GPU 加速，因为过滤器内核必须同时对多个像素进行操作；这些内核从图形中使用的纹理缓存硬件中受益匪浅，因为每个图像样本可以同时被多个内核使用。然而，在每个元素都独立的情况下，并不总是可以分派工作组。在开始项目的下一阶段之前，可能需要确保组中的所有元素都已完成。提供同步原语来处理这种情况。障碍是程序中所有元素在允许继续执行之前必须达到的点。这可以通过多种方式实现，但处理这些情况的专用硬件正变得越来越常见，以减少驱动程序软件的开销。

---

> [!NOTE]

Allowing the CPU and GPU to share access to memory is only one solution for addressing issues related to limited bandwidth and processing power. Other solutions focus on bypassing bottlenecks. For example, direct memory access (DMA) is a method that allows input/output (I/O) devices to exchange data directly with the main memory, bypassing the CPU, which frees up the CPU for other tasks while streamlining communications between the I/O devices and memory. Another solution enables the GPU to communicate directly a field programmable gate array (FPGA, an integrated circuit that developers can configure) through a PCI Express (PCIe) bus to bypass system memory.

> 允许 CPU 和 GPU 共享对内存的访问只是解决与有限带宽和处理能力有关的问题的一种解决方案。其他解决方案侧重于绕过瓶颈。例如，**直接存储器访问(DMA)是一种方法**，它允许输入/输出(I/O)设备直接与主存储器交换数据，绕过 CPU，从而释放 CPU 用于其他任务，同时简化 I/O 设备和存储器之间的通信。**另一种解决方案使 GPU 能够通过 PCI Express(PCIe)总线直接与现场可编程门阵列(FPGA，一种开发人员可以配置的集成电路)通信，以绕过系统内存。**

### OpenCL

The Open Computing Language (OpenCL) was first released by Apple in 2009 as a vendor-independent framework through which programs could be executed across heterogeneous systems, including CPUs, GPUs, FPGAs, and DSPs. In short, it provides a standard interface for parallel computing. It also defines a four-level memory hierarchy: global memory, read-only memory (writeable by the CPU only), local memory (shared by processing elements) and private memory (per processing element). However, it is not required that each level in the memory hierarchy is implemented in hardware, and shared memory between the CPU and GPU is not explicitly mandated. These relaxations have allowed OpenCL portability between platforms, at the expense of performance guarantees due to the range of permissible implementations. However, such is the popularity of exposing general compute capability that OpenGL ES has introduced the concept of compute shaders in version 3.1 of the API; these now coexist with vertex and fragment shaders in the standard graphics pipeline.

> 开放计算语言(OpenCL)由苹果公司于 2009 年首次发布，作为一个独立于供应商的框架，通过该框架，程序可以跨异构系统执行，包括 CPU、GPU、FPGA 和 DSP。**简而言之，它为并行计算提供了一个标准接口。它还定义了四级内存层次结构：全局内存、只读内存(仅可由 CPU 写入)、本地内存(由处理元件共享)和专用内存(每个处理元件)。**然而，不需要在硬件中实现内存层次结构中的每个级别，CPU 和 GPU 之间的共享内存也没有明确规定。这些放宽允许 OpenCL 在平台之间的可移植性，但由于允许的实现范围，牺牲了性能保证。然而，由于公开通用计算功能的流行，OpenGLES 在 API 3.1 版中引入了计算着色器的概念；这些现在与标准图形管道中的顶点和片段着色器共存。

Although the Raspberry Pi GPU does not natively support OpenCL, it does provide a mechanism for executing general-purpose shaders, known in VideoCore IV as _user shaders._ These are programs written for execution on the QPU, which can be directly issued to the hardware by programming start addresses for the data and instructions to be fetched from memory. User shaders have been used to write a fast-fourier transform (FFT) library for the VideoCore IV V3D, available through the Raspberry Pi website at [`https://www.raspberrypi.org/blog/accelerating-fourier-transforms-using-the-gpu/`](https://www.raspberrypi.org/blog/accelerating-fourier-transforms-using-the-gpu/).

> 尽管树莓派 GPU 不支持 OpenCL，但它确实提供了一种执行通用着色器的机制，在 VideoCore IV 中称为*user 着色器。*这些是为在 QPU 上执行而编写的程序，通过编程从存储器中取出的数据和指令的起始地址，可以直接向硬件发出这些程序。用户着色器已用于为 VideoCore IV V3D 编写快速傅里叶变换(FFT)库，可通过 Raspberry Pi 网站获取，网址为[`https://www.raspberrypi.org/blog/accelerating-fourier-transforms-using-the-gpu/`](https://www.raspberrypi.org/blog/accelerating-fourier-transforms-using-the-gpu/).
