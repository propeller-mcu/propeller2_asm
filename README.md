# Propeller 2 Assembly Beginner Guides

Welcome to the **Propeller 2 Assembly Guides**, a complete beginner-friendly repository to programming the **Propeller 2 microcontroller** in assembly.

---

## Contents

- [Propeller2 Assembly Beginner Guides](https://github.com/propeller-mcu/propeller2_asm/tree/main/documents) Step-by-step instructions for learning Propeller 2 assembly  
-  [Propeller2 Assembly example programs](https://github.com/propeller-mcu/propeller2_asm/tree/main/example) – Clean P2ASM programs corresponding to each guide 
-  [Propeller2 Assembly video demontrations](https://github.com/propeller-mcu/propeller2_asm/tree/main/videos) – Videos to help you follow along and understand each example

---

## Helpful Resources

- [Parallax Website](https://www.parallax.com/) – Official Propeller 2 info and documentation  
- [Parallax Forums](https://forums.parallax.com/) – Community discussion and support
- [Spin Tools IDE](https://www.maccasoft.com/en/spin-tools-ide/) – a development environment for the Parallax Propeller 1 and 2.
- [FlexProp](https://github.com/totalspectrum/flexprop/) – a simple GUI for creating applications for the Parallax Propeller 1 and 2.

## Updates

### 2026-02-24

#### Safe Program Termination Update

All examples now explicitly terminate with:

```asm
endprog
    jmp #$
```

This prevents execution into variable (`res`) memory and ensures stable PST behavior.

### 2026-02-25

#### Simclk Removal Update

References to the obsolete simclk variable have been removed from all examples. Timing in spin-wait loops and SmartPin routines now relies entirely on real instruction cycles and the system clock (_CLKFREQ), as handled automatically by the compiler or, optionally, asmclk.

#### WAITX / NOP Instruction Timing Correction

In the “WAITX vs NOP” topic, the previous statement that instructions execute in one clock cycle has been corrected. On final Propeller 2 hardware, all base instructions take two clock cycles. This affects timing calculations for spin-wait loops, SmartPin delays, and bit-banging routines.

### 2026-03-03

### General updates

- Fixed all code so res variables for RAM storage are now consistently placed below byte/word/long declarations.
- Tested all programs with FlexProp and the Spin IDE to ensure full compatibility.
- Updated the comparison / if_* Instructions chapter to include the new if_a instruction.
- Added explanation of the wcz flags in the comparison section for clarity.
- Revised the Decimal to String section to include an explanation of the ptra register and its role in memory operations
