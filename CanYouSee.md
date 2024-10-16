# WriteUp-PicoCTF-Forensic
#CanYouSee
!!Author: Mubarak Mikail!!
Description
How about some hide and seek?
Download this file here.

Open the challenge
Download this file ! (Before decompress)

Now we decompress the file
//Here I use the 'unzip' command to extract files from an archive in .zip format.//
┌──(root㉿gin)-[/home/griffin/Downloads]
└─# unzip unknown.zip 
Archive:  unknown.zip
  inflating: ukn_reality.jpg  

After decompressing, I got an image !
ukn_reality.jpg

Here we can see that in the image there is no information that can be found.
we can use gathering information in its metadata. Use the command 'exiftool'

look at all the information in the file we can find there is encoding in the Attribution URL information !
Attribution URL : cGljb0NURntNRTc0RDQ3QV9ISUREM05fM2I5MjA5YTJ9Cg==

Now it's time to decode the base64 text to text using the 'echo' command.

finally i managed to find the flag after decoding it !!!
┌──(root㉿gin)-[/home/griffin/Downloads]
└─# echo "cGljb0NURntNRTc0RDQ3QV9ISUREM05fM2I5MjA5YTJ9Cg=="  | base64 -d
picoCTF{ME74D47A_HIDD3N_3b9209a2}

flag : picoCTF{ME74D47A_HIDD3N_3b9209a2}
