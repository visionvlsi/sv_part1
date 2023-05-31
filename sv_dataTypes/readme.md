## SV Data types will be discussed here

#### Data Types in System Verilog

- A storage format having a specific range or type is called data type.
      - 2 state data type: It has bits 0 and 1
      - 4 state data type: It has bits 0, 1, X, and Z

- Signed and Unsigned
    - Unsigned: can hold positive values alone.
    - Signed: can hold both positive and negative values.

- Literals
    - Fixed value in the program is called literal. In simple terms, it is known as constants. Its value can not be altered during the execution of the program.

- Variables
    - Variables can store any value in memory based on their data type. Its value can be changed during run time.

- Constants
    - The value of constants cannot be changed. It is read-only in nature.

#### Integer Data types

Data type | Description
---|---
int| 2 state data type, 32-bit signed integer
integer| 4 state data type, 32-bit signed integer
shortint| 2 state data type, 16-bit signed integer
longint|2 state data type, 64-bit signed integer
bit|2 state data type, unsigned, user-defined vector size
byte|2 state data type, 8-bit signed integer or ASCII character
logic|4 state data type, unsigned, user-defined vector size
reg|4 state data type, unsigned, user-defined vector size
