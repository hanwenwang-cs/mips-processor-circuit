# 16-bit MIPS-like Processor (CircuitVerse)

This project implements a simplified 16-bit MIPS-style processor, designed and simulated in [CircuitVerse](https://circuitverse.org), as part of CS211: Computer Architecture (Spring 2025) at Rutgers University.

 **Live Project**: [View Phase 3 Processor in CircuitVerse](https://circuitverse.org/simulator/embed/phase-3-r-i-j-types)

---

## Instruction Support

| Type   | Instruction | Description                           |
|--------|-------------|---------------------------------------|
| R-type | `ADD`       | Reg[rd] = Reg[rs] + Reg[rt]           |
|        | `SUB`       | Reg[rd] = Reg[rs] - Reg[rt]           |
|        | `AND`       | Bitwise AND                           |
|        | `OR`        | Bitwise OR                            |
|        | `SLT`       | Set if less than (signed)             |
| I-type | `LOADI`     | Reg[rt] = Immediate                   |
|        | `BEQZ`      | Branch if Zero                        |
|        | `BNEZ`      | Branch if Not Zero                    |
| J-type | `JUMP`      | PC ← target address                   |
|        | `JAL`       | Reg[7] ← return address; jump         |

---

## Components

- **Register File**: 16 registers (4-bit addressing)
- **ALU**: Performs operations based on opcode
- **Control Unit**: 4-bit opcode decoder → ALU control signals + branching
- **MUXes**: Used for selecting ALU inputs and jump targets
- **Zero Flag**: Used by BEQZ and BNEZ
- **Instruction Memory**: ROM manually loaded via RAM
- **PC**: Program Counter with +1 logic and jump control

---

## Tools

- CircuitVerse.org (digital logic simulator)
- No built-in processor blocks; all components manually constructed
