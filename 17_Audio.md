Chapter 11

# Audio

**SOUND CAPABILITY ON** computers is certainly a significant matter. An old adage in the film and video industry states, `Sound is 70 percent of your production` . Sound accentuates the visual, sets moods, increases excitement, inspires the user and more. Computer games are one great example that demonstrates the importance of sound.

> 计算机的声音能力当然是一个重要问题。电影和视频行业的一句老话是： `声音占你制作的 70%` 。声音增强了视觉效果，设定了情绪，增加了兴奋感，激励了用户等等。电脑游戏就是一个很好的例子，证明了声音的重要性。

In short, this chapter is an exploration of sound on computers in general and specifically how the architecture of the Raspberry Pi supports music and all sorts of other sound manipulations. We discuss analog versus digital audio, sound over High Definition Multimedia Interface (HDMI), 1-bit digital analog conversion (DAC), both signal and sound processing, and Inter-IC Sound (I<sup>2</sup>S, a communications protocol for carrying digital audio signals).

> 简而言之，本章是对计算机上声音的一般探索，特别是树莓派的架构如何支持音乐和其他各种声音操作。我们讨论了模拟音频与数字音频、高清晰度多媒体接口(HDMI)上的声音、1 位数字模拟转换(DAC)、信号和声音处理以及 IC 间声音(I<sup>2</sup>S，一种用于传输数字音频信号的通信协议)。

We also cover the Raspberry Pi’s onboard sound, both the input and output features. We begin with the basics of sound on computers and a little history.

> 我们还介绍了树莓派的板载声音，包括输入和输出功能。我们从计算机声音的基础知识和一些历史开始。

## Can You Hear Me Now?

Right after World War II ended, the first computers were silent—except, of course, for the grinding and clacking of gears in the mechanical computers, the buzzing of power supplies and the _plink_ of vacuum tubes burning out in electronic mainframes. Then there was also the often-colourful language of operators when these monsters crashed due to faulty programs and the lack of operating systems to prevent or recover from the software mishap, necessitating a lengthy reboot.

> 第二次世界大战刚结束，第一批计算机就沉寂了，当然，除了机械计算机中齿轮的摩擦和咔嗒声、电源的嗡嗡声和电子主机中真空管烧坏的声音。此外，当这些怪物由于程序错误和缺乏操作系统来防止软件故障或从软件故障中恢复时，运营商的语言也常常丰富多彩，因此需要长时间重新启动。

The `language` we’re referring to is not COBOL or FORTRAN—or, to be more modern, Python or JavaScript. We’re talking about those nifty words learned by the soldiers, sailors, and airmen in combat during the war and generously passed to their fellow operators after they came into the growing data processing field.

> 我们所指的 `语言` 不是 COBOL 或 FORTRAN，或者更现代的 Python 或 JavaScript。我们谈论的是战争期间士兵、水手和飞行员在战斗中学到的那些妙语，在他们进入日益增长的数据处理领域后，他们慷慨地传递给了他们的同事。

Notice that when you read the preceding two paragraphs you hear sounds, even if they’re only in your head. Sound sets the stage and creates atmosphere. Sound is important. Think of this classic movie moment, the computer HAL 9000 singing `Daisy Bell` in the film _2001: A Space Odyssey_. Inspired by the IBM 7094 (from 1961), Hal provided an iconic moment in cinema and computer-generated sound/voice history. Although special effects were used at the time, computer sound capabilities quickly have become reality.

> 注意，当你阅读前两段时，你会听到声音，即使它们只在你的脑海中。声音设置舞台并营造氛围。声音很重要。想想这个经典的电影时刻，电脑 HAL9000 在电影《2001：太空漫游》中演唱 `黛西·贝尔` 。受到 IBM 7094(1961 年)的启发，哈尔在电影和计算机生成的声音/语音历史上提供了一个标志性的时刻。尽管当时使用了特效，但计算机声音功能很快就成为现实。

### MIDI

The true dawn of sound on computers, at least so far as widespread user interest is concerned, came with the advent of the personal computer. For the purposes of this discussion we consider that to have happened in 1980, when the Commodore 64, Radio Shack’s TRS-80 and the Apple II were popular. Then in 1981, IBM’s first IBM PC came on the market and more people started using personal computers for pleasure, such as playing games, as well as doing real work. Consequently, the sounds made by personal computers started to matter more and more, especially as people interested in music were figuring out ways for computers to assist them.

> 至少就广泛的用户兴趣而言，计算机声音的真正曙光是伴随着个人计算机的出现而来的。出于本次讨论的目的，我们认为这发生在 1980 年，当时准将 64、Radio Shack 的 TRS-80 和 Apple II 大受欢迎。然后在 1981 年，IBM 的第一台个人电脑上市，更多的人开始使用个人电脑来娱乐，比如玩游戏，以及做真正的工作。因此，个人电脑发出的声音开始变得越来越重要，特别是当对音乐感兴趣的人正在寻找计算机帮助他们的方法时。

In 1981, the Musical Instrument Digital Interface (MIDI) hit the music industry. It caused a lot of excitement among both professional and amateur musicians. Now you could turn music into _data_ right on your personal computer. You could load it into a device called a sequencer, edit it, save it and play it back later. Cool!

> 1981 年，乐器数字接口(MIDI)冲击了音乐行业。这在职业和业余音乐家中都引起了极大的兴奋。现在你可以在你的个人电脑上把音乐变成数据。你可以把它加载到一个叫做音序器的设备中，编辑它，保存它，稍后再播放。凉的

Of course, it occurred to many people that _their_ personal computers would be ideal for this purpose. Soon MIDI add-on cards and sequencing software hit the market. People could add a MIDI player to their computers and download all sorts of MIDI music from bulletin boards (which were precursors to the Internet).

> 当然，许多人都想到，他们的个人电脑是实现这一目的的理想选择。很快，MIDI 附加卡和排序软件进入市场。人们可以在电脑上添加 MIDI 播放器，并从公告板(这是互联网的前身)下载各种 MIDI 音乐。

### Sound Cards

Of course, it is rather hard to enjoy music if you cannot hear it. Yes, many of the early computers, such as the IBM PC, came with tiny built-in speakers. These were good for little more than the occasional diagnostic beep or other system sound. In fact, that was their design purpose. They provided a limited audio frequency range and very low power. It was useless to hope for decent music reproduction from them.

> 当然，如果你听不到音乐，欣赏音乐是相当困难的。是的，许多早期的电脑，如 IBM PC，都配备了微型内置扬声器。除了偶尔的诊断嘟嘟声或其他系统声音外，这些声音都很好。事实上，这就是他们的设计目的。它们提供了有限的音频范围和极低的功率。希望从他们那里复制出像样的音乐是没有用的。

For quite some time, the best way to achieve good sound in a personal computer was with an add-on card. It took about six years for sound cards to become common built-in features in computers.

> 在相当长的一段时间里，在个人电脑中实现良好声音的最佳方法是使用附加卡。声卡成为电脑常见的内置功能大约花了六年时间。

Beginning around 1988, sound cards became common and several good choices existed, which meant digital audio moved from being a possibility to a necessity for many computer owners. These cards included capability for sound amplification and they supported external speakers, which remains the norm for personal computers today.

> 从 1988 年左右开始，声卡变得普遍，有几个好的选择，这意味着数字音频对许多电脑用户来说从一种可能性变成了一种必需品。这些卡具有声音放大功能，并支持外部扬声器，这仍然是当今个人电脑的标准。

Most modern personal computers come boxed with decent sound cards, speakers, network adapters and other accessories for which you once had to buy additional cards. However, for the very best in sound, great alternatives exist, from speakers to a separate subwoofer bass box that can shake your whole house.

> 大多数现代个人电脑都配有像样的声卡、扬声器、网络适配器和其他配件，而你曾经不得不为此购买额外的卡。然而，为了获得最好的声音，有很多替代品，从扬声器到一个单独的低音音箱，可以震动整个房子。

Computers with add-on sound cards had the capability to digitally record output from the speakers to the microphone input. A number of truly professional sound cards are available for turning your computer into a studio-level sound editor and mixer.

> 带有附加声卡的计算机能够以数字方式记录从扬声器到麦克风输入的输出。许多真正专业的声卡可用于将您的计算机变成录音室级的声音编辑器和混音器。

Today, computer sound rocks. Now you need to know how it works.

> 今天，电脑声音很震撼。现在你需要知道它是如何工作的。

## Analog vs. Digital

People began using and recording sound in the nineteenth century—think of Alexander Graham Bell’s telephone (see Figure 11-1), Thomas Edison’s phonograph, and so on. This type of producing sound and the recording of it used a _transducer_ (a microphone is one of those) to convert variations in air pressure to an electrical waveform that changed in frequency and amplitude to match the actual sounds. When played back on a speaker (which is like a reverse transducer), people heard a close approximation of the recorded sounds. This type of recording is known as _analog._

> 人们在 19 世纪开始使用和录制声音，比如亚历山大·格雷厄姆·贝尔的电话(见图 11-1)、托马斯·爱迪生的留声机等等。这种类型的声音产生和记录使用了一个转换器(麦克风就是其中之一)将气压的变化转换为频率和振幅变化的电波形，以匹配实际声音。当在扬声器上回放时(这就像一个反向换能器)，人们听到的声音与录制的声音非常接近。这种类型的记录称为 *analog*

![[FIGURE 11-1:](#14_9781119183938-ch11.xhtml#rc11-fig-0001) An 1876 photo of Alexander Graham Bell’s famous first call on the first telephone,  `Come here, Mr. Watson, I want to see you,`  was all analog sound.](./media/images/9781119183938-fg1101.png)

Over the next hundred years, analog sound recording techniques got very good indeed. Tapes and records played through high-end stereo equipment certainly approached the quality of `being there` . So, you might now ask, `If analog is so good, why change?`

> 在接下来的一百年里，模拟录音技术确实变得非常好。通过高端立体声设备播放的录音带和唱片肯定接近 `在那里` 的质量。所以，你现在可能会问，`如果模拟如此好，为什么要改变？`

The answer is simple: only the first generation (the original) recording is good. If you copy, say, the master tape from a recording studio onto another tape, it creates a little noise, and all those squiggly audio waves become slightly distorted. Copying the copy introduces more noise, and so on. Static, hisses, whistles. Besides, because computers are digital, they can’t manipulate recorded sound.

> 答案很简单：只有第一代(原始)录音是好的。例如，如果你把录音室的母带复制到另一盘磁带上，它会产生一点噪音，所有那些弯弯曲曲的音频波都会稍微失真。复制副本会引入更多噪音，等等。静电、嘶嘶声、口哨声。此外，由于计算机是数字的，它们不能操纵录制的声音。

_Digital audio_ solves the noise problem and makes for easy editing in many ways. When sound comes into a digital recorder—via a microphone or from a recorded analog tape or some other medium—the recorder changes the waveforms into binary 1s and 0s that the computer can understand. In other words, the sounds become _data_ and can be formatted and saved as an audio file such as `.wav`</code> or `.mp3`.

> _数字音频解决了噪声问题，并在许多方面便于编辑。当声音通过麦克风或录制的模拟磁带或其他介质进入数字录音机时，录音机会将波形转换为计算机可以理解的二进制 1 和 0。换句话说，声音变为_data_，可以格式化并保存为音频文件，如 `.wav` </code>或 `.mp3` 。

A digital audio file can be copied hundreds, thousands, millions of times and remain exactly the same quality as the first-generation file. No noise is introduced. In addition, the file is now in digital format and thus available for editing, cutting, enhancing and mixing in all sorts of ways.

> 数字音频文件可以复制数百、数千、数百万次，并保持与第一代文件完全相同的质量。不会引入噪音。此外，该文件现在是数字格式，因此可以以各种方式进行编辑、剪切、增强和混合。

It was once true that analog techniques provided all electronic sound, the sound itself being a recording of what humans could actually hear. That’s not the case anymore. Software can create music and other sounds from scratch, all digitally. Hundreds of music creation programs, which are available on the Internet, aid in this creation of virtual music, sound effects and even synthesis of artificial `human` speech.

> 曾经，模拟技术确实提供了所有的电子声音，声音本身就是人类实际听到的声音的记录。现在已经不是这样了。软件可以从头开始创作音乐和其他声音，全部都是数字化的。互联网上有数百个音乐创作程序，它们有助于创造虚拟音乐、音效，甚至合成人工 `人类` 语音。

To sum up, in a comparison of analog and digital audio, digital wins for three major reasons:

> 综上所述，在模拟音频和数字音频的比较中，数字音频获胜有三个主要原因：

- Sounds and/or music become computer data, which is easy to manipulate.

> -声音和/或音乐成为计算机数据，易于操作。

- No noise is introduced, regardless of how many generations of copies you make.

> -无论您**制作了多少代拷贝，都不会引入任何噪音。**

- Software can create digital music and sound with any analog input.

> -**软件可以通过任何模拟输入创建数字音乐和声音。**

## Sound and Signal Processing

Processing audio refers to several things, most of which concern deliberately modifying a recorded or created digital audio file. This section gives a general overview of audio processing. An explanation of the hardware specifics and computer architecture that make sound, input and output possible follow later in this chapter. The chapter concludes with information about how to actually edit sound using the Raspberry Pi and its onboard sound hardware.

> 处理音频涉及多个方面，其中大多数涉及故意修改录制或创建的数字音频文件。本节概述了音频处理。本章稍后将对硬件细节和计算机架构进行解释，以使声音、输入和输出成为可能。本章最后介绍了如何使用 Raspberry Pi 及其内置声音硬件实际编辑声音。

With the advent of digital audio, manipulating audio with computers rapidly replaced the old methods, and digital audio now dominates in the music industry, broadcasting, home recording and so forth. Podcasts (recorded segments like radio programs but intended to be played online) proliferate on the Internet, and music lovers download millions upon millions of music files daily.

> 随着数字音频的出现，用计算机操纵音频迅速取代了旧方法，数字音频现在在音乐行业、广播、家庭录音等领域占据主导地位。播客(广播节目等录制片段，但打算在线播放)在互联网上激增，音乐爱好者每天下载数以百万计的音乐文件。

Computerised audio manipulation can take several forms:

> 计算机音频操作可以采取多种形式：

- Editing the file to delete or add sounds, adjust the volume, and so on

> -编辑文件以删除或添加声音、调整音量等

- Recording the audio with special effects (reverb, for example) or adding effects during editing.

> -使用特殊效果(例如混响)录制音频或在编辑过程中添加效果。

- Compressing the file to make high and low amplitudes even out and improve sound

> -压缩文件以使高低振幅均匀，并改善声音

- Encoding or decoding information from audio for the purpose of computer operation, data collection or various modes of digital communication

> -为计算机操作、数据收集或各种数字通信模式而对音频中的信息进行编码或解码

### Editing

In the days of analog-only sound, editing was a pain. To remove a small bit of annoying noise in a recording, one had to cue the tape, guess where the offending sound lay, use a razor blade or scissors to cut out the section and then glue the tape back together. (Film editing used the same process.) Precise? Definitely not.

> 在只有模拟声音的时代，编辑是一种痛苦。为了消除录音中的一点恼人的噪音，人们必须提示录音带，猜测冒犯的声音在哪里，用剃须刀片或剪刀剪下部分，然后将录音带粘在一起。(电影剪辑使用了相同的过程。)精确吗？绝对不是。

To edit digital audio today, you look at the waveform or waveforms, use a mouse pointer to highlight the part that needs to go and press the Delete button. When you play the file, you cannot tell where the edits took place.

> 要编辑今天的数字音频，请查看波形，使用鼠标指针突出显示需要删除的部分，然后按 Delete 按钮。播放文件时，无法确定编辑发生的位置。

Editing enables you to adjust volume, reduce noise—including wind pops in microphones that happen while recording outdoors, or someone’s cough during a concert—and do many other things such as adding various enhancing effects, which is covered in the next section.

> 编辑使您能够调整音量，减少噪音，包括在户外录制时麦克风中的爆裂声，或演唱会期间某人的咳嗽声，还可以做许多其他事情，如添加各种增强效果，这将在下一节中介绍。

Editing includes _mixing_ (combining audio waves) of many _tracks_. During recording of an orchestra, for example, there might be 20 or more microphones spread around to record different tracks. By combining or emphasising various tracks, the person editing the final release of this recording can work all sorts of magic to get a more pleasing and inspiring result.

> 编辑包括许多跟踪的混合(组合音频波)。例如，在录制管弦乐队的过程中，可能会有 20 个或更多的麦克风分散在一起录制不同的曲目。通过组合或强调各种曲目，编辑这段录音的最终版本的人可以发挥各种魔力，以获得更令人愉悦和鼓舞人心的结果。

### Compression

_Compression_ of an audio waveform allows better quality audio on transmission media than other degrade reproduction. Recordings of old time AM broadcast and movies from the 1930s and 1940s provide a prime example. Voices especially sound tinny, less full and rich than they do in modern broadcast and movie audio. In radio audio, this tininess was emphasized by audio-limiting circuits designed to protect transmitters from over-modulation damage as well as preventing distortion. In other words, an announcer shouting on air could blow an expensive transmitter and shut down the station.

> _音频波形的压缩允许传输媒体上的音频质量优于其他降级再现。20 世纪 30 年代和 40 年代的旧 AM 广播和电影录音就是一个很好的例子。声音特别微弱，不像现代广播和电影音频那样饱满和丰富。在无线电音频中，设计用于保护发射机免受过度调制损坏以及防止失真的音频限制电路强调了这种微小性。换言之，播音员在空中喊话可能会炸掉昂贵的发射机并关闭电台。

Pioneering effects, such as the CBS radio network’s Audimax system in the 1960s, changed that by making earlier attempts at compression practical. Compression techniques allow reproduction of voice and music more accurately and distortion free.

> 开创性的效果，如 20 世纪 60 年代 CBS 广播网的 Audimax 系统，通过使早期的压缩尝试变得实用而改变了这一点。压缩技术使声音和音乐的再现更准确、无失真。

Two types of compression are popular and available in software (such as Audacity) for the Raspberry Pi:

> Raspberry Pi 的软件(如 Audacity)中流行两种压缩类型：

- **Audio compression:** Reduces the amount of data in an audio waveform to effect accurate reproduction via CD, MP3, Internet radio and so forth with little or no loss of quality

> -**音频压缩：**减少音频波形中的数据量，以通过 CD、MP3、互联网收音机等实现准确的再现，同时几乎不损失质量

- **Dynamic range compression:** Reduces the difference between loud and quiet, again resulting in accurate reproduction

> -**动态范围压缩：**减少了响亮和安静之间的差异，再次实现精确再现

### Recording with Effects

Features that enable you to modify all or parts of sound files are called _effects._ Effects add ambience, excitement, fullness and other changes to sounds that do not exist in the original recording. Effects can turn drab reality into a magical virtual soundscape. You can even use more than one effect on a sound. Some standard examples of effects include:

> 允许您修改所有或部分声音文件的功能称为*effects。*效果为原始录音中不存在的声音添加了氛围、兴奋、饱满和其他变化。效果可以将单调的现实变成神奇的虚拟声景。你甚至可以在一个声音上使用多个效果。效果的一些标准示例包括：

- **Echo:** Gives the effect of sound echoing off the walls of a large hall or cavern

> -**回声：**产生声音在大厅或洞穴墙壁上回响的效果

- **Chorus:** Adds a very slight delay to make one recorded voice sound like more than one person or make a group of recorded voices sound like many more

> -**合唱：**添加非常轻微的延迟，使一个录制的声音听起来像多个人，或使一组录制的声音看起来像多个人

- **Pitch shift:** Moves the pitch of music or other sounds up or down; for example, you could copy a track, move the pitch of the copy up or down an octave and mix it with the original track for an interesting effect. You can also change the pitch of an actor’s voice to use for a cartoon character. Pitch shift can also be used to change the pitch of an out-of-tune singer so that their voice is in tune.

> -**音高偏移：**向上或向下移动音乐或其他声音的音高；例如，您可以复制一个音轨，将副本的音高向上或向下移动一个八度，并将其与原始音轨混合以获得有趣的效果。你也可以改变演员声音的音调，以用于卡通人物。音调变换也可以用来改变走调歌手的音调，使他们的声音保持一致。

> ---

> [!NOTE]

Some karaoke machines use pitch shift in real time to assist singers, making them sound better than they actually are. Called _autotune_, this technique is common in pop culture these days and is even used by professional singers.

> 一些卡拉 OK 机使用实时音调变换来辅助歌手，使他们的声音比实际情况更好。这种技术被称为 `自动调谐` ，如今在流行文化中很常见，甚至被职业歌手使用。

- **Robotic voice effects:** Turns the human voice into a mechanical synthesised version. Add a pitch shift effect for a scary result

> -**机器人语音效果：**将人声转换为机械合成版本。为可怕的结果添加音调变换效果

- **Time stretching:** Increases or decreases speed of an audio signal without affecting its pitch

> -**时间拉伸：**在不影响音调的情况下增加或降低音频信号的速度

Hundreds more effects exist, either in audio editing software or available to be downloaded and added as needed. Figure 11-2 shows an example of Adobe Audition, which is part of the Creative Cloud suite and offers extensive sound editing capabilities.

> 还有数百种效果存在，无论是在音频编辑软件中，还是可以根据需要下载和添加。图 11-2 显示了 Adobe Audition 的一个示例，它是 Creative Cloud 套件的一部分，提供了广泛的声音编辑功能。

![[FIGURE 11-2:](#14_9781119183938-ch11.xhtml#rc11-fig-0002) Adobe Audition professional sound editing program showing some of the many effects available](./media/images/9781119183938-fg1102.png)

### Encoding and Decoding Information for Communication

Voice recognition is an example of encoding information for controlling software and computers. For example, when you say `Stop` and a program on a computer ends, it’s because your word is compared against an encoded version of the word _stop_ and recognized, and the command is initiated. (Naturally the computer must have a microphone attached and software for identifying and comparing words to their encoded versions.)

> 语音识别是用于控制软件和计算机的编码信息的示例。例如，当你说 `停止` ，计算机上的一个程序结束时，这是因为你的单词与单词 *Stop* 的编码版本进行了比较并被识别，命令被启动。(当然，计算机必须连接麦克风和软件，用于识别单词并将其与编码版本进行比较。)

Sensors, industrial instruments, satellites and thousands of other devices on the Internet of Things use variously modulated audio signals to accept and return information. These audio signals are not necessarily words but various commands and other data encoded into audio waveforms. _Decoding_ is the process by which the information is extracted and acted on.

> 传感器、工业仪器、卫星和物联网上成千上万的其他设备使用各种调制的音频信号来接收和返回信息。这些音频信号不一定是单词，而是编码成音频波形的各种命令和其他数据_解码是提取和处理信息的过程。

Broadcast radio and TV stations add modulated sound waves to their radio frequency carriers to send out voice and music. The radio waveform is encoded with the program material. Your receiver decodes it and converts the voice and music to sound for your enjoyment.

> 广播电台和电视台在其射频载波上添加调制声波，以发送语音和音乐。无线电波形与节目材料一起编码。您的接收器将其解码，并将语音和音乐转换为声音，供您享受。

Here’s another example: if you’ve ever seen an amateur radio operator sending Morse code, that’s sound manipulation, resulting in _dits_ and _dahs_ reproduced after being sent through the air to another radio ham’s receiver and a message being passed hundreds or thousands of miles. The same is true of more sophisticated methods of communications like radioteletype (RTTY) and technically cutting-edge advances like JT65 or JT9 (low signal modes allowing consistent communications between continents with only a few watts), as shown in Figure 11-3.

> 这是另一个例子：如果你曾经见过业余无线电操作员发送莫尔斯电码，那就是声音操纵，导致在通过空中发送到另一个无线电爱好者的接收器后再现的 *dits* 和 *dhs*，并将消息传递数百或数千英里。如图 11-3 所示，无线电报(RTTY)等更复杂的通信方法和 JT65 或 JT9(低信号模式，只需几瓦就能实现大陆之间的一致通信)等尖端技术进步也是如此。

![[FIGURE 11-3:](#14_9781119183938-ch11.xhtml#rc11-fig-0003) A radio ham in North Carolina contacts another in Hungary using a computer to convert typed messages into digital waveforms which modulate a radio signal received and decoded by the computer of the ham in Europe.](./media/images/9781119183938-fg1103.png)

The multitude of sound and signal processing applications continues to grow rapidly.

> 声音和信号处理应用的数量继续快速增长。

## 1-Bit DAC

DAC stands for digital-to-analog converter and ADC stands for analog-to-digital converter. DAC is also known as a bitstream converter.

> DAC 代表数模转换器，ADC 代表模数转换器。DAC 也称为位流转换器。

Earlier in the chapter we discussed the advantages of digital audio over analog, but this does not mean digital audio has totally replaced analog audio. Why? After all, you can plug headphones into the 3.5mm audio jack on the Raspberry Pi board and hear music. Headphones are transducers that convert recorded analog waveforms to sound waves (which are vibrations in the air) and flings them against your eardrums. To make this happen, some kind of digital-to-analog conversion has to happen on the Raspberry Pi board. If you want to use both video and audio via the audio jack on a Raspberry Pi 2 or B+, you need a connector like the one shown in Figure 11-4.

> 在本章的前面，我们讨论了数字音频相对于模拟音频的优势，但这并不意味着数字音频已经完全取代了模拟音频。为什么？毕竟，您可以将耳机插入复盆子 Pi 板上的 3.5mm 音频插孔并收听音乐。耳机是将记录的模拟波形转换为声波(即空气中的振动)并将其抛向耳膜的传感器。为了实现这一点，必须在复盆子 Pi 板上进行某种数模转换。如果您想通过复盆子 Pi 2 或 B+ 上的音频插孔同时使用视频和音频，则需要一个如图 11-4 所示的连接器。

---

> [!NOTE]

The type of connector shown in [Figure 11-4](#14_9781119183938-ch11.xhtml#c11-fig-0004) includes provision for video as well as audio, whereas the audio jack on the older Model B is a standard stereo configuration with the composite video jack separate.

> [图 11-4](#14_9781119183938-ch11.xhtml#c11-fig-0004) 中所示的连接器类型包括视频和音频，而旧型号 B 上的音频插孔是标准立体声配置，复合视频插孔分开。

Prior to Raspberry Pi 2, the stereo jack was not the `3 pole` variety, and it was used only for audio. But there’s good news: the plug in [Figure 11-4](#14_9781119183938-ch11.xhtml#c11-fig-0004) is 4-pole (TRRS or Tip, Ring, Ring, Sleeve), but the conventional 3-pole stereo plug (such as the one on headphones) still works! Only when you’re using video does this plug require a 4-pole connector.

> 在树莓派 2 之前，立体声插孔不是 `三极` 类型，它只用于音频。但有一个好消息：插头[图 11-4](#14_9781119183938-ch11.xhtml#c11-fig-0004) 是 4 极(TRRS 或 Tip、Ring、Ring 和 Sleeve)，但传统的 3 极立体声插头(如耳机上的插头)仍然有效！只有在使用视频时，此插头才需要 4 极连接器。

![[FIGURE 11-4:](#14_9781119183938-ch11.xhtml#rc11-fig-0004) Connections on a 3.5mm plug to match the Raspberry Pi](./media/images/9781119183938-fg1104.png)

Bear in mind that a computer costing around £30 retail might not have the highest possible quality of audio. The quality isn’t terrible, though, and the HDMI connector supplies very acceptable sound. The audio from the 3.5mm stereo audio jack, however, does not have as much quality. What is the difference between the two? The 3.5mm jack outputs analog audio and the HDMI jack outputs digital audio.

> 请记住，一台零售价约为 30 英镑的电脑可能没有最高的音频质量。不过，质量并不可怕，HDMI 连接器提供了非常可接受的声音。然而，来自 3.5 毫米立体声音频插孔的音频质量却没有那么高。两者之间有什么区别？3.5 毫米插孔输出模拟音频，HDMI 插孔输出数字音频。

The Raspberry Pi’s onboard DAC conversion is generated by the Pulse Width Modulation (PWM) module and is 1-bit. This is not bad. Many CD players, boom boxes, and other sound-producing consumer electronic devices use 1-bit DACs (or the equivalent) with great results. The 1-bit DAC samples audio at several times its actual rate, converting with quality similar to 16 to 20 bits; in the Raspberry P, however, it’s stated as being equivalent to only 11 bit. 1-bit DAC is also cheap, which is something important to manufacturers of low-cost units.

> 复盆子 Pi 的板载 DAC 转换由脉宽调制(PWM)模块生成，为 1 位。这还不错。许多 CD 播放器、音箱和其他产生声音的消费电子设备使用 1 位 DAC(或同等产品)，效果非常好。1 位 DAC 以其实际速率的几倍对音频进行采样，以类似于 16 至 20 位的质量进行转换；然而，在复盆子 P 中，它被称为仅相当于 11 位。1 位 DAC 也很便宜，这对于低成本设备的制造商来说很重要。

An ADC measures analog audio amplitudes many times each second, storing those as numbers in a file. The most common format used for this in computers is pulse code modulation (PCM). The digital-to-analog conversion DAC, such as the PWM emulation of 1-bit DAC on the Raspberry Pi board, samples a PCM audio file and reconstructs the analog waveform according to the numeric data in the PCM file.

> ADC 每秒多次测量模拟音频振幅，并将其作为数字存储在文件中。计算机中最常用的格式是脉冲编码调制(PCM)。数模转换 DAC(如 Raspberry Pi 板上 1 位 DAC 的 PWM 仿真)对 PCM 音频文件进行采样，并根据 PCM 文件中的数字数据重建模拟波形。

To simplify, a soundwave varies continuously in amplitude over time. The ADC rapidly measures the wave many times a second, recording the amplitude of the wave each time. These points then are encoded into a digital pulse width waveform. When that PWM waveform is decoded, the original analog waveform is reconstruction and can drive a speaker or headphone thus playing the original content.

> 为了简化，声波的振幅随时间不断变化。ADC 每秒快速测量多次波，记录每次波的振幅。然后将这些点编码成数字脉宽波形。当该 PWM 波形被解码时，原始模拟波形被重建，并且可以驱动扬声器或耳机，从而播放原始内容。

The problem here is that you may have beautiful music produced in a studio and turned into a 24-bit audio file. Although the 1-bit DAC reads the file okay, it’s reconstructing the analog waveform of the music based on its overrate sampling technique which is 11-bit (in the Raspberry Pi’s case) to 20-bit, instead of the file’s native 24-bit quality. Small distortions due to this faster sampling might also creep in.

> 这里的问题是，你可能在录音室中制作了美妙的音乐，并将其转换为 24 位音频文件。尽管 1 位 DAC 读取文件正常，但它正在基于其超高速采样技术重建音乐的模拟波形，该技术为 11 位(在树莓派的情况下)到 20 位，而不是文件的原始 24 位质量。由于这种更快的采样，小的失真也可能会慢慢出现。

---

> [!NOTE]

The term _overrate_ in the preceding paragraph is significant for bandwidth-limited waveforms such as those produced by the type of DAC described earlier. There is a term in signal processing called the _Nyquist rate_, which is twice the highest frequency in a waveform. Theoretically, at least, such a waveform can be more accurately decoded if sampled above the Nyquist rate, thus reducing noise and distortion. This over-rate technique is how the equivalent 11-bit rate is achieved from a 1-bit DAC encoded file.

> 前一段中的术语 `覆盖` 对于带宽受限的波形(如前面描述的 DAC 类型产生的波形)非常重要。在信号处理中有一个术语叫做奈奎斯特率，它是波形中最高频率的两倍。至少从理论上讲，如果采样高于奈奎斯特速率，这样的波形可以被更准确地解码，从而减少噪声和失真。这种过速率技术是如何从 1 位 DAC 编码文件获得等效的 11 位速率的。

When using the Raspberry Pi as a media centre driving high-end amplifiers and speaker systems, you want the best sound possible. The Raspberry Pi can do it, but you need to hang a higher quality DAC from it, which is a cheap and easy solution. With a 24-bit DAC, you will get more clarity and depth of sound. The difference is subtle, but it is definitely there.

> 当使用复盆子 Pi 作为驱动高端放大器和扬声器系统的媒体中心时，您需要尽可能最佳的声音。树莓派可以做到这一点，但你需要挂上一个更高质量的 DAC，这是一个廉价而简单的解决方案。使用 24 位 DAC，您将获得更清晰和深度的声音。差异是微妙的，但它确实存在。

So, how does the Raspberry Pi communicate with this better DAC? It happens via a sound transport protocol referred to as I<sup>2</sup>S.

> 那么，树莓派如何与这个更好的 DAC 通信？它通过称为 I<sup>2</sup>S 的声音传输协议发生。

## I<sup>2</sup>S

_I<sup>2</sup>S_—which is short for Inter-IC Sound, Interchip Sound or IIS—is a type of serial bus interface standard that connects digital audio devices to one another. As an example, I<sup>2</sup>S connects the Raspberry Pi to an external DAC.

> _I<sup>2</sup>S_-是 Inter-IC Sound、Interchip Sound 或 IIS 的缩写，是一种将数字音频设备彼此连接的串行总线接口标准。例如，I<sup>2</sup>S 将复盆子 Pi 连接到外部 DAC。

But wait. You may have noticed we have nothing labelled `I<sup>2</sup>S Connector` on the Raspberry Pi board. We could use one of the USB ports for outputting PCM audio to a DAC, but that can introduce distortion. The best solution is to use the general purpose input output (GPIO) pins on the Raspberry Pi board. Also, it’s best to use the shortest path possible. Consequently, external DAC boards for the Raspberry Pi plug directly into the GPIO pins.

> 但请稍候。您可能已经注意到，复盆子 Pi 板上没有任何标有 `I<sup>2</sup>S 连接器` 的内容。我们可以使用一个 USB 端口将 PCM 音频输出到 DAC，但这会导致失真。最好的解决方案是使用 Raspberry Pi 板上的通用输入输出(GPIO)引脚。此外，最好使用尽可能短的路径。因此，Raspberry Pi 的外部 DAC 板直接插入 GPIO 引脚。

You might want to check out the following list of DAC boards, all of which cost less than £25:

> 您可能需要查看以下 DAC 板列表，所有这些板的成本都低于 25 英镑：

- **SainSmart HIFI DAC Audio Sound Card Module for Raspberry Pi 2** ([`www.sainsmart.com/sainsmart-hifi-dac-audio-sound-card-module-i2s-interface-for-raspberry-pi-2-b.html`](http://www.sainsmart.com/sainsmart-hifi-dac-audio-sound-card-module-i2s-interface-for-raspberry-pi-2-b.html)): Plugs directly to the Raspberry Pi board.

> -**Raspberry Pi 2 的 SainSmart HIFI DAC 音频声卡模块**([`www.SainSmart.com/SainSmart-HIFI-DAC-Audio-Sound-Card-Module-i2s-interface-for-Raspberry-Pi-2-b.html`](http://www.sainsmart.com/sainsmart-hifi-dac-audio-sound-card-module-i2s-interface-for-raspberry-pi-2-b.html))：直接插入 Raspberry Pi 板。

- **HiFiBerry DAC+** ([`www.hifiberry.com/dac/`](http://www.hifiberry.com/dac/)): Plugs into A, B, B+, and 2, but it may not work with some older As and Bs.

> -**HiFiBerry DAC+**([`www.HiFiBerry.com/DAC/`](http://www.hifiberry.com/dac/))：可插入 A、B、B+ 和 2，但可能无法与一些旧的 A 和 B 一起使用。

- **Eleduino HIFI DAC Audio Sound Card Module** ([`http://www.eleduino.com/HIFI-DAC-Audio-Sound-Card-Module-I2S-interface-for-Raspberry-pi-B-Raspberry-Pi-2-Model-B-p10546.html`](http://www.eleduino.com/HIFI-DAC-Audio-Sound-Card-Module-I2S-interface-for-Raspberry-pi-B-Raspberry-Pi-2-Model-B-p10546.html))

> -**Eleduino HIFI DAC 音频声卡模块**([`http://www.eleduino.com/HIFI-DAC-Audio-Sound-Card-Module-I2S-interface-for-Raspberry-pi-B-Raspberry-Pi-2-Model-B-p10546.html`](http://www.eleduino.com/HIFI-DAC-Audio-Sound-Card-Module-I2S-interface-for-Raspberry-pi-B-Raspberry-Pi-2-Model-B-p10546.html))

- **Arducam HIFI DAC Audio Sound Card Module** ([`http://www.amazon.com/Arducam-Audio-Module-Interface-Raspberry/dp/B013JZI3DS`](http://www.amazon.com/Arducam-Audio-Module-Interface-Raspberry/dp/B013JZI3DS))

> -**Arducam HIFI DAC 音频声卡模块**([`http://www.amazon.com/Arducam-Audio-Module-Interface-Raspberry/dp/B013JZI3DS`](http://www.amazon.com/Arducam-Audio-Module-Interface-Raspberry/dp/B013JZI3DS))

---

> [!NOTE]

You can find other options for DAC boards by searching for `Raspberry Pi DAC` .

> 您可以通过搜索 `树莓派 DAC` 找到 DAC 板的其他选项。

## Raspberry Pi Sound Input/Output

The Raspberry Pi supplies two types of connector for getting sound into and out of it: the audio output jack and the HDMI jack.

> 复盆子 Pi 提供两种类型的连接器，用于将声音输入和输出：音频输出插孔和 HDMI 插孔。

### Audio Output Jack

The Raspberry Pi board provides a standard 3.5mm audio stereo jack. Here you can plug in headphones, powered speakers or anything else that takes and plays audio input and matches the connections of the jack.

> 复盆子 Pi 板提供标准 3.5 毫米音频立体声插孔。在这里，您可以插入耳机、电动扬声器或任何其他接收和播放音频输入并与插孔连接相匹配的设备。

A limitation of this output is the quality of sound. The audio out from this connector, as specs state, is 11-bit. (For truly good sounding music you want 16-bit or 24-bit.)

> 这种输出的一个限制是声音的质量。按照规格，从该连接器输出的音频为 11 位。(对于真正好听的音乐，您需要 16 位或 24 位。)

No worries, though: like other Raspberry Pi limitations, solutions abound. For example, you can add a generic USB/audio adapter. One of these adapters puts out better sound and allows for microphone _input_ as well. This lets you use the Raspberry Pi as a voice or music recorder, or teach it to work via voice commands, and so forth. Alternatively, as mentioned earlier in the chapter, an external DAC board is the yellow brick road to high-end quality sound.

> 不过，不用担心：像其他树莓派的局限性一样，解决方案比比皆是。例如，您可以添加通用 USB/音频适配器。其中一个适配器可以发出更好的声音，并允许麦克风输入。这让你可以将树莓派用作语音或音乐录音机，或通过语音命令等方式教它工作。或者，如本章前面所述，外部 DAC 板是通往高端音质的黄砖之路。

### HDMI

HDMI was developed in the early 2000s as a method of transferring high-quality video and audio to playback devices. A number of versions exist, but they all use the same cable and connectors. The Raspberry Pi includes an HDMI connector on its board.

> HDMI 是在 2000 年代早期开发的一种将高质量视频和音频传输到播放设备的方法。存在多种版本，但它们都使用相同的电缆和连接器。复盆子 Pi 在其板上包括 HDMI 连接器。

---

> [!NOTE]

HDMI is a proprietary interface owned by a consortium of large flat-screen TV manufacturers. The development of HDMI technology paralleled and contributed to the rise of these big entertainment devices. Big screens require better picture quality, and home theatre sound systems require better audio.

> HDMI 是一个由大型平板电视制造商组成的联盟拥有的专有接口。HDMI 技术的发展与这些大型娱乐设备的兴起并行，并对其做出了贡献。大屏幕需要更好的画面质量，家庭影院音响系统需要更好的音频。

There’s nothing as fine as a nice big display that shows the colourful graphic user interface (GUI) of the Raspberry Pi and enables you to watch videos, play games and do all the stuff you expect a computer to do. The best solution involves HDMI, and here are two of the advantages of using HDMI output:

> 没有什么比一个漂亮的大屏幕更好的了，它显示了树莓派丰富多彩的图形用户界面(GUI)，并使您能够观看视频、玩游戏和做您期望计算机做的所有事情。最佳解决方案涉及 HDMI，以下是使用 HDMI 输出的两个优点：

- HDMI allows the transfer of video and audio from an HDMI-compliant display controller (think Raspberry Pi here) to compatible computer monitors, projectors, digital TVs or digital audio devices.

> -HDMI 允许将视频和音频从 HDMI 兼容的显示控制器(此处为 Raspberry Pi)传输到兼容的计算机显示器、投影仪、数字电视或数字音频设备。

- HDMI’s higher quality provides a marked advantage over composite video (such as what comes out of the yellow or sometimes black connector on the Raspberry Pi board). This also provides a display that’s much easier on the eyes and provides higher resolution instead of composite video’s noisy and sometimes distorted video and/or audio.

> -HDMI 的更高质量提供了优于复合视频的显著优势(例如 Raspberry Pi 板上的黄色或有时黑色连接器)。这也提供了一种更容易在眼睛上看到的显示器，并提供了更高的分辨率，而不是复合视频的噪声和有时失真的视频和/或音频。

---

> [!WARING]

It is important to know that HDMI-to-HDMI connections include _both_ video and audio. For connections that convert HDMI to DVI (Digital Video Interface) or VGA (Video Graphics Array), only video goes through the connection. Your options for audio include a separate audio cable from the audio out port of the Raspberry Pi. Alternatively, some adapters recommended earlier in this chapter have audio ports. You still need to run an audio cable from the converter’s connector to the audio input on the monitor or to separate speakers.

> 重要的是要知道 HDMI 到 HDMI 的连接包括视频和音频。对于将 HDMI 转换为 DVI(数字视频接口)或 VGA(视频图形阵列)的连接，只有视频通过连接。您的音频选项包括从复盆子 Pi 的音频输出端口连接单独的音频电缆。或者，本章前面推荐的一些适配器具有音频端口。您仍然需要将音频电缆从转换器的连接器连接到显示器上的音频输入或连接到单独的扬声器。

Remember, audio coming from the HDMI output of the Raspberry Pi is better quality than from the 3.5mm audio output jack. Although it might seem like a good idea to plug in nice computer speakers that include a built-in amplifier, or any other powered speaker, the best method employs the Raspberry Pi’s onboard I<sup>2</sup>S to a separate DAC.

> 请记住，来自树莓派 HDMI 输出的音频比来自 3.5mm 音频输出插孔的音频质量更好。尽管插入内置放大器或任何其他电源扬声器的漂亮计算机扬声器似乎是个好主意，但最好的方法是将树莓派的板载 I<sup>2</sup>s 连接到单独的 DAC。

## Sound on the Raspberry Pi

Do not mistake our suggestion of using an external DAC for a complaint that the Raspberry Pi has bad sound. It does not. It has _great_ sound features. In this section, we look at the Raspberry Pi’s onboard sound hardware and then see how this fantastic little computer enables us to manipulate sound in all sorts of good ways.

> 不要将我们使用外部 DAC 的建议误认为 Raspberry Pi 声音不好。事实并非如此。它具有巨大的声音功能。在本节中，我们将看看树莓派的板载声音硬件，然后看看这台神奇的小电脑是如何让我们以各种好的方式操纵声音的。

### Raspberry Pi Sound on Board

As of the Raspberry Pi 2, all of the Raspberry Pi 2’s magic occurs in the Broadcom BM2535 system-on-a-chip (SoC). Among other things, this chip provides the following three things that provide the Raspberry Pi 2’s audio features:

> 从树莓派 2 开始，树莓派的所有魔力都出现在 Broadcom BM2535 芯片系统(SoC)中。除此之外，该芯片还提供以下三项功能，以提供树莓派 2 的音频功能：

- DAC conversion providing left and right stereo analog audio for the 3.5mm jack

> -DAC 转换，为 3.5mm 插孔提供左右立体声模拟音频

- HDMI digital audio

> -HDMI 数字音频

- Support of I<sup>2</sup>S audio transport

> -支持 I<sup>2</sup>S 音频传输

Now that you know where the magic happens, it’s time to do something practical, such as editing audio.

> 现在你知道了神奇的地方，是时候做一些实际的事情了，比如编辑音频。

### Manipulating Sound on the Raspberry Pi

As mentioned in [Chapter 8](#11_9781119183938-ch08.xhtml), Raspbian (a version of Debian Linux optimised for the Raspberry Pi) is a good starting point for installing as an operating system. The audio editing techniques in this section work in most Linux distros on the Raspberry Pi, but we have used Raspbian for our examples.

> 如[第 8 章](#11_9781119183938-ch08.xhtml)中所述，Raspbian(为复盆子 Pi 优化的 Debian Linux 版本)是作为操作系统安装的良好起点。本节中的音频编辑技术适用于 Raspberry Pi 上的大多数 Linux 发行版，但我们使用了 Raspbian 作为示例。

#### Selecting Audio Devices

Like many devices with powerful modern operating systems, the Raspberry Pi recognises several methods of achieving most goals. For example, there’s more than one way to select the audio device.

> 像许多具有强大的现代操作系统的设备一样，树莓派认识到实现大多数目标的几种方法。例如，选择音频设备的方法不止一种。

The Raspberry Pi comes with two methods of audio playback. The first is analog stereo with digital files converted to work with headphones or speakers. The second is HDMI, which features higher-quality digital sound. A 4-pole connector is supplied for analog audio output and there’s also an HDMI connector for cabling to TVs, stereo systems and other HDMI-enabled devices.

> 树莓派有两种音频播放方法。第一种是模拟立体声，将数字文件转换为耳机或扬声器。第二个是 HDMI，它具有更高质量的数字声音。4 极连接器用于模拟音频输出，还有一个 HDMI 连接器用于连接电视、立体声系统和其他支持 HDMI 的设备。

The default output method is to use the 4-pole 3.5mm socket on the Raspberry Pi board (video output possible in addition to sound). As explained earlier in this chapter, using a standard 3-pole mini stereo plug, such as those on the end of headphones or computer speakers, works by design also, so you can use any powered computer speakers and your Raspberry Pi will sound good.

> 默认输出方法是使用复盆子 Pi 板上的 4 极 3.5mm 插座(除了声音外，还可以输出视频)。如本章前面所述，使用标准的 3 极迷你立体声插头，如耳机或电脑扬声器末端的插头，也可以通过设计实现，因此您可以使用任何带电源的电脑扬声器，您的复盆子 Pi 将听起来很好。

#### MAKING A PERMANENT CHANGE

Let’s say you’re using the Raspberry Pi as an entertainment centre controller hooked to a TV and/or stereo system. In that case, manually selecting HDMI after booting the Raspberry Pi would become a pain. Here’s the solution for that:

> 假设你正在使用树莓派作为连接到电视和/或立体声系统的娱乐中心控制器。在这种情况下，启动 Raspberry Pi 后手动选择 HDMI 将成为一个难题。以下是解决方案：

1. Open the command-line terminal (usually the little TV-like icon with a black screen). 2. Type the command `sudo raspi-config`. (The `sudo` means super user do, giving you permission to change configuration—in this case the way the board boots up.) 3. After the Raspberry Pi Software Configuration Tool screen appears (see Figure 11-5), use the down arrow key and select 9 Advanced Options. Press Enter. 4. Select A9 Audio. 5. On the Choose the Audio Output screen, select 2 Force HDMI. 6. Click OK and then click Finish. 7. Reboot the Raspberry Pi.

> 1.打开命令行终端(通常是带有黑色屏幕的类似电视的小图标)。2.键入命令 `sudo raspi config` 。( `sudo` 意味着超级用户做，在这种情况下，您可以按照主板启动的方式更改配置。)3。出现 Raspberry Pi Software Configuration Tool(树莓派软件配置工具)屏幕后(见图 11-5)，使用向下箭头键并选择 9 Advanced Options(高级选项)。按 Enter 键。4.选择 A9 Audio(A9 音频)。5.在选择音频输出屏幕上，选择 2 强制 HDMI。6.单击 `确定` ，然后单击 `完成` 。7.重新启动树莓派。

![[FIGURE 11-5:](#14_9781119183938-ch11.xhtml#rc11-fig-0005) Raspberry Pi Software Configuration Tool](./media/images/9781119183938-fg1105.png)

From now on, the Raspberry Pi boots up with the HDMI as the default audio output device.

> 从现在起，树莓派将 HDMI 作为默认音频输出设备启动。

#### SELECTING OUTPUT MANUALLY

Manual selection of how you want sound output from a Raspberry Pi is easy. To begin simply, we can use the omxplayer utility, which is included in Raspbian. This player not only plays standard audio digital file formats such as `.wav` and `.mp3` but it also plays video formats including `.mp4` and `.avi`.

> 手动选择 Raspberry Pi 的声音输出方式很简单。首先，我们可以使用 Raspbian 中包含的 omxplayer 实用程序。该播放器不仅播放标准音频数字文件格式，如 `.wav` 和 `.mp3` ，还播放视频格式，包括 `.mp4` 和 `.avi` 。

---

> [!NOTE]

.mp3` is a very popular format for music, but it’s a proprietary format. To play it, you’ll need to install an encoder/decoder, such as lame. It’s free. Install it using the command

```
sudo apt-get install lame
```

Then omxplayer plays MP3s without further effort on your part.

> 然后，omxplayer 播放 MP3，而无需您进一步努力。

The omxplayer utility has no GUI capability, so you use it in the terminal with command-line instructions. For example, you invoke omxplayer with only the name of a digital file. The command

> omxplayer 实用程序没有 GUI 功能，因此您可以在带有命令行指令的终端中使用它。例如，您只使用数字文件的名称调用 omxplayer。命令

```

omxplayer Beethoven_Ode_To_Joy.wav

> omxplayer贝多芬_颂歌_欢乐.wav
```

plays the file on the default device, depending on what you’ve set in the procedure described in the preceding section.

> 在默认设备上播放文件，具体取决于在上一节所述过程中设置的内容。

The command

> 命令

```
omxplayer -local Beethoven_Ode_To_Joy.wav
```

produces output to the 3.5mm audio connector and the command

> 向 3.5mm 音频接口和命令生成输出

```
omxplayer -hdmi Beethoven_Ode_To_Joy.wav
```

produces output to the HDMI connector.

> 产生到 HDMI 连接器的输出。

The omxplayer utility contains many other options. Type its name in the terminal without parameters to get a list of these.

> omxplayer 实用程序包含许多其他选项。在不带参数的终端中键入其名称以获得这些参数的列表。

#### Playing Audio

A number of media players—software that plays both audio and video files—exist for the Raspberry Pi. These allow operation from the desktop in your operating system. On Raspbian, a good starting point is XiX. You can download the Linux ARM version and installation instructions at [`www.xixmusicplayer.org`](http://www.xixmusicplayer.org/).

> 树莓派有许多播放音频和视频文件的媒体播放器软件。它们允许从操作系统的桌面进行操作。在 Raspbian，一个好的起点是 XiX。您可以从[`www.xixmusicplayer.org`]下载 Linux ARM 版本和安装说明([http://www.xixmusicplayer.org/)](http://www.xixmusicplayer.org/)).

---

> [!NOTE]

Media players should not be confused with media centre software. The latter does much more in setting up libraries and all the other functions expected of a media centre in selecting and serving entertainment. Some of the major software packages for PC and Mac also have versions that run on the Raspberry Pi, such as XBMC and Kodi.

> 媒体播放器不应与媒体中心软件混淆。后者在建立图书馆以及媒体中心在选择和提供娱乐方面的所有其他职能方面做得更多。PC 和 Mac 的一些主要软件包也有在树莓派上运行的版本，如 XBMC 和 Kodi。

As previously mentioned, the Raspberry Pi is certainly capable of better sound than it outputs through the 3.5mm audio connector or even the HDMI output. An inexpensive (and we mean _really inexpensive_) method involves adding a USB sound card (which is less than £7 from major online retailers). Many of these have microphone input in addition to speaker/headphone output. They are similar to the sound cards in PCs and have many of the same features, albeit in a smaller package.

> 如前所述，树莓派当然能够比通过 3.5mm 音频连接器甚至 HDMI 输出输出的声音更好。一种便宜(我们的意思是非常便宜)的方法包括添加一个 USB 声卡(从主要的在线零售商那里购买不到 7 英镑)。除扬声器/耳机输出外，其中许多还具有麦克风输入。它们与 PC 中的声卡相似，具有许多相同的功能，尽管包装较小。

These inexpensive USB sound card dongles do not require drivers. To install one, power down your Raspberry Pi, plug the dongle into a USB receptacle, and then boot up the Raspberry Pi.

> 这些廉价的 USB 声卡加密狗不需要驱动程序。要安装一个，请关闭树莓派的电源，将加密狗插入 USB 插座，然后启动树莓派。

You also need to switch the audio output device to the USB sound card. You can’t use the omxplayer utility for that because it currently doesn’t support USB sound. Instead, use a player called aplay. Like omxplayer, aplay is controlled through the command line using a terminal utility.

> 您还需要将音频输出设备切换到 USB 声卡。你不能使用 omxplayer 实用程序，因为它目前不支持 USB 声音。相反，使用名为 aplay 的播放器。与 omxplayer 一样，aplay 是使用终端实用程序通过命令行控制的。

Use these steps to get aplay on Raspbian:

> 使用以下步骤获取 Raspbian 上的应用程序：

1. Type the following in the command line:

> 1.在命令行中键入以下内容：

`sudo apt-get install aplay

> `sudo apt-get 安装应用程序

2. Get the device number for your USB sound card by typing the following on the command line:

> 2.通过在命令行中键入以下内容获取 USB 声卡的设备编号：

`aplay -l

> ` 应用程序-l

---

> [!NOTE]

The parameter in that command is not the digit one (1) but a lowercase L (l).

> 该命令中的参数不是数字 1，而是小写的 L(L)。

Look for the device number of the USB sound card and make a

> 查找 USB 声卡的设备编号，并制作

> [!NOTE]
> of it. The listing on our test Raspberry Pi 2 shows several lines, but the following two show the sound devices:

`card 0: ALSA [bcm2835 ALSA], device 1: bcm2835 ALSA [bcm2835 IEC958/HDMI] ` card 1: Device [C-Media USB Audio Device], device 0: USB Audio [USB Audio]

The first, `card 0`, has 2835 in it; that’s the number of the Broadcom SoC, so we can deduce it’s the default sound output that came as part of our Raspberry Pi. The second, `card 1`, tells us it’s a C-Media USB Audio Device. 3. Get the device number, which is a little confusing because `card 1` is considered _device 0_ (because it’s the second card going to the first device—computer cards, devices, disks and so on often start numbering at 0 instead of 1). With that information, you’re ready to play music with your headphones or powered speakers plugged into the USB dongle itself. 4. Find the PCM method for your USB sound card by typing the following command (this time using an uppercase `L` ):

> 第一张 `卡片 0` 中有 2835 张；这是 Broadcom SoC 的编号，因此我们可以推断它是作为复盆子 Pi 的一部分的默认声音输出。第二张 `卡 1` 告诉我们这是一个 C-Media USB 音频设备。3.获取设备编号，这有点令人困惑，因为 `卡 1` 被视为 *device0*(因为它是第一个设备的第二个卡，计算机卡、设备、磁盘等通常从 0 开始编号，而不是 1)。有了这些信息，您就可以使用插入 USB 加密狗本身的耳机或电动扬声器播放音乐了。4.通过键入以下命令(这次使用大写 `L` )查找 USB 声卡的 PCM 方法：

`aplay -L

---

> [!NOTE]

PCM is the format generated by the Raspberry Pi when converting a digital file into an analog sound output. You are going to use the `-D` option to specify a PCM method.

> PCM 是复盆子 Pi 在将数字文件转换为模拟声音输出时生成的格式。您将使用 `-D` 选项指定 PCM 方法。

You see several lines of output. Look at the two listings showing the name of your USB device. In our test here using C-Media, the first line sends the digital signal without conversion. This is useful if you have a device plugged in, such as one of the DACs discussed earlier in the chapter. However, headphones, speakers and audio inputs to TVs and stereo sets are generally still analog, so you want PCM audio coming out of the USB dongle.

> 您可以看到几行输出。查看显示 USB 设备名称的两个列表。在我们使用 C-Media 进行的测试中，第一行发送数字信号而不进行转换。如果您插入了设备(如本章前面讨论的 DAC 之一)，这将非常有用。然而，耳机、扬声器以及电视和立体声设备的音频输入通常仍然是模拟的，因此您希望 PCM 音频从 USB 加密狗中输出。

```
`hw:CARD=Device,DEV=0 ` C-Media USB Audio Device, USB Audio
`   Direct hardware device without any conversions` plughw:CARD=Device,DEV=0
`   C-Media USB Audio Device, USB Audio` Hardware device with all software conversions
```

For this example, `plughw:CARD=Device,DEV=0` is the information you need for the `-D` parameter required to the desired digital file (`Beethoven Ode to Joy.wav`, in this example). 5. Use the following command to play an audio file through the USB sound card:

> 在本例中，`plughw:CARD=设备，DEV=0` 是所需数字文件(本例中为 `贝多芬欢乐颂.wav` )所需的 `-D` 参数所需的信息。5.使用以下命令通过 USB 声卡播放音频文件：

`aplay -D plughw:CARD=Device,DEV=0 Beethoven\*Ode_To_Joy.wav

Wait, we need one more item of information. It lies in the \*-D_stuff above. As in omxplayer and many other utilities you’ll encounter, entering its name without parameters generates a list of its available commands. Doing that and looking at the -D line, we find:

> 等等，我们还需要一条信息。它位于上面的\*-D_内容中。正如在 omxplayer 和您将遇到的许多其他实用程序中一样，在不带参数的情况下输入其名称会生成其可用命令的列表。这样做并查看-D 行，我们发现：

-D --device=NAME select PCM by name

> -D--device=NAME 按名称选择 PCM

You’ll probably want to install a player with a nice GUI and run it from the desktop. Many players have a desktop icon you can click to switch the audio output.

> 您可能希望安装一个具有良好 GUI 的播放器，并从桌面运行它。许多播放器都有一个桌面图标，您可以单击以切换音频输出。

#### Installing a Powerful Free Sound Editor

A good choice for an all-around useful editor that runs as it is on Raspbian (and can be installed from Raspbian) is Audacity, which you can download from [`www.audacityteam.org`](http://www.audacityteam.org).

> 对于在 Raspbian 上运行(并且可以从 Raspbian 安装)的全面有用的编辑器来说，Audacity 是一个很好的选择，您可以从[`www.audacityteam.org.]下载(http://www.audacityteam.org).

Audacity is a useful tool for all sorts of purposes, such as producing blogs, creating multi-layered sound effects, grabbing cuts of audio for presentations, and so forth.

> Audacity 是一种用于各种用途的有用工具，例如制作博客、创建多层音效、抓取演示文稿的音频片段等等。

To install Audacity on your Raspberry Pi, make sure the board is connected to the Internet and type:

> 要在 Raspberry Pi 上安装 Audacity，请确保板已连接到 Internet，然后键入：

```
sudo apt-get install audacity
```

Click the Menu button (which is next to the raspberry on the Raspbian GUI) and then type the command `audacity` in the Run box. The program starts and displays a screen like the example shown in Figure 11-6. An audio file of Beethoven’s stirring `Ode to Joy` (a `.wav` digital audio file) is already loaded in and ready to edit.

> 单击菜单按钮(位于树莓 GUI 上树莓旁边)，然后在运行框中键入命令 `audacity` 。程序启动并显示如图 11-6 所示的屏幕。贝多芬激动人心的《欢乐颂》(一个 `.wav` 数字音频文件)的音频文件已经加载并准备编辑。

![[FIGURE 11-6:](#14_9781119183938-ch11.xhtml#rc11-fig-0006) Audacity running on the Raspbian desktop of a Raspberry Pi 2 Model B](./media/images/9781119183938-fg1106.png)

Editing an audio file is very similar to using a word processor to edit a text document. You insert the cursor where you want to make a change, hold down the left mouse button and drag to select an area of the wave form. Click the Delete button to erase the selected section, and the waveform is shortened seamlessly. The copy, paste and undo functions all work very much the same as they do in the word processor.

> 编辑音频文件与使用文字处理器编辑文本文档非常相似。将光标插入要进行更改的位置，按住鼠标左键并拖动以选择波形的一个区域。单击 `删除` 按钮删除所选部分，波形将无缝缩短。复制、粘贴和撤消功能的工作方式与文字处理器中的工作方式完全相同。

Audacity includes lots of effects, and you can download and install more. Figure 11-7 shows a few of the included effects. Click Help on the menu bar for information on how and why to use them.

> Audacity 包含许多效果，您可以下载并安装更多。图 11-7 显示了一些包含的效果。单击菜单栏上的 `帮助` 以获取有关如何使用和为什么使用它们的信息。

![[FIGURE 11-7:](#14_9781119183938-ch11.xhtml#rc11-fig-0007) The Effect menu in Audacity](./media/images/9781119183938-fg1107.png)

[Figure 11-6](#14_9781119183938-ch11.xhtml#c11-fig-0006) shows a stereo waveform with left and right channels, or two tracks. However, nothing limits you to only two tracks. Record yourself playing a guitar. Add in another track playing the same music on a banjo, on a trumpet, some drums, and so on. Sync it up, add a few effects, and you have a major musical production. Mix all the tracks down into left and right for stereo and you’ve got a hit on your hands.

> [图 11-6](#14_9781119183938-ch11.xhtml#c11-fig-0006) 显示了左右声道或两个声道的立体声波形。然而，没有什么限制您只能使用两条轨迹。记录自己弹吉他的情况。加入另一首在班卓琴、小号、一些鼓等上播放相同音乐的曲目。将其同步，添加一些效果，就可以制作出一部大型音乐作品。把所有的音轨混合成左右立体声，你的手就会被击中。

Figure 11-8 shows four tracks in Audacity. The two original `Ode to Joy` tracks have been copied and pasted slightly offset into an additional two tracks. Playing the result gives an interesting sound—not good, kind of weird, but interesting.

> 图 11-8 显示了 Audacity 中的四条轨迹。两首原创的《欢乐颂》曲目被复制并稍微偏移粘贴到另外两首曲目中。播放结果会产生一种有趣的声音——不好，有点奇怪，但很有趣。

![[FIGURE 11-8:](#14_9781119183938-ch11.xhtml#rc11-fig-0008) Additional tracks in Audacity](./media/images/9781119183938-fg1108.png)

#### Some Specifics of Encoding and Decoding

Audio and video files use standards called codecs. A _codec_ is a device or software for encoding and/or decoding a digital stream or signal. Reasons for doing this include compressing a file to save space, encrypting for copy protection and improving playback. The Raspberry Pi hardware knows how to decode the most common formats. You can also add other formats as needed.

> 音频和视频文件使用称为编解码器的标准。*codec* 是用于编码和/或解码数字流或信号的设备或软件。这样做的原因包括压缩文件以节省空间、加密以防止复制和改进播放。复盆子 Pi 硬件知道如何解码最常见的格式。还可以根据需要添加其他格式。
