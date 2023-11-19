# Digital Logic

## Logic Gates
Digital Logic involves hardware that performs simple operations like AND, OR, NOT. These gates take binary inputs and produce binary outputs. Behavior is described using a truth table.

### Examples:
AND Gate:
  | A | B | Output |
  |---|---|--------|
  | 0 | 0 |   0    |
  | 0 | 1 |   0    |
  | 1 | 0 |   0    |
  | 1 | 1 |   1    |

OR Gate:
  | A | B | Output |
  |---|---|--------|
  | 0 | 0 |   0    |
  | 0 | 1 |   1    |
  | 1 | 0 |   1    |
  | 1 | 1 |   1    |

NOT Gate:
  | A | Output |
  |---|--------|
  | 0 |   1    |
  | 1 |   0    |

NAND and NOR Gates
These gates are the opposites of AND and OR gates.

## Logical Completeness
Any truth table can be implemented using AND, OR, and NOT gates. For example, combining AND gates that yield a "1" and then ORing the results.

Example Circuit:
```
       A
        |
   ___AND___
  |         |
  B         C
```
For A = 0, B = 1, C = 0.

## Beneath the Digital Abstraction
- Digital circuits use discrete values (0 and 1).
- Voltage, being continuous, is used to represent 0s and 1s. Transistors act as switches, representing 1s and 0s.

### Voltage
- Voltage is not discrete; it is continuous.
- Since our hardware is prone to noise (cosmic rays, magnets, etc.), we can use voltage to represent 0s and 1s.
- How do we do this? We use a range of analog values that correspond to digital values (logic).

### Transistor
Microprocessors consist of millions (or billions) of transistors that combine to implement logic functions and build higher-level structures.

## DeMorgan’s Law
Converts AND to OR (with some help from NOT).

### Example:
```
NOT(AB) = (A + B)
```

## NAND and NOR Functional Completeness
Any gate can be implemented using either NAND or NOR gates. This is useful for chip design.

## More Than 2 Inputs
AND/OR gates can take any number of inputs. We can implement this with multiple two-input gates or with a single CMOS circuit.

## Circuit Design
1. Have an idea for a useful circuit.
2. Derive a truth table for the circuit.
3. Using the truth table, derive a boolean expression.
4. Build the circuit using the boolean expression.

### Converting Truth Table to Boolean Expression
- Isolate rows where the output should be true.
- A product term with one instance of every variable is a minterm.
- Sum-of-products (SOP): Build a boolean expression for the entire table.

## Formal Definition of Minterms
A product term in which all variables appear once, either complemented or uncomplemented. Denoted by mX, where X corresponds to the variable assignment for which mX = 1.

### Example (3 variables - A, B, C):
- m0: A'B'C'
- m1: A'B'C
- m2: A'BC'
- ...
- m7: ABC

## Simplifying Boolean Expressions
SOP forms are often not minimal. Two approaches to simplify:
1. Algebraic rules of boolean logic.

### Example:
```
F = AB + AC + BC
F = A(B + C) + BC
```

## Decoder
A combinational circuit with n inputs and 2^n outputs. Converts input patterns to a single output.

### Example:
1:2 Decoder
```
   A
   |
   --- O
   |
   --- O
```
2:4 Decoder can be built from 1:2 decoders.

## Encoder
The inverse of a decoder. Converts m-bit input to n-bit output, where n <= m.

## Multiplexer (MUX)
A combinational circuit with an n-bit selector and 2^n inputs, producing one output. Output equals one of the inputs based on the selector.

## Functions with Decoders or MUXes
For example, F = A'B + BC. Inputs can be connected to the decoder or multiplexer.

### Example:
```
   A ---\
   B ----\___ 1:2 MUX
   C ---/    |
            O
```

---

Quick Recap
- Basic logic gates: AND, NOT, OR
- Building blocks: decoder and multiplexer
- Circuit implementation from truth tables
- Knowledge of minterms and sum of products
- Understanding of basic identities

---

