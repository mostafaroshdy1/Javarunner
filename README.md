# Java Compiler and Runner Script (JR)

This Bash script (`JR`) provides a convenient way to compile and run Java programs from the command line. It automates the process of compiling Java source files and running the resulting class files.

## Features

- Compiles Java source files (`*.java`) using the `javac` command.
- Runs compiled Java programs (`*.class`) using the `java` command.
- Checks if compilation is necessary based on file timestamps.
- Displays helpful error messages if compilation fails or if the script is used incorrectly.

## Usage

To use the script, follow these steps:

1. Ensure you have Bash installed on your system. This script is intended to be run in a Unix-like environment (e.g., Linux, macOS, or WSL on Windows).

2. Make sure the script file (`JR`) is executable. If not, you can make it executable using the following command:
   ```bash
   chmod +x JR
3. Run the script with the following command:
   ```bash
   ./JR <java_file> [args]
4. If compilation is necessary, the script will automatically compile the Java source file using the javac command. If compilation fails, the script will display an error message and exit.

5. If compilation is successful or if a precompiled .class file already exists, the script will run the Java program using the java command. Any output produced by the Java program will be displayed in the terminal.

# Notes
- This script assumes that both the javac and java commands are available in your system's PATH.
- Add JR script to /usr/bin to be able to run it anywhere without (`./`).
