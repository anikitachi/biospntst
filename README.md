1.
( a.) Display the path of your current directory
   pwd>> /home/anand
( b.) List out the contents of your current directory
   ls>> Desktop    ''$'\222''h'$'\246\004'   Public            Templates
 Documents   Music                    snap              tgram
 Downloads   Pictures                 spotify-adbloc
( c.) List out the contents of your current directory including hidden files
  ls-a>>     .               .gnupg                   .profile
 ..              .gtkrc-2.0               Public
 .anydesk        .gtkrc-xfce              .python_history
 .bash_history  ''$'\222''h'$'\246\004'   snap
 .bash_logout    .ICEauthority            spotify-adblock
 .bashrc         .icons                   .sudo_as_admin_successful
 .cache          .ipython                 Templates
 .cargo          .jupyter                 tgram
 .config         .linuxmint               .var
 Desktop         .local                   Videos
 .dmrc           .mozilla                 .vscode
 Documents       Music                    .Xauthority
 .dotnet         Pictures                 .xsession-errors
 Downloads       .pki                     .xsession-errors.old

2.
( a.) Create a new directory named a
   mkdir a
( b.) Move to the newly created directory a
   cd a
( c.) Create a blank file named “file1”
    touch file1
( d.) Display the file type of “file1”
     file file1 <<<<file1:empty
( e.) Add the line “Hello World” to “file1” using the command echo
   echo “Hello World”  >file1
( f.) Display the contents of “file1”
   cat file1
( g.) Display the file type of “file1” again   
   file file1  <<<<file1:ASCII text
3.
( a.) Stay in directory a. Create a file “file2” and add the contents below using the  command cat
First Line Second Line Third Line
   
   cat>file2<<EOF 
 > FIRST LINE.
 > SECOND LINE.
 > THIRD LINE.
 > EOF

( b.) Display the contents of “file2”
  cat file2:
FIRST LINE.
SECOND LINE.
THIRD LINE.
( c.) Display the contents of “file2” with the lines reversed
  tac file2:
  THIRD LINE.
  SECOND LINE.
  FIRST LINE.


4.
( a.) Stay in directory a. Concatenate the contents of “file1” and “file2” and save them into a new file “file3”
  cat file1 file2 >file3
( b.) Display the contents of “file3”
  cat file3:
     hello world
     FIRST LINE.
    SECOND LINE.
    THIRD LINE.
5.
( a.) Stay in directory a. Create 2 directories b/c with a single command
mkdir b c
( b.) Create a new directory d
 mkdir d
( c.) Copy the directory d to directory c using a single command
 cp -r d c
( d.) Delete the directory d in the current directory a
  rmdir d
( e.) Copy “file3” to the directory d with a single command

   cp file3 /home/anand/a/c/d


6.
( a.) Go to directory d and rename “file3” to “file0”
cd a/c/d
mv file3 file0
( b.) Stay in the same directory and move “file0” to directory a
  mv file0 /home/anand/a


7.
( a.) Go to your home directory
 cd
( b.) Create a file named “test” in the directory a/b/c/d
  mkdir a/b/c
  mkdir a/b/c/d
  touch a/b/c/d/test
( c.) Stay in the home directory. Find and display the path of “test”
  cd
 find ~/ -name "test" -type f

      result  :/home/anand/a/b/c/d/test

8.
( a.) Go to directory a. Get the man page of grep and save its contents to a file named “grepman.txt”
   cd a
   man grep>grepman.txt
( b.) Print the lines containing the word “FILE” (Case sensitive) in the file “grepman.txt”
   grep “FILE” grepman.txt
9.
( a.) Go to directory a and remove the directory b with a single command
   cd a
   rm -r b
( b.) Remove the files starting with the word “file” with a single
command
   rm file*

10.
( a.) Go to https://blog.bi0s.in/  and download the logo.png image using wget
     wget -P /home/anand/Documents/bashwrk https://blog.bi0s.in/assets/logo.png

(b.) Do the same with python script (Hint : request library)
  python code:
import requests
url='https://blog.bi0s.in/assets/logo.png'
out=requests.get(url)
if out.status_code==200:
   with open('samp','wb') as file:
     file.write(out.content)
     print("Done") 
  
save it as .py
navigate  to the containing folder and enter
  python3 scriptforlogo.py

(c.) Also, display the metadata of the png.
import requests
from PIL import Image
url='https://blog.bi0s.in/assets/logo.png'
out=requests.get(url)
if out.status_code==200:
  with open('samp','wb') as file:
  file.write(out.content)
  print("Done") 

  img=Image.open('samp')
  print("Image format:",img.format)
  print("Image mode:",img.mode)
  print("Image size:",img.size)
  print("Image info:",img.info)

output:
Done
Image format: PNG
Image mode: RGBA
Image size: (1606, 1233)
Image info: {'dpi': (299.9994, 299.9994)}

11.
( a.) Use traceroute on google.com and find list of the IP addresses and hostnames between you and  google.com

traceroute google.com
traceroute to google.com (142.250.196.14), 30 hops max, 60 byte packets
 1  _gateway (192.168.181.77)  65.199 ms  65.185 ms  65.174 ms
 2  255.0.0.0 (255.0.0.0)  439.371 ms  439.366 ms  439.425 ms
 3  255.0.0.2 (255.0.0.2)  444.367 ms  444.477 ms  444.349 ms
 4  255.0.0.3 (255.0.0.3)  439.245 ms  439.197 ms  439.225 ms
 5  192.168.224.99 (192.168.224.99)  444.291 ms  444.282 ms  444.273 ms
 6  192.168.153.20 (192.168.153.20)  441.649 ms 192.168.153.36 (192.168.153.36)  565.562 ms 192.168.153.34 (192.168.153.34)  565.461 ms
 7  * * *
 8  * * *
 9  * * *
10  * * *
11  * * 172.253.73.34 (172.253.73.34)  601.625 ms
12  142.251.55.232 (142.251.55.232)  601.521 ms 216.239.43.172 (216.239.43.172)  596.294 ms 142.251.55.66 (142.251.55.66)  596.340 ms
13  108.170.253.97 (108.170.253.97)  596.219 ms 108.170.253.113 (108.170.253.113)  596.232 ms 74.125.242.139 (74.125.242.139)  596.260 ms
14  maa03s44-in-f14.1e100.net (142.250.196.14)  596.193 ms 108.170.253.113 (108.170.253.113)  601.277 ms 108.170.253.97 (108.170.253.97)  601.233 ms







( b.) Find  Subdomains,ip addresses of google.com (Tool i will add if you want me to
 pip install sublist3r

create account in virustotal , copy the api key since virustotal was giving errors

sublist3r -d google.com -v '--virustotal apikey' -o subdom.txt
all the subdomains  are now stored in subdom.txt file
to check for the ipadresses:
while read -r line; do dig +short "$line"; done < subdom.txt
this lists all the ipadresses of the subdomains

12.
Start a web server on port 8080 with python command
(In any directory and access the files in web browser )

cd Documents/bashwrk
python -m https.server 8080

proceed to http://localhost:8080 to access the files

13.
( a.) Learn about nmap and use that scanner to scan your own machine
   use the command   ip addr to get the ipaddress of your machine
    nmap <your ip>  scans your machine and gives detaiils accordingly
( b.) Go to https://tryhackme.com/room/furthernmap and get ip address and
Scan the ip address with (-sS,-sV,-A) in your terminal include all ports
(Hint : start machine )
nslookup https://tryhackme.com/room/furthernmap

 this gives the ip of the site too
nmap -p- -sS -sV -A 127.0.0.53#53
make sure you are superuser while doing this
-p is for all ports the arguments that follow are the types of scannings
output:
Starting Nmap 7.80 ( https://nmap.org ) at 2024-01-01 22:06 IST
Nmap scan report for localhost (127.0.0.53)
Host is up (0.000075s latency).
Not shown: 65534 closed ports
PORT   STATE SERVICE VERSION
53/tcp open  domain?
| fingerprint-strings: 
|   DNSVersionBindReqTCP: 
|     version
|_    bind
1 service unrecognized despite returning data. If you know the service/version, please submit the following fingerprint at https://nmap.org/cgi-bin/submit.cgi?new-service :
SF-Port53-TCP:V=7.80%I=7%D=1/1%Time=6592EA2E%P=x86_64-pc-linux-gnu%r(DNSVe
SF:rsionBindReqTCP,20,"\0\x1e\0\x06\x85\x82\0\x01\0\0\0\0\0\0\x07version\x
SF:04bind\0\0\x10\0\x03");
No exact OS matches for host (If you know what OS is running on it, see https://nmap.org/submit/ ).
TCP/IP fingerprint:
OS:SCAN(V=7.80%E=4%D=1/1%OT=53%CT=1%CU=33660%PV=N%DS=0%DC=L%G=Y%TM=6592EACB
OS:%P=x86_64-pc-linux-gnu)SEQ(SP=100%GCD=1%ISR=104%TI=Z%CI=Z%II=I%TS=A)OPS(
OS:O1=MFFD7ST11NW7%O2=MFFD7ST11NW7%O3=MFFD7NNT11NW7%O4=MFFD7ST11NW7%O5=MFFD
OS:7ST11NW7%O6=MFFD7ST11)WIN(W1=FFCB%W2=FFCB%W3=FFCB%W4=FFCB%W5=FFCB%W6=FFC
OS:B)ECN(R=Y%DF=Y%T=1%W=FFD7%O=MFFD7NNSNW7%CC=Y%Q=)T1(R=Y%DF=Y%T=1%S=O%A=S+
OS:%F=AS%RD=0%Q=)T2(R=N)T3(R=N)T4(R=Y%DF=Y%T=40%W=0%S=A%A=Z%F=R%O=%RD=0%Q=)
OS:T5(R=Y%DF=Y%T=40%W=0%S=Z%A=S+%F=AR%O=%RD=0%Q=)T6(R=Y%DF=Y%T=40%W=0%S=A%A
OS:=Z%F=R%O=%RD=0%Q=)T7(R=Y%DF=Y%T=40%W=0%S=Z%A=S+%F=AR%O=%RD=0%Q=)U1(R=Y%D
OS:F=N%T=40%IPL=164%UN=0%RIPL=G%RID=G%RIPCK=G%RUCK=G%RUD=G)IE(R=Y%DFI=N%T=4
OS:0%CD=S)

Network Distance: 0 hops

OS and Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 169.92 seconds

14.
( a.) Create a chat application using nc on your local machine with one terminal as server and other as the client

   nc -l 64325
   this command opens server at port 64325. l is given in the command to indicate listen mode for server
   nc <servername> 64325   opens connection to that port as a client and thus texting is possible
( b.) Transfer a file from server to client (save that file with another name) and display the file.
    nc -l 64235 </home/anand/Documents/bashwrk/subdom.txt 
    this command sends the content of subdom.txt from server
   nc Concasser 64235 >out.txt
   saves the content sent from server to out.txt
   exit from client or open new terminal enter cat out.txt to view the file
  

