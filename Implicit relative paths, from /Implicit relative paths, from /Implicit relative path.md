# Implicit relative paths, from /
This challenge requires you to execute it by invoking relative path of a file 

## My Solve
**Flag:** 'pwn.college{EoJGAhTAD3IjCGApz6gMLNOEF-c.QX5QTN0wSOwEzNzEzW}'

```
hacker@paths~implicit-relative-paths-from-:~$ /challenge/run
Incorrect...
You are not currently in the / directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~implicit-relative-paths-from-:~$ cd /
hacker@paths~implicit-relative-paths-from-:/$ challenge/run
Correct!!!
challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{EoJGAhTAD3IjCGApz6gMLNOEF-c.QX5QTN0wSOwEzNzEzW}
```

## What I Learned
A relative path is any path that does not start at root (i.e., it does not start with /).
Thus, the path to the run challenge by using the relative path while having current working direcotry of /.
Hence, challenge/run is a relative path, invoked from the right directory!

## References
None.
