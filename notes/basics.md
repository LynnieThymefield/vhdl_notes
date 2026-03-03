# Verilog Basics
## Introduction
Verilog models composes of keywords such as ```module, endmoudle, input, output, wire``` and et cetera. \
Comments on verilog code files are given after ```//```, while multi-line comments begin with ```/*``` and terminates with ```*/``` \
Blank psaces cannot appear within the text of a keyword, identifier, operator or representation of a number. \
Verilog is case sensitive.
## Module decelration
A module is a fundamental component in verilog, it is declared by the keyword ```module``` and must always be terminated by ```endmodule```. ```ports``` are the inputs and outputs of the module. Objects within a module are given identifiers so they can be referenced in other parts of the model. The following syntax is used to declare a module:

```
module identifier(port, port ...) 
// your code
endmodule 
```

Identifiers are composed of alphanumerical characters and ```_```, and they cannot start with a number. \
The ports list is enclosed in parentheses, which should be terminated with a semicolon. \
To define inout and output ports, use used the following syntax:

```
input port, port, port, ..., port;
output port, port, port, ..., port;
```

### Components and gates

Intenral connections are identified by the keyword "wire", which is declared by

```
wire identifier, identifier, ....;
```

The circuit is formed by 12 primitive gates which is predefined, and are identified by the following keywords,

```
and, or, not, nor, nand, xor, xnor, buf
```
The elements of the primitive gate list are refereed to as instantiations of a gate, and each one of them, a gate instance. privitive gate keywords has the following syntax

```
instance instancename(output, input);
```

For example,
```
and G1(C,A,B);
```
Note that *decelration* defines a module and its behaviour, but does not use said module. Once a module is defined, it may be *instantiated* (used) within a design

### Time directive
Propagation delay of a gate is specified using ```#```, the unit time delay can be delcared before the module by using 
```
`timescale 1ns/100ps
```
where ```1ns``` is the unit for time delay, and ```100ps``` is the precision for which the delay is rounded off.

### Other properties 
Identifiers can have multipul bit-width called vectors
```
output [0:3] D; // an output vector with 4 bits
wire [7:0] SUM; // wire vector sum with 8 bits
```
The leftmost square bracket is always the most significant bit of the vector. \
to address a (group of) bit within a vector, use the following syntax
```
D[2] // or 
SUM[2:0] // specifies 3 least significant bits
```
## Test Bench
A test bench consists of a signal generator and instantiation of the module.\
A test bench has no input or output ports.\
```initial``` statements are used to provide initial values.
### Example
The inputs to the circuit are declared with ```reg```,\
the set of statements to be executed are enclosed by ```begin ... end```,\
the test is terminated by system task ```$finish```\ 
Other system functions include
```
$display // Shows one-time value of variables/strings
$write // same as display, without \n
$monitor // display variables whenever a value changes
$time // displays simulation time 
$finish // terminates simulation
```