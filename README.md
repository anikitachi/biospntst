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

