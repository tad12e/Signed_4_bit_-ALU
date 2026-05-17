**4-Bit Signed Calculator — Logisim-evolution Project**

- **Description:** A 4-bit digital calculator and comparator implemented in Logisim-evolution. The design includes a 1-bit full adder module used to build 4-bit adders/subtractors, two's-complement handling, overflow detection, keypad conversion, and unsigned/negative comparators. This workspace contains the project file ready to open in Logisim-evolution.

- **Main file:** [Final_project.circ](Final_project.circ)

**Features**

- **4-bit arithmetic:** Addition and subtraction using chained 1-bit full adders and two's-complement for signed subtraction.
- **Comparators:** Unsigned and signed (negative-aware) comparators with LED outputs for Greater, Equal, and Less.
- **Overflow & sign handling:** Dedicated overflow detection and sign output circuitry.
- **Keypad to hex conversion:** Keypad converter and hex digit display support.

**Included circuits (high-level)**

- `FullAdder` — 1-bit full adder module used as a building block.
- `main` — Top-level wiring that assembles the full 4-bit calculator, displays, and I/O.
- `Complment_2` — Two's-complement handling for subtraction.
- `MUx` — Multiplexer / routing block used in display or mode selection.
- `OVER` — Overflow detection logic.
- `Unsigned_Comparaotr` — Unsigned comparator logic.
- `Negative_comparator` — Signed comparator for two's-complement inputs.
- `Key_pad_converte` — Converts keypad inputs to 4-bit values and interfaces to displays.

**Requirements**

- Open with Logisim-evolution v4.1.0 (project header indicates this version).

**How to run**

1. Install Logisim-evolution (https://github.com/logisim-evolution/).
2. Open `Final_project.circ` in Logisim-evolution.
3. Use the DipSwitch components or keypad inputs to set operands/mode.
4. Observe results on the Hex Digit Display and the status LEDs (Equal / Less_than / Greater_than / Sign / Overflow).

**Notes & tips**

- The `README.md` in this repository was initially empty; this file gives a short overview. For a circuit-level walkthrough, specify which named box (for example, `FullAdder` or `Unsigned_Comparaotr`) you want explained and I will document its inputs, outputs, and internal logic.

**Credits**

- Project designed for a digital logic course; components built inside Logisim-evolution.

If you'd like, I can (choose one):

-- produce a component list/netlist from `Final_project.circ`;
-- extract and document a specific subcircuit in detail;
-- export schematic images of selected circuits.

**Documented subcircuit: `FullAdder`**

- **Purpose:** 1-bit full adder used as the building block for 4-bit add/subtract operations.
- **Pins:**
  - Inputs: `A`, `B`, `Cin` (carry-in)
  - Outputs: `Sum`, `Cout` (carry-out)
- **Logic (high-level):**
  - `Sum = A xor B xor Cin`
  - `Cout = (A AND B) OR (Cin AND (A xor B))`
- **Implementation (in this project):** two XOR gates compute the sum stages, two AND gates form the partial carry terms, and an OR gate combines them into `Cout`. This matches the standard full-adder structure used when chaining four instances for 4-bit arithmetic.
- **Usage:** The top-level `main` circuit instantiates four `FullAdder` boxes to implement 4-bit addition and subtraction (subtraction via two's-complement in `Complment_2`).

**Exporting schematic images (PNG or SVG)**

If you want images for `FullAdder`, `Unsigned_Comparaotr`, and `main`, follow these steps in Logisim-evolution:

1. Open Logisim-evolution and load `Final_project.circ`.
2. In the project tree, double-click the circuit name you want to export (e.g., `FullAdder`) so it is the active view.
3. Adjust zoom or pan so the circuit is framed as you want (View → Zoom to Fit is helpful).
4. Use File → Export Image (or File → Export → Image) and choose PNG or SVG. Set image size/scale and save.

Notes:

- I cannot render/export images from this environment because it requires the Logisim-evolution GUI or its headless export facility. If you want, I can provide a command-line recipe to export images using the Logisim-evolution JAR (requires Java and the JAR present on your system).
- If you'd like, I can also produce a component list or a textual netlist from the project XML and include it in the repo.
