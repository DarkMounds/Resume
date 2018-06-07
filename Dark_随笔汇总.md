cd 进入下一级
./ 执行脚本
cd .. 返回上一级
cd ...返回上上级
cd\ 返回根目录
ls 显示所有文件
pwd 显示绝对路径



--命令行
--从res中安装资源，资源打包命令 ，必须进到资源工程目录下
./install.sh /Users/darkmounds/ClientPro/tianzha
--打更新包命令。
./game_build.py w
--./make_update_files.py w
输入的环境ID为： w/t  此环境ID【必须】与安卓清单文件中的【VerType】
或者ios的info.plist中的【VerType】完全相等，否则热更不会被执行
--项目打包编译资源
路径：安卓：sydtz/frameworks/runtime-src/proj.android_no_anysdk/
./build_res.sh w/t
--拷贝项目
./copy_project.sh test2 --路径


----
export ANDROID_SDK_ROOT=/Users/darkmounds/ClientPro/adt-bundle-mac/sdk
export ANDROID_NDK_ROOT=/Users/darkmounds/ClientPro/android-ndk-r10d

--eclipse安装问题：

android-ndk-r10d-darwin-x86_64.bin 文件的打开  如果用Mac自带的打开工具打开是有问题的。

用命令行 打开：
第一步：获取权限：进入到.bin文件的目录  chmod a+x android-ndk-r10d-darwin-x86_64.bin
第二部：解压文件： ./android-ndk-r10d-darwin-x86_64.bin


--安装eclipse介绍：
https://www.cnblogs.com/luorende/archive/2016/11/12/6056667.html


--sourcetree 安装：
安装好之后
生成Key
https://blog.csdn.net/u010026245/article/details/50454103
配置Git私钥   Git远端配置Git公钥
https://blog.csdn.net/qq_34101611/article/details/52057666

--打包安卓包：
1.路径：项目文件夹下frameworks/runtime-src/proj.android_no_anysdk/
2.build_native.sh   编译新的so库文件，如果底层没改动就不需要重新编译
3.buiild_native_release.sh 跟build_native.sh一样  但是是release版本的
4.bui_res.sh 加密资源代码文件  需要输入版本号
5.将项目导入eclipse，修改storekey(偏好设置中)
6.run as
7.apk文件生成在bin文件中。



