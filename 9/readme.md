## 🔡 GDB Text User Interface (TUI)

### 📖 Overview

**GDB's TUI** is a terminal interface leveraging the `curses` library. It provides an enhanced view of the debugging session by segmenting the display into different text windows, each catering to a unique aspect of debugging.

### 📜 Windows Displayed:

1. **Source File**: Shows the source code of the program being debugged.
2. **Assembly Output**: Provides an assembly representation of the code.
3. **Program Registers**: Displays the CPU register values.
4. **GDB Commands**: Displays and takes in GDB commands.

🔍 **Availability**: TUI mode is dependent on the availability of a compatible `curses` library on the platform.

🚀 **Activation**: Invoke GDB with `gdbtui` or `gdb -tui` for TUI mode. You can also toggle TUI mode during a GDB session using TUI-specific commands and key bindings.

### 🎹 Commands and Key Bindings:

- `Ctrl-l`: Repaints the screen, especially useful when output from commands like `printf` disrupt the view.
  
- `Ctrl-x a`: Toggles in and out of TUI mode.
  
- `Ctrl-x o`: Alternates focus between the command line view and the source code view. In the command line view, arrow keys will navigate the entered command or scroll through command history. In the source code view, they'll scroll the displayed code.

---

### 🎤 Interview Questions:

1. **Q**: What is the primary advantage of GDB's TUI mode over the regular command-line interface?  
   **A**: The TUI mode provides a segmented display which simultaneously shows the source code, assembly output, program registers, and GDB commands, making it easier to visualize the debugging session.

2. **Q**: How do you activate the TUI mode when launching GDB?  
   **A**: You can start GDB in TUI mode by invoking it with `gdbtui` or `gdb -tui`.

3. **Q**: Imagine the source code view in TUI is disrupted by outputs of some commands. How do you refresh the screen?  
   **A**: Use the `Ctrl-l` key binding to repaint the screen.

4. **Q**: How can you switch focus between the command line view and the source code view in TUI mode?  
   **A**: You can switch focus using the `Ctrl-x o` key binding.

---

This revised note and interview questions should serve as a comprehensive guide on GDB's Text User Interface (TUI).
