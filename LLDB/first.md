
Getting around Rootless
Before you can start working with LLDB, you need to learn about a feature introduced by Apple to thwart malware. Unfortunately, this feature will also thwart your attempts to introspect and debug using LLDB and other tools like DTrace. Never fear though, because Apple included a way to turn this feature off — for those who know what they’re doing. And you’re going to become one of these people who knows what they’re doing!
The feature blocking your introspection and debugging attempts is System Integrity Protection, also known as Rootless. This system restricts what programs can do — even if they have root access — to stop malware from planting itself deep inside your system.
Although Rootless is a substantial leap forward in security, it introduces some annoyances as it makes programs harder to debug. Specifically, it prevents other processes from attaching a debugger to programs Apple signs.
Since this book involves debugging not only your own applications, but any application you’re curious about, it’s important that you to remove this feature while you learn about debugging so you can inspect any application of your choosing.
If you currently have Rootless enabled, you’ll be unable to attach to the majority of Apple’s programs. There are exceptions however, such as any apps shipped on the iOS Simulator.
For example, try attaching LLDB to the Finder application.
Open up a Terminal window and look for the Finder process, like so:


> lldb -n Finder


You’ll notice the following error:
error: attach failed: cannot attach to process due to System Integrity
Protection
Note: There are many ways to attach to a process, as well as specific configurations when LLDB attaches successfully. To learn more about attaching to a process, check out Chapter 3, “Attaching with LLDB”.



<hr>

<hr>
<hr>


Disabling Rootless
To disable Rootless, perform the following steps:
1. Restart your macOS machine.
2. When the screen turns blank, hold down Command + R until the Apple boot logo appears. This will put your computer into Recovery Mode.
3. Now, find the Utilities menu from the top and then select Terminal.
4. With the Terminal window open, type:
csrutil disable; reboot
5. Your computer will restart with Rootless disabled.
You can verify if you’ve successfully disabled Rootless by trying the same command in Terminal again once you log into your account.
lldb -n Finder
LLDB should now attach itself to the current Finder process. The output of a successful
attach should look like this:


<hr>

After verifying a successful attach, detach LLDB by either killing the Terminal window, or typing quit and confirming in the LLDB console.

