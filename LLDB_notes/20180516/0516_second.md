
## 第二段


<hr>


```
Last login: Wed May 16 14:45:07 on ttys001
/Users/dengjiangzhou/.zshrc:7: no such file or directory: span
/Users/dengjiangzhou/.zshrc:13: parse error near `\n'
dengjiangzhou% lldb 
(lldb) help process launch
     Launch the executable in the debugger.

Syntax: 

Command Options Usage:
  process launch [-s] [-A <boolean>] [-p <plugin>] [-w <directory>] [-a <arch>] [-v <none>] [-c[<filename>]] [-i <filename>] [-o <filename>] [-e <filename>] [<run-args>]
  process launch [-st] [-A <boolean>] [-p <plugin>] [-w <directory>] [-a <arch>] [-v <none>] [-c[<filename>]] [<run-args>]
  process launch [-ns] [-A <boolean>] [-p <plugin>] [-w <directory>] [-a <arch>] [-v <none>] [-c[<filename>]] [<run-args>]
  process launch [-s] [-A <boolean>] [-p <plugin>] [-w <directory>] [-a <arch>] [-v <none>] [-X <boolean>] [<run-args>]

       -A <boolean> ( --disable-aslr <boolean> )
            Set whether to disable address space layout randomization when
            launching a process.

       -X <boolean> ( --shell-expand-args <boolean> )
            Set whether to shell expand arguments to the process when
            launching.

       -a <arch> ( --arch <arch> )
            Set the architecture for the process to launch when ambiguous.

       -c[<filename>] ( --shell=[<filename>] )
            Run the process in a shell (not supported on all platforms).

       -e <filename> ( --stderr <filename> )
            Redirect stderr for the process to <filename>.

       -i <filename> ( --stdin <filename> )
            Redirect stdin for the process to <filename>.

       -n ( --no-stdio )
            Do not set up for terminal I/O to go to running process.

       -o <filename> ( --stdout <filename> )
            Redirect stdout for the process to <filename>.

       -p <plugin> ( --plugin <plugin> )
            Name of the process plugin you want to use.

       -s ( --stop-at-entry )
            Stop at the entry point of the program when launching a process.

       -t ( --tty )
            Start the process in a terminal (not supported on all platforms).

       -v <none> ( --environment <none> )
            Specify an environment variable name/value string (--environment
            NAME=VALUE). Can be specified multiple times for subsequent
            environment entries.

       -w <directory> ( --working-dir <directory> )
            Set the current working directory to <path> when running the
            inferior.
     
     This command takes options and free-form arguments.  If your arguments
     resemble option specifiers (i.e., they start with a - or --), you must use
     ' -- ' between the end of the command options and the beginning of the
     arguments.
(lldb) ^D
dengjiangzhou% lldb -f /bin/ls
(lldb) target create "/bin/ls"
Current executable set to '/bin/ls' (x86_64).
(lldb) process launch
Process 8439 launched: '/bin/ls' (x86_64)
40151516952930_.pic_hd.jpg	Music
Applications			Pictures
DefaultFontFallbacks.plist.bak	Public
Desktop				awesome-terminal-fonts
Documents			compile_commands.json
Downloads			dev
Gemfile				fonts
Gemfile.lock			hi.aiff
IdeaProjects			oh-my-zsh-powerline-theme
Library				one.png
Movies				ttys001
Process 8439 exited with status = 0 (0x00000000) 
(lldb) 
```