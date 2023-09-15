## 📊 Displaying Data in GDB

### 🖨️ Print Command
- The `print` command is used to display the value of variables and other expressions.
    ```markdown
    p [/format] [expression]
    ```
    Examples:
    - `(gdb) print i` - Prints value of `i`.
    - `(gdb) print &i` - Prints the address of `i`.
    - `(gdb) print sizeof(i)` - Prints the size of `i`.
    - `(gdb) print sizeof(&i)` - Prints the size of the address of `i`.

### 🔍 Examining Memory with 'x' Command
- The `x` command examines memory, starting at a particular address.
    - `(gdb) x &i` - Examines memory at the address of `i`.
- Provides precise control over the number of bytes to examine and how to format them.
    - `(gdb) x/4xb &i` - Examines 4 values formatted as hexadecimal numerals, one byte at a time.
- 💡 **Note**: On Intel machines, bytes are stored in “little-endian” order.

### 🧪 Examining Types with `ptype`
- Use `ptype` to know the type of a C expression.
    - `(gdb) ptype i` - Returns the type of `i` which is `int`.
    - `(gdb) ptype &i` - Returns the type of `&i` which is `int *`.
    - `(gdb) ptype main` - Returns the type of the `main` function.

---

### 🎤 Interview Questions:
1. **Q**: How can you use GDB to display the value of a variable?  
    **A**: By using the `print` or `p` command followed by the variable name. For example: `(gdb) print i`.
  
2. **Q**: How can you examine the memory at the address of a variable in GDB?  
    **A**: Using the `x` command followed by the address of the variable. For example: `(gdb) x &i`.
  
3. **Q**: What does the command `(gdb) x/4xb &i` do in GDB?  
    **A**: It examines 4 values starting from the address of `i`, each formatted as a hexadecimal numeral and displayed one byte at a time.

4. **Q**: How can you determine the type of a variable or expression in GDB?  
    **A**: By using the `ptype` command followed by the variable or expression. For example: `(gdb) ptype i`.

5. **Q**: What is "little-endian" order in the context of Intel machines?  
    **A**: On Intel machines, bytes are stored in "little-endian" order, meaning the least significant byte (LSB) is stored first, followed by the remaining bytes in increasing order of significance.
