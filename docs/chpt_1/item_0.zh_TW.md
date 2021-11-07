# 第 0 項：Python 之禪

嘗試進入 Python 互動模式，輸入 `import this`。不知道如何進入互動模式？開啟終端輸入 `python` 試試。

!!! note "提示"
    對於部分平臺，可能 `python` 命令實際指代的是 Python 2 而非 Python 3，因此你可能需要透過 `python3` 來執行命令。  
    在之後的內容中，一概預設 `python` 為 Python 3。

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

!!! quote "翻譯"
    美麗優於醜陋  
    明確優於隱晦  
    簡短優於複雜  
    複雜優於凌亂  
    平坦優於巢狀  
    稀疏優於密集  
    可讀性很重要  
    儘管實用性勝過純潔性，  
    特殊情況也不足以打破規則  
    除非有明確的必要，  
    否則錯誤絕不可被悄悄忽略  
    面對模稜兩可，拒絕妄加猜測  
    應該提供一種，最好是隻有一種明確的方法解決問題  
    儘管這種方法開始可能並不直觀，除非你是荷蘭人[^1]  
    立刻行動要比從不行動好  
    但不加思索還不如不行動  
    如果實現難以解釋，那麼這一定不是什麼好主意  
    如果實現容易解釋，這有可能是個好主意  
    名稱空間的概念很好，我們要充分利用它

Python 之禪包含了 19 條影響 Python 語言設計的軟體編寫原則，被列入於 PEP 20 中[^2]。Python 之禪以這種簡短的形式概括了 Python 語言的設計原則與規範。

全文的核心思想就是，要去編寫邏輯清晰、易於閱讀與維護的程式碼[^3]。

[^1]: 根據 Python 之禪的作者 Tim Peters [自述](https://softwareengineering.stackexchange.com/questions/148790/is-the-14th-line-of-the-zen-of-python-a-reference-to-dijkstra/148794#148794)，荷蘭人指 Python 的作者 Guido van Rossum。
[^2]: [PEP 20 -- The Zen of Python](https://www.python.org/dev/peps/pep-0020/)
[^3]: 有意思的是，`this` 模組的 [實現](https://hg.python.org/cpython/file/3.5/Lib/this.py) 算是徹頭徹尾地違反了上面的原則。
