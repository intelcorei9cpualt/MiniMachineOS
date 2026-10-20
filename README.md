# MiniMachineOS

A lightweight, custom operating system written entirely in x86 Assembly that fits within a single 512-byte boot sector. It features a Bash-styled prompt with simulated implementations of standard terminal commands.

## Features
- **Bash Prompt:** Emulates `user@minios:~$ `
- **`echo [text]`:** Dynamically outputs strings directly to your monitor.
- **`sudo`:** Handles unauthorized root user attempts with standard terminal reporting logic.
- **`clear`:** Resets the hardware video display matrix.

## How to Run It

### Prerequisites
You need **NASM** (to compile) and **QEMU** (to run). 

- **Mac:** `brew install nasm qemu`
- **Linux (Ubuntu/Debian):** `sudo apt install nasm qemu-system-x86`
- **Windows:** Install [NASM](https://nasm.us) and [QEMU](https://qemu.org) and add them to your System Path variables.

### Build and Launch
Run the following commands in your computer's terminal:

```bash
# 1. Compile the Assembly file into a 512-byte OS binary
nasm -f bin boot.asm -o boot.bin

# 2. Launch the OS inside an emulator
qemu-system-x86_64 -drive format=raw,file=boot.bin
```
