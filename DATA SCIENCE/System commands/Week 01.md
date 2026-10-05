In system commands we are going to learn linux commands and how to operate with terminal to command our computer. 
Some basic commands:-
- pwd:- Shows you the current directory you are in 
- ls:- Shows you all the files in ur current directory
- ps:- Shows you all the terminals and processes running 
- uname:- Shows the name of your os
- clear and ctrl + L:- To clear the terminal page
- exit and ctrl + d:- to close the shell
- ls -a :- list all the files (even hidden)
- ls -l :- shows all the files in a long format with their dates, locations and time added.
- man (command):- you can write man in front of any command to get the manual of the particular command. This manual has many sections and you can list the number of section before the command to get a particular section. 
- cd - :- this would put u in the previous directory where you were. 
- cd ~ :- this will take u to home directory 
- cal :- shows u the current calendar
- cal aug 1947:- shows you calendar of august 1947, you can also use number of the month instead of the name 
- ncal:- different orientation calendar
- free:- shows amount of memory available 
- free -h:- to make it readable for human
- groups:- shows the users on the computer
- mkdir:- helps you make a folder
- chmod:- it is a Unix/Linux command used to change file or directory permissions.
- touch filename:- to make an empty file
- cp filename1 filename2:- copies filename1 and makes filename2 with filename1 content
- mv filename .. :- move file to parent directory
- mv filename filename2 :- to change name of a file
- mv filename "file name":- to change name of a file to a name which has spaces. "" are used so that it wont take file and name as two diff arguments
- chmod 700 "file name":- changing permissions of a file with space in its name.
-  rm filename:- remove file 
- alias rm =" rm - i":- This is a very interesting command as here we are setting rm as the alias for rm -i. rm -i is used when u dont want rm to take permission of yes or no before removing and it removes the file directly. this alias allows u to use rm in place of rm -i so that everytime u use rm it will remove the file without asking for permission. 
- less filename :- allows u to read a file
- file filename:- allows u to see if the file is a text file or binary, will so ascii text if its readable. it will also show if its executable 
- touch filename :- if this filename file exists then it will change its timestamp to current. 
date:- Tells you the current timestamp, U can do man date to see what all formats you u can use to print date. 
![[Screenshot 2026-10-02 at 9.31.03 PM.png|435]]


File system hierarchy of linux:-
![[Screenshot 2026-10-06 at 1.54.04 AM.png|651]]
gphani is home directory
here we use . for current directory and .. for parent directory
![[Screenshot 2026-10-06 at 1.58.32 AM.png|531]]

![[Screenshot 2026-10-06 at 1.58.55 AM.png|532]]

![[Screenshot 2026-10-06 at 1.59.23 AM.png|549]]
![[Screenshot 2026-10-06 at 1.59.41 AM.png|554]]

### File types and modifications

![[Screenshot 2026-10-06 at 2.12.25 AM.png|548]]

In this photo we see how a file is listed when we do ls -l. The first letter tells the type of file. Then the 3 letters following file type tell u the permissions of owner, next 3 tell u the permission of group and next 3 tell u the other permissions. then comes the number of hard links, the owner name, the group name, the size of the file, last modified timestamp of the file and then the name of the file. 

Lets see the file types in this picture:-
![[Screenshot 2026-10-06 at 2.15.05 AM.png|540]]

![[Screenshot 2026-10-06 at 2.24.17 AM.png|564]]

This is how the permission string is structured which comes after your file type. 
here r is read, w is write and x is execute

Now that we know how to how to read types and permissions of a file lets see how to change these permissions. 
U can create a file in ur home directory and by default it will have 775 permission
here is how we can change it:-
`chmod g-x filename`
here g means group permissions.
for others:-
`chmod o-w filename`
But instead of changing everything one by one you can just use the number system:-

`chmod 750 filename`

#### Hard Links
A hard link is another filename that points to the same underlying file (inode).
Think of it as giving one file multiple names.
 Creating a Hard Link
First, create a file:
```echo "hello" > file.txt```
Create a hard link:
```ln file.txt copy.txt```
Now:
```text
file.txt ──┐
           ├──> same inode / same data
copy.txt ──┘
```

`file.txt` and `copy.txt` are **not two separate copies**. They are two names referring to the same underlying file.
#### Modifying a Hard Link
If we modify `copy.txt`:
```echo "hello world" >> copy.txt```
The change will also appear when reading `file.txt`:
```cat file.txt```
Output:
```text
hello
hello world
```
This happens because both names refer to the **same data**.
#### Deleting a Hard Link
Suppose we delete the original name:
```rm file.txt```
`copy.txt` will still work.
```text
file.txt  ❌
copy.txt  ───> actual data
```
Deleting a filename only removes **that particular link**.
The underlying data is deleted only when **all hard links to it are removed**.
#### Inodes
Every file has an **inode** that stores information about the file and points to its data.
We can see the inode number using:
```ls -li```
Example:
```text
12345 -rw-r--r-- 2 user user 6 file.txt
12345 -rw-r--r-- 2 user user 6 copy.txt
```
Both files have the same inode number:
This confirms that they are hard links to the same underlying file.
The `2` represents the **number of hard links** to that inode.
