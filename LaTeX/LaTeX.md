## 安装

### 安装 LaTeX

> [TeXLive](http://www.ctex.org/TeXLive) 是由国际 [TeX](http://www.ctex.org/TeX) 用户组织 TUG 开发的 [TeX](http://www.ctex.org/TeX) 系统，支持不同的操作系统平台。其 Windows 版本又称 fpTeX ， Unix/Linux 版本即著名的 teTeX 。
>
> 网址：http://tug.org/texlive/
>
> <p style="text-align:right">——http://www.ctex.org/texlive</p>

#### 下载地址

因为 TeX Live 的安装镜像高达 3.7G，所以[官方](https://www.tug.org/texlive/)提供了多种下载方式：

+ ISO 镜像：[清华大学镜像站](https://mirrors.tuna.tsinghua.edu.cn/CTAN/systems/texlive/Images/)（下载名为 texlive.iso 的文件即可）
+ 运行安装程序：[清华大学镜像站](https://mirrors.tuna.tsinghua.edu.cn/CTAN/systems/texlive/Source/)（下载名为 install-tl-unx.tar.gz 的文件即可）
+ 其他下载方式：[TeX Live availability](https://www.tug.org/texlive/acquire.html)

#### 安装

如果你下载的是完整的 ISO 镜像，下载完成以后直接打开（如果是低于 Windows 10 的系统，可以下载可以加载虚拟光驱的软件，例如：Daemon tool lite）。

打开后找到名为 install-tl-windows.bat 的文件（如果是过往的，例如低于 20200406 的可能会有其他类似的名字，认准后缀名为 .bat 的文件即可。）右键使用管理员权限打开该文件即可进入安装界面。

![texlive-install-p1](https://raw.githubusercontent.com/Soanguy/imgbak/master/img/texlive-install-p1.png)

当然，我们可以通过点击 **Advanced** 来来决定安装的具体内容和地址。建议其他的选项不需要更改，在该界面更改安装位置即可。

之后可以点击 Advanced 来选择免安装一些不需要的语言包。该选项在 Advanced 下的：

![texlive-install-p2.png](https://raw.githubusercontent.com/Soanguy/imgbak/master/img/texlive-install-p2.png)

点击 **Customize** 即可选择或者取消一些自己不需要的语言包。

之后一路okay即可。安装过程需要经过一个漫长的等待。

### 配置编辑器

#### 安装 VS Code

[官方下载页](https://code.visualstudio.com/Download)

> 如果是 Windows，推荐下载 system installer。

下载结束之后依然使用系统管理权限安装。

#### 安装 VS Code 插件

在 VS Code 插件市场内搜索 latex workshop，并安装。

![texlive-install-p3](https://raw.githubusercontent.com/Soanguy/imgbak/master/img/texlive-install-p3.png)

之后新建一个 tex 文件并输入以下文字测试程序是否安装正确。

```latex
\documentclass{article}
\usepackage{lipsum}
\begin{document}
\lipsum[1]
\[
    a^2 + b^2 = c^2
\]
\lipsum[2]
\end{document}
```

如果一切正常，那么在点击右上角的 ![normal](https://raw.githubusercontent.com/Soanguy/imgbak/master/img/texlive-install-p4.png)（或者使用快捷键 <kbd>CTRL</kbd>+<kbd>ALT</kbd>+<kbd>V</kbd> 打开 PDF 预览）就可以成功的编译出来。

![texlive-install-p6](https://raw.githubusercontent.com/Soanguy/imgbak/master/img/texlive-install-p6.png)

当然，可有可能会收到如下的错误提醒：

```bash
Recipe terminated with fatal error: spawn latexmk ENOENT.
```

> 出现该错误的原因很可能是因为在安装时选择了非默认的安装路径。此时需要将 Tex Live 添加到系统路径当中。
>
> + 打开文件管理器，右击计算机并选择 **属性**，在设置界面找到 **高级系统设置**
> + 点击打开的页面最下方的 **环境变量**→**系统变量**→**path**（下拉就可以找到这个变量，之后点击）→**编辑**→**新增**→输入 `D:\Disms\texlive\2020\bin\win32`（这是你自己的 TeX Live 安装路径，本文假设安装在 D:\Disms\ 目录下）
> + 之后不断确认即可。
> + 重启计算机。

### 配置LaTeX Workshop

[LaTeX 编译环境配置](https://github.com/EthanDeng/vscode-latex)