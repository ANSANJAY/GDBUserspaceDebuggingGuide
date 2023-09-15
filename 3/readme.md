
# Different Ways to Pass Command Line Arguments in GDB 🖥️📝

Command line arguments are essential when debugging applications that rely on them. GDB provides a variety of methods to incorporate these arguments.

## 1️⃣ Using `--args` Parameter

GDB allows you to run the executable with arguments right from the command line:

```bash
$ gdb --args executablename arg1 arg2 arg3
```

## 2️⃣ Starting Within GDB

First, you start GDB with your executable, and then run it with your desired arguments:

```bash
$ gdb ./a.out
```

And within GDB:

```bash
(gdb) r arg1 arg2 arg3
```

---

## Interview Questions on Passing Command Line Arguments in GDB 🤔

### Q1: How can you initialize GDB with command line arguments directly from the shell?
**A**: You can use the `--args` parameter, like so: `$ gdb --args executablename arg1 arg2 arg3`.

### Q2: If you've already started GDB, how can you run the program with command line arguments?
**A**: Once inside GDB, you can use the `r` or `run` command followed by the desired arguments: `(gdb) r arg1 arg2 arg3`.

### Q3: Why might you want to use command line arguments while debugging with GDB?
**A**: Command line arguments can modify the behavior of the program, enabling the testing and debugging of specific scenarios or functionalities that are triggered by these arguments.

---

Hope this format helps with your interview preparations! Best of luck! 🌟

