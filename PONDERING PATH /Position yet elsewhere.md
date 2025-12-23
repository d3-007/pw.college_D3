# Position yet elsewhere 
The challenge requires you to navigate trough files by using the keyword cd as a command and passing a path as its argument.

## My Solve
**Flag:** 'pwn.college{wbF168Du3VYHBoE8OTzwi6Hzr4S.QX3QTN0wSOwEzNzEzW}'


```
hacker@paths~position-yet-elsewhere:~$ /challenge/run
Incorrect...
You are not currently in the /proc/144/fd directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-yet-elsewhere:~$ cd /proc/144/fd
hacker@paths~position-yet-elsewhere:/proc/144/fd$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{wDSjjC7bKcbWI5q6H8XRkb3aZiQ.QX4QTN0wSOwEzNzEzW}

```

## What I Learned
The correct directory was given in the challenge instructions when you run /challenge/run from the wrong location, which will give the right directory.
/challenge/run is an absolute path, invoked from the right directory after changing the directory.


'
