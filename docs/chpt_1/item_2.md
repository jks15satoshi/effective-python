# 第 2 项：遵循 PEP 8 规范

理论来讲，编写一个 Python 并不需要什么规范，只要你的项目合乎 Python 的语法规则，可以顺利执行，就没什么问题。不过正如 [Python 之禅](./item_0.md) 所表达的，项目的源码是给人看的，尤其是给其他人看的，为了源码更容易被任何人理解和维护，维持源码的美观与易读就十分重要。

PEP 8 是 Python 提供的代码格式化规范，罗列了相当多项 Python 官方建议或不建议使用的代码风格，整个 Python 社区都在尽力遵循 PEP 8 所规定的诸多规范。因此在编写 Python 项目时，**强烈建议** 遵循 PEP 8 规范。

PEP 8 规范原文请参考 [PEP 8 文档](https://www.python.org/dev/peps/pep-0008/)。

## 善用代码格式化工具

PEP 8 的规则比较零散琐碎，与其记住每个规则细节，在项目中使用格式化工具辅助可能是一个较为高效的方式。

### 静态代码格式检查

静态代码格式检查工具（code linter）能够检查出代码存在的不符合规范的地方。以 `pycodestyle` 为例，对下面令人血压升高的 Python 代码进行检查：

``` python title="choice.py" linenums="1"
import random

class Choice:
    def __init__(self,choices):
      self.choices=choices
    
    def action(self):
      return random.choices(self.choices)
        
choice=Choice([1,2,3])
print(choice.action())
```

执行下面的命令就可以查看文件中不符合规范的位置及详细原因：

``` shell
$ pycodestyle choice.py
choice.py:3:1: E302 expected 2 blank lines, found 1
choice.py:4:22: E231 missing whitespace after ','
choice.py:5:7: E111 indentation is not a multiple of four
choice.py:5:19: E225 missing whitespace around operator
choice.py:6:1: W293 blank line contains whitespace
choice.py:8:7: E111 indentation is not a multiple of four
choice.py:9:1: W293 blank line contains whitespace
choice.py:10:1: E305 expected 2 blank lines after class or function definition, found 1
choice.py:10:7: E225 missing whitespace around operator
choice.py:10:17: E231 missing whitespace after ','
choice.py:10:19: E231 missing whitespace after ','
```

不同的静态检查工具在使用上大同小异，但检查方向可能存在不同。静态检查大体上分为以下几种方向：

- 逻辑检查：检查代码中存在的语法错误，或者不合理与可能导致意料之外结果的代码，如 [`bandit`](https://github.com/PyCQA/bandit) 和 [`mypy`](https://github.com/python/mypy)；
- 风格检查：检查代码风格是否符合 PEP 8 规范，如 [`pycodestyle`](https://github.com/PyCQA/pycodestyle)；
- 类型检查：检查代码中的变量类型在执行过程中是否符合预期，如 [`pyright`](https://github.com/microsoft/pyright)。

部分检查工具可能能够处理多种检查方向，例如 [`Pylint`](https://pylint.org) 和 [`Flake8`](https://github.com/PyCQA/flake8) 都具备逻辑检查和风格检查的功能。

由于选择很多，可以事先花上一些时间使用这些工具，再根据自己或团队的习惯选取静态检查工具。

### 自动格式化工具

自动格式化工具 (formatter) 可以自动将不符合 PEP 8 规范的代码更正为符合规范的代码。目前常见的自动格式化工具有 [`autopep8`](https://github.com/hhatto/autopep8)、[`yapf`](https://github.com/google/yapf) 和 [`black`](https://github.com/psf/black)。

以 `autopep8` 为例，和上面的代码检查类似，通过执行下面的命令即可对原来不符合规范的代码文件进行自动更正：

``` shell
$ autopep8 choice.py --in-place  # --in-place 表示将更正后的代码写回原文件
$ cat choice.py
import random


class Choice:
    def __init__(self, choices):
        self.choices = choices

    def action(self):
        return random.choices(self.choices)


choice = Choice([1, 2, 3])
print(choice.action())
```

不过尽管同为自动格式化工具，每个工具还是有着不同的侧重：

- `autopep8` 只会对代码进行最基本的格式化，使代码能够满足最基本的 PEP 8 规范即可，弹性较大，但是不能做到统一整个项目的风格一致性；
- `yapf` 可以通过配置设置整个项目的风格，并按照配置风格对代码进行格式化，因此可以保证项目整体的代码风格一致。牺牲了一定的弹性，同时由于 `yapf` 提供了非常多的配置选项，因此可能也需要花费一定的时间进行调校；
- `black` 的开发团队规定了一套他们所认为更加合理的代码规范，并强制将所有代码都按照自定的规范进行格式化，因此风格一致性最强，但是弹性可以说几乎没有。

使用前可以综合考虑项目的实际情况与习惯，选择适合自己或团队的自动格式化工具。

许多 IDE（例如 Visual Studio Code 或 PyCharm）都提供了静态检查与自动格式化工具的适配，可以通过其自定义的操作，脱离控制台，更加快捷地使用上述工具。

## PEP 8 不是教条

尽管 PEP 8 是一项强烈建议遵循的规范，但这并不意味着你必须一成不变地完全遵循这个规范。PEP 8 不是教条，它只是一项指导性的规范建议。

这里举两个反例：

- 在 Python 标准库中的单元测试模块 `unittest` 中就并未完全遵循 PEP 8 的命名规范，例如 `setUp` 和 `tearDown`，其使用的就是小驼峰式命名而非 PEP 8 建议的小写下划线式命名[^1]；
- 上一节介绍的自动格式化工具 `black`，其设置的行长度限制为 88 字符，而非 PEP 8 所建议的 79 字符[^2]。

在实际开发过程中，你其实也可以灵活地应用自己认为更加合理的规范，并不一定需要拘泥于 PEP 8 的规范。真正重要的是，无论是 PEP 8 还是自定规则，你都需要让整个项目遵循相同的规范。维持代码的可读性，这才是建立与采用代码风格规范的核心目的。

除了 PEP 8 规范以外，如 Google 的 [风格规范](https://google.github.io/styleguide/pyguide.html) 等同样值得参考。

[^1]: `unittest` — Unit testing framework. Python.org. https://docs.python.org/3/library/unittest.html#test-cases
[^2]: The *black* code style — Line length. Black documentation. https://black.readthedocs.io/en/stable/the_black_code_style/current_style.html#line-length
