# Position elsewhere 
The challenge requires you to navigate trough files by using the keyword cd as a command and passing a path as its argument.

## My Solve
**Flag:** 'pwn.college{wbF168Du3VYHBoE8OTzwi6Hzr4S.QX3QTN0wSOwEzNzEzW}'


```
hacker@paths~position-elsewhere:~$ cd
hacker@paths~position-elsewhere:~$ cd /
hacker@paths~position-elsewhere:/$ /challenge/run
Incorrect...
You are not currently in the /usr/share/zoneinfo/posix/Asia directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-elsewhere:/$ ^C
hacker@paths~position-elsewhere:/$ cd  /usr/share/zoneinfo/posix/Asia
hacker@paths~position-elsewhere:/usr/share/zoneinfo/posix/Asia$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{wbF168Du3VYHBoE8OTzwi6Hzr4S.QX3QTN0wSOwEzNzEzW}

```

## What I Learned
The correct directory was given in the challenge instructions when you run cd / and run /challenge/run from the wrong location, which will give the right directory.
The given file was in the /usr/share/zoneinfo/posix/Asia direcotry file and i had to change the path of the directory by passing a command cd and argument /usr/share/zoneinfo/posix/Asia which took the control line to home page from where the files was accessed.
/challenge/run is an absolute path, invoked from the right directory after changing the directory.

## References
None.
'
