# Cat command
cat is used to read files, the challege asks u to read flag file 
here flag is an arrgument
```
hacker@commands~cat-not-the-pet-but-the-command:~$ /challenge/run ~/flag
cat: /challenge/DESCRIPTION.md: No such file or directory
hacker@commands~cat-not-the-pet-but-the-command:~$ ls
a  flag  h
hacker@commands~cat-not-the-pet-but-the-command:~$ cat flag
pwn.college{sdNg5smUjmBrDRv_ynJDxQCI-i-.QXxcTN0wiN2QDN3EzW}
```

# Catting absolute paths 
her flag is reffered to using absolute path /flag 
```
hacker@commands~catting-absolute-paths:~$ cat /flag
pwn.college{MxMHs_bVU5YfQ5sTsOLo3NWbSrp.QX5ETO0wiN2QDN3EzW}
```

# more catting practice 
using absolute path to retirive the flag 
```
hacker@commands~more-catting-practice:~$ /lib/python3.12/logging/flag
bash: /lib/python3.12/logging/flag: Permission denied
hacker@commands~more-catting-practice:~$ cat /lib/python3.12/logging/flag
pwn.college{ovVBIbwvQR4Br9yIuyhUb9TneMx.QXwITO0wiN2QDN3EzW}

```
# grepping for needle 
grep is used to search in the file using a key word
syntax : grep {string} path 

```
hacker@commands~grepping-for-a-needle-in-a-haystack:~$ grep pwn.college /challenge/data.txt
pwn.college{o40mmX4bOUvap41A3XjbR8bgZe3.QX3EDO0wiN2QDN3EzW}
```
# comparing files 
diff is used to compare two files for differnce
xCy shows the diffence in two files 
xAy shows that a line in extra in either of the file 

```
hacker@commands~comparing-files:~$ diff /challenge/decoys_only.txt /challenge/decoys_and_real.txt
55a56
> pwn.college{MMbXY4vgSTF-qSu7cxX50oB8BPZ.01MwMDOxwiN2QDN3EzW}
```

# listing files 
ls is used to list all the files present in the directorate 

```
hacker@commands~listing-files:~$ ls /challenge
18066-renamed-run-26583  Dockerfile
hacker@commands~listing-files:~$ cat /challenge/18066-renamed-run-26583
#!/usr/bin/exec-suid -- /bin/bash -p

echo "Yahaha, you found me! Here is your flag:"
cat /flag
hacker@commands~listing-files:~$  /challenge/18066-renamed-run-26583
Yahaha, you found me! Here is your flag:
pwn.college{IS6tavKhWoatSo0m4XH31Yrln7C.QX4IDO0wiN2QDN3EzW}

```
# touching files 
touch is the easiest way to create a new blank file
you can not create a new file using touch by giving a absolute path 
```
hacker@commands~touching-files:~$ touch /temp/pwn 
touch: cannot touch '/temp/pwn': No such file or directory
hacker@commands~touching-files:~$ ls
a  h
hacker@commands~touching-files:~$ cd /tmp
hacker@commands~touching-files:/tmp$ touch pwn 
hacker@commands~touching-files:/tmp$ touch college 
hacker@commands~touching-files:/tmp$ ls
college  pwn
hacker@commands~touching-files:/tmp$ /challenge/run
Success! Here is your flag:
pwn.college{Y6TvH8lMqEugVs0UcWn9BB5zvm0.QXwMDO0wiN2QDN3EzW}
```
# removing files 
rm is used to remove files form the directory 

```
hacker@commands~removing-files:~$ touch delete_me
hacker@commands~removing-files:~$ ls 
a  delete_me  h
hacker@commands~removing-files:~$ rm delete_me 
hacker@commands~removing-files:~$ /challenge/check
Excellent removal. Here is your reward:
pwn.college{IfEQts2O1r9tAkBWZfRYyKQJ9jP.QX2kDM1wiN2QDN3EzW}
```

# moving files 
mv is used to move the file to a new location and then the file ceases
to exist 
synatax: mv [file to be moved] [new loc/ file moved to] 
absolute ya relative path bith can be used 

```
hacker@commands~moving-files:~$ mv /flag /tmp/hack-the-planet 
Correct! Performing 'mv /flag /tmp/hack-the-planet'.
hacker@commands~moving-files:~$ /challenge/run 
bash: /challenge/run: No such file or directory
hacker@commands~moving-files:~$ /challenge/check
Congrats! You successfully moved the flag to /tmp/hack-the-planet! Here it is:
pwn.college{kOCwWTxWbzte7gGpDo79D2WqUvl.0VOxEzNxwiN2QDN3EzW}
```

# copying files 
cp is used when u dont want to delete the file and keep the original 
source code 
syntax is similar to mv 

```
hacker@commands~copying-files:~$ cp /flag /tmp/hack-the-planet 
Correct! Performing 'cp /flag /tmp/hack-the-planet'.
hacker@commands~copying-files:~$ /challenge/check
Congrats! You successfully copied the flag to /tmp/hack-the-planet! Here it is:
pwn.college{A3Leb5OwLWs8pk6KxyUcy41csAa.0lNxQTMywiN2QDN3EzW}
```

# hidden files 
ls -a shows all the files in directory inculading the one starting with {.}
by default ls does not list files strting with . to acces that 
we have to use ls -a 

```
hacker@commands~hidden-files:~$ cd /
hacker@commands~hidden-files:/$ ls -a
.           .flag-81731476121572  challenge  home   media  opt   run   sys  var
..          bin                   dev        lib    mnt    proc  sbin  tmp
.dockerenv  boot                  etc        lib64  nix    root  srv   usr
hacker@commands~hidden-files:/$ .flag-81731476121572
bash: .flag-81731476121572: command not found
hacker@commands~hidden-files:/$ cat .flag-81731476121572
pwn.college{YQzBAECm4j0qhK1eMYXYiJECXzg.QXwUDO0wiN2QDN3EzW}
```

# an epic quest 
## notes 
to access the files in a direcory without cding trough it use ls directory 
after that to read the file use cat path/file_name
```
hacker@commands~an-epic-filesystem-quest:~$ cd /
hacker@commands~an-epic-filesystem-quest:/$ ls
NUGGET  boot       dev  flag  lib    media  nix  proc  run   srv  tmp  var
bin     challenge  etc  home  lib64  mnt    opt  root  sbin  sys  usr
hacker@commands~an-epic-filesystem-quest:/$ cat tmp
cat: tmp: Is a directory
hacker@commands~an-epic-filesystem-quest:/$ cat root 
cat: root: Permission denied
hacker@commands~an-epic-filesystem-quest:/$ cat NUGGET
Yahaha, you found me!
The next clue is in: /usr/share/man/es/man1

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/$ cat /usr/share/man/es/man1
cat: /usr/share/man/es/man1: Is a directory
hacker@commands~an-epic-filesystem-quest:/$ /usr/share/man/es/man1
bash: /usr/share/man/es/man1: Is a directory
hacker@commands~an-epic-filesystem-quest:/$ usr/share/man/es/man1
bash: usr/share/man/es/man1: Is a directory
hacker@commands~an-epic-filesystem-quest:/$ tougch temp
bash: tougch: command not found
hacker@commands~an-epic-filesystem-quest:/$ touch temp
touch: cannot touch 'temp': Permission denied
hacker@commands~an-epic-filesystem-quest:/$ cp /usr/share/man/es/man1 NUGGET
cp: -r not specified; omitting directory '/usr/share/man/es/man1'
hacker@commands~an-epic-filesystem-quest:/$ ls /usr/share/man/es/man1 NUGGET
NUGGET

/usr/share/man/es/man1:
BLUEPRINT-TRAPPED      lexgrog.1.gz     manconv.1.gz  which.1.gz
apropos.1.gz           man-recode.1.gz  manpath.1.gz  which.debianutils.1.gz
dpkg-distaddfile.1.gz  man.1.gz         whatis.1.gz   zsoelim.1.gz
hacker@commands~an-epic-filesystem-quest:/$ cat BLUEPRINT-TRAPPED 
cat: BLUEPRINT-TRAPPED: No such file or directory
hacker@commands~an-epic-filesystem-quest:/$ ls /usr/share/man/es/man1
BLUEPRINT-TRAPPED      lexgrog.1.gz     manconv.1.gz  which.1.gz
apropos.1.gz           man-recode.1.gz  manpath.1.gz  which.debianutils.1.gz
dpkg-distaddfile.1.gz  man.1.gz         whatis.1.gz   zsoelim.1.gz
hacker@commands~an-epic-filesystem-quest:/$ cat /usr/share/man/es/man1/BLUEPRINT-TRAPPED
Congratulations, you found the clue!
The next clue is in: /usr/lib/x86_64-linux-gnu/perl/5.38.2/gnu

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/$ cd /usr/lib/x86_64-linux-gnu/perl/5.38.2/gnu
hacker@commands~an-epic-filesystem-quest:/usr/lib/x86_64-linux-gnu/perl/5.38.2/gnu$ ls
ALERT  stubs-64.ph  stubs.ph
hacker@commands~an-epic-filesystem-quest:/usr/lib/x86_64-linux-gnu/perl/5.38.2/gnu$ cat ALERT
Great sleuthing!
The next clue is in: /usr/share/perl/5.38.2/Config
hacker@commands~an-epic-filesystem-quest:/usr/lib/x86_64-linux-gnu/perl/5.38.2/gnu$ cd /usr/share/perl/5.38.2/Config
hacker@commands~an-epic-filesystem-quest:/usr/share/perl/5.38.2/Config$ ls
Extensions.pm  Perl  SNIPPET
hacker@commands~an-epic-filesystem-quest:/usr/share/perl/5.38.2/Config$ cat SNIPPPET
cat: SNIPPPET: No such file or directory
hacker@commands~an-epic-filesystem-quest:/usr/share/perl/5.38.2/Config$ cat SNIPPET
Yahaha, you found me!
The next clue is in: /usr/local/src

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/usr/share/perl/5.38.2/Config$ ls /use/local/src
ls: cannot access '/use/local/src': No such file or directory
hacker@commands~an-epic-filesystem-quest:/usr/share/perl/5.38.2/Config$ cd /
hacker@commands~an-epic-filesystem-quest:/$ ls /use/local/src
ls: cannot access '/use/local/src': No such file or directory
hacker@commands~an-epic-filesystem-quest:/$ ls /usr/local/src
EVIDENCE-TRAPPED
hacker@commands~an-epic-filesystem-quest:/$ cat /usr/local/src/EVIDENCE-TRAPPED
Tubular find!
The next clue is in: /usr/share/doc/python3-pyelftools

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/$ cd /usr/share/doc/python3-pyeftools 
bash: cd: /usr/share/doc/python3-pyeftools: No such file or directory
hacker@commands~an-epic-filesystem-quest:/$ cd /usr/share/doc/python3-pyelftools 
hacker@commands~an-epic-filesystem-quest:/usr/share/doc/python3-pyelftools$ ls -a
.  ..  .TIP  changelog.Debian.gz  copyright
hacker@commands~an-epic-filesystem-quest:/usr/share/doc/python3-pyelftools$ cat .TIP
Yahaha, you found me!
The next clue is in: /usr/share/perl/5.38.2/Test/Builder

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'
oYLfjFxLJLSMeVqIYVK3eCs2H1m.QX5IDO0wiN2QDN3EzW

```
# making directories 
mkdir is used to make new directoied mkdir can handel an absolute path directly 
to create a new file within the directlry 

use touch path/file_name
```
hacker@commands~making-directories:~$ mkdir /tmp/pwn
hacker@commands~making-directories:~$ ls 
a  h  tmp
hacker@commands~making-directories:~$ cd tmp
hacker@commands~making-directories:~/tmp$ mkdir pwn
mkdir: cannot create directory ‘pwn’: File exists
hacker@commands~making-directories:~/tmp$ ls
pwn
hacker@commands~making-directories:~/tmp$ cd /pwn
bash: cd: /pwn: No such file or directory
hacker@commands~making-directories:~/tmp$ /challenge/run
Uh oh! /tmp/pwn/college does not exist. Please use the 'touch' command to 
create it!
hacker@commands~making-directories:~/tmp$ touch college
hacker@commands~making-directories:~/tmp$ /challenge/run
Uh oh! /tmp/pwn/college does not exist. Please use the 'touch' command to 
create it!
hacker@commands~making-directories:~/tmp$ touch /tmp/pwn/college
hacker@commands~making-directories:~/tmp$ /challenge/run
Success! Here is your flag:
pwn.college{Yn46r1JYjSOHt-jkYLMMiqbTqWI.QXxMDO0wiN2QDN3EzW}

```
# findinf files 
how to use files 
file can be used with absolute path 
and if the path is unknow use [find / -name "keyword"]

# linking files 
simlink ln -s 
hard link ln 
file it tells u the character of the content in the file and slo shows if its hard/soft link

a soft link does not override the existing file hece we had to delte the old file coopy the contents into the delted file and then run challenge/catflg as it is designed to pit to the delteed file at defualt 

```
hacker@commands~linking-files:~$ ln -s /flag /home/hacker/not-the-flag
ln: failed to create symbolic link '/home/hacker/not-the-flag': File exists
hacker@commands~linking-files:~$ rm /home/hacker/not-the-flag
hacker@commands~linking-files:~$ ln -s /flag /home/hacker/not-the-flag
hacker@commands~linking-files:~$ /challenge/catflag
About to read out the /home/hacker/not-the-flag file!
pwn.college{4R81KbhJu5HYaDgHL3N6QoYcYDw.QX5ETN1wiN2QDN3EzW}
hacker@commands~linking-files:~$
```
