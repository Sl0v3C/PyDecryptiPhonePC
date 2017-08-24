# PyDecryptiPhonePC
Decrypt for iPhone Parental-Control password written by Python.

## Introduction
One day my best friend asked me to decrypt the password for his iPhone parental-control, which he cannot remember it any longer.  
I just searched the method from internet, and found the website [Recover iOS7+ Restrictions Passcodes](http://ios7hash.derson.us/).  
This website can help us to decrypt the password of the parental-control for ios 7, 8 and 9.  
And I decrypted the password for my friend in this website, thanks to the author.  
I thought meybe I can implement this using Python, which can be faster than the website.  
So created the PyDecryptiPhonePC. 

## Usage
This tool only need the ```HashKey``` and the ```Salt```, which contains from iPhone backup file ```com.apple.restrictionspassword.plist ```.  
You will find the hashkey and salt like:  
<code>
<plist version="1.0"\>  
<dict\>  
&nbsp;&nbsp;&nbsp;&nbsp;<key\>RestrictionsPasswordKey</key\>  
&nbsp;&nbsp;&nbsp;&nbsp;<data\>  
&nbsp;&nbsp;&nbsp;&nbsp;**axo6VEI3Tn2ekTeLxA8KBBmH7CA=**  
&nbsp;&nbsp;&nbsp;&nbsp;</data\>  
&nbsp;&nbsp;&nbsp;&nbsp;<key\>RestrictionsPasswordSalt</key\>  
&nbsp;&nbsp;&nbsp;&nbsp;<data\>  
&nbsp;&nbsp;&nbsp;&nbsp;**GuCyTQ==**  
&nbsp;&nbsp;&nbsp;&nbsp;</data\>  
</dict\>  
</plist\>   
</code>
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
When finish the decryption, it will print the password and save the password in result.txt file if decrypt successfully.  
Or it will show nothing. 