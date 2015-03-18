# Assembly Cheat

Assembly information and cheatsheets.

Most important files:

-   [Pros and cons](pros-and-cons.md)
-   [IA-32](ia32.md): IA-32 information
    - [ia32/nasm/main/main.asm](ia32/nasm/main/main.asm): main IA-32 and NASM syntax cheatsheet
    - [x86 paging tutorial](http://stackoverflow.com/questions/18431261/how-does-x86-paging-work)
-   [C calling conventions](c-calling-conventions.md)
    - [cdecl](cdecl.md)

## Scope

Topics not covered here:

-   OS specific such as Linux system calls.

	Search for those under their own plaftorm (e.g.: a Linux repo)

-   Compiler specific topics which cannot be done in a portable way, such as inline assembly (assembly in the middle of C code).

	Look for this info under extensions for each compiler.

This repository contains mostly x86 information now, but I'd love to try out other architectures.

## Sources

-   <http://www.tldp.org/HOWTO/Assembly-HOWTO/index.html>

-   <http://en.wikibooks.org/wiki/X86_Assembly/X86_Architecture>

-   Programming from the ground up.

    <http://download.savannah.gnu.org/releases/pgubook/>

    Linux GAS, for complete programming beginners.

-   PC assembly language.

    <http://www.drpaulcarter.com/pcasm/>

    NASM.

-   <https://github.com/dennis714/RE-for-beginners>

    Reverse engineering for beginners.

    Lots of info on what C code maps to in assembly, and how to look for what matters to reverse engineer stuff.

## Instruction set architectures (ISA)

List of operations the processor can do. Obviously ultra processor dependant.

<http://en.wikipedia.org/wiki/Comparison_of_CPU_architectures>

### Popular architectures

Some of the major architectures are:

-   x86 family

-   ARM

    Great majority of mobile phones.

    Low power consumption.

-   SPARC.

### CISC vs RISC

#### RISC

Reduced Instruction set.

Has few operations, but performs each one very fast.

#### CISC

Complex instruction set.

Lots of operations.

It is the case of the x86 family.

### Flynn's taxonomy

<http://en.wikipedia.org/wiki/Flynn%27s_taxonomy>

- SISD
- SIMD
- MIMD

### SIMD instructions

Single instruction, multiple data, for example, making 4 multiplications on a single CPU cycle.

More and more, SIMD instructions are being added on different processors.

For some time now Intel has been grouping those instructions under the `SSE` name.

see: <http://neilkemp.us/src/sse_tutorial/sse_tutorial.html>

## Assemblers

Programs that transform text in computer code.

See also: NASM.

### GAS

GNU assembler.

Executable name: `as`.

GCC backend. Point up to learning its syntax: allows you to to understand GCC generated code!

AT&T based syntax.

Outputs to lots of different architectures:

- i386
- SPARC
- arm

and more.

NASM manual says it is inconvenient to write by hand, maybe because is is meant to be a GCC backend.

#### GCC

GCC can be used as a frontend for gas:

    gcc -S a.c -o a.s
    gcc -masm=att -S a.c -o a.s
    gcc -masm=intel -S a.c -o a.s

### MASM

Microsoft.

x86.

### TASM

Borland.

Stands for "turbo assembler". LOL, why not "basm" instead?

Windows only.
