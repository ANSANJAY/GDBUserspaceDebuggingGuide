

# GDB Debugging: Pausing, Observing, and Proceeding 🔍

The primary objective behind using `gdb` is the ability to **pause**, **observe**, and **proceed** in code execution. Essentially, it's all about understanding the behavior of your program by interrupting its flow.

✨ _Remember_: Running a program without a breakpoint in GDB is like watching a movie without stopping to get your popcorn! 🍿

## Breakpoints 🔴

Breakpoints allow you to interrupt the execution of a program at designated points. When `gdb` encounters a breakpoint, it halts your program and offers you the chance to inspect its state.

Setting a breakpoint is straightforward:
- Using the function name:
  ```bash
  (gdb) break factorial 
  ```
  > Breakpoint 1 at 0x400538: file source_code.c, line 5.

- Or specifying a line number:
  ```bash
  (gdb) break 7
  ```
  > Breakpoint 2 at 0x400545: file source_code.c, line 7.

### 📋 Available Functions

To view a list of all the functions:
```bash
(gdb) info functions 
```

### 📍 Available Breakpoints

To see the active breakpoints:
```bash
(gdb) info breakpoints 
```

### 🚀 Execution

Initiate the program. It will pause at the first breakpoint:
```bash
(gdb) r
```

### 🗑️ Managing Breakpoints

- **Delete a breakpoint**:
  ```bash
  (gdb) delete <bpnumber>
  ```

- **Disable a breakpoint**:
  ```bash
  (gdb) disable <bpnumber>
  ```

- **Enable a breakpoint**:
  ```bash
  (gdb) enable <bpnumber>
  ```

## Stepping Through Code 🚶

Once you've paused at a breakpoint, you can finely control the program execution using these commands:

- **Continue** till the next breakpoint or end:
  ```bash
  (gdb) continue
  ```

- **Run** to restart the program from the start:
  ```bash
  (gdb) run
  ```

- **Next**: Go to the next line (skipping function calls):
  ```bash
  (gdb) next
  ```

- **Step**: If on a function call:
  - `next` will run the entire function.
  - `step` will enter the function.
  ```bash
  (gdb) step
  ```

- **Finish** the current function and pause:
  ```bash
  (gdb) finish
  ```

## Inspecting Variables 🔍

- Print the value of a variable:
  ```bash
  (gdb) print n
  ```

- Print the hexadecimal value of a variable:
  ```bash
  (gdb) print/x n
  ```

💡 **Tip**: If you find typing `step` or `next` repeatedly tedious, just press `ENTER`. GDB will repeat the last command you input!

---

## Interview Questions on GDB Breakpoints & Stepping 🤔

### Q1: Why are breakpoints essential in GDB?
**A**: Breakpoints allow you to interrupt the execution of a program at designated points, offering the chance to inspect its state, which is crucial for debugging and understanding program behavior.

### Q2: How do you set a breakpoint at a specific function or line number?
**A**: You can use the command `(gdb) break <function_name>` for a function or `(gdb) break <line_number>` for a specific line.

### Q3: If you're inside a function and want to execute it completely and then pause, which GDB command should you use?
**A**: `(gdb) finish`.

### Q4: What's the difference between the `next` and `step` commands in GDB?
**A**: Both commands proceed to the next line of execution. However, if the current line has a function call, `next` will execute the entire function, while `step` will enter the function.

### Q5: How can you view the value of a variable in hexadecimal format in GDB?
**A**: By using the command `(gdb) print/x <variable_name>`.

---

Hope this format aids you in your interview preparations! All the best! 🌟
