Chapter 10

# 3D Graphics

**HISTORICALLY, THE UNDERSTANDING** of classical computer systems architectures has focused squarely on the interaction between the central processing unit (CPU) and the memory infrastructure. However, a new breed of system is upon us, in which the graphics processing unit (GPU) plays an integral role and is as important as both these key components.

> 从历史上看，对经典计算机系统体系结构的理解完全集中在中央处理单元(CPU)和内存基础架构之间的相互作用上。然而，我们正在出现一种新的系统，其中图形处理单元(GPU)起着不可或缺的作用，并且与这两种关键组成部分一样重要。

As software developers and consumers have demanded increased photorealism from games and more complexity and fluidity from their user interfaces, the requirements of computer graphics have increased. The humble GPU has been catapulted from a simple line-drawing accelerator to a highly parallel, multithreaded subsystem in its own right, with such computing power that it has become integral to modern computer architectures.

> 随着软件开发人员和消费者要求从游戏中提高的光真相以及用户界面的更复杂性和流动性，计算机图形的要求也增加了。不起眼的 GPU 已从简单的线绘制加速器弹射到一个高度平行的多线程子系统本身，具有这样的计算能力，以至于它已成为现代计算机架构不可或缺的一部分。

However, to understand the potential of graphics technology we must focus on its primary purpose and make sense of it in the context of modern 3D graphics.

> 但是，要了解图形技术的潜力，我们必须将重点放在其主要目的上，并在现代 3D 图形的背景下理解它。

## A Brief History of 3D Graphics

Although William Fetter is credited with coining the term `computer graphics` to describe his work on human body animation with Boeing in the early 1960s, the origin of 3D graphics can be traced back to the 1950s and military flight simulators (see Figure 10-1). As early as 1951, the Whirlwind computer at the Massachusetts Institute of Technology (MIT) was being used as a visualisation tool. The Whirlwind computer allowed oscilloscope-style graphics with user input via a device resembling a _light pen_. The Whirlwind was developed as part of the U.S. Navy’s Airplane Stability and Control Analyzer (ASCA) project, and the digital computer provided a programmable flight simulation environment where radar information was used to superimpose an aircraft symbol on top of a set of pre-programmed geographical data points. The result was viewed on a cathode-ray tube (CRT) display. By pointing the light pen at the CRT, the user could query the state of the aircraft, such as its location and speed.

> 尽管威廉·费特特(William Fetter)在 1960 年代初通过波音的 `计算机图形` 一词来描述他在人体动画上的工作，但 3D 图形的起源可以追溯到 1950 年代和军事飞行模拟器(见图 10-1，请参见图 10-1)。早在 1951 年，马萨诸塞州理工学院(MIT)的旋风计算机就被用作可视化工具。旋风计算机允许通过类似于 *light pen* 的设备输入用户输入示波器式图形。旋风是作为美国海军飞机稳定和控制分析仪(ASCA)项目的一部分开发的，数字计算机提供了可编程的飞行模拟环境，其中使用雷达信息将飞机符号叠加在一组预编程的地理位置上数据点。在阴极射线管(CRT)显示屏上查看了结果。通过将轻笔指向 CRT，用户可以查询飞机的状态，例如其位置和速度。

---

> [!NOTE]

A light pen is a photo-sensitive device, like a wand, which can be used to point to or highlight objects on a CRT screen in the same way a finger can be used on a touchscreen device.

> 轻笔是一种对光敏设备，例如魔杖，可用于指向或以相同的方式在 CRT 屏幕上指向或突出对象，就像可以在触摸屏设备上使用手指一样。

Throughout the 1950s and 1960s various parallel streams of research developed the ideas of computer-aided design (CAD) and visualisation. By the mid-1950s, IBM was able to demonstrate the first system capable of displaying vector graphics; the IBM 740 (CRT recorder) was attached to the IBM 701 (data processing system) to record a series of points onto 35-millimetre (mm) photographic film. With variations in exposure, these points could be captured as lines and curves, and with the use of special programming techniques, the 740 could be used to display alphanumeric symbols, graphs and simple shapes. This was fundamental to the advent of computer-aided graphical design, but for a rental price of $2,850 per month it was prohibitively expensive even for commercial use. General Motors had also begun research into CAD with IBM, and this collaboration resulted in the world’s first computer-aided drawing system, the DAC-1, in the early 1960s, which was also capable of scanning in drawings provided by the user.

> 在整个 1950 年代和 1960 年代，各种平行的研究流都开发了计算机辅助设计(CAD)和可视化的思想。到 1950 年代中期，IBM 能够演示第一个能够显示向量图形的系统。IBM 740(CRT 录音机)连接到 IBM 701(数据处理系统)，以将一系列点记录到 35 毫米(MM)摄影膜上。随着曝光的变化，这些点可以作为线条和曲线捕获，并且使用特殊的编程技术，740 可用于显示字母数字符号，图形和简单形状。这对于计算机辅助图形设计的出现至关重要，但是以每月 2,850 美元的租金价格，即使用于商业用途，价格昂贵。通用汽车还开始使用 IBM 研究 CAD，这项合作导致了世界上第一个计算机辅助绘图系统 DAC-1，1960 年代初期，该系统也能够在用户提供的图纸中扫描。

---

> [!NOTE]

Vector graphics involve using _geometrical primitives_ (simple graphical building blocks) based on mathematical expressions to represent graphical images.

> 向量图形涉及基于数学表达式来表示图形图像，使用_地球图原始图(简单的图形构建块)。

![[FIGURE 10-1:](#13_9781119183938-ch10.xhtml#rc10-fig-0001) A summary timeline of the evolution of computer graphics](./media/images/9781119183938-fg1001.png)

### The Graphical User Interface (GUI)

In 1963, Ivan Sutherland, a PhD student at MIT, presented a thesis entitled `Sketchpad: A Man-Machine Graphical Communication System` , which consolidated much of the research of the late 1950s and introduced the first graphical user interface (GUI). Using MIT’s TX-2 computer equipped with the man-machine graphic communication system, a user could draw lines and curves directly onto a point plotter display using a light pen. In addition to this being the first complete GUI for a computer, it also allowed the user to constrain the geometric properties of the shapes on the screen, such as line lengths and the angles between them. Sutherland is widely regarded as a founding father of object-oriented programming (OOP) and modern day GUIs. In the mid-1960s he began research into `remote reality` in the quest to replace camera images with computer-generated scenes; these were nothing more than wireframe models, but Sutherland’s work was pioneering in the field of virtual reality and, together with Dr David Evans, he created a company to market these vector systems using custom hardware and software.

> 1963 年，麻省理工学院的博士生伊万·萨瑟兰(Ivan Sutherland)介绍了一篇名为 ` Sketchpad：人造图形通信系统` 的论文，该论文巩固了 1950 年代后期的许多研究，并引入了第一个图形用户界面(GUI)。使用 MIT 的 TX-2 计算机配备了 Man-Machine 图形通信系统，用户可以使用轻笔直接将线条和曲线直接绘制到点绘图仪显示器上。除了这是计算机的第一个完整 GUI 外，它还允许用户约束屏幕上形状的几何特性，例如线长度和它们之间的角度。萨瑟兰(Sutherland)被广泛认为是面向对象的编程(OOP)和现代 Guis 的创始父亲。在 1960 年代中期，他开始研究 `远程现实` ，以寻求用计算机生成的场景代替相机图像。这些不过是线框模型，但是萨瑟兰的作品在虚拟现实领域开创了开创性，他与戴维·埃文斯(David Evans)博士一起创建了一家公司，使用自定义硬件和软件来营销这些向量系统。

During the late 1960s and 1970s, computer graphics technology was being applied in various fields. For example, in medical imaging, X-ray images were captured digitally and processed on computers before being displayed. NASA also commissioned General Electric to develop a real-time colour raster graphics system as part of a monitor to train astronauts. (See the nearby sidebar for an explanation of raster graphics.) However, the cost of these systems, though falling, meant that computer graphics were limited to military and well-funded commercial applications. It wasn’t until the advent of personal computing that this technology became of interest to everyone, and the result was the inevitable flurry of activity in the industry as companies sought to take control of a potentially lucrative market.

> 在 1960 年代后期和 1970 年代后期，计算机图形技术正在各个领域应用。例如，在医学成像中，X 射线图像被数字捕获并在显示之前在计算机上处理。NASA 还委托通用电气开发一个实时色彩栅格图形系统，作为训练宇航员的监视器的一部分。(有关栅格图形的说明，请参见附近的侧边栏。)但是，这些系统的成本虽然下降，这意味着计算机图形仅限于军事和资金充足的商业应用。直到个人计算的出现，这项技术就引起了所有人的关注，结果是该行业不可避免地会浪费活动，因为公司试图控制一个潜在的利润丰厚的市场。
