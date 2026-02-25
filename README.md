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
- [FlexProp](https://github.com/totalspectrum/flexprop/) – Software used for Propeller development

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
