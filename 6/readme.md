## 🖼️ Understanding Frames in GDB

### 📚 Overview of Frames

- A running application maintains a **call stack** that has details of its invoked functions.
- Each item on this stack is known as a **call frame**.
    - Each frame carries:
        - The required details to revert to its caller.
        - The necessary data for the function's local variables.
- On program initiation, the call stack only contains the frame of `main` function.
- Each function call **pushes** a new frame onto the stack, and every function return **pops** the frame of that function.
- Recursive functions might result in multiple frames.

For practicing, you can use `backtrace.c`:

```bash
$ gcc backtrace.c -o backtrace -g
$ gdb ./backtrace
(gdb) b main
(gdb) run
(gdb) bt
(gdb) b func1
(gdb) bt
```

### 🔍 Navigating Through Frames

- You can effortlessly **switch** between frames using:  
    ```bash
    (gdb) frame [number]
    ```

### 📋 Fetching Frame Details

- `info frame [number]`: Get details of a specific frame.
    ```bash
    (gdb) info frame 1   # For current frame details.
    ```

- `info variables`: Obtain a list of all global and static variables.
- `info locals`: Displays local variable values of the current stack frame.
- `info args`: Displays argument values of the current stack frame.

### 🖥️ Info on Registers

- `info registers`: Provides a list of all register values.
    ```bash
    (gdb) info registers eax    # For specific register, e.g., eax.
    ```

### 🔗 Info on Breakpoints

- `info breakpoints`: Gives the status of all existing breakpoints.

---

### 🎤 Interview Questions:

1. **Q**: Explain what a call frame is in the context of a running application.  
   **A**: In a running application, each item in the call stack is known as a call frame. Each frame contains the necessary details to revert to its caller and the data for the function's local variables.

2. **Q**: How can you switch between different frames in GDB?  
   **A**: You can switch between different frames using the `frame [number]` command.

3. **Q**: How would you fetch details about a specific frame in GDB?  
   **A**: To get information about a specific frame, use the `info frame [number]` command.

4. **Q**: How can you see the values of the registers in GDB?  
   **A**: Use the `info registers` command to view all register values. For a specific register, say `eax`, use `info registers eax`.

5. **Q**: How can you monitor the status of all breakpoints set in your program via GDB?  
   **A**: The command `info breakpoints` provides the status of all set breakpoints.


## 🖥️ Using GDB to Examine CPU Registers

### 📘 Overview

- When debugging, it can be crucial to inspect the contents of the **CPU registers**.
- **GDB** provides the `i r` command to visualize the current contents of these registers.

### 📝 Details of `i r` command

- **First Column**: This is the **name** of the register.
  
- **Second Column**: Here, you'll find the **bit pattern** of the register's current content, typically displayed in **hexadecimal** notation.
  
- **Third Column**: This section will represent the **value** of the register content in either **32-bit or 64-bit unsigned decimal**, depending on the architecture of the CPU.

### 🔍 Example:

```bash
(gdb) i r
```

This command will output a list of registers with the details as described above.

---

### 🎤 Interview Questions:

1. **Q**: How can you view the contents of the CPU registers while debugging with GDB?  
   **A**: In GDB, you can use the `i r` command to view the current contents of the CPU registers.

2. **Q**: What information is typically displayed when you use the `i r` command in GDB?  
   **A**: The `i r` command in GDB displays three columns: the name of the register, the current bit pattern in the register in hexadecimal, and the register contents in 32-bit/64-bit unsigned decimal.

3. **Q**: How is the bit pattern of a register's content typically represented in GDB?  
   **A**: In GDB, the bit pattern of a register's content is typically represented in hexadecimal notation.

4. **Q**: Why might a developer want to inspect the contents of the CPU registers during debugging?  
   **A**: Inspecting the contents of the CPU registers can provide insights into the current state of a running program, especially when diagnosing low-level issues, understanding flow control, or verifying that operations on data (like arithmetic operations) are producing the expected results in the registers.

---
