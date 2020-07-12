# Mr-Robot-CTF
#TryHackMe

TASK 1 = Connect and deploy the machine

TASK 2 = Before going further uou should make a practice to do some recon like nmap and dirb on the ip as it will help in future.

Key 1 = Follow the hint given
         (ip/robots.txt)
         
Dirb results = After performing dirb on this ip we found many directories and so i have close look on each of them.
In the license page i found some interesting texts and further scrolling down i got a Base64 encoded string.I used cyberchef to decode the string and i got a username and password.
From my dirb scan i also got wp-login page.I have applied the credentionals i got earlier and we have successgully logged in.

After login,I checked Users tab and find out that Elliot has administrative privileges. So the first thing that came to my mind was to upload reverse shell. I got this reverse shell from pentestmonkey . 
Before using the shell remember to edit the php file for ip address and port

I started the listener at my localhost.
Using curl command i triggered the injected php.

BBOOMM

I got reverse shell at my listener side!

After alot of search in the shell i got the 2nd key but IT CAN ONLY BE SEEN BY ROOT(ROBOT)

But we have yet another file password.raw-md5. So it is encrypted(md5) password for user robot.

I decrypted the file by online md5 decoder tool(Using Google)

We should spawn some good tty terminal using python
Google python tty and get the correct command.



So now i ran su command to change the user to root.

Got the second key finally!!!

#KEY 3

For 3rd and last key after thinking for a while what else i can do, i decided to check for programs having suid bit on and i also see the hint given(nmap)

nmap has the suid bit set to on which works in interactive mode. That means we can get shell using that.
t 


         
