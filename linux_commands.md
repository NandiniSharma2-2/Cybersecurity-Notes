Linux Commands : 

1. pwd   : print current working directory

2. dir   : print contents of current directory or selected path

3. cd    : Change directory
   a) cd -  : move to previous working directory
   b) cd -- :
   c) cd ~  : Go to home directory
   d) cd .. : move one directory up


4. grep  : search specified string in a file

   Use : grep "string" filename

   a) grep -i "string" filename
      case-insensitive

   b) grep -v "string" filename
      inverts the result (displays line not containing the specified string)


5. | (pipe symbol) : send output of a command as input to the other command

   Use : ls | grep "string"
         (can search for a file or folder in the selecvted directory)


6. ls    : lists contents of current folder (traditional UNIX menthod)

7. ls -a : Display hidden files

8. ls -l : Display files with file permissions


   NOTE : ls -la, detailed list(time, date, ownership..) and hidden files


8. clear : clear screen


9. cat   : Displays contents of a file

   cat filename


10. mkdir : create a directory

11. rmdir : Delete an empty directory

12. touch : create a file


13. rm    : Removes a file (content or not)

    a) rm -r directory
       removes a diirectory and everything inside it

    b) rm -rf directory
       *DANGEROUS* beacause it recursively removes files/directories


14. mv    : move a file/directory to a new location

    mv file/directory location


    NOTE : Renaming a file

    mv oldname newname


15. cp    : copy a file/directory to a new location.


16. nano  : a) Terminal based file editor, open an existing file in nano from the selected
              directory

            b) Create a new file

    nano filename


17. find  : Search directories/ files that meet a specific criteria like,

    a) contain a specific string in the name
    b) are a certain file size
    c) were last modified within a certain time frame

    - find . -name "*.log"
      finds for files wiith extension .log

    - find . -type f -size +10M
      find files larger than 10MB

    - find . -type f -mtime -1
      find diles modified within the last day


18. man   : Displays information on other commands and how they work

    man ls


19. whatis : Displays one line description of a command


20. apropos : searches manual page names to help you find the exact command you need when
             you only know the concept or keyword

    It is extremely useful when you remember the concept but do not remember the command

    Use: apropos "list directory"


21. tree  : show directory structure of working directory

22. less  : read large files

23. head  : display first few lines

24. tail  : display last lines

25. tail -f : watch file in real time


26. sort  : sorts a file line by line (alphatically/numerically a-z or A-z,
            a has high priority than A)

    a) sort -r : reverse sorting

    Use : sort filename


# Types of ownerships:

1. user(owner) : An user is the owner of a file they create
                 They have read/write/execute permissions on those files


2. group       : A "group of users", all members share the group's permissions

   a) created with :
      sudo groupadd <group name>

   b) users added with :
      sudo usermod -aG <groupname> <username>

   c) group ownership of a file/folder changed with :
      sudo chown : <groupname> <filename>


NOTE :

- sudo chown :designer project.txt
  Changes the group to designer but the owner of project.txt remain the same
  with users in designer group having permissions on project.txt

- sudo chown aarya project.txt
  Chaanges the owner to aarya(user) and keeps the group same

- sudo chown aarya:designer project.txt
  Chnages both owner and the group


# permissions:

u = user/owner
g = group
o = others

r = read
w = write
x = execute


1. chmod u+rwx, g+rwx, o+rwx file/directory.

2. chmod u-rwx, g-rwx, o-rwx file/directory.

3. chmod u=r, g=r, o=r file/directory.


# sudo commands:

--sudo : Temporarily grants elevated permission to a specific user.


1. add a user :
   sudo useradd username.

2. delete a user :
   sudo userdel username.
