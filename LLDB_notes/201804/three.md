
From there, enter the following into LLDB:


 > (lldb) file /Applications/Xcode.app/Contents/MacOS/Xcode

<hr>


This will set the executable target to Xcode.
Note: If you are using a prerelease version of Xcode, then the name and path of Xcode could be different.
You can check the path of the Xcode you are currently running by launching Xcode and typing the following in Terminal:

$ ps -ef `pgrep -x Xcode`


<hr>


Once you have the path of Xcode, use that new path instead.
Now launch the Xcode process from LLDB, replacing /dev/ttys027 with your Xcode stderr tab’s tty address again:


  (lldb) process launch -e /dev/ttys001 --





> 从   (lldb) process launch -e /dev/ttys027 -- 
> 到   (lldb) process launch -e /dev/ttys001 --








### The launch argument e specifies the location of stderr. Common logging functionality, such as Objective-C’s NSLog or Swift’s print function, outputs to stderr — yes, not stdout! You will print your own logging to stderr later.


<hr>






> (lldb) process launch -e /dev/ttys027 --


The launch argument <b>e</b> specifies the location of stderr. Common logging functionality, such as Objective-C’s NSLog or Swift’s print function, outputs to stderr — yes, not stdout! You will print your own logging to stderr later.
