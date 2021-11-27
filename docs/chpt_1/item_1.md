# 第 1 项：了解 Python 解释器

与其他高级程序语言一样，**Python 解释器** (Python interpreter) 是负责将 Python 代码解释为机器码的程序。在该部分，我们将简要了解 Python 的解释器版本与 Python 的不同解释器实现。

## Python 解释器版本

你通常可以通过下面的命令来查看 Python 解释器版本：

``` shell
$ python --version
Python 3.10.0
```

!!! warning "注意"
    由于 Python 2 已于 2020 年 1 月 1 日开始停止维护[^1]，而目前 Python 3 正在积极维护，因此若无特别需求，请选择 Python 3 开发你的程序。

Python 版本的选取并非总是越新越好，实际如何选取 Python 版本取决于你的项目需求。你需要结合你所使用的依赖库的版本，以及你所希望使用的 Python 特性所支持的 Python 版本，综合考虑如何为你的项目选取 Python 版本。

## Python 解释器实现

Python 解释器可以使用多种语言实现。Python 使用 CPython 作为默认解释器实现，同时这也是 Python 的参考实现。多数情况下，你不需要考虑使用其他的解释器实现，使用 CPython 能够保证最大的兼容性，尤其是对于开源项目。

不过如果你有一些特别的需求，例如你十分看中项目的执行效率，那么你也可以考虑 [PyPy](https://www.pypy.org/) 这样的解释器实现；或者你需要你的项目与 Java 等其他语言项目配合使用，则诸如 [Jython](https://www.jython.org/) 或 [IronPython](https://www.ironpython.net/) 等解释器实现可能会很有帮助。

[^1]: Sunsetting Python 2. Python.org. https://www.python.org/doc/sunset-python-2/
