# RISC-V Single-Cycle Datapath Trace

An interactive tool for tracing how a single RV32I instruction flows through the single-cycle datapath. It was built for use in CSCI 26000, Computer Architecture II.

The datapath is drawn in the standard Patterson & Hennessy single-cycle construction. When an instruction is entered, the tool colors only the wires that instruction actually uses and labels each with the value it carries, so a student can read one instruction as a path through the hardware rather than as a static wiring diagram.

## Features

- Draws the single-cycle datapath in the standard textbook construction
- Colors only the wires a given instruction uses, and leaves the rest gray
- Labels every active wire with the value it carries that cycle
- Color-codes each route (fetch, register data, immediate, ALU result, branch, write-back) consistently
- Fills the mux ports that are selected and lights the control signals that are asserted
- Toggles data values between decimal and hexadecimal (addresses are always shown in hex)
- Has a blank mode that hides all values for board work and quizzes
- Runs entirely in the browser with no dependencies or network requests

## Supported Instructions

- **R-Type:** `add`, `sub`, `and`, `or`, `xor`, `sll`, `srl`, `sra`, `slt`, `sltu`
- **I-Type:** `addi`, `andi`, `ori`, `xori`, `slli`, `srli`, `srai`, `slti`, `sltiu`
- **Load:** `lw`
- **Store:** `sw`
- **Branch:** `beq`

These are the instructions expressible on the Patterson & Hennessy single-cycle datapath. Instructions that require hardware outside that figure (for example `jal` or `jalr`) are rejected with a message rather than drawn.

The tool does not support labels for branching, so to trace an example with branch-on-equal (`beq`), you enter the offset as a number. For example, `beq t0, t1, 48` conditionally jumps 48 forward relative to PC, and then traces through the datapath like any other instruction.

## Running Locally

Open `index.html` in a web browser. No installation or build step is required.