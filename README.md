
目录* [使用 brew 安装特定版本软件](https://github.com)
	+ [背景](https://github.com)
	+ [方法一：直接安装](https://github.com)
	+ [方法二：利用历史的 rb 文件安装](https://github.com)
	+ [参考资料](https://github.com)

# 使用 brew 安装特定版本软件


## 背景


`brew` 是 Mac 下非常好用的包管理工具，可以方便的下载并安装各种软件，类似于 Ubuntu 下的 `apt-get` 以及 centos 下的 `yum`


但是 `brew` 使用 `git` 来管理软件包，所以安装的软件包版本会随着其源仓库的更新而更新


如果需要安装旧版本软件，相对麻烦，这里记录一下方法


## 方法一：直接安装


部分软件包可以直接通过 brew install 安装指定版本，例如 `python`



```


|  | brew search python@ |
| --- | --- |
|  | ==> Formulae |
|  | python@3.10         python@3.12 ✔       python@3.8 |
|  | python@3.11         python@3.13 ✔       python@3.9 |
|  |  |
|  | # 安装 python 3.10 |
|  | brew install python@3.10 |


```

## 方法二：利用历史的 rb 文件安装


先利用 brew info 找到其 rb 文件的地址，然后去 GitHub 上找到历史版本的 rb 文件


* 下载/复制文本到本地，然后使用该 rb 文件安装
* 或者只用用该文件的链接地址安装


下面以安装 hugo 0\.136\.5 为例



```


|  | # 查看 hugo 信息 |
| --- | --- |
|  | brew info hugo |
|  | ==> hugo: stable 0.139.4 (bottled), HEAD |
|  | Configurable static site generator |
|  | https://gohugo.io/ |
|  | Installed |
|  | /opt/homebrew/Cellar/hugo/0.136.5 (53 files, 68.8MB) * |
|  | Poured from bottle on 2024-12-11 at 23:27:01 |
|  | From: https://github.com/Homebrew/homebrew-core/blob/HEAD/Formula/h/hugo.rb |
|  | License: Apache-2.0 |
|  | ==> Dependencies |
|  | Build: go ✘ |
|  | ==> Options |
|  | --HEAD |
|  | Install HEAD version |
|  | ==> Caveats |
|  | zsh completions have been installed to: |
|  | /opt/homebrew/share/zsh/site-functions |
|  | ==> Analytics |
|  | install: 15,963 (30 days), 49,454 (90 days), 203,875 (365 days) |
|  | install-on-request: 15,967 (30 days), 49,453 (90 days), 203,857 (365 days) |
|  | build-error: 52 (30 days) |


```

访问下 [https://github.com/Homebrew/homebrew\-core/blob/HEAD/Formula/h/hugo.rb](https://github.com):[slowerssr加速器](https://slowerss.com)


![进入 history 页面](https://img2024.cnblogs.com/blog/2829204/202412/2829204-20241217142703416-1134643174.png)


在 history 中找到需要的版本，然后复制链接地址


![寻找需要的版本](https://img2024.cnblogs.com/blog/2829204/202412/2829204-20241217142725038-922080098.png)


![复制链接地址](https://img2024.cnblogs.com/blog/2829204/202412/2829204-20241217142732946-2108517790.png)


然后在本地安装即可



```


|  | # 下载 rb 文件并安装 |
| --- | --- |
|  | wget https://raw.githubusercontent.com/Homebrew/homebrew-core/HEAD/Formula/h/hugo.rb |
|  | brew install ./hugo.rb |
|  |  |
|  | # 或者直接使用链接地址 |
|  | brew install https://raw.githubusercontent.com/Homebrew/homebrew-core/HEAD/Formula/h/hugo.rb |


```

## 参考资料


* [【stackoverflow】Homebrew install specific version of formula?](https://github.com)
* [【个人博客】工具 \- brew install 安装指定版本软件（protobuf 为例）](https://github.com)



> **本文作者：** ywang\_wnlo
> **本文链接：** [https://ywang\-wnlo.github.io/posts/89785ced/](https://github.com)
> **版权声明：** 本博客所有文章除特别声明外，均采用 [BY\-NC\-SA](https://github.com) 许可协议。转载请注明


