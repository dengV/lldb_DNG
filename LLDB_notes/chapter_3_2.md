Attaching to a future process
The previous command only addresses a running process. If Xcode isn’t running, or is already attached to a debugger, the previous commands will fail. How can you catch a process that's about to be launched, if you don’t know the PID yet?
You can do that with the -w argument, which causes LLDB to wait until a process launches with a PID or executable name matching the criteria supplied using the -p or - n argument.



For example, kill your existing LLDB session by pressing Ctrl + D in your Terminal window then type the following:



<hr>

 Ctrl + D  退出 lldb


> 我尝试，  `quit ` 命令 也可以

<hr>



<hr>

-w，


wait 的意思
<hr>

<hr>

<hr>
<hr>


一个 终端 窗口

```

dengjiangzhou% lldb -n Finder -w


```

<hr>


This will tell LLDB to attach to the process named Finder whenever it next launches. Next, open a new Terminal tab, and enter the following:


<hr>

Command + D


另一个 终端 窗口


```

dengjiangzhou% pkill Finder


```


<hr>


<hr>


This will kill the Finder process and force it to restart. macOS will automatically relaunch Finder when it’s killed. Switch back to your first Terminal tab and you’ll notice LLDB has now attached itself to the newly created Finder process.

