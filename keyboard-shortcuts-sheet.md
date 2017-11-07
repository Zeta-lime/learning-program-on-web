# 快捷键大全
---
[toc]
## Windows  快捷键
---
`alt-d`快速定位到地址栏
`windows-e`打开资源管理器
### 任务切换
`alt-tab`快速切换程序
`windows-tab`显示任务视图
### 新建桌面
`windows-ctrl-d`创建新桌面
`windows-ctrl-f4`关闭当前虚拟桌面
`windows-ctrl-左/右`切换虚拟桌面
`windows-左、右、上、下`将当前窗口移动到屏幕左、右侧，移动到顶部还会自动最大化，从顶部拉下来则会还原。
`windows-tab`打开显示任务视图，右键单击程序，或者鼠标拖拽可移动到新的桌面
### 文件夹
`alt-向左键`查看上一个文件夹
`alt-向右键`查看下一个文件夹
`alt-向上键`查看父文件夹
### 显示器
`windows-shift-左、右方向键`把当前窗口在两个显示器间移动

## Windows cmd dos命令
---
>dos命令不区分命令、参数大小写

- `help`命令
help command或者command /?

- `shutdown`关机
-s 关机
-r 重启
-t 延时（单位秒）
-f 强制关机（不提示确定关机，当t设置大于0时，默认强制关机）
-h 休眠
-a 取消关机指令
-c "内容" 关机提示消息
- `ver`显示当前机器上的操作系统版本信息
- `cls`清屏
- `pause`等待用户确认

- `cd`进入目录
`cd` 显示当前路径（相当于linux的pwd）
`cd \`显示当前驱动器的根目录(windows ~不表示用户文件夹 cd ~在Linux才进入用户目录)
`cd .`进入当前路径，实际上什么也不做
`cd ..`进入上级目录

- `dir`查看当前所在目录的文件和文件夹
无参数：查看当前所在目录的文件和文件夹。
/s：查看当前目录已经其所有子目录的文件和文件夹。
/a：查看包括隐含文件的所有文件。
/ah：只显示出隐含文件。
/w：以紧凑方式（一行显示5个文件）显示文件和文件夹。
/p：以分页方式（显示一页之后会自动暂停）显示。
|more：前面那个符号是“\”上面的那个，叫做重定向符号，就是把一个命令的结果输出为另外一个命令的参数。more也是一个命令，dir /w |more 得到的结果和dir /w /p的结果是一样的。

- `tree`显示文件夹树（默认只显示子文件夹，不显示文件、子文件）
-f 显示文件以及子文件
-a 以另一种格式显示

- `md(mkdir)`新建文件夹

- 新建空文件abc
    `cd. > abc`,`copy nul abc`,`type nul abc`（不能使用`cd >abc`,会将当前路径写入abc）
- 向文件中abc写入内容(若文件不存在则创建)
    - `echo hello world > abc`（覆盖原内容）
    - `type a > abc`将a文件内容写入abc并覆盖
    - `ping www.baidu.com >> abc`将命令运行结果追加到文件abc
>输出重定向符 > ,>>
`>`表示覆盖原有内容
`>>`表示在原有内容后追加

- `type`输出文件内容
- `notepad "filename"`使用记事本打开
- `write "filename"`使用写字板打开
- `atom "filename"`使用atom打开文件
- `more`输出时只显示一个屏幕（一般和管道符“|”搭配用来分屏显示一个大的文本文件内容。）
    - 语法

        command | more [/c] [/p] [/s] [/tn] [+n]

        more [[/c] [/p] [/s] [/tn] [+n]] < [Drive:][?Path} FileName

        more [/c] [/p] [/s] [/tn] [+n] [files]

    - 命令参数

        <dt>[drive:][path] filename</dt>

        指定要显示的文件。

        <dt>command</dt>

        指定要显示其输出的命令。

        <dt>/c</dt>

        显示页面前清除屏幕。

        <dt>/p</dt>

        扩展换页符。

        <dt>/s</dt>

        将多个空白行更改为一个空白行。

        <dt>/tn</dt>

        更改由 n 指定的空格数的制表符。

        <dt>+n</dt>

        显示由 n 指定的行开始的第一个文件。

        <dt>files</dt>

        指定要显示的文件列表。用空格分隔文件名。

        <dt>/?</dt>

        在命令提示符显示帮助。
    - 命令注释

        *   在故障恢复控制台中使用 more

            more 命令具有多个参数并可通过故障恢复控制台使用。

        *   使用 more 子命令

            以下命令在 more 提示 (`-- More --`) 下接受。

            | 键 | 操作 |
            |---|---|
            | SPACEBAR | 显示下一页 |
            | Enter | 显示下一行 |
            | F | 显示下一个文件 |
            | q | 退出 |
            | ? | 显示可用命令 |
            | = | 显示行号 |
            | P n | 显示下面的 n 行。 |
            | S n | 跳过下面的 n 行。 |

        *   数据源

            当使用重定向字符 (<) 时，必须指定文件名作为来源。在使用管道 (|) 时，可以使用诸如 dir、sort 和 type 之类的命令。

    - 命令范例

        要在屏幕上查看名为 Clients.new 的文件，请键入以下两个命令中的任意一个命令：

        more < clients.new

        type clients.new | more

        more 命令显示来自 Clients.new 的第一屏信息，然后显示以下提示：

        `-- More --`

        然后可以按 SPACEBAR 查看下一屏信息。

        要在显示文件 Clients.new 之前清除屏幕并删除所有附加空白行，请键入以下任意一个命令：

        more /c /s < clients.new

        type clients.new | more /c /s

        more 命令显示来自 Clients.new 的第一屏信息，然后显示以下提示：

        `-- More --`

        如果每次显示文件的一行，请按 ENTER 键。

        要显示下一页，请按 SPACEBAR 键。

        要显示命令行上列出的下一个文件，请键入 f。

        要退出 more，请键入 q。

        按照如下示例将命令添加到 more 提示中：

        `-- More [Options:psfq=<space><ret>] --`

        要显示当前行号，请键入 =。如此例中所示，当前行号被添加到 more 提示中：

        `-- More [Line: 24} --`

        要显示特定数目的行，请键入 p。more 将会提示输入要显示的行数（如下）：

        `-- More -- Lines:`

        键入要显示的行数然后按 ENTER 键。more 显示指定的行数。

        要跳过指定的行数，请键入 s。more 提示要跳过的行数（如下）：

        `-- More -- Lines:`

        键入要跳过的行数，然后按 ENTER 键。more 跳过指定的行数并显示下一屏信息。
- `move`移动文件、文件夹到指定路径
- `copy`复制文件、文件夹到指定路径
- `ren`重命名文件、文件夹
- `del`删除文件
- `rd`删除文件夹
    rmdir [/s] [/q] [drive:]path
    rd [/S] [/Q] [drive:]path
    无参数  只能删除空文件夹
    /s      除目录本身外，还将删除指定目录下的所有子目录和
            文件。用于删除目录树。

    /q      安静模式，带 /s 删除目录树时不要求确认
>使用通配符*来同时操作多个文件（或空格间隔多个文件）

- `echo`控制批处理命令在执行时是否显示命令行自身
    - `echo`显示echo设置状态
    - `echo on(off)`设置echo开关
    - `echo.`相当于一个换行符
    - 显示变量
    如：
    set name=world
    echo hello %name%

- `clip`将命令行工具的输出重定向到 Windows 剪贴板。这个文本输出可以被粘贴到其他程序中。
    dir | clip          将一份当前目录列表的副本放入 windows 剪贴板。
    clip < readme.txt   将 readme.txt 的一份文本放入 windows 剪贴板。
>管道符（|）的作用是将符号前的进程输出，当做符号后进程的输入。
例如：
有两条命令，“dir /s /b /a”和“ find ".txt"”，第一条显示当前文件夹中的所有文件、文件夹，第二条是查找含有字符“.txt”的字符串。
两条命令用管道符（|）连接就可以“查找当前文件夹中含有.txt的所有文件、文件夹”。
代码如下:
`dir /s /b /a | find ".txt"``
将当前日期放在剪贴板中。
复制代码 代码如下:
`echo %date:~,10%|clip`





- 使用`set`显示当前环境中的变量
>DOS批处理中的变量,分为两类,分别为"系统变量"和"自定义变量",系统变量又分为预定义和可以设置的两种

    ***预定义变量***
    下面是些已经被系统预定义好可以直接使用的变量：不会出现在 SET 显示的变量列表中
    %CD% - 扩展到当前目录字符串。
    %DATE% - 用跟 DATE 命令同样的格式扩展到当前日期。
    %TIME% - 用跟 TIME 命令同样的格式扩展到当前时间。
    %RANDOM% - 扩展到 0 和 32767 之间的任意十进制数字。
    %ERRORLEVEL% - 扩展到当前 ERRORLEVEL 数值。
    %CMDEXTVERSION% - 扩展到当前命令处理器扩展名版本号。
    %CMDCMDLINE% - 扩展到调用命令处理器的原始命令行。
    %0 bat的完整路径名如"C:\Windows\system32\xxx.bat"
    %1 bat参数1依次类推%2参数2...
    %path% - 当前的环境变量。以分号隔开的路径列表，路径可包含空格，可以以'\'结尾, 可以以双引号包围之。

    ***扩展变量***

    **与%i相关的变量（bat参数或者for循环的%i)**
    假设文件为C:\Documents and Settings\jinsun\桌面\ParseSinglePkgs.bat
    %0        C:\Documents and Settings\jinsun\桌面\ParseSinglePkgs.bat
    %~dp0 C:\Documents and Settings\jinsun\桌面\
    %cd%   C:\Documents and Settings\jinsun\桌面
    %~nx0   ParseSinglePkgs.bat
    %~n0     ParseSinglePkgs
    %~x0     .bat

    **与%VAR%相关的变量**

    %VAR:str1=str2%   会将VAR中的str1替换为str2(str2如果为空则可以达到删除的效果,str1前可以加*，变量`%ABC:*B=%`是`%C%`)
    %VAR:~2% 会提取VAR 变量的前两个字符
    %VAR:~0,-2% 会提取VAR 变量的所有字符，除了最后两个
    %VAR:~-2% 会提取VAR 变量的最后两个字符

    ***自定义变量（使用set）***
    - set指令 功能一览
    [设置变量]
    格式：set 变量名=变量值
    详细：被设定的变量以%变量名%引用
    [取消变量]
    格式：set 变量名=
    详细：取消后的变量若被引用%变量名%将为空
    [展示变量]
    格式：set 变量名
    详细：展示以变量名开头的所有变量的值
    [列出所有可用的变量]
    格式：set
    [计算表达式]
    格式：set  /a 表达式
    示例：set /a 1+2*3  
    输出：7
    [设置变量为表达式计算后的值]
    格式：set  /a a=表达式
    示例：
        set /a a=1+2
        echo %a%
    输出:3
    对比：
        set a=1+2
        echo %a%
    输出：1+3
    [设置变量为用户输入的值]
        set /p a=输入一个值
    输出：输入一个值
        echo %a%
    输出：<显示用户输入的值>
    **注意：**
    set不能用在复合语句里面比如`if 1==1 set a=2或者for %%i in (a) do set a=2`

- rem 命令
注释命令，类似于在C语言中的/*--------*/，它并不会被执行，只是起一个注释的作用，便于别人阅读
和你自己日后修改。
:: 也具有rem的功能
语法：Rem “Message”

## Atom常用快捷键(Windows)
---
- 文件
`ctrl-n`新建文件
`ctrl-s`保存
`ctrl-shift-s`另存为
`ctrl-o`打开文件
`ctrl-shift-o`打开文件夹
`ctrl-t (ctrl-p)`	打开project中的文件
`ctrl-b`	打开buff中的文件（buff指的是当前在编辑面板打开的文件）
- 视图
>视图中绿色高亮的文件、行号表示新加入git，黄色部分表示修改但还没有commit to git，灰色表示ignore，蓝色表示重命名，红色表示git已经移除
参见`ctrl-shift-p styleguide`

`ctrl-\`打开、关闭project面板
`alt-\`跳转到project文件tree中操作
`ctrl-alt-[或]`展开、折叠当前行
`ctrl-alt-shift-[或]`展、折叠全部
`ctrl-k, left/right/up/down`在相应方向上分割面板
`ctrl-k, ctrl-left/right/up/down`	光标跳到相应方向的面板上
`ctrl-shift-\`在目录树中显示当前编辑的文件位置
- 跳转
`home`、`end`跳到句首、句尾
`ctrl-home`、`ctrl-end`跳到全文首部、尾部
`ctrl-方向键left`、`ctrl-方向键right`调到词首、词尾
`ctrl-r`打开导航
`ctrl-m`前后括号之间跳转
`ctrl-g`跳转到指定行列
- 选取
`ctrl-l`选取一行
`shift-方向键左、右`向左向右选取单个字母
`ctrl-shift-方向键左、右`以词为单位向左向右选取
`shift-up` 向上选择
`shift-down` 向下选择
`shift-home\end`向左、右选取直到句首、尾
`shift-pageup\pagedown`以页面为单位向上向下选取
`ctrl-shift-home\end`向前、后选取直到文首、尾
- 编辑
`ctrl-shift-c`复制当前文件的路径
`ctrl-/`对代码进行注释
`ctrl-shift-d`复制一行
`ctrl-shift-k`删除一行
`ctrl-[或]`缩进
`ctrl-j` 将下一行与当前行合并
`ctrl-k ctrl-l`使当前字符小写
`ctrl-k ctrl-u`使当前字符大写
`ctrl-up\down`代码上移、下移
- 多行编辑
`ctrl`+鼠标
`ctrl-d`选取文档中和当前单词相同的下一处
`alt-ctrl-up\down`在当前光标的上面和下面增加多个光标
`alt-F3`选择文档中与当前光标所在单词一样的所有单词，并进入多行编辑模式
- 查找
`ctrl-f`	在buff中查找
`ctrl-shift-f`	在project中查找
>查找右上角四个按键分别是正则表达式、大小写匹配、只在选中的部分中查找、作为单个词查找（在其他词中出现的情况不算在内）

- 命令行
`ctrl-shift-p`打开命令行
atom-terminal:
    - Open terminal on current file's directory with ctrl-shift-t.
    - Open a terminal in the project's root directory with alt-shift-t.

## Jupyter Notebook 快捷键
---
Python | May 4, 2017 | [python](http://kuanghy.github.io/tags/#python) [jupyter](http://kuanghy.github.io/tags/#jupyter)

[Jupyter Notebook](http://jupyter.org/) 是一个交互式笔记本程序, 其有丰富的快捷键来便捷的完成工作。Notebook 有两种键盘输入模式。即命令模式和编辑模式，这与 [Vim](http://www.vim.org/)有些类似。在编辑模式下，可以往单元中键入代码或文本，此时单元格被绿色的框线包围，且命令模式下的快捷键不生效。在命令模式下，可以用快捷键命令运行单元格，移动单元格，切换单元格编辑状态等等，此时的单元格被灰色的框线包围，且编辑模式下的快捷键不生效。

从命令模式进入编辑模式需按 `Enter` 键，从编辑模式切换到命令模式需按 `Esc` 键。

以下两表分别是对命令和编辑两种模式下快捷键的简单说明：

### 命令模式快捷键（按 Esc 键开启）:

| 快捷键 | 作用 | 说明 |
| --- | --- | --- |
| Enter | 转入编辑模式 |   |
| Shift-Enter | 运行本单元，选中下个单元 | 新单元默认为命令模式 |
| Ctrl-Enter | 运行本单元 |   |
| Alt-Enter | 运行本单元，在其下插入新单元 | 新单元默认为编辑模式 |
| Y | 单元转入代码状态 |   |
| M | 单元转入 markdown 状态 |   |
| R | 单元转入 raw 状态 |   |
| 1 | 设定 1 级标题 | 仅在 markdown 状态下时建议使用标题相关快捷键，如果单元处于其他状态，则会强制切换到 markdown 状态 |
| 2 | 设定 2 级标题 |   |
| 3 | 设定 3 级标题 |   |
| 4 | 设定 4 级标题 |   |
| 5 | 设定 5 级标题 |   |
| 6 | 设定 6 级标题 |   |
| Up | 选中上方单元 |   |
| K | 选中上方单元 |   |
| Down | 选中下方单元 |   |
| J | 选中下方单元 |   |
| Shift-K | 连续选择上方单元 |   |
| Shift-J | 连续选择下方单元 |   |
| A | 在上方插入新单元 |   |
| B | 在下方插入新单元 |   |
| X | 剪切选中的单元 |   |
| C | 复制选中的单元 |   |
| Shift-V | 粘贴到上方单元 |   |
| V | 粘贴到下方单元 |   |
| Z | 恢复删除的最后一个单元 |   |
| D,D | 删除选中的单元 | 连续按两个 D 键 |
| Shift-M | 合并选中的单元 |   |
| Ctrl-S | 保存当前 NoteBook |   |
| S | 保存当前 NoteBook |   |
| L | 开关行号 | 编辑框的行号是可以开启和关闭的 |
| O | 转换输出 |   |
| Shift-O | 转换输出滚动 |   |
| Esc | 关闭页面 |   |
| Q | 关闭页面 |   |
| H | 显示快捷键帮助 |   |
| I,I | 中断 NoteBook 内核 |   |
| 0,0 | 重启 NoteBook 内核 |   |
| Shift | 忽略 |   |
| Shift-Space | 向上滚动 |   |
| Space | 向下滚动 |   |

### 编辑模式快捷键（ 按 Enter 键启动）:

| 快捷键 | 作用 | 说明 |
| --- | --- | --- |
| Tab | 代码补全或缩进 |   |
| Shift-Tab | 提示 | 输出帮助信息，部分函数、类、方法等会显示其定义原型，如果在其后加 `?` 再运行会显示更加详细的帮助 |
| Ctrl-] | 缩进 | 向右缩进 |
| Ctrl-[ | 解除缩进 | 向左缩进 |
| Ctrl-A | 全选 |   |
| Ctrl-Z | 撤销 |   |
| Ctrl-Shift-Z | 重做 |   |
| Ctrl-Y | 重做 |   |
| Ctrl-Home | 跳到单元开头 |   |
| Ctrl-Up | 跳到单元开头 |   |
| Ctrl-End | 跳到单元末尾 |   |
| Ctrl-Down | 跳到单元末尾 |   |
| Ctrl-Left | 跳到左边一个字首 |   |
| Ctrl-Right | 跳到右边一个字首 |   |
| Ctrl-Backspace | 删除前面一个字 |   |
| Ctrl-Delete | 删除后面一个字 |   |
| Esc | 切换到命令模式 |   |
| Ctrl-M | 切换到命令模式 |   |
| Shift-Enter | 运行本单元，选中下一单元 | 新单元默认为命令模式 |
| Ctrl-Enter | 运行本单元 |   |
| Alt-Enter | 运行本单元，在下面插入一单元 | 新单元默认为编辑模式 |
| Ctrl-Shift– | 分割单元 | 按光标所在行进行分割 |
| Ctrl-Shift-Subtract | 分割单元 |   |
| Ctrl-S | 保存当前 NoteBook |   |
| Shift | 忽略 |   |
| Up | 光标上移或转入上一单元 |   |
| Down | 光标下移或转入下一单元 |   |
| Ctrl-/ | 注释整行/撤销注释 | 仅代码状态有效 |

**注：** 如果快捷键被系统中的其它应用占用，则可能会失效
