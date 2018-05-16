
# apropos


### The "apropos" command



Sometimes you don’t know the name of the command you’re searching for, but you know a certain word or phrase that might point you in the right direction. The apropos command can do this for you; it’s a bit like using a search engine to find something on the web.



apropos will do a case-insensitive search for any word or string against the LLDB documentation and return any matching results. For example, try searching for anything pertaining to Swift:




<hr>

<hr>


<hr>


You can also use apropos to search for a particular sentence. For example, if you were searching for something that can help with reference counting, you might try the following:



```

(lldb) apropos "reference count"

```