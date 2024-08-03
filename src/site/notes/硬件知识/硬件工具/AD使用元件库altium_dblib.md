---
{"dg-publish":true,"permalink":"/硬件知识/硬件工具/AD使用元件库altium_dblib/"}
---

使用Altium Designer数据库DatabaseLib功能可以方便地把元器件与公司内的原理图库、PCB库以及器件的参数进行链接，减少人为操作的失误，并可提高输出BOM的工作效率。虽然数据库的维护刚开始的时候工作量比较繁重，但随着元件库的扩大，维护工作会越来越少，前期的投入是值得的。
# git的安装与使用
## 安装git
gitee中不支持大容量仓库以SVN协议管理，因此需要安装使用git。
从git官网下载windows版本的git安装包。[https://git-scm.com/downloads](https://git-scm.com/downloads)
按照提示安装git，安装完成之后，在任意文件夹下，右键，如果出现Git GUI/Bash选型，则说明已安装成功。
![clipboard.png](/img/user/%E7%A1%AC%E4%BB%B6%E7%9F%A5%E8%AF%86/%E7%A1%AC%E4%BB%B6%E5%B7%A5%E5%85%B7/attachments/clipboard.png)
选择"Git Bash Here"，在其中通过命令行设定用户名和邮箱。
`git config --global user.name "常坚"`
`git config --global user.email "changjian2007@126.com"`
## 将git仓库拉取到本地
例如，准备将该工程放在电脑中的01_develop/AltiumDesigner文件夹下，在该文件夹下右键单击，打开"Git Bash Here"。使用git clone命令，让对应的仓库拉取到本地电脑。
![clipboard 1.png](/img/user/%E7%A1%AC%E4%BB%B6%E7%9F%A5%E8%AF%86/%E7%A1%AC%E4%BB%B6%E5%B7%A5%E5%85%B7/attachments/clipboard%201.png)
`git clone https://gitee.com/changjian2007/altium_dblib.git`
仓库地址获取方法：
![Pasted image 20240802095806.png](/img/user/%E7%A1%AC%E4%BB%B6%E7%9F%A5%E8%AF%86/%E7%A1%AC%E4%BB%B6%E5%B7%A5%E5%85%B7/attachments/Pasted%20image%2020240802095806.png)
## 更新及提交
接下来按照AD的正常流程，在DT2010_XXX文件夹下创建项目，并画原理图和layout，针对dblib仓库，更新symbols，footprint，或数据库文件后，也需进行提交。
![clipboard 2.png](/img/user/%E7%A1%AC%E4%BB%B6%E7%9F%A5%E8%AF%86/%E7%A1%AC%E4%BB%B6%E5%B7%A5%E5%85%B7/attachments/clipboard%202.png)
在git bash窗口中，输入git status可以查看当前的文件夹中，文件更改或新添加的状态。
![clipboard 3.png](/img/user/%E7%A1%AC%E4%BB%B6%E7%9F%A5%E8%AF%86/%E7%A1%AC%E4%BB%B6%E5%B7%A5%E5%85%B7/attachments/clipboard%203.png)
可以看到git检测出了，我们新增加的几个文件。但是History文件夹和__Previews文件夹是AD临时生成的文件，一般不需要将其放入版本管理进行跟进。可在DT2010_XXX文件夹下创建".gitignore"文件，写入相关的内容。
![clipboard 4.png](/img/user/%E7%A1%AC%E4%BB%B6%E7%9F%A5%E8%AF%86/%E7%A1%AC%E4%BB%B6%E5%B7%A5%E5%85%B7/attachments/clipboard%204.png)
保存后，再在git bash中查看git status，便发现git不再跟踪History和__Previews文件夹了。
![clipboard 5.png](/img/user/%E7%A1%AC%E4%BB%B6%E7%9F%A5%E8%AF%86/%E7%A1%AC%E4%BB%B6%E5%B7%A5%E5%85%B7/attachments/clipboard%205.png)
添加所有修改的文件，添加提交说明并进行提交推送到gitlab服务器。
![clipboard 6.png](/img/user/%E7%A1%AC%E4%BB%B6%E7%9F%A5%E8%AF%86/%E7%A1%AC%E4%BB%B6%E5%B7%A5%E5%85%B7/attachments/clipboard%206.png)
刷新gitee仓库页面，便可以看到成功提交了原理图和layout。
### 通过AD更新及提交
将工程加入git后，直接双击项目PrjPcb文件，使用AD打开后，在AD中也能看到相应的更新和改动状态。
![clipboard 7.png](/img/user/%E7%A1%AC%E4%BB%B6%E7%9F%A5%E8%AF%86/%E7%A1%AC%E4%BB%B6%E5%B7%A5%E5%85%B7/attachments/clipboard%207.png)
在这次提交后，我对其中某个文件进行了修改。修改后，相应文件的对号，便会变成红色的圆圈，以表示进行了修改。
![clipboard 8.png](/img/user/%E7%A1%AC%E4%BB%B6%E7%9F%A5%E8%AF%86/%E7%A1%AC%E4%BB%B6%E5%B7%A5%E5%85%B7/attachments/clipboard%208.png)
修改完成后，可以在AD中直接进行提交推送。在项目上右键单击，选择版本管理->提交整个项目。
![clipboard 9.png](/img/user/%E7%A1%AC%E4%BB%B6%E7%9F%A5%E8%AF%86/%E7%A1%AC%E4%BB%B6%E5%B7%A5%E5%85%B7/attachments/clipboard%209.png)
会弹出版本控制的提交窗口，勾选更改或新建的文件，写入更改的内容，单击commit and push。
![clipboard 10.png](/img/user/%E7%A1%AC%E4%BB%B6%E7%9F%A5%E8%AF%86/%E7%A1%AC%E4%BB%B6%E5%B7%A5%E5%85%B7/attachments/clipboard%2010.png)
在弹出的窗口，输入用户名和密码。
![clipboard 11.png](/img/user/%E7%A1%AC%E4%BB%B6%E7%9F%A5%E8%AF%86/%E7%A1%AC%E4%BB%B6%E5%B7%A5%E5%85%B7/attachments/clipboard%2011.png)
提交后，AD中文件状态为无修改状态。在gitee仓库页面，刷新可看到提交的信息。
![clipboard 12.png](/img/user/%E7%A1%AC%E4%BB%B6%E7%9F%A5%E8%AF%86/%E7%A1%AC%E4%BB%B6%E5%B7%A5%E5%85%B7/attachments/clipboard%2012.png)
![clipboard 13.png](/img/user/%E7%A1%AC%E4%BB%B6%E7%9F%A5%E8%AF%86/%E7%A1%AC%E4%BB%B6%E5%B7%A5%E5%85%B7/attachments/clipboard%2013.png)

# AD使用altium_dblib仓库
## 获取altium_dblib仓库
从gitee获取最新的altium_dblib，参考 [[硬件知识/硬件工具/AD使用元件库altium_dblib#将git仓库拉取到本地\|AD使用元件库altium_dblib#将git仓库拉取到本地]]。涉及到git的使用，可在网上搜索更多的使用方法。
首先安装MS access engine，下载地址：[Download Microsoft Access Database Engine 2016 Redistributable from Official Microsoft Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=54920)
## 创建dblib文件
打开AD，File -> New -> Library，打开创建dblib文件。
![Pasted image 20240801210753.png](/img/user/%E7%A1%AC%E4%BB%B6%E7%9F%A5%E8%AF%86/%E7%A1%AC%E4%BB%B6%E5%B7%A5%E5%85%B7/attachments/Pasted%20image%2020240801210753.png)
选择database， database library，点击create
![Pasted image 20240802121450.png](/img/user/%E7%A1%AC%E4%BB%B6%E7%9F%A5%E8%AF%86/%E7%A1%AC%E4%BB%B6%E5%B7%A5%E5%85%B7/attachments/Pasted%20image%2020240802121450.png)

![Pasted image 20240802122102.png](/img/user/%E7%A1%AC%E4%BB%B6%E7%9F%A5%E8%AF%86/%E7%A1%AC%E4%BB%B6%E5%B7%A5%E5%85%B7/attachments/Pasted%20image%2020240802122102.png)

![Pasted image 20240802125906.png](/img/user/%E7%A1%AC%E4%BB%B6%E7%9F%A5%E8%AF%86/%E7%A1%AC%E4%BB%B6%E5%B7%A5%E5%85%B7/attachments/Pasted%20image%2020240802125906.png)
![Pasted image 20240802130026.png](/img/user/%E7%A1%AC%E4%BB%B6%E7%9F%A5%E8%AF%86/%E7%A1%AC%E4%BB%B6%E5%B7%A5%E5%85%B7/attachments/Pasted%20image%2020240802130026.png)
## 使用dblib文件
在component窗口中安装刚才altium_lib.dblib数据库文件。
![Pasted image 20240803205829.png](/img/user/%E7%A1%AC%E4%BB%B6%E7%9F%A5%E8%AF%86/%E7%A1%AC%E4%BB%B6%E5%B7%A5%E5%85%B7/attachments/Pasted%20image%2020240803205829.png)
在弹出的窗口中，安装dblib文件。
![Pasted image 20240803210007.png](/img/user/%E7%A1%AC%E4%BB%B6%E7%9F%A5%E8%AF%86/%E7%A1%AC%E4%BB%B6%E5%B7%A5%E5%85%B7/attachments/Pasted%20image%2020240803210007.png)

# 添加新的元器件

我们以添加一款多路复用开关元器件：ADG1213YRUZ，为例进行说明。
![Pasted image 20240803151520.png](/img/user/%E7%A1%AC%E4%BB%B6%E7%9F%A5%E8%AF%86/%E7%A1%AC%E4%BB%B6%E5%B7%A5%E5%85%B7/attachments/Pasted%20image%2020240803151520.png)
## 建立原理图库和封装库文件
根据对应物料型号，找到datasheet，根据datasheet的内容建立原理图库和封装库文件。注意：原理图库封装库文件单独建立，不要跟其他的元器件放在一起。
根据元器件型号：ADG1213YRUZ，在datasheet中找到对应的封装和电路实现如下图：
![Pasted image 20240803152031.png](/img/user/%E7%A1%AC%E4%BB%B6%E7%9F%A5%E8%AF%86/%E7%A1%AC%E4%BB%B6%E5%B7%A5%E5%85%B7/attachments/Pasted%20image%2020240803152031.png)
### 原理图库文件
在AD中建立名为"SCH - SWITCH - ADG1213 SPST 16PIN.SCHILIB"的原理图库文件，并放到symbols文件夹中对应的位置。
![Pasted image 20240803152431.png](/img/user/%E7%A1%AC%E4%BB%B6%E7%9F%A5%E8%AF%86/%E7%A1%AC%E4%BB%B6%E5%B7%A5%E5%85%B7/attachments/Pasted%20image%2020240803152431.png)
对应的元件库如下图：
![Pasted image 20240803152602.png](/img/user/%E7%A1%AC%E4%BB%B6%E7%9F%A5%E8%AF%86/%E7%A1%AC%E4%BB%B6%E5%B7%A5%E5%85%B7/attachments/Pasted%20image%2020240803152602.png)
### 封装库文件
在datasheet中找到对应的封装说明部分：
![Pasted image 20240803154927.png](/img/user/%E7%A1%AC%E4%BB%B6%E7%9F%A5%E8%AF%86/%E7%A1%AC%E4%BB%B6%E5%B7%A5%E5%85%B7/attachments/Pasted%20image%2020240803154927.png)
在仓库的封装文件夹中创建对应的封装文件，根据规格创建封装。
![Pasted image 20240803160225.png](/img/user/%E7%A1%AC%E4%BB%B6%E7%9F%A5%E8%AF%86/%E7%A1%AC%E4%BB%B6%E5%B7%A5%E5%85%B7/attachments/Pasted%20image%2020240803160225.png)
对应的封装库文件如下：
![Pasted image 20240803160249.png](/img/user/%E7%A1%AC%E4%BB%B6%E7%9F%A5%E8%AF%86/%E7%A1%AC%E4%BB%B6%E5%B7%A5%E5%85%B7/attachments/Pasted%20image%2020240803160249.png)
## 添加元件到excel文件
在altium_lib.xlsx文件中，相应的页面更新元件的信息。
![Pasted image 20240803203306.png](/img/user/%E7%A1%AC%E4%BB%B6%E7%9F%A5%E8%AF%86/%E7%A1%AC%E4%BB%B6%E5%B7%A5%E5%85%B7/attachments/Pasted%20image%2020240803203306.png)
其中Library Ref、Library Path、Footprint Ref、Footprint Path四项为AltiumDesigner规定的必须参数，其他参数（如Part Number、Specification、Comment等）建议按照模板进行，或根据实际情况进行更改。
* **Library Ref**是元器件在原理图库中引用的封装名称
* **Library Path**是原理图库的路径
* **Footprint Ref**是元器件在PCB库中引用的封装名称
* **Footprint Path**是PCB库的路径
## 更新dblib数据库
按照[[硬件知识/硬件工具/AD使用元件库altium_dblib#创建dblib文件\|#创建dblib文件]] 的说明创建dblib文件，覆盖原有dblib文件。或者直接刷新即可。
![Pasted image 20240803204630.png](/img/user/%E7%A1%AC%E4%BB%B6%E7%9F%A5%E8%AF%86/%E7%A1%AC%E4%BB%B6%E5%B7%A5%E5%85%B7/attachments/Pasted%20image%2020240803204630.png)
## 上传到git仓库
按照[[硬件知识/硬件工具/AD使用元件库altium_dblib#更新及提交\|#更新及提交]]的说明，提交到git仓库，并告知相关人员。

# 准备材料

- 原理图库

# 错误情况的处理

## 点击"Connect"时，出现"Connection Failed.Check your connnecton settings."

![](https://images2018.cnblogs.com/blog/869740/201803/869740-20180319235559179-1400381254.png)

此问题，

### 可能在于源excel中使用VLOOUP进行了引用

解决办法：去除公式引用，保留纯数据。新建一个excel表格，把原来带引用的内容，右键粘贴，粘贴时选择仅保留值即可。

### 可能在于excel的源出现了问题

解决办法：：因为Altium Designer在使用链接读取excel时，使用的是Microsoft.ACE.OLEDB.12.0，而excel在应用“筛选”功能时，出现了_xlnm#_FilterDatabase，这是一个隐藏的名称，需要删除。删除的方法：

1、顺序按Alt+F11，Alt+i，m，拷贝下面内容

Sub showallname()  
For Each n In ThisWorkbook.Names  
n.Visible = True  
Next  
End Sub

关闭。

2、在excel中，按F5运行，罪魁祸首如下：

![](https://images2018.cnblogs.com/blog/869740/201803/869740-20180320000231567-961070128.png)

3、点击"公式"，"名称管理器"或者快捷方式Ctrl+F3，删除名称管理器中的_fliterD...如下：

![](https://images2018.cnblogs.com/blog/869740/201803/869740-20180320000438174-71163868.png)

![](https://images2018.cnblogs.com/blog/869740/201803/869740-20180320000318861-92295138.png)

4、保存，重新加载数据库文件，选择excel（NOT  Excel2007），即可。

![](https://images2018.cnblogs.com/blog/869740/201803/869740-20180320001502179-1561280788.png)

参考链接：

Altiumdesigner官方资料：http://www.altium.com/documentation/cn/17.1/display/ADES/((Working+with+Database+Libraries))_AD#

http://www.xuebuyuan.com/664368.html

http://club.excelhome.net/thread-675925-1-1.html

http://blog.sina.com.cn/s/blog_163b107610102y1b5.html

http://blog.csdn.net/alan_wdd/article/details/53443025

# 总结
此次使用的是本地数据库（Excel或Access），也可以链接公司的数据库。并且可以把元器件datasheet、URL等进行链接。使用SVN可以对原理图库、PCB库、project进行版本控制，修改前后difference对比，减少版本泛滥。