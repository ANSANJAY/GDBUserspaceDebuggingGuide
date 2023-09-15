## 🔍 Understanding Arrays in GDB

### 🖨️ Print and `ptype` Command for Arrays
- When you have an array like `a` initialized with `{1, 2, 3}`, you can view its content and type using the following commands:
    - `(gdb) print a` - This will display the contents of the array `a`.
        ```markdown
        $2 = {1, 2, 3}
        ```
    - `(gdb) ptype a` - This will display the type of the array `a`.
        ```markdown
        type = int [3]
        ```

### 🔍 Examining Array Memory with 'x' Command
- To see the representation of the array `a` in memory:
    - `(gdb) x/12xb &a` - This examines 12 values (bytes) starting from the address of array `a`, formatted as hexadecimal numerals.
        ```markdown
        0x7fffffffded0:	0x01	0x00	0x00	0x00	0x02	0x00	0x00	0x00
        0x7fffffffded8:	0x03	0x00	0x00	0x00
        ```
    - The 12 bytes are broken down into 3 sets of 4 bytes each. The first four bytes represent `a[0]`, the next four `a[1]`, and the last four `a[2]`.

### 📏 Checking Size of an Array in GDB
- To determine the size of an array in memory, use the `sizeof` operator.
    - `(gdb) print sizeof(a)`
        ```markdown
        $3 = 12
        ```

---

### 🎤 Interview Questions:

1. **Q**: How can you print the contents and type of an array in GDB?  
    **A**: Use the `print` command to display the contents of the array and the `ptype` command to show its type. For example: `(gdb) print a` and `(gdb) ptype a`.

2. **Q**: How can you examine the memory representation of an array in GDB?  
    **A**: Use the `x` command followed by a format, the number of values to examine, and the address of the array. For instance: `(gdb) x/12xb &a`.

3. **Q**: What do the 12 bytes in the command `(gdb) x/12xb &a` represent?  
    **A**: They represent the memory storage of the array `a` with three integers. The first four bytes represent `a[0]`, the next four bytes represent `a[1]`, and the last four bytes represent `a[2]`.

4. **Q**: How can you check the size (in bytes) of an array using GDB?  
    **A**: Use the `sizeof` operator in conjunction with the `print` command. For example: `(gdb) print sizeof(a)`.

---
