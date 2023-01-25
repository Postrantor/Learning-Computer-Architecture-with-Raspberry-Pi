# Circuits

Electricity works in circles. (A closed loop is called a _circuit._) A very simple circuit, as shown in Figure 12-11, consists of a battery (voltage source) and a resistor (or load). The load performs work by resisting the voltage and consuming current as the battery overcomes the resistance to complete its circuit.

> 电在循环中工作。(闭环称为电路。)如图 12-11 所示，一个非常简单的电路由电池(电压源)和电阻器(或负载)组成。当电池克服电阻完成电路时，负载通过抵抗电压和消耗电流来完成工作。

Putting a switch (a device that breaks the circuit when in the ‘off’ position and completes it when in the ‘on’ position) anywhere in the circuit gives us a way of controlling it.

> 在电路中的任何位置放置开关(一种当处于“关闭”位置时断开电路，当处于“打开”位置时完成电路的装置)，可以为我们提供一种控制电路的方法。

If there is no load component (like a resistor), a wire from the positive to negative terminals of the battery creates a _short circuit_ and quickly depletes all the energy stored in the battery.

> 如果没有负载部件(如电阻器)，从蓄电池正极到负极的导线会产生短路，并迅速耗尽蓄电池中存储的所有能量。

To use the GPIO pins, we need to make complete circuits and avoid short circuits or otherwise overloading the Raspberry Pi’s current-providing capacity. Don’t worry, you’ll be provided with safe guidelines for doing this later in this chapter.

> 要使用 GPIO 引脚，我们需要制作完整的电路，避免短路或使 Raspberry Pi 的电流供应能力过载。别担心，本章稍后将为您提供安全指南。

Of the 26 GPIO pins on the Model B, 17 are programmable switches — specifically 3, 5, 7, 8, 10, 11, 12, 13, 15, 16, 18, 19, 21, 22, 23, 24 and 26.

> 在 B 型的 26 个 GPIO 引脚中，有 17 个是可编程开关，具体为 3、5、7、8、10、11、12、13、15、16、18、19、21、22、23、24 和 26。

Ground pins (places to complete a circuit) are 6, 9, 14, 20 and 25.

> 接地引脚(完成电路的位置)为 6、9、14、20 和 25。

Pins 2 and 4 supply 5 volts (like the positive terminal on a battery). Pins 1 and 17 give 3.3 volts. Both require circuits that eventually come back to one of the ground pins noted earlier.

> 针脚 2 和 4 提供 5 伏电压(与蓄电池正极端子相同)。针脚 1 和 17 给出 3.3 伏。两者都需要最终返回到前面提到的接地引脚之一的电路。

#### GPIO Operation

A GPIO pin, such as the 17 out of 26 pins on the Raspberry Pi B’s board that are programmable switches, works in _binary_ mode. Binary is just a fancy way of saying “on” or “off”. That’s how digital computers compute—they have bunches of circuits tied together, and those circuits are either on or off. In computer talk, 0 represents _off_ and the number 1 represents _on_. Programmers call the _state_ of the circuit—whether it’s on or off—_high_ (on) and _low_ (off).

> GPIO 引脚，例如 Raspberry Pi B 板上 26 个引脚中的 17 个是可编程开关，在二进制模式下工作。二进制只是“开”或“关”的一种奇特说法。这就是数字计算机的计算方式，它们有一束束电路连接在一起，这些电路要么通要么断。在计算机交谈中，0 代表 *off*，数字 1 代表 *on*。程序员调用电路的 *state*，无论它是开还是关——_high_(开)和 *low*(关)。

---

> [!NOTE]

The high/low terminology is not strictly true in hardware interfacing with terms “active low” and “active high”. For instance, in SPI a chip select pin (CS) is “active low”, meaning that the chip will only respond (i.e. be “on”), when CS is set low (0V).

> 在硬件接口中，高/低术语与术语“低活动”和“高活动”并不严格相同。例如，在 SPI 中，芯片选择引脚(CS)为“低激活”，这意味着当 CS 设置为低(0V)时，芯片将仅响应(即“打开”)。

So how would you expect the Raspberry Pi to communicate with real-world devices? The 17 GPIO pins work with the Raspberry Pi’s internal voltage, 3.3VDC. When the logic state is high, the pin shows 3.3VDC. When the logic switches to low, the voltage is 0. By using this scheme, the Raspberry Pi can send commands out and/or receive incoming information.

> 那么，你如何期望树莓派与现实世界的设备进行通信？17 个 GPIO 引脚与 Raspberry Pi 的内部电压 3.3VDC 一起工作。当逻辑状态为高时，引脚显示 3.3VDC。当逻辑切换为低时，电压为 0。通过使用这种方案，树莓派可以发送命令和/或接收传入信息。

Here’s how simple it truly is. One of the most basic circuits we can build is a light and a battery or other power source. We can do this easily with the GPIO pins.

> 这是一个多么简单的过程。我们可以构建的最基本的电路之一是灯、电池或其他电源。我们可以使用 GPIO 引脚轻松完成这一操作。

Figure 12-9 depicts a simple binary on/off circuit. To make it, we choose an output pin and hook one side of an LED light to it using a jumper cable. (LEDs are low current and fun to use as indicator lights, etc.) The other side of the light connects to a 220-ohm resistor (more about this in just a moment) and the other side of the resistor connects to a ground pin.

> 图 12-9 描述了一个简单的二进制开/关电路。为了制作它，我们选择了一个输出引脚，并使用跳线将 LED 灯的一侧连接到它。(LED 电流低，用作指示灯很有趣，等等)灯的另一侧连接到 220 欧姆电阻器(稍后将详细介绍)，而电阻器的另一侧则连接到接地引脚。

![[FIGURE 12-9:](#15_9781119183938-ch12.xhtml#rc12-fig-0009) A GPIO simple LED circuit](./media/images/9781119183938-fg1209.png)

When the output pin is high (has voltage), the LED lights; the LED goes out when the pin has 0 voltage. Later we look at writing programs in Python, which let the Raspberry Pi control the GPIO pins.

> 当输出引脚高(有电压)时，LED 亮起；当引脚具有 0 电压时，LED 熄灭。稍后我们将研究用 Python 编写程序，让树莓派控制 GPIO 引脚。

---

> [!NOTE]

The resistor we used in the circuit in Figure 12-12 is a _current limiting_ component, which is a safeguard to prevent damaging both the Raspberry Pi and the LED.

> 我们在图 12-12 的电路中使用的电阻器是一个限流元件，它是防止损坏树莓派和 LED 的保护措施。

Of course, you normally don’t use all 17 pins. The accepted rule of thumb is to limit each pin to a maximum of about 16mA and not exceed a total of 50mA. No _exact_ power specifications list exists for the Raspberry Pi. Such a list is impossible to create because there are too many variables, such as how the board gets its power and how it connects to a computer (using a USB port or by plugging into a converter connected to a wall socket). However, many smart Raspberry Pi experimenters have done measurements, and the figures we use in this chapter form a consensus of what’s safe and what’s not.

> 当然，您通常不会使用所有 17 个引脚。公认的经验法则是将每个引脚的最大电流限制在 16mA 左右，总电流不超过 50mA。树莓派不存在正确的电源规格列表(_E)。这样的列表是不可能创建的，因为有太多的变量，例如电路板如何获得电源以及它如何连接到计算机(使用 USB 端口或通过插入连接到墙上插座的转换器)。然而，许多聪明的树莓派实验者已经进行了测量，我们在本章中使用的数字形成了关于什么是安全的，什么是不安全的共识。

#### Managing Power

The issue with managing power on the Raspberry Pi stems from its main strength—its small size. On a board the size of a credit card, there is just no room for a massive power-handling circuit.

> 树莓派管理权力的问题源于其主要优势——体积小。在一个信用卡大小的电路板上，根本没有空间容纳大规模的电源处理电路。

That makes it sound like there’s not much power available, right? Don’t worry; there’s plenty of power available. If you are careful, you can run mighty machines with the Raspberry Pi. You just can’t do it directly! Using GPIO requires using control circuits, which utilise relays, stepping switches and other types of external controllers, power transistors, microcontroller boards and other good stuff that lets the Raspberry Pi boss high-current devices.

> 这听起来好像没有太多可用的电力，对吧？别担心；有充足的电力可用。如果你小心，你可以用树莓派运行强大的机器。你不能直接做！使用 GPIO 需要使用控制电路，这些电路利用继电器、步进开关和其他类型的外部控制器、功率晶体管、微控制器板和其他让 Raspberry Pi 控制大电流设备的好东西。

There are two ways to make sure you are using damage-free current levels for the Raspberry Pi. You can _calculate_ it or _measure_ it. First, let’s look at calculation. It’s all about power, which we can measure using the following formula:

> 有两种方法可以确保你使用的是树莓派的无损伤电流等级。你可以计算它或测量它。首先，让我们来看看计算。这都是关于功率的，我们可以使用以下公式来测量：

> _I = V / R_

where I expresses current (in amps), V is voltage (in volts) and R is resistance in ohms. So if you know the voltage (3.3 VDC) and the resistance, you can plug those numbers into the formula to determine the current. Multiply the answer by 1,000 and you’ll have milliamps.

> 其中 I 表示电流(单位：安培)，V 表示电压(单位：伏特)，R 表示电阻(单位：欧姆)。所以如果你知道电压(3.3 VDC)和电阻，你可以把这些数字代入公式来确定电流。把答案乘以 1000，你就会得到毫安。

Here’s an example: say we have a 220-ohm resistor. Divide 3.3 (the voltage) by 220, which results in 0.015. Multiply .015 by 1,000 and you get 15, or 15mA. That’s a safe current for one pin (so long as you do not exceed 50mA overall).

> 这里有一个例子：假设我们有一个 220 欧姆的电阻器。将 3.3(电压)除以 220，得到 0.015。将.015 乘以 1000，得到 15，即 15mA。这是一个引脚的安全电流(只要总电流不超过 50mA)。

---

> [!NOTE]

About the only device you can power safely directly from the GPIO pins is an LED light. However, be sure to put a 220-ohm resistor in series with the LED to limit the current to a safe level.

> 关于唯一可以直接从 GPIO 引脚安全供电的设备是 LED 灯。但是，一定要将一个 220 欧姆的电阻器与 LED 串联，以将电流限制在安全水平。

The formula we just used is called _Ohm’s Law_ (see Figure 12-10). It’s a great tool for calculating safe limits for all your projects. Of course, with the Raspberry Pi, you’ll be working in milliwatts and milliamps (thousandths of watts or amps) and mostly 3.3 VDC.

> 我们刚刚使用的公式称为“欧姆定律”(见图 12-10)。这是一个计算所有项目安全极限的好工具。当然，使用树莓派，你的工作单位是毫瓦和毫安(千分之一瓦或安培)，大部分是 3.3 VDC。

![[FIGURE 12-10:](#15_9781119183938-ch12.xhtml#rc12-fig-0010) Ohm’s Law, where V = voltage in volts, I = current in amps and R = resistance in ohms](./media/images/9781119183938-fg1210.png)

The second way of testing for current level requires a test instrument—a _multimeter_—that measures voltage, current and resistance. You can find inexpensive digital readout multimeters online at Sparkfun ([`www.sparkfun.com`](http://www.sparkfun.com)), Adafruit ([`www.adafruit.com`](http://www.adafruit.com)) and other online retailers for £4 to £15. [Figure 12-11](#15_9781119183938-ch12.xhtml#c12-fig-0011) shows a multimeter.

> 第二种电流水平测试方法需要一个测量电压、电流和电阻的测试仪器——万用表。您可以在 Sparkfun([`www.Sparkfun.com`])在线找到便宜的数字读数万用表(http://www.sparkfun.com))，Adafruit([`www.Adafruit.com`](http://www.adafruit.com))以及其他在线零售商，价格为 4 至 15 英镑。[图 12-11](#15_9781119183938-ch12.xhtml#c12-fig-0011) 显示了万用表。

![[FIGURE 12-11:](#15_9781119183938-ch12.xhtml#rc12-fig-0011) Multimeter](./media/images/9781119183938-fg1211.png)

You use a multimeter _before_ you connect the circuit. Two techniques work here:

> 在连接电路之前使用万用表。这里有两种技术：

- Measure the resistance of the circuit by connecting the multimeter (switched to ohms) across the positive and negative leads of the _unpowered_ circuit. If it reads 220 ohms or more, the circuit is a safe one.

> -通过将万用表(切换至欧姆)跨接在 *unpowered* 电路的正极和负极引线上，测量电路的电阻。如果读数为 220 欧姆或更大，则电路是安全的。

---

> [!TIP]

An infinite reading means your circuit is open and will not work. Check your connections.

> 无限读数意味着电路开路，无法工作。检查您的连接。

- Use a power supply set to 3.3 VDC. With the multimeter set to measure current (amps), put it _in series_ (make it part of the circuit) and check the current. If your reading’s greater than 16mA, add a resistor that limits the current to 16mA or less before connecting the circuit to the Raspberry Pi. [Figure 12-12](#15_9781119183938-ch12.xhtml#c12-fig-0012) shows an example of connecting a battery, resistor and amp meter (such as a multimeter switched to read current). When it’s in series with the circuit, the multimeter reads the amount of current the resistor consumes. In [Figure 12-12](#15_9781119183938-ch12.xhtml#c12-fig-0012), R1 the resistor (right) is represented by the standard symbol for a resistor. The battery is on the left with a plus (+) showing its positive side, and the A in a circle denotes an amp meter for measuring current.

> -使用设置为 3.3 VDC 的电源。将万用表设置为测量电流(安培)，将其置于串联中(使其成为电路的一部分)并检查电流。如果您的读数大于 16mA，在将电路连接到树莓派之前，添加一个电阻器，将电流限制在 16mA 或以下。[图 12-12](#15_9781119183938-ch12.xhtml#c12-fig-0012) 显示了连接电池、电阻器和电流表(例如切换为读取电流的万用表)的示例。当它与电路串联时，万用表读取电阻器消耗的电流量。在[图 12-12](#15_9781119183938-ch12.xhtml#c12-fig-0012) 中，R1 电阻器(右)由电阻器的标准符号表示。电池位于左侧，正极为正(+)，圆圈中的 a 表示用于测量电流的安培表。

![[FIGURE 12-12:](#15_9781119183938-ch12.xhtml#rc12-fig-0012) Measuring current with a multimeter](./media/images/9781119183938-fg1212.png)

---

> [!TIP]

Another great reason for owning a multimeter is for measuring the value of resistors. Resistors have bands of colour indicating how many ohms they are. If you’ve lost the package a resistor came in and don’t know the colour code, a multimeter comes in handy for finding that out. It’s beneficial to learn the colour code, as you won’t always have a multimeter with you.

> 拥有万用表的另一个重要原因是测量电阻值。电阻器有颜色带，指示其电阻值。如果你丢失了包装，一个电阻器进来了，而且不知道颜色代码，万用表就可以帮你找到。学习颜色代码是有益的，因为你不会总是随身携带万用表。

All of the information provided in this section applies to the two 3.3V pins and the 17 switching pins. The two 5 VDC pins pull current through the Raspberry Pi’s 5 VDC “rail”(where all the board’s circuits get their power) and thus from the power source (USB port on a computer, external battery, a converter in a wall socket and so on). Because the current capacities vary widely, keep those current levels low. However, if you must have more power than the 3.3 VDC pins safely supply, the 5-volt pins might be useful.

> 本节中提供的所有信息适用于两个 3.3V 引脚和 17 个开关引脚。两个 5 VDC 引脚通过复盆子 Pi 的 5 VDC“导轨”(所有板的电路都在那里获得电源)拉动电流，从而从电源(计算机上的 USB 端口、外部电池、墙上插座中的转换器等)拉动电流。因为电流容量变化很大，所以保持低电流水平。但是，如果您必须有比 3.3 VDC 引脚安全供电更多的电源，则 5 伏引脚可能有用。

---

CAUTION

> 注意安全

Someone’s likely to point out that you _could_ disconnect the USB cable and run 5 VDC _into_ one of the 5-volt GPIO pins. This setup powers the Raspberry Pi and gives you more current for GPIO operations. The problem is that this bypasses the built-in fuse protection of the Raspberry Pi, which _is not_ a good thing and can result in current greater than a safe level, which can cause damage to the Raspberry Pi’s components. We recommend against it.

> 有人可能会指出，你可以断开 USB 电缆，向一个 5 伏 GPIO 引脚运行 5 VDC。此设置为复盆子 Pi 供电，并为 GPIO 操作提供更多电流。问题是，这绕过了树莓派的内置保险丝保护，这不是一件好事，会导致电流超过安全水平，从而损坏树莓派组件。我们建议反对。

On the other hand, the GPIO truly gives the Raspberry Pi (and you) fantastic capacity for controlling real-world devices. It’s worth learning how to do this safely.

> 另一方面，GPIO 确实为复盆子 Pi(和你)提供了控制现实设备的强大能力。如何安全地做到这一点值得学习。

#### GPIO on the Model B+ and Raspberry Pi 2

If you have the new Model B+ or the Raspberry Pi 2 Model B, there are now 40 GPIO pins. For example, you will have 26 programmable pins overall instead of 17 (9 programmable pins have been added), two more grounds and a couple of pins (27 and 28) that are used as indexes by specialised plug-in boards. Figure 12-13 shows the GPIO pins on the Model B+.

> 如果你有新的 B+ 型或复盆子 Pi 2 B 型，现在有 40 个 GPIO 引脚。例如，您将拥有 26 个可编程引脚，而不是 17 个(增加了 9 个可编程的引脚)，另外两个接地和两个引脚(27 和 28)，这些引脚被专用插件板用作索引。图 12-13 显示了 B+ 型上的 GPIO 引脚。

![[FIGURE 12-13:](#15_9781119183938-ch12.xhtml#rc12-fig-0013) Close-up of GPIO pins on the Raspberry Pi 2 Model B](./media/images/9781119183938-fg1213.png)

### Programming GPIO

The Python scripting language is the recommended and easiest method of programming GPIO. It’s relatively easy to learn and comes standard in operating systems like Raspbian. To find out which version of Python you have, just go to the command line and type _python;_ the version is returned, as shown here:

> Python 脚本语言是 GPIO 编程的推荐和最简单的方法。它相对容易学习，在 Raspbian 等操作系统中是标准的。要了解您的 Python 版本，只需转到命令行并键入*Python；*返回版本，如下所示：

```python
    Python 2.7.9 (default, Mar 8 2015, 00:52:26)
    [GCC 4.9.2] on linux2
```

When you update Raspbian (something you should do regularly), any newer version of Python downloads and installs along with the latest updates of everything else in Raspbian. To update and upgrade Raspbian, type the following from the command line (use the terminal if you run a GUI):

> 当你更新 Raspbian(你应该经常做的事情)时，任何更新版本的 Python 都会下载并安装 Raspbian 中所有其他内容的最新更新。要更新和升级 Raspbian，请在命令行中键入以下命令(如果运行 GUI，请使用终端)：

```
sudo apt-get update && sudo apt-get upgrade
```

---

> [!TIP]

You should update Raspbian regularly for reasons of security and utility—that is, to keep your system secure while taking advantage of ongoing improvements in the hundreds of software packages on your Raspberry Pi.

> 出于安全性和实用性的原因，您应该定期更新复盆子，也就是说，在利用复盆子 Pi 上数百个软件包的持续改进的同时，保持您的系统安全。

Also, if this is your first time using GPIO, you’ll definitely want to install the Python GPIO library by using the following command:

> 此外，如果这是您第一次使用 GPIO，您肯定希望使用以下命令安装 Python GPIO 库：

```
sudo apt-get install rpi.gpio
```

---

> [!NOTE]

Python has many libraries of features and commands; you install only the ones needed for the tasks at hand.

> Python 有许多功能和命令库；您只安装手头任务所需的软件。

Using Python, we write scripts to control the GPIO pins. The first step in writing one of these is to import the GPIO library, giving the script access functions concerning GPIO into your favourite editor, such as _nano_. Type the following command into the editor window:

> 使用 Python，我们编写脚本来控制 GPIO 引脚。编写其中之一的第一步是导入 GPIO 库，将有关 GPIO 的脚本访问函数提供给您喜爱的编辑器，例如 *nano*。在编辑器窗口中键入以下命令：

```
import RPi.GPIO as GPIO
```

The next line specifies the layout of the GPIO pins (yes, you can change it). There are two choices: either match the layout on the board or use a numbering scheme matching the pins on the Broadcom SoC, as in:

> 下一行指定 GPIO 引脚的布局(是的，您可以更改它)。有两种选择：要么匹配电路板上的布局，要么使用与 Broadcom SoC 上的引脚匹配的编号方案，如：

```
GPIO.setmode(GPIO.BOARD)
```

Now we can start programming pins. Add the following lines to set pin 12 as an output:

> 现在我们可以开始编程引脚了。添加以下行以将引脚 12 设置为输出：

```
GPIO.setmode(GPIO.BOARD)
GPIO.setup(12,GPIO.OUT)
```

or as an input:

```
GPIO.setup(12,GPIO.IN)
```

That’s it. Three lines in a Python script and you’ve set up the GPIO to actually do something. For a good starting tutorial on programming GPIO pins, including alternative modes, see “Raspberry Pi GPIO Pins and Python” at [`http://makezine.com/projects/tutorial-raspberry-pi-gpio-pins-and-python/`](http://makezine.com/projects/tutorial-raspberry-pi-gpio-pins-and-python/).

> 就是这样。Python 脚本中有三行代码，您已经设置了 GPIO 来实际执行某些操作。有关编程 GPIO 引脚(包括替代模式)的良好入门教程，请参阅“Raspberry Pi GPIO 引脚和 Python”，网址：[`http://makezine.com/projects/tutorial-raspberry-pi-gpio-pins-and-python/`](http://makezine.com/projects/tutorial-raspberry-pi-gpio-pins-and-python/).

Using Raspbian Jessie (the latest release) on a Raspberry Pi 2 you can easily check GPIO pin settings. In the terminal, type:

> 在 Raspberry Pi 2 上使用 Raspbian Jessie(最新版本)，您可以轻松检查 GPIO 引脚设置。在终端中，键入：

```
gpio readall
```

and a table like the one shown in Figure 12-14 is generated.

> 并生成如图 12-14 所示的表。

![[FIGURE 12-14:](#15_9781119183938-ch12.xhtml#rc12-fig-0014) Table of GPIO pin assignments on Raspberry Pi 2](./media/images/9781119183938-fg1214.png)

#### Building a Simple Circuit

Are you ready to actually make something happen? How about turning on an LED and making it blink? We mentioned lighting an LED earlier but here we’re providing more detail so you can do it yourself. You need the following components to follow along with this example:

> 你准备好了吗？打开 LED 并使其闪烁怎么样？我们之前提到过点亮 LED，但这里我们提供了更多细节，因此您可以自己动手。在本示例中，您需要遵循以下组件：

- A small LED (your choice of colour)
- A 200-ohm resistor
- A breadboard or alligator clips for making connections
- Some small-gauge wire or jumper wires

---

> [!NOTE]

You could use a lower value resistor, but 200 ohms allows the LED to light brightly and the circuit draws less current. Less is always better when using GPIO pins, so use the minimum that you can to make your project successful.

> 你可以使用一个电阻值较低的电阻器，但 200 欧姆可以让 LED 发光，电路消耗的电流也较少。当使用 GPIO 引脚时，越少越好，所以尽可能少地使用，以使项目成功。

Use the following steps to build a simple circuit:

> 使用以下步骤构建简单电路：

1. Use a jumper wire to connect GPIO pin 7 (the positive side of the circuit) to one end of the resistor.
2. Look at your LED. LEDs usually have one wire leg longer than the other, or one leg might have a bend in it. This is the positive side. Connect it to the other end of the resistor.
3. Hook the negative side of the LED to GPIO pin 6, which is ground in the GPIO layout we’re using.

> 1. 使用跳线将 GPIO 引脚 7(电路的正极)连接到电阻器的一端。
> 2. 看看你的 LED。LED 通常有一根电线腿比另一根长，或者一根电线可能有弯曲。这是正面。将其连接到电阻器的另一端。
> 3. 将 LED 的负极连接到 GPIO 引脚 6，该引脚在我们使用的 GPIO 布局中接地。

Your circuit is complete! It might look something like the one in Figure 12-15.

> 你的电路完成了！它可能看起来像图 12-15 所示。

![[FIGURE 12-15:](#15_9781119183938-ch12.xhtml#rc12-fig-0015) Simple breadboard circuit for flashing an LED; the white overlay shows the circuit](./media/images/9781119183938-fg1215.png)

#### Example of Using Output

Now it’s time to write the simple Python script that controls the LED’s blinks. You use a text editor such as nano to write your Python script. Our script (with comments) is shown here.

> 现在是编写控制 LED 闪烁的简单 Python 脚本的时候了。您可以使用诸如 nano 之类的文本编辑器来编写 Python 脚本。我们的脚本(带注释)显示在这里。

```python
## Blinking LED ###################################
import RPi.GPIO as GPIO   ## Import GPIO library
import time               ## Need this for blink delay
GPIO.setmode(GPIO.BOARD)  ## Use board pin numbering
GPIO.setwarnings(False)   ## Disable "Channel already

led = 7                   ## Variable for pin number
GPIO.setup(led, GPIO.OUT) ## Set pin to output

## Blink the LED 60 times, once per second for 2 minutes
print "Blinking"          ## Blinking in progress
for x in range(0, 59):    ## repeats 60 times
     time.sleep(1)        ## Keep it on for 1 second
     GPIO.output(led, 0)  ## Turn LED off
     time.sleep(1)        ## Wait 1 second
GPIO.cleanup()              ## End program gracefully
```

---

> [!TIP]

If this script doesn’t work for you, check your circuit and also check for typos in the script. Typos are the most likely culprit. **As with any code, things have to be exactly right for proper operation to occur.**

> 如果这个脚本不适合您，请检查电路并检查脚本中的拼写错误。台风是最有可能的罪魁祸首。与任何代码一样，事情必须完全正确，才能进行正确的操作。
