# WSA_setup

> 以Windows11家庭版为例， Windows11都可以参考

## 前期准备

### 1. 修改区域为美国

![image-20230612125137903](https://github.com/AuriaY/WSA_setup/assets/55018403/219faae7-c137-415a-a2f8-b22ec9429a82)

![image-20230612125204703](https://github.com/AuriaY/WSA_setup/assets/55018403/20dc7d6d-1f5b-4ba9-b28f-8642b7a442aa)

### 2. 启动Windows功能（虚拟机平台，Hyper-V，Windows虚拟机监控程序平台）

【Windows】+【R】

输入：```optionalfeatures.exe```

![image-20230612130137159](https://github.com/AuriaY/WSA_setup/assets/55018403/4cc0fc6a-2866-4c96-831a-8e354216ed29)

![image-20230612125754061](https://github.com/AuriaY/WSA_setup/assets/55018403/d1a3484b-9ad1-48e2-90b6-8c51af4c5857)

#### 家庭版可能会出现Hyper-V功能隐藏的情况

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

   ![image-20230612130645830](https://github.com/AuriaY/WSA_setup/assets/55018403/d7695795-217e-4843-a885-3a4169ddbdd4)

​	选中后右键，以管理员身份运行

​	运行结束后输入“ Y ”就会重启电脑，成功添加Hyper-V

![image-20230612130841863](https://github.com/AuriaY/WSA_setup/assets/55018403/a984816d-11f8-45f6-b8a1-1daf0867d224)

## 安装WSA

#### 打开```https://store.rg-adguard.net/```

#### 输入```https://www.microsoft.com/store/productid/9p3395vx91nr```

#### 选择Slow，并点击✔

![image-20230612131225251](https://github.com/AuriaY/WSA_setup/assets/55018403/8c14c86f-d7f9-4e9d-9aba-55ba497785ce)

#### 接下来翻到最下面点击链接下载

#### （如果有代理，可能无法下载，需要暂时关闭）

![image-20230612131532972](https://github.com/AuriaY/WSA_setup/assets/55018403/fa3545c1-863b-4aa7-bb7b-41128a63be3b)

#### 下载完成后，找到文件，选中并右键

![image-20230612131711159](https://github.com/AuriaY/WSA_setup/assets/55018403/fdd3377f-6e07-4de5-a394-18f20ff32aeb)

#### 【Windows】+【x】点击【终端（管理员）】

![image-20230612131815392](https://github.com/AuriaY/WSA_setup/assets/55018403/0395e273-e0fa-49bf-a4a0-3931e470d03c)

#### 输入```Add-AppPackage (右键粘贴刚才复制的地址)```

#### AppPackage后面个空格

#### 安装后可以看到

![image-20230612132005576](https://github.com/AuriaY/WSA_setup/assets/55018403/b9806b9d-cb7f-405a-ad1a-30e20f9895fe)

#### 记得打开程序，打开开发者模式

![image-20230612132242955](https://github.com/AuriaY/WSA_setup/assets/55018403/2cecb193-e61f-4558-b2ea-f219245c8392)

## 安装 WSA Tools

```https://apps.microsoft.com/store/detail/wsatools-apk-installer-and-more/9N4P75DXL6FG?hl=en-us&gl=us```

#### 按照程序指引完成安装

#### * 可能会打不开Microsoft store，试一下关闭代理。

#### * 【Windows】+【R】

  #### 分两次输入运行 ```systeminfo``` 和 ```WSReset.exe``` 试试

## 安装安卓应用程序```.apk```

#### 下载好软件安装包后，点击选中右键，用wsa tools打开

#### 根据步骤操作即可

![image-20230612132526145](https://github.com/AuriaY/WSA_setup/assets/55018403/f0ac1541-e20f-4a79-8125-340f199e99f7)
