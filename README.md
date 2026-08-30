<div align="center">
  <h1>💻 my-vm-os</h1>
  <p>
    <strong>A custom operating system written in CVM for the my-vm architecture.</strong>
  </p>
</div>

## 📖 Overview

**my-vm-os** is a "toy" operating system designed to run exclusively on the **my-vm** architecture. It is written in the custom **CVM** programming language and compiled using **my-vm-compiler**. 

The OS leverages the advanced features of the CVM ecosystem, including direct memory access, inline assembly, hardware interrupts, and custom struct layouts to interact with the simulated hardware of the underlying virtual machine.

## ✨ Features

- **VGA Text Mode Support**: Directly writes to the VM's simulated VGA buffer.
- **Interrupt Handling**: Includes interrupt handlers for system events and timer scheduling.
- **Process Scheduling**: Foundation for process management and scheduling via custom `Process` data structures.
- **System Calls**: Low-level I/O operations through inline assembly (`IN`, `OUT`).

## 🚀 Getting Started

### Prerequisites

You need the full toolchain to build and run the OS:
1. **[my-vm-compiler](../my-vm-compiler)** to compile the `.cvm` code to `.asm`.
2. **[my-vm](../my-vm)** to execute the compiled `.asm`.

### Building and Running

1. Compile the OS using the CVM compiler:
```bash
cd ../my-vm-compiler
cargo run --release -- ../my-vm-os/test.cvm ../my-vm-os/kernel.asm
```

2. Run the OS on the VM:
```bash
cd ../my-vm
cargo run --release -- ../my-vm-os/kernel.asm
```

## 🏗️ Ecosystem

This project relies on:
- **[my-vm](../my-vm)**: The Virtual Machine execution engine.
- **[my-vm-compiler](../my-vm-compiler)**: The CVM language transpiler to Assembly.
