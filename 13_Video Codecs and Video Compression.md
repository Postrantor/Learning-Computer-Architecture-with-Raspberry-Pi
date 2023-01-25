Chapter 9

> [!NOTE]
> 这一章主要讲了视频的编码技术，是围绕视频来讲的
> 下面一章节时围绕显示技术来展开的，及 GPU

# Video Codecs and Video Compression

**A VIDEO IS** a sequence of images that are shown one after the other. In principle, you could store them as a digital flip-book, with a picture for each frame. Without compression, roughly 3 bytes per pixel (one to store each of the red, green and blue colour components) are required to avoid introducing perceptible _quantisation artefacts_ (visible steps in brightness or colour). If you wanted to store video even at a relatively low resolution (640 × 480 pixels) at 25 frames a second, each second would then take up 3 \* 640 \* 480 \* 25 bytes, which works out to just more than 23 megabytes (MB) per second. A two-hour film would take up more than 165 gigabytes (GB), which is equivalent to 10 double-sided, double-layer DVDs. Applying a generic lossless compression algorithm such as ZIP might make it a little smaller, but you’d still need several of these disks.

> **视频是**一系列依次显示的图像。原则上，你可以将它们存储为一本数字翻书，每一帧都有一张图片。如果没有压缩，每个像素大约需要 3 个字节(一个字节用于存储红色、绿色和蓝色分量)，以避免引入可感知的量化伪影(亮度或颜色的可见步长)。如果您想以每秒 25 帧的速度以相对较低的分辨率(640×480 像素)存储视频，那么每秒将占用 3\*640\*480\*25 字节，这相当于每秒仅超过 23 兆字节(MB)。一部两小时的电影将占用超过 165 GB 的空间，相当于 10 张双面双层 DVD。应用一种通用的无损压缩算法(如 ZIP)可能会使其变小一些，但您仍然需要几个这样的磁盘。

Storing footage as just described would basically make almost any form of digital video distribution completely impractical. Changing the side of a DVD every six minutes would be annoying, and downloading a TV show would take days. YouTube would only work for clips a few seconds long. Video chat would require either an image too small to be useful or the fastest Internet connection available.

> 存储刚刚描述的视频基本上会使几乎任何形式的数字视频分发完全不切实际。每六分钟换一次 DVD 的边会很烦人，下载一个电视节目需要几天的时间。YouTube 只能播放几秒钟长的视频片段。视频聊天可能需要图像太小而无法使用，或者需要最快的 Internet 连接。

In order to make digital video distribution possible, it’s essential to find ways to make the videos much smaller. This shrinking of files is known as compression. There are two basic types of compression: lossless and lossy. In _lossless_ compression, the file is shrunk in such a way that it’s possible to recreate the original file perfectly from the compressed file, down to the level of individual bits. This is how file formats such as `.zip`</code> or `tar.gz` work. However, there’s a limit to how small you can make a file with lossless compression, and lossless compression on its own generally isn’t sufficient for most video applications.

> 为了使数字视频分发成为可能，必须找到使视频更小的方法。这种**文件的收缩称为压缩。压缩有两种基本类型：无损和有损**。在 *lossless* 压缩中，文件以这样的方式收缩，即可以从压缩的文件完美地重建原始文件，直到单个位的级别。这就是 `.zip` </code>或 `tar.gz` 等文件格式的工作原理。然而，使用无损压缩制作文件的大小是有限制的，而且无损压缩本身通常不足以满足大多数视频应用程序的需要。

In contrast with lossless compression, _lossy_ compression makes a file smaller by removing some of the information. After lossy compression, it is no longer possible to recreate the original file perfectly from the compressed file. As a trivial example of lossy video compression, imagine simply halving the horizontal and vertical resolution of each image in the video stream. The resulting video file would shrink by a factor of four, at the cost of a significant reduction in visual fidelity. The art of designing lossy video compression algorithms and encoder implementations lies in keeping the perceived quality of the decoded stream as high as possible while making the file as small as possible.

> 与无损压缩相比，*lossy* 压缩通过删除一些信息使文件变小。有损压缩后，再也无法从压缩文件中完美地重建原始文件。作为有损视频压缩的一个简单示例，想象一下将视频流中每个图像的水平和垂直分辨率减半。生成的视频文件将缩小四倍，代价是视觉逼真度显著降低。设计有损视频压缩算法和编码器实现的艺术在于保持解码流的感知质量尽可能高，同时使文件尽可能小。

Most video encoders use both lossless and lossy compression techniques to get the files as small as possible.

> 大多数视频编码器都使用无损和有损压缩技术来获得尽可能小的文件。

## The First Video Codecs

The International Telecommunication Union (ITU) developed the first widely used video compression standard (known as H.261) to enable video calls over Integrated Services Digital Network (ISDN) lines in 1988. In comparison to more modern standards, H.261 delivered relatively poor image quality for a given bit rate, but it is notable for having laid the technical foundations for future video compression standards. Compression standards are often known informally as codecs, a mash-up of *co*der-*dec*oder. More formally, the term codec refers to an implementation of a standard in software, hardware or a combination of the two.

> 1988 年，国际电信联盟(ITU)开发了第一个广泛使用的视频压缩标准(称为 H.261)，以支持通过综合业务数字网(ISDN)线路进行视频呼叫。与更现代的标准相比，对于给定的比特率，H.261 提供了相对较差的图像质量，但值得注意的是，它为未来的视频压缩标准奠定了技术基础。压缩标准通常被非正式地称为编解码器，是 *co*der-*dec*oder 的混合体。更正式地说，术语编解码器是指软件、硬件或两者的组合中的标准实现。

The Moving Picture Experts Group (MPEG) was formed in 1988 by the International Organization for Standardization (ISO) and International Electrotechnical Commission (IEC) to take this foundation and build it up to support higher video quality than was possible over ISDN lines. Both the ITU and MPEG continue to develop codecs, often in collaboration with one another. Since 2001 much of this work has been done under the auspices of the Joint Video Team (JVT), which was responsible for the successful H.264/MPEG-4 AVC codec. The MPEG series of standards includes more than just video. It includes the file structure, audio and other parts needed to make a fully functional video file.

> 1988 年，国际标准化组织(ISO)和国际电工委员会(IEC)成立了运动图像专家组(MPEG)，以建立这一基础，支持比 ISDN 线路更高的视频质量。ITU 和 MPEG 都在继续开发编解码器，经常是相互合作。自 2001 年以来，这项工作大部分是在联合视频团队(JVT)的主持下完成的，该团队负责成功的 H.264/MPEG-4AVC 编解码器。MPEG 系列标准不仅仅包括视频。它包括文件结构、音频和制作完整功能视频文件所需的其他部分。

The first standard developed by MPEG (known as MPEG-1) was released in 1993. There are two ways the designers of MPEG-1 sought to minimise file size while maximising image quality:

> MPEG 开发的第一个标准(称为 MPEG-1)于 1993 年发布。MPEG-1 的设计者有两种方法来最小化文件大小，同时最大化图像质量：

- Preferentially removing information that humans find hard to perceive (exploiting the eye) - Exploiting the sort of information that videos hold (exploiting the data)

> -优先删除人类难以感知的信息(利用眼睛)-利用视频中的信息(使用数据)

### Exploiting the Eye

Our eyes possess two types of receptors that detect light: rods that detect brightness and cones that detect colour. Rods are more sensitive than cones, which is why we lose the ability to see colours when it gets dark, although we can still make out shapes. We also have about 20 times as many rods as cones. This means that we’re far better at making out fine variations in brightness than in colour. It’s a little quirk of human physiology that can be exploited when compressing video since there’s no point in storing information that the eye can’t see.

> 我们的眼睛有两种检测光的受体：检测亮度的杆和检测颜色的锥体。杆比锥体更敏感，这就是为什么我们在天黑时失去了看到颜色的能力，尽管我们仍然可以辨认形状。我们还有大约 20 倍于圆锥体的杆。这意味着我们比颜色更善于分辨亮度的细微变化。这是人类生理学的一个小怪癖，**可以在压缩视频时加以利用，因为存储眼睛看不见的信息是没有意义的**。

To treat brightness and colour differently in a codec, it is helpful first to transform the image from the RGB colorspace, where each pixel is represented by a red, a green and a blue value, to the so-called Y’C<sub>b</sub>C<sub>r</sub> colorspace, where each pixel is represented by a _luma_ (brightness) value Y’ and two _chroma_ (colour) values C<sub>b</sub> and C<sub>r</sub>. Luma corresponds to perceived brightness and is computed as a weighted sum of the original red, green and blue values. There are several slightly different YC<sub>b</sub>C<sub>r</sub> colorspaces, which are used for different applications. The weights and sums for the commonly used ITU-R BT.601standard are:

> 为了在编解码器中区别对待亮度和颜色，首先将图像从 RGB 颜色空间转换为所谓的 Y'C<sub>b</sub>C<sub>r</sub>颜色空间，其中每个像素由一个 *luma*(亮度)值 Y'和两个 *chroma*(颜色)值 C<sub>b</sub>和 C<sub>r</sub>表示，这很有帮助。亮度对应于感知亮度，并作为原始红、绿和蓝值的加权和计算。有几个稍微不同的 YC<sub>b</sub>C<sub>r</sub>颜色空间，用于不同的应用。常用 ITU-R BT.601 标准的权重和总和为：

Y’ = 0.257R + 0.504G + 0.098B +16

> Y’=0.257R+0.504G+0.098B+16

Cr = 0.439R – 0.368G – 0.071B + 128

> 铬=0.439R–0.368G–0.071B+128

Cb = -0.148R – 0.219G + 0.439B + 128

> Cb=-0.148R–0.219G+0.439B+128

If we visualise the 24-bit RGB colorspace as a cube, increasing luma moves us roughly along a leading diagonal from black (0,0,0) to white (255,255,255), through 254 shades of grey. The chroma values represent movement away from the diagonal: roughly speaking, C<sub>b</sub> and C<sub>r</sub> represent how much of a blue or red tint the colour has, respectively.

> 如果我们将 24 位 RGB 颜色空间视为立方体，则亮度的增加会使我们大致沿着从黑色(0,0,0)到白色(255255255)的前导对角线移动 254 个灰度。色度值表示远离对角线的移动：粗略地说，C<sub>b</sub>和 C<sub>r</sub>分别表示颜色具有多少蓝色或红色色调。

Changing the colorspace like this doesn’t make the image any smaller (each pixel is still represented by three numbers, and each number requires roughly the same number of bits of precision as before), but it splits up the brightness from the colour. In effect, there are three independent images, or _channels_: one of brightness, one of `redness` and one of `blueness` . The individual pixel values that make up a channel are referred to as _samples_. These are displayed together, but they can be stored in different ways. Because we have so many more rods, which are for seeing detail, it doesn’t matter if the colour values are at a lower resolution. The first, and simplest, stage of MPEG-1 compression is chroma subsampling. This leaves the luma channel at full resolution, but halves the horizontal and vertical resolution of both chroma channels, shrinking the space they occupy by a factor of four (see Figures 9-1, 9-2 and 9-3). The overall space occupied by the image is thus halved (because 1 + ¼ + ¼ = ½ × 3) at no cost in visual quality. Not bad for a first step!

> 这样改变颜色空间并不会使图像变小(每个像素仍然由三个数字表示，每个数字所需的精度位数与之前大致相同)，但它将亮度与颜色分开。实际上，有三个独立的图像，即通道：一个是亮度，一个是 `红色` ，一个 `蓝色` 。组成通道的各个像素值称为 *samples*。这些显示在一起，但可以以不同的方式存储。因为我们有更多的杆，用于查看细节，所以颜色值是否处于较低的分辨率并不重要。MPEG-1 压缩的第一个也是最简单的阶段是色度子采样。这将使亮度通道保持全分辨率，但将两个色度通道的水平和垂直分辨率减半，从而将它们占用的空间缩小四倍(见图 9-1、9-2 和 9-3)。因此，图像所占的总空间减半(因为 1+¼+¼=½×3)，视觉质量不受影响。第一步还不错！

![[FIGURE 9-1:](#12_9781119183938-ch09.xhtml#rc09-fig-0001) The luma channel of the image](./media/images/9781119183938-fg0901.png)

![[FIGURE 9-2:](#12_9781119183938-ch09.xhtml#rc09-fig-0002) The chroma red channel of the image](./media/images/9781119183938-fg0902.png)

![[FIGURE 9-3:](#12_9781119183938-ch09.xhtml#rc09-fig-0003) The chroma blue channel of the image](./media/images/9781119183938-fg0903.png)

### Exploiting the Data

The second technique that video compression can use is to make assumptions about the properties of the content being transmitted. Typically, each image in a video isn’t completely different to those before and after it. If it was, the screen would just display different unrelated images in quick succession, and you wouldn’t be able to make much sense of what is happening. Instead, most frames are very similar to the ones before and after it. Perhaps most of the background is the same with just a few static or slowly changing objects moving around, or perhaps the whole frame moves as the camera pans. Either way, this means that most of the information is already available in a preceding frame. Sometimes the whole image changes as the video cuts to a new scene, but this is infrequent considering there may be between 24 and 60 frames per second.

> 视频压缩可以使用的第二种技术是对正在传输的内容的属性进行假设。通常情况下，视频中的每一幅图像与它之前和之后的图像并不完全不同。如果是这样，屏幕将快速连续显示不同的不相关图像，你将无法理解正在发生的事情。相反，大多数帧与它之前和之后的帧非常相似。也许大多数背景都是相同的，只有一些静止或缓慢变化的物体在移动，或者也许整个帧随着相机的平移而移动。无论哪种方式，这意味着大多数信息在前一帧中已经可用。有时，当视频切换到新场景时，整个图像会发生变化，但考虑到每秒可能有 24 到 60 帧，这种情况并不常见。

To take advantage of this feature of video data, an MPEG-1 encoder splits the sequence of frames into I frames, P frames and B frames.

> 为了利用视频数据的这一特性，MPEG-1 编码器将帧序列分成 I 帧、P 帧和 B 帧。

#### I Frames

Intra-frames, or I frames, are stored in a way that allows them to be decoded by themselves, without reference to any other frame in the video. From a technical perspective, I frames are encoded in a very similar way to the JPEG format for storing still images; the compression techniques you’ll see used on I frames work in much the same way to keep photographs small.

> 帧内帧或 I 帧以允许它们自己解码的方式存储，而不参考视频中的任何其他帧。从技术角度来看，I 帧的编码方式与 JPEG 格式非常相似，用于存储静止图像；你会看到在 I 帧上使用的压缩技术在很大程度上与保持照片小的方式相同。

The first stage is to split each channel (Y’, C<sub>b</sub> and C<sub>r</sub>) of the I-frame image into 8×8 sample blocks. Because the chroma channels have already been subsampled, a single 8×8 block in the chroma channel corresponds to four adjacent 8×8 blocks in the luma channel. This collection of six blocks (one C<sub>b</sub>, one C<sub>r</sub> and four Y’) is known as a macroblock. We’ll look at how these macroblocks are used later on, but first let’s take a look at the other types of frame.

> 第一阶段是将 I 帧图像的每个通道(Y'、C<sub>b</sub>和 C<sub>r</sub>)分割成 8×8 个样本块。因为色度通道已经被二次采样，所以色度通道中的单个 8×8 块对应于亮度通道中的四个相邻的 8×8 个块。这六个块(一个 C<sub>b</sub>、一个 C<sub>r</sub>和四个 Y')的集合称为宏块。稍后我们将讨论如何使用这些宏块，但首先让我们看看其他类型的帧。

#### P Frames

Predicted frames, or P frames, depend on image data from the preceding I or P frame. They don’t describe the whole image, just the bits that have changed. As such, they can’t be decoded without the preceding I or P frame being decoded first. The P frames are divided into macroblocks in exactly the same way as I frames.

> 预测帧或 P 帧取决于来自先前 I 或 P 帧的图像数据。他们没有描述整个图像，只是描述了发生变化的部分。因此，如果前面的 I 或 P 帧没有被首先解码，它们就不能被解码。P 帧以与 I 帧完全相同的方式被划分为宏块。

As previously mentioned, a large portion of each image will probably be the same as in the previous image, just moved slightly. When encoding a P frame, the encoder looks at each macroblock in the image in turn and tries to find similar macroblock-sized areas in the preceding frame; this procedure is known as _motion search_. If the encoder finds a similar area, it doesn’t encode the new macroblock from scratch; instead it encodes a motion vector indicating where in the previous frame the match has been found. A macroblock encoded in this way is known as a P macroblock; when the decoder comes to decode a P macroblock it decodes the motion vector and copies the appropriate area of the preceding frame. If the encoder fails to find a sufficiently similar macroblock in the previous frame, it stores the macroblock in exactly the same way that macroblocks are stored in I frames. A macroblock encoded in this way is known as an I macroblock.

> 如前所述，每个图像的大部分可能与前一图像中的相同，只是稍微移动了一下。当对 P 帧进行编码时，编码器依次查看图像中的每个宏块，并尝试在前一帧中找到类似宏块大小的区域；这个过程称为动作搜索。如果编码器发现类似的区域，它不会从头开始编码新的宏块；相反，它对指示在前一帧中的何处找到匹配的运动向量进行编码。以这种方式编码的宏块被称为 P 宏块；当解码器开始解码 P 宏块时，它解码运动向量并复制前一帧的适当区域。如果编码器未能在前一帧中找到足够相似的宏块，则它以与宏块存储在 I 帧中完全相同的方式存储宏块。以这种方式编码的宏块称为 I 宏块。

Even if motion search has identified a good candidate for prediction, it’s likely that there will still be some small differences between the current frame and the corresponding section of the preceding frame. For example, a macroblock may contain a bird flying across the screen. As it flies, it also changes shape as its wings flap. This difference is known as the _prediction error_ or _residual_. The encoder may choose to encode the residual using the same techniques that it would use for I macroblock image data and store the encoded residual along with the motion vector; when the decoder comes to decode the macroblock, it decodes the residual and combines it with the image data copied from the preceding frame.

> 即使运动搜索已经确定了一个很好的预测候选，当前帧和前一帧的相应部分之间仍可能存在一些小的差异。例如，宏块可能包含飞过屏幕的鸟。当它飞行时，它也会随着翅膀的摆动而改变形状。这种差异称为*预测错误*或* sidual*。编码器可以选择使用它将用于 I 宏块图像数据的相同技术来编码残差，并将编码的残差与运动向量一起存储；当解码器开始解码宏块时，它解码残差并将其与从前一帧复制的图像数据相结合。

The smaller the residual, the less information there is to store, and therefore the smaller the file size. In order to capture movement as accurately as possible, MPEG-1 motion vectors can be specified down to the half-pixel (also called half-pel) level in both _x_ and _y_ directions. If it decodes a half-pel motion vector for a macroblock, the decoder must do more than just copy pixels from the previous frame: it must also have a scheme for generating the `missing` pixel values that lie halfway between the real pixel values. This process is called interpolation. If you visualize a single line of pixels, in a single channel, you’ll have a single sample for each pixel. These could be plotted on a graph to show how the sample value changes along the line of pixels. The easiest interpolation scheme, used by MPEG-1, is to draw a straight line between the two points and plot the middle point on this line (mathematically, we take the average of the two adjacent samples); this is known as linear interpolation.

> 剩余量越小，存储的信息就越少，因此文件大小就越小。为了尽可能准确地捕捉运动，MPEG-1 运动矢量可以在 *x* 和 *y* 方向上指定到半像素(也称为半像素)级别。如果它解码宏块的半像素运动矢量，解码器必须做的不仅仅是从上一帧复制像素：它还必须有一个方案来生成位于实际像素值中间的 `缺失` 像素值。此过程称为插值。如果在单个通道中可视化一行像素，则每个像素都有一个样本。这些可以绘制在图形上，以显示样本值如何沿像素线变化。MPEG-1 使用的最简单的插值方案是在两个点之间画一条直线，并在这条线上画出中间点(数学上，我们取两个相邻样本的平均值)；这被称为线性插值。

Of course, in a 2D picture, we need to do this vertically as well as horizontally. Motion vectors that have integer _x_ or _y_ components (for example (1, ½) or (3½, 2)) are straightforward, as they require linear interpolation in one direction only. Motion vectors that have half-pel _x_ and _y_ components (for example (2½, ½)) require us to average four adjacent samples in the source image. This is known as bilinear interpolation. See Figure 9-4 for details.

> 当然，在 2D 图片中，我们需要垂直地和水平地进行此操作。具有整数 *x* 或 *y* 分量(例如(1，½)或(3½，2))的运动矢量是直接的，因为它们只需要在一个方向上进行线性插值。具有半像素 *x* 和 *y* 分量(例如(2½，½))的运动矢量要求我们对源图像中的四个相邻样本进行平均。这称为双线性插值。详见图 9-4。

![[FIGURE 9-4:](#12_9781119183938-ch09.xhtml#rc09-fig-0004) The location of the full pixels (squares) and the half-pixel values (crosses) on a 2×1 grid. Later video standards also use quarter-pixel values (circles).](./media/images/9781119183938-fg0904.png)

This encoding of movement is obvious if you’ve ever seen a corrupted MPEG video. Parts of the frame still move around, but because the preceding frame is wrong, the images that are moving are incorrect.

> 如果你看过损坏的 MPEG 视频，这种运动编码是显而易见的。部分帧仍在移动，但由于前一帧错误，因此移动的图像不正确。

#### B Frames

Bi-directional frames, or B frames, are much like P frames except that they can contain elements from the preceding I or P frame and the subsequent I or P frame;

> 双向帧或 B 帧与 P 帧非常相似，不同之处在于它们可以包含前一个 I 或 P 帧和后一个 I 帧或 P 帧的元素；

> [!NOTE]
> that no frame is ever predicted off a B frame.

Each macroblock in a B frame can be predicted off areas in one or both of these frames. If it’s predicted off both, then the encoder must store two motion vectors, and the decoder computes a weighted average of the two areas before combining it with the residual (if any).

> B 帧中的每个宏块可以在这些帧中的一个或两个帧中的区域之外进行预测。如果这两个都是预测的，那么编码器必须存储两个运动向量，解码器在将其与残差(如果有)组合之前计算两个区域的加权平均值。

If the video stream has a large number of B frames in a row, one of the reference frames could be quite a way ahead. This could create a problem for the decoder because it would have to read forward all the way to the reference frame and decode that before coming back to decode the B frame. In order to simplify this problem, the encoder doesn’t write frames to the file in the order they appear on the screen, but so that the reference frames are always before the frames that are predicted off them. Table 9-1 shows an example video stream.

> 如果视频流在一行中有大量的 B 帧，那么其中一个参考帧可能会遥遥领先。这可能会给解码器带来问题，因为它必须一直向前读取参考帧，并在返回解码 B 帧之前对其进行解码。为了简化这个问题，编码器不会按照帧在屏幕上出现的顺序将帧写入文件，而是使参考帧总是在预测帧之前。表 9-1 显示了示例视频流。

<figure> <figcaption>

[Table 9-1](#12_9781119183938-ch09.xhtml#rc09-tbl-0001)  Example Group of Pictures with Frame Types

> [表 9-1](#12_9781119183938-ch09.xhtml#rc09-tbl-0001)  带有框架类型的图片组示例

</figcaption>

-------------- --- --- --- --- --- --- --- Frame number 1 2 3 4 5 6 7 Frame type I B B P B B I -------------- --- --- --- --- --- --- ---

</figure>

This would be stored in the order 1,4,2,3,7,5,6. First the decoder gets to frame 1. This is an I frame so it can be decoded independently. Then the decoder gets to frame 4. This is a P frame, so it’s predicted off an earlier frame. Because frames 2 and 3 are B frames, it’s predicted off frame 1, which has already been decoded. Then the decoder gets to frame 2, which is a B frame. The two reference frames (1 and 4) have already been decoded, and likewise for frame 3, which has the same reference frames. The same method is used to reorder the second half of the frames.

> 这将按 1,4,2,3,7,5,6 的顺序存储。首先，解码器到达帧 1。这是一个 I 帧，因此可以独立解码。然后解码器进入第 4 帧。这是一个 P 帧，所以它是从早期帧预测出来的。因为第 2 帧和第 3 帧是 B 帧，所以预测的是已经解码的第 1 帧。然后解码器到达帧 2，这是 B 帧。两个参考帧(1 和 4)已经被解码，同样对于具有相同参考帧的帧 3。使用相同的方法对帧的后半部分重新排序。

This reordering doesn’t change the order in which the frames are displayed on the screen (the _presentation order_). That is still done in numerical order. They’re just stored like this to make life easier for the decoder.

> 这种重新排序不会改变帧在屏幕上的显示顺序(\_presentation order)。这仍然是按照数字顺序进行的。它们只是这样存储，以便解码器更容易使用。

There isn’t a set way for MPEG-1 encoders to split the video into I, P and B frames. Each piece of encoding software does it a little differently. Most videos follow the pattern shown in [Table 9-1](#12_9781119183938-ch09.xhtml#c09-tbl-0001), with I frames at regular intervals, P frames evenly spaced between I frames, and B frames for the rest. An I frame and its successive P and B frames are known as a _group of pictures_ (GOP); the pattern of P and B frames is known as the _GOP structure_; and the size of the gap between I frames is known as the _GOP size_.

> MPEG-1 编码器没有将视频分割成 I、P 和 B 帧的固定方式。每一个编码软件都有点不同。大多数视频遵循[表 9-1](#12*9781119183938-ch09.xhtml#c09-tbl-0001) 中所示的模式，I 帧以规则的间隔排列，P 帧在 I 帧之间均匀分布，其余为 B 帧。I 帧及其连续的 P 和 B 帧被称为图片组(GOP)；P 和 B 帧的模式称为\_GOP 结构；并且 I 帧之间的间隙的大小被称为\_GOP 大小\*。

The GOP size and structure can be set by the encoder depending on the required bit rate, and how easily we wish to be able to seek through a video. Because only I frames can be decoded independently, we can only seek to a GOP boundary; a small GOP size makes it easier to seek to an arbitrary location in the video, generally at the cost of requiring a higher bit rate for a given quality due to the increased number of expensive I frames.

> GOP 大小和结构可以由编码器根据所需的比特率以及我们希望能够通过视频搜索的容易程度来设置。因为只有 I 帧可以独立解码，所以我们只能搜索 GOP 边界；小的 GOP 大小使得更容易寻找视频中的任意位置，通常以由于昂贵的 I 帧数量的增加而要求给定质量的较高比特率为代价。

Available bandwidth is particularly important because videos are usually intended to be played without buffering. We typically think of bandwidth today in terms of an Internet connection, but when the MPEG-1 codec was designed, other factors were more important because streaming video over the web wasn’t yet possible. MPEG-1 was designed to work at a range of bit rates, but the key one for the designers was the speed at which a CD-ROM drive could read data (1.5 megabits per second (Mbits/s)). MPEG-1 provides roughly the same quality as a VHS video cassette at this bit rate. The Video CD format, a precursor to DVDs, stores 74 minutes of MPEG-1 video on a standard CD.

> 可用带宽特别重要，因为视频通常在没有缓冲的情况下播放。我们通常认为今天的带宽是指互联网连接，但当设计 MPEG-1 编解码器时，其他因素更为重要，因为通过网络传输视频还不可能。MPEG-1 被设计为在各种比特率下工作，但对设计者来说，关键是 CD-ROM 驱动器读取数据的速度(每秒 1.5 兆比特(Mbit/s))。MPEG-1 在该比特率下提供与 VHS 盒式录像带大致相同的质量。VCD 格式是 DVD 的前身，在标准 CD 上存储 74 分钟的 MPEG-1 视频。

Video CD is a good example of a `constant bit rate` format: it isn’t possible to run the CD faster to get more bit rate to encode a rapidly changing scene, or to run it more slowly to conserve space when the scene isn’t changing. Modern streaming video codecs often vary their bit rate (within limits) according to scene complexity. There are a variety of techniques an encoder can use to keep the video stream at the required bit rate. First you need to understand how MPEG-1 encodes image data and residuals.

> 视频 CD 是 `恒定比特率` 格式的一个很好的例子：不可能更快地运行 CD 以获得更多的比特率来对快速变化的场景进行编码，也不可能在场景没有变化时更慢地运行 CD 来节省空间。现代流式视频编解码器通常根据场景复杂性改变其比特率(在限制范围内)。编码器可以使用多种技术来将视频流保持在所需的比特率。首先，您需要了解 MPEG-1 如何编码图像数据和残差。

### Understanding Frequency Transform

As previously described, MPEG-1 exploits the eye’s inability to distinguish fine changes in colour through chroma subsampling. Another helpful (for codec designers) attribute of the human visual system is that we find it harder to detect fine (high-frequency) changes in either brightness or colour than to detect coarser-grained (low-frequency) changes. In principle, we can represent high-frequency details in the scene less accurately, or even discard them altogether, without compromising perceptual quality.

> 如前所述，MPEG-1 利用眼睛无法通过色度二次采样区分颜色的细微变化。人类视觉系统的另一个有用(对编解码器设计者来说)属性是，我们发现检测亮度或颜色的精细(高频)变化比检测粗粒度(低频)变化更困难。原则上，我们可以不太准确地表示场景中的高频细节，甚至完全丢弃它们，而不影响感知质量。

Just as we transformed the image into the Y’C<sub>b</sub>C<sub>r</sub> colorspace to allow us to separate and subsample chroma, we must transform our data again to allow us to discard high-frequency details. This time, the four 8×8 luma blocks and two 8×8 chroma blocks that make up a macroblock are each passed through a discrete cosine transformation (DCT). The mathematical details are beyond the scope of this book, but the key is that after applying the DCT we no longer store a grid of 8×8 sample values, one for each point (a _spatial representation_), but instead store details of how the samples change as we move across the block in the _x_ and _y_ directions (a _frequency representation_).

> 正如我们将图像转换为 Y'C<sub>b</sub>C<sub>r</sub>颜色空间以允许我们分离和二次采样色度一样，我们必须再次转换数据以允许我们丢弃高频细节。这一次，构成宏块的四个 8×8 亮度块和两个 8×9 色度块分别通过离散余弦变换(DCT)。数学细节超出了本书的范围，但关键是，在应用 DCT 之后，我们不再存储 8×8 个样本值的网格，每个点一个(空间表示)，而是存储样本在块中沿\_x 和\_y 方向移动时如何变化的细节(频率表示)。

It’s easiest to understand the DCT by first thinking of the one-dimensional case: a single line of an 8×8 sample block. This one line has eight sample values that could be displayed as a line graph. The DCT decomposes this line into a weighted sum of several cosine waves (_basis functions_) of different frequencies. When added together, these functions have the same value as the line (at least at the sample points). The cosine waves are described by coefficients that give the amplitude of each cosine wave. It turns out that eight coefficients (and eight waves of different frequencies) are enough to accurately capture the original signal—we’ve traded eight spatial-domain samples for eight frequency-domain coefficients. In the two-dimensional case, it turns out that we need 64 two-dimensional cosine waves (surfaces that vary at different rates in the _x_ and _y_ directions) and 64 coefficients.

> 首先考虑一维情况：8×8 样本块的单行，最容易理解 DCT。这一行有八个样本值，可以显示为折线图。DCT 将这条线分解为不同频率的几个余弦波(_basis functions_)的加权和。当将这些函数相加时，它们的值与直线的值相同(至少在采样点处)。余弦波由给出每个余弦波振幅的系数来描述。事实证明，八个系数(和八个不同频率的波)足以准确捕获原始信号，我们用八个空间域样本交换了八个频域系数。在二维情况下，我们需要 64 个二维余弦波(在 *x* 和 *y* 方向上以不同速率变化的表面)和 64 个系数。

It is helpful to write the 64 coefficients in an 8×8 block, with the ones in the top left representing the lower frequencies, and the ones in the bottom right representing the higher frequencies (see Figure 9-5). The top-left value is known as the DC coefficient and is always equal to the average value of all the samples in the block. In other words, it’s the value of the block without taking into account any of the spatial changes.

> 将 64 个系数写在一个 8×8 的块中很有帮助，左上角的系数代表较低的频率，右下角的系数则代表较高的频率(见图 9-5)。左上角的值称为 DC 系数，总是等于块中所有样本的平均值。换句话说，它是块的值，而不考虑任何空间变化。

---

> [!NOTE]

The name DC comes from direct current and is a relic from when similar methods were used to analyse electricity.

> DC 这个名字来源于直流电，是用类似方法分析电力时的遗留物。

![[FIGURE 9-5:](#12_9781119183938-ch09.xhtml#rc09-fig-0005) The spatial frequencies that each coefficient represents](./media/images/9781119183938-fg0905.png)

All the other values are called AC (alternating current) coefficients. In [Figure 9-5](#12_9781119183938-ch09.xhtml#c09-fig-0005), the top line represents changes in purely the horizontal direction, with the leftmost AC coefficient (next to the DC) holding the lowest frequency data, while the rightmost one holds the highest frequency data. Similarly, the leftmost column holds information about changes in purely the vertical direction. The other values hold information about changes in both directions. For example, the rightmost value on the second row corresponds to high-frequency change in the horizontal direction and low-frequency change in the vertical direction.

> 所有其他值称为 AC(交流)系数。在[图 9-5](#12_9781119183938-ch09.xhtml#c09-fig-0005) 中，顶线表示纯水平方向的变化，最左侧的 AC 系数(DC 旁边)保存最低频率数据，而最右侧的 AC 系数保存最高频率数据。类似地，最左边的列保存关于纯垂直方向上的变化的信息。其他值保存有关两个方向上的变化的信息。例如，第二行中最右侧的值对应于水平方向上的高频变化和垂直方向上的低频变化。

Just as when we transformed from RGB to Y’CbCr, the DCT hasn’t compressed the image itself: the cosine coefficients take up roughly the same amount of space as the original data. However, once again it has set us up to be able to apply a subsequent lossy compression step in a way that minimises the perceived impact on visual quality. The lossy step in this case is _quantisation_—dividing each coefficient by a number and rounding down during encoding, and then multiplying by the same number during decoding to get back a similar (but generally not quite identical) number. As human eyes are more able to detect errors in low-frequency data than high-frequency data, the encoder generally quantises the high-frequency coefficients more coarsely.

> 正如我们从 RGB 转换为 Y'CbCr 时一样，DCT 并没有压缩图像本身：余弦系数占用的空间与原始数据大致相同。然而，它再次使我们能够以最小化对视觉质量的感知影响的方式应用随后的有损压缩步骤。在这种情况下，有损步骤是量化-将每个系数除以一个数字，并在编码过程中向下舍入，然后在解码过程中乘以相同的数字，得到一个相似(但通常不完全相同)的数字。由于人眼比高频数据更能检测低频数据中的误差，编码器通常更粗略地量化高频系数。

Take a look at Figures 9-6, 9-7 and 9-8, which contain a frame with increasingly large amounts of compression. As the file size gets smaller, more and more errors start to creep into the higher-frequency portions of the image.

> 看看图 9-6、9-7 和 9-8，其中包含一个压缩量越来越大的帧。随着文件大小变小，越来越多的错误开始进入图像的高频部分。

![[FIGURE 9-6:](#12_9781119183938-ch09.xhtml#rc09-fig-0006) At maximum quality, there’s little quantisation, so both the high- and low-frequency portions of the image are displayed well. This image has about 6 bits per pixel.](./media/images/9781119183938-fg0906.png)

![[FIGURE 9-7:](#12_9781119183938-ch09.xhtml#rc09-fig-0007) As the quantisation starts to come in, the high-frequency portions of the image (like edges) start to lose definition. This image has 0.9 bits per pixel.](./media/images/9781119183938-fg0907.png)

![[FIGURE 9-8:](#12_9781119183938-ch09.xhtml#rc09-fig-0008) With a high level of quantisation, only the low-frequency image is really visible, and you can see the boundaries between macroblocks. This image has 0.3 bits per pixel.](./media/images/9781119183938-fg0908.png)

Per-coefficient quantisation is performed by applying a _quantisation matrix_, which can be varied on a frame-by-frame basis to hit the target bit rate. This matrix has the same dimensions as the matrix holding the output from the DCT, and each entry in the quantisation matrix is the level of quantisation for the corresponding coefficient in the DCT output. The DCT value is divided by the quantisation value, and this result is rounded down. This reduces the numbers to a smaller range, and smaller ranges take less space to store.

> 每系数量化通过应用量化矩阵 x\_来执行，量化矩阵可以逐帧变化以达到目标比特率。该矩阵具有与保持 DCT 输出的矩阵相同的维数，量化矩阵中的每个条目是 DCT 输出中相应系数的量化级别。DCT 值除以量化值，此结果向下舍入。这将数字减少到更小的范围，更小的范围占用更少的存储空间。

In general, quantisation usually reduces many of the higher-frequency portions of the DCT to 0. Having a large proportion of the numbers the same makes the next step (entropy coding) efficient.

> 通常，量化通常将 DCT 的许多较高频率部分减少到 0。拥有大量相同的数字使得下一步(熵编码)变得高效。

Figures 9-9, 9-10 and 9-11 show the quantisation matrices that were used in [Figures 9-6](#12_9781119183938-ch09.xhtml#c09-fig-0006), [9-7](#12_9781119183938-ch09.xhtml#c09-fig-0007) and [9-8](#12_9781119183938-ch09.xhtml#c09-fig-0008), respectively. You can extract these from JPEG images (which are very similar to MPEG-1 I frames) on your Raspberry Pi using `djpeg`. First you need to install it with

> 图 9-9、9-10 和 9-11 分别显示了在[图 9-6](#12_9781119183938-ch09.xhtml#c09-fig-0006)、[9-7](#12_781119183938-ch09.xhtml#c09-config-0007) 和 [9-8](#1_978111918938-ch09-xhtml#c9-fig-0008) 中使用的量化矩阵。您可以使用 `djpeg` 从 Raspberry Pi 上的 JPEG 图像(非常类似于 MPEG-1 I 帧)中提取这些图像。首先，您需要使用

```
sudo apt-get install libjpeg-progs
```

![[FIGURE 9-9:](#12_9781119183938-ch09.xhtml#rc09-fig-0009) There’s no quantisation, which means that all of the frequency data is kept.](./media/images/9781119183938-fg0909.png)

![[FIGURE 9-10:](#12_9781119183938-ch09.xhtml#rc09-fig-0010) Quite a lot of quantisation, and heavily focused on the higher-frequency portions](./media/images/9781119183938-fg0910.png)

![[FIGURE 9-11:](#12_9781119183938-ch09.xhtml#rc09-fig-0011) Much of the high-frequency data is removed entirely.](./media/images/9781119183938-fg0911.png)

Then you can run the following where `image.jpeg` is the name of the JPEG file:

> 然后可以运行以下命令，其中 `image.jpeg` 是 jpeg 文件的名称：

```

djpeg -verbose -verbose image.jpeg > /dev/null

> djpeg-verbose-verbose image.jpeg>/dev/null
```

Normally this gives two matrices—one for the luma values and one for the chroma values—but these images are black and white so only have luma values. If you’re testing the output of the Raspberry Pi camera module, you may find that the quantisation matrix is set to not quantise at all (that is, it’s all 1s) unless you specify a quality option in the `raspistill` command (for example, `-q 50`).

> 通常这会给出两个矩阵，一个用于亮度值，另一个用于色度值，但这些图像是黑白的，因此只有亮度值。如果您正在测试 Raspberry Pi 相机模块的输出，您可能会发现量化矩阵设置为完全不量化(即，全为 1)，除非您在 `raspistill` 命令中指定了质量选项(例如，`-q 50` )。

As you can see in [Figures 9-10](#12_9781119183938-ch09.xhtml#c09-fig-0010) and [9-11](#12_9781119183938-ch09.xhtml#c09-fig-0011), the quantisation values tend to be roughly equal along trailing diagonals. This is because these lines contain coefficients to which our eyes have roughly the same sensitivity. For example, in [Figure 9-11](#12_9781119183938-ch09.xhtml#c09-fig-0011), the fourth value across the top line corresponds to the same frequency horizontally as the fourth one down on the leftmost line does vertically. One has a quantised coefficient of 80, whereas the other has one of 70; they’re not exactly the same because empirical studies have found that slightly asymmetric matrices yield slightly better perceptual quality at a given bit rate. The two coefficients between them (65 and 70) correspond to DCT basis functions with slightly lower horizontal frequency and slightly higher vertical frequency, and are similar in magnitude.

> 如您在[图 9-10](#12_9781119183938-ch09.xhtml#c09-fig-0010) 和 [9-11](#12_781119183938-ch09.xtml#c09-pict-0011) 中所见，量化值沿后对角线方向大致相等。这是因为这些线包含的系数与我们的眼睛具有大致相同的灵敏度。例如，在[图 9-11](#12_9781119183938-ch09.xhtml#c09-fig-0011) 中，顶行上的第四个值在水平方向上对应的频率与最左边行上的下一个值在垂直方向上的频率相同。一个量化系数为 80，而另一个为 70；它们并不完全相同，因为实证研究发现，在给定的比特率下，稍微不对称的矩阵会产生稍微更好的感知质量。它们之间的两个系数(65 和 70)对应于具有略低水平频率和略高垂直频率的 DCT 基函数，并且在幅度上相似。

The matrix of quantised DCT coefficients has to be serialised into a single stream of numbers in order to be stored in a file or transmitted over a network. Usually when serialising a matrix like this, each row is sent one after the other; in this case, however, the final step (entropy coding) is more efficient if the matrix is serialised in a zig-zag pattern.

> 量化 DCT 系数矩阵必须串行化为单个数字流，以便存储在文件中或通过网络传输。通常，当对这样的矩阵进行串行化时，每一行都会一个接一个地发送；然而，在这种情况下，如果矩阵以 Z 字形模式串行化，则最后一步(熵编码)更有效。

This zig-zag pattern starts with the coefficient that our eyes are most sensitive to and moves through them in the order of decreasing sensitivity. This should roughly equate to quantisation levels getting higher and higher. As the quantisation level gets higher, more and more of the quantised values will be zero, and this string of zeros is very effectively compressed in the next stage. See Figure 9-12 for an example.

> 这种 Z 字形图案从我们的眼睛最敏感的系数开始，并以敏感度降低的顺序穿过它们。这应该大致等同于量化水平越来越高。随着量化水平越来越高，越来越多的量化值将为零，这串零在下一阶段被非常有效地压缩。示例见图 9-12。

![[FIGURE 9-12:](#12_9781119183938-ch09.xhtml#rc09-fig-0012) The process of quantising and serialising the output from MPEG-1 I frame DCT](./media/images/9781119183938-fg0912.png)

### Using Lossless Encoding Techniques

The final part of the MPEG-1 encoding process applies lossless compression techniques to the quantised coefficients and other data including mode choice flags and motion vectors. There are three methods that MPEG-1 uses to get the file size as small as possible:

> MPEG-1 编码过程的最后部分将无损压缩技术应用于量化系数和其他数据，包括模式选择标志和运动矢量。MPEG-1 使用三种方法使文件大小尽可能小：

- Differential pulse-code modulation (DPCM) - Run-length encoding (RLE) - Huffman coding

> -差分脉冲编码调制(DPCM).游程长度编码(RLE).霍夫曼编码

Certain parameters, notably DC coefficients and motion vectors, are strongly correlated between successive macroblocks. DPCM exploits this correlation by storing only the difference between the last value and the current value. The differences have a tighter frequency distribution than the values themselves, and so respond better to Huffman coding.

> 某些参数，特别是 DC 系数和运动矢量，在连续宏块之间强烈相关。DPCM 通过仅存储上一个值和当前值之间的差值来利用这种相关性。这些差异具有比值本身更紧密的频率分布，因此对霍夫曼编码的响应更好。

RLE is simply the process of shortening strings of the same value. For example, if a quantised DCT matrix ends with a series of 40 zeros, this could be represented by 40 repetitions of the number zero. However, in RLE, it’s represented by the zero once, and a count of 40 times. This is particularly effective in MPEG encoding because the zigzag ordering of coefficients ensures that this situation happens very frequently, especially at higher quantisation levels.

> RLE 只是缩短相同值字符串的过程。例如，如果量化 DCT 矩阵以一系列 40 个零结尾，这可以用数字零的 40 个重复来表示。然而，在 RLE 中，它由零表示一次，计数为 40 次。这在 MPEG 编码中特别有效，因为系数的 Z 字形排序确保了这种情况非常频繁发生，尤其是在更高的量化级别。

Huffman coding also removes duplicated data, but it works on sequences of symbols that are repeated at different locations in the data, not simply blocks of repeated identical symbols. Sequences that occur frequently are assigned short binary representations, while those that occur rarely are assigned longer representations. For example, if the text of this chapter were Huffman coded, the encoder might see that the word `encoded` is repeated many times and so replace this with a representation that’s only 1 byte long, saving space. The statistics of the MPEG-1 symbol stream are such that Huffman encoding typically performs very well.

> 霍夫曼编码也可以去除重复的数据，但它适用于在数据中不同位置重复的符号序列，而不仅仅是重复的相同符号块。频繁出现的序列被指定为短二进制表示，而很少出现的序列则被指定为较长的表示。例如，如果本章的文本是霍夫曼编码的，编码器可能会看到单词 `encoded` 重复多次，因此将其替换为仅 1 字节长的表示，从而节省空间。MPEG-1 符号流的统计数据使得霍夫曼编码通常表现得非常好。

## Changing with the Times

These basic techniques in MPEG-1 still form the basis of modern video compression today, more than 20 years after they were first introduced, that is:

> MPEG-1 中的这些基本技术在首次引入 20 多年后仍然是现代视频压缩的基础，即：

- Colorspace transformation, where incoming data in the RGB colorspace is transformed into the Y’C<sub>b</sub>C<sub>r</sub> colorspace and subsampled to exploit the eye’s differential sensitivity to luma and chroma - Splitting into GOPs comprising I, P and B frames and applying motion compensation to exploit the fact than many frames are similar - A frequency domain transform (DCT or other) to transform the spatial representation into a frequency representation - Quantisation that reduces the amount of data in the DCT coefficient matrix, exploiting the eye’s differential sensitivity to high- and low-frequency data - Entropy coding

> -色彩空间转换，其中 RGB 色彩空间中的输入数据被转换为 Y‘C ＜ sub ＞ b ＜ sub ＜ C ＜ sub ＞ r ＜ sub’色彩空间，并进行二次采样，以利用眼睛对亮度和色度的差分敏感性，P 和 B 帧，并应用运动补偿来利用比许多帧相似的事实-频域变换(DCT 或其他)将空间表示转换为频率表示-量化减少 DCT 系数矩阵中的数据量，利用眼睛对高频和低频数据的差分敏感性-熵编码

However, modern video codecs have developed more efficient ways of performing each of these tasks.

> 然而，现代视频编解码器已经开发出了执行这些任务的更有效的方法。

MPEG-1 started the digital video revolution, but some limitations quickly became apparent. It supported only two audio channels (stereo) but not surround sound. Also, it didn’t properly support interlaced video .

> MPEG-1 开启了数字视频革命，但一些限制很快就显现出来。它只支持两个音频通道(立体声)，但不支持环绕声。此外，它还不能正确支持隔行扫描视频。

---

> [!NOTE]

Interlaced video is a video technique to increase the apparent frame rate of a video. It’s commonly used in broadcast TV.

> 隔行视频是一种视频技术，用于提高视频的表观帧速率。它通常用于广播电视。

With these weaknesses corrected, MPEG-2 was the first digital video format to really become popular. Although nearly 20 years old at the time of writing, it still forms the basis of much commercial video compression, such as broadcast digital TV and DVDs. These applications place a premium on quality at reasonable file sizes. The MPEG-2 video compression standard is the same as the ITU’s H.262 standard.

> 纠正了这些缺点后，MPEG-2 成为第一种真正流行的数字视频格式。尽管在撰写本文时已近 20 年，但它仍然是许多商业视频压缩的基础，如广播数字电视和 DVD。这些应用程序以合理的文件大小来提高质量。MPEG-2 视频压缩标准与 ITU 的 H.264 标准相同。

Initially, an MPEG-3 video encoding standard was designed as an extension to MPEG-2. However, many of the proposed techniques were incorporated into MPEG-2 and the formal MPEG-3 designation was retired. The audio standard commonly known as MPEG-3 is, in fact, MPEG-1 layer 3, the most sophisticated of three possible audio encoding schemes specified alongside the MPEG-1 standard.

> 最初，MPEG-3 视频编码标准被设计为 MPEG-2 的扩展。然而，许多提议的技术被纳入 MPEG-2，正式的 MPEG-3 名称被废除。通常称为 MPEG-3 的音频标准实际上是 MPEG-1 第 3 层，它是与 MPEG-1 标准一起指定的三种可能的音频编码方案中最复杂的一种。

In parallel with the development of new standards, numerous encoder techniques have been developed that can be used to improve compression or perceptual quality in older standards as well as in newer ones.

> 在开发新标准的同时，已经开发了许多编码器技术，这些技术可以用于改进旧标准和新标准中的压缩或感知质量。

Just as our eyes are more sensitive to lower spatial frequencies, they’re also more sensitive to changes in brightness at some levels, particularly in the middle of the brightness range. _Lumi masking_ is the process where the encoder preferentially removes detail from areas of the image that are either very bright or very dark. This can assign more bitstream space to encoding medium-brightness blocks, which means that the frame looks better for a particular bit rate.

> 正如我们的眼睛对较低的空间频率更敏感一样，它们对某些水平的亮度变化也更敏感，特别是在亮度范围的中间 *Lumi masking* 是编码器优先从图像中非常亮或非常暗的区域去除细节的过程。这可以为编码中等亮度块分配更多的比特流空间，这意味着对于特定的比特率，帧看起来更好。

Encoders have considerable latitude in how they choose to quantise individual transform coefficients. The straightforward division-with-rounding approach described in the earlier `[Understanding Frequency Transform](#12_9781119183938-ch09.xhtml#c09-sec-0008)` section minimises error, but does not fully take into account the bit rate benefits of choosing small coefficients, which have shorter entropy codes, and of discarding isolated non-zero coefficients that break up long runs of zeros, which are cheap to encode using RLE. Techniques such as uniform or adaptive deadzone and trellis quantisation attempt to capture these benefits by biasing coefficients toward zero. Trellis quantisation, as implemented by the popular x264 encoder, uses a comparatively detailed model of a codec’s RLE and entropy coding schemes to identify quantisation choices that yield significant bit rate savings.

> 编码器在如何选择量化单个变换系数方面具有相当大的自由度。在前面的 `[理解频率变换](#12_9781119183938-ch09.xhtml#c09-sec-0008)` 部分中描述的带舍入的直接除法方法最小化了误差，但没有充分考虑选择具有较短熵码的小系数以及丢弃分解长串零的孤立非零系数的比特率优势，其使用 RLE 进行编码是廉价的。诸如均匀或自适应死区和网格量化之类的技术试图通过将系数偏置为零来获取这些益处。由流行的 x264 编码器实现的网格量化使用编解码器的 RLE 和熵编码方案的相对详细的模型来识别量化选择，从而显著节省比特率。

Both lumi-masking and trellis quantisation can be used in older and newer MPEG standards.

> 亮度掩蔽和格量化都可以在较旧和较新的 MPEG 标准中使用。

### The Latest Standards from MPEG

Just as digital video using MPEG-2 was starting to become popular, the landscape changed when home Internet connections started to become fast enough to download video.

> 正如使用 MPEG-2 的数字视频开始流行一样，当家庭互联网连接开始变得足够快，可以下载视频时，情况发生了变化。

If you’re putting a film on DVD, it really doesn’t matter what size the file is as long as it’s smaller than the capacity of the disc (4.7–9.4GB per side depending on the type of disk). However, when streaming video over the Internet, every megabyte counts. Smaller file sizes mean cheaper storage costs, less buffering for the viewer and lower bandwidth. What’s more, the playback devices for Internet viewing tend to be more powerful than digital TV set-top boxes. This extra processing power can be used to perform more complex decoding.

> 如果您要将电影放在 DVD 上，只要文件的大小小于光盘的容量(每边 4.7–9.4GB，取决于光盘的类型)，那么文件的大小实际上并不重要。然而，当通过互联网传输视频时，每兆字节都很重要。更小的文件大小意味着更便宜的存储成本、更少的观众缓冲和更低的带宽。此外，用于互联网观看的播放设备往往比数字电视机顶盒更强大。这种额外的处理能力可用于执行更复杂的解码。

There are two video compression sections to MPEG-4: parts 2 and 10. Part 2 was the first to become popular, and it introduced many new features such as quarter-pel motion vectors and global motion compensation. The term MPEG-4 is generally used informally to refer to the part 2 standard. Two implementations, Xvid and DivX, were particularly popular in the early days of illegal file sharing because they had small file sizes compared to the MPEG-2 DVDs from which the files were usually ripped. The implementations differed slightly in their implementation of the standard, so the implementations wouldn’t always play the same files.

> MPEG-4 有两个视频压缩部分：第 2 部分和第 10 部分。第 2 部分是第一个流行的部分，它引入了许多新功能，如四分之一像素运动矢量和全局运动补偿。术语 MPEG-4 通常非正式地用于指代第 2 部分标准。在非法文件共享的早期，Xvid 和 DivX 这两种实现特别受欢迎，因为它们的文件大小比 MPEG-2 DVD 小，而 MPEG-2 DVD 通常是从这些 DVD 中提取文件的。这些实现在标准的实现上略有不同，因此这些实现不会总是播放相同的文件。

MPEG didn’t release the entire MPEG-4 suite of standard in one go. MPEG-4 part 2 was released in 1999, whereas part 10 (more commonly known by its equivalent ITU designation, H.264) didn’t emerge for another four years. This meant that hardware had again improved, and part 10 is more complex (with a corresponding increase in compression performance) than any of the preceding standards.

> MPEG 并没有一次性发布整个 MPEG-4 标准套件。MPEG-4 第 2 部分于 1999 年发布，而第 10 部分(更常见的是其等同的 ITU 名称，H.264)在四年后才出现。这意味着硬件再次得到了改进，第 10 部分比之前的任何标准都更加复杂(压缩性能也相应提高)。

One of the main ways in which H.264 improves on its predecessors is by increasing the flexibility and precision of the motion compensation scheme.

> H.264 改进其前身的主要方式之一是增加运动补偿方案的灵活性和精度。

In previous standards, B frames could be predicted off two adjacent reference frames; H.264 increases this to a (probably excessive) maximum of 16 nearby frames, depending on resolution. As with MPEG-4, motion vectors are specified to quarter-pel precision. Earlier we said that MPEG-1 uses bilinear interpolation to calculate values halfway between integer sample positions. With quarter-pel motion vectors, there are three possible locations between any two pixels. It is possible to use the same bilinear interpolation to generate estimated sample values at these locations, but better results are possible with a more advanced interpolation method. Think again of the graph showing the sample values for a single channel along one line of pixels. Using linear interpolation, we said, was the same as drawing a straight line between adjacent samples and reading the value off that. A more effective way would be to try to fit a smooth curve against the line of samples using more than just the two immediately adjacent values, and using this to calculate the intermediate values.

> 在先前的标准中，可以从两个相邻的参考帧中预测 B 帧；H、 264 将其增加到(可能过度)16 个附近帧的最大值，这取决于分辨率。与 MPEG-4 一样，运动矢量被指定为四分之一像素精度。前面我们说过 MPEG-1 使用双线性插值来计算整数样本位置之间的中间值。对于四分之一像素运动矢量，任意两个像素之间有三个可能的位置。可以使用相同的双线性插值来生成这些位置的估计样本值，但使用更高级的插值方法可以获得更好的结果。再想想显示沿一行像素的单个通道的采样值的图表。我们说，使用线性插值与在相邻样本之间绘制直线并从中读取值相同。一种更有效的方法是尝试使用不止两个紧邻的值来拟合样本线的平滑曲线，并使用该曲线来计算中间值。

The sub-pel values are calculated in two stages in H.264. Firstly, the half-pel values are calculated using a six-tap filter. It has six taps because it takes into account the value of six nearby samples when calculating the value; in contrast, a bilinear filter has two taps. Although this enables it to calculate the half-pel values more accurately, it can take more time and energy to perform. So once the half-pel values have been calculated, we use linear interpolation to derive quarter-pel values as the average of two adjacent half- or whole-pel values.

> 在 H.264 中分两个阶段计算子像素值。首先，使用六抽头滤波器计算半像素值。它有六个抽头，因为它在计算值时考虑了六个附近样本的值；相比之下，双线性滤波器有两个抽头。尽管这使它能够更准确地计算半像素值，但执行此操作可能需要更多的时间和精力。因此，一旦计算了半像素值，我们就使用线性插值来导出四分之一像素值，作为两个相邻半像素或全像素值的平均值。

Where MPEG-1 performs motion compensation on a whole macroblock at a time, H.264 macroblocks can be split into smaller partitions for motion compensation. These can be as small as 4×4 luma pixels (which corresponds to 2×2 chroma pixels because these have been subsampled). These smaller areas can capture some motion better, though, of course, there is a decreased return because more motion vectors need to be stored should the small partitions be used.

> 当 MPEG-1 一次对整个宏块执行运动补偿时，H.264 宏块可以被分割成更小的分区用于运动补偿。这些像素可以小到 4×4 亮度像素(这对应于 2×2 色度像素，因为这些像素已经进行了二次采样)。这些较小的区域可以更好地捕捉一些运动，当然，由于如果使用较小的分区，则需要存储更多的运动向量，因此返回会减少。

H.264 also allows more efficient entropy coding methods including Context Adaptive Binary Arithmetic Coding (CABAC) and Context Adaptive Variable Length Coding (CAVLC). Both these coding methods exploit the fact that some things are more likely to appear when surrounded by other pieces of data. For example, look at this sentence:

> H、 264 还允许更有效的熵编码方法，包括上下文自适应二进制算术编码(CABAC)和上下文自适应可变长度编码(CAVLC)。这两种编码方法都利用了这样一个事实，即当被其他数据块包围时，某些东西更容易出现。例如，看看这句话：

Europe and America are separated by the \*\*\*\*\*\*\*\*\* ocean.

> 欧洲和美洲被海洋隔开。

You can probably guess that the missing word is Atlantic. Moreover, whenever you see the word ocean, it’s probably preceded by Atlantic, Pacific, Arctic, Indian or Southern. In these cases, you’re getting some information about what the word is, based on its context. Both CABAC and CAVLC use this sense of context to perform the final, lossless, stage of encoding more efficiently than the Huffman coding used in earlier video compression formats. As always, the trade-off is that these schemes require significantly more processing power to encode and decode.

> 你可能会猜到缺少的单词是大西洋。此外，每当你看到海洋这个词时，它的前面可能是大西洋、太平洋、北极、印度或南方。在这些情况下，您可以根据上下文获得有关单词的一些信息。CABAC 和 CAVLC 都使用这种上下文感来比早期视频压缩格式中使用的霍夫曼编码更有效地执行最终的无损编码阶段。与往常一样，权衡是这些方案需要显著更多的处理能力来编码和解码。

At high levels of quantisation, DCT-based video compression methods have a tendency to introduce _blocking artefacts_. These appear at the borders of transform blocks (8×8 pixel DCT blocks in the MPEG-1 case) and manifest as sudden step changes in brightness or colour. Prior to the introduction of H.264, some decoders implemented _deblocking filters,_ which are context-aware, low-pass filters that act to reduce blocking artefacts by tweaking the sample values on each side of transform block edges that are deemed to be `blocky` . These filters were not standardised and were generally out-of-loop, which is to say that they were applied immediately prior to displaying a frame and dependent P or B frames would fetch them from the non-deblocked image.

> 在高量化水平下，基于 DCT 的视频压缩方法有引入分块伪影的趋势。这些出现在变换块的边界(MPEG-1 情况下为 8×8 像素 DCT 块)，并表现为亮度或颜色的突然变化。在引入 H.264 之前，一些解码器实现了分块滤波器，这些滤波器是上下文感知的低通滤波器，通过调整被认为是 `块` 的变换块边缘每一侧的采样值来减少分块伪影。这些滤波器没有标准化，并且通常不在环路内，也就是说，它们在显示帧之前立即应用，并且相关的 P 或 B 帧将从非去块图像中提取它们。

H.264 introduced a sophisticated, standardised, in-loop deblocking filter. This is applied as the last stage of the frame decoding process, generally before the frame is written to memory, so dependent P or B frames now fetch their motion-compensation data from the (hopefully higher quality) deblocked image.

> H、 264 引入了一种复杂的、标准化的环内去块滤波器。这通常在将帧写入存储器之前作为帧解码过程的最后阶段应用，因此依赖 P 或 B 帧现在从(希望更高质量)解块图像中获取它们的运动补偿数据。

Take a look at Figures 9-13 and 9-14 to see the improvements in I frame compression between MPEG-1 and MPEG-4 part 10. Both of these are compressed at the same bit rate (0.9 bits per pixel). Because these are I frames, the image quality isn’t helped by the improved motion compensation.

> 查看图 9-13 和 9-14，了解 MPEG-1 和 MPEG-4 第 10 部分之间 I 帧压缩的改进。这两者都以相同的比特率(每像素 0.9 比特)进行压缩。因为这些是 I 帧，所以改进的运动补偿对图像质量没有帮助。

![[FIGURE 9-13:](#12_9781119183938-ch09.xhtml#rc09-fig-0013) MPEG-4 part 10 compressed I frame. Notice how there are few artefacts (the slight blurriness is because it’s zoomed in to show detail).](./media/images/9781119183938-fg0913.png)

![[FIGURE 9-14:](#12_9781119183938-ch09.xhtml#rc09-fig-0014) MPEG-1 compressed I frame. At this level of compression, the quantisation errors are significant.](./media/images/9781119183938-fg0914.png)

None of these improvements fundamentally changes the overall shape of the video codec pipeline. In fact, it hasn’t really changed since MPEG-1. However, the improvements do result in a significant increase in compression at the cost of requiring significantly more processing power for both encoding and decoding.

> 这些改进都没有从根本上改变视频编解码器管道的整体形状。事实上，自 MPEG-1 以来，它并没有真正改变。然而，这些改进确实导致压缩的显著增加，代价是编码和解码都需要显著更多的处理能力。

On the Raspberry Pi, VideoCore is capable of doing more or less all the work of video decoding. This is controlled through Open Media Acceleration (OpenMAX), an API that allows programmers to utilise the hardware acceleration in a standard way. Not all video software for the Raspberry Pi makes full use of VideoCore capability, but Raspbian does come with the source code for a simple H.264 player to demonstrate how to use VideoCore.

> 在复盆子 Pi 上，VideoCore 能够或多或少地完成视频解码的所有工作。这是通过 OpenMedia Acceleration(OpenMAX)控制的，OpenMAX 是一种 API，允许程序员以标准方式利用硬件加速。并非所有 Raspberry Pi 的视频软件都充分利用了 VideoCore 功能，但 Raspbian 确实附带了一个简单 H.264 播放器的源代码，以演示如何使用 VideoCore。

To test video encoding on your Raspberry Pi, the first thing you need to do is compile the example code. Launch LXTerminal and type the following command:

> 要在 Raspberry Pi 上测试视频编码，首先需要编译示例代码。启动 LXTerminal 并键入以下命令：

```

cd /opt/vc/src/hello_pi./rebuild.sh

> cd/opt/vc/src/hello_pi/重建.sh
```

Then you can run the example video by entering this:

> 然后，您可以通过输入以下内容来运行示例视频：

```

cd hello_video./hello_video.bin test.h264

> cd hello_video/hello_video.bin测试h.264
```

An H.264 video plays in full-screen mode. The first thing you should notice when the video is finished is that it didn’t use much CPU power (the green graph at the bottom right stayed quite low).

> H.264 视频以全屏模式播放。当视频完成时，您应该注意的第一件事是它没有使用太多的 CPU 功率(右下角的绿色图形保持得很低)。

Similarly, you can use OpenMAX to help encode video. You can test this out using the `hello_encode` example program with the following:

> 类似地，您可以使用 OpenMAX 来帮助编码视频。您可以使用下面的 `hello_encode` 示例程序对此进行测试：

```

cd ../hello_encode./hello_encode.bin

> cd/hello_encode/hello_encode.bin
```

You may notice that this process hogs the CPU for a few seconds because not all of the encoding functions can be run on the GPU. However, it’s still far faster than CPU-only encoding.

> 您可能会注意到，这个过程占用了 CPU 几秒钟，因为不是所有的编码功能都可以在 GPU 上运行。然而，它仍然比仅 CPU 编码快得多。

This creates a file called `test.h264`. You can play this file with the hello_video player with:

> 这将创建一个名为 `test.h264` 的文件。您可以使用 hello_video 播放器播放此文件：

```

../hello_video/hello_video.bin test.h264

> ../hello_video/hello_video.bin测试h.264
```

### H.265

H.264 is the most advanced video codec in wide use at the time of writing. However, it doesn’t represent the end of the road for video compression. Work has recently finished on the High Efficiency Video Codec (HEVC) standard, generally known by its ITU name, H.265.

> H、 264 是编写时广泛使用的最先进的视频编解码器。然而，这并不意味着视频压缩的终点。最近完成了高效视频编解码器(HEVC)标准的工作，该标准通常以 ITU 名称 H.265 而闻名。

The goal of H.265 is to reduce bit rate at constant quality by 50 percent compared to H.264 without significantly increasing the computational complexity of the decoding process.

> 与 H.264 相比，H.265 的目标是将恒定质量的比特率降低 50%，而不会显著增加解码过程的计算复杂性。

To achieve this goal, H.265 uses a new structure for storing the information. Instead of macroblocks, it uses coding tree units (CTUs). These fulfil roughly the same role as macroblocks in motion compensation, but they can be much larger (up to 64×64 luma pixels), and are recursively subdivided as needed. Larger CTUs allow graphically simple regions, such as clear blue sky or plain-coloured walls, to be encoded simply, whereas smaller CTUs allow regions with finer detail to be properly captured.

> 为了实现这一目标，H.265 使用新的结构来存储信息。它使用编码树单元(CTU)代替宏块。这些块在运动补偿中的作用与宏块大致相同，但它们可以更大(高达 64×64 亮度像素)，并根据需要递归细分。较大的 CTU 允许对图形简单的区域进行简单的编码，如清晰的蓝天或素色的墙壁，而较小的 CTU 则允许正确捕捉细节更精细的区域。

The final ITU H.265 standard was released in April 2013, but is only beginning to see widespread use. One reason for this is the lack of available decoding hardware. Although high-power CPUs like the ones found in modern desktop computers can decode HEVC, lower power devices, such as smartphones or the Raspberry Pi, need the assistance of the GPU; older GPUs aren’t able to decode H.265.

> 最终的 ITU H.265 标准于 2013 年 4 月发布，但只是开始广泛使用。原因之一是缺乏可用的解码硬件。虽然像现代台式计算机中的高功率 CPU 可以解码 HEVC，但低功率设备，如智能手机或树莓派，需要 GPU 的帮助；较旧的 GPU 无法解码 H.265。

## Motion Search

As we have seen, one of the key ways that encoders compress videos is by finding motion vectors that accurately describe the movement of one block compared to the previous frame, thereby minimising the residual and its associated bitstream requirement.

> 正如我们所看到的，**编码器压缩视频的关键方法之一是找到准确描述一个块相对于前一帧的运动的运动矢量，从而最小化残差及其相关的比特流要求。**

This begs the question, how do you calculate these motion vectors? In principle—for P frames at least—the process is easy. You take each block and compare it to all the potential locations on the preceding I or P frame (or other eligible frames depending on the compression standard). For each location, you compute the residual and work out the length of bitstream required to encode it, remembering to add the bits required to encode the motion vector: the DPCM and Huffman coding (in the case of MPEG-1) applied to the vector components means that it is generally cheapest to encode a vector very similar to that of the previous macroblock. The location that results in the smallest overall number of bits emitted `wins` and is used to construct the final stream (unless its cost exceeds that of simply encoding an I macroblock).

> 这就引出了一个问题，你如何计算这些运动向量？原则上，对于 P 帧，至少该过程是简单的。获取每个块并将其与前一个 I 或 P 帧(或其他符合条件的帧，取决于压缩标准)上的所有可能位置进行比较。对于每个位置，您计算残差并计算出对其进行编码所需的比特流长度，记住添加对运动向量进行编码所需要的比特：应用于向量分量的 DPCM 和霍夫曼编码(在 MPEG-1 的情况下)意味着对与前一宏块非常相似的向量进行编码通常是最便宜的。导致发射的比特总数最小的位置 `获胜` ，并用于构建最终流(除非其成本超过简单编码 I 宏块的成本)。

The problem with this is that it would take far too long to calculate all the differences, so instead encoders use algorithms that cut down the search area in some way, often using a hill-climbing hierarchical approach.

> 这样做的问题是，计算所有差异所需的时间太长，因此编码器使用的算法以某种方式减少搜索区域，通常使用爬山分级方法。

One such option is the diamond search. In this search, nine points in the reference frame are chosen in a diamond pattern around the place the block is located in the frame to be encoded. Then the search step takes place, which is:

> 其中一种选择是钻石搜索。在该搜索中，参考帧中的九个点以菱形图案围绕块在要编码的帧中所处的位置进行选择。然后进行搜索步骤，即：

- If the centre point has the lowest errors, move on to the final step. Otherwise, centre a new diamond around the point that has the lowest error rate. - Once you have located a diamond where the lowest error rate is in the middle, the final step is to switch to a smaller diamond. This subdivides the centre of the diamond into five sections, and the one with the smallest difference is chosen.

> -如果中心点的误差最小，请转到最后一步。否则，在错误率最低的点周围居中放置一个新的菱形。-一旦找到错误率最低的菱形，最后一步就是切换到较小的菱形。这将钻石的中心细分为五个部分，并选择差异最小的部分。

Figure 9-15 shows this algorithm in action. Step 1 shows the starting grid around the point (the circle). In Step 2, the grid moves again. In Step 3, the point with the smallest difference is the centre point, so it moves on to the final step with a smaller grid. This is only performed once in Step 4, and the point with the smallest difference is used.

> 图 9-15 显示了该算法的作用。步骤 1 显示围绕点(圆)的起始网格。在步骤 2 中，网格再次移动。在步骤 3 中，具有最小差异的点是中心点，因此它将以较小的网格移动到最后一步。这只在步骤 4 中执行一次，使用差异最小的点。

> [!note]
> 这是优化算法？叫啥来着

![[FIGURE 9-15:](#12_9781119183938-ch09.xhtml#rc09-fig-0015) The diamond motion search algorithm. The circle represents the starting point for that step and the hollow shape is the point with the smallest difference.](./media/images/9781119183938-fg0915.png)

You may think that there’s a good chance that this algorithm misses the actual motion, particularly in the case of fast motion, corresponding to many pixels per frame. This is correct, but the point here is not to create a perfect algorithm; the algorithm only needs to be good enough and run quickly enough to be useful. The described diamond search runs quite fast, but it doesn’t always find the optimum motion vectors. Remember that the residual (the difference between the motion compensation result and the actual source frame) is encoded, so even if the motion estimation isn’t perfect, the frame can still have a high image quality; it just needs to include more data in each frame.

> 您可能会认为，这种算法很有可能错过实际的运动，特别是在快速运动的情况下，对应于每帧许多像素。这是正确的，但这里的重点不是创建一个完美的算法；算法只需要足够好并且运行足够快就可以使用。所描述的菱形搜索运行得很快，但它并不总是找到最佳的运动向量。请记住，残差(运动补偿结果与实际源帧之间的差异)是编码的，因此即使运动估计不完美，帧仍然可以具有高图像质量；它只需要在每个帧中包括更多的数据。

When encoding a video, you have to make a choice between the quality of the motion estimation and the amount of time you want the encoding to take. Lower quality motion estimation results in either lower quality videos or larger file sizes (depending on how you set up the encoder), but lower quality motion estimation also results in a correspondingly shorter execution time.

> 在对视频进行编码时，您必须在运动估计的质量和编码所需的时间之间做出选择。较低质量的运动估计会导致较低质量视频或较大的文件大小(取决于如何设置编码器)，但较低质量运动估计也会导致相应的执行时间更短。

Take a look at Table 9-2 for the difference between encoding time and file size for a video using the `avconv` command on the Raspberry Pi.

> 请参阅表 9-2，了解使用 Raspberry Pi 上的 `avconv` 命令编码视频的时间和文件大小之间的差异。

<figure> <figcaption>

[Table 9-2](#12_9781119183938-ch09.xhtml#rc09-tbl-0002)  A Comparison of Motion Search Algorithms

> [表 9-2](#12_9781119183938-ch09.xhtml#rc09-tbl-0002)  运动搜索算法的比较

</figcaption>

**Motion search algorithm** **Filesize (bytes)** **Time taken to encode (seconds)** ----------------------------------- ---------------------- ------------------------------------ Exhaustive search algorithm (esa) 89961 39 Diamond (dia) 90713 23 Hadamard exhaustive search (tesa) 90004 44

> **运动搜索算法\***文件大小(字节)**_编码所需时间(秒)_**-------------------------------穷举搜索算法(esa)89961 39 Diamond(dia)90713 23 Hadamard 穷举搜索(tesa)90004 44

</figure>

The times in [Table 9-2](#12_9781119183938-ch09.xhtml#c09-tbl-0002) are based on a 2-second, 200×200 pixel video recorded on the Raspberry Pi camera module. You may have noticed that this takes far longer than `hello_encode.bin` despite this video being shorter. This shows just how much of a speed-up the GPU gives the encoder.

> [表 9-2](#12_9781119183938-ch09.xhtml#c09-tbl-0002) 中的时间基于树莓派相机模块上记录的 2 秒 200×200 像素视频。您可能已经注意到，尽管视频较短，但这比 `hello_encode.bin` 花费的时间要长得多。这显示了 GPU 为编码器提供了多少加速。

You can experiment with this yourself using the `avconv` command:

```
sudo apt-get install libav-tools
```

The basic usage is

> 基本用法是

```
avconv -i inputfile -vcodec libx264 -me_method method-name -crf 15 -g GOPsize outputfilename.mp4
```

where `method-name` is replaced with `dia`, `esa` or `tesa`, and `GOPsize` is replaced with the group of pictures size you want.

> 其中 `方法名` 替换为 `dia` 、 `esa` 或 `tesa` ，`GOPsize` 替换为所需的图片大小组。

At the end of the encoding, the output is various pieces of information, including details of the different frame types. Here’s the section from one of the preceding runs:

> 在编码结束时，输出的是各种信息，包括不同帧类型的详细信息。以下是前面运行的部分：

```
[libx264 @ 0x8b6360] frame I:3     Avg QP:12.69  size:  3229
[libx264 @ 0x8b6360] frame P:32    Avg QP:15.66  size:  2050
[libx264 @ 0x8b6360] frame B:13    Avg QP:18.11  size:   973
```

This shows you the breakdown in the number of frame types as well as their average size. QP is the quantisation parameter and is used to select a quantisation matrix on a per-frame or even per-macroblock basis; higher QPs mean higher quantisation. Remember that P frames and B frames can use I macroblocks as well as P macroblocks, so this also accounts for some of the size of the P frames in the preceding example.

> 这将显示帧类型数量及其平均大小的细分。QP 是量化参数，用于在每帧或甚至每宏块的基础上选择量化矩阵；较高的 QP 意味着较高的量化。请记住，P 帧和 B 帧可以使用 I 宏块，也可以使用 P 宏块，因此这也解释了前面示例中 P 帧的一些大小。

Try this for yourself to see how different quality settings (the number after `-crf`)—between 0 (very little compression) and 51 (very high compression)—change these numbers.

> 自己尝试一下，看看 0(非常小的压缩)和 51(非常高的压缩)之间的不同质量设置( `-crf` 之后的数字)如何改变这些数字。

If you remove `-g GOPsize` the encoder calculates which size it thinks is best. You can use this with different CRF values to see how this changes things.

> 如果删除 `-g GOPsize` ，编码器将计算其认为最佳的大小。您可以将其与不同的 CRF 值一起使用，以了解这是如何改变事情的。

### Video Quality

We’ve talked about how the encoder can get rid of some of the information to make the file smaller. As more and more information is removed to make the file size smaller, the video quality gets worse—but how much worse?

> 我们已经讨论了编码器如何去除一些信息以使文件变小。随着越来越多的信息被删除以使文件大小变小，视频质量会变得更差，但会差多少？

This is actually a difficult question to answer because the important fact is how good we humans perceive the quality to be. Something like the chroma subsampling would be very obvious to a computer checking for distortion, but it’s difficult for the eye to see. Other things are very obvious to the eye, but have less difference to synthetic quality metrics.

> 这实际上是一个很难回答的问题，因为重要的事实是我们人类对质量的感知有多好。像色度二次采样这样的东西对于计算机检查失真是非常明显的，但眼睛很难看到。其他的东西很明显，但与合成质量指标的差别较小。

The best way to assess video quality is to get real people to watch video samples and rate the comparative quality. This is the method MPEG uses when comparing different proposals for inclusion in a standard. However, it’s not really practical for most video encoding. Instead, you need a way of estimating the quality computationally. The most common method is the peak signal to noise ratio (PSNR).

> 评估视频质量的最佳方法是让真人观看视频样本并对比较质量进行评分。这是 MPEG 在比较标准中包含的不同建议时使用的方法。然而，对于大多数视频编码来说，它实际上并不实用。相反，您需要一种通过计算来估计质量的方法。最常见的方法是峰值信噪比(PSNR)。

PSNR is calculated by comparing what the image should be (the signal) to the difference between the image as it should be and the image as it is displayed after compression (the noise). The error rate is squared, so the PSNR can be calculated with the following equation:

> PSNR 是通过将图像应该是什么(信号)与图像应该是的图像和压缩后显示的图像之间的差异(噪声)进行比较来计算的。误差率为平方，因此 PSNR 可通过以下公式计算：

PSNR = 20 \* log<sub>10</sub>(Max/squareroot(MSE))

> PSNR=20\*log ＜ sub ＞ 10</sub ＞(最大/平方误差(MSE))

MSE (which stands for mean squared error) is calculated by taking the difference between the correct and actual values for each pixel, squaring this value and then taking the average across all the pixels. Max is the maximum value that a pixel can take. In most cases, video has 8 bits per colour channel, so this will be 255.

> MSE(代表均方误差)是通过取每个像素的正确值和实际值之间的差值，将该值平方，然后取所有像素的平均值来计算的。Max 是像素可以获取的最大值。在大多数情况下，视频每个颜色通道有 8 位，因此这将是 255 位。

It’s important to realise, though, that PSNR doesn’t correlate exactly to image quality as it’s perceived by the eye.

> 然而，重要的是要认识到，PSNR 与人眼感知的图像质量并不完全相关。

PSNR looks at the image like a computer does: as a grid of data. The Structural Similarity (SSIM) index is an alternative that attempts to look at the image like a person does. Therefore, it doesn’t look at an image on a pixel-by-pixel basis; instead it compares the image in three different ways: the luminance, the contrast and the structure. Each thing is calculated across the image as a whole and then compared with the results from the frame before compression.

> PSNR 像计算机一样查看图像：作为数据网格。结构相似性(SSIM)索引是一种尝试像人一样看待图像的替代方法。因此，它不会逐个像素地查看图像；相反，它以三种不同的方式比较图像：亮度、对比度和结构。在整个图像中计算每一项，然后与压缩前帧的结果进行比较。

### Processing Power

Playing video is often thought of as a basic function of a computer. After all, even cheap DVD players can do it without a problem. However, it actually entails a huge amount of processing power to perform, and this increases as demand for higher and higher resolution video increases. Many computers use the extra power in their GPUs to help them perform quickly. That’s not the only use of the GPU, as we’ll explore further in the next chapter.

> 播放视频通常被认为是计算机的基本功能。毕竟，即使是便宜的 DVD 播放机也能做到这一点。然而，它实际上需要大量的处理能力来执行，并且随着对越来越高分辨率视频的需求增加，这一点也会增加。许多计算机使用 GPU 中的额外功率来帮助它们快速运行。这不是 GPU 的唯一用途，我们将在下一章进一步探讨。
