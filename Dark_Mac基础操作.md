iOS_1_Mac XCode 操作入门

1、Mac下调出命令行/终端界面

（1）快捷键  command + space

        （2）输入 Terminal

（3）已有终端打开时再次开启另一个终端， 快捷键 ： command + n

2、复制粘贴

（1）复制快捷键 ： command + c

（2）粘贴快捷键： command + v

（3）保存操作 ：   command + s

3、Mac下压缩格式为zip，rar格式有些无法打开

4、Mac OS下/usr,/bin等默认隐藏，命令行打开

5、Finder下浏览文件系统时，默认不显示当前完整路径，通过命令开启

default  write  com.apple.finder  -FXshowPosixPathInTitle  -bool YES

6、Finder下，文件拖动复制

option + 左键 ： 拖动文件复制

7、Finder下，获取选中文件的绝对路径

option + command + c

8、截屏功能

（1）全屏 ： shift + command + 3， 默认存储到桌面路径

（2）选定区域： shift + command + 4， 默认存储到桌面路径

9、显示桌面

command + F3

control + 左/右箭头

10、显示当前打开的所有程序

F3

11、显示Launchpad

F4

12、浏览文件/网页时快速移动光标

（1）光标移动到头部 ： fn + 左箭头

（2）光标移动到尾部 ： fn + 右箭头

（3）光标上移一部分 ： fn + 上箭头

（4）光标下移一部分 ： fn + 下箭头

（5）光标移到行首     :   command + 左箭头

（6）光标移到行尾     :   command + 右箭头

（7）全选当前位置到行首位置： shift + command + 左箭头

（8）全选当前位置到行尾位置： shift + command + 右箭头

14、打开听写功能

双击 fn 打开， 双击 fn关闭

15、快速浏览文件内容

Finder下，按space空格键可以浏览文件内容



16、Mac下查看静态库/动态库信息的终端命令

（1）查看静态库支持平台 ; lipo-infolibst.a

（2）查看静态库包含的一个或多个平台的版本： ar-tlibst.a

（4）合并不同平台的静态库到一个库中，便于在模拟机和真机下用同一个库开发，调试完毕后再分离 ： lipo  /proj1/libapi1.a    /proj2/libapi2.a   -output   /liball.a

（3）查看动态库文件接口 ： nm -Dlibst.so

17、IOS工程导入静态库开发

（1）确定使用的平台版本，输出的平台版本： armv7, armv7s, arm64, i386, x86_64，导出头文件

（2）工程所需的.a， .h文件拖动到XCode工程目录中，注意要复制到项目目录中

（3）点击项目名，点击 Build Phases，在Link Binary With Libraries下，选择导入上述拖动的所有.a文件

（4）随便打开一个源文件，导入头文件，编译 command + B, 运行 comman + R，确定是否配置成功

（5）真实调用函数接口等，是否引用.a文件成功

18、XCode工程下调出第二编辑窗口

（1）调出 ： option + command + enter

（2）关闭： command + enter

19、XCode中的帮助

（1）XCode菜单栏，点击Help， 在Search中输入关键字，会给予提示的动画效果，如操作步骤等

（2）XCode中点击显示某个.swift文件，右侧点击 问号图标，再在类文件中点击类名、方法名等，可以其对于提示信息

（3）XCode中点击显示某个.swift文件，按住option键，鼠标再放在某个类、方法、变量上，鼠标会变成 ？状态，点击后会显示提示帮助信息

（4）XCode中点击显示某个.storyboard视图文件，右侧点击 问号图标，再点击某个控件，右侧提示该控件的帮助信息

20、UIImageView中加载的图片可以通过选择配置

     或直接拖动图片到storyboard中就可以自动创建一个UIImageView

21、Finder浏览时回到上级目录

     在标题栏点击右键，可以选择回到哪一级目录

22、C头文件引出函数

    Object-c工程，需要函数用 extern "C"修饰

    Swift工程，不能用 extern "C"修饰

    VS工程，要用 extern "C"修饰
