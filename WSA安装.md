## WSA安装

> 以Windows11家庭版为例， Windows11都可以参考

### 前期准备

#### 1. 修改区域为美国

![image-20230612125121704](C:\Users\Auria_Y\AppData\Roaming\Typora\typora-user-images\image-20230612125121704.png)

![image-20230612125137903](C:\Users\Auria_Y\AppData\Roaming\Typora\typora-user-images\image-20230612125137903.png

![image-20230612125204703](C:\Users\Auria_Y\AppData\Roaming\Typora\typora-user-images\image-20230612125204703.png)

#### 2. 启动Windows功能（虚拟机平台，Hyper-V，Windows虚拟机监控程序平台）

【Windows】+【R】

输入：```optionalfeatures.exe```

![image-20230612130137159](C:\Users\Auria_Y\AppData\Roaming\Typora\typora-user-images\image-20230612130137159.png)

![image-20230612125754061](C:\Users\Auria_Y\AppData\Roaming\Typora\typora-user-images\image-20230612125754061.png)

##### 家庭版可能会出现Hyper-V功能隐藏的情况

1. 新建文本文档

2. 在文档中复制这段

   ```
   pushd "%~dp0"
   
   dir /b %SystemRoot%\servicing\Packages\*Hyper-V*.mum >hyper-v.txt
   
   for /f %%i in ('findstr /i . hyper-v.txt 2^>nul') do dism /online /norestart /add-package:"%SystemRoot%\servicing\Packages\%%i"
   
   del hyper-v.txt
   
   Dism /online /enable-feature /featurename:Microsoft-Hyper-V-All /LimitAccess /ALL
   ```

3. 将文本另存为

   保存类型选“所有文件”

   在文件名的后面加上```.cmd```即可

   ![image-20230612130645830](C:\Users\Auria_Y\AppData\Roaming\Typora\typora-user-images\image-20230612130645830.png)

​	选中后右键，以管理员身份运行

​	运行结束后输入“ Y ”就会重启电脑，成功添加Hyper-V

![image-20230612130841863](C:\Users\Auria_Y\AppData\Roaming\Typora\typora-user-images\image-20230612130841863.png)

### 安装WSA

打开```https://store.rg-adguard.net/```

输入```https://www.microsoft.com/store/productid/9p3395vx91nr```

选择Slow，并点击✔

![image-20230612131225251](C:\Users\Auria_Y\AppData\Roaming\Typora\typora-user-images\image-20230612131225251.png)

接下来翻到最下面点击链接下载

（如果有代理，可能无法下载，需要暂时关闭）

![image-20230612131532972](C:\Users\Auria_Y\AppData\Roaming\Typora\typora-user-images\image-20230612131532972.png)

下载完成后，找到文件，选中并右键

![image-20230612131711159](C:\Users\Auria_Y\AppData\Roaming\Typora\typora-user-images\image-20230612131711159.png)

【Windows】+【x】点击【终端（管理员）】

![image-20230612131815392](C:\Users\Auria_Y\AppData\Roaming\Typora\typora-user-images\image-20230612131815392.png)

输入```Add-AppPackage (右键粘贴刚才复制的地址)```

AppPackage后面个空格

安装后可以看到

![image-20230612132005576](C:\Users\Auria_Y\AppData\Roaming\Typora\typora-user-images\image-20230612132005576.png)

记得打开程序，打开开发者模式

![image-20230612132242955](C:\Users\Auria_Y\AppData\Roaming\Typora\typora-user-images\image-20230612132242955.png)

### 安装 WSA Tools

```https://apps.microsoft.com/store/detail/wsatools-apk-installer-and-more/9N4P75DXL6FG?hl=en-us&gl=us```

按照程序指引完成安装

* 可能会打不开Microsoft store，试一下关闭代理。

* 【Windows】+【R】

  分两次输入运行 ```systeminfo``` 和 ```WSReset.exe``` 试试

### 安装安卓应用程序```.apk```

下载好软件安装包后，点击选中右键，用wsa tools打开

根据步骤操作即可

![image-20230612132526145](C:\Users\Auria_Y\AppData\Roaming\Typora\typora-user-images\image-20230612132526145.png)
