# Xcode-C-
解决xcode平台c++无法使用万能头文件的问题
# 使用教程
![image](https://user-images.githubusercontent.com/110269012/185610994-51ef3556-7e6c-4c79-8878-b9f28992e3a4.png)
当我们使用xcode的时候，输入万能头文件会报错
这是因为xcode默认的是使用 libc++ 作为 C++ 标准库实现，而万能头 bits/stdc++.h 是 GNU libstdc++ 所独有的。
## Step1
![截屏2022-08-19 19 44 59](https://user-images.githubusercontent.com/110269012/185611593-066e0e50-e95a-4741-853a-9809c0fb8de6.png)
打开终端，输入：
``` 
sudo -i
```   
来启用root
**接着前往头文件文件夹**
```
cd /Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/include/c++/v1
```   
**注意⚠️：如果你的xcode在12.5及以上，请输入下面的代码**
```
cd /Applications/Xcode.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX.sdk/usr/include/c++/v1/
```
## Step2
我们需要创建目录
```
mkdir bits
```
接着切换到该目录
```
cd bits
```
## Step3
安装vim文本编辑器（如果有请跳过下面一行代码）
```
sudo apt-get install vim-gtk
```
使用vim创建并编辑bits/stdc++.h
```
vim stdc++.h
```
![截屏2022-08-19 20 00 05](https://user-images.githubusercontent.com/110269012/185614144-906f1a02-abfd-496f-83f5-87d2f30ecab7.png)

按i键进入文本编辑模式，将.h头文件里内容复制并粘贴进去
接着按下 esc 退出编辑模式，输入
```
:wq
```
保存并推出
## Step4
再次使用bits/stdc++.h头文件的时候就会发现Build成功了
![截屏2022-08-19 20 04 12](https://user-images.githubusercontent.com/110269012/185615099-0ec59d65-17c5-4e89-92e4-fd931f13e8a4.png)
