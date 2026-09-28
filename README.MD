# Xtensa Assembly Highlighter for VS Code

Syntax highlighting for Xtensa GNU assembly, aimed at ESP32-class Xtensa targets such as ESP32, ESP32-S2 and ESP32-S3.

## Preview

![Xtensa Assembly syntax highlighting](https://raw.githubusercontent.com/ForenZes/xtensa-assembly-synatax-highlighter/refs/heads/main/images/xtensa-highlight-preview.png)

## Features

- Xtensa a0-a15 registers and sp
- Common Xtensa special registers
- Xtensa integer, branch, load/store, system and floating-point instructions
- Narrow instruction aliases such as ret.n, addi.n, l32i.n, s32i.n
- GNU assembler directives
- Labels and numeric local labels (1:, 1f, 1b)
- Decimal, hexadecimal, binary and octal immediates
- //, #, and /* ... */ comments
- .s and .S file associations

## Example

```asm
.section .text
.global syContextSwitcher
.type syContextSwitcher, @function
.align 4

syContextSwitcher:
    addi a1, a1, -32
    s32i a0,  a1, 0
    s32i a12, a1, 4
    s32i a13, a1, 8
    s32i a14, a1, 12
    s32i a15, a1, 16

    s32i a1, a2, 0
    mov  a1, a3

    l32i a0,  a1, 0
    l32i a12, a1, 4
    l32i a13, a1, 8
    l32i a14, a1, 12
    l32i a15, a1, 16
    addi a1, a1, 32
    ret
```

If another extension already claims .s, use **Change Language Mode** and select **Xtensa Assembly**.

## Nota bene!

Xtensa cores are configurable, so not every instruction is present on every Xtensa implementation. This extension highlights the common Xtensa/ESP32 instruction families but it does not validate whether a particular opcode is implemented by your exact core configuration.

## Developed by
- GeoSn0w ([Twitter](https://twitter.com/fce365))

For [ForenZes Labs](https://forenzes.com)
