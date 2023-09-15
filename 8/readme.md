## 👁️ Watchpoints in GDB

### 📘 Overview

Unlike breakpoints, which halt execution at specific lines or functions, **watchpoints** monitor variables. When specified variables are read or written, the watchpoint triggers, pausing the program's execution.

### 📝 Using Watchpoints

- **Setting a Write Watchpoint**: Monitor when a variable gets written to.

  ```bash
  (gdb) watch [variable_name]
  ```

  Note: Ensure the variable is within the current scope when setting a watchpoint on non-global variables.

- **Setting a Read Watchpoint**: Monitor when a variable is read.

  ```bash
  (gdb) rwatch [variable_name]
  ```

- **Setting a Read/Write Watchpoint**: Monitor both reads and writes to a variable.

  ```bash
  (gdb) awatch [variable_name]
  ```

- **Disabling Watchpoints**: Watchpoints can be disabled just like breakpoints.

  ```bash
  (gdb) info breakpoints          # This will list all breakpoints and watchpoints
  (gdb) disable [watchpoint_number]
  ```

---

### 🎤 Interview Questions:

1. **Q**: How do watchpoints differ from breakpoints in GDB?  
   **A**: While breakpoints pause execution at specific lines or functions, watchpoints monitor variables. Execution halts when the monitored variables are read or written.

2. **Q**: You suspect a variable `count` is being unexpectedly modified. How would you use GDB to monitor when `count` is written to?  
   **A**: You can set a write watchpoint on `count` using the command `(gdb) watch count`.

3. **Q**: If you wanted to check every instance where the variable `array` is either read from or written to, how would you set a watchpoint in GDB?  
   **A**: You can set a read/write watchpoint using the command `(gdb) awatch array`.

4. **Q**: How can you disable an active watchpoint in GDB?  
   **A**: You can list all active breakpoints and watchpoints using `(gdb) info breakpoints`. Then, use `(gdb) disable [watchpoint_number]` to disable the desired watchpoint.

---

This structured note should help with your interview preparations on the topic of Watchpoints in GDB.
