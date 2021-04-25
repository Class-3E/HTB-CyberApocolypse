## Passphrase 

This challenge provides a binary file. Let's analyse it and get our flag!
I am using radare2 tool which comes pre-installed with Kali Linux.


Only 4 commands on terminal nedded to get closer with our flag :) 
```
1. r2 passphrase  
2. aaa 
3. afl 
4. pdf @main 
```
Look at the characters on right hand side inside ' ' in the screenshot.

![img](https://github.com/Class-3E/HTB-CyberApocolypse/blob/master/Reversing/Images/passphrase.png)

We can some how conclude that these are the characters which resembles our flag. But the below line confirms that these are part of flag. 

``` "\nSorry for suspecting you, please transfer this important message to the chief: CHTB{%s}\n\n" ```

With putting character in syntax of our flag we finally got sucess. GG

``` Flag - CHTB{3xtr4t3rR3stR14L5_VS_hum4n5} ``` 
