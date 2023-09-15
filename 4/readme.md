# Debugging Segmentation Fault in GDB 🐞🔍

Segmentation faults are common errors arising due to accessing invalid memory. GDB can be an invaluable tool to pinpoint the exact source of these errors.

## 1️⃣ Compiling the Program with Debugging Flags

Compile with `-g` flag for debugging information:

```bash
$ gcc -g source_code.c
$ gdb ./a.out
```

## 2️⃣ Running and Observing the Crash 💥

```bash
(gdb) run
```

When you see `Program received signal SIGSEGV, Segmentation fault`, it means an invalid memory address was accessed.

## 3️⃣ Using Backtrace to Find the Call Stack 📚

```bash
(gdb) backtrace
```

You can pinpoint where the error occurred:

```bash
(gdb) frame 3
```

Inspecting variables can give clues:

```bash
(gdb) print buf
```

💡 _**Tip**: If `malloc` returns NULL, it means memory allocation failed._

---

# Viewing Source Code in GDB Console 📜

GDB lets you inspect your source code directly in the console.

- **List Source Code**:
  ```bash
  (gdb) list
  ```

  This command prints 10 lines of source code at a time.

- **Specifying Start Point**:

  By line number:
  ```bash
  (gdb) list 12
  ```

  By function:
  ```bash
  (gdb) list main
  ```

  Range of lines:
  ```bash
  (gdb) list 1,14
  ```

---

## Interview Questions on Debugging with GDB 🤔

### Q1: How can you compile your program to be ready for debugging in GDB?
**A**: Use the `-g` flag with `gcc` like so: `$ gcc -g source_code.c`.

### Q2: In the context of GDB, what does SIGSEGV signify?
**A**: It signifies a Segmentation fault, meaning that the program tried to access an invalid memory address.

### Q3: How can you inspect a specific stack frame in GDB?
**A**: Use the `frame` or `f` command followed by the frame number: `(gdb) frame 3`.

### Q4: If you suspect a variable might be causing a segmentation fault, how can you inspect its value in GDB?
**A**: Use the `print` or `p` command followed by the variable name: `(gdb) print buf`.

### Q5: How do you view lines of source code centered around a specific line number or function in GDB?
**A**: Use the `list` command followed by the line number or function name: `(gdb) list 12` or `(gdb) list main`.

---

I hope this format helps with your interview preparations! Best of luck! 🌟🍀
