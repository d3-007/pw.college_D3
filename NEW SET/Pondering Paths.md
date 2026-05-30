# the root 
to invoke a path just use the path name 
cd is to navigate in the system

```
hacker@paths~the-root:~$ /pwn
BOOM!!!
Here is your flag:
pwn.college{gig_0i7oua9EfXGAcy_6Y8v1e7i.QX4cTO0wiN2QDN3EzW}
hacker@paths~the-root:~$ 

```

# Program and absolute paths 
to invoke a path just use the path name 

```
hacker@paths~program-and-absolute-paths:~$ /challenge/run 
Correct!!!
/challenge/run is an absolute path! Here is your flag:
pwn.college{08Ghr3SI7LzePU-xHvRWiW35W5u.QX1QTN0wiN2QDN3EzW} 

```

# Position thy self 
the terminal will show the file under which the flag might be present
enter ablsolte path 

```
hacker@paths~position-thy-self:~$ cd /
hacker@paths~position-thy-self:/$ /challenge/run
Incorrect...
You are not currently in the /sys/kernel directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-thy-self:/$ cd /sys/kernel
hacker@paths~position-thy-self:/sys/kernel$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{sD8BK-qh_0Lbmn6A6lKAhv-i9UV.QX2QTN0wiN2QDN3EzW}

```
# Position elsewhere

```
hacker@paths~position-elsewhere:~$ cd /
hacker@paths~position-elsewhere:/$ /challenge/run
Starting level 1.
Incorrect...
You are not currently in the /etc directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-elsewhere:/$ cd /etc
hacker@paths~position-elsewhere:/etc$ /challenge/run
Starting level 1.
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Moving on to level 2
Please use the `cd` utility to change directory to /sys/kernel
hacker@paths~position-elsewhere:/etc$ cd /sys/kernel
hacker@paths~position-elsewhere:/sys/kernel$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Moving on to level 3
Please use the `cd` utility to change directory to /usr/include
hacker@paths~position-elsewhere:/sys/kernel$ cd /usr/include
hacker@paths~position-elsewhere:/usr/include$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Moving on to level 4
Please use the `cd` utility to change directory to /var/log
hacker@paths~position-elsewhere:/usr/include$ cd /var/log
hacker@paths~position-elsewhere:/var/log$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Moving on to level 5
Please use the `cd` utility to change directory to /usr/bin
hacker@paths~position-elsewhere:/var/log$ cd /usr/bin
hacker@paths~position-elsewhere:/usr/bin$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{0NnpsM9pt_H0JzJf3SeBJfP9sYM.QX3QTN0wiN2QDN3EzW}

```
# implicit relative paths, from /
cwd is realtive to 
is my path is /a/b/c then 
id cwd is /, relative path is a/b/c 
and cwd is /a, relative path is /b/c

```
hacker@paths~implicit-relative-paths-from-:~$ cd /
hacker@paths~implicit-relative-paths-from-:/$ challenge/run
Correct!!!
challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{ECLnPK8toUz_ZT1rllpg9Pe2Uso.QX5QTN0wiN2QDN3EzW}
```

# explicite realtive path, from /
mian concept is the diffentiate btw relative and absolute 
relative c/./ or c, or ./c (basically does not start with root )
absolute /c, /c/., /././c

```
hacker@paths~explicit-relative-paths-from-:~$ cd /
hacker@paths~explicit-relative-paths-from-:/$ challenge/run
Incorrect...
This challenge must be called with a relative path that explicitly starts with a `.`!
hacker@paths~explicit-relative-paths-from-:/$ ./challenge/run
Correct!!!
./challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{wvsRm6XH5kO6rhepI6dQ6tNauRa.QXwUTN0wiN2QDN3EzW}

```

# implicit relative path 

```
hacker@paths~implicit-relative-path:~$ cd /challenge
hacker@paths~implicit-relative-path:/challenge$ ./run
Correct!!!
./run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{Y3o1I-Y2j8_CjxKlSob6VWtdF1Z.QXxUTN0wiN2QDN3EzW}
```

# home sweet home 
so 
hacker@dojo:~$ /challenge/run YOUR_PATH_HERE
is the the comand where u have to pass the argument, 
now the condition says 
1. Your argument must be an absolute path.
2. The path must be inside your home directory.
3. Before expansion, your argument must be three characters or less.

so path has to have ~/{a single letter}, here the flag is being 
copied into a new path which is rading back to us 

```
hacker@paths~home-sweet-home:~$ /challenge/run ~/hello
The argument you provided must not have been longer than 3 characters (it's 
currently 7 characters long)!
hacker@paths~home-sweet-home:~$ /challenge/run ~/h
Writing the file to /home/hacker/h!
... and reading it back to you:
pwn.college{Q8NakcQr8P8jAan5XRw_dRA3yfw.QXzMDO0wiN2QDN3EzW}

```
