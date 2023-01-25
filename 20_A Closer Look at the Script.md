# A Closer Look at the Script

We want to give a little more detail about a few things in the script. Look first at the `GPIO.setwarnings()` line. If a GPIO script has been interrupted, the next script you run may cause this warning because the system thinks the crashed program still is using the GPIO service. It’s only a warning and does not stop the script, but this line stops this minor annoyance.

> 我们想对脚本中的一些内容提供更多的细节。首先看 `GPIO.setwarnings()` 行。如果 GPIO 脚本被中断，您运行的下一个脚本可能会导致此警告，因为系统认为崩溃的程序仍在使用 GPIO 服务。这只是一个警告，并没有停止脚本，但这一行停止了这个小烦恼。

Also, the `GPIO.cleanup()` command (the last line in the script) cleans up by releasing the GPIO to prevent the warning we just discussed. It’s good programming practice to include in your scripts.

> 此外， `GPIO.cleanup()` 命令(脚本中的最后一行)通过释放 GPIO 来进行清理，以防止我们刚才讨论的警告。将其包含在脚本中是很好的编程实践。

#### Example of Using Input

Using a pin for output is perhaps not as simple as it might appear. When a pin is set to input, pressing a switch connected from the pin to ground closes a circuit and you get an input, right? The problem is that in actual use, the Raspberry Pi can become confused about whether a switch is open or closed. This phenomenon is called _floating_.

> 使用引脚进行输出可能不像看起来那么简单。当一个引脚被设置为输入时，按下一个从引脚连接到接地的开关，电路就会闭合，你会得到一个输入，对吗？问题是，在实际使用中，树莓派可能会混淆开关是打开还是关闭。这种现象被称为 `漂浮` 。

Input pins actually have three states—on, off and floating (where the logic is not clear). For practical results in using input logic, we need the Raspberry Pi detecting on or off states (true or false) only.

> 输入引脚实际上有三种状态：开、关和浮动(逻辑不清楚)。对于使用输入逻辑的实际结果，我们只需要 Raspberry Pi 检测开或关状态(真或假)。

A solution to this problem of three states involves providing `pull up` and `pull down` reference voltages so the Raspberry Pi knows definitely when it gets an input. GPIO pins have an internal pull-up/pull-down resistor that can be enabled via programming, such as in a Python script.

> 解决这个三态问题的方法包括提供 `上拉` 和 `下拉` 参考电压，以便树莓派明确知道何时收到输入。GPIO 引脚有一个内部上拉/下拉电阻器，可以通过编程(如 Python 脚本)启用。

---

> [!NOTE]

_Pull up_ means the switch or other input device connects to the negative end of the pull-up resistor. _Pull down_ hooks the device to the positive end. A diagram of pull up and pull down is shown in Figure 12-16.

> *上拉*表示开关或其他输入设备连接到上拉电阻器的负端\_将设备向下拉至正极。上拉和下拉示意图如图 12-16 所示。

![[FIGURE 12-16:](#15_9781119183938-ch12.xhtml#rc12-fig-0016) Pull up (top) and pull down (bottom)](./media/images/9781119183938-fg1216.png)

In [Figure 12-16](#15_9781119183938-ch12.xhtml#c12-fig-0016), Vcc refers to a positive voltage supply. This would be 3.3 VDC on the Raspberry Pi. Because this connection and the pull-up resistor are internal, all that’s required of you is a line in Python when you want to use a pin as an input.

> 在[图 12-16](#15_9781119183938-ch12.xhtml#c12-fig-0016) 中，Vcc 表示正电压电源。树莓派上的电压为 3.3 VDC。因为这个连接和上拉电阻是内部的，所以当你想使用管脚作为输入时，你只需要 Python 中的一条线。

For example, we can write a script detecting the press of a button like this:

> 例如，我们可以编写一个检测按下按钮的脚本，如下所示：

```python
    ## Input Using Pullup #############################################
    import RPi.GPIO as GPIO                    ## Import GPIO library
    import time                                ## Need this for delay
    GPIO.setmode(GPIO.BOARD)                   ## Use board pin numbering

    GPIO.setup(15, GPIO.IN) ## Set pin 15 to input with pullup

    ## Let us know whenever button is pressed, please #################

    print `Push this button`
    while True:
         button_pressed = GPIO.input(15)
         if button_pressed == False:
              print(`DING DONG, button pressed!`)
              time.sleep(0.3)

    GPIO.cleanup                           ## End program gracefully
```

The physical circuit using alligator clips or on a breadboard is minimal to construct. Run a jumper wire from pin 15 to one side of the switch and run another jumper wire from the other side of the switch to ground. Run the script, press the button three times and you get the following output:

> 使用鳄鱼夹或在试验板上构建的物理电路是最小的。将一根跨接导线从触针 15 连接到开关的一侧，并将另一根跨接线从开关的另一侧连接到接地。运行脚本，按下按钮三次，您将得到以下输出：

```
    Push this button
    DING DONG, button pressed!
    DING DONG, button pressed!
    DING DONG, button pressed!
```

### Alternative Modes

In the previous section we mentioned the alternative modes of the GPIO pins. Theoretically, there can be up to six alternative uses of a particular pin. The ALT functions are pin dependent. You can set individual pins to be in different ALT modes at any given time. In other words, not all pins need to be in ALT 1 mode at the same time; some pins can be in ALT 0 mode and a couple of others can be in ALT 4 mode.

> 在上一节中，我们提到了 GPIO 引脚的替代模式。理论上，一个特定引脚可以有多达六种替代用途。ALT 功能取决于引脚。您可以在任何给定时间将各个引脚设置为不同的 ALT 模式。换句话说，并非所有引脚都需要同时处于 ALT1 模式；一些引脚可以处于 ALT 0 模式，而一些其他引脚可以处于 ALT4 模式。

---

> [!TIP]

The `Raspberry Pi GPIO Pin Alternative Functions` article ([`www.dummies.com/how-to/content/raspberry-pi-gpio-pin-alternative-functions.html`](http://www.dummies.com/how-to/content/raspberry-pi-gpio-pin-alternate-functions.html)) is good reading for a fast start in using alternative modes. Also check out the Broadcom documentation for the 2835 and 2836 (the latter is for the Raspberry Pi 2 Model B) for more detailed information.

> `树莓皮 GPIO 引脚替代功能` 一文([`www.dummies.com/how-to/content/树莓皮GPIO引脚替代功能.html`](http://www.dummies.com/how-to/content/raspberry-pi-gpio-pin-alternate-functions.html))是在使用替代模式时快速启动的良好读数。请查看 2835 和 2836 的 Broadcom 文档(后者适用于复盆子 Pi 2 B 型)以了解更多详细信息。

For the aforementioned detailed information concerning the 2835 chip, download the Broadcom 205-page PDF at [`www.alldatasheet.com/datasheet-pdf/pdf/502533/BOARDCOM/BCM2835.html`](http://www.alldatasheet.com/datasheet-pdf/pdf/502533/BOARDCOM/BCM2835.html). Evidently, this level of detail is not available yet for the 2836.

> 有关 2835 芯片的上述详细信息，请下载 Broadcom 205 页 PDF，网址为[`www.alldatasheet.com/datasheetpdf/PDF/502533/BOARDCOM/BCM2835.html`](http://www.alldatasheet.com/datasheet-pdf/pdf/502533/BOARDCOM/BCM2835.html). 显然，2836 还没有这种详细程度。

### GPIO Experimentation the Easy Way

We should mention that when using jumper cables on something as crowded with pins as P1, the GPIO header is a pin. Also you need to take great care to avoid shorts. Using such aids as breakout boards, breadboards and prototyping boards—many of which are available at low cost from major online retailers—offers a better solution.

> 我们应该提到，当在像 P1 这样的引脚密集的设备上使用跳线时，GPIO 头是一个引脚。此外，你需要非常小心地避免穿短裤。使用诸如突破板、试验板和原型板等辅助工具，其中许多可以从主要在线零售商以低成本获得，提供了更好的解决方案。

These boards have connectors that plug into P1, and the additional board gives you much more room for adding jumpers, resistors and other components.

> 这些电路板具有插入 P1 的连接器，额外的电路板为您提供了更多的空间来添加跳线、电阻器和其他组件。

# WILEY END USER LICENSE AGREEMENT

Go to [www.wiley.com/go/eula](http://www.wiley.com/go/eula) to access Wiley’s ebook EULA.

> 转到 [www.wiley.com/Go/eula](http://www.wiley.com/go/eula) 访问 Wiley 的电子书 EULA。
