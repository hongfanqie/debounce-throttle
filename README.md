# JavaScript 函数去弹跳与节流

作者 [Ivan Yan](http://yanxyz.net/)，文章版权["署名-非商用-相同方式共享"](http://creativecommons.org/licenses/by-nc-sa/4.0/)，意见[反馈](https://github.com/hongfanqie/debounce-throttle/issues)。

先说节流（throttle），它相对好理解。类比水龙头控制水流大小，函数节流意思是控制函数执行的频率。

去弹跳（debounce），在电路设计中有一个现象：“开关弹跳”（switch bounce），参见 [Richyway位老師教學部落格: 開關彈跳波形](http://richywayteach.blogspot.com/2015/01/blog-post_13.html)（天朝点[这里](http://oszine.com/richyway-button/)），解决这个问题即“开关去弹跳”（switch debounce）。类似地，函数去弹跳意思是只要函数在连续调用就不执行，直到停止调用一段时间后才执行。

译文：

- [Debounce 与 Throttle: 图解](./debounce-and-throttle-visual-explanation)
- [jQuery throttle / debounce: 有时，少就是多！](./jquery-throttle-debounce-plugin)

实现可以参考:

- underscore.js: [.throttle()](http://underscorejs.org/#throttle) [.debounce()](http://underscorejs.org/#debounce)
- lodash.js [.throttle()](https://lodash.com/docs#throttle) [.debounce()](https://lodash.com/docs#debounce)
- [Throttling function calls](https://remysharp.com/2010/07/21/throttling-function-calls)
