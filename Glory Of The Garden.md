#WriteUp-PicoCTF-Forensic
#Glory Of The Garden
Author: jedavis/Danny
Description
This garden contains more than it seems.

download the 'garden' file first !

If we look at the image we cannot find the flag information.
use the 'string' command to extract human-readable text from binary files or other files containing raw data
useful when you want to find hidden or concealed information inside files that are generally not directly readable, such as executable files, images, or other binary files.

┌──(root㉿gin)-[/home/griffin/Downloads]
└─# strings garden.jpg 

it's very easy, scroll down and you will find the flag
Here is a flag "picoCTF{more_than_m33ts_the_3y33dd2eEF5}"

flag : picoCTF{more_than_m33ts_the_3y33dd2eEF5}
