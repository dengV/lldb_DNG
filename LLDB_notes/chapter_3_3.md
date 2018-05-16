Another way to attach to a process is to specify the path to the executable and manually
launch the process at your convenience:

```
dengjiangzhou% lldb -f /System/Library/CoreServices/Finder.app/Contents/MacOS/Finder
(lldb) target create "/System/Library/CoreServices/Finder.app/Contents/MacOS/Finder"   // 这行是自动的


```



This will set Finder as the executable to launch. Once you’re ready to begin the debug session, simply type the following into the LLDB session:


```
(lldb) process launch

```


<hr>


<hr>


<hr>


> Note: An interesting side effect is that stderr output (i.e. NSLog & company) are automatically sent to the Terminal window when manually launching a process. Other LLDB attaching configurations don’t do this automatically.





<hr>


<hr>



Options while launching
The process launch command comes with a suite of options worth further exploration. If you’re curious and want to see the full list of available options for process launch, simply type help process launch.


```
help process launch

```


Close previous LLDB sessions, open a new Terminal window and type the following:


```
dengjiangzhou% lldb -f /bin/ls

```



This tells LLDB to use /bin/ls (the file listing command) as the target executable.







>
> Note: If you omit the -f option, LLDB will automatically infer the first argument to be the executable to launch and debug. When debugging Terminal executables, I'll oftentimes type lldb $(which ls) (or equivalent), which then gets translated to lldb /bin/ls.
>


> 翻译： 忽略 -f 选项， 自动用参数选项的 默认第一个

