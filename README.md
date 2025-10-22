# coroutine-tools

```std::coroutine``` debugging tools. 

## Walking the async  call stack

```
Async Stack:
resume:  00007FF7F728D540 C:\...\corodebug.cpp(15732480): corodebug!inner_function$_ResumeCoro$1
resume:  00007FF7F728F750 C:\...\corodebug.cpp(15732480): corodebug!middle_function$_ResumeCoro$1
resume:  00007FF7F7290E10 C:\...\corodebug.cpp(15732480): corodebug!outer_function$_ResumeCoro$1
resume:  00007FF7F7287630 C:\...\corodebug.cpp(15732480): corodebug!spawn_task$_ResumeCoro$1<int>
```

```
```

### Debuggers

#### MSVC
- use the [natvis](corodebug.natvis) file

#### clang
- see the [doc](). YMMV.
- as of clabg 21 no ```std::stacktrace``` support

#### gdb
- no helping scripts. Manually walk the stack: ```info symbol <resumeAddr>```


## Homework
- https://www.youtube.com/watch?v=lKUVuaUbRDk
- https://godbolt.org/z/d7EPTGTdd
- https://releases.llvm.org/21.1.0/tools/clang/docs/DebuggingCoroutines.html
