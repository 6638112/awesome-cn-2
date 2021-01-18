<div class="github-widget" data-repo="mhinz/vim-galore"></div>
<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script><ins class="adsbygoogle" style="display:block" data-ad-client="ca-pub-6890694312814945" data-ad-slot="5473692530" data-ad-format="auto"  data-full-width-responsive="true"></ins><script>(adsbygoogle = window.adsbygoogle || []).push({});</script>
<div align='center'>
  <br /><br /><br />
  <img src='https://raw.githubusercontent.com/mhinz/vim-galore/master/static/images/logo-vim-galore.png' alt='vim-galore logo' />
  <br /><br /><br /><br />
  <div>
    <a href='https://github.com/wsdjeg/vim-galore-zh_cn'>中文</a>|
    <a href='http://postd.cc/?s=vim-galore'>日文</a>|
    <a href='https://github.com/lsrdg/vim-galore'>葡萄牙语</a>|
    <a href='http://givi.olnd.ru/vim-galore/vim-galore-ru.html'>俄语</a>|
    <a href='https://github.com/kyoz/vim-galore-vi'>越南文</a>
    <div>
      <br />
      <sub>根据<a href='https://creativecommons.org/licenses/by-sa/4.0'>CC BY-SA 4.0</a>许可<a/>.</a></sub>
    </div>
  </div>
  <br /><br />
</div>










- [:global and :vglobal](#global-and-vglobal) -在所有匹配的行上执行命令.
- [:normal and :execute](#normal-and-execute) -脚本梦想团队.
- [:redir and execute()](#redir-and-execute) -捕获命令输出.











### [List of colorschemes](https://github.com/mhinz/vim-galore/blob/master/PLUGINS.md#colorschemes-1)

### [List of plugins](https://github.com/mhinz/vim-galore/blob/master/PLUGINS.md)

<br>

## Intro

## What is Vim?

[Vim](http://www.vim.org) 是一个文本编辑器，有很多祖先
回到 [qed](https://en.wikipedia.org/wiki/QED_(text_editor) ）.  [布拉姆
Moolenaar]（https://en.wikipedia.org/wiki/Bram_Moolenaar）于1991年发布.

该项目在线托管在 [vim.org](http://www.vim.org/index.php).

获取Vim：使用您喜欢的软件包管理器或访问[下载
页面]（http://www.vim.org/download.php）从vim.org.

讨论和用户问题最好在
[vim_use](https://groups.google.com/forum/#!forum/vim_use) 邮件列表或使用
IRC（[Freenode](https://freenode.net)) in the `#vim` channel.

开发发生在 [GitHub](https://github.com/vim/vim)，关于
[vim_dev](https://groups.google.com/forum/#!forum/vim_dev) 邮件列表.

Read [Why, oh WHY, do those #?@! nutheads use
vi？]（http://www.viemu.com/a-why-vi-vim.html）了解有关以下内容的常见误解
Vim解释.

## The Vim Philosophy

 Vim遵循模式编辑理念. 这意味着它提供
多种模式，按键的含义会根据模式而变化. 您
在_normal模式_中导航文件，在_insert模式_中插入文本，然后选择
_visual模式_中的行，您可以访问_命令行模式_中的命令，依此类推.
乍一看这听起来很复杂，但具有巨大的优势：您没有
大部分时间一次按住几个键来折断手指
只需一个接一个地按它们. 任务越常见，键越少
是必需的.

与模态编辑配合使用的一个相关概念是运算符和运动.
_操作员_开始执行特定操作，例如更改，删除或选择文本.
之后，您可以使用_motion_指定要操作的文本区域.
要更改括号之间的所有内容，请使用`ci（`（阅读_change inner
括弧_）. 要删除整个文本段落，请使用`dap`（请阅读_delete
在段落_周围）.

如果看到Vim高级用户正在工作，您会注意到他们说的是
 Vim的语言以及钢琴家会处理他们的乐器. 复杂
仅需几次按键即可完成操作. 他们甚至都不考虑
不再是 [muscle memory](https://en.wikipedia.org/wiki/Muscle_memory) 拿
已经结束了. 这降低了[认知
加载]（https://en.wikipedia.org/wiki/Cognitive_load）并有助于专注于
实际任务.

## First steps

Vim随附了一个交互式教程，该教程教授最基本的知识.
您需要了解的事情. 您可以从外壳启动它：

```
$ vimtutor
```

不要因看起来无聊而烦恼，并通过练习来进行工作. 
您之前使用的编辑器或IDE可能都是非模式的，因此
切换模式起初看起来很尴尬，但是使用Vim越多，
它成为了 [muscle memory](https://en.wikipedia.org/wiki/Muscle_memory).

Vim狂奔 [Stevie](https://en.wikipedia.org/wiki/Stevie_(text_editor)）， 一种
[vi](https://en.wikipedia.org/wiki/Vi) 克隆，并支持两种操作模式：
 “兼容”和“不兼容”. 在兼容模式下使用Vim意味着使用vi
默认为所有选项，而不是Vim默认. 只要你没有创造
用户vimrc或以`vim -N`启动Vim，假定为兼容模式！ 别
在兼容模式下使用Vim. 只是不要.

下一步：

1.创建自己 [vimrc](#minimal-vimrc).
2.吃一些 [cheatsheets](#cheatsheets) 准备第一周.
3.通读 [basics](#basics-1) 部分以了解甚至有什么可能.
 4.按需学习！ 您永远不会完成学习Vim. 如果遇到任何
   问题，只需在互联网上查找即可. 您的问题已经解决.
   Vim随附了许多出色的文档，并且必须知道如何导航：
   [Getting help offline](#getting-help-offline).
5.看看 [additional resources](#additional-resources).

最后一条建议：在开始添加所有Vim之前，请学习如何正确使用Vim.
各种炒作 [plugins](#managing-plugins) 仅实现了
Vim已经本地支持.

## Minimal vimrc

用户vimrc可以放入`〜/ .vimrc`或为了更好的分离
进入`〜/ .vim / vimrc`. 后者使放置整个配置变得容易
在版本控制下并将其上传到GitHub.

您会在网上发现许多“最小vimrcs”，也许我的版本不如
虽然应该是最小的，但是它提供了我认为不错的一组理智的设置
对入门很有用.

最终，您还是必须阅读所有提到的设置并决定
为自己.  :-)

所以这里是： [minimal-vimrc](https://github.com/mhinz/vim-galore/blob/master/static/minimal-vimrc.vim)

如果您有兴趣，这里是
[my vimrc](https://github.com/mhinz/dotfiles/blob/master/.vim/vimrc).

**技巧**：大多数插件作者都会维护多个插件，并发布他们的插件
GitHub上的vimrc（通常在名为“ vim-config”或“ dotfiles”的存储库中），因此
每当您找到喜欢的插件时，请查看其维护者的GitHub页面，然后
浏览存储库.

## What kind of Vim am I running?

查看`：version`将为您提供所有您需要了解的信息
当前正在运行的Vim二进制文件是如何编译的.

第一行告诉您二进制文件的编译时间和版本，例如7.4.
接下来的一行之一声明“包含的补丁程序：1-1051”，即补丁程序
水平. 因此，您的确切Vim版本是7.4.1051.

另一行指出类似“没有GUI的微型版本”或“巨大版本”之类的内容
与GUI`. 显而易见的信息是您的Vim是否包含GUI
支持，例如从shell启动`gvim`或从Vim运行`：gui`
在终端仿真器中. 其他重要信息是“ Tiny”和
巨大 Vim区分了称为“小”，“小”，“正常”，
“ big”和“ huge”，都启用了功能的不同子集.

`：version`输出的大部分内容由功能列表本身使用.
`+ clipboard`表示剪贴板功能已被编译，`-clipboard`表示它已被编译
没有被编译.

一些Vim功能需要编译才能起作用. 例如`：prof`
工作中，您需要一个具有强大功能集的Vim，因为该功能可以启用
+配置文件功能.

如果不是这种情况，并且从软件包管理器中安装了Vim，请确保
安装名为`vim-x`，`vim-x11`，`vim-gtk`，`vim-gnome`的软件包或
类似，因为这些软件包通常带有巨大的功能集.

您还可以通过编程方式测试版本或功能：

```vim
“如果至少在启用了+ profile的情况下运行Vim 7.4.42，请执行一些操作.
如果（v：version&gt; 704 || v：version == 704 &amp;&amp; has（&#39;patch42&#39;））&amp;&amp; has（&#39;profile&#39;）
  “ 做东西
endif
```

Help:

```
：h：版本
：h功能列表
：h +功能列表
：h具有补丁
```

## Cheatsheets

- http://people.csail.mit.edu/vgod/vim/vim-cheat-sheet-en.png
- https://cdn.shopify.com/s/files/1/0165/4168/files/preview.png
- http://michael.peopleofhonoronly.com/vim/vim_cheat_sheet_for_programmers_screen.png
- http://www.rosipov.com/images/posts/vim-movement-commands-cheatsheet.png

或者从Vim内部快速打开备忘单： [vim-cheat40](https://github.com/lifepillar/vim-cheat40).

## Basics

## Buffers, windows, tabs

 Vim是文本编辑器. 每次显示文字时，文字都是
 **缓冲**. 每个文件将在其自己的缓冲区中打开. 插件显示内容
他们自己的缓冲区等

缓冲区具有许多属性，例如，其中包含的文本是否可修改，
或者它是否与文件关联，因此需要同步到
磁盘上保存.

 ** Windows **是视口_onto_缓冲区. 如果要查看几个文件，请访问
在同一时间甚至同一文件的不同位置，都可以使用Windows.

而且，请不要称它们为_splits_. 您可以将一个窗口一分为二，但是
不会使它们_splits_.

窗口可以垂直或水平拆分，高度和宽度
现有窗口也可以更改. 因此，您可以使用任何窗口
您喜欢的布局.

标签页**（或仅标签页）是Windows的集合. 因此，如果您想
使用多个窗口布局，使用标签.

简而言之，如果您不带参数启动Vim，您将拥有一个
标签页，其中包含一个显示一个缓冲区的窗口.

顺便说一下，缓冲区列表是全局的，您可以从任何位置访问任何缓冲区
tab.

## Active, loaded, listed, named buffers

像`vim file1`这样运行Vim. 文件的内容将被加载到缓冲区中.
您现在已经**已加载缓冲区**. 缓冲区的内容仅同步
如果将其保存在Vim中，则将其写入磁盘（写回文件）.

由于缓冲区也显示在窗口中，因此它也是“活动缓冲区” **. 现在
如果您通过`：e file2`加载另一个文件，`file1`将成为**隐藏缓冲区**
和`file2`是活动的.

两个缓冲区也被“列出”，因此它们将在输出中列出.
 `：ls`. 插件缓冲区或帮助缓冲区通常被标记为未列出，因为
它们不是您通常使用文本编辑器编辑的常规文件. 列出并
未列出的缓冲区可以通过`：ls！`显示.

**未命名的缓冲区**，也是插件经常使用的缓冲区，它们没有
关联的文件名. 例如：：enew将创建一个未命名的暂存缓冲区. 加
一些文本，然后通过`：w / tmp / foo`将其写入磁盘，它将被命名为
buffer.

## Argument list

The [global buffer list](#buffers-windows-tabs) 是Vim的东西. 在此之前，
vi，以前只有参数列表，Vim中也有.

在shell命令行上给Vim的每个文件名都会被记住.
参数列表. 可以有多个参数列表：默认情况下，所有参数
被放入全局参数列表，但是您可以使用：argarg来创建一个
窗口本地的新参数列表.

用`：args`列出当前参数. 从参数在文件之间切换
与以下列表：:下一个`，`：上一个`，`：第一个`，`：最后`和朋友. 用
`：argadd`，`：argdelete`或`：args`以及文件列表.

如果您更喜欢使用缓冲区或参数列表来处理文件，则为
随便吃我的印象是大多数人都使用缓冲区列表
exclusively.

但是，参数列表有一个巨大的用例：批处理
通过`：argdo`！ 一个简单的重构示例：

```vim
：args ** / *.[ch]
 ：argdo％s / foo / bar / ge | 更新
```

这将在所有C源文件和头文件中将所有出现的“ foo”替换为“ bar”
从当前目录和下面.

帮助：`：h arguments-list`

## Mappings

您可以使用：map系列命令来定义自己的映射. 每
该系列的命令定义了一组特定模式的映射. 技术上
 Vim带有多达12种模式，其中6种可以被映射. 另外，一些
命令一次作用于多种模式.

 | 递归非递归| 取消映射模式|
|-----------|---------------|-----------|----------------------------------|
 |  `：map` |  `：noremap` |  `：unmap` | 普通，可视，待处理操作员|
 |  `：nmap` |  `：nnoremap` |  `：nunmap` | 正常
 |  `：xmap` |  `：xnoremap` |  `：xunmap` | 视觉|
 |  `：cmap` |  `：cnoremap` |  `：cunmap` | 命令行|
 |  `：omap` |  `：onoremap` |  `：ounmap` | 待处理的运营商|
 |  `：imap` |  `：inoremap` |  `：iunmap` | 插入|

E.g. this defines the mapping for normal mode only:

```vim
 ：nmap<space>  ：echo“ foo”<cr>
```

使用`：nunmap再次取消映射<space> `.

有关更多但不常见的模式（或它们的组合），请参见`：h
map-modes`.

到现在为止还挺好. 只有一个问题可能使您非常困惑
初学者：`：nmap`是_recursive_！ 也就是说，右侧需要其他
考虑到映射.

因此，您定义了一个仅回显“ Foo”的映射：

```vim
：nmap b：echo“ Foo”<cr>
```

但是，如果要将默认行为“ b”（返回一个单词）映射到
另一个钥匙？

```vim
：nmap ab
```

<kbd>如果</kbd>碰到，我们预计光标回去一个字，而是
在命令行中打印“ Foo”！ 因为右边的b是
已经映射到另一个动作，即`：echo“ Foo”<cr>  `.

解决此问题的正确方法是使用_non-recursive_映射
instead:

```vim
：nnoremap ab
```

经验法则：始终使用非递归映射，除非实际上是递归
desired.

通过不显示右侧来查找映射. 例如：: nmap`显示所有
普通映射和`：nmap<leader>  `显示所有以开头的法线映射
地图负责人.

如果要禁用标准映射，请将它们映射到特殊的`<nop>  `
字符，例如`：noremap<left><nop>  `.

Help:

    ：h键符号
    ：h映射
    ：小时05.3

## Mapleader

mapleader只是一个占位符，无法与自定义映射和
默认情况下设置为“ \”.

```vim
 nnoremap<leader>  h：helpgrep<space>
```

该映射由\ h触发. 如果要使用`<space>  h`代替：

```vim
让mapleader =&#39;&#39;
 nnoremap<leader>  h：helpgrep<space>
```

此外，还有<localleader> `是`的本地对应项<leader> `
并且应该用于缓冲区本地的映射，例如.
特定于文件类型的插件. 它也默认为`\`.

 **注意**：在映射之前设置地图领导者！ 中的所有领导者映射
效果已经存在，不会仅仅因为mapleader被更改而改变.  `：nmap
<leader>`将显示所有已解决的mapleader的普通模式领导者映射
已经，所以用它来仔细检查您的映射.

有关更多信息，请参见`：h mapleader`和`：h maplocalleader`.

## Registers

寄存器是保存文本的插槽. 将文本复制到寄存器中称为
**拉动**并从寄存器中提取文本称为**粘贴**.

Vim提供以下寄存器：

 | 类型性格填满？  | 只读？  | 包含文字？  |
|---------------------|------------------------|------------|-----------|---------------------|
 | 未命名 `“`| vim | [] |最后拉动或删除.（`d`，`c`，`s`，`x`，`y`）|
 | 编号从0到9  vim |  [] | 寄存器0：最后一次拉动. 寄存器1：最后删除. 寄存器2：倒数第二次删除. 等等. 将寄存器`1`-`9`视为只读 [queue](https://en.wikipedia.org/wiki/Queue_(abstract_data_type) ）的9个元素.  |
 | 小删除|  `-` |  vim |  [] | 上次删除少于一行.  |
 | 命名|  `a`到`z`，`A`到`Z` | 用户|  [] | 如果您要注册`a`，请替换其文本. 如果您要注册`A`，则将其附加到寄存器`a`中.  |
 | 只读|  `：`，`.`，`％`|  vim |  [x] |  `：`：最后一个命令，`.`：最后插入的文本，`％`：当前文件名.  |
| Alternate buffer    | `#`                    | vim        | [ ]       | Most of the time the previously visited buffer of the current window. See `:h alternate-file` |
 | 表达|  `=`| 用户|  [] | 评估被拉动的VimL表达. 例如，在插入模式下执行此操作：<c-r>  = 5 + 5<cr>  `和“ 10”将插入缓冲区.  |
 | 选择|  `+`，`*`|  vim |  [] |  *和+是 [clipboard](#clipboard) 寄存器.  |
 | 下降|  `〜`|  vim |  [x] | 从上次拖放开始.  |
 | 黑洞|  `_` |  vim |  [] | 如果您不希望其他任何寄存器隐式受影响. 例如，“ _ dd”删除当前行，而不影响寄存器“”，“ 1”，“ +”，“ *”.  |
 | 最后搜索模式|  `/`|  vim |  [] | 最后一个与`/`，`？`，`：global`等一起使用的模式.

每个非只读寄存器可以由用户设置：

```vim
：let @ / =&#39;注册&#39;
```

之后， <kbd>n</kbd>将跳到下一个出现的“寄存器”.

隐式填充寄存器时会有很多例外，因此请确保
读取`：h寄存器&#39;.

用`y`抽出并用&#39;p` /`P`粘贴，但要注意Vim可以区分
按字符和按行的视觉选择. 参见`：h linewise`.

**示例：逐行**

`yy`（或仅`Y`）拉动当前行，将光标移到其他位置，使用
“ p”粘贴到当前行“ P”下方，然后粘贴到其上方.

**示例：charwise **

用&#39;0yw&#39;提取第一个单词，移到其他位置，将光标粘贴到
当前行带有p，光标之前带有p.

**示例：寄存器的显式命名**

`“ aY`将当前行拖入寄存器`a`.移至另一行.
将当前行附加到寄存器a中.

我建议稍微玩弄所有这些寄存器并不断检查
`：reg`，因此您可以看到实际发生的情况.

**有趣的事实**：在Emacs中，“ yanking”代表粘贴（或_reinserting以前
杀死text_）不能复制.

## Ranges

范围很容易理解，但是许多Vimmer不知道它们的范围.
充分发挥潜力.

-许多命令采用范围.
-地址表示某行.
-范围可以是单个地址，也可以是由其中一个分隔的一对地址
  `，`或`;`.
-范围告诉命令要执行的行.
 -默认情况下，大多数命令仅在当前行上起作用. 值得注意的例外是
  在所有行上起作用的`：write`和`：global`.

范围的用法非常直观，因此这里有一些示例（使用`：d`
作为`：delete`的缩写形式）：

| Command | Lines acted on |
|---------|----------------|
 |  `：d` | 当前行.  |
 |  `：.d` | 当前行.  |
 |  `：1d` | 第一行.  |
 |  `：$ d` | 最后一行.  |
 |  `：1，$ d` | 所有行.  |
 |  `：％d` | 所有行（“ 1，$`的语法糖”）.  |
 |  `：.，5d` | 当前行到第5行.
 |  `：，5d` | 也是当前行到行5.
 |  `：，+ 3d` | 当前行和接下来的3行.  |
 |  `：1，+ 3d` | 第一行到当前行+ 3.
 |  `：，-3d` | 当前行和最后3行.  （Vim会提示您，因为这是反向范围.）
 |  `：3，&#39;xdelete` | 第3行到标有的行 [mark](#marks)  X.  |
 |  `：/ ^ foo /，$ delete` | 从以“ foo”开始的下一行到结尾.  |
 |  `：/ ^ foo / + 1，$ delete` | 从以“ foo”开头的行之后的行到结尾.  |

请注意，可以使用&#39;;;代替&#39;，`来作为分隔符. 区别在于
在from，to的情况下，_to_相对于当前行，但是当
使用`from; to`，_to_相对于_from_的地址！ 假设你是
在第5行，`：1，+ 1d`将删除第1至6行，而`：1; + 1d`仅
删除第1行和第2行.

 “ /”地址之前可以是另一个地址. 这使您可以_stack_
模式，例如：

```vim
:/foo//bar//quux/d
```

这将删除第一行之后的包含“ quux”的第一行
在第一行之后包含“ bar”，在当前行之后包含“ foo”.

有时，Vim会自动在命令行前添加一个范围. 例如开始一个
用“ V”选择视线，选择一些线并键入“：”. 命令行
将以范围&#39;&#39;&lt;，&#39;&gt;`填充，这意味着以下命令将
使用先前选择的行作为范围.  （这也是为什么您有时
参见`：vnoremap foo这样的映射：<c-u> 命令`. 在这里<c-u> `用于删除
范围，因为Vim给命令指定范围时会抛出错误
不支持.）

另一个例子是在正常模式下使用“ !!”. 这将填充
带有`：.！`的命令行. 如果后面有外部程序，则该程序
输出将替换当前行. 所以你可以取代目前
通过使用`：？^ $？+ 1，/ ^ $ /-1！ls`输出ls. 看中！

Help:

```
：h cmdline-范围
：h 10.3
```

## Marks

您可以使用标记来记住文件中的位置，即行号和列.

 | 商标| 设置者： 用法
|-------|----------|-------|
 |  `a`-`z` | 用户| 本地文件，因此仅在一个文件内有效. 跳转到小写标记表示跳转到当前文件中.  |
 |  `A`-`Z` | 用户| 全局，因此在文件之间有效. 也称为_file标记_. 跳到文件标记可能会切换到另一个缓冲区.  |
 |  `0`-`9` |  viminfo |  “ 0”是最后写入viminfo文件的位置. 实际上，这意味着最后一个Vim进程何时结束.  1是第二个Vim进程结束时的位置，依此类推.  |

将&#39;/ g&#39;或&#39;/ g&#39;标记在前面.

使用“ mm”记下带有“ m”标记的当前位置. 移动文件
然后通过`&#39;m`（第一个非空白）或``m&#39;（精确列）返回.
如果您告诉viminfo，退出Vim后会记住小写标记
文件，请参见`：h viminfo-&#39;.

使用`mM`记住带有文件标记“ M”的当前位置. 切换到另一个
缓冲并通过`&#39;M`或``M``返回.

其他动议包括：

 | 运动| 跳到.. |
|------------------|-----------|
 |  `&#39;[`，```[``| 先前更改或粘贴的文本的第一行或字符.  |
 |  `&#39;]`，```]``| 先前更改或粘贴的文本的最后一行或字符.  |
| `'<`, `` `< ``   | Beginning line or character of last visual selection. |
 |  `&#39;&gt;`，```&gt;``| 最后视觉选择的结尾线或字符.  |
 |  `&#39;&#39;`，````````| 在最新跳转之前的位置.  |
 |  `&#39;&#39;`，```&#39;&#39;``| 最后退出当前缓冲区的位置.  |
 |  `&#39;^`，```^``| 最后插入停止的位置.  |
 |  `&#39;.`，```.  ``| 上次更改的位置.  |
 |  `&#39;（`，```（``|当前句子的开头.
 |  `&#39;）`，```）``| 当前句子的结尾.  |
 |  `&#39;{`，```{``| 当前段落的开始.  |
 |  `&#39;}`，```}``| 当前段落的结尾.  |

标记也可以用于 [range](#ranges) . 您可能以前看过
想知道这是什么意思：在可视模式下选择一些文本并执行`：`
命令行将以`：&#39;&lt;，&#39;&gt;`开头，这意味着以下命令
将获得一个表示视觉选择的范围.

使用`：marks`列出所有标记. 阅读`：h mark-motions`中的所有内容.

## Completion

 Vim提供了多种插入模式补全. 如果有多个
匹配项，弹出菜单将让您导航到您选择的匹配项.

补全的典型种类是标签，来自导入模块的功能或
库，文件名，字典或当前缓冲区中的单词.

Vim为每种完成提供映射，它们都以
 `<c-x>  `（记住要在插入模式下使用它们）：

 | 映射| 种类| 帮助|
|---------|------|--------------|
 |  `<c-x><c-l>  `| 整行|  `：hi ^ x ^ l` |
 |  `<c-x><c-n>  `| 当前文件中的关键字|  `：hi ^ x ^ n` |
 |  `<c-x><c-k>  `|  &#39;&#39;dictionary&#39;`选项中的关键字|  `：hi ^ x ^ k` |
 |  `<c-x><c-t>  `|  “ thesaurus”选项中的关键字|  `：hi ^ x ^ t` |
 |  `<c-x><c-i>  `| 当前文件和包含文件中的关键字|  `：hi ^ x ^ i` |
 |  `<c-x><c-]>  `| 标签|  `：hi ^ x ^]`|
 |  `<c-x><c-f>  `| 文件名|  `：hi ^ x ^ f` |
 |  `<c-x><c-d>  `| 定义或宏|  `：hi ^ x ^ d` |
 |  `<c-x><c-v>  `|  Vim命令|  `：hi ^ x ^ v` |
 |  `<c-x><c-u>  `| 用户定义（在`completefunc&#39;中指定）|  `：hi ^ x ^ u` |
 |  `<c-x><c-o>  `| 全方位完成（在&#39;omnifunc&#39;中指定）|  `：hi ^ x ^ o` |
 |  `<c-x>  s` | 拼写建议|  `：hi ^ Xs` |

人们可能对用户定义的补全之间的差异感到困惑
和全能完成，但从技术上讲，它们执行相同的操作. 他们拿一个
该功能检查当前位置并返回建议列表.
用户定义的完成是由用户出于自己的个人目的定义的.
 （惊讶！）可以是任何东西.  Omni完成是针对特定于文件类型
目的，例如完成结构成员或类方法，并且通常由
文件类型插件.

Vim还可以通过设置
 `&#39;complete&#39;`选项. 默认情况下，该选项包含很多内容，因此请确保
修剪使其符合您的口味. 您可以使用任一`<c-n>  `
 （下一个）和`<c-p>  `（上一个），它也恰好是用于
在弹出菜单中选择条目. 有关更多信息，请参见`：hi ^ n`和`：h&#39;complete&#39;`.
this.

请务必签出`：h&#39;completeopt&#39;`来配置
弹出菜单. 默认值非常合理，但是我也喜欢添加“ noselect”.

Help:

```
：h ins-completion
：h popupmenu键
：h new-omni-completion
```

## Motions, operators, text objects

 **动作**移动光标. 大家都知道`h` /`j` /`k` /`l`. 或`w`和`b`. 甚至
 “ /”是一个动作. 他们也很重要.  `2？<cr>  `跳到倒数第二
发生“的”.

有关所有可用的动作，请参见`：h导航&#39;和下面的所有内容.

**运算符**作用于文本区域，例如`d`，`〜`，`gU`，`&gt;`只是一个
很少. 它们在正常或可视模式下的两种情况下使用. 在正常情况下
模式下，操作员先执行动作，然后执行“&gt; j”. 在视觉模式下，
运算符只对选择起作用，例如“ Vjd”.

像动作一样，运算符也要计数，例如，`2gUw`使剩余的电流
word and the next one uppercase. Since motions and operators take counts,
`2gU2w`同样工作，并执行两次`gU2w`.

有关所有可用的运算符，请参见`：h运算符`. 使用`：set tildeop`来制作〜
充当操作员.

**文本对象**作用于周围区域，而不是作用于周围的动作
一个方向. 实际上，他们在处理对象，例如整个单词，整个单词
句子，括号之间的所有内容，依此类推.

文本对象不能在正常模式下移动光标，因为即使
最熟练的光标不能同时跳入两个方向. 有用
但是在可视模式下，因为此时对象的一侧已被选中
然后光标仅跳到另一侧.

文本对象以“ i”（认为_inner_）或“ a”（认为_around_）开头
后跟一个表示对象的字符. 使用`i`时，它仅作用于对象
本身，对象上带有`a&#39;加上结尾的空格. 例如diw删除
当前单词和`ci（`会更改括号之间的所有内容.

文本对象很重要. 想象一下`（（（（）））`和光标在
大多数内圆括号，那么d2a（`将删除两对内圆括号
介于两者之间.

有关所有可用的文本对象，请参见`：h text-objects`.

## Autocmds

您可以在Vim中发生许多事件（例如缓冲区被
通过所谓的_autocmds_保存或启动Vim.

 Vim广泛依赖于autocmds. 不相信我吗检查`：au`，但不要让
输出使您不知所措. 这些都是有效的autocmds
now!

有关所有可用事件的简要概述，请参见`：h {event}`.
有关更多详细信息，请参见autocmd-events-abc`.

一个典型的示例是特定于文件类型的设置：

```vim
autocmd FileType红宝石setlocal shiftwidth = 2 softtabstop = 2条注释-=：#
```

但是，缓冲区如何知道它包含Ruby代码呢？ 因为另一个
autocmd将其检测为该文件并相应地设置文件类型
触发了“ FileType”事件.

每个人添加到其vimrc的第一件事就是`filetype on`. 这个
只是意味着在启动时会读取`filetype.vim`，从而将autocmds设置为
阳光下几乎所有文件类型.

如果您足够勇敢，请看一下：`：e $ VIMRUNTIME / filetype.vim`. 搜索
代表“ Ruby”，您会发现Vim只是使用文件扩展名“ .rb”来
检测Ruby文件：

**注意**：相同事件的自动命令按执行顺序执行
创建.  `：au`以正确的顺序显示它们.

```vim
au BufNewFile，BufRead * .rb，*.rbw setf ruby
```

在这种情况下，`BufNewFile`和`BufRead`事件被硬编码在C中
Vim的源代码，并且每次通过`：e`和类似文件打开文件时都会被释放
命令. 然后，来自`filetype.vim`的所有​​数百种文件类型都是
经过测试.

简而言之，Vim大量使用了事件和autocmds，但是
公开一个干净的接口以连接到该事件驱动的系统中
customization.

帮助：`：h autocommand`

## Changelist, jumplist

最近100次更改的位置保留在“更改列表”中. 一些
同一行上的小变化将合并在一起，但位置将是
尽管如此，最后一次更改的内容（如果您在中间添加了一些内容
行）.

每次您跳起时，都会在
 **跳转列表**. 跳转列表最多可包含100个条目. 每个窗口都有自己的窗口
跳转列表. 拆分窗口时，将复制跳转列表.

跳转是以下命令之一：`，`，``，&#39;&#39;G`，`/`，`？`，`n`，`N`，
`％`，`（`，`）`，`[[`，`]]`，`{`，`}`，`：s`，`：tag`，`L`，`M`，`H `和命令
开始编辑新文件.

 | 列表| 列出所有条目| 转到较旧的位置| 转到新位置|
|------------|------------------|----------------------|----------------------|
 | 跳转列表|  `：跳转`|  `[count]<c-o>  `|  `[count]<c-i>  `|
 | 变更清单|  `：changes` |  `[count] g;`|  `[count] g，`|

当您列出所有条目时，标记“&gt;”将用于显示当前
位置. 通常情况下，该价格将低于最新的排名1.

如果您希望两个列表在重启Vim之后仍然存在，则需要使用
viminfo文件和`：h viminfo-&#39;.

并可以通过````````或`&#39;&#39;`跳转到.

Help:

```
：h变更清单
：h跳转列表
```

## Undo tree

记住对文本状态的最新更改. 您可以使用_undo_
还原更改，然后_redo_重新应用以前还原的更改.

掌握最新数据结构的重要一点
变化不是
[queue](https://en.wikipedia.org/wiki/Queue_(abstract_data_type)），但是
[tree](https://en.wikipedia.org/wiki/Tree_(data_structure) ）！ 您的更改是
树中的每个节点（但顶部节点除外）都有一个父节点. 每个节点保持
有关更改的文本和时间的信息. 分支是一系列节点
从任何节点开始，一直到顶部节点. 新分支在以下时间创建
您撤消更改，然后插入其他内容.

```
ifoo<esc>
obar<esc>
obaz<esc>
u
oquux<esc>
```

现在您有3行，并且撤消树如下所示：

```
     富（1）
       /
    酒吧（2）
   /      \
baz（3）队列（4）
```

撤消树有4个更改. 数字代表节点所在的_time_
created.

现在有两种遍历该树的方法，我们称它们为_branch-wise_和
_time-wise_.

撤消（`u`）和重做（`<c-r>  `）以分支方式工作. 他们上下流
科.  u将把文本状态恢复为节点“ bar”之一. 另一个`u`
将进一步将文本状态还原为节点“ foo”之一. 现在`<c-r>  `
回到节点“ bar”的状态，另一个`<c-r>  `到节点的状态
 “ quux”.  （再也无法使用分支命令来到达节点“ baz”.）

与此相反，“ g-”和“ g +”在时间上有效. 因此，“ g-”不会恢复为
像“ u”一样，节点“ bar”的状态，但按时间顺序为先前的状态，
节点“ baz”. 另一个`g-`会将状态恢复为节点“ bar”之一，因此
上. 因此，“ g-”和“ g +”分别只是在时间上来回移动.

 | 命令/映射| 动作|
|-------------------|--------|
 |  `[count] u`，`：undo [count]`| 撤消[count]个更改.  |
 |  `[count]<c-r>  `，`：redo` | 重做[计数]更改.  |
 |  `U` | 撤消所有更改到最新更改的行.  |
 |  `[count] g-`，`：较早的[count]吗？ 转到较早的文本状态[count]次.  “？” 可以是“ s”，“ m”，“ h”，“ d”或“ f”. 例如，`：earlier 2d`从2天前进入文本状态.  `：early 1f`将进入最新文件保存状态.  |
 |  `[count] g +`，`：以后[count]？`| 与上述相同，但方向相反.  |

撤消树保留在内存中，并且在Vim退出时将丢失. 请参阅[撤消
files](#undo-files) for how to enable persistent undo.

如果您对撤消树感到困惑，
[undotree](https://github.com/mbbill/undotree) 在可视化方面做得很好
it.

Help:

```
：h undo.txt
：h usr_32
```

## Quickfix and location lists

快速修复列表是保存文件位置的数据结构. 本质上，
快速修复列表中的每个条目均由文件路径，行号和
可选列和说明.

典型的用例是组装编译器错误或grep工具的结果.

Vim有一种特殊的缓冲区来显示快速修复列表：quickfix
缓冲.  quickfix缓冲区中的每一行都显示quickfix列表中的一项.

通常，您会打开一个新窗口来显示快速修复程序列表：快速修复程序窗口.
发生这种情况时，最后一个窗口将与quickfix窗口关联.

在quickfix缓冲区中<cr> `在关联的窗口中打开选定的条目
和`<c-w><cr> 在新窗口中.

快速修复列表以[Aztec C
compiler](https://en.wikipedia.org/wiki/Aztec_C).

实际上，有两种列表：quickfix和位置列表. 他们表现得很
几乎相同，但有以下差异：

 -只有一个Quickfix列表. 可以有多个位置列表. 每一个
  窗口.
-他们使用略有不同的命令进行导航.

 | 动作| 快速修复| 位置|
|----------------|--------------|--------------|
 | 开窗|  `：copen` |  `：步行`|
 | 关闭窗口|  `：cclose` |  `：lclose` |
 | 下一个条目 `：cnext` |  `：下一个`|
 | 上一个条目|  `：cprevious` |  `：lprevious` |
 | 第一次进入|  `：cfirst` |  `：lfirst` |
 | 最后进入 `：clast` |  `：llast` |

Mind that the quickfix and location windows don't need to be open for these
命令起作用.

有关更多信息和命令的完整列表，请参见`：h quickfix`.

为简洁起见，_quickfix_和_location_通常缩写为_qf_和
分别_loc_.

**Example**:

让我们用好朋友“ grep”来搜索当前文件
递归特定查询的目录，并将结果放入quickfix
list.

```vim
：let＆grepprg =&#39;grep -Rn $ *.&#39;
 ：握！ 富
<grep output - hit enter>
:copen
```

假设任何文件都包含字符串“ foo”，则现在应将其显示在
quickfix窗口.

## Macros

Vim允许_recording_个键入的字符到一个 [register](#registers) . 它是
快速实现某些任务自动化的好方法.  （对于更复杂的任务，Vim
应该改用脚本.）

 -输入“ q”，然后输入寄存器，例如“ q”，开始记录.  （
  命令行将通过“ recording @q”表示这一点.）
-再次点击“ q”停止录制.
-通过[[count] @q]执行宏.
-通过“ [count] @@”重复最后使用的宏.

**范例1：**

插入一行并重复10次：

```
qq
iabc<cr><esc>
q
10@q
```

 （没有宏也可以这样做：`oabc<esc>  10.`）

**范例2：**

要在所有行的前面添加行号，请从第一行开始并添加
 “ 1.”手动. 使用`增加光标下的数字<c-a> `，
显示为“ ^ A”.

```
qq
0yf jP0 ^ A
q
1000@q
```

在这里，我们只是希望文件包含的行数不超过1000行
使用`1000 @ q`，但我们也可以使用_recursive macro_，该宏执行到
该宏不能再应用于行：

```
qq
0yf jP0 ^ A @ q
q
@q
```

（没有宏也可以这样做：`：％s / ^ / \ = line（&#39;.&#39;）.&#39;.&#39;`）

请注意，我还展示了如何在不使用宏的情况下实现相同的功能，但这
大多数情况下仅适用于此类简单示例. 对于更复杂的自动化，宏
是炸弹！


Help:

```
：h录制
：h&#39;lazyredraw&#39;
```

## Colorschemes

 Colorschemes是样式您的Vim的方式.  Vim由许多组件组成，
可以为前景中的每一个自定义不同的颜色，
背景和其他一些属性（如粗体文本等）.可以将它们设置为
this:

```vim
：highlight正常ctermbg = 1 guibg =红色
```

这样会将编辑器的背景涂成红色. 参见`：h：highlight`了解更多
information.

因此，colorchemes主要是`：highlight`命令的集合.

实际上，大多数颜色方案实际上是2种颜色方案！ 上面的例子
通过`ctermbg`和`guibg`颜色. 前一个定义（`cterm *`）仅
如果Vim是在终端仿真器（例如xterm）中启动的，则使用此命令. 后者（`gui *`）
将用于gvim或MacVim等图形环境.

如果您碰巧在终端Vim中使用了colorcheme而颜色却没有
看起来就像屏幕截图中的那些一样，很可能是colorcheme
仅定义GUI的颜色. 相反，如果您使用图形Vim（例如
gvim或MacVim），并且颜色看起来不一样，colorscheme可能只定义了
终端的颜色.

通过在Neovim或Vim中启用真彩色，可以“解决”后一种情况
 7.4.1830及更高版本. 这使得终端Vim改为使用GUI定义，但是
还需要终端仿真器本身及其之间的所有软件（例如
 tmux）以能够处理真彩色.  （[这个
要点]（https://gist.github.com/XVilka/8346728）很好地概述了
topic.)

Help:

-`：h&#39;termguicolors&#39;`
- [List of colorschemes](https://github.com/mhinz/vim-galore/blob/master/PLUGINS.md#colorschemes-1)

## Folding

每个文本（或源代码）都有特定的结构. 如果你有一个结构，它
表示您有逻辑上分开的文本区域. 折叠允许“折叠”
这样的区域变成一行并显示简短说明. 有
作用于这些区域的许多命令称为_folds_. 褶皱可以嵌套.

Vim区分几种折叠方法：

 |  &#39;foldmethod&#39;| 用法
|--------------|-------|
 | 差异| 在差异窗口中用于折叠未更改的文本.  |
 |  expr | 使用`foldexpr&#39;基本上创建一个新的fold方法.  |
 | 缩进基于缩进的折痕.  |
 | 手册| 通过`zf`，`zF`和`：fold`自己创建折叠.  |
 | 标记| 根据文本中的标记折叠（通常在注释中）.  |
 | 语法| 基于语法的折叠，例如折叠`if`块.  |

 **注意**：折叠可能需要大量计算！ 如果您遇到任何
性能上的缺点（键入时延迟很小），请查看
[FastFold](https://github.com/Konfekt/FastFold)，防止Vim从
不需要时更新折叠.

Help:

```
：h usr_28
：h折
```

## Sessions

如果保存** view **（`：h：mkview`），则窗口的当前状态（以及
选项和映射）将被保存以供以后使用（`：h：loadview`）.

会话**保存所有窗口的视图以及全局设置. 基本上
制作当前Vim实例的快照并将其保存在会话文件中.
让我强调一下：它保存了当前状态； 保存一个后所做的一切
会话将不属于会话文件. 要“更新”会话，只需编写
再次出来.

这非常适合保存_projects_，并且易于在之间切换
them.

立即尝试！ 打开几个窗口和选项卡，然后执行`：mksession Foo.vim`. 如果
您省略文件名，将使用`Session.vim`. 该文件将保存到
当前工作目录，检查`：pwd`. 重新启动Vim并执行`：source
Foo.vim和voilà，缓冲区列表，窗口布局，映射，工作目录
等等都应该与保存会话之前相同. 做更多的工作
并通过覆盖现有会话文件来更新会话
 `：mksession！  Foo.vim`.

请注意，会话文件实际上只是Vim命令的集合，
应该恢复Vim实例的特定状态，因此可以随意
看它：`：vs Foo.vim`.

您可以通过设置&#39;sessionoptions&#39;来告诉Vim在会话中保存哪些内容.

为了编写脚本，Vim保留了上一个来源或书面会话的名称.
在内部变量`v：this_session`中.

Help:

```
：h会议
：h&#39;会话选项&#39;
：hv：this_session
```

## Locality

上面提到的许多概念也具有_local_对应项：

 | 全球| 当地| 范围| 帮助|
|--------|-------|-------|------|
 |  `：set` |  `：setlocal` | 缓冲区或窗口|  `：h local-options | |
 |  `：map` |  `：地图<buffer> `| 缓冲|  `：h：map-local` |
 |  `：autocmd` |  `：autocmd *<buffer>  `| 缓冲|  `：h autocmd-buflocal` |
| `:cd`      | `:lcd`                | window           | `:h :lcd`             |
 |  `<leader>  `|  `<localleader>  `| 缓冲|  `：h maplocalleader` |

[Variables also have different scopes](https://vimhelp.appspot.com/usr_41.txt.html#41.2).

## Usage

## Getting help offline

Vim带有单个文本文件形式的出色文档，并带有
特殊的布局.  Vim使用基于标签的系统来访问其中的某些部分
这些帮助文件.

首先，请阅读：`：help：help`. 这将打开文件
$ VIMRUNTIME / doc / helphelp.txt在新窗口中跳转到`：help`标记
在该文件中.

一些简单的规则：

-选项用单引号引起来，例如`：h&#39;textwidth&#39;`
-VimL函数以`（）&#39;结尾，例如`：h reverse（）`
-命令以`：`开头，例如`：h：echo`

您可以使用`<c-d>  `（这是<kbd>ctrl</kbd> + <kbd>d</kbd> ）以列出所有
匹配当前输入的查询. 例如`：h选项卡<c-d> `将为您提供所有清单
标签从“ softtabstop”上的“ tab”到“ setting-guitablabel”.

您要列出所有VimL函数吗？ 简单：`：h（）<c-d>  `. 您要列出所有
与Windows有关的VimL函数？  `：h win *（）<c-d>  `.

这很快就变成了第二天性，但是特别是在一开始，您
有时不知道您要查找的标签的任何部分. 你只能
想象一些可能涉及的关键字.  `：helpgrep`来解救！

```
：helpgrep向后
```

这将在所有文档文件中查找“向后”，并跳转到第一个
比赛. 比赛将被组装在快速修复列表中. 使用`：cn` /`：cp`来
跳至下一个/上一个比赛. 或者使用`：copen`打开quickfix窗口，
导航至条目并点击`<cr>  `跳至该比赛. 参见`：h quickfix`
整个事实.

## Getting help offline (alternative)

该列表由最活跃的Vim开发人员之一@chrisbra编译，并且
发布到 [vim_dev](https://groups.google.com/forum/#!forum/vim_dev).

稍有更改，便重新发布在这里.

---

如果您知道要查找的内容，通常搜索起来会更容易
使用帮助系统，因为主题遵循特定的样式指南.

另外，该帮助的优势在于属于您特定的Vim版本，因此
过时的主题或以后添加的主题将不会出现.

因此，必须学习帮助系统及其使用的语言.
以下是一些示例（不一定完整，我可能已经忘记了
something).

 1.选项用单引号引起来. 因此，您将使用`：h&#39;list&#39;`转到
   列表选项的帮助主题. 如果您只知道，您正在寻找
   某些选项，您还可以执行：h options.txt打开帮助页面，
   描述所有选项处理，然后您可以使用常规搜索
   表达式，例如`/ width`. 某些选项具有自己的名称空间，例如`：h
   cpo-a`，`：h cpo-A`，`：h cpo-b`等.

 2.普通模式命令就是这样. 使用`：h gt`转到帮助页面
   “ gt”命令.

3.正则表达式项始终以“ /”开头，因此`：h / \ +`将带您进入帮助项
   在Vim正则表达式中的“ \ +”量词. 如果您需要了解任何有关
   正则表达式，请从`：h pattern.txt&#39;开始阅读.

 4.组合键. 它们通常以单个字母开头表示模式
   可以使用它们. 例如：: h i_CTRL-X`带您到
   插入模式的CTRL-X命令，可用于自动完成不同
   东西. 请注意，某些键将始终写入相同的位置，例如Control
   将始终为CTRL. 请注意，对于普通模式命令，“ n”不存在，
   例如`：h CTRL-A`. 相反，`：h c_CTRL-R`将描述CTRL-R的作用
   在命令行中输入命令时，`：h v_Ctrl-A`讨论
   在可视模式下递增数字，`：h g_CTRL-A`讨论g<C-A>
   命令（因此您必须先按“ g”<Ctrl-A>  ）. 这里的“ g”代表
   普通命令“ g”，总是在执行前需要第二个键
   类似于以“ z”开头的命令.

5.寄存器总是以“ quote”开头，因此使用`：h quote`可以找到有关
   特殊的“：”寄存器.

 6. Vim脚本（VimL）在`：h eval.txt`中可用. 某些方面
   语言在`：h expr-X`中可用，其中&#39;X&#39;是单个字母，例如`：h
    expr-！`将带您到描述&#39;！&#39;的主题.  （非）运算符
    VimL. 同样重要，请参见`：h function-list`以找到以下内容的简短说明：
   所有可用功能.

 7.在帮助页面`：h map.txt`中讨论了映射. 使用`：h mapmode-i`
   来了解`：imap`命令. 也使用`：map-topic`找出
   关于某些特定于映射的子主题（例如：：h：map-local`
   本地缓冲区映射或`：h map_bar`了解&#39;|&#39;的方式在映射中处理.

8.命令定义在`：h command- *`讨论，所以使用：h command-bar
   找出有关“！”的信息自定义命令的参数.

9.窗口管理命令始终以CTRL-W开头，因此您会找到
   `：h CTRL-W_ *`中的相应帮助（例如：: h CTRL-W_p`切换到
   先前访问的窗口）. 您还可以访问`：h windows.txt`并阅读
   如果您正在寻找窗口处理命令，请按照以下步骤操作.

10. Ex命令始终以“：”开头，因此`：h：s`涵盖了“：s”命令.

11.输入主题后使用CTRL-D，让Vim尝试完成所有可用的操作
    主题.

12.使用`：helpgrep`来搜索所有帮助页面（通常还包括帮助
    页面（已安装的插件））. 有关如何使用它的信息，请参见`：h：helpgrep`. 一旦您
    搜索了一个主题，所有匹配项都可以在quickfix中找到（或
    位置）窗口，可通过`：copen`或`：lopen`打开. 那里你
    也可以使用“ /”进一步过滤匹配项.

13.`：h helphelp`包含一些有关如何使用帮助的信息.

 14.用户手册. 这在相当程度上描述了初学者的帮助主题.
    友好的方式. 从`：h usr_toc.txt`开始查找目录（如您
    可能已经猜到）. 略过那有助于找到某些主题，例如
    您会在以下位置找到条目“图”和“输入特殊字符”
    第24章（因此，可使用`：h usr_24.txt`转到该特定的帮助页面）.

 15.突出显示组始终以“ hl- *”开头. 例如：: h hl-WarningMsg`讲话
    关于“ WarningMsg”突出显示组.

16.语法高亮被命名为“：syn-topic”，例如：: h：syn-conceal
    讨论了：syn命令的隐藏参数.

17. Quickfix命令通常以“：c”开头，而位置列表命令
    通常以“：l”开头.

 18.`：h BufWinLeave`讨论BufWinLeave autocmd. 另外，：h
    autocommands-events`讨论所有可能的事件.

19.启动参数总是以“-”开头，所以`：h -f`可以帮助您
    Vim的“ -f”命令开关.

20.编译后的附加功能始终以“ +”开头，因此`：h + conceal`讨论
    隐藏的支持.

 21.错误代码可以直接在帮助中查找.  `：h E297`带您
    完全与错误消息的描述相同. 但是有时候
    错误代码没有描述，而是在Vim命令中列出，
    通常会导致这种情况. 例如:: h hE128`直接将您带到`：function`
    命令.

22.包含语法文件的文档通常在`：h中可用.
     ft- *语法`. 例如：: h ft-c-syntax`讨论C语法文件和
    它提供的选项. 有时，还会有其他部分用于全能补全（`：h
    ft-php-omni`或文件类型插件（`：h ft-tex-plugin`）可用.

此外，还有用户文档的链接（该文档进一步描述了某些命令
从用户的角度出发（较不详细））将在帮助顶部提到
页面（如果有）. 所以`：h pattern.txt`提到了用户指南主题
`：h 03.9`和`：h usr_27`.

## Getting help online

如果您有无法解决的问题或需要一般指导，请参阅
the [vim_use](https://groups.google.com/forum/#!forum/vim_use) 邮件列表.
另一个很棒的资源是使用
[IRC](https://de.wikipedia.org/wiki/Internet_Relay_Chat). The channel `#vim` on
[Freenode](https://freenode.net) 人数众多，通常充满帮助的人.

如果要报告Vim错误，请使用
[vim_dev](https://groups.google.com/forum/#!forum/vim_dev) 邮件列表.

## Autocmds in practice

您可以立即触发任何事件：`：doautocmd BufRead`.

### User events

特别是对于插件，创建自己的“ User”事件非常有用：

```vim
功能！ 胖（）
  “这里发生了很多事情.
  “最后
  doautocmd用户ChibbyExit
endfunction
```

现在，当Chibby完成运行时，插件的用户可以执行任何操作：

```vim
autocmd用户ChibbyExit调用ChibbyCleanup（）
```

顺便说一句，如果没有“ catching”：autocmd，：doautocmd将输出一个讨厌
 “没有匹配的自动命令”消息. 这就是为什么许多插件使用`silent
 doautocmd ...`. 但这有一个缺点，就是您不能简单地使用
：autocmd中的`echo“ foo”`，则必须改用`unsilent echo“ foo”`.

这就是为什么最好检查是否有一个接收autocmd而不是
否则会麻烦发出该事件：

```vim
if exists('#User#ChibbyExit')
  doautocmd用户ChibbyExit
endif
```

帮助：`：h用户`

### Nested autocmds

默认情况下，autocmds不嵌套！ 如果autocmd执行命令，则在
转弯通常会触发另一个事件，但不会发生.

假设每次启动Vim时都想自动打开vimrc：

```vim
autocmd VimEnter *编辑$ MYVIMRC
```

现在，当您启动Vim时，它将打开您的vimrc，但是您首先要做的是
注意，尽管通常会突出显示，但不会有任何突出显示.

问题是非嵌套autocmd中的`：edit`不会触发
“ BufRead”事件，因此文件类型永远不会设置为“ vim”，并且
 $ VIMRUNTIME / syntax / vim.vim从未获得. 参见`：au BufRead * .vim`. 用这个
instead:

```vim
autocmd VimEnter *嵌套编辑$ MYVIMRC
```

帮助：`：h autocmd-nested`

## Clipboard

Required [features](#what-kind-of-vim-am-i-running)：`+ clipboard`和可选
+ xterm_clipboard`，如果要在Unix系统上使用`clipboard&#39;选项
没有GUI支持的Vim.

Help:

```
：h&#39;剪贴板&#39;
:h gui-clipboard
:h gui-selections
```

另请参见：[括号内的粘贴（或为什么我必须将所有
time?)](#bracketed-paste-or-why-do-i-have-to-set-paste-all-the-time)

### Clipboard usage (Windows, macOS)

Windows随附
[clipboard](https://msdn.microsoft.com/en-us/library/windows/desktop/ms649012(v=vs.85).aspx)
而macOS随附
[pasteboard](https://developer.apple.com/library/mac/documentation/Cocoa/Conceptual/PasteboardGuide106/Introduction/Introduction.html#//apple_ref/doc/uid/TP40008100-SW1).

两者都能像大多数用户期望的那样工作. 您复制带有
`ctrl + c` /`cmd + c`并将其粘贴到带有`ctrl + v` /`cmd + v`的另一个应用程序中.

请注意，复制的文本实际上已传输到剪贴板，因此您可以关闭
您粘贴之前从中复制的应用程序，而没有其他应用程序
problems.

每当这种情况发生时，剪贴板寄存器“ *”就会充满
选择. 从Vim使用`“ * y`和`” * p`从剪贴板粘贴并粘贴.
respectively.

如果您甚至不想一直指定`*`寄存器，请将其放入
您的vimrc：

```vim
设置剪贴板=未命名
```

通常，所有yank / delete / put操作都填充`“寄存器，现在是`*`
寄存器用于相同的操作，因此简单地将`y`和`p`
enough.

让我重复一遍：使用上面的选项意味着每次猛拉/粘贴，即使在
仅在同一个Vim窗口中使用，会更改剪贴板. 自己决定
是否有用.

如果您懒得输入y，则可以将所有视觉选择发送到
通过使用以下设置的剪贴板：

```vim
设置剪贴板=未命名，自动选择
设置guioptions + = a
```

Help:

```
：h剪贴板未命名
：h自动选择
：h&#39;go_a&#39;
```

### Clipboard usage (Linux, BSD, ...)

如果您的操作系统使用 [X](http://www.x.org/wiki) ，事情有点不同.  X
实现[X Window系统
协议]（http://www.x.org/releases/X11R7.7/doc/xproto/x11protocol.html）
自1987年以来恰好是主要版本11，因此X也经常称为X11.

以前，在X10中，[剪切
buffers](http://www.x.org/releases/X11R7.7/doc/xorg-docs/icccm/icccm.html#Peer_to_Peer_Communication_by_Means_of_Cut_Buffers)
在复制文本中被介绍为类似于_clipboard_
实际上由X拥有，并且所有其他应用程序都可以访问它. 这个
机制仍然存在于X中，但现在已弃用，大多数软件
不再使用它.

如今，数据通过以下方式在应用程序之间传输：
[selections](http://www.x.org/releases/X11R7.7/doc/xorg-docs/icccm/icccm.html#Peer_to_Peer_Communication_by_Means_of_Selections).
在定义的3个“选择原子”中，实际上仅使用2个：PRIMARY和
CLIPBOARD.

选择工作大致如下：

```
程序A：<ctrl+c>
计划A：声明对CLIPBOARD的所有权
程式B：<ctrl+v>
程序B：请注意，CLIPBOARD的所有权由程序A持有
程序B：向程序A请求数据
程序A：响应请求并将数据发送到程序B
程序B：从程序A接收数据并将其插入到窗口中
```

 | 选择| 何时使用？  | 如何贴上？  | 如何从Vim访问？  |
|-----------|------------|---------------|-------------------------|
 | 主要| 选择文字|  “中键单击”，“ Shift +插入” |  *注册
 | 剪贴板| 选择文本和`ctrl + c` |  `ctrl + v` |  `+`注册|

**注意**：选项（不，甚至不是CLIPBOARD选项）从不保存
 X服务器！ 因此，当应用程序运行时，您将丢失用`ctrl + c`复制的数据
closes.

使用“ * p”粘贴“ PRIMARY”选择，或使用“” + y1G”将整个文件粘贴到
CLIPBOARD选择.

如果您碰巧一直访问两个寄存器之一，请考虑使用：

```vim
设置剪贴板^ =未命名“ *注册
“ 要么
设置剪贴板^ = unnamedplus“ +注册
```

（`^ =`用于添加默认值`：h：set ^ =`.）

This will make all yank/delete/put operations use either `*` or `+` instead of
未命名的寄存器“”.之后，您只需使用“ y”或“ p”进行访问
您选择的X选择.

Help:

```vim
：h剪贴板未命名
：h剪贴板-unnamedplus
```

## Restore cursor position when opening file

当您打开文件时，光标将位于第1行第1列.
幸运的是，viminfo文件可以记住 [marks](#marks) .  “”标记包含
缓冲区中您停止的位置.

```vim
autocmd BufReadPost *
    \ if line（“&#39;\”“）&gt; 1 &amp;&amp; line（”&#39;\“”）&lt;= line（“ $”）|
    \执行“正常！g` \”” |
    \ 万一
```

读取：如果标记`“`包含的行号大于第1行但不大于第1行
比文件中的最后一行跳到它.

    ：h viminfo-&#39;
    ：h`quote
    ：hg`

## Temporary files

### Backup files

在保存文件之前，Vim将创建一个备份文件. 如果写入磁盘是
成功后，备份文件将被删除.

使用`：set backup`，备份将持续存在. 这意味着备份文件将
总是与原始文件_before_最近的保存具有相同的内容.
由您决定这是否有用.

您可以使用`：set nobackup nowritebackup`完全禁用备份，但是您可以
如今不需要.  `&#39;writebackup&#39;`是一项安全功能，可以使
确保您不会丢失原始文件，以防保存失败.
无论以后是否保留备份文件.

如果您经常使用Vim编辑大文件，[您可能
shouldn't](#editing-huge-files-is-slow), you can exclude those from backups with
`'backupskip'`.

Vim知道创建备份的不同方法：_copying_和_renaming_.

-**复制**
    1.创建原始文件的完整副本，并将其用作备份.
    1.清空原始文件，然后将其内容
    Vim缓冲区.
-**重命名**
    1.将原始文件重命名为备份文件.
    1. Vim缓冲区的内容被写入名称为的新文件.
    原始文件.

有关所有实质内容，请参见`：h&#39;backupcopy&#39;`.

---

Demo:

```vim
 ：set backup backupskip = backupdir =.  backupext =-备份
：e / tmp / foo
ifoo<esc>
:w
创建原始文件，无需备份文件
obar<esc>
:w
“已创建备份文件，原始文件已更新
```

```diff
$ diff -u / tmp / foo-backup / tmp / foo
--- / tmp / foo-backup 2017-04-22 15：05：13.000000000 +0200
+++ / tmp / foo 2017-04-22 15：05：25.000000000 +0200
@@ -1 +1,2 @@
 富
+bar
```

---

    ：h备份
    ：h写失败

### Swap files

编辑文件时，未保存的更改将写入交换文件.

Get the name of the current swap file with `:swapname`. Disable them with `:set
noswapfile`.

交换文件将全部更新为200个字符，或者未输入任何内容时更新
 4秒当您停止编辑文件时，它们将被删除. 您可以更改这些
`：h&#39;updatecount&#39;`和`：h&#39;updatetime&#39;`的数字.

如果Vim被杀死（例如断电），您将失去自上次以来的所有更改
该文件已写入磁盘，但不会删除交换文件. 现在，如果你
再次编辑文件，Vim将提供机会从交换中恢复文件
file.

当两个人尝试编辑同一文件时，第二个人将收到通知
交换文件已经存在. 它可以防止人们试图保存
文件的不同版本. 如果您不想要这种行为，请参见`：h
'directory'`.

    ：h交换文件
    ：h usr_11

### Undo files

The [undo tree](#undo-tree) 保留在内存中，退出Vim时将丢失.
如果你想保留它，`：set undofile`. 这会将撤消文件保存为
〜/ foo.c.un〜中的〜/ foo.c

    ：h&#39;撤消文件&#39;
    ：h撤消持久性

### Viminfo files

当备份，交换和撤消文件都与文本状态有关时，viminfo文件即为
用于保存退出Vim时可能丢失的所有其他内容.
viminfo文件保留历史记录（命令行，搜索，输入），寄存器，
标记，缓冲区列表，全局变量等

默认情况下，viminfo被写入`〜/ .viminfo`.

    ：h viminfo
    ：h&#39;viminfo&#39;

### Example configuration for temporary files

将所有临时文件放在自己的目录下~~ ..vim / files下：

```vim
“根据需要创建目录
如果！isdirectory（$ HOME.&#39;/.vim / files&#39;）&amp;&amp;存在（&#39;* mkdir&#39;）
  调用mkdir（$ HOME.&#39;/.vim / files&#39;）
endif

“ 备份文件
设置备份
设置backupdir = $ HOME / .vim / files / backup /
设置backupext = -vimbackup
设置backupskip =
交换文件
设置目录= $ HOME / .vim / files / swap //
设置updatecount = 100
撤消文件
set undofile
unity set = $ HOME / .vim /文件/撤消/
“ viminfo文件
设置viminfo =&#39;100，n $ HOME / .vim / files / info / viminfo
```

## Editing remote files

 Vim带有netrw插件，该插件可以编辑远程文件. 其实呢
通过scp将远程文件传输到本地临时文件，打开缓冲区
使用该文件，并在保存时将更改写回到远程文件.

如果您想使用本地配置而不是
进入服务器并使用管理员希望您使用的任何内容.

```
：和SCP：//bram@awesome.site.com/.vimrc
```

如果已经设置了〜/ .ssh / config，它将自动使用：

```
主机很棒
    主机名awesome.site.com
    端口1234
    用户吹牛
```

假设上述内容在`〜/ .ssh / config`中，效果也一样：

```
：e scp：//awesome/.vimrc
```

用〜/ .netrc可以完成类似的操作，参见`：h netrw-netrc`.

确保阅读`：h netrw-ssh-hack`和`：hg：netrw_ssh_cmd`.

---

另一种可能性是使用 [sshfs](https://wiki.archlinux.org/index.php/Sshfs)
使用 [FUSE](https://en.wikipedia.org/wiki/Filesystem_in_Userspace) 至
将远程文件系统挂载到本地文件系统中.

## Managing plugins

[Pathogen](https://github.com/tpope/vim-pathogen) 是第一个流行的工具
管理插件. 实际上，它只是将_runtimepath_（`：h&#39;rtp&#39;`）调整为
include all the things put under a certain directory. You have to clone the
repositories of the plugins there yourself.

真正的插件管理器提供了可帮助您安装和更新插件的命令
从Vim内部.

[List of plugin managers](https://github.com/mhinz/vim-galore/blob/master/PLUGINS.md#plugin-managers)

## Block insert

这是一种在同一行的多个连续行上插入相同文本的技术
同时. 看到这个
[demo](https://raw.githubusercontent.com/mhinz/vim-galore/master/static/images/content-block_insert.gif).

使用`切换到可视块模式<c-v> `. 然后下降几行.
点击“ I”或“ A”，然后开始输入您的文本.

刚开始时可能会有些混乱，但是总是输入当前文本
行，只有在完成当前的插入操作后，相同的文本才会显示为
应用于先前视觉选择的所有其他行.

So a simple example is `<c-v>3jItext<esc>`.

如果您有不同长度的行，并且想在右边附加相同的文本
在每行结束后，执行以下操作：<c-v>  3j $ Atext<esc>  `.

有时您需要将光标放置在当前行结束之后的某个位置
线. 默认情况下，您不能执行此操作，但是可以设置`virtualedit`选项：

```vim
设置virtualedit = all
```

之后，`$ 10l`或`90 |`即使在行尾也起作用.

有关更多信息，请参见`：h blockwise-examples`. 乍一看似乎很复杂，
但很快成为第二天性.

如果你想得到真正的幻想，看看
[multiple-cursors](https://github.com/terryma/vim-multiple-cursors).

## Running external programs and using filters

免责声明：Vim是单线程的，因此在
前景将阻止其他所有内容. 当然，您可以使用Vim的其中之一
编程接口（例如Lua）并使用其线程支持，但是在此期间
仍然会阻止Vim进程.  Neovim通过添加一个
适当的作业API.

（显然，Bram也在考虑向Vim添加作业控制.如果您
有最新版本，请参见`：helpgrep startjob`.）

使用`：！`开始工作. 如果要列出当前工作中的文件
目录，使用`：！ls`. 像往常一样使用`|`在外壳中进行管道输送，例如`：！ls -1 |
排序尾-n5`.

Without a range, the output of `:!` will be shown in a scrollable window. On the
另一方面，如果给定范围，这些行将是
[filtered](https://en.wikipedia.org/wiki/Filter_(software) ）. 这意味着他们
将通过管道传输到
[stdin](https://en.wikipedia.org/wiki/Standard_streams#Standard_input_.28stdin.29)
过滤程序的代码，并在处理后由
[stdout](https://en.wikipedia.org/wiki/Standard_streams#Standard_output_.28stdout.29)
过滤器的例如，将数字前置到下5行，请使用以下命令：

    ：.，+ 4！Nl -ba -w1 -s&#39;&#39;

由于手动添加范围非常繁重，因此Vim还提供了一些功能.
方便的助手. 与范围一样，您也可以选择
视觉模式，然后按`：`. 还有一个操作符`！`动作.
例如`！ip！sort`将对当前段落的行进行排序.

过滤的一个好用例是[Go编程
语言]（https://golang.org）. 缩进很自以为是，甚至
带有一个名为`gofmt`的过滤器，用于正确缩进Go源代码. 所以
Go的插件通常会提供称为`：Fmt`的帮助程序命令，基本上
`：％！gofmt`，因此它们缩进文件中的所有行.

人们经常使用`：r！prog`将prog的输出置于当前行下方，
这对于脚本来说很好，但是在运行过程中，我发现它更易于使用
取而代之的是!!! ls，它将替换当前行.

    ：h过滤器
    ：h：读！

## Cscope

[Cscope](http://cscope.sourceforge.net/) 做的比
[ctags](http://ctags.sourceforge.net/), but only supports C (and C++ and Java to
在某种程度上）.

标签文件仅知道符号的定义位置，而cscope数据库
更了解您的数据：

-这个符号在哪里定义？
-该符号在哪里使用？
-这个全局符号的定义是什么？
-这个变量从哪里获得价值？
-此功能在源文件中的什么位置？
-什么功能称为该功能？
-该功能调用什么功能？
-“空间不足”消息从何而来？
-此源文件在目录结构中的什么位置？
-哪些文件包含此头文件？

### 1. Build the database

在项目的根目录中执行此操作：

```sh
$ cscope -bqR
```

这将创建3个文件：当前工作中的`cscope {，.in，.po} .out`
目录. 将它们视为您的数据库.

不幸的是，`cscope`默认只分析`*.[c | h | y | l]`文件. 如果你想
而是将cscope用于Java项目，请执行以下操作：

```sh
 $查找. 名称“ * .java”&gt; cscope.files
$ cscope -bq
```

### 2. Add the database

打开到新构建的数据库的连接：

```vim
：cs添加cscope.out
```

验证已建立连接：

```vim
：cs显示
```

（是的，您可以添加多个连接.）

### 3. Query the database

```vim
：cs查找<kind><query>
```

例如：：cs find d foo将列出所有由foo（...）调用的函数.

 | 种类| 说明|
|------|-------------|
 |  s |  ** s **符号：查找对令牌的所有引用|
 |  g |  ** g ** lobal：查找令牌的全局定义|
 |  c |  ** c ** alls：查找对该函数的所有调用|
 |  t |  ** t ** ext：查找文本的所有实例|
 |  e |  ** e ** grep：egrep搜索单词|
 |  f |  ** f ** ile：打开文件名|
 | 我 ** i **不包括：查找包含文件名的文件|
 |  d |  ** d **附加：查找此函数调用的函数|

我建议一些方便的映射，例如：

```vim
 nnoremap<buffer><leader>  cs：cscope查找s<c-r>  = expand（&#39;<cword>  &#39;）<cr><cr>
 nnoremap<buffer><leader>  cg：cscope查找g<c-r>  = expand（&#39;<cword>  &#39;）<cr><cr>
 nnoremap<buffer><leader>  cc：cscope查找c<c-r>  = expand（&#39;<cword>  &#39;）<cr><cr>
 nnoremap<buffer><leader>  ct：cscope查找t<c-r>  = expand（&#39;<cword>  &#39;）<cr><cr>
 nnoremap<buffer><leader>  ce：cscope查找e<c-r>  = expand（&#39;<cword>  &#39;）<cr><cr>
 nnoremap<buffer><leader>  cf：cscope查找f<c-r>  = expand（&#39;<cfile>  &#39;）<cr><cr>
 nnoremap<buffer><leader>  ci：cscope找到我^<c-r>  = expand（&#39;<cfile>  &#39;）<cr>  $<cr>
 nnoremap<buffer><leader>  cd：cscope查找d<c-r>  = expand（&#39;<cword>  &#39;）<cr><cr>
```

因此，当`：tag`（或`<c-]>  `）从标签文件`：cstag`跳转到定义.
这样做，但也考虑了连接的cscope数据库. 
选项`&#39;cscopetag&#39;`使`：tag`像`：cstag`一样自动工作. 这非常
如果您已经具有与标签相关的映射，则非常方便.

帮助：`：h cscope`

## MatchIt

由于Vim用C编写，因此许多功能都采用类似C的语法. 默认，
if your cursor is on `{` or `#endif`, you can use `%` to jump to the
corresponding `}` or `#ifdef` respectively.

Vim捆绑了一个名为matchit.vim的插件，该插件未启用
默认. 如果/ else / endif构造在
VimL等，并引入了一些新命令.

#### Installation for Vim 8

```vim
vimrc
 packadd！ 火柴
```

#### Installation for Vim 7 and older

```vim
vimrc
运行时宏/matchit.vim
```

由于matchit的文档非常广泛，因此我建议也
以下一次：

```vim
：！mkdir -p〜/ .vim / doc
：！cp $ VIMRUNTIME / macros / matchit.txt〜/ .vim / doc
：helptags〜/ .vim / doc
```

#### Small intro

该插件现在可以使用了. 有关支持的信息，请参见`：h matchit-intro`.
命令和`：h matchit-languages`以获取支持的语言.

也就是说，很容易定义自己的匹配对：

```vim
 autocmd FileType python让b：match_words =&#39;\<if\>  ：\<elif\>  ：\<else\>  &#39;
```

之后，您可以使用来循环遍历任何Python文件中的这3条语句
％（向前）或g％（向后）.

Help:

```
：h matchit-安装
：h matchit
：hb：match_words
```

## True colors

在终端仿真器中使用真彩色意味着能够将24位用于RGB
颜色. 这样就形成了16777216（2 ^ 24）种颜色，而不是通常的256种颜色.

如前所述 [here](#colorschemes)，colorschemes实际上可以是_two_
通过定义终端（xterm）和GUI（gvim）定义颜色.
在终端仿真器了解真彩色之前，这很有意义.

在`：set termguicolors`之后，Vim开始发出只能理解的转义序列.
由支持真实色彩的终端仿真器. 当你的颜色看起来很奇怪时
可能是您的终端模拟器不支持真彩色，或者您
colorcheme尚未定义GUI颜色.

很多人使用终端多路复用器
[tmux](https://github.com/tmux/tmux/wiki) 基本上位于
终端仿真器和Vim. 使tmux _forward_成为真实的颜色逃逸
Vim发出的序列，您必须在用户
`.tmux.conf`:

```
设置选项-g默认终端&#39;tmux-256color&#39;
设置选项-ga终端重写&#39;，xterm-256color：Tc&#39;
```

-第一行对于大多数人应该是相同的，并表示“ $ TERM”
  在_tmux中使用.
-第二行将tmux特有的“ Tc”（本色）功能添加到
   xterm-256color的其他terminfo条目. 显然，这是假设
  用户正在使用tmux的`TERM = xterm-256color` _outside_.

因此，这是启用真彩色的清单：

-阅读`：h&#39;termguicolors&#39;`.
-在您的vimrc中放入`set termguicolors`.
 -确保您的colorcheme具有GUI的颜色定义.  （应包含
  带有`guifg`和`guibg`的行.）
-确保您选择的终端仿真器支持真实色彩.
 -使用tmux？ 配置它以添加“ Tc”功能.

终端中流行的颜色参考：
https://gist.github.com/XVilka/8346728

## Tips

## Go to other end of selected text

可视选择中的“ o”和“ O”使光标移到另一端. 试试看
逐块选择以查看差异. 这对于快速更改很有用
所选文字的大小.

```
：小时v_o
：小时v_O
```

## Saner behavior of n and N

“ n”和“ N”的方向取决于是否将“ /”或“？”用于
分别向前或向后搜索. 这让我很困惑.

如果您希望n总是向前搜索而N则向后搜索，请使用以下命令：

```vim
 nnoremap<expr>  n&#39;Nn&#39;[v：searchforward]
 xnoremap<expr>  n&#39;Nn&#39;[v：searchforward]
 Onoremap<expr>  n&#39;Nn&#39;[v：searchforward]

 nnoremap<expr>  N&#39;nN&#39;[v：searchforward]
 xnoremap<expr>  N&#39;nN&#39;[v：searchforward]
 Onoremap<expr>  N&#39;nN&#39;[v：searchforward]
```

## Saner command-line history

如果您像我一样，习惯了通过
 `<c-n>  `和`<c-p> 分别. 默认情况下，这也适用于
命令行，并从历史记录中调出较旧或较新的命令行.

到现在为止还挺好. 但是<up> `和`<down>  `甚至更聪明！ 他们记得
开头与当前命令行匹配的命令行. 例如：: echo<up>  `
可能会更改为`：echo“ Vim岩石！”`.

当然，我不希望您到达箭头键，只需将其映射即可：

```vim
cnoremap<c-n><down>
cnoremap<c-p><up>
```

我一天几次依赖这种行为.

## Saner CTRL-L

默认情况下，<c-l>  `清除并重新绘制屏幕（如:: redraw！`）. 
接下来的映射也是如此，再取消突出显示通过`/`找到的匹配项，
`？`等，加上固定的语法高亮显示（有时Vim会由于高亮而丢失高亮显示
到复杂的突出显示规则），以及强制更新
差异模式：

```vim
 nnoremap<leader>  l：nohlsearch<cr>  ：diffupdate<cr>  ：syntax fromstart同步<cr><c-l>
```

## Disable audible and visual bells

```vim
设置无铃
设置无视铃
设置t_vb =
```

See [Vim Wiki: Disable beeping](http://vim.wikia.com/wiki/Disable_beeping).

## Quickly move current line

有时我需要一种快速的方法来将当前行移到上方或下方：

```vim
 nnoremap [e：<c-u> 执行“移动-1-”. 在：count1<cr>
 nnoremap] e：<c-u> 执行“移动+”. 在：count1<cr>
```

这些映射也需要计数，因此“ 2] e”将当前行移动到下面两行.

## Quickly add empty lines

```vim
 nnoremap [<space>  ：<c-u> 放！  =重复（nr2char（10），v：count1）<cr>  &#39;[
 nnoremap]<space>  ：<c-u> 把= repeat（nr2char（10），v：count1）<cr>
```

现在`5 [<space>  `在当前行上方插入5个空行.

## Quickly edit your macros

这是一颗真正的宝石！ 映射将获取一个寄存器（默认情况下为*）并打开
它在cmdline窗口中. 打`<cr>  `完成设置后的编辑
register.

我经常用它来纠正录制宏时所做的错别字.

```vim
 nnoremap<leader>  m：<c-u><c-r><c-r>  =&#39;让@&#39;.  v：register.  =&#39;. 字符串（getreg（v：register））<cr><c-f><left>
```

像这样使用它<leader> m`或`“ q<leader>  m`.

注意`的使用<c-r><c-r>以确保<c-r>插入了
从字面上看. 参见`：h c_ ^ R ^ R`.

## Quickly jump to header or source file

该技术可能可以应用于许多文件类型. 设置_file标记_
（请参见`：h标记`），当您离开源文件或头文件时，可以快速跳转
返回到最后使用“ C”或“ H”访问的地址（参见“：h&#39;A”）.

```vim
autocmd BufLeave *.{c，cpp}标记C
autocmd BufLeave * .h标记H
```

**注意**：信息保存在viminfo文件中，因此请确保`：set
viminfo？`包括`：h viminfo-&#39;.

## Quickly change font size in GUI

我认为这是从tpope的配置中获取的：

```vim
命令！ 更大的：let＆guifont = replace（＆guifont，&#39;\ d \ + $&#39;，&#39;\ = submatch（0）+1&#39;，&#39;&#39;）
命令！ 较小的：let＆guifont = replace（＆guifont，&#39;\ d \ + $&#39;，&#39;\ = submatch（0）-1&#39;，&#39;&#39;）
```

## Change cursor style dependent on mode

我喜欢在普通模式下使用块光标，在插入模式下使用i型光束光标，并且
在替换模式下将光标置于下划线.

```vim
如果为空（$ TMUX）
  让＆t_SI =“ \<Esc>  ] 50; CursorShape = 1 \ x7“
  让＆t_EI =“ \<Esc>  ] 50; CursorShape = 0 \ x7“
  让＆t_SR =“ \<Esc>  ] 50; CursorShape = 2 \ x7“
else
  让＆t_SI =“ \<Esc>  Ptmux; \<Esc>  \<Esc>  ] 50; CursorShape = 1 \ x7 \<Esc>  \\“
  让＆t_EI =“ \<Esc>  Ptmux; \<Esc>  \<Esc>  ] 50; CursorShape = 0 \ x7 \<Esc>  \\“
  让＆t_SR =“ \<Esc>  Ptmux; \<Esc>  \<Esc>  ] 50; CursorShape = 2 \ x7 \<Esc>  \\“
endif
```

这只是告诉Vim打印一定的字符序列（[转义
进入/离开时的序列]（https://en.wikipedia.org/wiki/Escape_sequence））
插入模式. 基础终端或类似程序
[tmux](https://tmux.github.io) 位于Vim和终端之间
处理和评估.

但是有一个缺点：有许多终端仿真器实现
并非所有人都使用相同的序列来做相同的事情. 使用的序列
以上可能不适用于您的实施. 您的实现可能不会
甚至支持不同的光标样式. 检查文档.

上面的示例适用于iTerm2.

## Don't lose selection when shifting sidewards

如果选择一个或多个行，则可以使用`&lt;`和`&gt;`来移动它们
向侧面. 不幸的是，之后您立即失去选择.

您可以使用`gv`重新选择最后一个选择（参见`：h gv`），这样您就可以工作了
像这样围绕它：

```vim
xnoremap &lt;
xnoremap &gt;&gt; gv
```

现在，您可以在视觉选择中使用`&gt;&gt;&gt;&gt;&gt;`，而不会出现任何问题.

**注意**：使用`.`可以实现相同的效果，重复上一次更改.

## Reload a file on saving

Using [autocmds](#autocmds) 您可以在保存文件上做任何事情，例如采购
如果是dotfile或运行linter以检查是否存在语法错误
您的源代码.

```vim
autocmd BufWritePost $ MYVIMRC源$ MYVIMRC
autocmd BufWritePost〜/ .Xdefaults调用系统（&#39;xrdb〜/ .Xdefaults&#39;）
```

## Smarter cursorline

我喜欢光标线，但我只想在当前窗口中使用它
处于插入模式时：

```vim
autocmd InsertLeave，WinEnter *设置光标线
autocmd InsertEnter，WinLeave *设置nocursorline
```

## Faster keyword completion

关键字完成（`<c-n>  `/`<c-p>  `）尝试完成列出的内容
 &#39;&#39;complete&#39;`选项. 默认情况下，它还包括标签（可以是
烦人）并扫描所有包含的文件（这可能非常慢）. 如果你可以的话
生活中没有这些东西，禁用它们：

```vim
设置完成-= i“禁用扫描包含的文件
设置complete- = t“禁用搜索标签
```

## Cosmetic changes to colorschemes

无论选择哪种颜色方案，请始终使用深灰色状态线：

```vim
autocmd ColorScheme *高亮显示StatusLine ctermbg = darkgray cterm = NONE guibg = darkgray gui = NONE
```

每次您使用`：colorscheme ...`时都会触发. 如果要触发
仅适用于某些颜色方案：

```vim
autocmd ColorScheme沙漠高亮显示StatusLine ctermbg = darkgray cterm = NONE guibg = darkgray gui = NONE
```

仅对`：colorscheme desert&#39;触发.

## Commands

有用的有用命令. 使用`：h：<command name>  `了解更多
关于它们的信息，例如`：h：global`.

## :global and :vglobal

在所有匹配的行上执行命令. 例如`：global / regexp / print`将使用
在包含“ regexp”的所有行上使用`：print`.

有趣的事实：你们可能都知道旧的grep，这是Ken编写的过滤程序
汤普森它有什么作用？ 它打印与某个常规匹配的所有行
表达！ 现在猜想`：global / regexp / print`的缩写形式？ 那就对了！
是`：g / re / p`. 肯·汤普森（Ken Thompson）在写grep时受到vi的`：global`的启发.

尽管它的名字是`：global`，默认情况下它只作用于所有行，但是它也需要
一个范围. 假设您要在从当前行到当前行的所有行上使用`：delete`.
包含“ foo”的下一个空行（与正则表达式^ $`匹配）：

```vim
:,/^$/g/foo/d
```

要在不匹配给定模式的所有行上执行命令，请使用
`：global！`或其别名`：vglobal`（认为_inVerse_）.

## :normal and :execute

这些命令通常在Vim脚本中使用.

使用`：normal`可以从命令行进行普通模式的映射. 例如
 `：正常！  4j`将使光标下降4行（不使用任何自定义
由于“！”而映射到“ j”）.

记住`：normal`也需要一个 [range](#ranges) ，所以`：％norm！  Iabc`会
在每行前面加上“ abc”.

使用`：execute`可以混合使用命令和表达式. 假设您编辑一个C
源文件并想要切换到其头文件：

```vim
 ：execute&#39;edit&#39;fnamemodify（expand（&#39;％&#39;），&#39;：r&#39;）.  &#39;.H&#39;
```

这两个命令经常一起使用. 假设您要移动光标
在“ n”行中：

```vim
：let n = 4
 ：执行“正常！”  n.  &#39;j&#39;
```

## :redir and execute()

许多命令打印消息，`：redir`允许重定向该输出. 您
可以重定向到文件， [registers](#registers) 或变量.

```vim
：redir =&gt; var
:reg
：redir结束
：echo var
：“有趣的是，我们也将其放在当前缓冲区中.
：把= var
```

在Vim 8中，有一个更短的方法：

```vim
：put = execute（&#39;reg&#39;）
```

Help:

```
：h：redir
：h execute（）
```

## Debugging

## General tips

如果遇到奇怪的行为，请尝试按以下方式重现它：

```
-u无-N
```

这将在没有vimrc（因此为默认设置）且不兼容的情况下启动Vim.
模式（这使其使用Vim默认值而不是vi默认值）.  （参见`：h
--noplugin`，以了解启动时要加载的内容的其他组合.）

如果您现在仍然可以重现它，则很可能是Vim本身的错误！ 报告
它到 [vim_dev](https://groups.google.com/forum/#!forum/vim_dev) 邮寄
清单. 在大多数情况下，此刻此问题无法解决，您将
进一步调查.

插件通常会引入新的/更改的/错误的行为. 例如，如果发生
保存后，检查`：verb au bufWritePost`以获得潜在罪魁祸首的列表.

如果您使用的是插件管理器，请将其注释掉，直到找到罪魁祸首.

问题仍然没有解决？ 如果不是插件，则必须是您的其他插件
设置，因此可能是您的选项或autocmds等.

是时候使用二进制搜索了. 反复将搜索空间一分为二，直到您
找到罪魁祸首. 由于二进制除法的性质，它不需要很多
steps.

实际上，它是这样工作的：将`：finish`命令放在您的中间
 vimrc.  Vim将跳过所有内容. 如果仍然发生，则问题出在
活跃的上半部分. 将`：finish`移动到_that_一半的中间.
否则，问题出在非活动的下半部分. 将`：finish`移到
那一半的中间. 等等.

## Verbosity

观察Vim当前正在执行的另一种有用方法是增加
详细程度. 目前，Vim支持9个不同级别. 参见`：h&#39;verbose&#39;`
查看完整列表.

```vim
：e / tmp / foo
：set verbose = 2
:w
：set verbose = 0
```

这将显示所有来源的文件，例如撤消文件或各种
用于保存的插件.

如果您只想增加单个命令的详细程度，则还有
 `：verbose`，它只是放在任何其他命令的前面. 它需要
详细级别为count，默认为1：

```vim
：verb设置详细
“ verbose = 1
：10动词设置详细
“详细= 10
```

它经常与默认详细级别1结合使用，以显示选项的位置
最后设置：

```vim
：动词设置为AI？
“最后一个来自〜/ .vim / vimrc
```

自然，详细程度越高，输出越不堪重负. 但
不用担心，您只需将输出重定向到文件即可：

```vim
 ：set verbosefile = / tmp / foo |  15详细回显“ foo” |  vsplit / tmp / foo
```

您还可以在开始时使用-V选项启用详细信息. 它
默认为详细级别10.例如`vim -V5`.

## Profiling startup time

 Vim启动感觉慢吗？ 是时候计算一些数字了：

```
vim --startuptime /tmp/startup.log + q &amp;&amp; vim /tmp/startup.log
```

The first column is the most important as it shows the elapsed absolute time. If
两行之间的时间跨度很大，第二行是
大文件或VimL代码错误的文件值得研究.

## Profiling at runtime

Required [feature](#what-kind-of-vim-am-i-running)：`+ profile`

Vim提供了一种内置功能，可在运行时进行性能分析，是一种很好的方法
在您的环境中查找慢速代码.

`：profile`命令使用一堆子命令来指定要执行的操作.
profile.

如果要配置_everything_，请执行以下操作：

    ：profile开始/tmp/profile.log
    ：配置文件*
    ：profile func *
    <do something in Vim>
    ：qa

Vim将分析信息保留在内存中，仅将其写到
退出时的日志文件.  （Neovim已使用`：profile dump`修复了该问题）.

看看`/ tmp / profile.log`. 分析期间执行的所有代码
将显示. 每行，执行的频率和花费的时间.

跳到日志底部. 这是两个不同的部分
值得一试的“总时间”和“自定义时间功能”. 在
快速浏览一下，您可以看到哪些功能花费的时间最长.

您也可以在启动过程中使用`：profile`：

     $ vim --cmd&#39;教授开始prof.log | 教授文件* | 教授*&#39;test.c
    ：q
    $ tail -50 prof.log

## Debugging Vim scripts

如果您以前使用过命令行调试器，`：debug`将会很快让您感到
familiar.

只需在任何其他命令前加上：debug，您就会进入调试模式.
也就是说，执行将在即将执行的第一行停止，并且
将显示一行.

有关6个可用的调试器命令，请参见`：h&gt; cont`及以下内容，请注意，
像在gdb和类似的调试器中一样，您也可以使用其简短形式：`c`，`q`，
`n`，`s`，`i`和`f`.

除此之外，您还可以自由使用任何Vim命令，例如`：echo myvar`，
它在代码中当前位置的上下文中执行.

你基本上得到一个
[REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) 通过
只需使用`：debug 1`.

如果必须单步执行每一行，那将是一件痛苦的事情，因此
当然我们也可以定义断点.  （断点称为断点，
因为当它们被击中时执行会停止，因此您只需跳过代码
您不感兴趣.）请参见`：h：breakadd`，`：h：breakdel`和`：h
：breaklist`了解更多详细信息.

假设您想知道每次保存文件时都运行什么代码：

```vim
：在BufWritePost
”表示BufWritePost
"     *         call sy#start()
：breakadd func *开始
:w
" Breakpoint in "sy#start" line 1
“进入调试模式.键入” cont“继续.
" function sy#start
“第1行：如果g：signify_locked
>s
" function sy#start
”第3行：endif
>
" function sy#start
“第5行：let sy_path = resolve（expand（&#39;％：p&#39;））
>q
：breakdel *
```

如您所见，使用`<cr>  `将重复上一个调试器命令，即s
这个案例.

`：debug`可以与 [verbose](#verbosity) 选项.

## Debugging syntax files

语法文件通常是由于错误和/或复杂而导致速度降低的原因
在编译时，Vim提供了超级有用的`：syntime`命令.

```vim
：同步时间
 ”命中<c-l>几次以重新绘制窗口，从而导致再次应用语法规则
：同步关闭
：syntime报告
```

输出包含重要指标. 例如，您也可以查看使用哪个正则表达式
时间长，应该进行优化，或者始终使用哪些正则表达式，但是永远不要
甚至匹配.

参见`：h：syntime`.

## Miscellaneous

## Additional resources

 | 资源| 描述
|----------|-------------|
| [Seven habits of effective text editing](http://www.moolenaar.net/habits.html)  |  Vim的作者Bram Moolenaar.  |
| [Seven habits of effective text editing 2.0 (PDF)](http://www.moolenaar.net/habits_2007.pdf) | See above. |
| [IBM DeveloperWorks: Scripting the Vim editor](http://www.ibm.com/developerworks/views/linux/libraryview.jsp?sort_order=asc&sort_by=Title&search_by=scripting+the+vim+editor)  | 关于Vim脚本的五部分系列.  |
| [Learn Vimscript the Hard Way](http://learnvimscriptthehardway.stevelosh.com)  | 从头开始开发Vim插件.  |
| [Practical Vim (2nd Edition)](http://www.amazon.com/Practical-Vim-Edit-Speed-Thought/dp/1680501275/)  | 传授有关Vim的最好的书.  |
| [Why, oh WHY, do those #?@! nutheads use vi?](http://www.viemu.com/a-why-vi-vim.html)  | 常见的误解得到了解释.  |
| [Your problem with Vim is that you don't grok vi](http://stackoverflow.com/a/1220118)  | 简明，翔实和正确. 一个真正的宝石.  |

#### Screencasts

- [vimcasts.org](http://vimcasts.org/episodes/archive)
- [By wincent](https://www.youtube.com/channel/UCXPHFM88IlFn68OmLwtPmZA)
- [By Derek Wyatt](http://derekwyatt.org/vim/tutorials/index.html)

## Vim distributions

Vim发行版是Vim的自定义设置和插件的捆绑包.

更高级的用户知道如何仍然配置他们的编辑器，因此发行版
主要针对初学者. 如果你考虑一下，那是相当
矛盾的是：通过添加更多要学习的东西使它变得更容易吗？

我知道许多人不想花很多时间来定制
编辑器（实际上，当您最终获得
迷上了），但最终，只有花点时间才能在Vim中高效
正确学习.

在我之后重复一遍：“程序员应该知道他们的工具.”

无论如何，如果您知道自己在做什么，则可能会从中得到一些启发
看一些分布：

- [cream](http://cream.sourceforge.net)
- [janus](https://github.com/carlhuda/janus.git)
- [spacevim](https://github.com/SpaceVim/SpaceVim)
- [spf13](https://github.com/spf13/spf13-vim)

## Standard plugins

Vim附带了一些标准，这让很多人感到惊讶
插件. 有些默认加载（`：e $ VIMRUNTIME / plugin），有些没有
 （`：e $ VIMRUNTIME / pack / dist / opt`）. 阅读`：h pack-add`了解如何获取
latter.

不过，大多数默认加载的插件将永远不会使用.
视需要禁用它们. 它们仍将显示为来源
（`：scriptnames`），但实际上只有前几行在Vim释放之前被读取
出来. 不会再处理其他代码（映射，命令，逻辑）.

 | 插件| 禁用它. 帮助|
|------------|-------------------------------------|------|
 |  2html | 让let g：loaded_2html_plugin = 1  `：h 2html` |
 | 脚本| 让g：loaded_getscriptPlugin = 1 |  `：h pi_getscript` |
 |  gzip |  `let g：loaded_gzip = 1` |  `：h pi_gzip` |
 |  logipat | 让g：loaded_logipat = 1 |  `：h pi_logipat` |
 | 配对|  `let g：load_matchpairs = 1` |  `：h pi_paren` |
 |  netrw | 让g：loaded_netrwPlugin = 1 |  `：h pi_netrw` |
 |  rrhelper |  `let g：loaded_rrhelper = 1` |  `：e $ VIMRUNTIME / plugin / rrhelper.vim` |
 | 拼写文件| 让g：loaded_spellfile_plugin = 1  `：h spellfile.vim` |
 | 焦油| 让g：loaded_tarPlugin = 1 |  `：h pi_tar` |
 |  vimball | 让G：loaded_vimballPlugin = 1  `：h pi_vimball` |
 | 拉链让let g：loaded_zipPlugin = 1  `：h pi_zip` |

## Map CapsLock to Control

CapsLock属于键盘上最无用的键，但要容易得多
因为它位于您的[home
row](https://raw.githubusercontent.com/mhinz/vim-galore/master/static/images/content-homerow.png).
将CapsLock映射到Control是防止或至少减少CapsLock的好方法
[RSI](https://de.wikipedia.org/wiki/Repetitive-Strain-Injury-Syndrom) 如果你
编程很多.

注意：一旦习惯了，就不能没有它了.

**macOS**:

系统偏好设置-&gt;键盘-&gt;键盘标签-&gt;修改键. 更改
将“ CapsLock”更改为“ Control”.

**Linux**:

要更改X中的键，请将其放在`〜/ .xmodmap`中：

    删除锁= Caps_Lock
    键符Caps_Lock = Control_L
    添加控件= Control_L

然后通过`$ xmodmap〜/ .xmodmap`来获取它.

一种替代方法是使用 [caps2esc](https://github.com/oblitum/caps2esc) 要么
[xcape](https://github.com/alols/xcape).

**Windows**:

请参阅[superuser.com：将Caps-Lock映射到Windows中的控件
8.1](http://superuser.com/questions/764782/map-caps-lock-to-control-in-windows-8-1).

## Generating HTML from buffer

从2html [standard使用`：TOhtml`从任何缓冲区生成HTML.
plugin](#standard-plugins). The output can be used for printing or easy web
publishing.

该命令创建一个新的同名缓冲区，并附加`.html`. 
颜色与Vim中的颜色相同. 他们取决于
[colorscheme](#colorschemes).

该插件知道几种用于微调输出的选项，例如用于设置
编码和字体.

参见`：h：TOhtml`.

## Easter eggs

 | 指令| 留言|
|-----------|---------|
 |  `：Ni！`|  “你需要灌木丛吗？” |
 |  `：h&#39;sm&#39;` |  `注意：使用缩写形式的等级为PG.
 |  `：h 42` | 生命，宇宙和一切的含义是什么？ 不幸的是，唯一一个真正知道这个问题的人道格拉斯·亚当斯现在已经死了. 所以现在您可能想知道死亡的含义是什么.
 |  `：h UserGettingBored` |  `当用户按相同键42次时. 开玩笑！  :-)`|
 |  `：h bar` |  `这不是管道.
 |  `：h圣杯`|  “你找到了，亚瑟！” |
 |  `：h map-modes` |  `：nunmap也可以在修道院外使用.
 |  `：help！`|  “ E478：不要惊慌！”（小故障？在帮助缓冲区（buftype = help）中使用时，它的工作方式类似于：: h help.txt）.
 |  `：smile` | 自己尝试一下.  ;-)在7.4.1005中添加.  |

## Why hjkl for navigation?

When [Bill Joy](https://en.wikipedia.org/wiki/Bill_Joy) 被创造
[vi](https://en.wikipedia.org/wiki/Vi)是Vim的前身，他是在
[ADM-3A](https://en.wikipedia.org/wiki/ADM-3A) 没有多余的光标按钮
但是使用过，您可能已经猜到了，而不是hjkl.

键盘布局： [click](https://raw.githubusercontent.com/mhinz/vim-galore/master/static/images/content-adm-3a-layout.jpg)

这也说明了为什么在Unix系统上使用〜来表示主目录.

## Common problems

## Editing small files is slow

有两件事会对性能产生巨大影响：

 1.复杂的“正则表达式”. 特别是Ruby语法文件引起
   人们过去曾经放慢脚步.  （另请参阅 [Debugging syntax files](#debugging-syntax-files).)
 2. **屏幕重绘**. 一些功能会强制所有线条重新绘制.

 | 罪魁祸首| 为什么？  | 解？  |
|-----------------|------|-----------|
 |  `：set cursorline` | 使所有线条重绘.  |  `：set nocursorline` |
 |  `：set cursorcolumn` | 使所有线条重绘.  |  `：set nocursorcolumn` |
 |  `：set relativenumber` | 使所有线条重绘.  |  `：set norelativenumber` |
 |  `：set foldmethod =语法`| 如果语法文件已经很慢，那就更糟了.  |  `：set foldmethod = manual`，`：set foldmethod = marker`或 [FastFold](https://github.com/Konfekt/FastFold) |
 |  `：set synmaxcol = 3000` | 由于内部表示，Vim通常会遇到长行问题. 突出显示列直到列3000.  `：set synmaxcol = 200` |
 |  matchparen.vim | 默认加载. 使用正则表达式查找随附的括号.  | 禁用插件：`：h matchparen` |

**注意**：仅当您遇到实际效果时才需要这样做
缺点. 在大多数情况下，使用上述内容绝对可以.

## Editing huge files is slow

大文件的最大问题是Vim一次读取整个文件. 这个
由于缓冲区在内部的表示方式而完成.
([Discussion on vim_dev@](https://groups.google.com/forum/#!topic/vim_dev/oY3i8rqYGD4/discussion))

如果您只想阅读，`tail hugefile |  vim -`是一个很好的解决方法.

如果暂时没有语法，设置和插件，您可以进行以下操作：

```
$强制-Q无-N
```

这应该使导航快很多，尤其是因为它不贵
使用语法高亮的正则表达式. 您还应该告诉Vim
不要使用swapfiles和viminfo文件，以避免长时间的写入延迟：

```
$ vim -n -u NONE -i NONE -N
```

简而言之，在打算真正编写时尽量避免使用Vim
大文件.  ：\

## Bracketed paste (or why do I have to set 'paste' all the time?)

括号粘贴模式允许终端仿真器区分键入的文本
和粘贴的文本.

您是否曾经尝试将代码粘贴到Vim中，然后一切似乎都混乱了
up?

只有通过“ cmd + v”，“ shift-insert”，“ middle-click”等粘贴时，才会发生这种情况.
because then you're just throwing text at the terminal emulator. Vim doesn't
知道您刚刚粘贴了文字，就认为您是一位非常快速的打字员.
因此，它尝试缩进行并失败.

显然，这不是问题，如果使用Vim的寄存器（例如，“ + p”）进行粘贴，
因为那样Vim知道您实际上正在粘贴.

要解决此问题，您必须`：set paste`，使其按原样粘贴. 参见`：h
&#39;paste&#39;`和`：h&#39;pastetoggle&#39;`.

如果您一直都厌倦了切换“&#39;paste&#39;`”，请看一下
为您完成的插件：
[bracketed-paste](https://github.com/ConradIrwin/vim-bracketed-paste).

与该插件来自同一作者的其他阅读：
[here](http://cirw.in/blog/bracketed-paste).

** Neovim **：Neovim试图使所有这些变得更加无缝，并进行设置
如果终端仿真器支持，则自动粘贴方括号粘贴模式.

## Delays when using escape key in terminal

如果您生活在命令行中，则可能使用所谓的_terminal
emulator_，例如xterm，gnome-terminal，iTerm2等（与实数相对
[terminal](https://en.wikipedia.org/wiki/Computer_terminal)).

就像他们的祖先一样，终端模拟器使用[转义
序列]（https://en.wikipedia.org/wiki/Escape_sequence）（或_control
sequence_）以控制诸如移动光标，更改文本颜色等操作.
它们只是以转义字符开头的ASCII字符串
（显示在 [caret notation](https://en.wikipedia.org/wiki/Caret_notation) 如
 `^ [`）. 当这样的字符串到达​​时，终端仿真器查找
伴随行动 [terminfo](https://en.wikipedia.org/wiki/Terminfo)
database.

为了使问题更清楚，我将首先解释映射超时. 他们总是
当映射之间存在歧义时发生：

```vim
：nnoremap，a：echo&#39;foo&#39;<cr>
：nnoremap，ab：回显&#39;bar&#39;<cr>
```

两种映射均按预期工作，但是在键入`，a`时将延迟1
其次，因为Vim等待用户是否键入另一个`b`.

转义序列引起相同的问题：

 -`<esc>  `通常用于返回正常模式或退出操作.
-使用转义序列对光标键进行编码.
-Vim希望<kbd>Alt</kbd> （也称为_Meta key_）发送适当的8位
  高位编码，但许多终端仿真器不支持
  （或默认情况下不启用它）并发送转义序列.

您可以像这样测试上面的内容：`vim -u NONE -N`并输入`i<c-v><left>  `和
您会看到插入的序列以`^ [`开头，表示转义
character.

简而言之，Vim很难区分类型
 `<esc>  `字符和正确的转义序列.

默认情况下，Vim使用`：set timeout timeoutlen = 1000`，因此会延迟歧义.
 _ _键映射的映射时间减少1秒. 这是映射的合理值，但是
您可以自行定义最常用的密钥超时
整个问题的解决方法：

```vim
为映射设置超时
设置timeoutlen = 1000“默认值
设置ttimeout为关键代码
设置ttimeoutlen = 10“很小的值
```

在`：h ttimeout`下，您可以找到一张小表，显示之间的关系
这些选项.

If you're using tmux between Vim and your terminal emulator, also put this in
您的`〜/ .tmux.conf`：

```tmux
设置-sg转义时间0
```

## Function search undo

-命令中的搜索模式（`/`，`：substitute`，...）会更改“最后使用
  搜索模式”.（保存在`/`寄存器中；使用`：echo @ /`打印）.
 -可以使用`.`重做一个简单的文本更改.  （它保存在`.`寄存器中；
  用`：echo @ .`打印）.

但是，如果您从函数中进行操作，这两种情况都不是！ 这样你
无法轻松突出显示功能中的单词或重做由
it.

帮助：`：h function-search-undo`

## Technical quirks

## Newline used for NUL

文件中的NUL字符（\ 0）作为换行符（\ n）存储在内存中，
在缓冲区中显示为“ ^ @”.

有关更多信息，请参见`man 7 ascii`和`：h NL-for-Nul`.

## Terminology

## Vim script? Vimscript? VimL?

Vim脚本，Vimscript和VimL都指同一件事：
用于编写Vim脚本的编程语言. 即使
[8.0.360](https://github.com/vim/vim/commit/b544f3c81f1e6a50322855681ac266ffaa8e313c)
将所有对“ VimL”的引用更改为“ Vim脚本”，现在可以考虑
官方术语“ VimL”仍然在互联网上广泛传播.

无论您使用哪个术语，每个人都会理解它.
