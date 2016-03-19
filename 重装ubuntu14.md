#菜鸟的ubuntu装机及残留问题记录

那天我乱卸驱动，乱安软件，导致ubuntu12.04无法进入图形界面:
* 开机启动到一半出现：
    `could not write bytes: broken pipe`
* 进入命令行界面，使用命令行`startx`，结果出现：
    `Fatal server error: no screens found`
    
本菜鸟百度、谷歌了一下，看得懂的方法都不行，看不懂的方法更让我两眼发黑，只好重装成ubuntu14.04
幸好大学同学曾经留给我一个BioLinux3的刻录u盘，谢天谢地

### Ubuntu小知识
1. 用户登录则自动运行`/.bash_profile`、`/.bash_login`以及`./profile`中第一个被搜索到的文件，我的是`./profile`。
2. 用户退出则自动运行`/.bash_logout`
3. 一个称为crond的守护程序会周期性地检查`/var/spool/cron`目录下的一组命令文件的内容，并在设定的时间执行这些文件中的命令。用户可以通过crontab 命令来建立、修改、删除这些命令文件。 参考自[推酷文章](http://www.tuicool.com/articles/euYJVr)

###1. 利用u盘启动，拷贝原系统下的重要文件
通过u盘启动试用版ubuntu，原系统会被视为一个外部设备被加载，利用`sudo`管理员权限拷贝出所有重要的文档，此时无需输入任何密码，不管这是否是ubuntu的Bug，他总之是本菜鸟的救命稻草。

ThinkPad的`Bios`引导设置是`F12`，注意也许有需要加上`Fn`键。开机即可狂按，以防错过时机。进入`Bios`引导界面后选择对应的USB就行了。
  
###2. 重装系统
重要文件拷贝完毕后，认真反复检查几遍，确认没有遗漏，这时一定要发扬土豪精神、“宁滥勿缺”！然后就可以肆无忌惮地重装了。对于本菜鸟来说，不会分区，不会任何高级设置，直接傻瓜式一键安装。
  
###3. 无线驱动
我的电脑是ThinkPad E430c，无线网卡是BCM43142，根据ubuntu中文论坛中的一个[帖子](http://forum.ubuntu.org.cn/viewtopic.php?t=461389)，可以这样安装驱动
	
```shell
sudo apt-get update
sudo apt-get install --reinstall bcmwl-kernel-source 
```

如果不`update`的话，有可能出现软件包未经验证的情况。

另外我之前下载了一个`hybrid_wireless_driver`，其中的驱动按照说明安装后也是能用的，现在Broadcom官网貌似没有他了，把他上传至[reference-files](https://github.com/HuangRuocheng/git-learning/tree/master/reference-files)保存一下。
  
###4. 选取中文输入法
我选择了搜狗输入法，通过官网可以下载deb安装包，双击即可安装，注销重新登录就能使用。

###5. 安装skype
Linux下的skype只更新到4.3版本，之后便没有更新了，安装方式参考该[英文网站](http://ubuntuhandbook.org/index.php/2014/06/skype-4-3-install-in-ubuntu-1404/)
* remove old skype and .skype folder:
	
```shell
sudo apt-get remove skype skype-bin
rm -rf ~/.skype
```
	
* Open “Software & Updates” and enable Canonical partners(there are 2) repository under Other Software tab
* run the commands below to install skype:
	
```shell
sudo apt-get update
sudo apt-get install skype
```

2016年2月以后，Linux版skype初次进行小组通话会议时，可能会被阻止并提示更新，不过没有关系，再拨打一次，或者重启skype就没有这个问题了

###6. 安装virturalbox
从Oracle VM VirtualBox官网即可下载deb安装包，双击即可安装

通过`新建`->...->`使用已有的虚拟硬盘文件`即可使用原有虚拟系统，参考[百度知道](http://jingyan.baidu.com/article/95c9d20da33a5fec4e7561d4.html)

###7. 安装Rstudio
从Rstudio官网即可下载安装包
  
  - [ ] **当前Rstudio无法支持输入法**
      1. 把`libfcitxplatforminputcontextplugin.so`拷进`/usr/lib/rstudio/bin/plugins/platforminputcontexts/`也是不管用...

###8. 安装git
git安装非常简单
	
```shell
$sudo apt-get install git
```
