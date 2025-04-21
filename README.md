# ╔════════════════════════════════════════════════════════╗
# ║               16-bit ALU in Logisim                   ║
# ╚════════════════════════════════════════════════════════╝

📘 DESCRIPTION
This is a digital design of a 16-bit Arithmetic Logic Unit (ALU)
created in Logisim. The ALU performs essential arithmetic and
logic operations, useful in CPU and processor design courses.

──────────────────────────────────────────────────────────────

🧠 FEATURES
├─✔ 16-bit wide inputs and output
├─✔ Supports basic operations:
│    ├─ ADD (A + B)
│    ├─ SUB (A - B)
│    ├─ AND, OR, XOR, NOT
│    ├─ SHIFT LEFT/RIGHT
│    └─ COMPARE (Zero, Carry, Overflow flags)
└─✔ Flag outputs: Zero, CarryOut, Overflow

──────────────────────────────────────────────────────────────

📥 INPUTS
• A[15:0]   - First operand
• B[15:0]   - Second operand
• OP[3:0]   - Operation selector (4-bit control)

📤 OUTPUTS
• OUT[15:0] - Result of the selected operation
• Zero      - High if OUT == 0
• CarryOut  - Set if carry occurred
• Overflow  - Set if result overflowed

──────────────────────────────────────────────────────────────

## 🛠 HOW TO RUN
1. Install Logisim: http://www.cburch.com/logisim/
2. Open `16 bit alu.circ` in Logisim
3. Toggle the OP code and inputs A/B to simulate operations
4. Observe outputs and flags

──────────────────────────────────────────────────────────────

## 🧪 ALU Operation Examples

This section contains working examples for each ALU operation: `ADD`, `AND`, `OR`, and `SUB`. Each table includes operand values, control signals, results, and flag outputs.

---

### ➕ ADD Example

```text
Operand A: 00000001 00000001 (0x0101 = 257)
Operand B: 00000000 00000010 (0x0002 = 2)
Binvert   : 0
CarryIn   : 0
Operation : 10 (ADD)
```

```Result:
00000001 00000011 (0x0103 = 259)
Zero = 0
Carry15 = 0
Overflow = 0
```

---

### 🔀 AND Example

```Operand A: 11110000 10101010 (0xF0AA)
Operand B: 10101010 11110000 (0xAAF0)
Binvert   : 0 (ignored)
CarryIn   : 0 (ignored)
Operation : 00 (AND)```

```10100000 10100000 (0xA0A0 = 41120)
Zero = 0
Carry15 = 1 ✅
Overflow = 0
```

---

### 🟠 OR Example
```
Operand A: 00001111 00000000 (0x0F00)
Operand B: 00000000 11110000 (0x00F0)
Binvert   : 0 (ignored)
CarryIn   : 0 (ignored)
Operation : 01 (OR)
```

```
00001111 11110000 (0x0FF0 = 4080)
Zero = 0
Carry15 = 0
Overflow = 0
```

---

### ➖ SUB Example
```
Operand A: 00010011 00000000 (0x1300 = 4864)
Operand B: 00010000 00000000 (0x1000 = 4096)
Binvert   : 1
CarryIn   : 1
Operation : 10 (A + ~B + 1 → A - B)
```

```
00000011 00000000 (0x0300 = 768)
Zero = 0
Carry15 = 0
Overflow = 0
```
