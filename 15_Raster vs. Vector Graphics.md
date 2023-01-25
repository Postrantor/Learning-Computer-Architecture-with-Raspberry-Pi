# Raster vs. Vector Graphics

All modern displays are a matrix of luminescent pixels with each pixel being a coloured dot or point at a particular screen location. Two different methods are used to describe how the dots are arranged on the screen to form an image. Images formed by these two methods are referred to as either raster graphics or vector graphics.

> 所有现代显示器都是发光像素的矩阵，每个像素是一个彩色点或在特定屏幕位置的点。使用两种不同的方法来描述如何在屏幕上排列点以形成图像。由这两种方法形成的图像称为栅格图形或向量图形。

_Raster graphics_ are images with these characteristics:

- They are stored as an array of pixels, each of which is assigned a red-green-blue (RGB) colour value and (optionally) a transparency value.
- They are generally simpler to conceptualise than vector graphics because the pixels are arranged in a dot matrix (a grid), sort of like colouring in squares on graph paper. However, large images require storage of much more data because instructions are required to specify the position and colour of each individual pixel.
- They have _resolution_ typically determined by the number of dots per inch (dpi). Making the image larger decreases its quality and may result in the image looking blurry, as shown in Figure 10-2.
- They are generally used for photographs and other images that require _continuous tone_: smoothly merging colours and shades as opposed to sharply outlined shapes.

>

- 它们被存储为像素数组，每个像素都分配了红色绿色(RGB)颜色值和((可选))透明度值。
- 它们通常比矢量图形更简单，因为像素是在点矩阵(网格)中排列的，有点像在图形纸上的正方形中的颜色。但是，大图需要存储更多数据，因为需要指定说明来指定每个单独像素的位置和颜色。
- 它们的 _Resolution_ 通常由每英寸点数(DPI)确定。如图 10-2 所示，使图像更大会降低其质量，并可能导致图像看起来模糊。- 通常用于照片和其他需要_连续色调的图像：平稳地合并颜色和阴影，而不是形状鲜明的形状。

_Vector graphics_ are images with these characteristics:

- They are stored as a collection of mathematically defined points, lines, curves, and fills.
- They generally result in smaller files, because the mathematical formulas describe points, paths and fills instead of having to define the location and colour of each and every pixel.
- They can be made larger without any loss of quality, as shown in [Figure 10-2](#13_9781119183938-ch10.xhtml#c10-fig-0002).
- They are the preferred format for fonts, logos and illustrations that require smooth, well-defined edges and flat colours.

>

- 它们被存储为数学定义的点，线，曲线和填充的集合。
- 它们通常会导致较小的文件，因为数学公式描述了点，路径和填充，而不必定义每个像素的位置和颜色。
- 可以使它们更大，而不会损失任何质量，如[图 10-2](%EF%BC%8313_9781119183938-CH10.XHTML%EF%BC%83C10-FIG-0002)。
- 它们是字体，徽标和插图的首选格式，需要光滑，定义明确的边缘和扁平颜色。

![[FIGURE 10-2:](#13_9781119183938-ch10.xhtml#rc10-fig-0002) Magnified vector (left) and raster (right) graphics images](./media/images/9781119183938-fg1002.png)

### 3D Graphics in Video Games

Alongside the research into computer graphics in the early 1950s, academics also began experimenting with games as part of their computer science and artificial intelligence research. The first computer game credited with a graphical output was _OXO_ in 1952. This was a noughts and crosses puzzle where the players used a rotary telephone controller to determine in which square to place their next move. In this game, which was developed by Alexander Douglas in Cambridge, the user played against the computer, and the noughts and crosses board was displayed on a simple CRT display.

> 除了 1950 年代初期对计算机图形技术的研究外，学者们还开始尝试游戏，作为其计算机科学和人工智能研究的一部分。第一个以图形输出归功于 _oxo_ 的电脑游戏在 1952 年。这是一个荒谬的拼图，玩家使用旋转电话控制器来确定在哪个正方形上放置下一步。在这款游戏中是由剑桥的亚历山大·道格拉斯(Alexander Douglas)开发的，用户对付了计算机，而 `Noughts and Crosses板` 在简单的 CRT 显示屏上显示。

Another early computer game with graphical output was _Tennis for Two_. Developed by William Higinbotham to alleviate the boredom of visitors to Brookhaven National Laboratory, the game allowed two people to play against each other. A side view of a tennis court was displayed on an oscilloscope and each user could deflect a moving ball to each other using their own controller, with a knob for navigation and a button-press to hit the ball. The circuit would correctly model the trajectory of the ball on hitting the edge of the screen or net, and simulate drag as the ball moved through the air. The game was popular with the public, but after two seasons was dismantled to allow the hardware to be reused for other projects. As with many of these early examples, interest and resources focused very much on research rather than the opportunity to commercialise these games.

> 另一个具有图形输出的早期计算机游戏是 _tennis 的两个_。威廉·希金博坦(William Higinbotham)开发的，以减轻布鲁克黑文国家实验室的游客无聊，这场比赛使两个人互相对抗。网球场的侧视图显示在示波器上，每个用户都可以使用自己的控制器将移动的球偏向彼此，并带有旋钮进行导航和纽扣式击球以击球。该电路将在撞击屏幕或网的边缘时正确对球的轨迹进行正确建模，并在球中移动空气时模拟阻力。该游戏在公众中很受欢迎，但是在两个赛季被拆除后，可以将硬件重新用于其他项目。与许多早期示例一样，兴趣和资源非常关注研究，而不是将这些游戏商业化的机会。

Perhaps the first game to achieve widespread distribution was _Spacewar!_ Developed as a hack by Steve Russell and a group of friends at MIT, and inspired by the visual potential of the high-quality vector display of Digital Equipment Corporation’s (DEC’s) PDP-1, this two-player game involved user-controlled spaceships that could fire missiles at each other whilst manoeuvring around the gravitational well of a central sun. By the end of the 1960s, most U.S. university computer labs possessed a copy of the game, as DEC decided to distribute it as test software with every PDP-1. However, the huge $120,000 price tag meant that only 50 PDP-1s were ever made, thus limiting the game’s commercial viability despite its huge popularity.

> 也许第一个获得广泛发行的游戏是*spacewar！*史蒂夫·罗素(Steve Russell)和麻省理工学院(MIT)的一群朋友开发，并受到数字设备公司(DEC)PDP-1 的高质量矢量显示的视觉潜力的启发。，这款两人游戏涉及用户控制的飞船，可以在中央太阳的重力井周围互相发射导弹。到 1960 年代末，大多数美国大学计算机实验室都拥有游戏的副本，因为 DEC 决定使用每个 PDP-1 将其作为测试软件分发。但是，巨额 $ 120,000 的价格意味着有史以来只有 50 个 PDP-1，因此尽管它的知名度很高，但仍限制了游戏的商业生存能力。

As computer hardware became cheaper, the coin-operated game market could seriously consider introducing video gaming to the general public. In the early 1970s, arcade-game developers pioneered rich visual displays and electronic sound effects in an attempt to capture the imagination of the masses. Two engineers, Nolan Bushnell and Ted Dabney, introduced _Computer Space,_ a derivative of _Spacewar!,_ to the coin-operated arcades of California, but this ended up being too costly and too complex to succeed. However, after forming Atari Inc. together in 1972, Bushnell and Dabney created _Pong_. Similar to table tennis, _Pong_ was a two-player bat and ball game where each player attempted to direct a moving ball past their opponent on the other side of a net. Derived from a simple game provided with the Magnavox Odyssey, the world’s first home console, they decided to manufacture this for public distribution, and with 19,000 units sold it became the first arcade game to achieve commercial success. Arcades flourished throughout the 1970s and early 1980s, helping to fuel the growing popularity of video gaming and with it the promise of a bright future for computer graphics.

> 随着计算机硬件变得更便宜，投币游戏市场可以认真考虑向公众介绍视频游戏。在 70 年代初期，街机游戏开发商开创了丰富的视觉显示和电子音效，试图抓住大众的想象力。两位工程师，Nolan Bushnell 和 Ted Dabney，将 _Computer Space _ _Spacewar! 的衍生产品 _ 引入了加利福尼亚的投币式拱廊，但最终成本太高且太复杂而无法成功。然而，在 1972 年共同成立 Atari Inc. 后，布什内尔和达布尼创建了 *Pong*。与乒乓球类似，_Pong_ 是一种双人击球和球类游戏，每个玩家都试图将移动的球引导到网另一侧的对手身边。源自世界上第一款家用游戏机 Magnavox Odyssey 提供的简单游戏，他们决定制造这款游戏用于公开发行，并以 19,000 件的销量成为第一个取得商业成功的街机游戏。街机在整个 1970 年代和 1980 年代初期蓬勃发展，有助于推动视频游戏的日益普及，并为计算机图形学带来光明的前景。

### Personal Computing and the Graphics Card

During the early 1970s, distributed video games were manufactured as single-purpose devices, designed and manufactured solely to play a single game. The problem with this approach was that consumers had to purchase a new device each time they wanted to play a new game. (_Pong_ was such a game.) By the mid-1970s manufacturers had a solution for this problem—the microprocessor. Games could be run on general-purpose computing hardware; each game was essentially a new set of instructions to be run by the microprocessor in the system and could be sold separately from the gaming unit. The first console of this kind was the Video Entertainment System (VES) released by Fairchild in 1976. Games were released as cartridges containing read-only-memory (ROM) and could be swapped and plugged into the VES console to form an equivalent electrical circuit to that previously built from discrete components. Although game design and translation to ROM code were very much specialist skills, the microprocessor, and therefore the computer, became the next gaming platform.

> 在 20 世纪 70 年代初期，分布式视频游戏被制造为单一用途的设备，专为玩一款游戏而设计和制造。这种方法的问题在于，消费者每次想玩新游戏时都必须购买新设备。(_Pong_ 就是这样一种游戏。)到 20 世纪 70 年代中期，制造商有了解决这个问题的方法——微处理器。游戏可以在通用计算硬件上运行；每个游戏本质上都是一组新的指令，由系统中的微处理器运行，可以与游戏单元分开出售。第一个此类控制台是 Fairchild 于 1976 年发布的视频娱乐系统 (VES)。到以前由分立元件构建的。尽管游戏设计和 ROM 代码的翻译是非常专业的技能，但微处理器和计算机成为了下一个游戏平台。

From the late 1970s onward, 3D graphics developed at a rapid pace, fuelled by users’ desire for more immersive experiences and more complex geometries to be modelled and animated in life-like ways. Many industries contributed to this dramatic and rapid advancement. For the purposes of this brief history, we’re focusing on the development of hardware for the personal computer.

> 从 20 世纪 70 年代后期开始，3D 图形发展迅速，用户渴望获得更身临其境的体验和更复杂的几何形状，以便以逼真的方式建模和制作动画。许多行业都为这一巨大而迅速的进步做出了贡献。出于本简史的目的，我们将重点放在个人计算机硬件的开发上。
