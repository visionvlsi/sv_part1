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
time|4 state data type, 64-bit unsigned integer

#### Real, shortreal, and realtime data types

- Real, shortreal, and realtime data types – Known as real variables.
    - real – same as double datatype in C
    - shortreal – same as a float in C
    - realtime – interchangeably used with the real data type.

#### void data type
Non-existence data is known as a void data type. It is usually used with functions where it’s return type is void.

#### String
An ordered collection of characters is called a string data type. The length of string variables may vary during simulation, hence the variable having type string is dynamic in nature.

#### Event
Data type event is a handle to a synchronization object. The object which is referenced by an event variable can be triggered and waited for.

event is_empty; // declaration of is_empty event.
As proceeding further, we will discuss events in detail.

#### User-defined types
User-defined types use keyword typedef which is an extension of SystemVerilog data type.

typedef int myint;  // Declaration
myint a,b;          // Usage of user defined data type.

#### Enumeration
A set of integral named constants is called an enumerated type. It defines a set of named values having an anonymous int type.

enum {red, yellow, green} traffic_signal;
//Anonymous int type -> red = 0, yellow = 1 and green = 2

#### Logic data type
In Verilog behavior modeling, always, and initial procedural blocks use reg data type whereas, in dataflow modeling, continuous assignment uses wire data type. SystemVerilog allows driving signals in the ‘assign’ statements and procedural blocks using logic data type. The logic is a 4-state data type that allows capturing the Z or X behavior of the design.
