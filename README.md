# PyDecryptiPhonePC
Decrypt for iPhone Parental-Control password written by Python.

## Introduction
One day my brother asked me to decrypt the password for his iPhone parental-control, which he cannot remember it any longer.  
I just searched the method from internet, and found the website [Recover iOS7+ Restrictions Passcodes](http://ios7hash.derson.us/).  
This website can help us to decrypt the password of the parental-control for ios 7, 8 and 9.  
And I decrypted the password for my friend in this website, thanks to the author.  
I thought meybe I can implement this using Python, which can be faster than the website.  
So created the PyDecryptiPhonePC. 

## Usage
This tool only need the ```HashKey``` and the ```Salt```, which contains from iPhone backup file ```com.apple.restrictionspassword.plist ```.  
You will find the hashkey and salt like:  

```
<plist version="1.0"\>  
<dict\>  
    <key\>RestrictionsPasswordKey</key\>  
    <data\>  
    axo6VEI3Tn2ekTeLxA8KBBmH7CA= 
    </data\>  
    <key\>RestrictionsPasswordSalt</key\>  
    <data\>  
    GuCyTQ==
    </data\>  
</dict\>  
</plist\>   
```
You should copy the ```axo6VEI3Tn2ekTeLxA8KBBmH7CA=``` and ```GuCyTQ==```.  
### Windows version
Just install the tool and modify the run.bat, add hashKey & salt into it.  
Like: ```decryption.exe "axo6VEI3Tn2ekTeLxA8KBBmH7CA=" "GuCyTQ=="```  
Then you can execute run.bat  

### Linux version
Just run command as:  
<pre>
$ python3 decryption.py "axo6VEI3Tn2ekTeLxA8KBBmH7CA=" "GuCyTQ=="
</pre>  

### result
When finish the decryption, it will print log as ```****** Found it!!!!! ****** The password is  1984``` and save the password in result.txt file if decrypt successfully，Or it will show failure log.   

# 中文说明(README in Chinese version)
对苹果iPhone访问限制密码进行破解的Python工具。

## 楔子
某天我兄弟问我有没有办法可以破解他的访问限制密码，因为他忘记自己设置的是多少了。我就在互联网上搜索破解方法，找到了这个网站[Recover iOS7+ Restrictions Passcodes](http://ios7hash.derson.us/)可以破解出IOS7，8和9的访问限制密码。  
我通过该网站破解出我朋友的密码，在这里要感谢该网页的作者。  
访问限制密码是4个数字的组合，区间从0000 ~ 9999，采用pbkdf2 hmac sha1加密。  
我思考能否通过Python语言实现一套破解的工具，同时采用多线程的方式可以比较快的计算出密码。  
因此有了PyDecryptiPhonePC这个项目。

## 使用方法
本工具只需要传入```HashKey```和```Salt```，而这两个值是从需要破解的手机备份文件里提取出来的，通过在文件```com.apple.restrictionspassword.plist ```里查找如下的内容：  
```
<plist version="1.0"\>  
<dict\>  
    <key\>RestrictionsPasswordKey</key\>  
    <data\>  
    axo6VEI3Tn2ekTeLxA8KBBmH7CA= 
    </data\>  
    <key\>RestrictionsPasswordSalt</key\>  
    <data\>  
    GuCyTQ==
    </data\>  
</dict\>  
</plist\>   
```
将如上例中的```axo6VEI3Tn2ekTeLxA8KBBmH7CA=```和```GuCyTQ==```保存下来。（上述只是例子，每个人的这两个值应该都不一样）  
### Windows运行版本
安装releases里针对32位或64位的安装包，并修改工具目录里的run.bat,将保存的两个值添加如下：  
```decryption.exe "axo6VEI3Tn2ekTeLxA8KBBmH7CA=" "GuCyTQ=="```  
修改好之后就直接执行run.bat即可。 

### Linux运行版本
直接运行命令如下：  
<pre>
$ python3 decryption.py "axo6VEI3Tn2ekTeLxA8KBBmH7CA=" "GuCyTQ=="
</pre>  

### 结果查看
当工具完成了破解，如果打印了如下信息：
```****** Found it!!!!! ****** The password is  1984```则表示破解成功，同时会把密码保存到工具目录中的```result.txt```里。  
否则会打印失败信息。
