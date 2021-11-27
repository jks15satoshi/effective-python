# 第 0 项：Python 之禅

在控制台界面输入 `python` 进入 Python 交互模式，并输入 `import this` 查看输出结果。

!!! note "提示"
    对于部分平台，可能 `python` 命令实际指代的是 Python 2 而非 Python 3，因此你可能需要通过 `python3` 来执行命令。  
    在之后的内容中，一概默认 `python` 为 Python 3。

``` python
>>> import this
The Zen of Python, by Tim Peters

Beautiful is better than ugly.
Explicit is better than implicit.
Simple is better than complex.
Complex is better than complicated.
Flat is better than nested.
Sparse is better than dense.
Readability counts.
Special cases aren't special enough to break the rules.
Although practicality beats purity.
Errors should never pass silently.
Unless explicitly silenced.
In the face of ambiguity, refuse the temptation to guess.
There should be one-- and preferably only one --obvious way to do it.
Although that way may not be obvious at first unless you're Dutch.
Now is better than never.
Although never is often better than *right* now.
If the implementation is hard to explain, it's a bad idea.
If the implementation is easy to explain, it may be a good idea.
Namespaces are one honking great idea -- let's do more of those!
```

!!! quote "翻译"
    美丽优于丑陋  
    明确优于隐晦  
    简短优于复杂  
    复杂优于凌乱  
    平坦优于嵌套  
    稀疏优于密集  
    可读性很重要  
    尽管实用性胜过纯洁性，  
    特殊情况也不足以打破规则  
    除非有明确的必要，  
    否则错误绝不可被悄悄忽略  
    面对模棱两可，拒绝妄加猜测  
    应该提供一种，最好是只有一种明确的方法解决问题  
    尽管这种方法开始可能并不直观，除非你是荷兰人[^1]  
    立刻行动要比从不行动好  
    但不加思索还不如不行动  
    如果实现难以解释，那么这一定不是什么好主意  
    如果实现容易解释，这有可能是个好主意  
    命名空间的概念很好，我们要充分利用它

Python 之禅包含了 19 条影响 Python 语言设计的软件编写原则，被列入于 PEP 20 中[^2]。Python 之禅以这种简短的形式概括了 Python 语言的设计原则与规范。

全文的核心思想就是，要去编写逻辑清晰、易于阅读与维护的代码[^3]。后面的内容会出现许多对这些原则的体现。

[^1]: 根据 Python 之禅的作者 Tim Peters [自述](https://softwareengineering.stackexchange.com/questions/148790/is-the-14th-line-of-the-zen-of-python-a-reference-to-dijkstra/148794#148794)，荷兰人指 Python 的作者 Guido van Rossum。
[^2]: PEP 20 -- The Zen of Python. Python.org. https://www.python.org/dev/peps/pep-0020/
[^3]: 有意思的是，`this` 模块的 [实现](https://hg.python.org/cpython/file/3.5/Lib/this.py) 算是彻头彻尾地违反了上面的原则。
