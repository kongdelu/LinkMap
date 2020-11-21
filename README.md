## LinkMap
LinkMap解析工具：检查每个类占用空间大小
## 概述

一个大型的项目，只是代码段就有可能超过100M，算上armv7和arm64架构，就会超过200M。
这时候检查到底是哪个类、哪个第三方库占用了太多空间，就显得尤为重要。

这个工具是专为用来分析项目的LinkMap文件，得出每个类或者库所占用的空间大小（代码段+数据段），方便开发者快速定位需要优化的类或静态库。

## 使用方式：
    1.在XCode中开启编译选项Write Link Map File 
    XCode -> Project -> Build Settings -> 把Write Link Map File选项设为yes，并指定好linkMap的存储位置 
    2.工程编译完成后，在编译目录里找到Link Map文件（txt类型） 
    默认的文件地址：~/Library/Developer/Xcode/DerivedData/XXX-xxxxxxxxxxxxx/Build/Intermediates/XXX.build/Debug-iphoneos/XXX.build/XXX-LinkMap-normal-arm64.txt 
    3.回到本应用，点击“选择文件”，打开Link Map文件  
    4.点击“开始”，解析Link Map文件 
    5.点击“输出文件”，得到解析后的Link Map文件 
    6. * 输入目标文件的关键字(例如：libIM)，然后点击“开始”。实现搜索功能 
    7. * 勾选“分组解析”，然后点击“开始”。实现对不同库的目标文件进行分组
