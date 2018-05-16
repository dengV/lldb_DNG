> Note: Wondering why the command is po? po stands for print object. There’s also p, which simply prints the contents of RDI. po is usually more useful as it gives the NSObject’s description or debugDescription methods, if available.


## 汇编 的 重要性， 写得好

Assembly is an important skill to learn if you want to take your debugging to the next level. It will give you insight into Apple’s code — even when you don’t have any source code to read from. It will give you a greater appreciation of how the Swift compiler team danced in and out of Objective-C with Swift, and it will give you a greater appreciation of how everything works on your Apple devices.You will learn more about registers and assembly in Chapter 10, “Assembly Register Calling Convention”.


For now, simply know the $rdi register in the above LLDB command contains the instance of the subclass NSView the hitTest: method was called upon.

roduce different results depending on where you clicked and what version of Xcode you’re using. It could give a private class specific to Xcode, or it could give you a public class belonging to Cocoa.

In LLDB, type the following to resume the program:




> (lldb) continue



Instead of continuing, Xcode will likely hit another breakpoint for hitTest: and pause exection. This is due to the fact that the hitTest: method is recursively calling this method for all subviews contained within the parent view that was clicked. You can inspect the contents of this breakpoint, but this will soon become tedious since there are so many views that make up Xcode.



<hr>


<hr>


## Filter breakpoints for important content


Since there are so many NSViews that make up Xcode, you need a way to filter out some of the noise and only stop on the NSView relevant to what you’re looking for. This is an example of debugging a frequently-called method, where you want to find a unique case that helps pinpoint what you’re really looking for.


As of Xcode 9, the class responsible for visually displaying your code in the Xcode IDE is a private Swift class belonging to the IDEPegasusSourceEditor module, named SourceCodeEditorView. This class acts as the visual coordinator to hand off all your code to other private classes to help compile and create your applications.


Let’s say you want to break only when you click an instance of NSView. You can modify the existing breakpoint to stop only on a NSView click by using <strong>breakpoint conditions</strong>.