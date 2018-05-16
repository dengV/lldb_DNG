all the different ways you can attach LLDB to processes using various options, as well as what happens behind the scenes when attaching to processes.



<hr>


The phrase of LLDB “attaching” is actually a bit misleading. A program named debugserver (found in Xcode.app/Contents/SharedFrameworks/LLDB.framework/ Resources/) is responsible for attaching to a target process.



<hr>


If it’s a remote process, such as an iOS, watchOS or tvOS application running on a remote device, a remote debugserver gets launched on that remote device. It’s LLDB’s job to launch, connect, and coordinate with the debugserver to handle all the interactions in debugging an application.




<hr>


<hr>




Open Xcode, then open a new Terminal session, and finally run the following:


```
dengjiangzhou% lldb -n Xcode

```


<hr>


<hr>


