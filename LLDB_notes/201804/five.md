## Finding a class with a click


> Now that Xcode is set up and your Terminal debugging windows are correctly created and positioned, it’s time to start exploring Xcode using the help of the debugger.

<hr>


<hr>

While debugging, knowledge of the Cocoa SDK can be extremely helpful. For example, - [NSView hitTest:] is a useful Objective-C method that returns the class responsible for the handled click or gesture for an event <strong> in the run loop </strong> . This method will first be triggered on the containing NSView and recursively drill into the furthest subview that handles this touch. You can use this knowledge of the Cocoa SDK to help determine the class of the view you’ve clicked on.


<hr>

In your LLDB tab, type <code>Ctrl + C </code>to pause the debugger. From there, type:


> (lldb) b -[NSView hitTest:]


This is your first breakpoint of many to come. You’ll learn the details of how to create, modify, and delete breakpoints in Chapter 4, “Stopping in Code”, but for now simply know you’ve created a breakpoint on -[NSView hitTest:].
Xcode is now paused thanks to the debugger. Resume the program:


> (lldb) continue


Click anywhere in the Xcode window (or in some cases even moving your cursor over Xcode will do the same); Xcode will instantly pause and LLDB will indicate a breakpoint has been hit.