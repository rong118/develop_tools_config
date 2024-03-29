## Vim notes

* 命令:
“:q!”：退出 Vim
“:wq”：存盘退出
“:s”：执行替换
“:!”：执行外部命令
“:edit”（一般缩写为 “:e”）：编辑文件
“:w”：写文件
“:r”：读文件
“:help”：查看帮助
使用键 Ctrl-D 和 Tab 来进行命令行补全

* 模式:
正常（normal）模式（也称为普通模式），缺省的编辑模式；如果不加特殊说明，一般提到的命令都直接在正常模式下输入；在任何其他模式中，都可以通过键盘上的 Esc 键回到正常模式。
插入（insert）模式，输入文本时使用；比如在正常模式下键入 i（insert）或 a（append）即可进入插入模式。
可视（visual）模式，用于选定文本块；教程中已经提到可以用键 v（小写）来按字符选定，Vim 里也提供其他不同的选定方法，包括按行和按列块。
命令行（command-line）模式，用于执行较长、较复杂的命令；在正常模式下键入冒号（:）即可进入该模式；使用斜杠（/）和问号（?）开始搜索也算作命令行模式。命令行模式下的命令要输入回车键（Enter）才算完成。

* 跳转:

* 撤销：
Ctrl-r : redo
u : undo

* Move cursor:  
hjkl => left, down, up, right

gg : jump last line
G : jump last line

Jump to first line :0
Jump to last line :$

Jump words : b/w B/W

* 文本修改:
d 加动作来进行删除（dd 删除整行）；D 则相当于 d$，删除到行尾。
c 加动作来进行修改（cc 修改整行）；C 则相当于 c$，删除到行尾然后进入插入模式。
s 相当于 cl，删除一个字符然后进入插入模式；S 相当于 cc，替换整行的内容。
i 在当前字符前面进入插入模式；I 则相当于 ^i，把光标移到行首非空白字符上然后进入插入模式。
a 在当前字符后面进入插入模式；A 相当于 $a，把光标移到行尾然后进入插入模式。
o 在当前行下方插入一个新行，然后在这行进入插入模式；
O 在当前行上方插入一个新行，然后在这行进入插入模式。r 替换光标下的字符；
R 则进入替换模式，每次按键（直到 <Esc>）替换一个字符。
u 撤销最近的一个修改动作；U 撤销当前行上的所有修改。

dw（理解为 delete word）会删除 ame␣，结果是 if (message == "sesopen")
diw（理解为 delete inside word）会删除 sesame，结果是 if (message == " open")
搭配 s（sentence）对句子进行操作——适合西文文本编辑

更快地移动:
我们仍然可以使用 <PageUp> 和 <PageDown> 来翻页，但 Vim 更传统的用法是 <C-B> 和 <C-F>，分别代表 Backward 和 Forward。
除了翻页，Vim 里还能翻半页，有时也许这种方式更方便，需要的键是 <C-U> 和 <C-D>，Up 和 Down。
如果你知道出错位置的行号，那你可以用数字加 G 来跳转到指定行。类似地，你可以用数字加 | 来跳转到指定列。这在调试代码的时候非常有用，尤其适合进行自动化。

* Search:
/
N/n : 重复最近的字符查找操作，反方向

* 多文件：
在终端里进入到目标目录下
使用 vim *.cpp *.h 或 gvim *.cpp *.h 来打开需要编辑的文件
对于第一个文件，使用之前的方法贴入所需的文本
使用 V 进入行选择的可视模式，移动光标选中所需的文本，然后使用 y 复制选中的各行
执行命令 :set autowrite，告诉 Vim 在切换文件时自动存盘
执行命令 :n|normal ggP，切换到下一个文件并执行正常模式命令 ggP，跳转到文件开头并贴入文本
确认修改无误后，键入 :、上箭头和回车，重复执行上面的命令
待 Vim 报错说已经在最后一个文件里，使用 :w 存盘，或 :wq（抑或更快的 ZZ）存盘退出


* 窗口分割：
：vs

* 比较：
vimdiff

* Tabs:
当然，Vim 用户更经常会使用键盘：在已有命令行模式命令前加 tab␣ 可以在新标签页中展示命令的结果，如 :tab help 可以在新标签页中打开帮助，
:tab split 可以在新标签页中打开当前缓冲区:tabs 展示所有标签页的列表
:tabnew 或 :tabedit 可以打开一个空白的新标签页，后面有文件名的话则打开该文件
:tabclose 可以关闭当前标签页（如果标签页里只有一个窗口，使用窗口关闭命令 <C-W>c 应该更快）
:tabnext、gt 或 <C-PageDown> 可以切换到下一个标签页
:tabNext、:tabprevious 、gT 或 <C-PageUp> 可以切换到上一个标签页
:tabfirst 或 :tabrewind 切换到第一个标签页:tablast 切换到最后一个标签页

* 自动完成:
Vim 内置有自动完成功能。最基本的自动完成功能有两种：
基于当前文件文本的自动完成
基于文件系统的自动完成

Ctrl-p / Ctrl-n

* 剪切粘贴：
d/y 
p