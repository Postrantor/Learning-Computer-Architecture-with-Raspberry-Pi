Chapter 5

# Programming

**COMPUTER HARDWARE AND** computer software are traditionally considered two separate continents on Planet Computing. The term `computer architecture` usually means hardware architecture, to the extent that a great many university-level computer architecture books don’t cover programming at all, much less cover the higher level discipline of software architecture and design.

> **计算机硬件和**计算机软件传统上被认为是行星计算上两个独立的大陆。`计算机体系结构` 一词通常指硬件体系结构，以至于很多大学级别的计算机体系结构书籍根本不涉及编程，更不涉及软件体系结构和设计的更高层次学科。

This may be a mistake, especially for pre-university students who have had no formal instruction in either hardware or programming. Separating the study of hardware and software into two disciplines is a convenience only. Anyone who has a serious interest in computing needs to study both. It’s too glib to say that software wouldn’t exist without hardware. The truth is that modern hardware requires software to design and manufacture it, and, more to the point, all computers (which are hardware) require software to make them operative and useful.

> **这可能是一个错误**，尤其是对于那些在硬件或编程方面没有受过正式培训的大学预科学生来说。将硬件和软件的研究分为两个学科只是一种方便。任何对计算机有浓厚兴趣的人都需要学习这两方面。说没有硬件软件就不存在，这太油嘴滑舌了。**事实是，现代硬件需要软件来设计和制造它，更重要的是，所有计算机(硬件)都需要软件来使其运行和有用**。

Keep in mind that this book is primarily about hardware. Teaching programming using specific languages and tools is best done in separate books, many of which already exist, especially for Python, which is in some sense the `default` language for the Raspberry Pi. What we’re going to do in this chapter is present a broad picture of the _idea_ of programming, with an eye towards giving you a head start on choosing a programming language and an overall approach to the challenge of building your own software.

> 请记住，这本书主要是关于硬件的。使用特定语言和工具进行编程教学最好在单独的书中完成，其中许多已经存在，尤其是 Python，在某种意义上，Python 是树莓派的 `默认` 语言。在本章中，我们将要做的是展示编程的全貌，着眼于让您在选择编程语言和构建自己的软件的挑战方面有一个良好的开端。

## Programming from a Height

By now you should understand that computers do what they do by performing a very large number of very small steps in carefully arranged sequences. (Flip back to [Chapter 2](#05_9781119183938-ch02.xhtml), `Recapping Computing,` if this isn’t clear to you.) The steps are called _machine instructions_, and we’ve spoken of them informally all along. They are the `atoms` of a computer program, and cannot be broken down into smaller units of action (see [Chapter 4](#07_9781119183938-ch04.xhtml)).

> 现在你应该明白了，**计算机是通过以精心安排的顺序执行大量非常小的步骤来完成它们的工作的**。(如果您不清楚，请翻回到[第 2 章](#05_9781119183938-ch02.xhtml)，`重新计算` 。)这些步骤被称为机器指令，我们一直在非正式地谈论它们。它们是计算机程序的 `原子` ，不能分解成更小的行动单元(参见[第 4 章](#07_9781119183938-ch04.xhtml))。

What we call _computer programming_ is the process of writing and arranging these steps, verifying that they do what we need them to do, and keeping them current over time as those needs evolve. These three components of the programming process are called _coding_, _testing_ and _maintenance_.

> 我们称之为 **`计算机编程` 的是编写和安排这些步骤的过程**，验证它们是否完成了我们需要它们做的事情，并随着这些需求的发展不断更新。编程过程的这三个组件称为 _coding_、_testing_ 和 _maintenance_。

Prior to coding, there has to be a design stage. Writing program code off the top of your head (and observing the consequent error messages) is useful while you’re learning a new programming language, but long-term it’s a losing strategy for writing any sort of software that must do a real job over a period of time. Computer programs of any significant size must be designed before the programmer writes the first of those many steps. Different people or groups may do the design work versus the programming work, especially for large software systems that span different computers across networks.

> **在编码之前，必须有一个设计阶段。**当你学习一种新的编程语言时，从头开始编写程序代码(并观察由此产生的错误信息)是有用的，但从长远来看，编写任何一种必须在一段时间内完成实际工作的软件都是一种失败的策略。任何大小的计算机程序都必须在程序员编写这些步骤中的第一步之前进行设计。不同的人或群体可以做设计工作，而不是编程工作，特别是对于跨网络跨不同计算机的大型软件系统。

Software design is a separate, necessary discipline on which programming depends. For the sort of simple programs you may write while you’re first learning programming, the design step may seem almost trivial. For larger systems, design may become the toughest challenge you’ll face during the entire project, and inadequate design will likely doom the project to failure.

> **软件设计是编程所依赖的一个独立的、必要的学科。**对于您在第一次学习编程时可能编写的简单程序，设计步骤看起来几乎微不足道。对于更大的系统，设计可能会成为整个项目中面临的最严峻的挑战，**设计不足可能会导致项目失败**。

### The Software Development Process

Irrespective of what programming language or tools you use, the process of software development follows a pretty consistent map, which is shown in Figure 5-1. It begins with an idea that solves some sort of problem. An idea is just an idea; once you begin fleshing it out and taking notes you’ve already stepped off square one and have begun designing your program.

> 无论您使用什么编程语言或工具，软件开发过程都遵循一个非常一致的映射，如图 5-1 所示。它从解决某种问题的想法开始。想法只是一个想法；一旦你开始充实它并做笔记，你就已经迈出了第一步，开始设计你的程序。

![[FIGURE 5-1:](#08_9781119183938-ch05.xhtml#rc05-fig-0001) A map of the software development process](./media/images/9781119183938-fg0501.png)

With some sort of design in hand (and there are a multitude of ways of performing software design) you sit down in front of your programming tools, open an editor window and begin writing actual program code. Although purists frown on the notion, it’s true that the design and coding stages are not completely distinct. It’s in the nature of the creative process that making an idea concrete generates not only insights about the idea but also new ideas. Especially while you’re still building your programming skills, coding may cause you to realise that something in your design won’t work or doesn’t serve the mission of the project. Going back to the design process temporarily isn’t exactly `following the map` but it may keep the entire project from going off the rails later on, leaving you with hundreds, thousands or (yes, it happens!) tens of thousands of lines of essentially useless code.

> 有了某种设计(并且有多种执行软件设计的方法)，您可以坐在编程工具前，打开编辑器窗口，开始编写实际的程序代码。虽然纯粹主义者不赞成这个概念，但设计和编码阶段并不是完全不同的。**创意过程的本质是，将想法具体化不仅会产生关于想法的见解，还会产生新的想法**。尤其是当你还在培养你的编程技能时，编码可能会让你意识到你的设计中有些东西不起作用或者不符合项目的任务。暂时回到设计过程并不完全是 `遵循地图` ，但它可能会阻止整个项目在以后偏离轨道，留下数百、数千或(是的，确实如此！)数万行基本无用的代码。

At some point you’ll have one or more files containing program code that represent a working program. This is called your _source code_. The next step is to turn your programming language loose on it as you build an executable program from the textual code files that you’ve written in your editor. The term `build` contains one or more steps that depend on the programming language and toolset that you’re using. For some languages, like Python, much of the build process happens `behind the scenes` , whereas for others, like C, you are required to explicitly invoke tools such as compilers and linkers (which are described later in the `[High-Level Languages](#08_9781119183938-ch05.xhtml#c05-sec-0007)` section). For now, think of it this way: the build process crunches your code and either gives it a (qualified) clean bill of health or presents you with a list of compile-time errors.

> 在某些时候，您将拥有一个或多个包含表示工作程序的程序代码的文件。这称为源代码(_source code_)。下一步是在从编辑器中编写的文本代码文件构建可执行程序时，放松编程语言。术语 `构建` 包含一个或多个步骤，这些步骤取决于您使用的编程语言和工具集。对于某些语言(如 Python)，大部分构建过程都发生在 `幕后` ，而对于其他语言(如 C)，则需要显式调用编译器和链接器等工具(稍后将在 `[高级语言](#08_9781119183938-ch05.xhtml#c05-sec-0007)` 一节中介绍)。现在，可以这样想：构建过程处理您的代码，要么给它一个(合格的)干净的健康账单，要么给您一个编译时错误列表。

---

> [!NOTE]

A _compile-time error_ is something in your code that prevents your toolset from creating an executable program. All programming languages have _syntax_; that is, a set of rules about what program elements are called and how they’re put together in your source code files. Violate that syntax, and you get an error. In statically typed languages, some errors will be type mismatches, which means a conflict between the type of data you’ve defined (text, numbers, etc.) and what your code is trying to do with it. Dynamically typed languages give you more leeway at compile time: type mismatches make themselves known at runtime, when the offending statement is executed. This is called a _runtime error_.

> 代码中的 _compile-time error_ 会阻止工具集创建可执行程序。所有编程语言都有 _syntax_；也就是说，关于调用什么程序元素以及如何将它们放在源代码文件中的一组规则。违反该语法，就会出现错误。在静态类型语言中，一些错误将是类型不匹配，这意味着您定义的数据类型(文本、数字等)与代码试图使用的数据类型之间存在冲突。动态类型语言在编译时为您提供了更多空间：当执行有问题的语句时，类型不匹配会**在运行时被发现，这称为 _runtime error_**。

Error messages provide hints as to what you did wrong, and a line in a source code text file represents the point at which your toolset noticed the error. This is not necessarily where the error itself lies! You’ll have to think a little about what you wrote and how it adheres to or violates your language’s syntax or type rules. While you’re learning, you’ll doubtless spend time digging through a syntax chart or reference on your chosen language. Once you’ve internalised the language, it will take a lot less time and effort to spot errors.

> 错误消息提供了关于您做错了什么的提示，源代码文本文件中的一行表示工具集注意到错误的点。这不一定是错误所在！你必须考虑一下你写的东西，以及它是如何遵守或违反你的语言语法或类型规则的。在你学习的过程中，你无疑会花时间仔细阅读你所选择语言的语法表或参考资料。一旦你将语言内化，你就可以花更少的时间和精力去发现错误。

Fixing errors requires you to return to the text editor, change the problem source code and save a new version of the file or files. After that, you build the program again (and probably again, for several or many more iterations) until your toolset no longer gives you a list of errors. Done!

> 修复错误需要您返回文本编辑器，更改问题源代码并保存文件的新版本。之后，您再次构建程序(可能还会进行多次或多次迭代)，直到工具集不再提供错误列表。完成！

Well, not exactly done. Not even close. Once you have a program that can be run, you have to run it and see what it does. With that you move to the testing stage, during which you evaluate your program’s behaviour against what you’ve set out in your design. The program may run but then crash, and if you’re fortunate your toolset will give you a run-time error providing some hints as to why. Even if it runs, the program may do unexpected things. This sort of problem is known as a _bug_.

> 嗯，还没有完全完成。甚至没有接近。一旦你有了一个可以运行的程序，你就必须运行它，看看它做什么。至此，您将进入测试阶段，在测试阶段，您将根据您在设计中设定的内容来评估程序的行为。程序可能会运行，但随后会崩溃，如果幸运的话，您的工具集会给您一个运行时错误，并提供一些原因提示。即使它运行，程序也可能会发生意想不到的事情。这类问题被称为 _bug_。

---

> [!NOTE]

The first person to use the term bug in the context of computing was Admiral Grace Hopper of the United States Navy, who found a dead moth stuck in a relay of an early electromechanical computer in 1947. Although technically a hardware rather than a software problem, Admiral Hopper’s moth kept her program from running correctly, and she said she had to `debug` the computer to make things work again. She taped the moth itself to her log book, where it remains to this day at the Smithsonian Institution. Since then, anything that keeps a program from running correctly is called a bug.

> 第一个在计算环境中使用 bug 这个词的人是美国海军上将格蕾丝·霍珀，他在 1947 年发现**一只死飞蛾卡在早期机电计算机的继电器中**。虽然从技术上讲，这是一个硬件问题，而不是软件问题，但海军上将霍珀的飞蛾使她的程序无法正常运行，她说她必须 `调试` 计算机，使其重新工作。她把飞蛾粘在了她的日志簿上，至今仍保存在史密森尼学会。从那时起，**任何阻止程序正常运行的行为都被称为 bug**。

Debugging software is an art and a discipline all to itself. Identifying a bug does not imply understanding what you actually did wrong in your source code. Working out how to fix a bug takes some study and sometimes a walk around the block to clear your head. Once you’ve figured out the problem (or _think_ you’ve figured out the problem) you again return to your code editor, make your changes and then rebuild the program.

> **调试软件本身就是一门艺术和一门学科**。识别错误并不意味着理解你在源代码中到底做错了什么。弄清楚如何修复一个 bug 需要一些研究，有时还需要绕着街区走一走，才能理清思路。一旦你解决了问题(或者认为你已经解决了问题)，你就再次回到代码编辑器，进行修改，然后重建程序。

Getting the bugs out of a program can take longer than writing the program itself, especially while you’re still learning the game. There will come a time when you realise that your list of bugs has all been repaired, and the program is finally doing useful things in the ways that you had planned. Now you’re done!

> **从程序中找出 bug 可能比编写程序本身需要更长的时间，尤其是在你还在学习游戏的时候**。总有一天，你会意识到你的错误列表已经全部修复，程序终于按照你计划的方式做了有用的事情。现在你完成了！

### Waterfall vs. Spiral vs. Agile(瀑布 vs. 螺旋 vs. 敏捷)

But you’re still not really done. One of the tenets of modern software development is that software is rarely if ever `done` in the sense that nothing more needs to be changed, now or ever. The programming process is inherently _iterative_—that is, it’s a series of feedback loops that take into account a program’s design goals, its bug list, and new insights about how what needs to be done could be done better.

> 但你还没有真正完成。现代软件开发的一个原则是，软件很少被 `完成` ，因为无论现在还是将来，都不需要再做任何改变。**编程过程本质上是反复的**——也就是说，它是一系列反馈循环，考虑到程序的设计目标、错误列表以及关于如何更好地完成需要做的事情的新见解。

Programming wasn’t always like this. In its early years, the software development process was often conceptualised as a sort of construction task like erecting an office building, in which the entire blueprint must be complete, fully understood and costed before the first shovel of dirt is thrown. In this world, user requirements are gathered and a detailed design document for a piece of software that meets these requirements is produced; the design is implemented in code and tested; all known bugs are fixed; and then the implementation phase is deemed complete and the project is placed into an ongoing maintenance mode. This linear sequence of steps is now called the _waterfall model_ because it proceeds inexorably from the top to the bottom. In the model’s purest incarnation, user requirements cannot be changed after the design document is underway, and the design document cannot be changed after coding has begun. If the users do not understand their own needs, or if they cannot communicate their needs to the designers, what they get in the end might not help them or, in some cases, can be worse than nothing at all.

> 编程并不总是这样。在其早期，软件开发过程通常被认为是一种建设任务，比如建造一栋办公楼，在其中，在第一铲土被抛出去之前，整个蓝图必须完整、充分理解并计算成本。在这个世界中，收集用户需求，并为满足这些需求的软件生成详细的设计文档；该设计在代码中实现并测试；所有已知的错误都已修复；然后，实施阶段被视为完成，项目进入持续维护模式。这个线性的步骤序列现在被称为 _瀑布模型_，因为它从上到下是不可阻挡的。在模型最纯粹的体现中，用户需求在设计文档开始后不能更改，设计文档在编码开始后也不能更改。如果用户不了解自己的需求，或者他们无法将自己的需求传达给设计师，那么他们最终得到的结果可能对他们没有帮助，或者在某些情况下，可能比什么都没有更糟。

After recognising the shortcomings of the waterfall model, software designers began to explore something a little more like what’s shown in [Figure 5-1](#08_9781119183938-ch05.xhtml#c05-fig-0001). The insight was that, realistically, many projects cannot be fully understood by _anyone_ before at least some code has been written. Programmers take the user requirements and create a simple, feature-limited prototype and let the users play with it. Based on user feedback, the programmers then expand the prototype or in some cases scrap it entirely and begin again, correcting initial misunderstandings even if they were fundamental to the design. After users see their requirements implemented in software, they will as often as not update their requirements to reflect the insights that playing with a prototype have triggered. The requirements, design and coding steps are visited not once but many times, going around in a loop much like that in [Figure 5-1](#08_9781119183938-ch05.xhtml#c05-fig-0001). The prototype grows by increments; these development methodologies, of which Barry Boehm’s spiral model is the best-known example, are therefore known as _incremental models_. Figure 5-2 shows the waterfall and spiral models side by side.

> 在认识到瀑布模型的缺点之后，软件设计师开始探索一些更像[图 5-1](#08_9781119183938-ch05.xhtml#c05-fig-0001) 中所示的东西。事实上，在至少编写了一些代码之前，很多项目都无法被任何人完全理解。程序员接受用户需求，创建一个简单的、功能有限的原型，让用户使用它。**基于用户反馈，程序员然后扩展原型，或者在某些情况下完全废弃原型，然后重新开始，纠正最初的误解，即使它们是设计的基础。**在用户看到他们的需求在软件中实现后，他们会经常更新他们的需求，以反映玩原型所引发的见解。需求、设计和编码步骤不是一次访问，而是多次访问，在一个类似于[图 5-1](#08_9781119183938-ch05.xhtml#c05-fig-0001) 的循环中循环；因此，这些开发方法(Barry Boehm 的螺旋模型是其中最著名的例子)被称为 `增量模型` 。图 5-2 并排显示了瀑布模型和螺旋模型。

![[FIGURE 5-2:](#08_9781119183938-ch05.xhtml#rc05-fig-0002) Waterfall model vs. spiral model](./media/images/9781119183938-fg0502.png)

Although traditional incremental models generally represent an improvement on the waterfall, they are heavyweight, with an emphasis on up-front planning and top-down management of the development process. From the mid-1990s onwards, a variety of lightweight incremental models emerged, which emphasised flexibility and responsiveness. These approaches came to be known as _agile software development_, or simply _agile_. The (commendably brief) Agile Manifesto, issued in 2001, summarises the goals of agile software development:

> 虽然传统的增量模型通常代表对瀑布的改进，但它们是重量级的，强调开发过程的前期规划和自上而下的管理。从 20 世纪 90 年代中期开始，出现了各种轻量级增量模型，强调灵活性和响应性。这些方法被称为 `agile software development` ，或者简称为 `agile` 。2001 年发布的《敏捷宣言》(非常简短)总结了敏捷软件开发的目标：

---

We are uncovering better ways of developing software by doing it and helping others do it. Through this work we have come to value:

> 我们正在发现更好的方法来开发软件，通过做它并帮助他人做它。通过这项工作，我们获得了价值：

- **Individuals and interactions** over processes and tools - **Working software** over comprehensive documentation - **Customer collaboration** over contract negotiation - **Responding to change** over following a plan

> -**个人和互动**超过流程和工具**工作软件**超过全面文档**客户协作**超过合同谈判**响应更改**超过计划

That is, while there is value in the items on the right, we value the items on the left \[the bolded items] more.

> 也就是说，虽然右边的项目有价值，但我们更看重左边的项目。

Agile development is a `big picture` strategy, and the fine details of how the work is actually done may vary between teams and projects. Common agile practices include:

> 敏捷开发是一种 `大局观` 策略，团队和项目之间实际完成工作的细节可能有所不同。常见的敏捷实践包括：

- **Timeboxing:** A large project is divided into discrete smaller projects of fixed duration, each with its own schedule and deliverables, simplifying short-term time management.
- **Test-driven development:** A developer first produces a unit test for a new feature, and then writes the simplest good-quality implementation that passes the test.
- **Pair programming:** Two programmers (the driver and the observer) work together at a single terminal, providing continuous code review and a separation between the strategic and tactical aspects of programming.
- **Frequent or continuous integration:** Developers regularly commit their changes to the shared code base, avoiding `integration hell`.
- **Frequent stakeholder interaction:** Regular releases are made and feedback sought, providing early notice of requirement changes.
- **Scrum meetings:** Short daily team meetings promote team cohesion and provide a forum for team members to share progress, plans and impediments.

> - **时间表：**大型项目分为固定工期的离散小型项目，每个项目都有自己的时间表和可交付成果，简化了短期时间管理。
> - **测试驱动开发：**开发人员首先为新功能生成单元测试，然后编写通过测试的最简单的高质量实现。
> - **配对编程：**两名程序员(驾驶员和观察员)在一个终端共同工作，提供持续的代码审查，并将编程的战略和战术方面分开。
> - **频繁或持续集成：**开发人员定期将其更改提交给共享代码库，避免 `集成地狱` 。
> - **频繁的利益相关者互动：**定期发布并寻求反馈，提供需求变更的早期通知。
> - **Scrum 会议：**简短的每日团队会议促进团队凝聚力，并为团队成员提供分享进展、计划和障碍的论坛。

The following are two of the best-known agile methodologies:

> 以下是两种最著名的敏捷方法：

- **Scrum:** A framework in which development proceeds as a sequence of sprints, each allocated a certain limited amount of time. (This is called _timeboxing_.) At the start of each sprint, outstanding tasks from the project backlog are prioritised, and a subset is selected to form the sprint backlog. Daily scrum meetings are held during the sprint. At the end of each sprint, the product should be releasable (albeit incomplete if there are tasks remaining on the project backlog).
- **Extreme programming:** A variety of practices—including pair programming, and continuous integration, testing and deployment—that are, in a sense, `extreme` variants of accepted best practices. The development process consists of four mutually supporting activities: coding, testing, listening (that is, gathering user feedback) and designing. The overriding goal is to remain responsive to requirement changes.

> - **Scrum:**一个框架，在该框架中，开发以一系列冲刺的形式进行，每个冲刺都分配了一定的有限时间。(这被称为 *timeboxing*)在每个 sprint 开始时，项目待办事项列表中的未完成任务被优先排序，并选择一个子集来形成 sprint 待办事项列表。每日 scrum 会议在冲刺期间举行。在每个 sprint 结束时，产品应该是可发布的(如果项目待办事项列表中还有任务，尽管不完整)。
> - **极限编程：**各种实践，包括配对编程、持续集成、测试和部署，在某种意义上，这些实践是公认最佳实践的 `极限` 变体。开发过程包括四个相互支持的活动：编码、测试、倾听(即收集用户反馈)和设计。首要目标是保持对需求变化的响应。

One way to think about agile development is that it does not so much design software as evolve it, through continuous feedback from users triggering continuous improvement by programmers. In a way, the design emerges from experience. Although old-school programmers sometimes consider the agile process chaotic, across a range of problem domains it appears to produce better software faster than either the waterfall or traditional incremental models.

> 思考敏捷开发的一种方式是，与其说它是设计软件，不如说它是**通过用户的持续反馈引发程序员的持续改进来发展软件**。在某种程度上，设计是从经验中产生的。尽管老派程序员有时认为敏捷过程是混乱的，但在一系列问题领域，它似乎比瀑布模型或传统的增量模型更快地生成更好的软件。

### Programming in Binary

Programming is an old, hard game. In the very beginning, there were no tools, and programmers wrote sequences of machine instructions as binary numbers. These could then be loaded from paper tape or punch cards or, particularly in the case of `bootstrap` startup code, written into memory manually through toggle switches on the CPU cabinet front panel. An `up` toggle indicated a binary 1, and a `down` toggle indicated a binary 0. Programmers would flip the row of toggles until it reflected a binary machine instruction, and then push a button to store the binary pattern in memory. Then they did it again, flipping switches and storing the next instruction, and so on. The rows of switches you may have seen in movies on the control panels of gigantic old computers were for exactly this purpose. Front panel switches lingered until the late 1970s, particularly on cost-sensitive hobbyist computer systems like the Altair 8800, but better tools have long since made them unnecessary.

> 编程是一个古老而艰难的游戏。一开始，没有工具，程序员把机器指令序列写成二进制数。然后，可以从纸带或穿孔卡加载这些文件，特别是在 `引导` 启动代码的情况下，通过 CPU 机柜前面板上的拨动开关手动将其写入内存。`向上` 切换表示二进制 1，而 `向下` 切换则表示二进制 0。程序员会翻转一行开关，直到它反映出二进制机器指令，然后按下按钮将二进制模式存储在内存中。然后他们又做了一次，翻转开关，存储下一条指令，等等。你可能在电影中看到的巨大老式电脑控制面板上的一排排开关正是为了这个目的。前面板开关一直持续到 20 世纪 70 年代末，特别是在像 Altair 8800 这样对成本敏感的业余计算机系统上，但更好的工具早就让它们变得不必要了。

Writing a program in binary was done by first writing a description of a machine instruction, and then looking up the binary pattern for that instruction. For simple programs on machines with simple instructions sets, this was time-consuming but not terribly difficult. The manufacturers of early single-chip central processing units (CPUs) like the Motorola 6800 and Zilog Z80 would publish reference cards with tables showing the hex encoding for all instructions in common forms. The need to write more complex programs, on CPUs with more complex instruction sets, quickly turned binary programming into slow, painful drudgery that cost far more in time and trouble than it was worth.

> 用二进制编写程序是通过首先编写机器指令的描述，然后查找该指令的二进制模式来完成的。对于具有简单指令集的机器上的简单程序，这很耗时，但并不十分困难。摩托罗拉 6800 和 Zilog Z80 等早期单芯片中央处理单元(CPU)的制造商会发布参考卡，其中的表格显示了通用形式的所有指令的十六进制编码。需要在具有更复杂指令集的 CPU 上编写更复杂的程序，很快将二进制编程变成了缓慢而痛苦的苦差，花费的时间和麻烦远远超过了它的价值。

### Assembly Language and Mnemonics(汇编语言和助记符)

As early computers came to be used by a broader audience of academic and commercial users, simple tools were developed to automate the mechanical aspects of the programming process. As described in [Chapter 4](#07_9781119183938-ch04.xhtml), a typical machine instruction consists of an _opcode_ (literally an operation code, describing what sort of operation the instruction performs) and zero or more _operands_ (which define where a data processing instruction finds its input data and stores its result, or where a branch instruction branches to). If you assign a short, notionally meaningful name called a _mnemonic_ to each opcode, and come up with a textual convention for specifying the operands, code becomes much easier to write. For example, a machine instruction that moves data from one place in the computer to another might use `mov` as the mnemonic for its opcode.

> 随着早期计算机被更广泛的学术和商业用户所使用，开发了简单的工具来自动化编程过程的机械方面。如[第 4 章](#07*9781119183938-ch04.xhtml)所述，典型的机器指令由一个 _opcode_ (字面上是一个操作代码，描述指令执行的操作类型)和零个或多个 *operand*(定义数据处理指令找到其输入数据并存储其结果的位置，或分支指令分支到的位置)组成。如果您为每个操作码指定一个简短的、在理论上有意义的名称，称为 `mnemonic`，并提出一个用于指定操作数的文本约定，代码将变得更容易编写。例如，将数据从计算机中的一个位置移动到另一个位置的机器指令可能使用 `mov` 作为其操作码的助记符。

Following is a short sequence of machine instructions expressed as human-readable opcode mnemonics and operands. The mnemonics are on the left, and the operands are to the right of the mnemonics. There are several kinds of operands, including numbers, memory addresses, register names and qualifiers of various sorts. Any single opcode may have more than one operand, or none at all.

> 以下是表示为人类可读操作码助记符和操作数的机器指令的短序列。助记符在左侧，操作数在助记符的右侧。有几种操作数，包括数字、内存地址、寄存器名和各种类型的限定符。任何一个操作码都可以有多个操作数，或者根本没有。

```
    mov edx,edi
    cld
    repne scasb
    jnz Error
    mov byte [edi-1],10
    sub edi,edx
```

A software utility can translate the mnemonics and operand descriptions directly into binary, saving the programmer the work of doing the translation manually. This utility is called an _assembler_, as it does the work of assembling a binary machine instruction from information given in the mnemonic and operand descriptions; the textual description of a machine code program is called _assembly language_. ([Chapter 4](#07_9781119183938-ch04.xhtml) briefly mentioned assembly language.)

> 软件实用程序可以将助记符和操作数描述直接翻译成二进制，从而省去程序员手动翻译的工作。此实用程序称为 *assembler*，因为它根据助记符和操作数描述中给出的信息组装二进制机器指令；**机器代码程序的文本描述称为汇编语言**。([第 4 章](#07_9781119183938-ch04.xhtml)简要提到了汇编语言。)

Although nominally human-readable, assembly language is terse and reveals little about what the instructions are intended to accomplish. Programmers often include comments in their assembly language source code files to describe briefly an instruction’s purpose:

> 尽管名义上是人类可读的，但汇编语言是简洁的，很少透露指令的意图。程序员通常在汇编语言源代码文件中包含注释，以简要描述指令的用途：

```
    mov edx,edi            ;Copy starting address into EDX
    cld                    ;Set search direction to up-memory
    repne scasb            ;Search for null (0 char) in string at EDI
    jnz Error              ;REPNE SCASB ended without finding null
    mov byte [edi-1],10    ;Store an EOL where the NUL used to be
    sub edi,edx            ;Subtract position of NUL from start address
```

> [!NOTE]
> that comments describe not only the instruction but also its role within the program. In spite of any marketing hype, _no computer language is self-explanatory_. All computer languages allow comments, and you will always need comments to remind yourself what a given line of code is doing in the larger scheme of things. This is especially true after you’ve set a program aside long enough that its details are no longer fresh in your mind.
> 注释不仅描述了指令，还描述了它在程序中的作用。尽管有任何营销炒作，_没有一种计算机语言是不言自明的_。所有的计算机语言都允许注释，而且你总是需要注释来提醒自己给定的代码行在更大的事物方案中做了什么。当你把一个程序放在一边足够长以致于它的细节在你的脑海中不再新鲜时，尤其如此。

### High-Level Languages

Assembly language still exists, and you can write assembly language programs for the Raspberry Pi with the GNU tools that come free with the Raspbian operating system and all other flavours of Linux. We’ll have more on this tool set later on, in the section entitled `[A Tour of the GNU Compiler Collection Toolset](#08_9781119183938-ch05.xhtml#c05-sec-0056).` Unless you’re trying to eke every last drop of performance out of a system, however, it’s a lot more work than it needs to be. Assembly language describes the behaviour of a program at a low level of abstraction: one line of assembly language is translated by the assembler directly to one single machine instruction. Early on, computer scientists developed more sophisticated, expressive languages in which one textual command (generally called a _statement_) corresponded to a sequence of machine instructions. Such languages were called high-level languages because they allowed the programmer to describe the desired behaviour of a program at a higher level of abstraction than the very literal assembly language could.

> 汇编语言仍然存在，您可以使用 Raspberry Pi 的 GNU 工具编写汇编语言程序，这些工具随 Raspbian 操作系统和所有其他风格的 Linux 免费提供。稍后，我们将在标题为 `[GNU 编译器集合工具集教程](#08_9781119183938-ch05.xhtml#c05-sec-0056)` 的部分中详细介绍该工具集。然而，除非您试图从系统中获得最后一点性能，否则它需要做的工作要多得多。汇编语言在低抽象层次上描述程序的行为：**一行汇编语言被汇编程序直接翻译成一条机器指令**。早期，计算机科学家开发了更复杂、更具表现力的语言，其中一个文本命令(通常称为 _statement_)对应于一系列机器指令。这种语言被称为高级语言，因为它们允许程序员在比字面汇编语言更高的抽象级别上描述程序的期望行为。

---

> [!NOTE]

The term GNU refers to a large group of free and open-source software (FOSS) products, from assemblers to compilers to the Linux operating system itself, which is formally named GNU Linux. The Term `GNU` is an acronym, for `GNU’s Not Unix,` which is how the computer scientist Richard Stallman meant to indicate that he was writing an operating system called GNU that was similar to Unix, but not a literal clone.

> GNU 一词指的是一大群自由和开源软件(FOSS)产品，从汇编程序到编译器，再到 Linux 操作系统本身，正式名称为 GNU Linux。术语 `GNU` 是 `GNU is Not Unix` 的首字母缩略词，这就是计算机科学家理查德·史泰尔曼(Richard Stallman)表示**他正在编写一个名为 GNU 的操作系统的意思，该操作系统与 Unix 相似，但不是字面上的克隆**。

The earliest high-level language to see wide use was FORTRAN, developed at IBM by a team led by John Backus in the early 1950s, and made available to IBM’s customers in 1957. FORTRAN (from FORmula TRANslator) reduced the number of statements necessary in a program by a factor of 20. The classic `Hello, world` program written in early FORTRAN was simplicity itself:

> 最早被广泛使用的高级语言是 FORTRAN，由约翰·巴克斯领导的团队于 1950 年代早期在 IBM 开发，并于 1957 年提供给 IBM 的客户。FORTRAN(来自 FORmula TRANslator)**将程序中必需的语句数减少了 20 倍**。早期 FORTRAN 语言编写的经典 `Hello，world` 程序本身就很简单：

```fortran
    PRINT *, `Hello, world!`
    END
```

In addition to the obvious benefit of reducing the textual size of a program’s source code and making it easier to read, FORTRAN hid the details of the workings of the computer from the programmer. Programmers did not need to know how the CPU controlled the various mechanisms of the system printer, if all they wanted to do was print a line of text. The word PRINT was translated into a middling number of machine instructions that moved text across a cable to the printer and told the printer to print that text to paper. Furthermore, if the machine instructions for printing text to paper were always the same, it was a waste of effort to include them in every single program. The machine instructions for printing were necessary, but they were stored in a separate file. The utility that translated FORTRAN statements to machine instructions compiled the machine instructions from several sources (some of which would later be called libraries) to form the final executable program. The translator program was thus called a compiler.

> 除了减少程序源代码的文本大小并使其更易于阅读这一明显好处之外，FORTRAN 还**向程序员隐藏了计算机工作的细节**。如果程序员只想打印一行文本，他们不需要知道 CPU 如何控制系统打印机的各种机制。PRINT 一词被翻译成中等数量的机器指令，这些指令通过电缆将文本传送到打印机，并告诉打印机将文本打印到纸上。此外，如果将文本打印到纸上的机器指令总是相同的，那么将它们包含在每个程序中是一种浪费。印刷的机器说明是必要的，但它们存储在一个单独的文件中。将 FORTRAN 语句翻译成机器指令的实用程序从多个源(其中一些后来被称为库)编译机器指令，以形成最终的可执行程序。**翻译程序因此被称为编译器。**

FORTRAN was developed and used primarily for mathematical and scientific computing. It was quickly followed by COBOL, created by a group led by Admiral Grace Hopper (of `bug` fame) in 1960. Hopper’s COmmon Business Oriented Language went on to become one of the most-used languages in the history of computing. The minimal `Hello, world!` in COBOL is a little more complex than in FORTRAN:

> FORTRAN 语言主要用于数学和科学计算。1960 年，由海军上将格雷斯·霍珀(以 `bug` 闻名)领导的一个小组创建了 COBOL。Hopper 的通用面向业务语言后来成为计算史上使用最多的语言之一。COBOL 语言中最简单的 `Hello，world！` 比 FORTRAN 语言要复杂一点：

```cobol
    IDENTIFICATION DIVISION.
    PROGRAM-ID.HELLO-WORLD.
    PROCEDURE DIVISION.
    DISPLAY `Hello, world!`
		STOP RUN.
```

One of COBOL’s goals was to make program source code easier to read. It strove to put everything right there in front of the programmer in plain language. Why? A fair bit of long-horizon thinking went into COBOL, including the insight that long-term use of COBOL programs would require maintenance by different programmers over time, each of whom would have to learn how a program worked so it could be fixed or extended. There was thus value in making COBOL programs as easy to understand as possible. Long-horizon thinking definitely worked, and COBOL remained in common use on mainframe computers (that is, large systems designed for centralised use) for almost 40 years. COBOL still sees occasional use on legacy mainframe systems.

> COBOL 的目标之一是使程序源代码更易于阅读。它努力用通俗易懂的语言把一切都放在程序员面前。为什么？COBOL 有相当多的长远思考，包括**长期使用 COBOL 程序需要不同的程序员进行长期维护**，每个程序员都必须学习程序的工作原理，以便对其进行修复或扩展。因此，使 COBOL 程序尽可能容易理解是有价值的。长期思维肯定奏效了，COBOL 在大型计算机(即为集中使用而设计的大型系统)上仍然普遍使用了近 40 年。COBOL 仍然偶尔在遗留的大型机系统上使用。

Prior to the mid-1960s, computers were _batch-oriented_ systems. This means that programmers wrote their programs on paper, entered them to a stack of Hollerith punch cards, and handed the cards to the technicians who operated the mainframe systems in that era. (Figure 5-3 shows a punch card containing a FORTRAN statement.) The technicians would queue up stacks of cards, and drop them into card readers when a stack’s turn came. The card readers would read the cards and submit the code they contained to be compiled and then executed on the mainframe. The mainframe would either print a list of compiler errors or (if the program had compiled correctly) the program’s results. The printout would be stored with the stack of punch cards and handed back to the programmer some time later, depending on how busy the mainframe was and how many stacks were waiting their turn.

> 在 20 世纪 60 年代中期之前，计算机是面向批处理的系统。这意味着程序员将他们的程序写在纸上，输入到一堆霍尔瑞斯穿孔卡片中，然后将卡片交给那个时代操作大型机系统的技术人员。(图 5-3 显示了一张包含 FORTRAN 语句的穿孔卡片。)技术人员会将一摞卡片排成队列，当轮到一摞时，将它们放入读卡器。读卡器将读取卡片，并提交其中包含的代码，以进行编译，然后在主机上执行。大型机要么打印编译器错误列表，要么(如果程序编译正确)打印程序结果。打印输出将与一堆穿孔卡片一起存储，并在一段时间后交给程序员，这取决于主机有多忙以及有多少堆叠等待轮到他们。

![[FIGURE 5-3:](#08_9781119183938-ch05.xhtml#rc05-fig-0003) A punch card from a 1970s FORTRAN program](./media/images/9781119183938-fg0503.png)

By the mid-1960s, the price of computers, printers and card punches was falling to the point where universities and even the occasional secondary school could afford them. Terminals could be placed outside the `glass walls` of the computer room itself, allowing people other than technicians to submit programs. At first, these terminals were Teletype machines or IBM terminals incorporating their Selectric printing technology. The Teletypes could punch and read paper tape, and many of the IBM Selectric terminals had card readers attached. Dozens of terminals could be attached to a single mainframe computer through a mechanism called _time sharing_, in which the mainframe would give each terminal a little slice of time to work in round-robin style. Each slice might be a fraction of a second, but that was enough time to read a keystroke or print a character. Unless the system got too busy, programmers sitting at the terminals had a convincing illusion that they had the entire machine to themselves.

> 到 20 世纪 60 年代中期，电脑、打印机和打卡机的价格已经下降到大学甚至偶尔的中学都能负担得起的程度。终端可以放置在计算机室本身的 `玻璃墙` 外面，允许技术人员以外的人提交程序。起初，这些终端是电传打字机或 IBM 终端，结合了他们的选择性打印技术。电传打字机可以打孔和读取纸带，许多 IBM Selectric 终端都配有读卡器。数十个终端可以通过一种称为 _time sharing_ 的机制连接到一台大型计算机上，在这种机制中，大型计算机会给每个终端一小段时间，以循环方式工作。每个片段可能只有一秒钟的一小部分，但这足够用来读取击键或打印字符。除非系统太忙，否则坐在终端的程序员会产生一种令人信服的错觉，认为他们拥有整个机器。

Selectric terminals with card readers were still used mostly for submitting batch jobs to mainframes, but the presence of keyboards allowed something new: interactive computing. A programmer could type a sequence of lines comprising a simple program, and then submit them for immediate compilation and execution, without having to use punch cards. On a good time-sharing system the response time was almost immediate.

> 带有读卡器的选择性终端仍然主要用于向大型机提交批量作业，但键盘的出现允许了一些新的东西：交互式计算。程序员可以键入包含一个简单程序的一系列行，然后提交它们以供立即编译和执行，而无需使用穿孔卡片。在一个好的分时系统中，响应时间几乎是即时的。

In 1964, two researchers at Dartmouth College, John Kemeny and Thomas Kurtz, designed a programming language specifically for use by students at interactive terminals. Their Beginner’s All-Purpose Symbolic Instruction Code (BASIC) language owed a lot to FORTRAN and could be used for many of the same things. A BASIC program could consist of a single line, which reduced the `Hello, world!` test program to something close to a minimum:

> 1964 年，达特茅斯学院的两位研究人员约翰·凯门尼(John Kemeny)和托马斯·库尔茨(Thomas Kurtz)设计了一种编程语言，专门供学生在交互式终端上使用。他们的初学者通用符号指令代码(BASIC)语言在很大程度上归功于 FORTRAN，可以用于许多相同的事情。BASIC 程序可以由一行组成，这将 `Hello，world！` 测试程序减少到接近最小值：

```
    10 PRINT `HELLO, WORLD!`
```

BASIC grew popular at universities, and popularity became ubiquity when personal computers appeared in the mid-1970s. BASIC was easy to implement, even on very simple computers, and easy to learn. Through the end of the 1970s and into the early 1980s, BASIC was often the only language available to personal computer owners. IBM even put a version of BASIC in read-only memory (ROM) on its seminal IBM PC in 1981. It may still be true that more people have been introduced to programming through BASIC than any other single language.

> BASIC 在大学里越来越受欢迎，当个人电脑在 20 世纪 70 年代中期出现时，BASIC 就变得无处不在。BASIC 很容易实现，即使在非常简单的计算机上也很容易学习。从 20 世纪 70 年代末到 80 年代初，BASIC 一直是个人电脑用户唯一可以使用的语言。1981 年，IBM 甚至将 BASIC 的一个版本放在其开创性的 IBM PC 上的只读存储器(ROM)中。通过 BASIC 学习编程的人可能比任何其他单一语言都多。

### Après BASIC, Le Deluge

FORTRAN, COBOL and BASIC represent the deep roots of three cultures within computing: scientific, business and educational. They were not the only programming languages within those cultures. Thousands of programming languages have been designed and tried, nearly all of them now forgotten or used only by small groups of diehard enthusiasts and preservationists.

> **FORTRAN、COBOL 和 BASIC 代表了计算领域三种文化的深厚根基：科学、商业和教育。**它们不是这些文化中唯一的编程语言。成千上万的编程语言已经被设计和尝试过，几乎所有的语言现在都被遗忘了，或者只有少数铁杆爱好者和保护主义者使用。

These were not wasted efforts. Most languages are designed around a specific idea, often a new take on an existing idea and sometimes a new idea entirely. Here are a few early examples:

> 这些努力并没有白费。大多数语言都是围绕一个特定的想法来设计的，通常是对现有想法的新的理解，有时是完全新的想法。下面是一些早期的例子：

- Lisp (from LISt Processor) appeared at MIT in 1958, to explore the use of lambda calculus (a mathematical mechanism for expressing computation in terms of functions), recursion and tree-structured data.
- Pascal was created by Swiss researcher Niklaus Wirth in 1970 to explore structured programming and data structures. Wirth later created the similar languages Modula-2 and Oberon to explore his take on modular programming.
- In 1972, Bell Labs computer scientist Dennis Ritchie defined the C language (so named because it replaced the now-vanished B language, which in turn was based on Martin Richards’ BCPL, which happily is available on the Raspberry Pi) as a sort of CPU-independent higher-level assembly language. A key motivator for C was to allow easy implementation of the Unix operating system on different hardware architectures, and it remains a popular language for system-level programming. The Linux kernel used on the Raspberry Pi is written almost entirely in C.
- Researchers at Xerox’s PARC research lab developed the Smalltalk language during their exploration of object-oriented programming (OOP) concepts. (Read more about OOP in the section entitled `[Object-Oriented Programming](#08_9781119183938-ch05.xhtml#c05-sec-0051)`.) First released in 1980, Smalltalk lives on today mostly through an open-source implementation called Squeak. Squeak may be run on the Raspberry Pi.

> - Lisp(来自 LISt 处理器)于 1958 年出现在麻省理工学院，旨在探索 lambda 演算(一种用函数表示计算的数学机制)、递归和树结构数据的使用。
> - Pascal 由瑞士研究人员 Niklaus Wirth 于 1970 年创建，旨在探索结构化编程和数据结构。Wirth 后来创建了类似的语言 Modula-2 和 Oberon，以探索他对模块化编程的看法 1972 年，贝尔实验室的计算机科学家丹尼斯·里奇(Dennis Ritchie)将 C 语言定义为一种独立于 CPU 的高级汇编语言(之所以如此命名，是因为它取代了现在已经消失的 B 语言，而 B 语言又是基于马丁·理查兹(Martin Richards)的 BCPL，这很高兴可以在 Raspberry Pi 上使用)。**C 的一个主要动机是允许在不同的硬件架构上轻松实现 Unix 操作系统，并且它仍然是系统级编程的流行语言**。Raspberry Pi 上使用的 Linux 内核几乎完全用 C 语言编写。
> - 施乐 PARC 研究实验室的研究人员在探索**面向对象编程(OOP)概念时开发了 Smalltalk 语言**。(在题为 `[面向对象编程](#08_9781119183938-ch05.xhtml#c05-sec-0051)` 的章节中了解有关 OOP 的更多信息。)Smalltalk 于 1980 年首次发布，如今主要通过一个名为 Squeak 的开源实现而生存。Squeak 可能在树莓派上运行。

The insight to be taken from this is that different challenges require different approaches and, more fundamentally, that you have to try things to see what works. Computer science, like all science, builds on and sometimes abandons earlier knowledge. All languages in use today descend from earlier languages and earlier, simpler versions of themselves. C++ and Objective C are very nearly supersets of C. Pascal in 2014 draws on Wirth’s later languages, as well as FORTRAN and C. Ada was developed as a rigorously robust version of Pascal.

> 从中可以看出，不同的挑战需要不同的方法，更重要的是，你必须尝试一些东西，看看什么是有效的。计算机科学和所有科学一样，建立在早期知识的基础上，有时会抛弃早期知识。今天使用的所有语言都是从早期语言和早期更简单的语言版本演变而来的。C++ 和 Objective C 几乎是 C 的超集。Pascal 在 2014 年借鉴了 Wirth 后来的语言，以及 FORTRAN 和 C。Ada 是作为 Pascal 的严格健壮版本开发的。

If you intend to be a programming enthusiast, develop the habit of experimenting with as many different computer languages as you can. Being multilingual in programming languages has another, more subtle benefit: you’ll be better able to identify the common ideas used across languages, which makes learning new languages in the future even easier.

> 如果你想成为编程爱好者，养成尽可能多地尝试不同计算机语言的习惯。在编程语言中使用多语言还有另一个更微妙的好处：你将能够更好地识别跨语言使用的共同思想，这使得未来学习新语言更加容易。

### Programming Terminology

Before we go on, it may be helpful to sketch out what a typical program looks like conceptually. We can’t cover all current terminology in one chapter in one book, just as we can’t explain any particular programming language in detail. Instead, our goal is to define a few terms that we’re going to use for the rest of this chapter (and elsewhere in this book). A word of caution: much of what we present here relates specifically to imperative programming languages such as C and Python, which model computation as a sequence of discrete steps that modify state. Functional programming languages, such as Haskell, model computation in terms of functions, and are beyond the scope of this chapter. In Figure 5-4 we’ve sketched out a simple and very generic computer program and its most important components. There are a lot of details that will have to wait until later. Objects, for example, are vital in modern programming, but they don’t summarise well in 25 words or less.

> 在我们继续之前，从概念上勾勒出一个典型程序的样子可能会有所帮助。我们不能在一本书的一章中涵盖所有当前的术语，就像我们不能详细解释任何特定的编程语言一样。相反，我们的目标是定义一些我们将在本章其余部分(以及本书其他部分)使用的术语。需要注意的是：我们在这里介绍的很多内容都与命令式编程语言(如 C 和 Python)有关，这些语言将计算建模为一系列修改状态的离散步骤。函数式编程语言，如 Haskell，根据函数建模计算，超出了本章的范围。在图 5-4 中，我们描绘了一个简单而通用的计算机程序及其最重要的组件。有很多细节需要等到以后。例如，对象在现代编程中至关重要，但它们不能用 25 个字或更少的字来概括。

![[FIGURE 5-4:](#08_9781119183938-ch05.xhtml#rc05-fig-0004) Fundamental programming terminology](./media/images/9781119183938-fg0504.png)

Here are the concepts you need to be familiar with right now:

> 以下是您现在需要熟悉的概念：

- **Variable:** A named storage location whose value may change during execution. In contrast, a constant is a named or unnamed value that cannot be changed during execution.

> - **变量：**一个命名的存储位置，**其值在执行过程中可能会更改**。相反，**常量是在执行期间不能更改的已命名或未命名值**。

- **Expressions:** These combine the values of one or more variables and constants using operators to compute a result. In the expression `a+b*4`, `a` and `b` may be either variables or constants (depending on context), `4` is a constant, and `+` and `*` are operators.

> - **表达式：**这些表达式使用运算符组合一个或多个变量和常量的值以计算结果。在表达式 `a+b*4` 中，`a` 和 `b` 可以是变量或常量(取决于上下文)，`4` 是常量，`+` 和 `*` 是运算符。

- **Statements:** Sequential units of action. The simplest example in most languages is an assignment of the result of an expression to a variable; more complex statements can be built by concatenating together simpler statements, or by using conditional and looping constructs like `if` and `while`.

> - **声明：\*\***连续的行动单位**。大多数语言中最简单的例子是将表达式的结果赋值给变量；更复杂的语句可以**通过将更简单的语句串联在一起\*\*，或者通过使用条件和循环构造(如 `if` 和 `while` )来构建。

- **Functions (sometimes called procedures or subroutines):** Named blocks of code that may or may not return a value. Variables that are defined within a function are only accessible from inside the function and are said to be _local_ to it. Local variables are generally stored in the CPU register file or on a stack; the stack also stores function return addresses and preserves values for which there is no room in the register file. A function can call another function, meaning that the flow of control takes a temporary detour into the function, returning when it has finished its work.

> - **函数(有时称为过程或子程序)：**可能返回或不返回值的命名代码块。在函数中定义的变量只能从函数内部访问，并被称为本地变量。本地变量通常存储在 CPU 寄存器文件或堆栈中；堆栈还存储函数返回地址，并保留寄存器文件中没有空间的值。一个函数可以调用另一个函数，这意味着控制流暂时绕道进入该函数，在完成工作后返回。

Variables that are defined outside any function are said to be _global_ and are accessible from (almost) anywhere.

> **在任何函数外部定义的变量都被称为 _global_**，并且可以从(几乎)任何地方访问。

Some languages, including C, require all statements to be inside a function. The `main` function, which is called by the system when execution starts, marks the entry point to the program. Other languages, including Python, allow statements outside functions; execution starts with the first such statement in the program file.

> **包括 C 在内的一些语言要求所有语句都在函数内**。**`main` 函数在执行开始时由系统调用，它标记程序的入口点。其他语言，包括 Python，允许函数外的语句；执行从程序文件中的第一条这样的语句开始。**

- **Arguments:** Values passed to a function from its caller. Parameters are special-purpose local variables that receive the argument values when execution of the function begins. In this Python example:
  `a`, `b` and `c` are parameters, whereas `1`, `2` and `3` are arguments.

```python
def foo(a, b, c): return a*b+c
print foo(1, 2, 3)
```

> - **参数：**从调用方传递给函数的值。参数是特殊用途的局部变量，在函数开始执行时接收参数值。在此 Python 示例中：
>   `a`、`b` 和 `c` 是 _parameters_，而 `1`、`2` 和 `3` 是 _arguments_。

- **Heap:** A pool of memory where programs may allocate memory to store arbitrary-sized data items. _Pointers_ are values that describe the location of data in the heap, generally as a memory address.

> -**堆：**程序可以在其中**分配内存以存储任意大小的数据项的内存池**。_指针_ 是描述堆中数据位置的值，通常作为内存地址。

## How Native-Code Compilers Work

The job of a native-code compiler is to take a source code file written in a high-level language and generate an equivalent object code file composed of binary machine instructions. (Do not confuse the terms `object code` and `object,` as used in OOP. The two are unrelated.)

> 本机代码编译器的工作是获取用高级语言编写的源代码文件，并生成由二进制机器指令组成的等效目标代码文件。(不要混淆 OOP 中使用的术语 `对象代码` 和 `对象` 。两者不相关。)

Compilers process their input in several steps or passes. Although object code is the ultimate goal, the compiler may write one or more other files to disk along the way, and may delete such temporary files when they’re no longer needed.

> 编译器分几个步骤或过程处理输入。尽管目标代码是最终目标，编译器可能会将一个或多个其他文件写入磁盘，并在不再需要这些临时文件时删除这些文件。

The compilation process can be broken down into the following steps:

- Preprocessing (optional)
- Lexical analysis
- Parsing
- Semantic analysis
- Intermediate code generation
- Optimisation
- Target code generation

> 编译过程可分为以下步骤：
>
> - 预处理(可选)
> - 词汇分析
> - 分析
> - 语义分析
> - 中间代码生成
> - 优化
> - 目标代码生成

---

> [!NOTE]

Many of the preceding steps (particularly the first few) are common to both native-code and bytecode compilers, which are covered later in this chapter in the `[Bytecode Interpreted Languages](#08_9781119183938-ch05.xhtml#c05-sec-0028)` section and the sections that follow it; we’ll refer back to this section during that discussion.

> 前面的许多步骤(尤其是前几步)对于本机代码和字节码编译器都是通用的，本章稍后将在 `[bytecode 解释语言](#08_9781119183938-ch05.xhtml#c05-sec-0028)` 一节及其后续章节中介绍这些步骤；在讨论过程中，我们将回到本节。

Let’s look at each step in a little more detail. As we do, keep in mind that we’re not describing any single compiler product, and all compilers handle compilation a little differently. Some compilers simplify the process by combining two or more passes into a single pass.

> 让我们更详细地看一下每一步。正如我们所做的，请记住，我们没有描述任何一个编译器产品，所有编译器处理编译的方式都有点不同。一些编译器通过将两个或多个过程合并为一个过程来简化该过程。

### Preprocessing

Languages that incorporate a preprocessing pass, including C, perform a stage of text-based manipulation of the incoming source code before presenting it to the compiler proper. The C preprocessor performs several tasks:

> 包含预处理过程的语言，包括 C，在将传入源代码呈现给编译器之前，对其执行基于文本的操作。C 预处理器执行几个任务：

- **Removing comments:** All text enclosed by comment delimiters (or in some other way marked as comments) is removed because it’s for the sake of humans reading the source code and is of no use to the compiler. There are some exceptions in certain languages that place instructions to the compiler within specially marked comment blocks. How those are handled is both language and compiler dependent.
- **Defining and expanding macros:** Object-like macros provide a way to define constants. You might define a macro called `PI` to be `3.14159`; the preprocessor replaces each occurrence of `PI` in the source code with the literal `3.14159`. Function-like macros provide a way to define simple inline functions. You might define a macro called `RADTODEG(x)` to be `((x)*180/PI)`. The preprocessor replaces an occurrence of `RADTODEG(a+b)` in the source code with `((a+b)*180/3.14159)`.
- **Conditional compiling:** Sections of code can be conditionally excluded from compilation. This is often used to remove debugging code from release builds of software or to change behaviour depending on the target platform.
- **Including files:** The contents of other files can be incorporated wholesale into the source code. A C example is the `stdio.h` include file, which defines commonly used C input and output functions.

> - **删除注释：**所有由注释分隔符括起来的文本(或以其他方式标记为注释)都将被删除，因为这是为了人类阅读源代码，对编译器没有任何用处。某些语言中有一些例外情况，它们将编译器的指令放在特别标记的注释块中。如何处理这些都取决于语言和编译器。
> - **定义和扩展宏：**类对象宏提供了一种定义常量的方法。您可以将名为 `PI` 的宏定义为 `3.14159` ；预处理器将源代码中出现的每一个 `PI` 替换为文字 `3.14159` 。类似函数的宏提供了一种定义简单内联函数的方法。您可以将名为 `RADTODEG(x)` 的宏定义为 `((x)*180/PI)` 。预处理器将源代码中出现的 `RADTODEG(a+b)` 替换为 `((a+b)*180/3.14159)` 。
> - **条件编译：**可以有条件地从编译中排除代码段。这通常用于从软件的发布版本中**删除调试代码**，或根据目标平台改变行为。
> - **包含头文件：**其他文件的内容可以批量合并到源代码中。C 示例是 `stdio.h` include 文件，它定义了常用的 C 输入和输出函数。

### Lexical Analysis(词法分析)

During the lexical analysis stage, a part of the compiler called the _lexer_ scans the stream of characters making up the preprocessed source code and identifies all the various language features in the text. These include reserved words (also called keywords) like `break`, `begin`, and `typedef`, identifiers like `foo` and `bar`, symbols like `+` and `<<`, string literals like ``foo ` ` and numeric literals like `5` or `3.14159`. The lexer emits a stream of tokens, one for each keyword, identifier, symbol or literal. Any text that can’t be identified as a token understood by the compiler is flagged as a compilation error.

> 在词法分析阶段，编译器的一部分 _lexer_ **扫描组成预处理源代码的字符流**，并识别文本中的所有不同语言特征。其中包括:
> `break` 、`begin` 和 `typedef` 等保留字(也称为**关键字**)；
> `foo` 和 `bar` 等**标识符**；
> `+` 和 `<` 等**符号**；
> `foo` 等**字符串文字**；
> `5` 或 `3.14159` 等**数字文字**。
> lexer 发出一个标记流，每个关键字、标识符、符号或文字对应一个标记。任何不能被编译器识别为标记的文本都被标记为编译错误。

---

> [!NOTE]
> You will see the identifiers `foo,` `bar,` `bas,` and perhaps a few others come up in code examples within programming tutorials. These are called _metasyntactic_ identifiers because they’re used while describing programming language syntax in tutorials and demonstrations of language features. Metasyntactic identifiers are not treated specially by compilers and are used by convention among programmers, specifically programmers with roots in Unix and C.
> 您将看到标识符 `foo` 、 `bar` 、 `bas` ，也许还有一些其他标识符出现在编程教程中的代码示例中。这些被称为 _metasyntactic(伪变量) identifier_，因为它们在教程和语言功能演示中用于描述编程语言语法。**元语法标识符**不被编译器专门处理，而是在程序员之间按照惯例使用，特别是在 Unix 和 C 中有根的程序员。

The stream of tokens from the lexer is then scanned by the parser, which checks to see if the tokens follow the structural rules of the language. The lexer identifies tokens individually; the parser makes sure the tokens are arranged in a legal fashion. A `do` keyword must have a matching `while` keyword. An opening brace must have a closing brace, and so on, for the full description of a language’s syntax. Any deviation from that syntax is flagged as a compilation error. The output of the parser is a structure called an _abstract syntax tree_ (AST), which represents the structure of the program. The AST is directly analogous to a sentence diagram for a natural language that identifies a sentence’s subject, verb, object and so on.

> 然后解析器扫描来自 lexer 的令牌流，**检查令牌是否遵循语言的结构规则**。
> lexer 单独标识令牌；解析器确保令牌以合法的方式排列。`do` 关键字必须具有匹配的 `while` 关键字。要获得语言语法的完整描述，左大括号必须有右大括号等。与该语法的任何偏差都被标记为编译错误。
> 解析器的输出是一个名为 _abstract syntax tree_(AST)的结构，它表示程序的结构。AST 直接类似于自然语言的句子图，用于识别句子的主语、动词、宾语等。

### Semantic Analysis

During semantic analysis, the compiler checks the AST to be sure that the syntactically correct program is meaningful. Much of this work involves creating a symbol table of named items in the program, and then checking whether variables and constants of supported data types (numeric, text, Boolean, and so on) are used together in ways that make sense. A statement written in a statically typed language that adds a Boolean value to a character might well be correct in terms of syntax:

> 在语义分析期间，**编译器检查 AST 以确保语法正确的程序是有意义的**。这项工作的大部分涉及**在程序中创建命名项的符号表**，然后检查所支持数据类型(数字、文本、布尔等)的变量和常量是否以合理的方式一起使用。用静态类型语言编写的语句向字符添加布尔值，在语法方面可能是正确的：

```
    junk = true + ‘a’;
```

However, what does it mean to add `true` to `‘a’`? Nothing, of course! Although syntactically correct, the statement is semantically meaningless, and the compiler will flag it as a type mismatch error. Syntactically correct but semantically meaningless sentences appear in natural languages too: Noam Chomsky famously offered `Colourless green ideas sleep furiously` as an example of a syntactically valid English sentence that is semantically meaningless.

> 然而，将 `true` 添加到 `a` 是什么意思？当然没什么！**虽然语法正确，但该语句在语义上没有意义，编译器会将其标记为类型不匹配错误**。语法正确但语义无意义的句子也出现在自然语言中：诺姆·乔姆斯基(Noam Chomsky)提出了一个著名的 `无颜色的绿色想法疯狂睡觉` ，作为一个语法有效且语义无意义英语句子的例子。

Keep it straight in your head: Syntax is about _structure_. Semantics is about _meaning_.

> 保持头脑清醒：语法是关于 _structure_ 的。语义是关于 _meaning_ 的。

### Intermediate Code Generation(中间代码生成)

After the compiler verifies that the program is both syntactically correct and semantically meaningful, it is able to begin generating intermediate code. Using the parse tree as a guide, the compiler creates a linear sequence of instructions that expresses the logic of the program. These instructions are not generally the native machine instructions of the target CPU architecture. Instead, they are a sort of `artificial` instruction set belonging to a _virtual machine_ (VM) that acts as an `ideal` CPU that is a notch higher in abstraction than a real, silicon CPU. For example, a VM may have a great many registers in its definition—and sometimes, as many registers as the logic of the program calls for. No CPU has hundreds of registers, so a later pass has to rewrite the intermediate code to attempt to fit those `virtual registers` into the limited register set of the real CPU, spilling those that don’t fit to memory. This process is known as _register allocation._

> 在编译器验证程序在**语法上正确且语义上有意义之后，就可以开始生成中间代码了**。**使用解析树作为指导，编译器创建一个线性指令序列**，表达程序的逻辑。这些指令通常不是目标 CPU 体系结构的本机指令。相反，它们是一种**属于虚拟机(VM)的 `人工` 指令集**，充当一个 `理想` CPU，其抽象程度比真正的硅 CPU 高出一个档次。
> 例如，一个 VM 的定义中可能有很多寄存器，有时也有程序逻辑所需要的寄存器。没有一个 CPU 有数百个寄存器，因此稍后的过程**必须重写中间代码，以尝试将这些 `虚拟寄存器` 放入实际 CPU 的有限寄存器集**，从而溢出那些不适合内存的寄存器。此过程称为 _register allocation_。

### Optimisation

The intermediate code’s primary role is to simplify the implementation of one or more _optimisation_ passes. During optimisation, the compiler looks for ways to eliminate code duplication and rearrange intermediate code instructions to make the program more compact and faster to execute. The development of optimisation techniques is an area of ongoing research in both the academic and commercial domains.

> **中间代码的主要作用是简化一个或多个优化过程的实现。**在优化过程中，编译器会寻找消除代码重复和重新排列中间代码指令的方法，以使程序更紧凑，执行速度更快。优化技术的发展是学术和商业领域中正在进行的研究领域。

> [!NOTE]
> 这里提到的思想特别有意思
> 通过 VM 构件的中间指令集，将代码与 CPU 的指令集进行一个分隔，可以较好的翻译不同的指令集。
> 但是这里提到了可以在这个阶段进行优化，这是一个承上启下的阶段...
> 如果这里对代码翻译成指令集的过程有优化的方法，是否也可以移植到实时系统，在对任务进行编排调度的时候
> 编排好的任务再放到对应的 SOC 上的时候，可以进行 `优化` ？！

### Target Code Generation

With the creation of an optimised intermediate code file, we reach a fork in the road. Up to this point, the compilation process is close to the same, whether the compiler is a native code compiler or a bytecode compiler, and we’ll pick up the discussion again in the next section on bytecode languages. The next, and final, step in native code compilation is _target code generation_. During this step, the intermediate code is converted to a sequence of native machine instructions that can execute on a specific CPU.

> 通过创建优化的中间代码文件，我们到达了一个岔路口。到目前为止，无论编译器是本机代码编译器还是字节码编译器，编译过程都几乎相同，我们将在下一节中再次讨论字节码语言。**本机代码编译的下一步也是最后一步是 _target code_ 生成**。在这一步骤中，**中间代码被转换为可以在特定 CPU 上执行的本机指令序列**。

But which CPU? A compiler is not limited to creating code for the machine on which the compiler is running: a compiler running on an Intel CPU can be configured to generate code for the one of the ARM instruction set architectures (ISAs), and vice versa. This is called _cross-compilation_. A compiler is hosted on a specific CPU, which means that it is a native-code program compiled to run on that CPU. However, it may generate code that targets any CPU for which the compiler incorporates a code generator. Cross-compilation is especially useful for the creation of software to run on low-power embedded systems that don’t contain enough memory or disk storage to run the compiler itself. In your early work with the Raspberry Pi you’ll probably write programs and compile them right on the Raspberry Pi system itself. Many people who use the board as an embedded system develop code on Intel PCs by using a compiler that is hosted on Intel-based Windows or Linux and targets the ARMv6 ISA, which includes the ARM11 CPU . The generated code is almost always operating system-specific as well.

> **但是哪个 CPU 呢？**编译器不限于为运行编译器的机器创建代码：在 Intel CPU 上运行的编译器可以配置为为 ARM 指令集架构(ISA)之一生成代码，反之亦然。这称为 _交叉编译_。编译器托管在特定的 CPU 上，这意味着它是编译为在该 CPU 上运行的本地代码程序。
> 然而，它**可以生成针对编译器包含代码生成器的任何 CPU 的代码**。交叉编译对于创建在低功耗嵌入式系统上运行的软件特别有用，因为这些系统没有足够的内存或磁盘存储来运行编译器本身。在你早期使用树莓派的工作中，你可能会在树莓派系统本身上编写程序并编译它们。许多将该板用作嵌入式系统的人通过使用基于 Intel 的 Windows 或 Linux 上的编译器在 Intel PC 上开发代码，该编译器以 ARMv6 ISA 为目标，包括 ARM11 CPU。生成的代码几乎总是特定于操作系统的。

With the creation of a native code object file, the compilation process is complete.

> **创建本机代码对象文件后，编译过程就完成了。**

---

> [!NOTE]
> A _platform_ is the combination of a specific CPU running a specific operating system. An Intel CPU running Microsoft Windows is a platform. (It’s commonly called `Wintel.` ) An Intel CPU running Linux is an entirely separate platform, as is an ARMv6 CPU running Linux. The output of a cross-compilation operation is generally specified as being for a specific platform.
> 平台是运行特定操作系统的特定 CPU 的组合。运行 Microsoft Windows 的 Intel CPU 是一个平台。(通常称为 `Wintel` )运行 Linux 的 Intel CPU 是一个完全独立的平台，运行 Linux 的 ARMv6 CPU 也是如此。交叉编译操作的输出通常指定为特定平台的输出。

### Compiling C: A Concrete Example

Let’s take a look at the various stages involved in compiling a simple function, written in C. This section requires close attention, and perhaps a little experience in the C language itself.

> 让我们来看看编译一个用 C 编写的简单函数所涉及的各个阶段。这一部分需要密切关注，也许还需要一点 C 语言本身的经验。

The example function takes three integer arguments `a`, `b` and `c`, and a pointer to an area of memory, `d`. It writes the ten integers `b*c`, `a+b*c`, `2*a+b*c` … `9*a+b*c` into memory, starting at address `d`. The number of integers written can be changed at compile time by adjusting the constant `COUNT`, which is set using the C preprocessor directive `#define`:

> 示例函数采用三个整数参数 `a` 、 `b` 和 `c` ，以及指向内存区域 `d` 的指针。它从地址 `d` 开始，将十个整数 `b*c` 、 `a+b*c’、 ` 2*a+b*c `…` 9*a+b*c ` 写入内存。通过调整常量` COUNT `(使用 C 预处理器指令`#define` 设置)，可以在编译时更改写入的整数数：

```c
    #define COUNT 10
    void foo(int a, int b, int c, int *d)
    {
      int i = 0;
      do {
       d[i++] = i * a + b * c;// fill in table
      } while (i < COUNT);
    }
```

#### Preprocessor

The preprocessor discards the comments, and replaces the use of the macro `COUNT` with its value, 10. Few modern languages have preprocessors; in this case, constants and inline functions take the place of macros, and comments would be discarded by the lexer:

> 预处理器丢弃注释，并将宏 `COUNT` 的使用替换为其值 10。现代语言很少有预处理器；在这种情况下，常量和内联函数代替宏，注释将被 lexer 丢弃：

```c
    void foo(int a, int b, int c, int *d)
    {
      int i = 0;
      do {
       d[i++] = i * a + b * c;
      } while (i < 10);
    }
```

#### Lexer

The lexer analyses the character stream that makes up the program, and groups characters into tokens. Each token may be one or more characters in length, and represents a reserved word, an identifier (shown as a double-outlined box in Figure 5-5), a symbol or a literal. Whitespace is not syntactically meaningful in C, and so is discarded from the token stream at this stage.

> lexer 分析组成程序的字符流，并将字符分组为令牌。每个令牌的长度可以是一个或多个字符，并表示保留字、标识符(如图 5-5 中的双框框所示)、符号或文字。空白在 C 语言中没有语法意义，因此在这个阶段将从令牌流中丢弃。

![[FIGURE 5-5:](#08_9781119183938-ch05.xhtml#rc05-fig-0005) Tokens generated by a C compiler’s lexer](./media/images/9781119183938-fg0505.png)

#### Parser

The parser attempts to build an AST out of the stream of tokens from the lexer. It is powered by a set of rules, often expressed in a descriptive notation called Backus-Naur Form (BNF). BNF is perhaps the most-used metasyntactic notation system in computer science. It abstracts the structure of a programming language into a set of rules called a _grammar_. A grammar precisely describes the syntax of a programming language and can be used to determine if a given program is syntactically correct. The standard GNU utility, bison (derived from the older UNIX tool yacc—bison is GNU yacc), can automatically generate a parser for a programming language, given a BNF description. A selection of BNF grammars for various common programming languages may be found here: [`www.thefreecountry.com/sourcecode/grammars.shtml`](http://www.thefreecountry.com/sourcecode/grammars.shtml).

> 解析器试图从 lexer 的令牌流中构建 AST。它由一组规则提供支持，通常用一种称为巴克斯-瑙尔形式(BNF)的描述性符号表示。BNF 可能是计算机科学中最常用的元句法符号系统。它将**编程语言的结构抽象为一组规则，称为 _grammar_**。语法精确地描述了编程语言的语法，可以用来确定给定程序的语法是否正确。标准 GNU 实用程序 bison(源于旧的 UNIX 工具 yacc bison 是 GNUyacc)可以自动为编程语言生成解析器，给出 BNF 描述。各种常用编程语言的 BNF 语法可在以下位置找到：[grammers](http://www.thefreecountry.com/sourcecode/grammars.shtml).

As an example, imagine a simple language that consists only of expressions containing multiplication, addition and identifiers. This language would have three rules, which might appear in the input file to bison in roughly this form, using BNF:

> 例如，想象一种简单的语言，它只包含包含乘法、加法和标识符的表达式。该语言将有三个规则，它们可能以大致如下的形式出现在 bison 的输入文件中，使用 BNF：

```bnf
    add_expr  : mul_expr         { $$ = $0; }
       | add_expr ‘+’ mul_expr;   { $$ = ADD_EXPR($0, $2); }
       ;
    mul_expr  : identifier             { $$ = $0; }
       | mul_expr ‘*’ identifier; { $$ = MUL_EXPR($0, $2); }
       ;
    identifier : ID               { $$ = $0; }
       ;
```

Each rule has three parts:

> 每个规则有三个部分：

- A _name_ (in this case `add_expr`, `mul_expr` or `identifier`).
- One or more _productions_. A production describes something you might see in the token stream that this rule will match.
- For each production, an _action_; this is often used to create a node in the AST as a result of matching a rule. In a yacc grammar, actions can return values by assigning to the pseudovariable `$$`, and make use of values returned by the rule’s children (represented by pseudovariables `$0`, `$1` and so on).

> - _名称_(在本例中为 `add_expr` 、 `mul_expr` 或 `identifier` )。
> - 一个或多个 _productions_。产品描述了您可能在令牌流中看到的与此规则匹配的内容。
> - 对于每个生产，一个 _action_；这通常用于在 AST 中创建节点，作为匹配规则的结果。在 yacc 语法中，操作可以通过向伪变量 `$$` 赋值来返回值，并使用规则的子级返回的值(由伪变量 `$0` 、 `$1` 等表示)。

---

> [!NOTE]

A _pseudovariable_ is a sort of placeholder in a grammar rule. It tells us where a value may be substituted for the pseudovariable. Pseudovariables keep a rule abstract and independent of any particular type, value or values.

> 伪变量是语法规则中的一种占位符。它告诉我们在哪里可以用一个值来代替伪变量。伪变量保持规则抽象，并且独立于任何特定类型、值或值。

Our language description says that a valid `mul_expr` can be either an identifier, like `a` , or another (shorter) valid `mul_expr` followed by a `*` , followed by an identifier. So `a` (being an identifier) is a valid `mul_expr`, and so is `a*b` (because `a` (being an identifier) is a valid `mul_expr`, and `b` is an identifier), and so is `a*b*c` (because `a*b` is a valid `mul_expr` and `c` is an identifier). As the parser recognises `a*b*c` , the actions first build a `MUL_EXPR` node for `a*b` , and then a `MUL_EXPR` node that refers to the first node and represents `(a*b)*c` . The final AST could be written as:

> 我们的语言描述表明，有效的 `mul_expr` 可以是标识符，例如 `a` ，也可以是另一个(更短的)有效的 `mul_expr` 后跟一个 `*` ，然后是一个标识符。所以 `a`(作为标识符)是有效的 `mul_expr`，`a*b` 也是(因为 `a`(作为标识符)是有效的 `mul_expr`，而 `b` 是标识符)，`a*b*c` 也是(因为 `a*b` 是一个有效的 `mul_expr` 而 `c` 是一个标识符)。当解析器识别 `a*b*c` 时，操作首先为 `a*b` 构建一个 `MUL_EXPR` 节点，然后是一个指向第一个节点并表示 `(a*b)*` 的 `MUL_EXPR` 节点 `c`。最终的 AST 可以写成：

```ast
    MUL_EXPR(MUL_EXPR(a, b), c)
```

Satisfy yourself that the rule for `add_expr` successfully recognises the expression `a*b+c*d` and produces the following tree:

> 请确保 `add_expr` 规则成功识别表达式 `a*b+c*d` ，并生成以下树：

```
    ADD_EXPR(MUL_EXPR(a, b), MUL_EXPR(c, d))
```

A pleasing side effect of the way that these rules have been written is that multiplication is more `sticky` (or, more formally, it has higher precedence) than addition, so `a*b` and `c*d` have been correctly grouped together according to the precedence rules you remember from school. Applying a simplified version of the full C grammar to the earlier token string might yield the following AST:

> 这些规则编写方式的一个令人愉快的副作用是，乘法比加法更 `粘` (或者更正式地说，它具有更高的优先级)，因此 `a*b` 和 `c*d` 已根据你从学校记住的优先级规则正确地分组在一起。将完整 C 语法的简化版本应用于早期的标记字符串可能会产生以下 AST：

```
    FUNC_DEF (
              name: foo
              params: [(a, INT), (b, INT), (c, INT), (d, INT*)]
              returns: VOID
              body: SEQ_STMT (
                              stmt[0]: AUTO_DECL (
                                     name: I
                                     type: INT
                                     initialize: 0
                              )
                              stmt[1]: DO_LOOP_STMT (
                                     body: EXPR_STMT (
                                           expr: ASSIGN_EXPR (
                                                  lhs: INDEX_EXPR (
                                                        array: d
                                                        index: i
                                                  )
                                                  rhs: ADD_EXPR (
                                                        lhs: MUL_EXPR (
                                                              lhs: i
                                                              rhs: a
                                                        )
                                                  rhs: MUL_EXPR (
                                                        lhs: b
                                                        rhs: c
                                                  )
                                            )
                                     )
                              )
                              test: LESS_THAN_EXPR (
                                     lhs: i
                                     rhs: 10
                              )
                    )
              )
    )
```

#### Semantic Analysis

Armed with the AST, the compiler can construct a symbol table that describes the type of each formal parameter and local variable within function foo:

> **有了 AST，编译器可以构造一个符号表**，描述函数 foo 中每个形式参数和局部变量的类型：

```
    a: int
    b: int
    c: int
    d: int*
    i: int
```

From this, it can determine that both `d[i]` and `i * a + b * c` have type `int`, and that `d[i]` is an lvalue. **An _lvalue_ is a suitable target for an assignment**: `a` and `d[i]` are lvalues, whereas `b * c` is not. The assignment `d[i] = i * a + b * c` is therefore determined to be semantically valid.

> 由此，可以确定 `d[i]` 和 `i*a+b*c` 都具有类型 `int` ，并且 `d[i]` 是左值。_lvalue_ 是赋值的合适目标： `a` 和 `d[i]` 是 lvalue，而 `b*c` 不是。因此，赋值 `d[i]=i*a+b*c` 被确定为语义有效。

#### Intermediate Code Generation

When we have a semantically valid AST, we can set about converting it into intermediate code. The intermediate code generator knows how to convert each type of AST node into one or more intermediate code instructions, and these rules are applied recursively. For example, to convert an `ADD_EXPR` node we first convert its left and right children (called `lhs` and `rhs` in the example from the `[Parser](#08_9781119183938-ch05.xhtml#c05-sec-0020)` section), and then emit an `ADD` instruction to combine the results. To convert a `DO_LOOP_STMT` we emit a label, then convert the body of the loop and the loop test expression (called `body` and `test` in the example), and finally emit a conditional branch back to the start of the loop, which is predicated on the result of the test:

> 当我们有一个语义上有效的 AST 时，我们可以开始将其转换为中间代码。中间代码生成器知道如何将每种类型的 AST 节点转换为一个或多个中间代码指令，这些规则是递归应用的。例如，要转换 `ADD_EXPR` 节点，我们首先转换它的左和右子节点(在示例中称为 `[Parser](#08_9781119183938-ch05.xhtml#c05-sec-0020)` 部分中的 `lhs` 和 `rhs` )，然后发出 `ADD` 指令以组合结果。要转换 `DO_LOOP_STMT` ，我们发出一个标签，然后转换循环体和循环测试表达式(在示例中称为 `body` 和 `test` )，最后发出一个条件分支返回到循环的开头，这取决于测试结果：

```
    FUNCTION foo(p0, p1, p2, p3)
    MOV           t0, #0             ; temporary 0 stores count
    label:
      MUL           t1, t0, p0         ; calculate i * a
      MUL           t2, p1, p2         ; calculate b * c
      ADD           t3, t1, t2         ; calculate i * a + b * c
      MUL           t4, t0, #4         ; index = count * sizeof(int)
      ADD           t5, p3, t4         ; calculate address
      STW           [t5], t3           ; store i * a + b * c in d[i]
      ADD           t0, t0, #1         ; increment loop count
      BRANCHLT      t0, #10, label     ; branch if count < 10
```

#### Simple Optimisation

Notice that `b * c` is calculated each time around the loop, when it’s only dependent on the formal parameters `b` and `c`, which don’t change. We say that `b * c` is _loop invariant_, and apply loop-invariant code motion to hoist the computation out of the loop, saving nine cycles. As we only need one register to store `b * c`, rather than two registers to store the separate values, we’ve also usefully reduced _register pressure_ (the number of values that need to be remembered at any given point in the program) by one, which improves the chances of fitting all the values we need into the target CPU architecture’s registers. If we had needed `b` and `c` on their own as well as `b * c` then this optimisation would have required more registers than might be available, and the compiler would need to apply a heuristic (that is, a mechanism used to solve a particular code-generation case that might not apply to all cases) to see whether the trade-off was worth making.

> 请注意，`b*c` 在每次循环时都会计算，因为它只依赖于形式参数 `b` 和 `c`，而这些参数不会改变。我们说 `b*c` 是 _loop invariant_，并应用循环不变代码运动将计算移出循环，从而节省了九个周期。
> 由于我们只需要一个寄存器来存储 `b*c` ，而不需要两个寄存器来分别存储值，因此我们还将 _register pressure_(程序中任何给定点需要记住的值的数量)减少了一个，这提高了将所有所需值适配到目标 CPU 体系结构寄存器中的可能性。如果我们自己需要 `b` 和 `c` 以及 `b*c` ，**那么这种优化将需要比可用寄存器更多的寄存器，编译器需要应用启发式**(即，用于解决特定代码生成情况的机制，可能不适用于所有情况)，以确定是否值得进行权衡。

```
    FUNCTION foo(p0, p1, p2, p3)
      MOV            t0, #0
      MUL            t2, p1, p2    ; hoist loop-invariant calculation
    label:
      MUL            t1, t0, p0
      ADD            t3, t1, t2
      MUL            t4, t0, #4
      ADD            t5, p3, t4
      STW            [t5], t3
      ADD            t0, t0, #1
      BRANCHLT       t0, #10, label
      RET
```

#### More Aggressive Optimisation

> [!NOTE]
> A more aggressive optimiser might be able to detect that both the address, which we’ll de `a(i)`, and the value stored, which we’ll de `v(i)`, change by a fixed amount each time we go around the loop:
> 一个更积极的优化器可能能够检测到地址，我们将 de `a(i)` 和存储的值，我们将 de `v(i)`，每个都改变了一个固定的量 我们绕过循环的时间：

```
    a(0) = d         a(i+1) = a(i) + 4
    v(0) = b*c       v(i+1) = v(i) + a
```

Also we leave the loop just before we write to address `a(10) = d + 40`. It can therefore eliminate the potentially costly multiplication instructions, which can be hard to schedule due to their long pipeline depth, instead keeping a running value of `a(i)` and `v(i)`, and replace the test `i < 10` with the test `a(i) < a(10)`. This class of optimisation is known as _induction variable elimination_:

> 同样，我们在写入地址 `a(10)=d+40` 之前就离开了循环。因此，它可以消除可能代价高昂的**乘法指令，因为它们的流水线深度很长**，所以很难进行调度，而是保持 `a(i)` 和 `v(i))` 的运行值，并将测试 `i ＜ 10` 替换为测试 `a(i)＜ a(10)` 。这类优化称为 _产量变量消除_：

```
    FUNCTION foo(p0, p1, p2, p3)
      MUL            t1, p1, p2
      MOV            t2, p3
      ADD            t3, t2, #40
    label:
      STW            [t2], t1
      ADD            t1, t1, p0
      ADD            t2, t2, #4
      BRANCHLT       t2, t3, label
      RET
```

#### Target Code Generation (Register Allocation, Instruction Scheduling)

Now we have an optimised program represented in intermediate code; the final step is to convert that program into assembly language for our target platform. The key challenges are finding a machine register to store each value computed by the program between the point it is defined and the last point at which it is used (this is called _register allocation_), implementing each intermediate instruction by using one or more machine instructions, and ordering those machine instructions so as to avoid triggering interlocks inside the CPU pipeline (this is called _instruction scheduling_):

> 现在我们有了一个用中间代码表示的优化程序；最后一步是**将该程序转换为目标平台的汇编语言**。关键的挑战是找到一个机器寄存器来存储程序在定义的点和使用它的最后一点之间计算的每个值(这称为 _register allocation_)，通过使用一个或多个机器指令来实现每个中间指令，并对这些机器指令进行排序，以避免触发 CPU 管道内的联锁(这称为 _instruction scheduleing_)：

```
      ; In the ARM EABI calling convention, the first four
      ; arguments are in provided r0-r3

      ; r0-r3 may also be used as scratch registers without
      ; saving to the stack

    foo::
      mul            r1, r1, r2     ; r1 = b * c (reuse r1)
      add            r2, r3, #40    ; r2 = d + 40 (reuse r2)
    label:
      stw            [r3], r1       ; store v(i) at a(i)
      add            r3, r3, #4     ; a(i+1) = a(i) + 4
      add            r1, r1, r0     ; v(i+1) = v(i) + a
      cmp            r3, r2         ; have we reached a(10) yet?
      Blt            label          ; if not, loop
      B              lr             ; return to link address
```

### Linking Object Code Files to Executable Files

When the compilation process is done and the smoke clears, what you have is not quite an executable program file. Most modern compilers generate an object code file that requires one additional step before you can run it: _linking_. The key to understanding linking lies in these two points:

> 当编译过程完成并且烟雾散去时，您所拥有的**不是一个完全可执行的程序文件**。大多数现代编译器都会**生成一个目标代码文件**，在运行它之前需要一个额外的步骤：_linking_。理解联系的关键在于以下两点：

- Nearly all workaday programs (as opposed to simple test or learning programs) are written in several pieces, each of which is compiled separately to an object code file.
- Nearly all programs make use of code libraries that are object code files containing useful functions and data definitions that may be considered `standard parts` in software development.

> - 几乎所有的日常程序(与简单的测试或学习程序相反)都是**由多个部分编写的**，每个部分都单独编译成一个目标代码文件。
> - 几乎所有程序都使用**代码库**，这些代码库是包含有用函数和数据定义的目标代码文件，在软件开发中可以被视为 `标准部分` 。

Of course, the simple programs you write as you learn a programming language or toolset will be small enough to create in one piece. However, whether you realise it or not, even your simple test programs probably make use of existing code libraries. Nearly all high-level languages have a runtime library containing standard functions implementing support for text strings, higher maths, date and time manipulation, and so on; the runtime library also contains startup code, which runs before your main function and initialises data structures used by other library functions. Other libraries may contain code specific to a particular operating system, for access to displays, printers and file systems.

> 当然，当你学习编程语言或工具集时，你编写的简单程序将足够小，可以一块创建。然而，无论您是否意识到，即使是简单的测试程序也可能会使用现有的代码库。**几乎所有高级语言都有一个运行时库**，其中包含实现对文本字符串、高等数学、日期和时间操作等的支持的标准函数；**运行时库还包含启动代码，它在主函数之前运行**，并初始化其他库函数使用的数据结构。其他库可能包含特定于特定操作系统的代码，用于访问显示器、打印机和文件系统。

What a linker does is combine multiple object code files and functions from statically linked libraries into a single executable code file that may be run on the target computer. This requires more than just writing out the object code files nose-to-tail. Code in one object code file may call functions, or use data definitions, from libraries and other object code files. Calling a function requires the memory address of the function. There’s no way to specify a memory address in another object code file stored somewhere else on disk or solid-state drive (SSD.) Instead, the compiler puts a placeholder into the spot where such an external address needs to go. The placeholder says, in effect, `address to be determined` .

> **链接器**所做的是**将静态链接库中的多个目标代码文件和函数组合成一个可在目标计算机上运行的可执行代码文件**。这需要的不仅仅是从头到尾写出目标代码文件。**一个目标代码文件中的代码可以从库和其他目标代码文件调用函数或使用数据定义**。
> 调用函数需要**函数的内存地址。无法在存储在磁盘**或固态驱动器(SSD)上其他位置的另一个目标代码文件中指定内存地址。相反，编译器会将**占位符放置在需要放置此外部地址的位置。占位符实际上表示 `地址待定`**。

While the linker is combining separate object code files into a single executable file, it looks for such placeholders and calculates addresses that, in most cases, are offsets from the beginning of the executable file. The long and winding road from source code files to a finished executable program file is shown in Figure 5-6.

> 当链接器将单独的目标代码文件合并为单个可执行文件时，它会**查找这些占位符，并计算在大多数情况下与可执行文件开头偏移的地址**。从源代码文件到完成的可执行程序文件的漫长而曲折的道路如图 5-6 所示。

> [!NOTE]
> the way that references to identifiers in one object code file `plug in` to the actual functions or variables in another object code file.
> 将一个目标代码文件中的标识符引用 `插入` 到另一个目标代码文件中的实际函数或变量的方式。

![[FIGURE 5-6:](#08_9781119183938-ch05.xhtml#rc05-fig-0006) How the compiler and linker create a single executable program file](./media/images/9781119183938-fg0506.png)

## Pure Text Interpreters

> [!NOTE]
> 前面的是编译型语言，后面的是解释型语言哈
> 看下面的描述，感觉这个解释器就是 shell 的原型？

In the preceding section, we briefly mentioned the concept of bytecode compilation. Before we elaborate on this, it is helpful to take a brief detour back into programming history. Early versions of the BASIC language were modelled on FORTRAN and were compiled on mainframes and minicomputers just as FORTRAN was. In the mid-1970s, the first personal computers often had too little memory for a real operating system, much less a compiler. To enable users to learn programming and write their own software, a different kind of BASIC language system appeared: the _text interpreter_.

> 在上一节中，我们简要提到了**字节码编译**的概念。在我们详细阐述这一点之前，我们可以先回顾一下编程历史。
> BASIC 语言的早期版本是以 FORTRAN 为模型，并像 FORTRAN 一样在大型机和小型计算机上编译。在 20 世纪 70 年代中期，第一代个人计算机的**内存对于真正的操作系统来说往往太少**，更不用说编译器了。为了让用户能够学习编程和编写自己的软件，出现了一种不同的 BASIC 语言系统：_text interpreter_。

In a text interpreter system, a program is written in the form of a textual source code file, just as with native code compilation. However, there is no compilation step at all; when a program is run, the source code file is opened by a piece of software called an _interpreter_. The interpreter reads the first line from the source code file and then performs whatever work that line specifies. When the first line is done, the interpreter reads the next line, performs the work it specifies and so on, through the source code file. The key characteristic of text interpreters is that they process a single line of program source code at a time. Figure 5-7 illustrates this process.

> 在文本解释器系统中，程序以文本源代码文件的形式编写，就像本地代码编译一样。然而，根本没有编译步骤；当程序运行时，源代码文件由一个名为 interpreter 的软件打开。**解释器从源代码文件中读取第一行，然后执行该行指定的任何工作。当完成第一行时，解释器通过源代码文件读取下一行，执行它指定的工作等等。**文本解释器的关键特征是它们一次处理一行程序源代码。图 5-7 说明了这一过程。

![[FIGURE 5-7:](#08_9781119183938-ch05.xhtml#rc05-fig-0007) A text interpreter for the BASIC language](./media/images/9781119183938-fg0507.png)

A text interpreter takes each line of source code apart after it’s read from the file. It then calls subroutines to evaluate arithmetic expressions like `Height * Width` and process keywords like `INPUT` and `PRINT`. The text interpreter creates variables in memory as the source code introduces them, and manages them while the program runs. Values are read from variables as needed in calculations, and new values are given to variables when a program line assigns or recalculates a variable’s value. The text interpreter handles displaying the program’s output on the computer monitor, and the reading of text input from the computer keyboard.

> 文本解释器在从文件中读取源代码后，将每行代码拆开。然后，它调用子程序来计算算术表达式(如 `Height*Width` )，并处理关键字(如 `INPUT` 和 `PRINT` )。文本解释器在源代码引入变量时在内存中创建变量，并在程序运行时对其进行管理。在计算中根据需要从变量中读取值，当程序行分配或重新计算变量值时，将为变量提供新值。文本解释器处理在计算机监视器上显示程序的输出，以及从计算机键盘读取文本输入。

Text interpreters for simple dialects of BASIC were comparatively straightforward to write and (more importantly) were compact. An interpreter consisted of a simple line lexer and parser, and then a collection of functions to execute the various keywords and features of BASIC. Many early personal computers, from the Commodore VIC-20 up to the original IBM PC, had a BASIC interpreter stored on read-only memory (ROM) chips soldered to the motherboard. In many cases, the BASIC interpreter stood in for a simple operating system, and allowed single commands to be entered to an interactive command line.

> BASIC 简单方言的文本解释器相对简单，而且(更重要的是)紧凑。**解释器由一个简单的行词法分析器和解析器组成**，然后是一组函数，用于执行 BASIC 的各种关键字和特性。许多早期的个人电脑，从 Commodore VIC-20 到最初的 IBM PC，都有一个 BASIC 解释器，它存储在焊接在主板上的只读存储器(ROM)芯片上。在许多情况下，BASIC 解释器代表一个简单的操作系统，并允许在交互命令行中输入单个命令。

Pure text interpreters for programming languages like BASIC were everywhere in the 1970s and 1980s, but are nearly extinct today. Where text interpreters are still used, it is for creating command files for operating systems, database managers and large, complex applications that allow commands to be `batched` in text files. This was once called _scripting_, but that term has broadened to include programming for any language that incorporates interpretation at any level.

> 在 20 世纪 70 年代和 80 年代，BASIC 等编程语言的纯文本解释器随处可见，但如今几乎绝迹。在仍然使用文本解释器的地方，它用于为操作系统、数据库管理器和大型复杂应用程序创建命令文件，这些应用程序允许在文本文件中 `批处理` 命令。这曾经被称为 _scripting_，但该术语已经扩展到包括任何语言的编程，包括任何级别的解释。

## Bytecode Interpreted Languages

One useful characteristic of text interpreters is that they insulate a running program from the fine details of the underlying platform. A BASIC program’s `PRINT` keyword does the same thing, whether it’s running on DOS, Linux or any other operating system. The interpreter itself is a native-code machine-language program, and deals with hardware and operating system specifics, but a BASIC program will run identically on any text interpreter, on any platform, that understands the appropriate dialect of BASIC.

> 文本解释器的一个有用特性是，它们将正在运行的程序与底层平台的精细细节隔离开来。BASIC 程序的 `PRINT` 关键字执行相同的操作，无论它是在 DOS、Linux 还是任何其他操作系统上运行。解释器本身是一个本机代码机器语言程序，处理硬件和操作系统的细节，但 **BASIC 程序将在任何文本解释器上，在任何平台上运行**，只要理解 BASIC 的适当方言。

This attribute of BASIC programs is called _portability_; the portability of applications became an important consideration once computers grew cheap enough to be commodities, with hundreds and later thousands of different and often incompatible designs up and down the market. There were hundreds of different ways to write characters to a display, to send text to a printer, and to read and write data to storage devices. Programs had to be written in a slightly different way on each system, in order to take advantage of that system’s features. The portability problem plagues us to this day, and the best solution we now have centres on an evolved form of interpretation.

> BASIC 程序的这个属性称为 _portality_；一旦计算机变得足够便宜，可以成为商品，那么应用程序的**可移植性**就成为了一个重要的考虑因素，市场上上下出现了成百上千种不同且常常不兼容的设计。有数百种不同的方法可以将字符写入显示器，将文本发送到打印机，以及将数据读写到存储设备。为了利用系统的特性，程序必须在每个系统上以稍微不同的方式编写。可移植性问题一直困扰着我们，而我们现在拥有的最佳解决方案集中在一种进化的解释形式上。

### P-Code

In the mid-1970s, researchers at the University of California, San Diego developed a new kind of compiler for the Pascal programming language. The UCSD Pascal compiler operated in much the same way as the native-code compilers we described earlier. The resemblance stopped at the point where UCSD Pascal generated intermediate code. Native code compilers take their intermediate code and use it as a guide for generating native code. The UCSD compiler’s intermediate code was written to a file, and then that file of intermediate code was executed by an interpreter installed on a computer. As with BASIC’s text interpreter, the UCSD interpreter insulated the program from the details of the underlying computer. A program written in the UCSD Pascal syntax could theoretically be compiled once, and then the intermediate code could be run in an identical manner on any machine for which an interpreter had been written. The code was thus extremely portable between otherwise incompatible computers.

> 20 世纪 70 年代中期，加州大学圣地亚哥分校的研究人员为 Pascal 编程语言开发了一种新的编译器。UCSD Pascal 编译器的操作方式与我们前面描述的本机代码编译器大致相同。这种相似性在 UCSD Pascal 生成中间代码时停止了。本机代码编译器将其中间代码作为生成本机代码的指南。**UCSD 编译器的中间代码被写入一个文件，然后该中间代码文件由安装在计算机上的解释器执行**。与 BASIC 的文本解释器一样，UCSD **解释器将程序与底层计算机的细节隔离开来**。用 UCSD Pascal 语法编写的程序理论上可以编译一次，然后中间代码可以在任何编写了解释器的机器上以相同的方式运行。因此，该代码在其他不兼容的计算机之间极为便携。

This technology was dubbed the P-System, where the `P` originally stood for `pseudocode` and later `portability code` . (Both are now-obsolete terms for `bytecode` , which we will discuss in the next paragraph.) The intermediate code (p-code) generated by the UCSD compiler was not textual. It was a sequence of binary instructions that resembled machine instructions but were actually instructions understood and executed by the interpreter program. These instructions represented an instruction set for a virtual machine; that is, a CPU that did not exist in silicon, but was emulated using a p-code interpreter.

> 这项技术被称为 P 系统，其中 `P` 最初代表 `伪代码` ，后来代表 `可移植代码` 。(这两个词现在都是 `字节码` 的过时术语，我们将在下一段中讨论。)UCSD 编译器生成的中间代码(p 代码)不是文本代码。这是一个二进制指令序列，类似于机器指令，但实际上是由解释器程序理解和执行的指令。这些指令表示虚拟机的指令集；也就是说，一个不存在于硅中的 CPU，但使用 p 代码解释器进行模拟。

> [!note]
> python 和 matlab 在运行过程中都有类似的中间产物，和这里的是对应的吗？

The P-System was the first technology of its kind to win wide acceptance. The notion of p-code was soon taken up by other researchers for other languages. The underlying idea of a virtual instruction set for a virtual machine does not depend on Pascal or any other specific programming language, and the P-System was later expanded with support for languages including Modula-2, BASIC, and FORTRAN. The term p-code was eventually abandoned in favour of bytecode, but the meaning is the same: bytecodes are synthetic machine instructions generated by a bytecode compiler and intended to be executed by a bytecode interpreter. The term comes from the fact that most bytecode systems use 8-bit (1 byte) instructions. However, there is nothing inherent in the bytecode concept limiting instructions to a single byte. For example, the Dalvik bytecode technology, which forms part of the Android operating system, uses 16-bit instructions in its bytecode.

> P 系统是第一种获得广泛接受的同类技术。p 码的概念很快就被其他研究人员用于其他语言。虚拟机的虚拟指令集的基本思想不依赖于 Pascal 或任何其他特定的编程语言，P-System 后来被扩展为支持包括 Modula-2、BASIC 和 FORTRAN 在内的语言。**术语 p-code 最终被放弃，取而代之的是字节码**，但其含义是相同的：**字节码是由字节码编译器生成的合成机器指令，旨在由字节码解释器执行**。这个术语来源于大多数字节码系统使用 8 位(1 字节)指令的事实。然而，字节码概念中没有任何内在的东西将指令限制为单个字节。例如，Dalvik 字节码技术是 Android 操作系统的一部分，它在字节码中使用 16 位指令。

The firm Western Digital introduced an interesting product line in 1979: the Pascal MicroEngine, which was a custom microprocessor that executed UCSD p-code as its native instruction set. P-code ran much more quickly as native code without an interpreter between itself and the CPU, but the MicroEngine was eclipsed by the release of the IBM PC in 1981 and never hit critical mass. The concept of `hardware assist` for bytecode execution is a recurring theme: several vendors have released microprocessors that directly execute Java bytecode, and some members of the ARM family of CPUs include special features to execute Java language bytecode in hardware efficiently. ([Chapter 4](#07_9781119183938-ch04.xhtml) touches on this briefly.)

> Western Digital 公司在 1979 年推出了一个有趣的产品线：Pascal MicroEngine，这是一个定制微处理器，将 UCSD p 代码作为其原生指令集执行。P 代码作为本地代码运行得更快，在自身和 CPU 之间没有解释器，但 MicroEngine 在 1981 年 IBM PC 的发布中黯然失色，从未达到临界质量。字节码执行的 `硬件辅助` 概念是一个反复出现的主题：**几家供应商发布了直接执行 Java 字节码的微处理器**，并且 ARM 系列 CPU 的一些成员包括在硬件中高效执行 Java 语言字节码的特殊功能。([第 4 章](#07_9781119183938-ch04.xhtml)简要介绍了这一点。)

### Java

Bytecode never went entirely out of use after the P-System was released, but it was uncommon until the early 1990s, when James Gosling at Sun Microsystems (now a subsidiary of Oracle) developed the Java programming language and virtual machine as a bytecode system. The overriding goal with Java was portability: programs compiled to Java bytecode would run identically on any computer supporting the Java Runtime Environment (JRE). Sun popularised the slogan, `Write Once, Run Anywhere` to emphasise Java’s big selling point.

> 在 P 系统发布后，字节码从未完全停止使用，但直到 20 世纪 90 年代初，这种情况才很少见，当时 Sun Microsystems(现在是 Oracle 的子公司)的 James Gosling 将 Java 编程语言和虚拟机开发为字节码系统。Java 的首要目标是可移植性：编译成 Java 字节码的程序可以在任何支持 Java 运行时环境(JRE)的计算机上运行。Sun 推广了 `一次编写，随时随地运行` 的口号，以强调 Java 的大卖点。

Even in its first release, the Java system was much more sophisticated than the P-System ever was. The JRE includes the Java Virtual Machine (JVM), which implements the Java bytecode interpreter, as well as the Java runtime code libraries and various software tools that allow Java code to run inside web browsers and from web servers. Programmers who want to write Java programs need the Java Development Kit (JDK), which in addition to the JRE includes the Java language compiler and a number of other tools supporting software development.

> 即使在第一个版本中，Java 系统也比 P-system 更加复杂。JRE 包括 Java 虚拟机(JVM)，它实现了 Java 字节码解释器，以及 Java 运行时代码库和各种软件工具，**允许 Java 代码在 web 浏览器内部和 web 服务器上运行**。想要编写 Java 程序的程序员需要 Java 开发工具包(JDK)，除了 JRE 之外，它还包括 Java 语言编译器和许多其他支持软件开发的工具。

The JVM does more than simply execute Java bytecode. It manages an area of memory reserved for the use of Java programs, in which data items are created, used and then destroyed when no longer needed, with their memory space automatically reclaimed by a utility called a _garbage collector_. The JVM also monitors data manipulation and watches for program code that attempts to do undefined things with data that might potentially crash a program and damage the JRE or other software outside the JRE, like the operating system. The JRE became a model for similar bytecode systems created by others, and today such a system is more generally called a _managed runtime environment_ (MRE). The way bytecode programs are compiled and run in an MRE is shown in Figure 5-8.

> JVM 不仅仅执行 Java 字节码。它管理一个为 Java 程序保留的内存区域，在该区域中，数据项被创建、使用，然后在不再需要时被销毁，其内存空间由一个名为 _garbage collector_ 的实用程序自动回收。JVM 还监视数据操作并监视程序代码，这些程序代码试图使用可能导致程序崩溃并损坏 JRE 或 JRE 以外的其他软件(如操作系统)的数据执行未定义的操作。JRE 成为了其他人创建的类似字节码系统的模型，如今，这样的系统通常被称为 _managed runtime environment_(MRE)。字节码程序在 MRE 中编译和运行的方式如图 5-8 所示。

![[FIGURE 5-8:](#08_9781119183938-ch05.xhtml#rc05-fig-0008) Bytecode executed in an MRE](./media/images/9781119183938-fg0508.png)

An MRE is not by itself an operating system, and there is an operating system running underneath every MRE. The operating system manages the physical hardware of the computer on which it runs. To make itself operating-system independent, the MRE includes an operating system abstraction layer that gives the bytecode programs executed in the MRE a standard `view` of the operating system that is always the same, regardless of what operating system exists below the MRE.

> MRE 本身并不是一个操作系统，每个 MRE 下面都有一个运行的操作系统。操作系统管理其运行的计算机的物理硬件。为了使自己独立于操作系统，MRE 包括一个操作系统抽象层，该层为在 MRE 中执行的字节码程序提供了一个始终相同的操作系统的标准 `视图` ，而不管 MRE 下面存在什么操作系统。

Java was a spectacular success almost immediately. Microsoft soon saw the value in the Java idea and released its .NET Framework system in 2002 as a competitor. Architected by Anders Hejlsberg (the creator of Turbo Pascal) it included a new Java-like language, C#, which compiles to bytecode called the Common Intermediate Language (CIL), which in turn runs on the Common Language Runtime (CLR) VM.

> Java 几乎立即取得了惊人的成功。**微软很快看到了 Java 思想的价值，并于 2002 年发布了其.NET Framework 系统作为竞争对手**。它由 Anders Hejlsberg(Turbo Pascal 的创建者)设计，包括一种新的**类似 Java 的语言 C#，它可以编译成字节码，称为公共中间语言(CIL)**，后者反过来在公共语言运行时(CLR)VM 上运行。

> [!note]
> 从这里可以看到，这种在中间做动作的事情，似乎很有文章
> 车载中间件也是那是否可以从中窥见车载中间件的发展脉络和未来的历史

Many books have been published on programming Java with the JDK. One of the most popular is _The Java Tutorial: A Short Course on the Basics_, 5<sup>th</sup> edition, by Sharon Zakhour, Sowmya Kannan and Raymond Gallardo (Addison-Wesley, 2013). For younger students (aged 10 and up) _Java for Kids_ by Philip Conrod and Lou Tylee (Kidware Software, 2013) may be more accessible.

> 已经出版了许多关于用 JDK 编程 Java 的书籍。其中最受欢迎的是 Sharon Zakhour、Sowmya Kannan 和 Raymond Gallardo(Addison Wesley，2013 年)的《Java 教程：基础知识短教程》，第 5 版。对于年龄较小的学生(10 岁及以上)，Philip Conrod 和 Lou Tylee(Kidware Software，2013)的 _Java For Kids_ 可能更容易访问。

### Just-In-Time (JIT) Compilation

Portability and security are the big value-adds in bytecode systems like Java and .NET, but they come at a cost: execution speed. Interpreted bytecode, while faster than interpreted source code text in languages like BASIC (largely due to the elimination of repeated lexing and parsing) is still significantly slower than native code. One solution to this problem came out of research involving the Smalltalk language, and was first widely implemented for Java: _just-in-time_ (JIT) compilation.

> **可移植性和安全性是字节码系统(如 Java 和.NET)的巨大附加值，但它们的代价是执行速度。**解释字节码，虽然比 BASIC 等语言中的**解释源代码文本更快(主要是由于消除了重复的词法分析和解析)，但仍然比本地代码慢得多**。这个问题的一个解决方案来自于对 Smalltalk 语言的研究，并首先在 Java:_just-in-time_(JIT)编译中广泛实现。

The idea behind JIT compilation is fairly simple: instead of having the system interpret bytecode, a JIT compiler (informally called a _jitter_) compiles bytecode to native code `on the fly` , as it is needed. The whole file isn’t compiled at once and, on most systems, bytecode that is never executed isn’t compiled at all. Compilation is usually done in blocks; a block may be anything from a few consecutive bytecode instructions to an entire function. Once a block of bytecode is compiled to a block of native code, the MRE can branch directly to the native code rather than interpreting the bytecode for the block instruction by instruction. Because blocks of code are often executed multiple times during a program session, the native code blocks generated by the jitter are not discarded, but are stored in a software-managed cache (see Figure 5-9).

> JIT 编译背后的思想相当简单：JIT 编译器(非正式地称为 *jitter*)不是让系统解释字节码，而是根据需要将字节码 `动态` 编译为本机代码。整个文件不是一次编译的，在大多数系统中，从未执行过的字节码根本不会编译。编译通常分块进行；块可以是从几个连续字节码指令到整个函数的任何东西。一旦字节码块被编译成本地代码块，MRE 就可以直接分支到本地代码，而不是逐个指令解释块指令的字节码。由于代码块通常在程序会话期间执行多次，因此抖动生成的本地代码块不会被丢弃，而是存储在软件管理的缓存中(见图 5-9)。

> [!note]
> JAVA 的这种发展脉络确实可以引入实时系统中对任务的编排调度
> 对任务的编排调度也可以做到 `动态` ，这里就可以参考 JAVA
> 简单的理解是，既不是静也不是动，而是亦动亦静！

![[FIGURE 5-9:](#08_9781119183938-ch05.xhtml#rc05-fig-0009) How JIT compilation works](./media/images/9781119183938-fg0509.png)

Due to the initial overhead of JIT compilation, execution of a bytecode program is slow when the program is first run. As blocks of native code accumulate in the cache, execution occurs in native code more often, and performance improves. In general, the performance is never quite as good as a well-written program compiled with an optimising native-code compiler, but because much of the work of compilation is done when the program is first compiled from source code to bytecode, JIT compilation can be done with surprising speed.

> 由于 JIT 编译的初始开销，字节码程序在首次运行时执行速度很慢。随着本机代码块在缓存中的累积，本机代码中的**执行更加频繁，性能也会提高**。总的来说，性能永远不会比用优化的本地代码编译器编译的编写良好的程序好，但由于大多数编译工作是在程序首次从源代码编译为字节码时完成的，因此 JIT 编译可以以惊人的速度完成。

There is a sort of 80/20 effect in code execution, meaning that a relatively small proportion of program code ends up running the majority of the time. Newer versions of the Java JIT compiler contain logic that analyses a compiled Java program to determine where these `hotspots` are. It then focuses its attention on optimising those hotspots. The JIT’s analysis is _heuristic_—that is, it compiles statistics on what elements of a program impact code performance (this is called _tracing_) and `learns` as execution continues. Such a JIT compiler is called a tracing JIT. As the JIT accumulates trace data, it applies progressively more sophisticated optimisations to those code paths that execute most often.

> 在代码执行中有一种 80/20 的效果，这意味着一小部分程序代码在大部分时间内都会运行。较新版本的 Java JIT 编译器包含分析已编译 Java 程序以确定这些 `热点` 所在位置的逻辑。然后，它将注意力集中在优化这些热点上。JIT 的分析是 *heuristic* 也就是说，它编译程序中哪些元素影响代码性能的统计信息(这称为 *tracing*)，并在执行过程中 `学习` 。这种 JIT 编译器称为跟踪 JIT。**随着 JIT 积累跟踪数据，它会对那些最经常执行的代码路径逐步应用更复杂的优化。**

> [!note]
> 这种只掐要害的想法，和 CPU 中缓存命中的思想有些类似
> 这样考虑的话，在实时调度中确实可以进行考虑

A sophisticated tracing JIT can learn enough about a program during execution to actually rewrite portions of the code based on the types and even the values of function arguments. In certain circumstances these optimisations are so good that hotspots can run faster than an equivalent native program, which cannot typically be rewritten at runtime.

> 复杂的跟踪 JIT 可以在执行过程中充分了解程序，从而根据函数参数的类型甚至值重写部分代码。在某些情况下，这些优化非常好，以至于**热点的运行速度比等效的本地程序快，而本地程序通常无法在运行时重写**。

### Bytecode and JIT Compilation Beyond Java

Java remains the single most common use of bytecode technology. Since Java’s appearance, many other languages have either been designed to use bytecode or converted from pure text interpretation to bytecode, sometimes with a JIT compiler. Here’s a list of a few of the most popular:

> Java 仍然是字节码技术最常用的一种。自从 Java 出现以来，许多其他语言要么被设计为使用字节码，要么从纯文本解释转换为字节码，有时使用 JIT 编译器。以下是一些最受欢迎的：

- Ruby, inspired by Smalltalk, is commonly used with a web-application framework called Rails. Ruby and Rails are both available for the Raspberry Pi.
- JavaScript is a browser-based language supported by all modern web browsers. The current release of Mozilla Firefox includes the IonMonkey JIT compiler for JavaScript.
- Lua is a scripting language for control scripts within operating systems and applications, especially game engines. A separate implementation of the Lua language called LuaJIT uses a trace JIT compiler and achieves much higher performance than Lua 5.2. Both Lua 5.2 and LuaJIT are now distributed with Raspbian.
- Python is a bytecode language, and a JIT compiler implementation of Python called PyPy is now part of the standard Raspbian image.

> - Ruby 受到 Smalltalk 的启发，通常与名为 Rails 的 web 应用程序框架一起使用。Ruby 和 Rails 都可用于 Raspberry Pi。
> - JavaScript 是所有现代 web 浏览器都支持的基于浏览器的语言。Mozilla Firefox 的当前版本包括用于 JavaScript 的 IonMonkey JIT 编译器。
> - Lua 是一种脚本语言，用于控制操作系统和应用程序中的脚本，尤其是游戏引擎。Lua 语言的一个单独实现 LuaJIT 使用了跟踪 JIT 编译器，并**实现了比 Lua 5.2 高得多的性能**。Lua 5.2 和 LuaJIT 现在都与 Raspbian 一起发行。
> - Python 是一种字节码语言，Python 的 JIT 编译器实现 PyPy 现在是标准 Raspbian 映像的一部分。

### Android, Java and Dalvik

Oddly enough, one of the biggest uses of the Java programming language is not for the JRE at all. The Android operating system for smartphones and tablets is integrated with and depends on a bytecode MRE called Dalvik. Native code applications may be run on Android, but the Dalvik MRE is available on every Android device, without exception. An application that runs on any instance of Dalvik should run on all of them.

> 奇怪的是，Java 编程语言的最大用途之一根本不适用于 JRE。用于智能手机和平板电脑的 **Android 操作系统集成了一个名为 Dalvik 的字节码 MRE**，并依赖于它。本机代码应用程序可以在 Android 上运行，但 Dalvik MRE 在每个 Android 设备上都可用，无一例外。在 Dalvik 的任何实例上运行的应用程序都应该在所有实例上运行。

The recommended way to write applications for Android is first to write them in Java, and compile them to Java bytecode. The Android Software Development Kit (SDK) then takes the Java bytecode and compiles it to the completely different bytecode understood by the Dalvik MRE. Dalvik contains a JIT compiler that converts Dalvik bytecode to blocks of native code for whatever CPU the system runs on.

> 为 Android 编写应用程序的推荐方法是首先用 Java 编写应用程序，然后将其编译为 Java 字节码。然后，Android 软件开发工具包(SDK)**获取 Java 字节码，并将其编译为 Dalvik MRE 所理解的完全不同的字节码**。Dalvik 包含一个 JIT 编译器，它将 Dalvik 字节码转换为系统运行的任何 CPU 的本地代码块。

> [!NOTE]
> 这里又加了一层？
> 咋感觉和神经网络一样，层数多了，维度多了
> 在描述对象的时候就更容易了
> 就像解几何图形时候引入的辅助线一样，从更高的维度来看，就很简单？！

## Data Building Blocks

Earlier in this chapter, [Figure 5-4](#08_9781119183938-ch05.xhtml#c05-fig-0004) showed a simple program in diagram form to define some common terms. [Chapters 3](#06_9781119183938-ch03.xhtml) and [4](#07_9781119183938-ch04.xhtml) described the physical mechanisms by which data are stored (memory) and instructions are executed (the CPU). Now we take a closer look at some of the features that high-level languages provide to enable programmers to describe data and code.

> 在本章早些时候，[图 5-4](#08_9781119183938-ch05.xhtml#c05-fig-0004) 显示了一个以图表形式定义一些常用术语的简单程序。[第 3 章](#06_9781119183938-ch03.xhtml)和 [4](#07_978111918938-ch04.xhtml) 描述了存储数据(内存)和执行指令(CPU)的物理机制。现在，我们更仔细地看一看高级语言提供的一些功能，这些功能使程序员能够描述数据和代码。

The emphasis here is on understanding fundamental concepts, rather than on the syntax of any one specific language. The same concepts can be expressed in very different ways in different languages, but a solid grasp of the underlying principles will be of use regardless of which language you end up using.

> 这里的重点是理解基本概念，而不是任何一种特定语言的语法。相同的概念可以用不同的语言以非常不同的方式表达，但无论最终使用哪种语言，对基本原则的牢固掌握都将是有用的。

### Identifiers, Reserved Words, Symbols and Operators

In a programming language, an _identifier_ is a human-readable name given to something in the program. Most modern languages share a common lexical form for identifiers: a sequence of alphanumeric characters and underscores, where the first character is not a digit. `DelaySinceMidnight`, `Error17`, and `radius` are all identifiers. `2.746` and `42fish` are not. Some sequences of characters that would otherwise be valid identifiers may be considered _reserved words_ or _keywords_, which have special meaning to the compiler and can be used only in certain ways within the rules of the language’s syntax. The words `while` and `if` are reserved words in most languages, whereas `otherwise` is a reserved word in some languages but not others. The only way to be sure whether a word is reserved for a given language is to look in a language reference manual for that language.

> 在编程语言中，_identifier_ 是程序中某个事物的人类可读名称。大多数现代语言都有标识符的通用词汇形式：一系列字母数字字符和下划线，其中第一个字符不是数字 `DelaySinceMidnight`、`Error17` 和 `radius` 都是标识符 `2.746` 和 `42fish` 不是。
> 一些原本是有效标识符的字符序列可以被视为 _reserved words_ 或 _keywords_，它们对编译器具有特殊意义，只能在语言语法规则内以特定方式使用。单词 `while` 和 `if` 在大多数语言中是保留词，而 `otherwise` 在某些语言中是一个保留词，但在其他语言中不是。确定某个单词是否为给定语言保留的唯一方法是查看该语言的语言参考手册。

Certain non-alphanumeric characters may have special meaning in a language. Characters or short groups of characters with special meaning are called _symbols._ In C, the group `//` is a symbol called a _comment delimiter_. Anything from the `//` group to the end of a source code line is a comment that is ignored by the compiler at the preprocessing stage. (Comments, again, are meant to be read by programmers and not compilers.) In Pascal, pairs of curly braces enclose comments. In C, pairs of curly braces group statements and variable declarations to form compound statements. In C the semicolon character is a symbol called a _statement terminator_; it tells the compiler where a statement ends.

> 某些非字母数字字符在语言中可能具有特殊含义。具有特殊含义的字符或短字符组称为 _symbols_。在 C 中，组 `//` 是一个名为 _comment delimiter_ 的符号。从 `//` 组到源代码行末尾的任何内容都是编译器在预处理阶段忽略的注释。(注释，同样，是供程序员而不是编译器阅读的。)
> 在 Pascal 中，成对的大括号将注释括起来。在 C 语言中，大括号对语句和变量声明进行分组，以形成复合语句。在 C 中，分号字符是一个名为 _statement terminator_ 的符号；它告诉编译器语句的结束位置。

Some symbols are used as _operators_, which combine values to generate new values, exactly as familiar symbols like + and – do in an algebraic expression. There are operators in most languages: for familiar operations like addition, subtraction, multiplication, division and raising to a power; for bitwise and logical operations like AND, OR and XOR; for manipulation of character strings and sets; and a few odds and ends like address extraction and modulo maths. Unary operators like negation (-x in C) and bitwise NOT (~x) take one operand; binary operators like addition (x+y) and multiplication (x\*y) take two operands; some languages have ternary operators, which take three operands.

> 一些符号用作运算符，它们组合值以生成新的值，就像代数表达式中熟悉的符号 `+` 和 `–` 一样。大多数语言都有运算符：
> 用于熟悉的加法、减法、乘法、除法和乘幂运算；
> 用于位和逻辑运算，如 and、OR 和 XOR；
> 用于字符串和集合的操作；
> 还有一些零碎的东西，比如地址提取和模数学。
> 一元运算符，如求反(C 中的-x)和按位 NOT(~x)取一个操作数；
> 加法(x+y)和乘法(x\*y)等二进制运算符采用两个操作数；
> 有些语言有三元运算符，它接受三个操作数。

### Values, Literals and Named Constants

A _value_ is a single piece of data used by a program. The numbers 42 and 7.63, and the string `foo` and the Boolean values true and false (which implement Boolean logic in computer languages) are all values. Operators operate on values to create new values. In the expression `42+23`, `42` and `23` are both values (in this case they are referred to as _literal values_ or _literals_ because they appear literally in the expression), as is the result 65, which is created by the + operator at runtime.

> _value_ 是程序使用的单个数据。数字 42 和 7.63、字符串 `foo` 以及布尔值 true 和 false(在计算机语言中实现布尔逻辑)都是值。运算符操作值以创建新值。在表达式 `42+23` 中，`42` 和 `23` 都是值(在这种情况下，它们被称为 _lilateralvalues_ 或 _lilaterals_，因为它们在表达式中字面上出现)，结果 65 也是由 + 运算符在运行时创建的。

It’s often useful to give names to literals. Many languages provide a mechanism to define _named constants_, which allow an identifier to be used in place of a literal for more readable code. For example, you may be writing a program that compresses its database after more than 10,000 records are written to the database. You can define a named constant called `CompressionThreshold` with the value 10,000. This allows you to write a statement like this:

> 为文字命名通常很有用。许多语言都提供了一种定义命名常量的机制，允许使用标识符来代替文字，以获得更可读的代码。例如，您可能正在编写一个程序，该程序在向数据库写入超过 10000 条记录后压缩其数据库。可以使用值 10000 定义名为 `CompressionThreshold` 的命名常量。这允许您编写如下语句：

```c
    If RecordCount > CompressionThreshold:
       CompressDatabase()
```

Named constants allow you to name a value _once_ in your program, and use the named value everywhere in your program (which might be hundreds or thousands of places) in place of a literal. That way, if necessary, you can change the definition of the named constant at one place in your program and the compiler will `plug in` the changed literal value consistently everywhere you’ve used the constant’s name. It’s either that or change a literal value at all the necessary spots in your source code and just hope you don’t miss any!

> 命名常量允许您在程序中命名一个值 _once_，并在程序中的任何地方(可能是数百或数千个位置)使用命名值来代替文字。这样，如果有必要，您可以在程序中的一个位置更改命名常量的定义，编译器将在您使用常量名称的任何地方始终 `插入` 更改的文本值。要么就是这样，要么在源代码中的所有必要位置更改文字值，只希望您不会错过任何一个！

### Variables, Expressions and Assignment

Literals and named constants are values, and by definition are constant at runtime. If you need to change one, you must change its definition in the source code and rebuild. In contrast, _variables_ are not values but containers for values. Your program must fill them at runtime with either values given as constants or values computed by an expression. This is called _assigning_ a value to a variable, and it’s done with an assignment statement, as in the following examples:

> 文字和命名常量是值，根据定义，它们在运行时是常量。如果需要更改一个，则必须在源代码中更改其定义并重新生成。相反，_variables_ 不是值，而是**值的容器**。程序必须在运行时用给定的常量值或表达式计算的值填充它们。这称为 _assigning_ 变量赋值，它是通过赋值语句完成的，如下例所示：

```
    - C, C++, Java: `TheAnswer = 42;`
    - Python: `TheAnswer = 42`
    - Pascal: `TheAnswer := 42`
```

Although these examples look very similar, there is a little subtlety here. In Python and Pascal the assignment statement is a fundamental syntactic element of the language, whereas in C, C++ and Java assignment is performed as a side effect of the `=` operator in an expression.

> 尽管这些示例看起来非常相似，但这里有一点微妙之处。在 Python 和 Pascal 中，赋值语句是语言的**基本语法元素**，而在 C、C++ 和 Java 中，赋值是作为表达式中 `=` **运算符的副作用执行的**。

An _expression_ is a formula for the runtime calculation of a value using a language’s operators and syntax. Expressions may contain literals, named constants and variables that already contain values. If variable `R` contains the radius of a circle, the circle’s area may be computed by using the mathematical formula $\pi \times radius^{2}$. When expressed in a programming language, such a formula becomes an expression. Precisely how it’s written depends on a language’s syntax. Some languages, including Python, have a separate exponentiation operator. C, C++, Java, and Pascal do not:

> _expression_ 是使用语言的运算符和语法在运行时计算值的公式。表达式可能包含已包含值的文本、命名常量和变量。如果变量 `R` 包含圆的半径，则可以使用数学公式 $\pi \times radius^{2}$ 计算圆的面积。当用编程语言表达时，这样的公式就变成了一个表达式。它的确切写法取决于语言的语法。包括 Python 在内的一些语言有一个单独的求幂运算符。C、 C++、Java 和 Pascal 不：

```
    - C, C++, Java, Pascal, and many others : `Pi * (R * R)`
    - FORTRAN, Python, Ada, and others : `Pi * R**2`
```

In most languages, parentheses are used to set order of evaluation in expressions, just as they are in mathematical formulae.

> 在大多数语言中，括号用于设置表达式中的求值顺序，就像它们在数学公式中一样。

### Types and Type Definitions

Each data item that a program uses is represented in memory as one or more binary numbers. The meaning of a particular binary number is context-dependent: the byte 00000001<sub>2</sub> might represent the number 1, or the Boolean value `true`; the byte 01000001<sub>2</sub> might represent the number 65, or the character `A` in ASCII encoding. Most high-level languages have a type system, which associates a type with each value. The type allows the compiler or runtime to perform the appropriate operations when values are used, and to detect operations that are semantically meaningless (such as adding a Boolean to a character in many languages, or adding two pointers together in C).

> 程序使用的每个数据项在内存中表示为一个或多个二进制数。特定二进制数的含义取决于上下文：字节 ${0000000 1}_{2}$ 可能表示数字 1，或布尔值 `true` ；字节 ${01000001}_{2}$ 可能表示数字 65 或 ASCII 编码中的字符 `A` 。大多数高级语言都有一个类型系统，它将一个类型与每个值相关联。该类型允许编译器或运行时在使用值时执行适当的操作，并检测在语义上没有意义的操作(例如在许多语言中向字符添加布尔值，或在 C 中将两个指针一起添加)。

_Primitive types_ are the building blocks of a language’s type system. Common primitive types include:

> _原始类型_ 是语言类型系统的组成部分。常见的基元类型包括：

- **Booleans:** These take two values, true and false. A Boolean value can occupy as little as a single bit of storage, though for convenience at least 8 bits (1 byte) are generally used. Although not a requirement, it is common to use zero to represent false, and any non-zero number to represent true.

> -**布尔值：**这些值有两个值，true 和 false。布尔值只占用一位存储空间，但**为方便起见，通常至少使用 8 位(1 字节)**。虽然不是要求，但通常使用零表示假，使用任何非零数字表示真。

- **Integers:** Whole numbers, like 42 and –12. Unsigned integers must be positive, and can be represented as straight binary numbers; signed integers may be positive or negative, and are generally stored in two’s complement format (which is discussed in more detail in the `[Two’s Complement and IEEE 754](#08_9781119183938-ch05.xhtml#c05-sec-0040)` section). The range of representable integer values depends on the number of bits allocated to the number. C compilers for 32-bit architectures generally allocate 32 bits (4 bytes) to store an integer, giving a range of 0 to 4,294,967,295 for unsigned values.

> -**整数：**整数，如 42 和–12。无符号整数必须为正，并且可以表示为直二进制数；有符号整数可以是正整数，也可以是负整数，通常以二进制补码格式存储(这在 `[二进制补码和 IEEE 754](#08_9781119183938-ch05.xhtml#c05-sec-0040)` 一节中进行了详细讨论)。可表示整数值的范围取决于分配给该数字的位数。32 位体系结构的 C 编译器通常分配 32 位(4 字节)来存储整数，无符号值的范围为 0 到 4294967295。

- **Floats** (floating-point numbers): Can take on fractional values, like 3.4 and –10.77. Floats are often represented in memory as 32 or 64 bits of data, into which are packed a sign bit `s`, an exponent (the magnitude of the value) `e` and a mantissa (the value’s significant digits) `m`. The value represented is given by the formula:

> -**浮点数**(浮点数)：可以采用小数，如 3.4 和–10.77。浮点在内存中通常表示为 32 或 64 位数据，其中包含符号位 `s` 、指数(值的大小) `e` 和尾数(值的有效数字) `m` 。表示的值由以下公式给出：

```
   `m * 2e` if s == 0 or
   `-m * 2e` if s == 1
```

The IEEE 754 standard (which is covered in more detail later in the `[Two’s Complement and IEEE 754](#08_9781119183938-ch05.xhtml#c05-sec-0040)` section) specifies ways of packing `s`, `e` and `m` into words of various lengths, and rules for performing arithmetic operations on numbers stored in this form. Most modern architectures conform to this standard.

> IEEE 754 标准(稍后将在 `[Two's Complement and IEEE 754](#08_9781119183938-ch05.xhtml#c05-sec-0040)` 部分详细介绍)指定了打包 `s` 、 `e` 的方式 和 `m` 转换成各种长度的单词，以及对以这种形式存储的数字执行算术运算的规则。大多数现代架构都符合这个标准。

- **Characters:** Small (generally 8- or 16-bit) integers, each of which represents a character of printed text.

> -**字符：**小(通常为 8 位或 16 位)整数，每个整数代表打印文本的一个字符。

- **Strings:** Sequences of characters. Some languages provide strings as primitive types, whereas others implement strings as arrays of characters. C strings are null-terminated: the end of the string is marked by placing a special null character (with binary representation zero) in memory. Other languages store the length of the string separately alongside the array of character data or, in the case of Java, define a special class of object to represent strings. Even if strings are not primitive types, it is common to provide language features to make them appear to be. For example, in Java, where each string is represented by an instance of the system class `java.lang.String` (we will cover objects, instances and methods at the end of this chapter), it is legal to write:

> -**字符串：**字符序列。**一些语言将字符串作为原始类型提供，而另一些语言则将字符串作为字符数组实现**。C 字符串以空结尾：通过在内存中放置一个特殊的空字符(二进制表示为零)来标记字符串的结尾。其他语言将字符串的长度单独存储在字符数据数组旁边，或者在 Java 的情况下，定义一个特殊的对象类来表示字符串。即使字符串不是原始类型，提供语言特性使其看起来也是很常见的。例如，在 Java 中，每个字符串都由系统类 `Java.lang.string` 的一个实例表示(我们将在本章末尾介绍对象、实例和方法)，这样写是合法的：

`String s = foo +bar;` and the compiler silently translates this into a series of calls to methods of the `String` class.

In addition to providing primitive types, most languages provide ways of progressively building up more complex composite types by combining multiple primitive types or simpler composite types. Common varieties of composite types include:

> 除了提供原始类型之外，大多数语言还提供通过组合多个原始类型或更简单的复合类型来逐步构建更复杂的复合类型的方法。**复合类型**的常见品种包括：

- **Arrays:** Ordered sequences of variables, treated as a unit. Individual elements of an array are selected by an index, often specified using square brackets as index delimiters; for example, `GradeArray[42]`. Arrays may have more than one dimension, and each dimension may be a different size.

> -**数组：**变量的有序序列，视为一个单位。数组的单个元素由索引选择，通常使用方括号作为索引分隔符；例如 `GradeArray[42]` 。数组可以有多个维度，每个维度的大小可能不同。

- **Structs** (also called _records_ or _tuples,_ depending on the language): Groups of non-ordered named variables. Each variable in a struct is called a _member_ or a _field_. Fields within a struct are selected by name, often using the dot (`.`) field selection operator. Suppose you have a struct type named `ContactStruct` that includes a field named `LastNameField`, and a variable with type `ContactStruct` called `contact`. You would then refer to that field of `contact` using the syntax `contact.LastNameField`.

> -**结构**(也称为 _records_ 或 _tuples_，取决于语言)：非有序命名变量组。结构中的每个变量都称为 _member_ 或 _field_。结构中的字段按名称选择，通常使用点(`.`)字段选择运算符。假设您有一个名为 `ContactStruct` 的结构类型，其中包含名为 `LastNameField` 的字段和名为 `contact` 的 `ContactStrct` 类型的变量。然后使用语法 `contact.LastNameField` 引用 `contact` 的字段。

- **Sets:** Unordered collections of values, with the property that any value may not be present more than once. The internal implementation of a set is generally optimised to make testing for the presence of a particular value cheap, and facilities are provided to compute the union, intersection and differences of sets efficiently.

> -**集合：\*\***无序的值集合，具有任何值不能出现多次**的属性。**集合的内部实现通常被优化\*\*，以使测试特定值的存在变得廉价，并且提供了有效计算集合的并集、交集和差的设施。

- **Maps or dictionaries:** Provide a mechanism for storing a collection of values, each of which is indexed by a key. This can be a seen as a generalisation of the array composite type, often using the same square bracket notation, but allowing keys of (nearly) arbitrary types rather than just integers and eliminating the requirement to specify a maximum size when the array is created.

> -**映射或字典：**提供一种存储值集合的机制，每个值都**由键索引**。这可以看作是数组组合类型的一种推广，通常使用相同的方括号表示法，但**允许(几乎)任意类型的键，而不仅仅是整数，并且消除了创建数组时指定最大大小的要求**。

- **Enumerations:** Unordered collections of values, each given an arbitrary name by the programmer; the value chosen to represent each member is generally chosen automatically by the compiler. They can be used as a type-safe alternative to named constants if we have, for example, a parameter that controls the behaviour of a function and can take one of a small number of distinct values.

> -**枚举：\*\***无序的值集合，每个值由程序员指定一个任意名称\*\*；选择来表示每个成员的值通常由编译器自动选择。例如，如果我们有一个控制函数行为的参数，并且可以取少量不同值中的一个，那么它们可以用作命名常量的类型安全替代。

- **Pointers:** These specify the location of another value in memory and are generally defined to point to an instance of a specific type. When we have a pointer, we can dereference (follow) it to manipulate the underlying value. Careless use of pointers can lead to hard-to-debug crashes and security exploits, which is one reason that some languages, especially Java, do not include unrestricted pointer types but instead provide runtime-checked, type-safe references to objects or arrays.

> -**指针：**它们指定内存中另一个值的位置，通常定义为指向特定类型的实例。当我们有一个指针时，我们可以取消引用(跟随)它来操作基础值。不小心地使用指针可能会导致难以调试的崩溃和安全漏洞，这也是某些语言(尤其是 Java)不包含不受限制的指针类型，而是提供对对象或数组的运行时检查、类型安全引用的原因之一。

### Static and Dynamic Typing

Programming languages can be broadly divided into statically and dynamically typed languages based on how they treat types. In _statically typed_ languages such as C, types are associated with variables when the code is written, and the type of a value stored in a variable is implicitly that of the variable itself; the compiler is able to allocate storage for variables, and for the intermediate results generated when evaluating expressions, ahead of time, which is efficient, and can perform semantic analysis (as we saw in the section on compilers) to detect and flag operations between incompatible operands at compile time.

> 编程语言可以根据其处理类型的方式大致分为**静态和动态类型语言**。在诸如 C 之类的结构化语言中，类型在编写代码时与变量相关联，存储在变量中的值的类型隐含地是变量本身的类型；编译器能够提前为变量和计算表达式时生成的中间结果分配存储空间，这是高效的，并且可以执行语义分析(正如我们在编译器一节中所看到的)，以在编译时检测和标记不兼容操作数之间的操作。

In the following fragment of C code, the variable `foo` has type `int`, and the variable `bar` has type `float`. The compiler knows it can allocate either a single machine register or a 4-byte section of stack to hold each value (on a typical 32-bit machine), and that when adding them together it must (according to the C type rules) emit an instruction to convert or cast `foo` into a floating-point value, followed by a floating-point add instruction:

> 在下面的 C 代码片段中，变量 `foo` 的类型为 `int` ，变量 `bar` 的类型是 `float` 。编译器知道它可以分配一个机器寄存器或一个 4 字节的堆栈段来保存每个值(在典型的 32 位机器上)，并且在将它们相加时，它必须(根据 C 类型规则)发出一条指令，将 `foo` 转换或转换为浮点值，然后是一条浮点加法指令：

```c
    int foo = 42;
    float bar = 98.2;
    …
    float baz = foo + bar;
```

Throughout the lifetime of a variable in a statically typed language, only compatible values may be assigned to a variable, so the following C example will result in a compilation error:

> 在**静态类型语言中变量的整个生命周期中，只能为变量分配兼容值**，因此以下 C 示例将导致编译错误：

```c
    int foo = 42;               // foo has type int
    char *bar = `hello world` ;  // bar has type `pointer to char`
    foo = bar;                  // error!
```

By contrast, in _dynamically typed_ languages such as Python and JavaScript, types are associated with values at runtime. Variables have no type: they merely contain a reference to a typed value; in a naïve implementation, storage for the value (and a description of its type) will be allocated on the heap and recovered when it is no longer needed by a process of garbage collection. Semantic checks on the types of operands occur at runtime; this is potentially expensive, though the development of tracing JITs for dynamically typed languages has reduced the cost substantially.

> 相反，在动态类型语言(如 Python 和 JavaScript)中，类型与运行时的值相关联。**变量没有类型：它们只包含对类型值的引用**；在一个幼稚的实现中，值的存储(以及其类型的描述)将分配到堆上，并在垃圾收集过程不再需要时恢复。在运行时对操作数类型进行语义检查；**尽管为动态类型化语言开发跟踪 JIT 已经大大降低了成本，但这可能会很昂贵**。

In the following fragment of Python code, the function `add()` is invoked three times. On the first invocation, `x` and `y` refer to two values of type `int`, so the `+` operator is deemed to represent integer addition. On the second, `x` and `y` refer to two values of type `string`, so the `+` operator is deemed to represent concatenation. On the third, `x` and `y` have different types, so the attempt to add them causes a `TypeError` to be thrown. A tracing JIT, such as that found in PyPy, would potentially compile two versions of this function and invoke the appropriate one based on the operand types:

> 在下面的 Python 代码片段中，函数 `add()` 被调用了三次。
> 在第一次调用时，`x` 和 `y` 引用两个类型为 `int` 的值，因此 `+` 运算符被视为表示整数加法。
> 在第二种情况下，`x` 和 `y` 指的是 `string` 类型的两个值，因此 `+` 运算符被视为表示串联。
> 在第三种情况下，`x` 和 `y` 具有不同的类型，因此尝试添加它们会引发 `TypeError` 。
> 跟踪 JIT(如 PyPy 中的 JIT)可能会编译此函数的两个版本，并根据操作数类型调用相应的版本：

```python
    def add(x, y):
       return x + y

    print add(1, 2)                    # prints `3`
    print add( 'hello ' , 'world' )       # prints 'hello world'
    print add( 'foo' , 1)                # gives TypeError
```

As you will see shortly, statically typed object-oriented languages such as C++ and Java provide some dynamic features through the use of subtype polymorphism. Programmers can declare several types B, C or D, which are derived from type A and rely on dynamic dispatch to do different things depending on which type a particular value is an instance of. Polymorphism comes into play through object-oriented programming, which we’ll cover later in the section `[Object-Oriented Programming](#08_9781119183938-ch05.xhtml#c05-sec-0051)` .

> 正如您不久将看到的，**静态类型的面向对象语言(如 C++ 和 Java)通过使用子类型多态性提供了一些动态特性**。程序员可以声明几种类型 B、C 或 D，这些类型是从类型 A 派生的，并依赖于动态分派来执行不同的操作，具体取决于特定值是哪种类型的实例。多态性通过面向对象编程发挥作用，我们稍后将在 `[面向对象编程](#08_9781119183938-ch05.xhtml#c05-sec-0051)` 一节中介绍。

### Two’s Complement and IEEE 754

There are a number of possible ways of representing signed integers as strings of binary digits. Perhaps the most obvious is _sign and magnitude_ notation, in which we have a single bit that is set to one if the number represented is negative and a string of digits that represents the unsigned version of the number (its magnitude). Although this is simple to understand, it is unsatisfying that zero has two representations (+0 and –0), and arithmetic operations are somewhat difficult to implement: when we add two signed numbers, we must inspect the sign bits, decide whether to add or subtract the unsigned magnitudes, and then perform conversions to get the result back into sign and magnitude format.

> 有多种可能的方式将有符号整数表示为二进制数字字符串。也许最明显的是 _sign_ 和 _magnitude_ 表示法，其中，如果表示的数字是负数，我们有一个设置为 1 的位，以及一个表示数字的无符号版本(其大小)的数字串。虽然这很容易理解，但**令人不满意的是零有两种表示(+0 和–0)**，算术运算有些难以实现：当我们**添加两个有符号数字时，我们必须检查符号位，决定是添加还是减去无符号大小，然后执行转换以将结果返回到符号和大小格式**。

The vast majority of architectures represent numbers using _two’s complement_ notation. To compute the two’s complement representation of a negative number, we write the regular binary representation of the positive number and then invert every bit and add one. For example, the 8-bit binary representation of five is:

> 绝大多数体系结构使用 _two's complement_ 表示法表示数字。为了计算负数的两个补码表示，我们写正数的正则二进制表示，然后反转每一位并加一。例如，5 的 8 位二进制表示为：

```
    5 = 00000101<sub>2</sub>
```

To find the representation of -5, we invert each bit:

```
    11111010<sub>2</sub>
```

and add one:

```
    11111011<sub>2</sub> = -5
```

Table 5-1 shows the 8-bit binary and hexadecimal representations of the numbers from 3 down through 0 to -3.

```
		-------------------------------------------------- ----------------------------------------------------- --------------------------------------------------------  `Binary`    `Hexadecimal`  `Signed decimal`  `00000011`  `03`           `3`  `00000010`  `02`           `2`  `00000001`  `01`           `1`  `00000000`  `00`           `0`  `11111111`  `FF`           `-1`  `11111110`  `FE`           `-2`  `11111101`  `FD`           `-3`   -------------------------------------------------- ----------------------------------------------------- --------------------------------------------------------
```

The useful property of two’s complement notation is that regular unsigned addition now works to calculate the sum of signed values, regardless of whether they are positive or negative. So, for example:

> 补码符号的有用特性是，**无论正负，正则无符号加法现在都可以计算有符号值的和**。例如：

```
    1 + -3 = 00000001<sub>2</sub> + 11111101<sub>2</sub> = 11111110<sub>2</sub> = -2
    -1 + -2 = 1111111<sub>2</sub> + 11111110<sub>2</sub> = 11111101<sub>2</sub> (with 1 carried out) = -3
```

The situation for real numbers (values that may have decimal parts) is more complex. One possibility is to multiply the real number by a large constant (often a power of two), and then round the result to an integer, which can then be represented using two’s-complement notation. We might choose the constant 256 = 2<sup>8</sup>, so the number 1.0 would be represented as 256, and 2.125 would be represented as 544. This is referred to as a _fixed-point_ representation, because a fixed number of bits in the representation (in this case 8) are allocated to storing the fractional part of the number, with the rest allocated to storing the integer part.

> 实数(可能有小数部分的值)的情况更为复杂。一种可能是将实数乘以一个大常数(通常是 2 的幂)，然后将结果四舍五入为一个整数，然后可以用补码表示法表示。我们可以选择常数 256=2<sup>8</sup>，因此数字 1.0 表示为 256，2.125 表示为 544。这被称为 _fixed-point_ 表示，因为表示中的固定位数(在本例中为 8)被分配用于存储数字的小数部分，其余的被分配用于保存整数部分。

In most applications, the operations that are performed on real numbers involve values of widely varying magnitude; this can make it hard to choose an appropriate multiplier for a fixed-point representation. It is therefore customary to use a floating-point representation for real numbers, in which there is no fixed number of digits to the right of the decimal point. Floating-point numbers consist of a mantissa (the significant bits of the value), an exponent (the magnitude of the value) and a sign, positive or negative, packed into a single binary word. The representation and range of floating-point values, and the exact results of floating-point operations, were compiler-dependent until the IEEE 754 floating-point number standard appeared in 1985. IEEE 754 defines several floating-point formats that may be used as types in programming languages. The range of some is breathtaking: the 128-bit floating-point number can express positive values as high as 10<sup>6144</sup>. (To put this number into perspective, consider that there are `only` about 10<sup>80</sup> atoms in the entire observable universe.) Figure 5-10 shows how the three elements of a floating-point value (the sign, the mantissa and the exponent) are packed into an IEEE 754 64-bit value.

> 在大多数应用中，对实数执行的运算涉及幅度变化很大的值；这可能会导致**很难为定点表示选择合适的乘数**。因此，习惯于对实数**使用浮点**表示，其中小数点右侧没有固定位数。浮点数由尾数(值的有效位)、指数(值的大小)和正负符号组成，打包成一个二进制字。直到 1985 年 IEEE 754 浮点数标准出现之前，浮点值的表示和范围以及浮点运算的精确结果都依赖于编译器。IEEE 754 定义了几种可以用作编程语言类型的浮点格式。一些的范围是惊人的：128 位浮点数可以表示高达 10<sup>6144</sup>的正值。(为了将这个数字放在一个角度，请考虑在整个可观测宇宙中 `只有` 大约 10 个<sup>80</sup>原子。)图 5-10 显示了浮点值的三个元素(符号、尾数和指数)是如何被打包成 IEEE 754 64 位值的。

![[FIGURE 5-10:](#08_9781119183938-ch05.xhtml#rc05-fig-0010) Inside a 64-bit floating-point number](./media/images/9781119183938-fg0510.png)

## Code Building Blocks

A single-threaded program in an imperative programming language is a description of a series of steps required to perform an operation. A _statement_ is a complete description of one of those steps. It’s the equivalent of a sentence in a language spoken by humans. Put some number of statements in sequence, and you have a program. In broad terms, there are really only four kinds of statements:

> 命令式编程语言中的单线程程序是对执行操作所需的一系列步骤的描述。语句是对其中一个步骤的完整描述。这相当于人类所说的语言中的一个句子。按顺序排列一些语句，你就有了一个程序。广义而言，实际上只有四种说法：

- **Assignment statements:** These give a value to a variable or an element of a compound variable, as explained a little earlier in this section.
- **Function calls:** These are invocations of functions defined in a library or elsewhere in the program; for example, `print()` or `factorial()`. A function call is typically made simply by naming the function and providing zero or more arguments.
- **Control statements:** These alter the sequence of execution within the current function.
- **Compound statements:** These are sequences of statements treated as a group within some sort of control statement.

> - **赋值语句：**如本节前面所述，这些语句为变量或复合变量的元素提供值。
> - **函数调用：**这些是在库或程序中其他地方定义的函数调用；例如 `print()` 或 `factorial()`。函数调用通常只需命名函数并提供零个或多个参数即可完成。
> - **控制语句：**这些语句改变当前函数内的执行顺序。
> - **复合语句：**这些语句序列被视为某种控制语句中的一个组。

Control statements and compounds statements are inextricably connected, and we’ll treat them together.

> 控制语句和复合语句是密不可分的，我们将一起处理它们。

### Control Statements and Compound Statements

Being able to change the course of execution of a program at runtime is fundamental to the programming idea. Some statements must be executed under some circumstances but not others. This is called _conditional execution_. Some statements must be executed not once but multiple times. This is called _looping_. An imperative programming language provides varieties of control statement to implement each of these behaviours.

> 能够**在运行时改变程序的执行过程是编程思想的基础**。某些语句必须在某些情况下执行，但不能在其他情况下执行。这称为条件执行。某些语句必须执行多次，而不是一次。这称为 _looking_。命令式编程语言提供各种控制语句来实现这些行为。

Compound statements are written as sequences of statements between delimiters. In C, C++, C#, Java, and languages descended from them, these delimiters are generally curly braces (`{` and `}`). In Pascal and Ada, the delimiters are the keywords `begin` and `end`. Python is rare among languages in that it lacks delimiters completely. Compound statements in Python are delimited by indentation in the source code. We’ll show you how this works in the examples for the control statements.

> 复合语句被写成分隔符之间的语句序列。在 C、C++、C#、Java 及其派生语言中，这些分隔符通常是大括号( `｛` 和 `｝` )。在 Pascal 和 Ada 中，分隔符是关键字 `begin` 和 `end` 。Python 在语言中很少见，因为它完全缺少分隔符。Python 中的复合语句由源代码中的缩进分隔。我们将在控制语句的示例中向您展示这是如何工作的。

### If/Then/Else

The most fundamental control statement is the `if/then/else` statement, which exists in some form in all programming languages. The general structure of the statement is illustrated in Figure 5-11.

> 最基本的控制语句是 `if/then/else` 语句，它以某种形式存在于所有编程语言中。该声明的一般结构如图 5-11 所示。

![[FIGURE 5-11:](#08_9781119183938-ch05.xhtml#rc05-fig-0011) The `if/then/else` statement](./media/images/9781119183938-fg0511.png)

The simplest form of `if` statement tests a condition and executes a statement if the condition evaluates to `true`. If the condition is not true, execution falls through and continues with the statement immediately following the `if` statement.

> `if` 语句的最简单形式是测试一个条件，并在条件求值为 `true` 时执行一条语句。如果条件不为真，则执行失败，并继续执行紧接在 `If` 语句之后的语句。

To reiterate: _don’t obsess on syntax._ You can always look up syntax in a language reference. Focus on the logic. A simple example will give you a sense of the different ways that programming languages express the same logic:

> 重申一下：不要拘泥于语法您始终可以在语言引用中查找语法。关注逻辑。一个简单的例子将让您了解编程语言表达相同逻辑的不同方式：

```
    if (I > 99) FieldOverflow(Fieldnum, I);           C and its descendants`
    if I > 99 then FieldOverflow(Fieldnum, I)         Pascal`
    if I > 99:FieldOverflow(Fieldnum, I)                     Python`
```

> [!NOTE]
> from the examples above that the C family of languages lacks the keyword `then`, and in Python the colon, line break and indentation are an essential part of the syntax. If you’re coming to Python from some other language (especially C or its relatives) it’s crucial to remember: Python considers whitespace (line breaks, spaces, and tabs) significant. Very few other programming > languages do.
> 从上面的例子可以看出，**C 语言家族缺少关键字 `then` **，而在 Python 中，冒号、换行符和缩进是语法的重要组成部分。如果您是从其他语言(尤其是 C 或其亲戚)转到 Python，请务必记住：**Python 认为空格(换行符、空格和制表符)很重要**。很少有其他编程语言这样做。

`If` statements may contain an optional `else` part, which specifies a statement or compound statement to execute when the tested condition is not true. This is the last portion of the diagram in [Figure 5-11](#08_9781119183938-ch05.xhtml#c05-fig-0011). In between `then` and `else` you have the opportunity to insert additional tests, each governing execution of a statement or a compound statement. There may be any reasonable number of such nested tests, which are called `else/if` structures.

> `If​​` 语句可能包含可选的 `else` 部分，它指定在测试条件不为真时要执行的语句或复合语句。这是[图 5-11](#08_9781119183938-ch05.xhtml#c05-fig-0011) 中图表的最后一部分。在 `then` 和 `else` 之间，您有机会插入额外的测试，每个测试控制语句或复合语句的执行。可能有任何合理数量的此类嵌套测试，称为 `else/if` 结构。

What are multiple `else/if` s good for? One metaphor would be sorting categories out of a disordered pile. If you have a jar full of coins and want to bag them up for deposit at the bank, you first sit down at the table and sort them. Is the coin a penny? If so, slide it to the penny pile; otherwise, is it two pence? If so, slide it to the two-pence pile; otherwise, is it five pence? If so, slide it to the five-pence pile, and so on, up to the two-pound denomination. This form of logic is called a _multi-way branch_.

> 多重 `else/if` 有什么好处？一个比喻是**把一堆乱七八糟的东西分类**。如果你有一个装满硬币的罐子，想把它们装在袋子里存放在银行，你先坐在桌子旁把它们分类。硬币是一便士吗？如果是，请将其滑到硬币堆上；否则，是两便士吗？如果是，把它滑到两便士硬币堆上；否则，是五便士吗？如果是的话，把它滑到五便士硬币堆上，以此类推，直到两英镑面值。这种形式的逻辑被称为 _多路分支_。

### Switch and Case

Multi-way branches are so common in programming that in many languages a special type of control statement is provided to implement them. Different languages implement multi-way branch logic in different ways, using different keywords. The C family calls it a `switch` statement and uses the keyword `switch`. Pascal and Ada call it a `case` statement and use the keyword `case`. (A few languages, including FORTRAN and some versions of BASIC, use `select case`.)

> 多路分支在编程中非常常见，因此在许多语言中都提供了一种特殊类型的控制语句来实现它们。不同的语言使用不同的关键字以不同的方式实现多路分支逻辑。C 系列将其称为 `switch` 语句，并使用关键字 `switch` 。Pascal 和 Ada 将其称为 `case` 语句，并使用关键字 `case` 。(一些语言，包括 FORTRAN 和一些 BASIC 版本，使用 `select case` 。)

Unfortunately, the logic behind C’s `switch` is not quite the same as the logic behind Ada’s and Pascal’s `case`. The two are different enough, in fact, so that they should be mapped out separately. The general form of a `case` statement is shown in Figure 5-12. The general form of a `switch` statement is shown in Figure 5-13.

> 不幸的是，C 的 `switch` 背后的逻辑与 Ada 和 Pascal 的 `case` 后面的逻辑并不完全相同。事实上，这两者有着很大的不同，因此应该分别绘制它们。`case` 语句的一般形式如图 5-12 所示。`switch` 语句的一般形式如图 5-13 所示。

![[FIGURE 5-12:](#08_9781119183938-ch05.xhtml#rc05-fig-0012) The `case` statement](./media/images/9781119183938-fg0512.png)

![[FIGURE 5-13:](#08_9781119183938-ch05.xhtml#rc05-fig-0013) The `switch` statement](./media/images/9781119183938-fg0513.png)

The `case` statement is the simpler of the two. In a `case` statement, a variable is tested against a list of cases. Each case contains an individual value or list of values, generally expressed as constants. If the variable’s value matches one of the cases, the statement or compound statement belonging to that case is executed. In the coin metaphor, the case values on the left would literally be the values of each denomination. The statement associated with the penny case would increment a counter that tallies pennies, and so on. In a `case` statement, once a match is found and the case’s action is taken, the `case` statement is done, and execution continues with the next statement in the program. If no match is found, an optional `otherwise` case can be used to take a `none of the above` action. In our metaphor, this might be the action taken when a foreign coin like an American quarter or Mexican peso is found in the coin pile.

> case 语句是这两个语句中比较简单的一个。在 `case` 语句中，将根据案例列表测试变量。每种情况都包含一个单独的值或值列表，通常表示为常量。如果变量的值与其中一个 case 匹配，则执行属于该 case 的语句或复合语句。在硬币的比喻中，左边的大小写值实际上就是每个面额的值。与一分钱大小写关联的语句将递增一个计数一分钱的计数器，依此类推。在 `case` 语句中，一旦找到匹配项并执行大小写操作，`case` 就完成了，并继续执行程序中的下一条语句。如果找不到匹配项，则可以使用可选的 `otherwise` 情况来执行 `无上述` 操作。在我们的比喻中，这可能是当在硬币堆中发现像美国 25 美分或墨西哥比索这样的外国硬币时采取的行动。

The `switch` statement is similar, but with a very important twist: once a value is found, the case containing that value is executed, as are all the cases that follow it. If only one case is to be executed, a `break` statement must be placed at the end of the statements present in that case. A `break` statement ends the `switch` statement, and causes execution to continue with the next statement in the program. As with `case`, an optional `none of the above` case (this time referred to as the `default` case) can be defined.

> `switch` 语句类似，但有一个非常重要的转折点：**一旦找到一个值，就执行包含该值的 case，后面的所有 case 也是如此。如果只执行一个 case，则必须在该 case 中出现的语句末尾放置一个 `break` 语句。`break` 语句结束 `switch` 语句，并使程序中的下一条语句继续执行。**与 `case` 一样，可以定义可选的 `无上述情况` 情况(这次称为 `默认` 情况)。

This may seem bizarre to beginners, especially if they’ve used languages with the simpler `case` statement. The reason for case-action fall-through in `switch` is historical; it’s descended from a FORTRAN statement called a computed goto. In modern practice, there’s a `break` statement at the end of every case except in rare circumstances. When every case ends with a `break` statement, `switch` works the same way as `case`. We’ll see the `break` statement appear again shortly, in connection with loops.

> 对于初学者来说，这可能很奇怪，特别是如果他们使用的语言带有更简单的 `case` 语句。`switch` 中案例操作失败的原因是历史性的；**它是 FORTRAN 语句的派生，称为计算 goto。**在现代实践中，除了在罕见的情况下，每个案件的结尾都有一个 `中断` 陈述。当每个 case 都以 `break` 语句结束时，`switch` 的工作方式与 `case` 相同。我们将很快看到 `break` 语句再次出现，与循环相关。

---

> [!NOTE]

Python offers neither `switch` nor `case`, and multi-way branches must be written either as `else`/`if` sequences or by using Python dictionaries and functions, as in the following example:

> Python 既不提供 `switch` 也不提供 `case` ，多路分支必须写成 `else` / `if` 序列，或者使用 Python 字典和函数，如下例所示：

```python
    def case_penny():
      print 'Got a penny!'
    def case_tuppence():
      print 'Got a tuppence!'
    def case_fivepence():
      print 'Got a five pence!'
    def default():
      print 'Got something else!'

    Coincases = {'1': case_penny, '2': case_tuppence, '5': case_fivepence}

    x = raw_input('Coin value? ')

    if Coincases.has_key(x):
      Coincases[x]()
    else:
      default()
```

### Repeat Loops

When a statement or compound statement must be executed multiple times, it’s done within a framework called a _loop_. There are three general types of loop in programming:

> 当一个语句或复合语句必须执行多次时，它是在一个名为 _loop_ 的框架内完成的。编程中有三种常见的循环类型：

- **`repeat`** **loops:** These take some action and then test a condition. If the condition evaluates to `true`, the loop ends. Otherwise, the action is repeated.
- **`while`** **loops:** These test a condition first. If the condition evaluates to `true`, some action is taken. Otherwise, the loop ends.
- **`for`** **loops:** These take action once for every value in a collection of values. In computer science this is called _iteration_.

> - **`repeat`**循环：\*\*这些循环执行一些操作，然后测试条件。如果条件求值为 `true` ，则循环结束。否则，重复该操作。
> - **`而`**循环：\*\*这些循环首先测试一个条件。如果条件的计算结果为 `true` ，则会采取一些操作。否则，循环结束。
> - **`for `**循环：这些循环对值集合中的每个值执行一次操作。在计算机科学中，这叫做迭代。

The `repeat` loop is the simplest to understand. It’s illustrated in Figure 5-14. The sense of the logic is that some action is repeated until a condition becomes `true`. At that point the loop ends. If the test at the end of the loop turns up `false`, execution returns to the top of the loop and begins again. What’s important to remember is that a `repeat` loop’s action is always performed at least once.

> `重复` 循环最容易理解。如图 5-14 所示。逻辑的意义是，某些动作被重复，直到条件变为 `真` 。此时，循环结束。如果循环末尾的测试结果为 `false` ，则执行返回到循环的顶部并再次开始。重要的是要记住，`重复` 循环的动作总是至少执行一次。

![[FIGURE 5-14:](#08_9781119183938-ch05.xhtml#rc05-fig-0014) The `repeat` statement](./media/images/9781119183938-fg0514.png)

The `repeat` statement uses the `repeat` and `until` keywords in Pascal and languages descended from Pascal. In C and other C-like languages, `repeat` loops are implemented with the keywords `do` at the beginning of the loop and `while` at the end. The flow of control is the same, but the sense of the test is reversed, so the loop terminates when the test returns `false`.

> `repeat` 语句使用 Pascal 语言和 Pascal 语言的 `repeat` 和 `until` 关键字。在 C 语言和其他类 C 语言中，`repeat` 循环在循环的开头使用关键字 `do` ，在结尾使用关键字 `while` 。控制流程相同，但测试的意义相反，因此当测试返回 `false` 时，循环终止。

### While Loops

The `while` loop is like a `repeat` loop upside-down: The test is made at the _beginning_ of the loop rather than at the end. The condition is tested, and if the test returns `true`, the loop’s action is performed. After each pass through the loop, the condition is again tested at the top. When the condition returns `false`, the loop ends. If the condition is initially found to be `false`, the loop ends immediately and its action is never taken at all. See Figure 5-15.

> `while` 循环就像颠倒的 `repeat` 循环：测试是在循环的开头而不是结尾进行的。测试条件，如果测试返回 `true` ，则执行循环操作。每次通过循环后，再次在顶部测试条件。当条件返回 `false` 时，循环结束。如果最初发现条件为 `false` ，则循环立即结束，并且根本不执行其操作。见图 5-15。

![[FIGURE 5-15:](#08_9781119183938-ch05.xhtml#rc05-fig-0015) The `while` statement](./media/images/9781119183938-fg0515.png)

### For Loops

There are times when you need to perform an operation once for each element in a collection of values, rather than looping until a condition becomes `true` or `false`. This is called a `for` loop. Some languages restrict `for` loops to iterate over a sequence of monotonically increasing or decreasing integers that differ by a fixed step. So, for example, in Pascal we might write:

> 有时需要对值集合中的每个元素执行一次操作，而不是循环，直到条件变为 `true` 或 `false` 。这称为 `for` 循环。一些语言限制 `for` 循环在一系列单调递增或递减的整数上迭代，这些整数相差一个固定的步长。例如，在 Pascal 中，我们可以写：

```
    FOR i := 10 TO 20 DO  { Display every integer from 10 to 20 }
      WRITELN(i);
```

or in some dialects of BASIC it would look like this. (The `REM` means that the line is a remark; that is, a comment):

> 或者在 BASIC 的一些方言中，它看起来像这样。( `REM` 表示该行是注释；即注释)：

```basic
    REM PRINT 0, 2, 4, 6, 8, 10

    FOR I = 0 TO 10 STEP 2
      PRINT I
    NEXT
```

The variable that takes on the integer value for the current iteration is referred to as the _loop counter_. It’s possible that the loop counter is used simply as a counter and takes no part in the work done by the loop statements other than to dictate the number of times that the statements in the loop are executed. Most of the time, however, the loop counter is used to access elements in an array or to take part in some calculation.

> 在当前迭代中采用整数值的变量称为 _loop counter_。循环计数器可能仅用作计数器，除了指定循环中语句的执行次数外，它不参与循环语句所做的工作。然而，大多数时候，循环计数器用于访问数组中的元素或参与某些计算。

Python supports iteration over arbitrary collections of values, so we might write the following. (In Python, a line beginning with `#` is a comment):

> Python 支持对任意值集合的迭代，因此我们可以编写以下内容。(在 Python 中，以 `#` 开头的一行是注释)：

```python
    # print `foo`, `bar`, `baz`
    for s in [`foo`, `bar`, `baz`]:
      print s
```

A BASIC-like `for` loop can be implemented in Python using the built-in function `range()`, which generates the sequence of integers between a start and an end value with an optional step value. We could write the preceding BASIC example like this:

> 类似 BASIC 的 `for` 循环可以使用内置函数 `range()` 在 Python 中实现，该函数使用可选的步长值在开始值和结束值之间生成整数序列。我们可以这样编写前面的 BASIC 示例：

```
    # print 0, 2, 4, 6, 8, 10
    for i in range(0, 12, 2):   # ranges do not include the end value
      print i
```

C provides a very flexible `for` loop construct that behaves like a generalised `while` loop. It allows the user to specify an initialisation operation to occur before the loop, a loop test that is evaluated before each iteration and must be non-zero for the loop to proceed, and an operation to perform to move to the next element. So we might write the following to iterate over and print every element in a linked list:

> **C 提供了一个非常灵活的 `for` 循环构造，其行为类似于广义的 `while` 循环**。它允许用户指定在循环之前发生的初始化操作、在每次迭代之前评估的循环测试，循环必须为非零才能继续，以及要执行的操作以移动到下一个元素。因此，我们可以编写以下代码来遍历并打印链接列表中的每个元素：

```
    LINK_T *link;
    for (link = start; link != NULL; link = link->next)
      printf (`%d\n`, link->payload);
```

Figure 5-16 shows the logic of `for` loops.

> 图 5-16 显示了 `for` 循环的逻辑。

![[FIGURE 5-16:](#08_9781119183938-ch05.xhtml#rc05-fig-0016) The `for` statement](./media/images/9781119183938-fg0516.png)

### The Break and Continue Statements

Many languages provide two special-purpose control statements that are used almost exclusively in loops. A `break` statement ends the loop unconditionally. Execution continues with the next statement after the innermost enclosing loop. `break` may be placed anywhere in the loop, usually under the control of an `if`/`then`/`else` statement inside the loop. (As we saw earlier, the `break` statement is also used in `switch` statements.)

> 许多语言提供了两种特殊用途的控制语句，它们几乎只在循环中使用。`break` 语句无条件地结束循环。执行将在最内部的封闭循环之后继续执行下一条语句 `break` 可以放在循环中的任何地方，通常在循环内的 `if` / `then` / `else` 语句的控制下。(如前所述，`break` 语句也用于 `switch` 语句中。)

The `continue` statement may also be placed anywhere inside the loop, generally under the control of an `if`/`then`/`else` statement. When executed, `continue` jumps immediately to the test that governs the loop, so that the test is made again. In a sense, `continue` `short-circuits` the current pass through the loop. See Figure 5-17 to see the operation of `break` and `continue` shown side by side.

> `continue` 语句也可以放在循环内的任何地方，通常在 `if` / `then` / `else` 语句的控制下。执行时，`continue` 立即跳转到控制循环的测试，以便再次进行测试。在某种意义上，`continue` `short-circuits` 电流通过回路。参见图 5-17，查看并排显示的 `break` 和 `continue` 操作。

![[FIGURE 5-17:](#08_9781119183938-ch05.xhtml#rc05-fig-0017) The `break` and `continue` statements](./media/images/9781119183938-fg0517.png)

---

> [!NOTE]

The example shown in [Figure 5-17](#08_9781119183938-ch05.xhtml#c05-fig-0017) is a `while` loop, but `break` and `continue` work in all loop types.

> [图 5-17](#08_9781119183938-ch05.xhtml#c05-fig-0017) 中所示的示例是 `while` 循环，但 `break` 和 `continue` 在所有循环类型中都有效。

It’s worth remembering that `break` and `continue` are not necessarily present in all programming languages. Some languages support one or both under different keywords; for example, `continue` is implemented in Ruby as the `next` keyword.

> 值得记住的是，`break` 和 `continue` 不一定存在于所有编程语言中。有些语言在不同的关键字下支持一种或两种；例如，`continue` 在 Ruby 中实现为 `next` 关键字。

### Functions

In an imperative programming language, a _function_ is a named sequence of statements. When the function is called from elsewhere in the program, its statements are executed until execution reaches the end of the function or a `return` statement, at which point the function ends and execution continues at the statement following the call to the function (see Figure 5-18). Functions allow common tasks to be defined in one place and used whenever necessary, keeping duplication of code to a minimum.

> 在命令式编程语言中，_function_ 是一个命名的语句序列。当从程序的其他地方调用函数时，将执行其语句，直到执行到达函数的结尾或 `返回` 语句，此时函数结束，并在调用函数后的语句处继续执行(见图 5-18)。函数允许在一个地方定义通用任务，并在必要时使用，从而将代码重复降至最低。

![[FIGURE 5-18:](#08_9781119183938-ch05.xhtml#rc05-fig-0018) Function calls and returns](./media/images/9781119183938-fg0518.png)

That’s how functions operate from an execution standpoint. They have another very important trick: you can pass data values into a function. The function, having made use of those data values, can return one (or in some languages more than one) new value to the code that calls it. Because functions may return values, they can be used in expressions as well as statements. Figure 5-19 shows how this works. The `CalculateArea` function accepts a numeric value representing the radius of a circle, and returns a value calculated as the area of a circle. Radius in, area out.

> 从执行的角度来看，函数就是这样操作的。它们还有另一个非常重要的技巧：可以**将数据值传递到函数中**。使用了这些数据值的函数可以向调用它的代码返回一个(或在某些语言中返回一个以上)新值。因为函数可能返回值，所以它们可以在表达式和语句中使用。图 5-19 显示了这是如何工作的。`CalculateArea` 函数接受表示圆半径的数值，并返回作为圆面积计算的值。半径向内，面积向外。

![[FIGURE 5-19:](#08_9781119183938-ch05.xhtml#rc05-fig-0019) Passing values to and from functions](./media/images/9781119183938-fg0519.png)

A function can take zero or more _parameters_, which are special-purpose variables that `carry` values across the gap between the function and the code that calls it. The names and (for statically typed languages) types of a function’s parameters are given when the function is defined in your source code. In [Figure 5-19](#08_9781119183938-ch05.xhtml#c05-fig-0019), `CalculateArea` has a single parameter, `R`.

> 一个函数可以接受零个或多个 _parameters_，这是一个特殊用途的变量，可以在函数和调用它的代码之间 `携带` 值。当在源代码中定义函数时，会给出函数参数的名称和类型(对于静态类型语言)。在[图 5-19](#08_9781119183938-ch05.xhtml#c05-fig-0019) 中，`CalculateArea` 有一个参数 `R` 。

When a function is called, we must specify an argument corresponding to each of the function’s parameters. An _argument_ may be a literal or named constant, or a variable, or the result of an expression. In [Figure 5-19](#08_9781119183938-ch05.xhtml#c05-fig-0019), the main program declares a variable named `Radius`. `Radius` is assigned the value 17, and is then used as the argument to `CalculateArea`, providing the initial value of the parameter `R`. `CalculateArea` can use `R` as a variable during calculations. It defines its own variable `A`, and assigns the calculated area value to it. `A` is then specified as the function’s return value. The function takes the value from `A` and carries it back to the statement that called it. The main program’s variable `Area` accepts the value from the function and can display it or use it anywhere else a value may be used.

> 当调用一个函数时，我们必须指定与该函数的每个参数相对应的参数。_argument_ 可以是文字或命名常量、变量或表达式的结果。在[图 5-19](#08_9781119183938-ch05.xhtml#c05-fig-0019) 中，主程序声明了一个名为 `Radius` 的变量 `半径` 赋值为 17，然后用作 `CalculateArea` 的参数，提供参数 `R` 的初始值 `CalculateArea` 可以在计算期间使用 `R` 作为变量。它定义自己的变量 `A` ，并将计算出的面积值赋给它。然后将 `A` 指定为函数的返回值。函数从 `A` 中获取值，并将其带回调用它的语句。主程序的变量 `Area` 接受函数中的值，并可以显示该值或在其他任何地方使用该值。

### Locality and Scope

A function may define its own constants, variables, types, and even (in many languages) its own functions, like Russian nested dolls. If you’re perceptive, the question will soon arise: what if the identifiers that a function defines conflict with those defined elsewhere in the program? If a function defines a variable called `Area`, and there is already a variable called `Area` defined outside the function, which variable is accessed when you use the `Area` identifier?

> **一个函数可以定义自己的常量、变量、类型，甚至(在许多语言中)自己的函数**，比如俄罗斯嵌套的玩偶。如果你有敏锐的洞察力，那么问题很快就会出现：如果函数定义的标识符与程序中其他地方定义的标识符冲突怎么办？如果一个函数定义了一个名为 `Area` 的变量，并且已经在函数外部定义了名为 `Area` 的变量。当您使用 `Area` 标识符时，将访问哪个变量？

This problem involves the _scope_ of an identifier, which may be simply defined as the places in a program where a given identifier may be `seen` by the code. In most languages, identifiers that are defined within a function are local to that function. Anything defined outside a function is not local to anything so its scope is said to be _global_.

> 这个问题涉及标识符的作用域，它可以简单地定义为程序中代码可以 `看到` 给定标识符的位置。在大多数语言中，在函数中定义的标识符是该函数的本地标识符。在函数外部定义的任何对象都不是任何对象的本地对象，因此其作用域被称为 _global_。

Figure 5-20 illustrates global scope. The example program defines two functions: `CalculateArea` and `CalculatePerimeter`. It also defines the constant `pi` and two variables: `Area` and `Radius`. All of these definitions are global. Each of the two functions has its own local definitions. Both define a named constant: `TheAnswer`. `CalculateArea` defines a local variable called `Area`. Each function defines `TheAnswer` with a different value. Several questions arise:

> 图 5-20 说明了全局范围。示例程序定义了两个函数： `CalculateArea` 和 `CalculatePerimeter` 。它还定义了常量 `pi` 和两个变量： `Area` 和 `Radius` 。所有这些定义都是全局性的。这两个函数都有自己的局部定义。两者都定义了一个命名常量： `TheAnswer` `CalculateArea` 定义了一个名为 `Area` 的局部变量。每个函数用不同的值定义 `TheAnswer` 。出现了几个问题：

- If the main program references `TheAnswer`, which value does it get: 17 or 42? - Can the `CalculateArea` function call `CalculatePerimeter`?
- Can one of the functions redefine `pi` as 3.0?
- If `CalculateArea` assigns a value to its local variable `Area`, is the global variable `Area` affected? How about vice versa?

> - 如果主程序引用 `TheAnswer` ，它会得到哪个值：17 或 42？
> - `CalculateArea` 函数能否调用 `CalculatePerimeter` ？
> - 其中一个函数可以将 `pi` 重新定义为 3.0 吗？
> - 如果 `CalculateArea` 为其局部变量 `Area` 赋值，全局变量 `Area` 是否受影响？反之亦然？

![[FIGURE 5-20:](#08_9781119183938-ch05.xhtml#rc05-fig-0020) Global and local scope](./media/images/9781119183938-fg0520.png)

These questions can be answered by applying four general rules:

> 这些问题可以通过应用**四个一般规则**来回答：

- Local can see global.
- Global can’t see local.
- Local can’t see other local.
- Local can define a local item under the same identifier as a global item, and thus hide global.

> - 本地可以看到全局。
> - 全局无法查看本地。
> - 本地人看不到其他本地人。
> - Local 可以在与全局项相同的标识符下定义本地项，从而隐藏全局项。

> [!note]
> 这 4 个原则还可以进一步的抽象：
> 本地是不透明的，全局是透明的

Let’s use these rules to answer the four questions:

> 让我们使用这些规则来回答四个问题：

- The main program can’t reference either local definition of `TheAnswer`. Global can’t see local.
- `CalculateArea` can call `CalculatePerimeter`. Both functions were defined at global scope, and local can see global.
- Either function could define an identifier called `pi`, giving it the value 3.0, 17.76 or anything else. In doing so it would hide the global constant `pi`: subsequent uses inside the function would see the new identifier, whereas uses elsewhere in the program would continue to see the original one.
- Nothing the main program does to its variable `Area` affects the local variable `Area` defined by `CalculateArea`. Global can’t see local. Nor can `CalculateArea` change the main program’s global variable `Area`.

> - 主程序不能引用 `TheAnswer` 的本地定义。全局无法查看本地。
> - `CalculateArea` 可以调用 `CalculatePerimeter`。这两个函数都是在全局范围内定义的，并且本地可以看到全局。
> - 任何一个函数都可以定义一个名为 `pi` 的标识符，将其值设为 3.0、17.76 或任何其他值。这样做会隐藏全局常量 `pi` ：函数内的后续使用将看到新标识符，而程序中其他地方的使用将继续看到原始标识符。
> - 主程序对其变量 `Area` 所做的任何操作都不会影响由 `CalculateArea` 定义的局部变量 `Area` 。全局无法查看本地。`CalculateArea` 也不能更改主程序的全局变量 `Area` 。

But wait… can’t local see global? Of course. But in this case, `CalculateArea` has defined a local variable with the same identifier as a global variable. From `CalculateArea`’s perspective, the global variable `Area` is now hidden because `CalculateArea` used the identifier `Area` to define its own local variable `Area`. The global `Area` is hidden by the local `Area`.

> 但等等……局部变量看不到全局变量吗？当然但在本例中，`CalculateArea` 定义了一个**局部变量，其标识符与全局变量相同**。从 `CalculateArea` 的角度来看，全局变量 `Area` 现在是隐藏的，因为 `CalculateArea` 使用标识符 `Area` 来定义自己的局部变量 `Area` 。全局 `Area` 被本地 `Area` 隐藏。

The rules are not there solely to impose order. In most languages (including C, C++, Java, Ada and Pascal) a function’s arguments and local variables literally do not exist unless the function has been called and is running. A function’s arguments and local variables are set up on the system stack (which is explained in [Chapter 4](#07_9781119183938-ch04.xhtml)) by the code that calls the function. When the function returns, those arguments and local variables are removed from the stack and no longer exist. Languages like Python still use the idea of scope, even though functions are handled in an entirely different way `under the skin` . Scope is a subtle business, and as with almost everything else in programming, the details vary widely from language to language. Worse, there are occasional language implementations that permit certain tricks allowing code to violate the rules of scope. This is always a bad idea.

> 这些规则不仅仅是为了维持秩序。**在大多数语言(包括 C、C++、Java、Ada 和 Pascal)中，函数的参数和局部变量实际上不存在，除非函数已被调用并正在运行。函数的参数和局部变量由调用函数的代码设置在系统堆栈上**(在[第 4 章](#07_9781119183938-ch04.xhtml)中进行了解释)。**当函数返回时，这些参数和局部变量将从堆栈中删除，不再存在。**像 Python 这样的语言仍然使用作用域的概念，即使函数是以完全不同的方式 `隐藏` 处理的。范围是一项微妙的业务，与编程中的几乎所有其他内容一样，不同语言的细节差异很大。更糟糕的是，偶尔会有语言实现允许某些技巧允许代码违反范围规则。这总是个坏主意。

Scope will come up again in the next section of this chapter.

> 范围将在本章的下一节再次讨论。

## Object-Oriented Programming

Up to this point, we’ve drawn a hard distinction between code and the data that code operates upon. For the first three decades of digital computing, tools and development methodologies largely reflected this separation. A programmer would define a collection of functions to perform the operations required of the program, and a collection of concrete data structures (arrays, structs or records and so on) to contain the program’s state. For large applications, the choice of functions and structures is typically informed by a _domain modelling process_ during the design phase; this aims to capture the relevant real-world entities (perhaps vehicles and people for a government vehicle licensing application), constraints (every vehicle has a single owner) and operations (transferring ownership of a vehicle, applying for a driving licence) in the domain where the program will be used.

> 到目前为止，我们已经在代码和代码操作的数据之间画出了一个严格的区别。在数字计算的前三十年，工具和开发方法在很大程度上反映了这种分离。程序员将定义一组函数来执行程序所需的操作，以及一组包含程序状态的具体数据结构(数组、结构或记录等)。对于大型应用，功能和结构的选择通常由设计阶段的域建模过程决定；这旨在捕获计划使用领域中的相关真实实体(可能是政府车辆许可申请的车辆和人员)、约束条件(每辆车都有一个车主)和操作(转让车辆所有权、申请驾驶执照)。

In the 1970s, computer science researchers at a number of institutions began to experiment with a new conceptual model for programming, which became known as _object-oriented programming_ (OOP). OOP attempts to reduce the semantic gap between the design and implementation phases of the development process by providing facilities at the language level to describe entities and the operations that can be performed on them. A new species of data structure was born—the _object_—which expands on the notion of a struct or record (see the section in this chapter entitled `[Types and Type Definitions](#08_9781119183938-ch05.xhtml#c05-sec-0038)` ) by also incorporating the functions that act on its internal data.

> 20 世纪 70 年代，许多机构的计算机科学研究人员开始尝试一种新的编程概念模型，即面向对象编程(OOP)。**OOP 试图通过在语言级别提供描述实体和可以对其执行的操作的工具来减少开发过程的设计和实现阶段之间的语义差距。**一种新的数据结构诞生了 *object*，它扩展了结构或记录的概念(参见本章中标题为 `[类型和类型定义](#08_9781119183938-ch05.xhtml#c05-sec-0038)` 的部分)，同时还包含了作用于其内部数据的函数。

The jargon changed, as jargon often does when new concepts appear. Programmers define _classes_ of object, which often correspond closely to the entities identified during domain modelling; in the case of our vehicle licensing example the programmer might define a class `Car` and another class `Person`. As the program runs, individual objects will be created in memory, each of which is an _instance_ of some class; we might have millions of instances of class `Car`, of which one represents my car, and millions of instances of class `Person`, one of which represents me. A class definition describes the data elements (variously called fields, attributes or properties), which each instance of that class will possess, and a function (generally called a method) for each operation that can be performed on an instance. An instance of `Car` might have a string field `license_plate`, and a field `owner` that refers to the instance of `Person` that corresponds to the car’s current owner, and a method `change_owner` to change the current owner. Figure 5-21 provides a summary of this terminology.

> 术语发生了变化，就像新概念出现时术语经常发生的变化一样。程序员定义对象的类，这些类通常与领域建模过程中识别的实体紧密对应；在我们的车辆许可示例中，程序员可能会定义一个类 `Car` 和另一类 `Person` 。当程序运行时，将在内存中创建单独的对象，每个对象都是某个类的实例；我们可能有数百万个 `Car` 类的实例，其中一个代表我的车，还有数百万个 `Person` 类实例，其中之一代表我。类定义描述了该类的每个实例都将拥有的数据元素(各种称为字段、属性或属性)，以及可以在实例上执行的每个操作的函数(通常称为方法)。`Car` 的实例可能具有字符串字段 `license_plate` 、字段 `owner` 和方法 `change_owner` ，该字段引用与汽车当前所有者相对应的 `Person` 实例。图 5-21 提供了该术语的概述。

![[FIGURE 5-21:](#08_9781119183938-ch05.xhtml#rc05-fig-0021) Classes and objects](./media/images/9781119183938-fg0521.png)

Don’t get the terms class and object mixed up. A class is a type definition; it exists in your source code. An object is an instance of a class, and is a real data item in memory at runtime, allocated and initialised according to the specifications of its class and the particulars of the language you’re using.

> **不要混淆类和对象这两个术语。**类是一个类型定义；它存在于源代码中。对象是一个类的实例，是运行时内存中的真实数据项，根据其类的规范和所使用语言的细节进行分配和初始化。

In most languages, new objects are initialised by a special constructor method defined in the class definition. When an object is no longer needed, it may be explicitly destroyed (in languages like C++), or removed by automatic garbage collection (in languages that offer it, like Java). Any cleanup required is handled by a special destructor or finaliser method. In most cases, objects are referred to via references, which are effectively pointers to the location in memory where the object’s data is stored; when a new object is created, and the constructor has been executed, a reference is returned that can be used to access the object’s fields and call its methods.

> 在大多数语言中，新对象由类定义中定义的特殊构造函数初始化。当一个对象不再需要时，它可能会被显式销毁(在 C++ 等语言中)，或者被自动垃圾收集(在提供它的语言中，如 Java)移除。所需的任何清理都由特殊的析构函数或 finalizer 方法处理。在大多数情况下，对象是通过引用来引用的，引用实际上是指向内存中存储对象数据的位置的指针；创建新对象并执行构造函数后，将返回一个引用，该引用可用于访问对象的字段并调用其方法。

The syntax for defining classes, for creating objects and for accessing their fields and records varies widely among languages. Let’s take a look how a simple version of `Car` might be defined and used, first in C++:

> 定义类、创建对象以及访问它们的字段和记录的语法在不同语言之间存在很大差异。让我们先看看如何在 C++ 中定义和使用简单版本的 `Car` ：

```cpp
    class Car
    {
      Person *owner;
      char *plate;

      Car(Person *owner, const char *plate)
      {
        this->owner = owner;
        this->plate = strdup(plate);
      }

      ~Car()
      {
        free(this->plate);
      }

      void set_owner(Person *owner)
      {
        this->owner = owner;
      }
    };

    Car *my_car = new Car(me, 'RN04 KDK' );

    printf('%s\n', my_car->plate);
    my_car->set_owner(you);
```

and now in Python:

```python
    class Car:
      def __init__(self, owner, plate):
        self.owner = owner
        self.plate = plate
      def set_owner(self, owner):
        self.owner = owner

    my_car = Car(me, 'RN04 KDK')

    print my_car.plate
    my_car.set_owner(you)
```

Most object-oriented languages are share three basic language features:

> 大多数面向对象的语言都有三个基本的语言特性：

- **Encapsulation:** Classes define both the data elements (fields) that will be associated with each instance and the code (methods) that operate on them.
- **Inheritance:** A class may be a _subclass_ of another class, meaning that it inherits the fields and methods of its _superclass_, to which it adds its own.
- **Polymorphism:** An instance of a subclass may be used in a context where an instance of a superclass is expected.

> - **封装：**类定义将与每个实例关联的数据元素(字段)和对其进行操作的代码(方法)。
> - **继承：**一个类可以是另一个类的 _subclass_，这意味着它继承了其 _superclass_ 的字段和方法，并将其添加到其中。
> - **多态性：**子类的实例可以用于期望超类实例的上下文中。

> [!note]
> 上面提到过，对于静态类型的语言，也可以实现 `动态` ，主要就是由面向对象中的 `多态` 实现的！
> 所以这也是多态的一个意义吧

The next sections look at each of these features in a little more detail.

### Encapsulation(封装)

The binding together of data with the code that manipulates it is called _encapsulation_. But what is it good for? After all, even in a language that lacks object-oriented (OO) features, nothing stops us from declaring a struct or record type, and writing a function that takes a reference to an instance of that type and performs operations on its elements.

> 数据与操纵数据的代码的绑定称为 _encapsulation_。但它有什么好处？毕竟，即使在缺乏面向对象(OO)特性的语言中，也没有什么能阻止我们声明结构或记录类型，以及编写一个引用该类型实例并对其元素执行操作的函数。

The key distinction is that encapsulation usually implies a mechanism for _data hiding_, which is when the programmer has full control over which fields or methods are visible from outside the object. You can allow code from other parts of the program to `reach in` and directly read or write a field, or call a method, or you can declare the field _private_, which means it can only be accessed by the object’s methods. The methods then act as a sort of controlled interface to an object’s data. In C++ we might write:

> 关键区别在于**封装通常意味着数据隐藏的机制**，即程序员完全控制对象外部可见的字段或方法。您可以允许程序其他部分的代码 `进入` 并直接读取或写入字段，或调用方法，也可以声明字段 _private_，这意味着它只能由对象的方法访问。然后，这些方法充当对象数据的一种受控接口。在 C++ 中，我们可以写：

```cpp
    class MyClass
    {
    private:
      int my_attribute;

    public:
      int get_attribute();
      void set_attribute(int new_value);
    };

    MyClass *c = new MyClass();

    // these lines will give compile-time errors
    int a = c->my_attribute;
    c->my_attribute = 42;

    // use the accessor methods instead
    int a = c->get_attribute();
    c->set_attribute(42);
```

The `my_attribute` field is declared private (using the access qualifier `private`), and so is only accessible to the `get_attribute()` and `set_attribute()` methods. The compiler can detect and reject attempts to access `my_attribute` directly.

> `my_attribute` 字段被声明为 private(使用访问限定符 `private` )，因此只能由 `get_attribute()` 和 `set_attribue()` 方法访问。编译器可以检测并拒绝直接访问 `my_attribute` 的尝试。

A brief example may help to explain the importance of data hiding. Suppose you want to create a class that models a child’s piggy bank. A piggy bank contains coins of various denominations. The coins have a total value, but it might be interesting to record which denominations are present in the bank, and how many of each are there. The different coins are referred to by an enumerated type `CoinConstant`, with elements like `FivePence`, `TwentyPence` and `OnePound`. The interface to the object’s data will consist of methods to add a coin, remove a coin, report the number of coins of a given denomination and report the total value of all coins. In C++, the skeleton of our class might look like this:

> 一个简单的例子可能有助于解释数据隐藏的重要性。假设您想创建一个类，为孩子的存钱罐建模。存钱罐里有各种面值的硬币。这些硬币有一个总价值，但记录银行里有哪些面额，以及每种面额有多少可能会很有趣。不同的硬币由枚举类型 `CoinConstant` 表示，其中包含 `FivePence` 、 `TwentyPense` 和 `OnePound` 等元素。对象数据的接口将包括添加硬币、移除硬币、报告给定面额的硬币数量以及报告所有硬币的总价值的方法。在 C++ 中，我们类的框架可能如下所示：

```cpp
    class PiggyBank
    {
      // some internal state here
    public:
      void add_coin(CoinConstant c) { … }
      void remove_coin(CoinConstant c) { … }
      int how_many_of(CoinConstant c) { … }
      int total_value(){ … }
    };
```

> [!note]
> 前面提到封装的意义是 `限制`
> 感觉像是人类的发展，从公有制 --> 私有制
> 这也是意识的觉醒的标志？！
> 那要是从这个角度来看的话，编程语言的发展是否可以依照人类演进的脉络透看？
> 再者，语言可以表示一个文明演进

The four methods represent the only access that the outside world has to the coin bank object’s data. The outside world cannot see the data’s internal representation at all.

> 这四种方法表示外部世界对币库对象数据的唯一访问。外部世界根本看不到数据的内部表示。

There are a number of obvious ways to implement the `piggy bank` class. You could define a private counter field for each coin denomination. Or you could look around and see if there are any predefined library data types that would work as well or better. Most programming languages offer predefined data types called _collections_ that include arrays, lists and so on. A _bag_ is a collection data type that can tell you whether a particular value is present (in a way similar to the set data type) and also how many times that value is present in the bag. One bag collection inside your object would do almost the entire job of modelling the coin bank.

> 有许多明显的方法可以实现 `存钱罐` 类。您可以为每个硬币面额定义一个专用计数器字段。或者您可以四处查看，看看是否有任何预定义的库数据类型也可以更好地工作。大多数编程语言都提供名为 _collections_ 的预定义数据类型，包括数组、列表等。_bag_ 是一种集合数据类型，它可以告诉您某个特定值是否存在(以与设置的数据类型类似的方式)，以及该值在包中存在的次数。在你的物体内收集一个袋子，几乎可以完成整个硬币库的建模工作。

Whether you define the data yourself or use a `canned` data type instead doesn’t matter. The point is that the internal representation of the data remains hidden. If the data inside the coin bank object could be accessed directly from outside the object, outside code could make assumptions about the structure of the data, or change data in ways that have unintended consequences. By limiting data access to a small number of methods, access is controlled completely by the object itself, and you can change the internal representation of the data at any time without fear of breaking outside code that depends on the object’s internals.

> 无论您是自己定义数据还是使用 `罐装` 数据类型，都无关紧要。关键是数据的内部表示仍然隐藏。如果可以从对象外部直接访问硬币库对象内部的数据，则外部代码可能会对数据结构进行假设，或以具有意外后果的方式更改数据。通过将数据访问限制为少数方法，访问完全由对象本身控制，您可以随时更改数据的内部表示，而不用担心破坏依赖于对象内部的外部代码。

Taken together, the definitions of a class’s methods (and any public data items, if they exist) are called the class’s _interface_.

> 总之，类的方法(以及任何公共数据项，如果存在)的定义称为类的 _interface_。

### Inheritance

If encapsulation were the sole advantage of OOP, it would still be well worthwhile. OOP has other significant tricks up its sleeve, however, and the next one up for discussion is called inheritance.

> 如果封装是 OOP 的唯一优势，那么它仍然是值得的。然而，OOP 还有其他重要的技巧，接下来要讨论的是继承。

Most languages allow new types to be defined in terms of existing types. This is routine and done in various ways, for example an array of real numbers, a set of characters or a struct containing members of several other types. A struct, in fact, may include another struct as one of its members.

> 大多数语言都允许根据现有类型定义新类型。这是一个例程，可以通过多种方式完成，例如，一个实数数组、一组字符或一个包含多个其他类型成员的结构。事实上，一个结构可以包含另一个结构作为其成员之一。

This comes close to what _inheritance_ is: a class is defined as a child or subclass of an existing class. The child class inherits everything defined in its parent or superclass: all fields and methods defined in the parent class are available in the child class. The child class may add its own fields and methods that did not exist in its parent class; this extends the parent class but does not change the behaviour inherited from the parent class. Inheritance allows that too: a child class may redefine fields and methods belonging to a parent class. We say that the child class _overrides_ inherited elements.

> 这接近于 _inheritance_：类被定义为现有类的子类或子类。子类继承父类或超类中定义的所有内容：父类中定义定义的所有字段和方法都在子类中可用。子类可以添加其父类中不存在的自己的字段和方法；这扩展了父类，但不会改变从父类继承的行为。继承也允许这样做：子类可以重新定义属于父类的字段和方法。我们说，子类 _overrides_ 继承了元素。

Figure 5-22 illustrates how inheritance works. The base class `Shape` is used to model two-dimensional shapes as might be drawn in a flowcharting program. There’s not much in `Shape`: a constructor, a destructor and the fields `x,y` and `line_width`, which define where a shape is located on the screen and how bold a line the shape will use. A child class `Circle` is later defined as inheriting from `Shape`. The `Circle` class gets everything in `Shape` and adds a new property, `Radius`. It also defines a new method, `Redraw`, and defines its own constructor and destructor.

> 图 5-22 说明了继承的工作原理。基类 `Shape` 用于建模可能在流程图程序中绘制的二维形状。`Shape` 中没有太多：构造函数、析构函数以及字段 `x，y` 和 `line_width` ，它们定义了形状在屏幕上的位置以及形状将使用多粗的线条。子类 `Circle` 后来被定义为继承自 `Shape` 。`Circle` 类获取 `Shape` 中的所有内容，并添加一个新属性 `Radius` 。它还定义了一个新方法 `Redraw` ，并定义了自己的构造函数和析构函数。

![[FIGURE 5-22:](#08_9781119183938-ch05.xhtml#rc05-fig-0022) How inheritance works](./media/images/9781119183938-fg0522.png)

Now, why do it this way? The key to understanding inheritance is to think of classes in a hierarchy that moves from an abstract base class at the top to specific child classes at the bottom. An ellipse is a specific kind of shape. A polygon is another kind of shape. If you’re writing a flowcharting program, you would probably define an `Ellipse` child class and a `Polygon` child class below `Shape`. Drawing a rectangle is different from drawing a pentagon, so under `Polygon` you would then create child classes like `Rectangle`, `Pentagon`, `Hexagon` and so on. Such a hierarchy is shown in Figure 5-23.

> 现在，为什么要这样做？理解继承的关键是在一个层次结构中思考类，从顶部的抽象基类到底部的特定子类。椭圆是一种特殊的形状。多边形是另一种形状。如果您正在编写流程图程序，您可能会在 `Shape` 下面定义一个 `Ellipse` 子类和一个 `Polygon` 子类。绘制矩形与绘制五边形不同，因此在 `多边形` 下，您可以创建 `矩形` 、 `五边形` 、 `六边形` 等子类。这样的层次结构如图 5-23 所示。

![[FIGURE 5-23:](#08_9781119183938-ch05.xhtml#rc05-fig-0023) A class hierarchy](./media/images/9781119183938-fg0523.png)

A circle is a special case of an ellipse, and a square is a special case of a rectangle. This is why `Circle` is a child class of `Ellipse`, and `Square` is a child class of `Rectangle`. Classes are generally created as belonging to this kind of hierarchy, with an abstract base class providing the methods and fields that all child classes have. Child classes add specificity, either by defining new methods and fields, or by overriding those that they inherit.

> 圆是椭圆的特例，正方形是矩形的特例。这就是为什么 `Circle` 是 `Ellipse` 的子类，而 `Square` 是 `Rectangle` 的子级。类通常被创建为属于这种层次结构，抽象基类提供所有子类所具有的方法和字段。子类通过定义新的方法和字段，或者通过重写它们继承的方法和域来增加特定性。

You may already be experienced in this kind of thinking. Consider text styles in a word processor or desktop publishing program. A generic paragraph style might specify the font and the type size and nothing else. You can then define more specific paragraph styles that add first line indents, space before and after, margin insets, bullets and numbering and so on. This is key: _the generic paragraph style contains only those style items that all paragraphs have_. This provides a default font and type size for all paragraphs—and also allows you to change the font in all paragraph styles by changing it only once in the basic paragraph style. Because the more specific paragraph styles are, in a sense, child classes of the basic paragraph style, they inherit the font and type size and can override it to whatever they need for the specific types of paragraph that they are.

> 你可能已经有过这种思考的经验。考虑文字处理器或桌面出版程序中的文本样式。通用段落样式可以指定字体和类型大小，而不指定其他内容。然后，您可以定义更具体的段落样式，添加第一行缩进、前后空格、边距插入、项目符号和编号等。这是关键：通用段落样式仅包含所有段落都具有的样式项。这为所有段落提供了默认字体和字体大小，还允许您通过在基本段落样式中仅更改一次来更改所有段落样式中的字体。因为在某种意义上，更具体的段落样式是基本段落样式的子类，所以它们继承字体和类型大小，并可以将其覆盖到它们所属的特定段落类型所需的任何内容。

If you have some grounding in OOP, it may occur to you that the example shown in [Figure 5-22](#08_9781119183938-ch05.xhtml#c05-fig-0022) isn’t optimal. You’re right, it isn’t—but to explain why, we first have to explain the third leg in OOP’s three-legged stool: polymorphism.

> 如果您在 OOP 中有一些基础，您可能会想到[图 5-22](#08_9781119183938-ch05.xhtml#c05-fig-0022) 中所示的示例不是最佳的。你是对的，这不是解释为什么，我们首先要解释 OOP 的三条腿凳子中的第三条腿：多态性。

### Polymorphism(多态性)

Key to the idea of object-oriented programming is that objects know what to do. If we want to draw a shape object, we call its `Redraw()` method. The object knows what sort of shape it is, and its `Redraw()` method allows it to redraw itself on the screen according to its class. The redrawing itself is done in class-specific ways, but the method name is the same for all shapes.

> **面向对象编程思想的关键是对象知道该做什么。**如果我们想绘制形状对象，我们调用它的 `Redraw()` 方法。对象知道它是什么样的形状，它的 `Redraw()` 方法允许它根据其类在屏幕上重新绘制自己。重绘本身是以类特定的方式完成的，但所有形状的方法名都相同。

It sounds odd at first, but in OOP, you don’t always have to know the precise class of an object in order to call one of its methods. This feature goes by the heavy-duty word _polymorphism_, from the Greek for `many shapes` . Because objects know what to do, you simply have to tell them to go do it. You don’t have to tell them how.

> 一开始听起来很奇怪，**但在 OOP 中，您不一定要知道对象的精确类才能调用其方法之一。**这一特征源自希腊语中 `许多形状` 的重磅单词 _polymmorphism_。因为**对象知道该做什么，你只需要告诉他们去做，而不必告诉他们怎么做**。

A good metaphor for polymorphism is the humble farmer. There are many kinds of farmer who grow many different kinds of crops. However, all farmers have certain tasks in common: they prepare the ground, plant, tend and harvest. Each of these tasks is done in a different way for different crops; harvesting tomatoes is nothing like harvesting wheat. Tomato farmers know how to harvest tomatoes, and wheat farmers know how to harvest wheat. If a government weather office predicts that an early killer frost is coming later in the week, it would be enough to call or text all the farmers in the frost area with a simple message: `Harvest your crops now` . The weather office people don’t need to tell the farmers how to do their harvesting. The farmers know how. Telling them to start harvesting is enough.

> 多态性的一个好比喻是谦逊的农民。有许多种农民，他们种植许多不同种类的作物。然而，所有农民都有一些共同的任务：准备土地、种植、照料和收获。对于不同的作物，每一项任务都以不同的方式完成；收获西红柿和收获小麦没什么两样。番茄农民知道如何收获番茄，小麦农民知道如何收割小麦。如果政府气象局预测本周晚些时候将出现一场致命的霜冻，那么只要给霜冻地区的所有农民打电话或发短信，告诉他们一个简单的信息： `现在就收割庄稼` 就足够了。气象局的人不需要告诉农民如何收割。农民知道怎么做。告诉他们开始收割就够了。

In the programming world, polymorphism acts on classes in a hierarchy. If the base class in the hierarchy defines a method, then all classes that descend from it have that method. Each class may override the method with class specifics, but all classes in the hierarchy respond to a call to that particular method.

> 在编程世界中，**多态性作用于层次结构中的类**。如果层次结构中的基类定义了一个方法，那么从它派生的所有类都具有该方法。**每个类都可以用类细节重写方法，但层次结构中的所有类都响应对该特定方法的调用。**

How does this work in practice? Let’s go back to our shapes example, and the scenario illustrated in Figure 5-24. A number of shape objects have been created, and all have been added to a collection. (We described the idea of collections earlier in this chapter in the section entitled `[Types and Type Definitions](#08_9781119183938-ch05.xhtml#c05-sec-0038)` .) Here, the collection is defined as a list of class `Shape`. Inside, the list is really a list of pointers to objects of class `Shape`. We can step through the list and perform an operation on each object in the list. In this case, for each object in the list, we call `Redraw()`. It works because all classes descending from class `Shape` contain everything that `Shape` contains. If class `Shape` contains the `Redraw()` method, so do all of its descendants.

> 这在实践中是如何工作的？让我们回到我们的形状示例，以及图 5-24 所示的场景。已经创建了许多形状对象，并且所有形状对象都已添加到集合中。(我们在本章前面的 `[类型和类型定义](#08_9781119183938-ch05.xhtml#c05-sec-0038)` 一节中描述了集合的概念。)这里，集合定义为类 `Shape` 的列表。在内部，该列表实际上是指向 `Shape` 类对象的指针列表。我们可以遍历列表并对列表中的每个对象执行操作。在本例中，对于列表中的每个对象，我们调用 `Redraw()`。它之所以有效，是因为从类 `Shape` 开始的所有类都包含 `Shape` 包含的所有内容。如果类 `Shape` 包含 `Redraw()` 方法，那么它的所有后代也是如此。

![[FIGURE 5-24:](#08_9781119183938-ch05.xhtml#rc05-fig-0024) How polymorphism works](./media/images/9781119183938-fg0524.png)

This is why the example as originally configured in [Figure 5-22](#08_9781119183938-ch05.xhtml#c05-fig-0022) isn’t ideal. The `Redraw()` method wasn’t present in class `Shape` because `Shape` is so generic that there’s nothing to draw. However, if we intend to use polymorphism to call a method, that method must be present throughout the hierarchy. The proper place for the `Redraw()` method is in the hierarchy’s base class `Shape`, from which all other shape classes descend. This is true even if the `Redraw()` method is empty. A class like `Shape` that is not intended to be instantiated is called an _abstract class_. The whole purpose of an abstract class is to ensure that particular methods are defined in all classes that descend from the abstract class.

> 这就是为什么最初在[图 5-22](#08_9781119183938-ch05.xhtml#c05-fig-0022) 中配置的示例不理想的原因。类 `Shape` 中不存在 `Redraw()` 方法，因为 `Shape` 是通用的，没有什么可绘制的。然而，如果我们打算使用多态性来调用一个方法，那么该方法必须在整个层次结构中存在。**`Redraw()` 方法的正确位置是层次结构的基类 `Shape` ，所有其他形状类都从该基类派生。即使 `Redraw()` 方法为空，也是如此。**像 `Shape` 这样不打算实例化的类称为 _abstract class_。抽象类的全部目的是确保在从抽象类派生的所有类中定义特定的方法。

Polymorphism comes free in dynamically typed languages like Python and Smalltalk, because an association between an identifier and an object may be changed at any time, and every object carries with it type information that can be used to resolve which version of the method to call. In C++, however, the type of an identifier is determined at compile time, which can cause problems. Consider the following code:

> 多态性在动态类型语言(如 Python 和 Smalltalk)中是免费的，因为标识符和对象之间的关联可以随时更改，并且每个对象都带有类型信息，可以用来解析要调用的方法版本。然而，在 C++ 中，标识符的类型是在编译时确定的，这可能会导致问题。考虑以下代码：

```cpp
    class Rectangle {
      void name() {
        printf('Rectangle!\n');
      }
    };

    class Square : public Rectangle {
      void name() {
        printf('Square!\n');
      }
    };

    Rectangle *r = new Rectangle();
    r->name();             // prints `Rectangle`

    Square *s = new Square();
    s->name();             // prints `Square!`

    Rectangle *r = new Square();
    r->name();             // prints `Rectangle!` even though r
                           // points to an instance of Square
```

This defines a class `Rectangle`, with a method `name()` that prints `Rectangle!`, and a subclass `Square`, which overrides `name()` to print `Square!`. We instantiate a `Rectangle`, and call its `name()` method, which prints `Rectangle!`, as expected. Next we instantiate a `Square`, and call its `name()` method, which prints `Square!`, again as expected. The third example is more perplexing at first glance. We instantiate a `Square`, but store the pointer in an identifier that has type `Rectangle *` (pointer to `Rectangle`); this is semantically legal, as `Square` is a child of `Rectangle`, so every `Square` is also a `Rectangle`. However, when we call `name()`, the program prints `Rectangle!` rather than `Square!`. The reason for this is that the compiler decides which version of the `name()` method to call based on the type of the pointer `r`, rather than on the type of the object it points to.

> 这定义了一个类 `Rectangle`，它有一个打印 `Rectangle!` 的方法 `name()`，还有一个子类 `Square`，它覆盖 `name()` 来打印 `Square!`。
> 我们实例化一个 `Rectangle`，并调用它的 `name()` 方法，该方法按预期打印 `Rectangle!`。
> 接下来我们实例化一个 `Square`，并调用它的 `name()` 方法，该方法再次按预期打印 `Square!`。
> 第三个例子乍一看更令人费解。我们实例化一个 `Square`，但将指针存储在类型为 `Rectangle *` (指向 `Rectangle` 的指针)的标识符中； 这在语义上是合法的，因为 `Square` 是 `Rectangle` 的子元素，所以**每个 `Square` 也是一个 `Rectangle`**。
> 但是，当我们调用 `name()` 时，**程序会打印 `Rectangle!` 而不是 `Square!`**。这样做的**原因是编译器根据指针 `r` 的类型而不是它指向的对象的类型来决定调用哪个版本的 `name()` 方法**。

> [!note]
> 多态中的行为：**The reason is that the compiler decides which version of the `name()` method to call based on the type of the pointer `r` and not the type of the object it points to**
> 虚函数的意义就是为了多态哈

The fix for statically typed languages is called _dynamic dispatch_, which looks at the object itself to determine the appropriate method body to invoke. A common mechanism for implementing dynamic dispatch is to have each object carry around a pointer to its class’s virtual method table, which points to the appropriate implementation of each method. In C++ methods must be explicitly tagged as `virtual` to be included in the virtual method table and thus be available for polymorphic calls; methods that are not flagged as virtual are subject to static dispatch.

> 静态类型语言的修复方法称为 _dynamic dispatch_，它查看对象本身以确定要调用的适当方法体。实现动态分派的一种常见机制是**让每个对象携带指向其类的虚拟方法表的指针，该指针指向每个方法的适当实现**。在 C++ 中，方法必须显式标记为 `virtual` 才能包含在虚拟方法表中，**从而可用于多态调用；未标记为虚拟的方法将受到静态分派**。

### OOP Wrapup

OOP is both a programming technology and a way of thinking about structuring code and data. The basic idea is that data should be defined along with the code that manipulates it. A data type defining code and data together is a class. An object is an instance of a class; that is, a data item created in memory according to its class definition. Three basic principles define OOP:

> OOP 既是一种编程技术，也是一种构建代码和数据的思维方式。基本思想是，数据应该与操作它的代码一起定义。一起定义代码和数据的数据类型是一个类。对象是类的实例；即根据其类定义在内存中创建的数据项。OOP 有三个基本原则：

- **Encapsulation:** Combines code and data into classes, and allows the programmer to control access to a class’s code and data through the use of access qualifiers and class functions called methods which have privileged access to fields.
- **Inheritance:** Allows us to define a class as an extension of another class. Everything the parent class defines is inherited by the child class. This allows related classes to be combined into a hierarchy of classes moving from a generic parent at the root to specific descendant classes at the leaves.
- **Polymorphism:** Allows related classes in a hierarchy to respond to method calls in cases where the caller does not know the precise type of the object on which is it calling the method. Metaphorically, the caller tells an object, `Do X: you know how` , and relies on dynamic dispatch to ensure that the correct implementation is called.

> - **封装：**将代码和数据组合成类，并允许程序员通过使用访问限定符和称为方法的类函数来控制对类代码和数据的访问，这些方法具有对字段的特权访问。
> - **继承：**允许我们将一个类定义为另一个类的扩展。父类定义的所有内容都由子类继承。这允许将相关类组合成一个类层次结构，从根处的泛型父类移动到叶处的特定子类。
> - **多态性：**允许层次结构中的相关类在调用方不知道调用方法的对象的精确类型的情况下响应方法调用。打个比喻，调用者告诉对象 `Do X:you know how` ，并依赖于动态调度来确保调用正确的实现。

The details of how OOP is implemented vary significantly by language, and especially by whether a language is statically typed (C++, Object Pascal) or dynamically typed (Python, Smalltalk) but many of the principles are the same.

> OOP 的实现细节因语言而异，尤其是语言是静态类型的(C++，Object Pascal)还是动态类型的(Python，Smalltalk)，但许多原则都是相同的。

## A Tour of the GNU Compiler Collection Toolset

If you want to try native code programming on the Raspberry Pi, the easiest way involves a set of compilers and tools that predates Linux itself. Linux is written in C (with a very small amount of assembly language) and the GNU Compiler Collection (GCC) is the toolset used to build Linux from its source code files. The GCC is preinstalled in Raspbian Linux. This section takes you on a quick tour of the GCC toolset, with a test program in C.

> 如果你想在 Raspberry Pi 上尝试本机代码编程，最简单的方法是使用一组早于 Linux 本身的编译器和工具。Linux 是用 C 语言编写的(只有很少的汇编语言)，GNU 编译器集合(GCC)是用来从源代码文件构建 Linux 的工具集。GCC 预装在 Raspbian Linux 中。本节将带您快速浏览 GCC 工具集，并使用 C 语言编写测试程序。

### gcc as Both Compiler and Builder

The `gcc` is more than a set of compilers and utilities. The `gcc` program itself (always written in lowercase) is nominally the C compiler of the collection. However, in addition to being a compiler it’s also a sort of build supervisor. When you launch `gcc` to build a C program, `gcc` in turn launches several other tools present in the collection to complete the build. The `gcc` build process includes these four steps:

> `gcc` 不仅仅是一组编译器和实用程序。`gcc` 程序本身(总是小写)名义上是集合的 C 编译器。然而，除了编译器之外，它还是一种构建管理器。当您启动 `gcc` 来构建 C 程序时，`gcc` 依次启动集合中的其他几个工具来完成构建。`gcc` 构建过程包括以下四个步骤：

- **Preprocessing:** Expands macros and include files. To accomplish this step, `gcc` launches a preprocessor utility called `cpp`.
- **Compiling:** Translates a preprocessed C file into its intermediate code, which for `gcc` is assembly language source code. The `gcc` program does the compilation itself.
- **Assembly:** Translates the assembly language source code into native object code. The `gcc` program launches the GNU assembler, `as`, to perform this step.
- **Linking:** Converts and binds together one or more object code files into a single native code executable file. The `gcc` program launches the GNU linker, `ld`, to perform this step.

> - **预处理：**展开宏并包含文件。为了完成这一步，`gcc` 启动一个名为 `cpp` 的预处理器实用程序
> - **编译：**将预处理的 C 文件转换为其中间代码，对于 `gcc` ，它是汇编语言源代码。`gcc` 程序自己进行编译。
> - **汇编：**将汇编语言源代码转换为本机目标代码。`gcc` 程序启动 GNU 汇编程序 `as` 来执行此步骤
> - **链接：**将一个或多个对象代码文件转换并绑定到一个本地代码可执行文件中。`gcc` 程序启动 GNU 链接器 `ld` 以执行此步骤。

All four of these steps may be accomplished by a single invocation of the `gcc` program. To see how it works, let’s build the classic `Hello, World!` program in C, using the `gcc`.

> 所有这四个步骤都可以通过调用 `gcc` 程序来完成。要了解它是如何工作的，让我们使用 `gcc` 用 C 语言构建经典的 `Hello，World！` 程序。

To begin, open the Raspbian file manager and create a work folder somewhere under the `pi` folder. It doesn’t matter what the folder is called; `tests` will work fine. Next, open a text editor window and enter the following short program:

> 首先，打开 Raspbian 文件管理器，在 `pi` 文件夹下创建一个工作文件夹。文件夹的名称无关紧要 `测试` 将正常工作。接下来，打开文本编辑器窗口并输入以下简短程序：

```c
    #include <stdio.h>
    int main (void) {
        printf (`Hello, world!\n`);
        return 0;
		}
```

Save the C source code to a file named `hello.c` in your work folder. Navigate to your work folder with the file manager to be sure the file was saved. Then press the F4 key to open your work folder in a terminal window. (If F4 doesn’t launch a terminal window in the editing environment you’re using, you will have to launch one manually.) Enter the following command at the terminal command line:

> 将 C 源代码保存到工作文件夹中名为 `hello.C` 的文件中。使用文件管理器导航到您的工作文件夹，以确保文件已保存。然后按 F4 键在终端窗口中打开工作文件夹。(如果 F4 没有在正在使用的编辑环境中启动终端窗口，则必须手动启动一个。)在终端命令行输入以下命令：

```shell
    gcc hello.c -o hello
```

This command turns `gcc` loose on your source code file, and uses the `–o` option to direct it to generate an executable file named `hello`. (In general, Linux executable files don’t have file extensions.) Assuming you entered the source code correctly, `gcc` will do its work and return to the command-line prompt. In your work directory will now be the files `hello.c` and `hello`.

> 此命令将 `gcc` 放在源代码文件上，并使用 `–o` 选项指示它生成名为 `hello` 的可执行文件。(通常，Linux 可执行文件没有文件扩展名。)假设您正确输入了源代码，`gcc` 将完成其工作并返回到命令行提示符。在您的工作目录中，现在将是文件 `hello.c` 和 `hello` 。

To run the executable, enter this command:

```shell
    ./hello
```

The message will appear in the terminal window:

```shell
    Hello, world!
```

Now, let’s do it again, one piece at a time. Erase the executable file `hello`, and then execute this command in the terminal window:

```shell
    hello.c –o hello.i
```

The program `cpp` is the preprocessor utility. The `–o` command tells it to create an output file named `hello.i`. You’ll see the file appear in the file manager window. You can open `hello.i` in a text editor, but unless you’ve had some experience in C, it won’t make much sense to you. Basically, your test program is at the end, and the bulk of the rest consists of external function headers (in place of that `#include` preprocessor directive at the top of the original source) that allow your program to call functions in the standard C library.

> 程序 `cpp` 是**预处理器**实用程序。`–o` 命令告诉它创建一个名为 `hello.i` 的输出文件。您将在文件管理器窗口中看到该文件。你可以在文本编辑器中打开 `hello.i` ，但除非你有一些 C 语言的经验，否则这对你来说意义不大。基本上，测试程序已经结束，剩下的大部分由外部函数头(代替原始源代码顶部的 `#include` 预处理器指令)组成，允许程序调用标准 C 库中的函数。

The next step is to compile the preprocessed source code to intermediate code. Enter this command:

> 下一步是将预处理的源代码编译为中间代码。输入以下命令：

```
    gcc -S hello.i
```

Compilation is something that `gcc` itself does. The output in this case is `hello.s`, which is the program compiled into assembly language source code. The `–S` (uppercase) command tells `gcc` to create assembly source code and then stop. You can open `hello.s` in a text editor to see the assembly source code, and it’s an interesting exercise to see if you can follow the logic. Even if you’re writing in pure C on the Raspberry Pi, studying ARM assembly language may come in handy if you ever have to debug a peculiar problem. If you’re feeling really ambitious, or intend to pursue assembly language systematically, try invoking `gcc` with the options `–O1`, `-O2`, and `–O3` and then examining the code in the generated .s files. These three options (which use the letter `O` and not the digit `0,` by the way) instruct the compiler to apply increasingly sophisticated levels of optimization to the generated code.

> 编译是 `gcc` 本身所做的事情。这种情况下的输出是 `hello.s` ，它是编译成汇编语言源代码的程序。`–S` (大写)命令告诉 `gcc` **创建程序集源代码**，然后停止。
> 您可以在文本编辑器中打开 `hello.s` 以查看程序集源代码，这是一个有趣的练习，看看您是否能够遵循逻辑。即使你在树莓派上用纯 C 语言写作，如果你需要调试一个特殊的问题，学习 ARM 汇编语言可能会很有用。
> 如果你真的很有野心，或者打算系统地使用汇编语言，可以尝试使用选项 `-O1` 、 `-O2` 和 `-O3` 调用 `gcc` ，然后检查生成的 `.s` 文件中的代码。这三个选项(顺便说一句，使用字母 `O` 而不是数字 `0` )指示编译器对生成的代码应用**日益复杂的优化级别**。

That said, there’s a caution here: don’t try to learn how to write assembly language by using the assembly language source output of `gcc` as a model. A `.s` file produced by `gcc` contains all kinds of things that are necessary to generate machine code from a program originally written in C. Writing assembly language is a separate discipline, and you should learn it by reading books on assembly language.

> 尽管如此，这里有一个警告：不要试图通过使用 `gcc` 的汇编语言源输出作为模型来学习如何编写汇编语言。由 `gcc` 生成的 `.s` 文件包含从最初用 C 编写的程序生成机器代码所需的各种内容。编写汇编语言是一门独立的学科，您应该通过阅读汇编语言书籍来学习。

If you’re not convinced, take a look at `hello.s` in a text editor. Then compare it to the `Hello, World!` program as written from scratch in assembly language:

> 如果你不相信，请在文本编辑器中查看 `hello.s` 。然后将其与用汇编语言从头编写的 `Hello，World！` 程序进行比较：

```
    .data

    message:
    .asciz '\nHello, World!\n'

    .text
    .global main

    main:
    push {lr}@    Save return address on stack
    ldr r0, message_address    @ Load message address into R0
    bl puts  @ Call puts() function in clib
    pop {pc} @ Return by popping return address into PC

    message_address: .word message

    .global puts
```

In C work, it’s best simply to let assembly language be an intermediate language.

> 在 C 工作中，最好让汇编语言成为一种中间语言。

The third step is to assemble `hello.s` to an object-code file. Enter this command:

> 第三步是将 `hello.s` 组装到目标代码文件中。输入以下命令：

```shell
    as -o hello.o hello.s
```

This time, we’re using `as`, the GNU assembler. It will produce the object code file `hello.o`. Object code files contain binary machine instructions, and you can’t open them in a text editor to examine them in any useful way.

> 这次，我们使用的是 GNU 汇编程序 `as` 。它将生成目标代码文件 `hello.o` 。目标代码文件包含二进制机器指令，您不能在文本编辑器中打开它们以任何有用的方式检查它们。

You can’t execute them either. That takes one last step, which is linking `hello.o` with a fair number of other things in the C runtime library. Unfortunately, linking a C program manually by invoking the linker `ld` at the command line is a very complicated business, and it is where `gcc`’s skills as a build manager really come in handy. Instead of having you type in hundreds of characters, we’ll run `gcc` again in _verbose mode_, during which it will display every command it issues to `cpp`, `as`, and `ld`. Enter this command:

> 你也不能执行它们。这需要最后一步，即将 `hello.o` 与 C 运行库中的大量其他内容链接起来。不幸的是，通过在命令行调用链接器 `ld` 手动链接 C 程序是一项非常复杂的业务，而这正是 `gcc` 作为构建管理器的技能真正发挥作用的地方。我们将在 _verbose mode_ 下再次运行 `gcc` ，而不是让您输入数百个字符，在此期间，它将显示发出给 `cpp` 、 `as` 和 `ld` 的每个命令。输入以下命令：

```shell
    gcc –v hello.c –o hello
```

The `–v` command puts `gcc` in verbose mode. As you’ll see, while your terminal screen fills up and scrolls, it’s verbose with a vengeance. There’s a lesson here too: building a program is often complex even when the program itself is trivially simple. Unless you have a very good reason not to, let `gcc` do the heavily lifting on C projects.

> `–v` 命令将 `gcc` 置于详细模式。正如您将看到的，当您的终端屏幕填满并滚动时，它非常冗长。这里也有一个教训：即使程序本身很简单，构建程序也往往很复杂。除非你有很好的理由不这样做，否则让 `gcc` 来承担 C 项目的重任。

### Using Linux Make

The `gcc` compiler is actually very good at managing the complexity of the build process, but it has limits. Once you go beyond simple test programs like `Hello, World!` you should study Linux `make`. In general terms, a _make utility_ is a software mechanism that coordinates the compilation and linking of multiple source code files into a single executable file. Make utilities pay special attention to two things:

> `gcc` 编译器实际上非常擅长管理构建过程的复杂性，但它有局限性。一旦你超越了 `Hello，World！` 这样的简单测试程序，你就应该学习 Linux `make` 。一般来说，*make utility* 是一种协调将多个源代码文件编译和链接到单个可执行文件中的软件机制。让公用事业部门特别注意两件事：

- **Dependencies:** What source code files depend on what other files to provide functions, data definitions, constants and so on.
- **Timestamps:** When a source code file was last changed, and when object code files and executables were last built.

> - **相关性：**什么源代码文件取决于要提供函数、数据定义、常量等的其他文件。
> - **时间戳：**上次更改源代码文件的时间，以及上次生成目标代码文件和可执行文件的时间。

When we say that File X _depends_ on File Y, we mean that we need File Y to build File X. Furthermore, a change in File Y requires that File X be rebuilt, otherwise File X may make assumptions about code or data defined in File Y that are no longer true. That can cause several kinds of error. For example, if a variable called `Distance` is defined in File Y as an integer, code in File X will use integer maths to manipulate the `Distance` variable. If we change `Distance` to a floating-point number in File Y, the integer maths code in File X may no longer work correctly. We then have to modify and rebuild File X to match the changes we made earlier in File Y.

> 当我们说文件 X 依赖于文件 Y 时，意味着我们需要文件 Y 来构建文件 X。此外，文件 Y 中的更改需要重建文件 X，否则文件 X 可能会对文件 Y 中定义的代码或数据做出不再正确的假设。这可能会导致几种错误。例如，如果在文件 Y 中将名为 `Distance` 的变量定义为整数，则文件 X 中的代码将使用整数数学来操作 `Distance` 变量。如果将文件 Y 中的 `Distance` 更改为浮点数，则文件 X 中的整数数学代码可能不再正常工作。然后，我们必须修改和重建文件 X，以匹配之前在文件 Y 中所做的更改。

Files may depend upon files that in turn depend upon other files. This is called a _dependency chain_. We saw this on our quick tour of `gcc`: an executable file depends upon one or more object files, which in turn depend upon one or more source files (see Figure 5-25).

> 文件可能依赖于文件，而文件又依赖于其他文件。这称为 *dependency chain*。我们在快速浏览 `gcc` 时看到了这一点：一个可执行文件依赖于一个或多个对象文件，而对象文件又依赖于一或多个源文件(见图 5-25)。

![[FIGURE 5-25:](#08_9781119183938-ch05.xhtml#rc05-fig-0025) Dependency chains](./media/images/9781119183938-fg0525.png)

In [Figure 5-25](#08_9781119183938-ch05.xhtml#c05-fig-0025), a dependency chain begins at any block and follows the arrows to the executable file. All object files depend on their source files. The Library A object file depends on the Library A source file, and so on. Application Modules 2 and 3 both make calls into Library A, so both depend on Library A. Neither depends on Library B. Application Module 1 makes calls only into Library B, so it depends on Library B but not Library A. All chains end at the executable. This means that the executable file depends on everything.

> 在[图 5-25](#08_9781119183938-ch05.xhtml#c05-fig-0025) 中，依赖链从任何块开始，并按照箭头指向可执行文件。所有对象文件都依赖于其源文件。库 A 对象文件依赖于库 A 源文件，依此类推。应用程序模块 2 和 3 都调用库 A，因此都依赖于库 B。两者都不依赖库 B。这意味着可执行文件依赖于所有内容。

The brute-force way to avoid problems when building the application executable is to rebuild _everything_ whenever _anything_ changes anywhere in the chart. That may work for simple projects, but once there are eight or 10 source code files, lots of time will be wasted rebuilding code that doesn’t depend on anything that has changed since the last build.

> 在构建应用程序可执行文件时，避免问题的最有力的方法是每当图表中的任何地方发生变化时，都要重建所有内容。这可能适用于简单的项目，但一旦有了八个或十个源代码文件，那么将浪费大量时间来重新构建代码，这些代码不依赖于自上次构建以来发生的任何更改。

The make utility automates the build process. It uses file timestamps to determine what has to be rebuilt and what doesn’t. If an object file is newer than its source file, it means that any changes made to the source file are already reflected in the object file. Once edits are made to the source code, the source file will be newer than the object file. The make utility then invokes whatever tools are necessary to rebuild the object file.

> make 实用程序自动化了构建过程。它使用文件时间戳来确定哪些需要重建，哪些不需要重建。如果对象文件比其源文件新，则意味着对源文件所做的任何更改都已反映在对象文件中。对源代码进行编辑后，源文件将比目标文件更新。然后，make 实用程序调用重建对象文件所需的任何工具。

The same is true of object code files that make use of code or data in other object code files. In [Figure 5-25](#08_9781119183938-ch05.xhtml#c05-fig-0025), the App 1 object code file calls functions in Library B. So when the Library B source code changes, Library B has to be rebuilt. However, because Application Module 1 calls functions in Library B, any changes to Library B will require that Application Module 1 be rebuilt as well. Because the application executable depends on everything, it must be newer than everything. Once some part of a dependency chain becomes newer than the application, the whole chain starting at the newer file must be rebuilt.

> 使用其他目标代码文件中的代码或数据的目标代码文件也是如此。在[图 5-25](#08_9781119183938-ch05.xhtml#c05-fig-0025) 中，App 1 目标代码文件调用库 B 中的函数。因此，当库 B 源代码更改时，必须重建库 B。然而，因为应用程序模块 1 调用库 B 中的函数，所以对库 B 的任何更改都需要重新构建应用程序模块。因为应用程序可执行文件依赖于所有内容，所以它必须比所有内容都更新。一旦依赖链的某一部分变得比应用程序新，则必须重新构建从新文件开始的整个链。

How does the make utility know what depends on what? It needs a road map, and on Linux operating systems, the road map is called a _makefile_. The makefile is a simple text file that describes dependencies among files, and how files are to be rebuilt. Its default name is `makefile`. If you define a project folder and all project files are present in that folder, you can use the default name. Once you have a makefile that describes your project, you can kick off a build by simply executing the program `make` in a terminal window. Even if there’s only a single source code file in your project, it’s less keyboarding to simply type `make` than, for example, `gcc hello.c -o hello.`

> make 实用程序如何知道什么取决于什么？它需要路线图，在 Linux 操作系统上，路线图称为 *makefile*。makefile 是一个简单的文本文件，它描述了文件之间的依赖关系以及如何重建文件。其默认名称为 `makefile` 。如果定义了项目文件夹，并且该文件夹中存在所有项目文件，则可以使用默认名称。一旦有了描述项目的 makefile，就可以通过在终端窗口中执行程序 `make` 来启动构建。即使项目中只有一个源代码文件，简单地键入 `make` 也比键入 `gcc-hello.c-o-hello` 要简单得多 `

In its simplest form (as you’ll encounter it while learning a new language or programming generally) a makefile is a sequence of rules. Each rule has two parts:

> 在其最简单的形式中(正如您在学习新语言或编程时所遇到的)，makefile 是一系列规则。每个规则有两部分：

- A line defining a target file and one or more component files. The target file depends on the component files.
- A line immediately beneath it specifying the command used to build the target from its components. In Linux `make`, this second line must be indented from the left margin by a single tab character. The tab character helps `make` easily determine which line in the rule is which.

> - 定义目标文件和一个或多个组件文件的行。目标文件取决于组件文件。
> - 它下面的一行，指定用于从其组件构建目标的命令。在 Linux `make` 中，第二行必须从左边距缩进一个制表符。制表符有助于 `make` 轻松确定规则中的哪一行是哪一行。

For our simple `Hello, World!` project in C, the makefile would contain only one rule:

> 对于我们简单的 C 语言 `Hello，World！` 项目，makefile 只包含一个规则：

```make
    hello: hello.c
      gcc hello.c –o hello
```

Type the rule into a text editor and save it as `makefile`, with no file extension. Then type `make`. If your executable file is older than your source file, `hello.c`, `make` will rebuild your executable by running `gcc` as shown in the second line of the rule.

> 在文本编辑器中键入规则，并将其另存为 `makefile` ，不带文件扩展名。然后键入 `make` 。如果可执行文件比源文件旧，`hello.c` 、 `make` 将通过运行 `gcc` 重建可执行文件，如规则第二行所示。

As explained earlier, `gcc` hides some of the complexity of a build by automatically executing the preprocessor, assembler and linker as needed. If you’re not using compilers in `gcc`, you may have to spell out the steps separately in your makefile. Here’s an example makefile that invokes a non-`gcc` assembler and the `gcc` linker separately to create an executable:

> 如前所述，`gcc` 根据需要自动执行预处理器、汇编器和链接器，从而隐藏了构建的一些复杂性。如果您没有在 `gcc` 中使用编译器，您可能需要在 makefile 中单独列出这些步骤。下面是一个示例 makefile，它分别调用非 `gcc` 汇编器和 `gcc` 链接器来创建可执行文件：

```make
    hellosyscall: hellosyscall.o
      ld –o hellosyscall.o hellosyscall
    hellosyscall.o: hellosyscall.asm
      nasm –f elf –g –F stabs hellosyscall.asm
```

Rules generally begin with the executable file and work back from there. The preceding makefile begins with the rule defining the dependency of the executable file on its object file, and how the executable is created with the linker `ld`. The second rule defines the dependency of the object file `hellosyscall.o` on `hellosyscall.asm`, and how the object file is built from the source file with a non-`gcc` assembler called `nasm`.

> 规则通常从可执行文件开始，然后从那里开始工作。前面的 makefile 从定义可执行文件对其对象文件的依赖性以及如何使用链接器 `ld` 创建可执行文件的规则开始。第二条规则定义了对象文件 `hellosyscall.o` 对 `hellosys call.asm` 的依赖性，以及如何使用名为 `nasm` 的非 `gcc` 汇编器从源文件构建对象文件。

If your project has libraries or multiple modules with separate source code files, those rules would be included after rules building the executable. As a rule of thumb: the file that depends on everything (generally the executable) has the first rule in the makefile. The file or files that depend upon nothing but their own source would be last. Look back at [Figure 5-25](#08_9781119183938-ch05.xhtml#c05-fig-0025) and trace out its dependency chains if this isn’t clear to you.

> 如果您的项目具有带有单独源代码文件的库或多个模块，则这些规则将在规则构建可执行文件之后包含。作为经验法则：依赖于一切的文件(通常是可执行文件)在 makefile 中具有第一个规则。仅依赖于其自身来源的一个或多个文件将是最后一个。回头看[图 5-25](#08_9781119183938-ch05.xhtml#c05-fig-0025)，如果您不清楚，请追踪其依赖链。
