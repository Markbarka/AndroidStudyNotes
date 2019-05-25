
##Android studio模拟器启动报错  
##报错：android Process finished with exit code 0
翻阅资料发现，这个的原因很多：
我遇到的是其中一个原因：run的不是安卓工程，而是其他（例如：一个java工程－Main）,选择app即可；
以后遇到其他的再补充。
##报错：Android error error running app no target device found
解决方法：
原因：原因是adb没检测到设备(包括真机和虚拟机)。
1: 如果没有设备，确认虚拟机是否正确打开，真机是否连接打开USB调试并安装驱动(可以多等一会，有时候会比较慢)。可执行adb kill-server和adb start-server这两个命令重启adb。  
2. 如果有设备，选择run —>EditConfiguration—>General，查看Deployment Target Options选项，查看设置的Taget是否有问题，以及是否选中了Use same device for future launches选项。   
3. Target三个选项分别代表打开设备选择框、USB设备、虚拟机。如果设置的是第二项那么打开虚拟机就会提示No target device found
###原文：https://blog.csdn.net/aliujiujiang/article/details/79592657 
----
##模拟器打不开的解决方法
###报错模板：android studio 启动模拟器报错The emulator process for AVD ****  was killed. 
解决博客(较全面)：https://blog.csdn.net/inuyasha_1314/article/details/81077342
参考博客（有瑕疵）：
1. https://blog.csdn.net/hope93/article/details/86594426         
2. https://bbs.csdn.net/topics/392424550
但其实查阅大量资料后，总结:
### win10的Virtualization Technology（华硕）一般默认开启了VT（厂商给出，我用的华硕）
### win10打开BIOS方法http:winwin7.com/JC/8781.html ，在里面找到（大概在save&exit旁边）Intel Virtulization Technology，选择，按回车，然后点save&exit；
###（扩展）关于Win10系统的Hyper-V功能
1. Hyper-V功能使用前提: win10系统中内置的有Hyper-V虚拟机功能，但是这个针对的是Win10预览版/专业版（企业版）才有此功能的;
2. 使用Hyper-V需要CPU支持虚拟化并处于开启状态；
3. 操作方法：首先打开控制面板（可以点击开始右键找，或者使用搜索功能）。然后打开程序与功能（可能先是程序，点了之后才有程序与功能），点击“启动或关闭Windows功能”。最后勾选“Hyp-V”确定（子文件管理工具还有平台自动勾选）（这里我们遇到上述问题是来关闭这个功能的，后面讲的是开启这个功能，即开启win10虚拟机hyper-V）；稍等一段时间，重启，点击“开始”，“所以程序”，点击“Windows管理工具”然后就可以看到“Hyper-V”，点击它即可进入主界面。
 