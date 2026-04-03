# Assembly Word Guessing Game

![Assembly](https://img.shields.io/badge/Language-Assembly-blue)
![x86](https://img.shields.io/badge/Architecture-x86-orange)
![License: MIT](https://img.shields.io/badge/License-MIT-green)

A word guessing game written in x86 assembly language using the Irvine32 library. The program takes a word, randomly replaces some of its letters with underscores, and challenges the user to figure out the missing letters one at a time.

## How It Works

1. The program starts with a predefined word (e.g., `mizzly`).
2. It generates random positions using `RandomRange` and selects roughly half the letters to hide.
3. A deduplication step ensures no position is chosen twice (using conditional jumps to re-roll duplicates).
4. The selected letters are stored in a backup array, and their positions in the word are replaced with `_`.
5. The position array is sorted with a bubble sort so letters are guessed in order.
6. The user is repeatedly prompted to enter the missing letter until all blanks are filled.
7. On success, a congratulatory message is displayed.

## Prerequisites

- **MASM** (Microsoft Macro Assembler) -- included with Visual Studio
- **Irvine32 library** by Kip Irvine ([http://www.kipirvine.com/asm/](http://www.kipirvine.com/asm/))
- A Windows environment (32-bit protected mode)

## How to Run

1. Install Visual Studio with the C++ desktop workload (this includes MASM).
2. Set up the Irvine32 library following the instructions at [kipirvine.com](http://www.kipirvine.com/asm/gettingStartedVS2019/index.htm).
3. Create a new assembly project and add the source file.
4. Build and run:
   - **Build** the solution (`Ctrl+Shift+B`).
   - **Run** with debugging (`F5`) or without (`Ctrl+F5`).

## Key Concepts Demonstrated

- **Random number generation** -- `Randomize` and `RandomRange` for non-deterministic gameplay
- **String manipulation** -- replacing characters at computed offsets
- **Nested loops** -- outer game loop with inner sort and input loops
- **Conditional jumps** -- `je`, `jle`, `jmp` for control flow and duplicate checking
- **Bubble sort** -- sorting the position array in place using register-based comparisons
- **Irvine32 I/O** -- `WriteString`, `ReadString`, `WriteInt`, `Crlf` for console interaction

## License

This project is licensed under the MIT License.
