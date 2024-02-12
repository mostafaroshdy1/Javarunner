#!/bin/bash

# Function to compile Java files
compile_java() {
    javac "$1" 2>&1
}

# Function to run Java program
run_java() {
    java "${1%.*}" "${@:2}"
}

# Function to check if compilation is necessary
needs_compilation() {
    if [ ! -f "${1%.*}.class" ]; then
        return 0  # File doesn't exist, needs compilation
    fi
    if [ "$1" -nt "${1%.*}.class" ]; then
        return 0  # Source file is newer, needs compilation
    fi
    return 1  # No need for compilation
}

# Main function
main() {
    # Check if any Java file is provided
    if [ $# -eq 0 ]; then
        echo "Usage: $0 <java_file> [args]"
        exit 1
    fi

    java_file="$1"
    shift

    # Check if compilation is necessary
    if needs_compilation "$java_file"; then
        echo "Compiling $java_file..."
        compile_java "$java_file"

        # Check if compilation is successful
        if [ $? -ne 0 ]; then
            echo "Compilation failed!"
            exit 1
        fi
    else
        echo "Using existing .class file for $java_file"
    fi

    # Run Java program
    run_java "$java_file" "$@"
}

# Run main function
main "$@"
