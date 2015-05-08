# Debounce 与 Throttle: 图解

[Debounce and Throttle: a visual explanation](http://drupalmotion.com/article/debounce-and-throttle-visual-explanation) 由 [Ivan Yan](http://yanxyz.net/) 翻译。译文版权["署名-非商用-相同方式共享"](http://creativecommons.org/licenses/by-nc-sa/4.0/)，意见[反馈](https://github.com/hongfanqie/debounce-throttle/issues)。注意本文只是选译。

去弹跳（debounce）和节流（throttle）这两个概念，我们可以用到 JavaScript 中，以加强控制函数的执行，特别是事件处理器。

这两种技术以不同的方式回答了同一个问题“在一定时间内函数可以执行多少次”：

- **去弹跳** 把它想成“将多个事件积累为一个”。比如，你回家，进入电梯，电梯门正要关上……忽然你的邻居出现在大厅里并且想冲入电梯。讲礼貌！为他打开电梯门：你阻止（去弹跳）了电梯的离开。假如这种情况因第三个人再次发生，第四个人……可能延迟电梯几分钟。
- **节流** 把它想成一个阀门，调节函数执行的“流量”。我们可以决定在一定时间内函数能执行的最大次数。类比于电梯的例子，你讲礼貌，不过只想等人 10 秒，时间一过就走。

没有去弹跳与节流的事件处理器像只运载一个人的电梯：没效率。

我希望这个糟糕的类比有帮助，不过有时文字不能帮助理解这些概念，所以我创建了一个示例，将去弹跳与节流应用到 mousemove 事件上，从而可视化地理解它们。

## 实现

- [Underscore.js](http://underscorejs.org/)
- [Lodash.js](http://lodash.com/)
- [jQuery Plugin](../jquery-throttle-debounce-plugin/)

译注：原文的[示例](https://github.com/dcorb/debounce-throttle)现在不能正常运行了。更好的一个示例见 [Debounce and Throttle patterns, in a more interactive way](https://github.com/caiogondim/js-debounce-throttle-visual-explanation)。

## 去弹跳用例

使用它取消若干频繁发生的事件直到它缓慢下来。例如：

- 在文本框内快速输入时：你不想处理它的内容直到用户停止输入。
- 当通过 AJAX 向服务器发送数据时：你不想让你的服务器每秒接收几十个的垃圾内容。

## 节流用例

与去弹跳一样的用例，不过你想确保在一定的时间内至少执行几次回调。

- 如果用户快速的输入 30 秒，也许你想每 5 秒处理一次输入的内容。
- 节流滚动事件处理器会带来巨大的性能提升，简单的鼠标滚动移动每秒能触发数十次事件。
