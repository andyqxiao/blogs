使用自带内核（Chrome）作为App的HTML5宿主的思路：

Android从4.4开始，集成了Chromium项目，即从这个版本开始，Android上的Web Browser与Chrome的实现一致，只是低版本的Chrome.比如，Android5.1的Web Browser的版本是39，对应Chrome的版本为39.

Chrome与Android Web Browser之前版本（4.4之前）最大的区别是Chrome使用了V8作为JavaScript解释器，但Android Web Browser使用JSCore.这在我们现在的项目中没影响。

如需编译Web Browser内核，有两种方案：
（1）使用Chrome的Android版本，参考链接：https://www.chromium.org/developers/how-tos/get-the-code， https://chromium.googlesource.com/chromium/src/+/master/docs/android_build_instructions.md
（2）编译Android源码，使用编译产物，参考链接：http://source.android.com/source/initializing.html
注：如果采用（1），可以更进最新的Chrome版本，便于对Chrome的修改，采用（2）更容易理解与内核与Android Java层交互的代码。

1. 硬件要求：
不论是编译Android源码还是Chrome源码，对硬件要求都比较高，特别是内存（以前我们的编译机器都是超大内存，一般CPU）：
CPU：x86系列，64位，4核心以上，最好8核心（对频率没有限制）
内存：16G以上
硬盘：Chrome,100G以上;Android, 200G以上。如果使用SSD，可以大幅提高编译速度。
网速：要求能顺利快速访问国外相关开源网站，或者支持VPN

参考链接：
http://source.android.com/source/requirements.html
https://chromium.googlesource.com/chromium/src/+/master/docs/linux_build_instructions.md

2. 操作系统要求：
Linux系统，一般使用Ubuntu，可用系统有 https://wiki.ubuntu.com/Releases
(编译Android源码也可以采用MacOS X)


3. 软件要求：Key packages
(1) Python: http://www.python.org/
(2) GNU Make: http://www.gnu.org/software/make/manual/make.html
(3) Git: http://git-scm.com/
(4) JDK (Open JDK或Java JDK)
(5) 其它开源软件包（不一一提供参考链接）：it-core gnupg flex bison gperf build-essential \
  zip curl zlib1g-dev gcc-multilib g++-multilib libc6-dev-i386 \
  lib32ncurses5-dev x11proto-core-dev libx11-dev lib32z-dev ccache \
  libgl1-mesa-dev libxml2-utils xsltproc unzip


  关于编译时间：
  一般来说，Android源码编译：
  采用最新的i7处理器，16G内存，大约要2-4个小时左右。
  同步整个源代码根据网速而定（根据以前的经验，至少以天计算），这两步走完之后，增量编译时间可以忽略不计。
  Chrome编译，暂无参考时间。