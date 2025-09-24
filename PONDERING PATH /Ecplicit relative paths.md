# Ecplicit relative paths, from /
This challenge requires you to execute it by invoking a executive relative path of a file 

## My Solve
**Flag:** 'pwn.college{McvLDvWLf9Fz3x_WVyn7OSCMv6J.QXwUTN0wSOwEzNzEzW}'

```
hacker@paths~explicit-relative-paths-from-:~$ cd /
hacker@paths~explicit-relative-paths-from-:/$ challenge/.
bash: challenge/.: Is a directory
hacker@paths~explicit-relative-paths-from-:/$ ./challenge/run
Correct!!!
./challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{McvLDvWLf9Fz3x_WVyn7OSCMv6J.QXwUTN0wSOwEzNzEzW}
hacker@paths~explicit-relative-paths-from-:/$

```

## What I Learned
Every every directory has implicit entries that you can reference in paths: . ,refers right to the same directory
Current working directory is /, the relative paths are equivalent to the above absolute paths.
./challenge/run is a relative path, invoked from the right directory.

## References
None.
