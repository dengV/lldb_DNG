
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

<hr>


dengjiangzhou% echo "hello debugger Deng " 1>/dev/ttys001
## √


<hr>


dengjiangzhou% echo "hello DNG" 1>dev/ttys001            
zsh: not a directory: dev/ttys001
## X


<hr>


dengjiangzhou% echo "hello DNG" 1>/dev/ttys001  
# 好





<hr>


<hr>



Now switch back to the Xcode stderr tab. The words hello debugger should have popped up. You’ll use the same trick to pipe the output of Xcode’s stderr to this tab.




Finally, close the third, unnamed tab and navigate back to the LLDB tab.




To summarize: You should now have two Terminal tabs: a tab named "LLDB", which contains an instance of LLDB running, and another tab named "Xcode stderr", which contains the tty command you performed earlier.