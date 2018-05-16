there's other ways to do the same thing. You can attach to Xcode by providing the process identifier, or PID, of a running program.
Open Xcode, then open a new Terminal session, and finally run the following:


```
dengjiangzhou% pgrep -x Xcode
7556
dengjiangzhou% lldb -p 7556
(lldb) process attach --pid 7556

```





This will output the PID of the Xcode process.
Next, run the following, replacing 89944 with the number output from the command above: