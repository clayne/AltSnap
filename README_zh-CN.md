[English](./README.md) | 中文文档 | [한국어](./README_ko-KR.md)
# AltSnap
由Stefan Sundin制作的一个AltDrag的分支。

查看Wiki：https://github.com/RamonUnch/AltSnap/wiki

原始文档：https://stefansundin.github.io/altdrag/doc/

请注意，因为这是一个分支，所以文档并不是100%准确的。
请通过阅读更新日志来了解更多详细信息。

它允许您通过按住Alt键并单击窗口上的任何位置来移动和调整窗口大小，并不需要任何非常精确的单击。
这种方式在Linux发行版上很常见，在Windows上其实也并不难实现。

这个分支的目标是在保持功能丰富的情况下同时让最新版本的错误最少。

尽管它主要在Windows XP和Windows 10 上进行测试，但它理论上应该可以在Windows NT 4到Windows 10之间的任何Windows版本上使用，

与原版主要的不同：
为了大大简化代码，Hooks窗口的功能被删除，它允许在正常拖动窗口的同时捕捉窗口。然而，它需要在每个应用程序中注入一个dll，从而导致了明显的安全风险。仅仅为了这个特性而添加到代码中的混乱程度是巨大的，此外还被迫同时运行32位和64位版本的程序。

此版本不向其他应用程序注入任何内容。这意味着您不必担心您使用的是32位还是64位操作系统。

另一个被禁用的功能是“专注于打字”，我甚至无法开始测试这个功能，所以我删除了它。

除此之外，它还有一个简单得多的源代码，添加了一些额外的选项，如透明窗口拖动、最大化操作、暂停进程选项、更多用于更精细地控制AltSnap的黑名单等。

最后，它修复了原始AltDrag中的大量不良行为和错误。

新东西：

在选项对话框中可以看到许多新功能，但其中一些功能只能通过编辑AltSnap.ini文件才能使用（用鼠标中键单击该文件的托盘图标）。

# 构建
AltSnap使用gcc构建，我使用Mingw-w64（对于i686）。
只需要安装最新版本（我使用基于MinGW64的TDM-gcc 10.3）并使用：
`> make` 用于i386 Win32的构建
`> make -fMakefileX64` 用于x86_64构建。
`> make -fMakefileX64db` 用于构建x86_64的调试版本。
您也可以使用mk.bart和mk64.bat文件。