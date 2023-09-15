## 🔍 Conditional Breakpoints in GDB

### 📘 Overview

When debugging, while breakpoints are essential to halt execution at specific lines or functions, sometimes we need to pause only when certain conditions are met. GDB provides **conditional breakpoints** for this purpose.

### 📝 Using Conditional Breakpoints

- **Setting a Conditional Breakpoint**: You can set a breakpoint that halts only when a specific condition is met by using the following syntax:

  ```bash
  break [position] if [expression]
  ```

  Here, `[position]` can be a line number or function name. The `[expression]` is any valid condition, such as `i > 10` or `x == NULL`.

- **Modifying an Existing Breakpoint's Condition**: If you've already set a breakpoint and later decide to add or modify its condition, you can use:

  ```bash
  condition [bp_number] [expression]
  ```

  `[bp_number]` is the breakpoint's number, and `[expression]` is the condition you want to set.

---

### 🎤 Interview Questions:

1. **Q**: What is the primary purpose of a conditional breakpoint in GDB?  
   **A**: A conditional breakpoint allows the debugger to halt execution at a specific breakpoint only when a certain condition is met, offering more fine-grained control during debugging.

2. **Q**: How would you set a conditional breakpoint in GDB that stops execution when the variable `count` equals 10 at line 25?  
   **A**: In GDB, you can use the command `break 25 if count == 10` to set such a conditional breakpoint.

3. **Q**: You've set a breakpoint at function `foo()`. Later, you decide you want the breakpoint to trigger only when the variable `bar` is NULL. How can you modify this breakpoint condition in GDB?  
   **A**: First, you'd find the breakpoint number (e.g., using the `info breakpoints` command). If `foo()`'s breakpoint number is, say, 2, then you would use the command `condition 2 bar == NULL` to set the condition.

4. **Q**: In what scenarios might a conditional breakpoint be especially useful during debugging?  
   **A**: Conditional breakpoints can be invaluable when:
   - Diagnosing issues that only arise under specific conditions.
   - Debugging loops, to stop only after a loop has iterated a certain number of times or met some condition.
   - When there's a recurring function call, and you wish to halt on specific calls, not every call.

---

