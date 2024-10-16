#WiteUp-PicoCTF-Forensic
#Mob psycho

Author: NGIRIMANA Schadrack

Description
Can you handle APKs?
Download the android apk here.

First download the file with the extension .apk

Even though APK files are made for Android devices, you can open or extract them in Kali Linux using several methods depending on what you want to do, such as view their contents or run applications. 
Since APKs are basically ZIP files, you can extract them using the 'unzip' command.

┌──(root㉿gin)-[/home/griffin/Downloads]
└─# ls
mobpsycho.apk
                                                                                
┌──(root㉿gin)-[/home/griffin/Downloads]
└─# unzip mobpsycho.apk

see the files we have unzipped !
┌──(root㉿gin)-[/home/griffin/Downloads]
└─# ls
AndroidManifest.xml  classes2.dex  classes3.dex  classes.dex  META-INF  mobpsycho.apk  res  resources.arsc

here we don't find any flag or anything this is just an important file from 'mobpsycho.apk'
we can assume that the flag is stored in a file in '.txt' format

┌──(root㉿gin)-[/home/griffin/Downloads]
└─# ls
AndroidManifest.xml  classes3.dex  "META-INF"       "res"
classes2.dex         classes.dex   mobpsycho.apk  resources.arsc

we can see there are two directories "META-INF" and "res"                                                                              
we can enter the directory one by one first we can check the "META-INF" directory
┌──(root㉿gin)-[/home/griffin/Downloads]
└─# cd META-INF

There are no files in this directory so switch to the "res" directory
┌──(root㉿gin)-[/home/griffin/Downloads]
└─# cd res 
                                                                                
┌──(root㉿gin)-[/home/griffin/Downloads/res]
└─# ls
anim                      drawable-ldrtl-xxhdpi-v17   layout-land
animator                  drawable-ldrtl-xxxhdpi-v17  layout-ldrtl-v17
animator-v21              drawable-mdpi-v4            layout-sw600dp-v13
anim-v21                  drawable-v21                layout-v21
color                     drawable-v23                layout-v26
color-night-v8            drawable-v24                layout-watch-v20
color-v23                 drawable-watch-v20          mipmap-anydpi-v26
color-v31                 drawable-xhdpi-v4           mipmap-hdpi-v4
drawable                  drawable-xxhdpi-v4          mipmap-mdpi-v4
drawable-hdpi-v4          drawable-xxxhdpi-v4         mipmap-xhdpi-v4
drawable-ldrtl-hdpi-v17   interpolator                mipmap-xxhdpi-v4
drawable-ldrtl-mdpi-v17   interpolator-v21            mipmap-xxxhdpi-v4
drawable-ldrtl-xhdpi-v17  layout                      xml

there are many directories you can use the 'find' command
┌──(root㉿gin)-[/home/griffin/Downloads/res]
└─# cd .. 
                                                                                
┌──(root㉿gin)-[/home/griffin/Downloads]
└─# find res -name "*.txt"
res/color/flag.txt

finally we found the .txt file
now use the 'cat' command to open it

┌──(root㉿gin)-[/home/griffin/Downloads]
└─# cat res/color/flag.txt            
7069636f4354467b6178386d433052553676655f4e5838356c346178386d436c5f37343664666133397d

now we have found the flag in the res/color/flag.txt but it’s not a normal flag it’s a hex so let’s use any hex to string converter

use the 'echo' and 'xxd' commands (part of the vim-common package)
┌──(root㉿gin)-[/home/griffin/Downloads]
└─# echo 7069636f4354467b6178386d433052553676655f4e5838356c346178386d436c5f37343664666133397d| xxd -r -p
Explanation:
xxd -r: The -r option is used for reverse, that is, converting from hex to string.
-p: This option is to indicate that the input is hex in plain format (without spaces or other formats).

┌──(root㉿gin)-[/home/griffin/Downloads]
└─# echo 7069636f4354467b6178386d433052553676655f4e5838356c346178386d436c5f37343664666133397d| xxd -r -p
picoCTF{ax8mC0RU6ve_NX85l4ax8mCl_746dfa39}

flag : picoCTF{ax8mC0RU6ve_NX85l4ax8mCl_746dfa39}
