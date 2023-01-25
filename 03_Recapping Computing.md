Chapter 2

# Recapping Computing

**NOTE: YOU MAY** already know the material in this chapter. Anyone who’s taken any coursework in computing, or played around with computers and programming on their own, has at least a modest grasp of what we present here. This chapter is a broad and very high-level overview of what computers do and what parts of the computer are used to do it. You’ll know within a few pages whether it’s useful for you or not. If it isn’t, feel free to skip directly to [Chapter _3_](#06_9781119183938-ch03.xhtml).

> **注意：您可能**已经知道本章的内容。任何参加过任何计算课程或自己玩过计算机和编程的人，至少对我们在这里展示的内容有一定的了解。本章对计算机的功能以及计算机的哪些部分用于执行此操作进行了广泛而高度的概述。您将在几页内知道它是否对您有用。如果不是，请直接跳到[第*3*章](#06_9781119183938-ch03.xhtml)。

Although we created computers to do calculations, computers are not calculators. We’ve had calculators for a very long time. The abacus is known to have been used by the Persians as early as 600 BCE, and it was probably in use earlier than that. The precursor to the slide rule, called `Napier’s Bones` , was invented by John Napier in 1617. The very first mechanical calculator, the Pascaline, was invented by Blaise Pascal in 1642—when he was only 19! Better and more elaborate mechanical calculators were devised over the years until very recently, when digital calculators shoved mechanical and analogue calculators onto history’s high shelf.

> 虽然我们创造了计算机来进行计算，但计算机不是计算器。我们使用计算器已经很长时间了。众所周知，算盘早在公元前 600 年就已被波斯人使用，而且它的使用时间可能更早。计算尺的前身称为 `Napier 的骨头` ，由 John Napier 于 1617 年发明。第一台机械计算器 Pascaline 由 Blaise Pascal 于 1642 年发明，当时他只有 19 岁！ 多年来，人们设计出了更好、更精巧的机械计算器，直到最近，数字计算器将机械和模拟计算器推上了历史的高架。

Charles Babbage is usually credited with the idea of programmability in calculation. He was too poor and his `analytical engine` too complex for him to construct it in 1837, but his son built and demonstrated a more modest version of the machine in 1888. However, it wasn’t until the 1930s that the ideas underlying modern computing began to be understood fully. Alan Turing laid the theoretical groundwork for fully programmable computers in 1936. In 1941, Konrad Zuse built a programmable electromechanical computer, called the Z3 machine, that understood binary encoding and floating point numbers. Zuse’s machine was later proven to be `Turing complete` —that is, capable of implementing Turing’s principles of general-purpose computing.

> Charles Babbage 通常被认为是在计算中提出了可编程性的想法。1837 年，他太穷了，而且他的 `分析引擎` 太复杂了，无法建造它，但他的儿子在 1888 年建造并展示了一台更普通的机器。然而，直到 1930 年代，现代机器的思想才得到认可 计算开始被充分理解。1936 年，艾伦·图灵 (Alan Turing) 为完全可编程计算机奠定了理论基础。1941 年，康拉德·楚泽 (Konrad Zuse) 建造了一台可编程机电计算机，称为 Z3 机器，它可以理解二进制编码和浮点数。Zuse 的机器后来被证明是 `图灵完备` ——也就是说，能够实现图灵的通用计算原理。

Zuse’s Z3 had been created to perform statistical analysis of the German air force’s wing designs. World War II accelerated the development of digital computers on many fronts, driven first by the need to calculate artillery trajectories, and later to handle the complex mathematics used by the developers of the nuclear bomb. By 1944, the Colossus computers at Bletchley Park were in daily service aiding the cryptanalysis of German, Italian and Japanese wartime ciphers.

> 创建了 Zuse 的 Z3 来对德国空军的机翼设计进行统计分析。第二次世界大战加速了许多方面的数字计算机的开发，这首先是由计算炮兵轨迹的需求，后来处理核弹开发商使用的复杂数学。到 1944 年，布莱奇利公园(Bletchley Park)的巨人计算机正在日常服务，以帮助德国，意大利和日本战时密码的密码分析。

Not all calculation is done in a single step, as are basic arithmetic operations like addition and multiplication. Some calculation requires iterative operations that run in sequence until some limiting condition is reached. There are calculations so complex that the calculator must inspect its own operations and results as it goes along, to determine whether it has completed its job or must repeat some tasks or take up new ones. This is where programmability comes in, and where a calculator takes the fateful step away from calculation into true computing.

> 并非所有计算都是在一个步骤中完成的，基本的算术操作(如加法和乘法)也是如此。一些计算需要按顺序进行的迭代操作，直到达到某些限制条件。计算如此复杂，以至于计算器必须检查其自己的操作和结果，以确定其是否已完成工作或必须重复某些任务或承担新任务。这是可编程性的来源，而计算器将命运从计算转移到真实计算的地方。

It’s this simple: computers are not calculators. Computers follow recipes.

> 这很简单：计算机不是计算器。计算机遵循食谱。

## The Cook as Computer

In some respects, we’ve been computing since long before we were calculating. Homo sapiens broke away from the rest of the primate pack through the ability to pass along knowledge verbally from one generation to the next. Much of this transmitted knowledge was `how-to` in nature, such as how to shape an axe head from a piece of stone. Following step-by-step instructions is now such a pervasive part of life that, most of the time, we don’t even realize we’re doing it. Watch yourself work the next time you cook anything more complex than a toasted cheese sandwich. You’re not just cooking. You’re computing.

> 在某些方面，我们从很久以来就一直在计算计算。Homo Sapiens 通过口头从一代人传递知识的能力从灵长类动物包中脱颖而出。这种传播的知识大部分本质上是 `操作方法` ，例如如何从一块石头上塑造斧头头。遵循分步说明现在是生活中如此普遍的一部分，大多数时候，我们甚至都没有意识到自己正在这样做。下次您烹饪比烤奶酪三明治更复杂的事情时，请注意自己工作。您不仅仅是做饭。您正在计算。

### Ingredients as Data

All recipes begin with a list of ingredients. The list is very specific, in terms of both the ingredients and their quantities: For example, the ingredients for _carré d’agneau dordonnaise_ are:

> 所有食谱均以成分列表开始。就成分及其数量而言，该列表非常具体：例如，_carréD'Agneaudordonnaise 的成分是：

2 racks of lamb
½ cup shelled walnuts
1 small onion
1 3 oz can of liver pâté
½ cup bread crumbs
2 tablespoons parsley
1 tsp salt
2 tbsp lemon juice
½ tsp finely ground black pepper

The goal in cooking is to combine and process these ingredients to make something that doesn’t already exist in your refrigerator. In computing, there are also ingredients: text, numbers, images, symbols, photos, videos and so on. A computer program can take these ingredients and combine and process them into something new: a PDF document, a web page, an e-book or a PowerPoint presentation.

> 烹饪的目标是将这些成分结合在一起，以制造冰箱中不存在的东西。在计算中，还有一些成分：文本，数字，图像，符号，照片，视频等。计算机程序可以采用这些成分，并将它们合并为新事物：PDF 文档，网页，电子书或 PowerPoint 演示文稿。

Recipes are step-by-step instructions for going from the ingredients to _carré d’agneau dordonnaise_. Some recipes may be absurdly simple, but most are very explicit and usually done in a specified order:

> 食谱是从成分到 *carréD'Agneaudordonnaise* 的分步说明。有些食谱可能很简单，但大多数食谱非常明确，通常按照指定的顺序完成：

1. Remove the bones from both racks. 2. Trim the fat off the meat. 3. Finely chop the walnuts. 4. Grate the onion. 5. Stir the liver pâté until smooth. 6. Beat the walnuts and onion into the pâté. 7. Mix the breadcrumbs and parsley together. 8. Season the stuffing mix with salt, lemon juice and pepper.

> 1.从两个架子上取下骨头。2.从肉上修剪脂肪。3.切碎核桃。4.将洋葱磨碎。5.搅拌肝 p 直至光滑。6.击败核桃和洋葱进入 pâté。7.将面包屑和欧芹混合在一起。8.用盐，柠檬汁和胡椒粉调味混合物。

…and so on. Granted, you could grate the onion before you chopped the walnuts; in many cases order doesn’t matter. However, it does matter sometimes—you can’t beat the chopped walnuts into the pâté before you’ve chopped the walnuts.

> …等等。当然，您可以在切碎核桃之前将洋葱磨碎。在许多情况下，顺序无关紧要。但是，有时确实很重要 - 在切碎核桃之前，您无法将切碎的核桃击中到肉饼中。

Just like recipes, computer programs are sequences of steps that start at the beginning, do something with the data and then pause or stop after all the steps have been performed. You can see simple programs called scripts running in a terminal window on the Raspberry Pi as they do exactly that: they start, they run and they stop when their job is completed. You can see each step in the `recipe` scroll by as it is performed.

> 就像配方一样，计算机程序是从开始开始的步骤序列，使用数据进行操作，然后在执行所有步骤后停止或停止。您可以看到在 Raspberry Pi 上的终端窗口中运行的简单程序，就像他们这样做一样：它们开始，运行并在工作完成后停止。您可以在执行 `食谱` 滚动中看到每个步骤。

With more complex programs, like word processors, the recipe isn’t as linear and the steps aren’t reported onscreen. A word processor is a little like a cook in a café. At the counter you ask for a lunch special, the cook nods and then disappears into the heart of the kitchen to put your meal together. When it’s done, the cook hands the lunch special over the counter to you through the window and waits for another order. When you’re not typing or selecting commands from the menu, a word processor is like the cook waiting at the counter. When you type a character, the word processor takes the character and integrates it with the current document, then waits for another. Regardless of whether you can see the steps happen, each time you type a character, a whole long list of things happen in order, for example, to display the letter `y` at the end of the word `Raspberry` .

> 借助更复杂的程序，例如文字处理器，该食谱并不那么线性，并且在屏幕上没有报道这些步骤。文字处理器有点像咖啡馆里的厨师。在柜台上，您要求提供午餐特惠，厨师点点头，然后消失在厨房的心脏中，将您的饭菜放在一起。完成后，厨师通过窗户将午餐特别的午餐交给您，然后等待另一个订单。当您不从菜单中输入或选择命令时，文字处理器就像在柜台等待的厨师一样。当您键入字符时，文字处理器将接收角色并将其与当前文档集成在一起，然后等待另一个文档。无论您是否可以看到步骤发生，每次键入字符时，都会在 ` raspberry` 一词的末尾显示字母 ` y` 。

### Basic Actions

In both recipes and computer programs, individual steps may contain lists of other steps. The step of grating the onion, for example, is performed in several, smaller steps: first you have to grab the onion in one hand, then pick up the grater with the other hand, and then rub the onion against the face of the grater while allowing the grated onion to fall into a bowl.

> 在配方和计算机程序中，各个步骤都可能包含其他步骤列表。例如，将洋葱磨碎的步骤以几个较小的步骤进行：首先，您必须一只手抓住洋葱，然后用另一只手拿起刨丝器，然后将洋葱擦在刨丝器的脸上同时让磨碎的洋葱落入碗中。

In recipes, these internal steps are not called out every time. Most people who have done some cooking know how to grate an onion, and providing detailed directions for grating an onion is unnecessary. However, you follow steps when you grate an onion, whether the steps are spelled out explicitly in the recipe or not. This can happen only because you, the cook, already knew how to grate an onion.

> 在食谱中，这些内部步骤并非每次都被召集。大多数做烹饪的人都知道如何烤洋葱，并提供详细的指示洋葱。但是，您在烤洋葱时遵循步骤，无论是否在食谱中明确阐明这些步骤。这可能仅仅是因为您，厨师已经知道如何烤洋葱。

That’s an important point. Cooks use a large number of specific, named actions to complete a recipe. Expert cooks know them all and they can use them without explanation: peel, grate, mix, fold, zest, chop, dice, sift, skim, simmer, bake and so on. Some of these actions are commoner than others, while some—like acidulate—are used so rarely that recipes typically do spell them out in simpler terms, in this case, `Add vinegar or lemon juice to make the sauce more acidic` .

> 这是一个重要的一点。厨师使用大量的特定命名操作来完成食谱。专家厨师都知道所有这些，他们可以使用它们而无需解释：果皮，磨碎，混合，折叠，皮，切碎，骰子，筛子，筛，脱脂，慢火煮，烘烤等。其中一些动作比其他动作更常见，而某些动作(例如酸性)很少使用，以至于食谱通常以简单的术语拼写出来，在这种情况下，`添加醋或柠檬汁以使酱汁更酸性` 。

Computers, like cooks, understand a moderate list of fairly simple actions. These simple actions are combined into larger and more complex actions, which in turn are combined into complete operational programs. The simple, basic steps that a computer understands are called _machine instructions_. Machine instructions can be combined into more complex actions called _subprograms_, _functions_ or _procedures_. Here’s an example of a machine instruction:

> 像厨师一样，计算机理解了一个相当简单的动作列表。这些简单的动作被合并为更大，更复杂的动作，而这些动作反过来又结合了完整的操作程序。计算机理解的简单基本步骤称为 *machine 指令*。机器指令可以合并为更复杂的动作，称为 *subprograms*，*functions* 或 *procedures*。这是机器指令的示例：

```
	MOV PlaceB, PlaceA
```

The `MOV` instruction moves a single piece of data from one place to another place inside the computer. Machine instructions may be combined into functions that do a great deal more. Here, for example, is a function:

> ` MOV` 指令将单个数据从一个位置移至计算机内的另一个位置。机器说明可能会合并为更重要的功能。例如，这里是一个函数：

```
    capitalize(streetname)
```

The `capitalize()` function does what you probably expect: the name of a street is a short string of text characters, which the previous statement in the program placed in a named data item called `streetname`. The function capitalizes the words within the street name according to standard rules for capitalization. This is how a computer turns the text `garden of the gods road` into `Garden of the Gods Road.` Inside the `capitalize()` function may be dozens or hundreds of machine instructions, just as in a cooking task the instruction to `reduce` involves a fair bit of fussy adding, simmering, stirring and testing.

> `capitalize()` 函数执行您可能期望的操作：街道名称是一个简短的文本字符串，程序中的前一条语句将其放置在名为 `streetname` 的命名数据项中。该函数根据标准大写规则将街道名称中的单词大写。这就是计算机如何将文本 `众神花园路` 变成 `众神花园路` 。在 capitalize() 函数中可能有数十或数百条机器指令，就像在烹饪任务中的指令一样 `reduce` 涉及相当繁琐的添加、慢炖、搅拌和测试。

## The Box That Follows a Plan

That’s about as far as we can take the recipe metaphor, and perhaps a little further than we should. Computers are indeed a little like cooks following recipes. Cooks also improvise, try weird things and sometimes make a mess. Computers don’t improvise unless we tell them to, and when they make a mess it’s because we have made some kind of mistake, not them. A metaphor that is closer to reality is author Ted Nelson’s description of a computer as `a box that follows a plan` . A computer is a box, and inside the box are the plan, the machinery that follows the plan and the data upon which the plan acts.

> 据我们所知，这就是食谱的隐喻，也许比我们应有的更多。计算机的确有点像厨师之后的食谱。厨师还即兴创作，尝试怪异的事情，有时会弄乱。除非我们告诉他们，否则计算机不会即兴创作，而当他们弄得一团糟时，这是因为我们犯了某种错误，而不是它们。一个更接近现实的隐喻是作者泰德·尼尔森(Ted Nelson)对计算机的描述为 `遵循计划的盒子` 。计算机是一个盒子，框内是计划，遵循计划的机器以及计划所采用的数据。

### Doing and Knowing

One more metaphor and we’ll let it rest: programs are what a computer _does_ and data are what a computer _knows_. (This description is credited to computer author Tom Swan.) The part that `does` is called the _central processing unit_ (CPU). The part that `knows` is called _memory_. This `knowing` is done by encoding numbers, characters and logical states using the binary numeric notation discovered by Gottfried Leibniz in 1679. It wasn’t until 1937 that Claude Shannon systematized the use of binary numbers into the maths and logic that computers use to this day. A _bit_ is a binary digit, an irreducible atom of meaning that expresses either 1 or 0. As we explain a little later, bits are represented in computers by on/off electrical states.

> 再打一个比喻，我们就让它休息吧：程序是计算机*做*的，数据是计算机*知道*的。(此描述归功于计算机作者 Tom Swan。) `做` 的部分称为*中央处理单元* (CPU)。`知道` 的部分称为*内存*。这种 `了解` 是通过使用戈特弗里德·莱布尼茨 (Gottfried Leibniz) 于 1679 年发现的二进制数字符号对数字、字符和逻辑状态进行编码来完成的。直到 1937 年，克劳德·香农 (Claude Shannon) 才将二进制数字的使用系统化为计算机用来计算的数学和逻辑。这天。_bit_ 是二进制数字，表示 1 或 0 的不可约原子。正如我们稍后解释的那样，位在计算机中由开/关电状态表示。

Today, both the CPU and memory are made out of large numbers of transistors etched onto silicon chips. (A transistor is simply an electrical switch made out of exotic metals called semiconductors.) This wasn’t always the case; before silicon chips, computers were built out of individual transistors and even vacuum tubes. (Zuse’s seminal Z3 machine used electromechanical relays.)

> 如今，CPU 和内存都是由蚀刻到硅芯片上的大量晶体管制成的。(晶体管只是由称为半导体的外来金属制成的电开关。)并非总是如此。在硅芯片之前，计算机是由单个晶体管甚至真空管构建的。(Zuse 的开创性 Z3 机器使用了机电继电器。)

Whatever they were made of, early computers followed the general plan shown in Figure 2-1. A central control console monitored several different subsystems, each of which was generally in its own cabinet or cabinets. There was the CPU, a punched tape or magnetic tape storage unit and two different memory units. One of the memory units held a series of machine instructions that comprised a computer program. The other memory unit held the data that the program manipulated. This is sometimes called the Harvard architecture, because the Mark I, a very early electromechanical computer developed at Harvard University in 1944, stored data and instructions separately.

> 无论它们是由什么制成的，早期计算机都遵循图 2-1 所示的一般计划。中央控制控制台监视了几个不同的子系统，每个子系统通常都在其自己的橱柜或机柜中。有 CPU，一个打孔胶带或磁带存储单元和两个不同的存储单元。其中一个内存单元包含一系列组成计算机程序的机器指令。另一个内存单元保存了程序操纵的数据。这有时被称为哈佛建筑，因为 Mark I 是 1944 年在哈佛大学开发的一款非常早期的机电计算机，分别存储了数据和说明。

> ![[FIGURE 2-1:](#05_9781119183938-ch02.xhtml#rc02-fig-0001) A pre-von Neumann computer](./media/images/9781119183938-fg0201.png)

Not only were the data memory and the instruction memory of the Mark I physically separate, but they were also, generally, nothing like one another. Data memory might consist of vacuum tubes, dots on a phosphor screen or even sound pulses traveling through columns of mercury. (You can read more on the evolution of memory in [Chapter 3](#06_9781119183938-ch03.xhtml).) Early instruction memory consisted of rows of mechanical switches and wire jumpers that could be moved from one point on a terminal bar to another. Technicians had to set each individual machine instruction by hand, using switches or jumpers, before the program could be run. (As you might imagine, there weren’t a lot of machine instructions in early programs.)

> 我物理分开的数据内存和指令 Mem 不仅是它们的指令 Mem，而且通常它们彼此之间也没有。数据 Mem 可能包括真空管，磷光器屏幕上的点，甚至是穿过汞柱的声音脉冲。(您可以在[第 3 章](#06_9781119183938-CH03.XHTML)中阅读有关内存演变的更多信息。)早期指令 Mem 由机械开关和电线跳线行组成，可以从另一个终端栏上的一个点移动到另一个点。技术人员必须在运行程序之前，必须使用开关或跳线手动设置每个单独的机器指令。(您可能想象的，早期程序中没有很多机器说明。)

### Programs Are Data

The protean genius John von Neumann worked in many different fields, from mathematics to fluid dynamics, but computer people remember him for a remarkable insight: that _programs are data_ and should be stored in the same memory system as data, using the same memory address space as data. It took some work to redesign computers to read machine instructions from data memory but once it was done, computing was changed forever. Instructions could be entered through a single panel of switches and stored in data memory, one-by-one. Later they could be written out from memory onto lengths of tape punched with patterns of holes, so that they wouldn’t have to be entered by hand every time they were run.

> Protean Genius John von Neumann 在许多不同的领域工作，从数学到流体动力学，但是计算机人会记住他的出色见解：_编程是数据_，应该使用相同的内存地址空间将其存储在同一内存系统中，作为数据。重新设计计算机需要进行一些工作才能从数据存储器中读取机器说明，但是一旦完成，计算将永远更改。可以通过单个交换机输入说明，并存储在数据存储器中，一对一。后来，它们可以从 Mem 中写出，直到磁带图案的磁带长度，因此每次运行时都不必手动输入它们。

Von Neumann’s insight simplified computing greatly, and led straight to the explosion of computer power that occurred during the 1950s. Figure 2-2 is a highly simplified schematic of how modern computers operate. The figure shows no particular model or family of computer, and omits many of the more advanced features that we explain in later chapters.

> 冯·诺伊曼(Von Neumann)的洞察力大大简化了计算，并直接导致了 1950 年代发生的计算机功率的爆炸。图 2-2 是现代计算机运作方式的高度简化示意图。该图显示没有特定模型或计算机系列，并省略了我们在后面的章节中解释的许多更高级的功能。

> ![[FIGURE 2-2:](#05_9781119183938-ch02.xhtml#rc02-fig-0002) A simplified modern computer](./media/images/9781119183938-fg0202.png)

### Memory

In the simplest possible terms, _system memory_ is a long row of storage compartments for data. Each location in the row has a unique numeric _address_. All locations are the same size; in modern computers this is generally the 8-bit byte (see Figure 2-3). However, computers read data from system memory in multi-byte chunks. Thirty-two-bit systems like the Raspberry Pi access memory 32 bits (4 bytes, generally called a word) at a time, and perform most of their internal operations on 32-bit quantities. In larger 64-bit desktops and laptops, system memory is accessed 64-bits (8 bytes) at a time.

> 在最简单的术语中，*System Memory* 是数据的长行存储室。行中的每个位置都有一个唯一的数字 *address*。所有位置的大小相同；在现代计算机中，这通常是 8 位字节(见图 2-3)。但是，计算机从多字节块中读取系统内存的数据。32 位诸如 Raspberry Pi 访问存储器(通常称为单词通常称为单词)之类的 32 位系统，并在 32 位数量上执行其大部分内部操作。在较大的 64 位台式机和笔记本电脑中，一次可访问系统内存 64 位(8 个字节)。

> [!NOTE]
> that nearly all modern computers allow operations to be performed on single bytes or 2-byte _halfwords_, though there is sometimes a speed penalty for doing so. However, the `bitness` of a computer is the size of its internal data word and operations, _not_ the size of individual memory locations.
> 几乎所有现代计算机都允许对单字节或 2 字节 *halfwords* 执行操作，尽管这样做有时会降低速度。然而，计算机的 `位数` 是其内部数据字和操作的大小，而不是单个内存位置的大小。

![[FIGURE 2-3:](#05_9781119183938-ch02.xhtml#rc02-fig-0003) Memory locations and their addresses](./media/images/9781119183938-fg0203.png)

Memory addresses are ordered in numeric sequence beginning with 0. There is a little disconnect in having the first memory location at address 0 rather than 1, but think of number lines in mathematics, which start at 0. The maths of memory addresses is much easier when the addresses begin at 0.

> 内存地址以数字为单一的数字序列排序。在地址 0 而不是 1 处，将第一个内存位置在数学上有一点断开连接，但要考虑数学行，该数字线从 0 开始。当地址从 0 开始时。

The CPU locates its data for reading and writing by using memory addresses. It uses machine instructions to fetch data words from specified addresses in the system memory and place them in its registers for calculation or testing. It uses other machine instructions to write values stored in its registers to the system memory.

> CPU 通过使用内存地址来定位其数据以读取和写作。它使用机器指令从系统内存中指定的地址中获取数据单词，并将其放在寄存器中进行计算或测试。它使用其他机器指令将存储在其寄存器中的值写入系统内存中。

As mentioned earlier, computer programs themselves are stored in system memory, as sequences of machine instructions, each of which is (usually) a single data word. The difference between a program file and a data file lies almost entirely in how the CPU interprets the data in the file.

> 如前所述，计算机程序本身被存储在系统内存中，作为机器指令的序列，每个序列是(通常)一个数据字。程序文件和数据文件之间的差异几乎完全在于 CPU 如何解释文件中的数据。

Memory is a very complicated business, and we treat it in depth in [Chapter 3](#06_9781119183938-ch03.xhtml).

> 内存是一个非常复杂的业务，我们在[第 3 章](#06_9781119183938-CH03.XHTML)中深入对待它。

### Registers

All CPUs contain a certain limited number of storage locations called _registers_. Registers are right on the silicon of the CPU, and the digital logic that executes machine instructions is not only near them but literally all around them. Each register holds a single value. Some registers have no single job and can be put to many different kinds of work. These _general-purpose registers_ are named or numbered. Other registers have special jobs within the CPU. A few registers fall somewhere in between, in that they have specific jobs to do when certain machine instructions are executed, but in other cases may be used, like general- purpose registers, as a sort of silicon shirt pocket where the CPU can tuck values that will be needed again soon. Writing to registers and reading from them is fast—faster than accessing any other type of memory, especially system memory that lies outside the silicon on some other part of the computer’s main circuit board.

> 所有 CPU 都包含一定有限数量的存储位置，称为 *registers*。寄存器位于 CPU 的硅上，并且执行机器指令的数字逻辑不仅靠近它们，而且在它们周围。每个寄存器都有一个值。有些寄存器没有单一的工作，可以投入许多不同的工作。这些*通用寄存器*命名或编号。其他寄存器在 CPU 内有特殊工作。几个寄存器介于两者之间，因为在执行某些机器说明时，他们有特定的工作要做，但是在其他情况下，可以使用像通用目的寄存器一样，作为一种硅衬衫袋，CPU 可以在其中 tuck 值。这将很快再次需要。写信给寄存器和从中读取的内容是快速的 - 比访问其他任何类型的内存，尤其是在计算机主电路板其他部分外部硅外部的系统内存。

There are many kinds of special-purpose registers. Some of the most common are:

> 有很多特殊用途的登记册。一些最常见的是：

- **Program counter:** A program counter register holds the address of the next machine instruction to be brought in from memory for execution. It `keeps the place` in a computer program.
- **Status:** A status register (sometimes called a flags register) holds a value divided into single bits or groups of bits. Each bit or group is updated with the status of something the CPU has just done. When the CPU compares the values in two registers, a single-bit `equal` flag will be set to either 1 (if the values were equal) or 0 (if the values were not equal). This allows an instruction that follows the comparison to know which way the comparison went.
- **Stack pointer:** A stack pointer holds an address in memory where a data structure called a last-in-first-out stack is stored. Stacks are fundamental to CPU operation; we describe them in more detail in [Chapter 4](#07_9781119183938-ch04.xhtml) in the section `[Inside the CPU](#07_9781119183938-ch04.xhtml#c04-sec-0009)` .
- **Accumulator:** The accumulator is a register that holds the result of arithmetic and logical operations. (It is so named because it was used to accumulate intermediate values during calculations in very early computers.) In modern computers, no single register is the sole location for arithmetic results, and the accumulator’s job has been redistributed to some or all of the general-purpose registers. However, some older machine instructions assume that a single register will hold the results of their operations, which is why the term has survived.

> - **程序计数器：**程序计数器寄存器保留将从内存中带来的**下一个计算机指令的地址**。它在计算机程序中 `保留该位置` 。
> - **状态：**状态寄存器(有时称为标志寄存器)将一个值分为单位或一组。每个位或组都**具有 CPU 刚刚完成的状态的状态**。当 CPU 比较两个寄存器中的值时，单位 `等值` 标志将设置为 1(如果值相等)或 0(如果值不等于)。这允许进行比较后的指令，以了解比较的进行方式。
> - **堆栈指针：**堆栈指针在存储器中保存一个地址，其中存储了称为 `末端` 堆栈的数据结构。堆栈是 CPU 操作的基础；我们在[第 4 章](#07_9781119183938-CH04.XHTML)中更详细地描述它们。
> - **累加器：**累加器是寄存器，它是算术和逻辑操作的结果。(之所以命名是因为它用于在非常早期的计算机中计算过程中累积中间值。)在现代计算机中，没有单个寄存器是算术结果的唯一位置，并且累加器的作业已重新分配给某些或所有一般的一般性。
>   可用登记册。但是，一些较旧的机器指令假定单个寄存器将保留其操作的结果，这就是该术语幸存的原因。

The ARM11 processor at the heart of the original Raspberry Pi has a total of 16 registers available to ordinary programs, of which three have special jobs. An additional two registers act as status registers. We have more to say about this in [Chapter 3](#06_9781119183938-ch03.xhtml).

> 原始 Raspberry Pi 核心的 ARM11 处理器总共有 16 个登记册，可用于普通计划，其中三个有特殊工作。另外两个寄存器充当状态记录。我们在[第 3 章](#06_9781119183938-CH03.XHTML)中还有更多关于这一点。

Registers are `valuable` because they are inside the CPU itself and therefore extremely fast. The more registers a CPU has, the less it must access system memory to store intermediate results. A universal rule in computing is that memory access is slow. A great deal of engineering has been done in recent years to reduce the number of times system memory must be accessed in order to get a given amount of work done.

> 寄存器是 `有价值的` ，因为它们在 CPU 本身内，因此非常快。CPU 的寄存器越多，它必须访问系统内存以存储中间结果的越少。计算中的通用规则是，内存访问很慢。近年来，已经进行了大量的工程，以减少必须访问系统内存的次数，以便完成给定的工作量。

### The System Bus

One of the fundamental challenges of computing is getting values between system memory and the CPU as quickly as possible. Data values are stored in memory at locations that have specific numeric addresses. To access a value in the memory, the CPU must present the value’s address in the memory to the memory system. The value will then be copied from memory and sent back to the CPU.

> 计算的基本挑战之一是尽快获得系统内存和 CPU 之间的值。数据值存储在具有特定数字地址的位置中的内存中。要访问内存中的值，CPU 必须在存储器系统中向内存中显示值的地址。然后，该值将从内存复制并发送回 CPU。

There is a pathway between the CPU and memory called the _system bus_. The system bus is a side-by-side group of electrical conductors called _lines_, each of which carries one bit of information. The number of bus lines varies depending on the type of computer and the chips it uses. The system bus carries three things:

> CPU 与称为 *System Bus* 的内存之间有一个途径。系统总线是一组名为 *lines* 的电导导体组的组，每个导体都带有一点点信息。总线线的数量取决于计算机的类型及其使用的芯片。系统总线带有三件事：

- Memory addresses - Data values - Control signals that allow the CPU and system memory to coordinate traffic over the bus

> - 内存地址 - 数据值 - 允许 CPU 和系统内存可以通过总线协调流量的控制信号

In simple terms, the CPU places the address of a memory location on the bus. It also places one or more signals on the control lines, to tell the memory electronics whether the address is to be read from or written to. The CPU then either places a value on the bus to be written to the specified memory location, or waits for the system memory to place the value at the specified address on the bus to be sent back to the CPU.

> 简而言之，CPU 将内存位置的地址放在总线上。它还在控制线上放置一个或多个信号，以告诉内存电子设备是否要从中读取或写入地址。然后，CPU 将要么在要写入指定内存位置的总线上放置一个值，或者等待系统内存将值放置在要发送回 CPU 的总线上的指定地址。

Computer programs and program data are stored in different locations in memory but, except for how the CPU interprets them, there is no difference between a data word and a machine instruction. For this reason, the term `data values` embraces both data and instructions. We’ll have more to say about this in the next two chapters.

> 计算机程序和程序数据存储在内存中的不同位置中，但是除了 CPU 如何解释它们外，数据字和机器指令之间没有区别。因此，术语 `数据值` 包含数据和指令。在接下来的两章中，我们将有更多的话要说。

### Instruction Sets

There are a host of different CPU models in the world. Each has its own way of talking to memory and to other parts of the computer system. What sets the models apart most clearly are the individual operations that the CPU can perform. These are the machine instructions and, taken as a group, they are called an _instruction set_.

> 世界上有许多不同的 CPU 模型。每个人都有自己与内存和计算机系统其他部分交谈的方式。CPU 可以执行的单个操作，最清楚地将模型与众不同。这些是机器指令，作为一个组，它们被称为 *instruction set*。

An instruction set is specific to a specific family of CPUs. Intel’s CPUs represent one such family; ARM is another. Most individual CPUs understand only a single instruction set. The original Raspberry Pi’s ARM11 processor actually has two instruction sets, though only one of them is actually used by the Raspberry Pi software. (There will be more on this in [Chapter 4](#07_9781119183938-ch04.xhtml).)

> 指令集特定于特定的 CPU 家族。英特尔的 CPU 代表一个这样的家庭；手 ARM 是另一个。大多数个人 CPU 仅了解单个指令集。原始的 Raspberry Pi 的 ARM11 处理器实际上有两个指令集，尽管 Raspberry Pi 软件实际上只使用了其中一个。([第 4 章](#07_9781119183938-CH04.XHTML)中将有更多内容。)。

The machine instructions in an instruction set are grouped by their general function: instructions that move data from or to memory and between registers; instructions that perform arithmetic calculations; instructions that perform logical operations; instructions that read status bits or set control bits; and so on. Early CPUs might have had as few as a dozen machine instructions. Modern CPUs can have a hundred or more.

> 指令集中的机器指令按其一般函数进行分组：将数据从内存或内存以及寄存器之间移动的说明；执行算术计算的说明；执行逻辑操作的说明；读取状态位或设置控制位的说明；等等。早期的 CPU 可能只有十几个机器说明。现代 CPU 可以拥有一百或更多。

Although it’s useful to have a big-picture view of CPU instruction sets, you don’t need to memorize them. Programmers rarely write programs by stringing together machine instructions. (This is done sometimes, but it’s slow, specialized work.) Instead, programmers write lists of action statements that read more like human languages. These lists of action statements are then given to programs that translate them into lists of machine instructions. The translator programs are called _compilers_ or _interpreters_, depending on how they operate. We cover these in much more detail in [Chapter 5](#08_9781119183938-ch05.xhtml).

> 尽管对 CPU 指令集有一个大图表很有用，但您无需记住它们。程序员很少通过将机器指令串在一起来编写程序。(这有时是这样做的，但是这是缓慢而专业的工作。)相反，程序员编写的动作语句列表读起来更像人类语言。然后将这些动作语句列表提供给程序，以将其转换为机器指令列表。转换器程序称为 *compilers* 或* interpreters*，具体取决于它们的操作方式。我们在[第 5 章](#08_9781119183938-CH05.XHTML)中更详细地介绍这些内容。

## Voltages, Numbers and Meaning

It’s common to say that computers don’t really deal with text; they deal with numbers. Strictly speaking, even that isn’t true. Down inside the silicon of the CPU where things happen, computers deal only with electrical voltage levels. The actual operation of computer chips entails a constant storm of electrical activity in which voltage levels change back and forth between two—and only two—values. One level is no voltage at all (0 volts) and the other is a single higher voltage level that may vary from computer to computer. It could be 5V or 3V or 3.6V or (on many mobile computers, as well as the Raspberry Pi) 1.2V or less. It could be some other value entirely, as long as it’s always the same inside any given computer. We use 3V in the following discussion.

> 通常说计算机并没有真正处理文本。他们处理数字。严格来说，即使那不是真的。在发生事情发生的 CPU 硅内部，计算机仅处理电压水平。计算机芯片的实际操作需要持续的电活动风暴，其中电压水平在两个(只有两个)值之间来回变化。一个水平根本没有电压(0 伏)，另一个是一个更高的电压水平，可能因计算机而异。可能是 5V 或 3V 或 3.6V 或(在许多移动计算机以及 Raspberry Pi 上)1.2V 或更少。只要在任何给定的计算机内总是相同，它可能完全是其他价值。我们在以下讨论中使用 3V。

Computers do deal with numbers, but those numbers are encoded as voltage levels. By convention we say that a voltage level of 0V means the number 0 and a voltage level of 3V (or whatever level it is in the computer being discussed) means the number 1. Only two voltage levels are used in computer chip circuitry, so computers really only understand the two numeric digits, 0 and 1. That’s all, and it doesn’t sound like much. What can you do with only 0 and 1?

> 计算机确实处理数字，但是这些数字被编码为电压级别。按照惯例，我们说 0V 的电压级别表示数量 0，电压级别为 3V(或讨论计算机中的任何水平)表示数字 1。在计算机芯片电路中仅使用两个电压级别，因此计算机真的只了解两个数字数字，即 0 和 1。仅此而已，听起来并不多。您只能用 0 和 1 做什么？

Everything.

### Binary: Counting in 1s and 0s

Humans understand just 10 numeric digits: 0, 1, 2, 3, 4, 5, 6, 7, 8 and 9. Yet with those 10 digits we perform mind-bogglingly complex mathematical operations and express numbers that literally have no maximum value. We can express very large numbers with only a couple of different digits: a good approximation of the number of atoms in the entire observable universe can be stated as 1 followed by eighty 0s. Obviously, it’s not about the number of numeric digits we have; it’s about how we arrange them and (more to the point) the meaning that we assign to them.

> 人类仅了解 10 个数字数字：0、1、2、3、4、5、6、7、8 和 9。然而，在那 10 个数字的情况下，我们执行了令人难以置信的复杂数学操作，并表示没有最大值的数字。我们只能以几个不同的数字来表达大量数字：整个可观察到的宇宙中原子数的良好近似值可以说为 1，其次是八十 0s。显然，这与我们拥有的数字数字数量无关；这是关于我们如何安排它们以及(更重要的是)我们分配给它们的含义。

The decimal notation that we just call numbers*,* which we learned when we were little, is less about numeric digits than columns. Multidigit numbers are digits arranged in columns, with each column having a value 10 times that of the column to its right. In a decimal number like 72,905, each column has a value and a digit in the column to tell us how many times that value is present in the number as a whole. In 72,905, there are 7 ten-thousands, 2 thousands, 9 hundreds, 0 tens and 5 ones.

> 我们只调用数字的十进制表示法，我们在很小的时候就学会了，而不是数字数字，而不是列。多位数字是在列中排列的数字，每个列的值的值是右侧的 10 倍。在像 72,905 之类的小数中，每列在列中都有一个值和数字，以告诉我们整个数字中存在多少次该值。在 72,905 年，有 7 万，2,000，900，0 至 5 个。

This concept is easier to understand as a picture; see Figure 2-4.

> 这个概念更容易理解为图片。见图 2-4。

> ![[FIGURE 2-4:](#05_9781119183938-ch02.xhtml#rc02-fig-0004) How decimal numbers are evaluated](./media/images/9781119183938-fg0204.png)

We’re so used to thinking in terms of powers of ten that it seems odd to imagine column values other than powers of ten. However, it doesn’t just work; columnar notation using other column values is essential to understanding computing. So consider what numbers would look like if each column had a value _two_ times the value of the column on its right, rather than ten. Instead of columns of ones, tens, hundreds, thousands and ten thousands, we would have columns of ones, twos, fours, eights, sixteens and so on. How many different digits would such a columnar system need?

> 我们已经习惯了十个力量的思考，以至于想象十个力量以外的列值似乎很奇怪。但是，它不仅有效；使用其他列值的柱状符号对于理解计算至关重要。因此，请考虑如果每列具有一个值 *two* 乘以其右侧的列值，而不是十个，则该数字是什么样的。我们将拥有一列，数十万，成千上万和十万的列，而是有一列，二，四，八，六，六个人等。这样的柱状系统需要多少位数字？

Two: 0 and 1. In other words, instead of decimal notation with columnar multiples of ten, we have a _binary_ notation with columnar multiples of two. See Figure 2-5, which dissects the binary number 11010. In 11010, there is 1 sixteen, 1 eight, 0 fours, 1 two and 0 ones. (Commas are not used in binary columnar notation.)

> 二：0 和 1。换句话说，我们有一个 *binary* 符号，而不是用两个柱状表示法，而不是用两个的柱状倍数表示。参见图 2-5，剖析二进制编号 11010。在 11010 中，有 16，1 八，0 四，1 二和 0。(逗号未在二进制柱状符号中使用。)
> ![[FIGURE 2-5:](#05_9781119183938-ch02.xhtml#rc02-fig-0005) How binary numbers are evaluated](./media/images/9781119183938-fg0205.png)

There is an alien look about numbers without the digits 2 to 9, but the numbers are real. To see what the binary number’s value actually is in decimal terms we have to add up the values represented by all the columns: 16 + 8 + 0 + 2 + 0 = 26. The two numbers 11010 and 26 have the same value. They’re expressed in different notation, but the numbers are precisely equal. To recast a (very) old joke: there are only 10 kinds of people in the world: those who understand binary and those who don’t.

> 没有数字 2 到 9 的数字有一个外星人的外观，但是数字是真实的。要查看二进制数字的实际值，我们必须添加所有列代表的值：16 + 8 + 0 + 0 + 2 + 0 = 26。两个数字 11010 和 26 具有相同的值。它们以不同的符号表示，但数字完全相等。重铸(非常)古老的笑话：世界上只有 10 种人：那些了解二元的人和那些不了解二元的人。

The value of column multiples in a system of numeric notation is the base of the system. If the columnar multiple is 10, the system is _base 10_. If the columnar multiple is two, the system is base 2. (The small subscript numbers in the figures specify the number bases of the numbers beside them.) Theoretically, column multiples may be any integer value at all: base 3, base 4, base 8, base 11, base 16, anything. There’s only one problem, which is explained in the next section.

> 数字符号系统中列倍数的值是系统的碱基。如果柱状倍数为 10，则系统为 *base 10*。如果列倍倍数为两个，则系统为基础 2。(图中的小标准编号指定了它们旁边数字的数字库。)理论上，列倍可能完全是任何整数值：base 3，base 4，4，base 4，4 基础 8，基础 11，基础 16，任何东西。只有一个问题，下一节会解释。

### The Digit Shortage

Our ingrained decimal notation is called base 10, and uses 10 digits. Base 2 uses two digits. Base 8 uses eight digits. Base 16 uses 16 digits—except that there are only ten digits. Zero to 9 is all we have. What about the other six digits? If we had evolved with eight fingers on each hand, there would doubtless be 16 digits, each a single, distinct symbol. Any symbols will do, as long as we agree on what each symbol means. We could use the symbols @, %, , &, \# and $. However, there is an ordering problem. These symbols have no universally understood order. Does come before &? Only when they’re typed in that order. Confusion would result without an agreed-upon ordering. So let’s use six symbols that _do_ have an agreed-upon order: A, B, C, D, E and F. Counting to 10 in our familiar decimal notation and symbols looks like this:

> 我们根深蒂固的十进制符号称为基本 10，使用 10 位数字。基础 2 使用两个数字。Base 8 使用八位数字。Base 16 使用 16 位数字 - 除了只有 10 位数字。零到 9 是我们所拥有的。那其他六位数呢？如果我们每只手都用八个手指进化，无疑将有 16 位数字，每个数字都有一个独特的符号。只要我们同意每个符号的含义，任何符号都会做。我们可以使用符号 @，％，，＆，\#和 $。但是，有一个订购问题。这些符号没有普遍理解的顺序。之前＆？只有按照该顺序输入。如果没有商定的命令，就会造成混乱。因此，让我们使用六个符号，即 *do* 有一个约定的订单：a，b，c，d，e 和 f。在我们熟悉的十进制符号中计数到 10，而符号看起来像这样：

```
	1, 2, 3, 4, 5, 6, 7, 8, 9, 10.
```

To count to 16 with an expanded digit set, we could say:

> 以扩展的数字集数到 16，我们可以说：

```
    1, 2, 3, 4, 5, 6, 7 8, 9, A, B, C, D, E, F, 10.
```

In a scheme like this, the digit A represents decimal 10, B represents decimal 11, C represents decimal 12 and so on. A value is a value, irrespective of base. The differences between number bases is one of notation, not value. Base 16 is called _hexadecimal_ notation, and it is crucial in understanding modern computers.

> 在这样的方案中，数字 a 表示十进制 10，b 表示十进制 11，c 代表十进制 12，依此类推。值是一个价值，无论基础如何。数字基库之间的差异是符号之一，而不是价值。16 称为 *hexadecimal* 表示法，这对于理解现代计算机至关重要。

### Counting and Numbering and 0

Before we go on, it’s worth exploring a famous little weirdness from the computer world. Counting to 10, as we learned as kids, we begin with the digit 1. In computer technology, however, we start counting with the digit 0. When a computer person is counting memory locations, he or she starts at the first memory location and says, `0, 1, 2, 3, 4, 5…` . What’s going on here? It’s actually a misunderstanding. Counting memory locations like this really isn’t counting them. It’s numbering them. And just as a number line from mathematics begins at 0, numbering entities in computer science begins with 0. A person would say, `There are six memory locations, numbered 0 to 5` . A count (here, six) is how many entities are out there. Numbering them gives them both names and an order. The first memory location can be called `location 0` . Having given that first memory location the name `location 0` , it’s clear that the name of the second location is `location 1` and so on.

> 在我们继续之前，值得探索计算机世界中著名的小怪异。在我们小时候学到的那样，我们从数字 1 开始。但是，在计算机技术中，我们开始使用数字 0 来计算 0。当计算机人员计算内存位置时，他或她从第一个内存位置开始，并且说： ` 0、1、2、3、4、5…` 。这里发生了什么？这实际上是一种误解。计算这样的内存位置确实没有计算它们。它编号了。正如数学的数字线从 0 开始一样，计算机科学中的编号实体从 0 开始。一个人会说： `有六个Mem位置，编号为0到5` 。计数(这里，六个)是那里有多少个实体。编号给他们既有名字又一个订单。第一个内存位置可以称为 `位置0` 。在给出第一个内存位置的名称为 `位置0` 之后，很明显，第二个位置的名称是 `位置1` 等。

When memory locations are numbered in this way, counting from 0, the numbers we give them are called _addresses_. The first address in an address space is always 0.

> 当以这种方式编号内存位置时，从 0 计数，我们给它们的数字称为 *addresses*。地址空间中的第一个地址始终为 0。

### Hexadecimal as a Shorthand for Binary

Hexadecimal notation is a columnar notation, just as decimal and binary notations are. Each column has a value 16 times the value of the column to its right. The numbers look odd because the 16-digit symbols are a mixture of letters and numbers, but the notation works the same way as decimal and binary. The values of the columns mount up fast: by the fifth column, the value of the column is 65,536.

> 十六进制符号是柱状符号，就像十进制和二进制符号一样。每列的值是右侧列值的 16 倍。数字看起来很奇怪，因为 16 位数字的符号是字母和数字的混合物，但是符号的工作方式与十进制和二进制相同。列的值快速安装：到第五列，列的值为 65,536。

Figure 2-6 shows this. The hexadecimal number 3C0A9 is equivalent to the decimal number 245,929. Both numbers are equivalent to the binary value 111100000010101001. This is a clue as to why hexadecimal notation is important.

> 图 2-6 显示了这一点。十六进制的 3C0A9 等于小数号 245,929。这两个数字均等同于二进制值 111100000010101001。这是关于十六进制符号为何重要的线索。

> ![[FIGURE 2-6:](#05_9781119183938-ch02.xhtml#rc02-fig-0006) How hexadecimal numbers are evaluated](./media/images/9781119183938-fg0206.png)

So why does hexadecimal notation even exist? Computers don’t really use hexadecimal numbers. They use binary numbers, period, encoded as electrical voltage levels. `Hex` (as we say informally) is used by all of us who have trouble interpreting long strings of 1s and 0s. It’s a sort of shorthand, allowing us to express binary numbers in a much more accessible form. 111100000010101001 is the same value as 3C0A9. Which would you prefer to work with?

> 那么，为什么还存在十六进制符号呢？计算机实际上并没有使用十六进制数字。他们使用二进制数字，周期为电压水平。`十六进制` (正如我们非正式地说的那样)，我们所有人都在解释 1s 和 0s 的长字符串。这是一种速记，使我们能够以更容易访问的形式表达二进制数字。111100000010101001 与 3C0A9 相同。您想和哪个合作？

Figure 2-7 summarizes the use of hexadecimal as shorthand and also binary numbers are represented by a series of different voltage levels on electrical conductors like the system bus. The system bus shown is 16 bits wide. Each line in the system bus might be a copper trace on a circuit board or a microscopic wire inside a chip, with one of either two voltages on each of the copper traces. The digit 1 represents a 3V reading on a bus line. The digit `0` represents a 0V reading on a bus line.

> 图 2-7 总结了将十六进制作为速记和二进制数的使用，并由系统总线等电导体上的一系列不同的电压水平表示。显示的系统总线为 16 位。系统总线中的每条线可能是电路板上的铜轨迹，也可能是芯片中的微型电线，每个铜痕迹上的两个电压之一。数字 1 表示在公交线上的 3V 读数。数字 ` 0` 表示在总线线上的 0V 读数。
> ![[FIGURE 2-7:](#05_9781119183938-ch02.xhtml#rc02-fig-0007) Bus lines, voltages, binary bits and hexadecimal numbers](./media/images/9781119183938-fg0207.png)

Each digit in a hexadecimal number can represent values from 0 to 15. It takes four bits to represent values up to 15. This is why each digit in a hexadecimal number represents four binary digits of either 1 or 0.

> 十六进制数中的每个数字可以表示 0 到 15 的值。要表示值最高为 15 的值，这就是为什么十六进制数中的每个数字代表 1 个或 0 的四个二进制数字的原因。

It’s possible to lose track of which base a given value is written in. The number 11 is a binary number. It’s also a decimal number, and a hexadecimal number as well. The three values are of course different, but the two digits—11—look precisely the same. Different typographical conventions are used to explicitly specify the number base of a given number:

> 可能会丢失给定值写在哪个基础上。编号 11 是二进制数字。这也是十进制数字，也是十六进制的数字。这三个值当然是不同的，但是这两个数字(11)恰好相同。不同的印刷约定用于明确指定给定数字的数字库：

- For binary, the letter b or B is often used after the number; for example, 011010B. - For binary, the prefix 0b is often used, as in 0b011010. - You may also sometimes see the prefix _%_ in front of binary numbers; for example, %011010. - For hexadecimal, use the letter h or H after the number; for example, F2E5H. - The prefixes $ and 0x are also used to designate hexadecimal notation; for example, $F2E5 and 0xF2E5.

> - 对于二进制，字母 b 或 b 经常在数字之后使用；例如，011010b。- 对于二进制，如 0B011010 所示，通常使用前缀 0b。- 有时您可能还会在二进制数字前看到前缀*％*；例如，％011010。- 对于十六进制，使用数字后使用字母 H 或 H；例如，F2E5H。- 前缀$和0x也用于指定十六进制符号；例如，$ f2e5 和 0xf2e5。

In printed material, such as books and documentation, a subscript suffix is sometimes used to indicate the number base, as in F2E5<sub>16</sub>. Subscripts are difficult to do in editors used for programming, so even in printed work, one of the previously mentioned conventions is used.

> 在印刷材料(例如书籍和文档)中，下标被用来指示数字库，如 F2E5 <ub> 16 </sub>中的数字库。在用于编程的编辑器中很难进行下标，因此即使在印刷工作中，也使用了前面提到的约定之一。

### Doing Binary and Hexadecimal Arithmetic

Binary and hexadecimal are simply different forms of notation. All the laws of arithmetic still apply. It’s possible to do addition, subtraction, multiplication and division on paper in either binary or hexadecimal. The methods are identical; you simply have to remember things like the fact that, in binary, 1 + 1 = 10. In hex, A + 2 = C and A + C = 16 (just not the 16 you’re used to—16H is 22 decimal). Carries and borrows work the same way irrespective of base. Performing long division on paper in hex is a little surreal, but it can be done.

> 二进制和十六进制只是不同形式的符号。所有算术定律仍然适用。可以在二进制或十六进制中进行加法，减法，乘法和划分。这些方法是相同的；您只需要记住诸如二进制的事实，即 1 + 1 = 10。。无论基础如何，携带和借款的工作方式都一样。在十六进制中在纸上进行长期分裂有点超现实，但可以做到。

Yes, it can be done, and it may be good practice, but with a software calculator app on virtually every computer with a graphical shell it may not be the best use of your time. We’re not going to explain how to do manual binary or hex maths here. Instead, we suggest you become familiar with a software calculator capable of number bases other than decimal. On the Raspberry Pi under the Raspbian operating system, the calculator is called Galculator. It’s listed in the start menu in the Accessories group. If you haven’t yet used any operating system (Raspbian is only one of many, as are Windows and OS X), hold that thought; we’ll cover operating systems in the next section.

> 是的，可以做到，这可能是一个好练习，但是使用图形外壳的每台计算机上的软件计算器应用程序，这可能不是您时间的最佳用途。我们不会在这里解释如何进行手动二进制或十六进制数学。取而代之的是，我们建议您熟悉能够使用十进制以外的数字库的软件计算器。在 Raspbian 操作系统下的 Raspberry Pi 上，计算器称为射流器。它在附件组的 `开始` 菜单中列出。如果您尚未使用任何操作系统(Raspbian 和 Windows 和 OS X 一样，Raspbian 只是众多操作系统之一)，请考虑一下。我们将在下一节介绍操作系统。

By default, Galculator works in decimal only, in Basic mode. To use Galculator for calculation in other number bases, first select View and then Scientific mode. The keys for hex digits A–F are greyed out. To change the number base used, select Calculator from the main menu, then Number bases from the pull-down (see Figure 2-8). Click the radio button for the base of your choice. (Galculator also supports octal, which is base 8, but octal is increasingly uncommon and we don’t mention it further here.) For binary, all digits except 0 and 1 are greyed out. For hex, all digits become active.

> 默认情况下，射流器仅在基本模式下以十进制工作。要在其他数字碱基中使用节流子进行计算，请先选择视图，然后选择科学模式。十六进制数字 A – F 的钥匙被弄清楚。要更改所使用的数字库，请从主菜单中选择计算器，然后从下拉中选择数字库(请参见图 2-8)。单击 `单击单选` 按钮以获取您选择的基础。(节流子还支持八进制，这是基础 8，但八分位数越来越少见，我们在这里不提到。对于十六进制，所有数字都变得活跃。

> ![[FIGURE 2-8:](#05_9781119183938-ch02.xhtml#rc02-fig-0008) Changing number bases in Galculator](./media/images/9781119183938-fg0208.png)

When you’re in scientific mode with your base of choice selected, Galculator works just as a calculator works in decimal.

> 当您选择选择基础的科学模式时，射旋器的工作原理就像计算器在十进制中工作一样。

---

> [!TIP]

Here’s a tip: to convert a value from one base to another, enter the value in its original base and then select Calculator ⇒ Number bases and click the button for the base to which you want to convert the value. The conversion is done instantly, just by changing the base.

> 这是一个提示：要将一个值从一个碱基转换为另一个基数，请在其原始基础中输入值，然后选择计算器 ⇒ 数字库，然后单击要转换值的基础的按钮。仅通过更改基础即可立即进行转换。

## Operating Systems: The Boss of the Box

There is a great deal of digital machinery baked into the silicon of modern CPUs. They do not, however, run completely by themselves. Factories need managers and if a CPU and its memory system represent a factory, the factory manager is called an _operating system_ (OS). There have been thousands of operating systems throughout computer history, but at the time of writing only a handful have any significant market share: Windows, GNU/ Linux, Android, OS X and iOS. None of these arose in a vacuum. Windows has its roots in IBM’s OS/2, as well as an older `big iron` operating system called VAX VMS. All the others have deep roots in Unix, another big-system OS created by Bell Labs in the late 1960s.

> 现代 CPU 的硅融入了大量的数字机械。但是，他们没有自己运行。工厂需要经理，如果 CPU 及其内存系统代表工厂，则工厂经理被称为 *operating System*(OS)。在整个计算机历史上都有成千上万的操作系统，但是在撰写本文时，只有少数市场份额有很大的市场份额：Windows，GNU/ Linux，Android，OS X 和 iOS。这些都不是在真空中出现的。Windows 的根源在 IBM 的 OS/2 中，以及一个较旧的 `大铁` 操作系统，称为 VAX VM。其他所有人都在 Unix 中根深蒂固，Unix 是贝尔实验室在 1960 年代后期创建的另一个大型系统 OS。

Operating systems are programs, and like all programs they’re ultimately sequences of machine instructions. Unlike word processors and video games, operating systems have special powers that enable them to manage a computer system. Many of these powers depend on special machine instructions that are designed to be used only by operating systems. Operating systems are loaded and run first, through a boot-up process controlled by a computer’s bootloader, which is a special program tasked with getting the operating system from storage into memory and then running it. Once an OS has loaded and configured itself, the computer is `open for business` and the OS can begin management of the machine.

> 操作系统是程序，就像所有程序一样，它们最终都是机器说明的序列。与文字处理器和视频游戏不同，操作系统具有特殊的功能，使他们能够管理计算机系统。这些功能中有许多取决于专门的机器指令，这些指令仅由操作系统使用。通过由计算机的引导加载程序控制的引导过程，首先加载操作系统并运行，该过程是一个特殊的程序，其任务是将操作系统从存储中进行存储，然后运行。操作系统加载和配置后，计算机将 `为业务开放` ，并且 OS 可以开始管理机器。

### What an Operating System Does

A high-level definition of an operating system is that it stands between a computer user and the computer hardware, enabling the user to use the computer’s various resources without interfering with other users or with computer operation itself. Its major jobs can be broken down this way:

> 操作系统的高级定义是它位于计算机用户和计算机硬件之间，使用户能够使用计算机的各种资源，而无需干扰其他用户或计算机操作本身。它的主要工作可以通过这种方式分解：

- **Process management:** The OS launches individual threads of execution for its own needs and the needs of users. It allocates execution time on the CPU among executing threads. If the CPU has multiple cores, it distributes processes among the cores. (More on this later.)
- **Memory management:** The OS allocates memory to running processes, in most cases as separate memory spaces that are protected from interference by other processes. Through a technology called virtual memory, the OS allows the computer literally to use more memory than it actually has, by writing the least-used process memory out to disk when more memory is needed. (Much more on this in [Chapter 3](#06_9781119183938-ch03.xhtml).)
- **File management:** The OS maintains one or more file systems, which allocate file storage space on disks and other mass-storage devices and manage the reading of data from files and the writing to and deletion of files.
- **Peripheral management:** The OS manages access to system peripherals like keyboards, mice, printers, scanners, graphics coprocessors and (in cooperation with file systems) mass storage devices. This is generally done through specialised software interfaces called device drivers, which are written for specific peripherals and may be installed separately, much like user applications.
- **Network management:** The OS manages the computer’s access to external networks (like local area networks and the Internet) through a collection of standard methods called networking protocols. The protocols are implemented in one or more pieces of software that, taken together, are called the network stack.
- **User account management:** All modern operating systems allow different users to have their own accounts on the computer. An account includes a unique login, a set of security rules called privileges and a private file space protected from manipulation by other users.
- **Security:** Scattered throughout an OS are mechanisms to keep running processes from interfering with one another and with the OS itself. Much of OS security is done by defining rules that specify what processes and users can and cannot do. Certain users called administrators or super users have powers that ordinary users do not have, in order to control the way the OS does its work.
- **User interface management:** The OS manages user interaction with the computer through software mechanisms called shells. A shell may be as simple as a text command line in a terminal window, or it can be a full-blown windowed graphical environment like those used in Windows, Mac OS X and desktop implementations of Linux, including Raspbian on the Raspberry Pi.

> - **流程管理：** OS 为其自身需求和用户的需求启动单个执行线程。它将在执行线程中分配 CPU 上的执行时间。如果 CPU 具有多个核心，则将过程分布在核心之间。(稍后再详细介绍。)
> - **内存管理：** OS 将存储器分配给运行过程，在大多数情况下，作为单独的内存空间，这些空间不受其他进程的干扰。通过一种称为虚拟内存的技术，OS 允许计算机在需要更多内存时将最不使用的过程内存写入磁盘，从而使计算机实际上使用更多的内存。(在[第 3 章](#06_9781119183938-CH03.XHTML)中，有关此信息的更多信息)。)
> - **文件管理：** OS 维护一个或多个文件系统，它们在磁盘和其他质量存储设备上分配文件存储空间并管理文件中数据的读数以及文件的写入和删除。
> - **外围管理：** OS 管理键盘，鼠标，打印机，扫描仪，图形处理器等系统外围设备的访问，并(与文件系统合作)质量存储设备。这通常是通过称为 `设备驱动程序` 的专用软件接口来完成的，这些驱动程序是为特定外围设备编写的，并且可以单独安装，就像用户应用程序一样。
> - **网络管理：**操作系统通过称为网络协议的标准方法集合来管理计算机对外部网络的访问(例如局部网络和 Internet)。协议是在一个或多个软件中实现的，这些软件称为网络堆栈。
> - **用户帐户管理：**所有现代操作系统允许不同的用户在计算机上拥有自己的帐户。一个帐户包括一个唯一的登录名，一组称为特权的安全规则以及其他用户不受操纵保护的私人文件空间。
> - **安全性：**散布在整个操作系统中的机制是防止运行过程相互干扰和操作系统本身的机制。大部分 OS 安全性是通过定义指定过程和用户可以和不能做的规则来完成的。某些称为管理员或超级用户的用户具有普通用户没有的权力，以控制 OS 的工作方式。
> - **用户界面管理：** OS 通过称为 Shells 的软件机制管理用户与计算机的交互。外壳可能像终端窗口中的文本命令行一样简单，也可以是一个成熟的窗户图形环境，例如 Windows，Mac OS X 和 Linux 的桌面实现，包括 Raspberry Pi 上的 Raspbian。

### Saluting the Kernel

The issue of user shells highlights the question of what is and what is not actually a part of the operating system. We’re used to Microsoft Windows, in which the user interface is tightly bound to the operating system as a whole and cannot be changed except in small ways via configuration options. In Linux (including the Raspbian OS) the user interface is an installable module, not much different in nature from a pure application like a word processor. There are textual shells like bash and ksh, and many different graphical shells, including GNOME, KDE, Xfce, Cinnamon and others. These shells can be installed and uninstalled by users with administrator privileges.

> 用户外壳的问题突出了什么是什么是操作系统的问题，什么是什么。我们习惯了 Microsoft Windows，其中用户界面紧密地绑定到整个操作系统，除非通过配置选项以较小的方式进行更改。在 Linux(包括 Raspbian OS)中，用户界面是一个可安装的模块，本质上与纯应用程序(如文字处理器)没有太大不同。有文字贝壳，例如 Bash 和 Ksh，以及许多不同的图形壳，包括 Gnome，KDE，XFCE，Cinnamon 等。这些外壳可以由具有管理员特权的用户安装和卸载。

Linux has a long history of modular design. Many of its elements may be changed, within certain limitations. At its heart, however, is a monolithic block of code called a kernel. The Linux kernel has full control over the computer’s hardware. It adapts to differences in hardware through _loadable kernel modules_ (LKMs) that extend the kernel with device-specific code. LKMs include things like device drivers and file systems.

> Linux 具有模块化设计的悠久历史。它的许多元素可能会在某些局限性范围内更改。然而，它的核心是称为内核的代码的整体块。Linux 内核可以完全控制计算机的硬件。它可以通过*可载的内核模块*(LKMS)适应硬件的差异，该模块_(LKMS)使用特定于设备的代码扩展了内核。LKM 包括设备驱动程序和文件系统之类的东西。

### Multiple Cores

Modern CPUs often have more than a single execution core. A _core_ is a separate and almost entirely independent engine that executes machine instructions. (In silicon design circles, core has a broader meaning, as we explain in [Chapter 4](#07_9781119183938-ch04.xhtml).) At the time of writing, CPUs with two, four and six cores are common in the personal computing world, and units with eight cores are beginning to appear. Each core executes processes independently, but all cores share system resources like memory. The operating system controls the use of all cores in a system, just as it controls everything else. The OS typically runs in one core, and parcels processes out to the other core(s) as needed.

> 现代 CPU 通常具有超过单个执行核心。*core* 是执行机器指令的单独且几乎完全独立的引擎。(在硅设计圈中，核心具有更广泛的含义，正如我们在[第 4 章](#07_9781119183938-CH04.XHTML)中所述。世界和具有八个核心的单位开始出现。每个核心都独立执行进程，但是所有内核都共享系统资源等内存。操作系统控制系统中所有内核的使用，就像它控制其他所有内容一样。操作系统通常以一个核心运行，并且包裹可根据需要将其处理到另一个核心。

The ARM11 CPU in the Raspberry Pi has only one core. Other ARM processors have as many as four. However, the nature of ARM hardware allows chip designers to create custom CPUs, and the latest ARM CPU—Cortex-A15—supports arbitrary numbers of cores in clusters of four if designers want them.

> Raspberry Pi 中的 ARM11 CPU 只有一个核心。其他手 ARM 处理器有多达四个。但是，ARM 硬件的性质允许芯片设计人员创建自定义 CPU，而最新的 ARM CPU-Cortex-A15 - 如果设计师想要的话，请在四个群集中提供任意数量的内核。

We’ll have more to say about how ARM CPUs and ARM-based single-chip systems are created in [Chapter 3](#06_9781119183938-ch03.xhtml).

> 关于如何在[第 3 章](#06_9781119183938-CH03.XHTML)中创建 ARM CPU 和基于 ARM 的单芯片系统的方式，我们将有更多的话要说。
