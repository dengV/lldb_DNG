
## Open a new Terminal window. Next, edit the Terminal tab’s title by pressing ⌘ + Shift + I. A new popup window will appear. Edit the Tab Title to be LLDB.





### Create a new Terminal tab by pressing ⌘ + T. Edit the tab’s title again using ⌘ + Shift + I and name the tab Xcode stderr. This Terminal tab will contain all output when you print content from the debugger.



<hr>

<hr>

<hr>


Make sure you are on the Xcode stderr Terminal tab and type the following: 

> ~ $ tty
 


You should see something similar to below:
  /dev/ttys027
Don’t worry if yours is different; I’d be surprised if it wasn’t. Think of this as the address to your Terminal session.



<hr>

<hr>




dengjiangzhou% echo "hello DNG" 1>dev>ttys001
### X

dengjiangzhou% echo "hello debugger Deng " 1>/dev/ttys001
## √


dengjiangzhou% echo "hello DNG" 1>dev/ttys001            
zsh: not a directory: dev/ttys001
## X

dengjiangzhou% echo "hello DNG" 1>/dev/ttys001  
# 好