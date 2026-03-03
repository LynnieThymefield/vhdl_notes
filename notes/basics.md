# Verilog Basics

## Introduction

Verilog models are composed of keywords such as `module`, `endmodule`, `input`, `output`, `wire`, and others. Comments in Verilog are written after `//`, while multi-line comments begin with `/*` and end with `*/`. Blank spaces cannot appear within keywords, identifiers, operators, or number literals. Verilog is case-sensitive.

## Module Declaration

A module is the fundamental building block in Verilog. It is declared with the `module` keyword and must always be terminated with `endmodule`. Ports define the inputs and outputs of a module. Objects within a module are assigned identifiers so they can be referenced elsewhere in the design. The following syntax declares a module:

```verilog
module identifier(port, port, ...)
  // your code
endmodule
```

Identifiers consist of alphanumeric characters and underscores (`_`), and cannot start with a number. The ports list is enclosed in parentheses and terminated with a semicolon. To define input and output ports, use the following syntax:

```verilog
input port, port, port, ..., port;
output port, port, port, ..., port;
```

### Components and Gates

Internal connections are identified by the keyword `wire`, declared as follows:

```verilog
wire identifier, identifier, ...;
```

Circuits are formed using 12 predefined primitive gates:

```
and, or, not, nor, nand, xor, xnor, buf
```

Each gate usage is called a gate instance. Primitive gates follow this syntax:

```verilog
gate_type instance_name(output, input);
```

For example:

```verilog
and G1(C, A, B);
```

**Note:** Declaration defines a module and its behavior, but does not instantiate it. Once defined, a module may be instantiated (used) within a design.

### Time Directive

Propagation delay is specified using `#`. The timescale can be declared before the module using:

```verilog
`timescale 1ns/100ps
```

Here, `1ns` is the unit for time delay, and `100ps` is the precision for rounding.

### Other Properties

Identifiers can have multiple bits, called vectors:

```verilog
output [0:3] D;    // a 4-bit output vector
wire [7:0] SUM;    // an 8-bit wire vector
```

The leftmost bracket represents the most significant bit. To access a single bit or range of bits within a vector, use:

```verilog
D[2]        // single bit
SUM[2:0]    // 3 least significant bits
```

## Test Bench

A test bench consists of a signal generator and module instantiation. Test benches have no input or output ports. The `initial` statement provides initial values.

### Example

Inputs are declared with `reg`. Statements are enclosed by `begin ... end`. Simulation terminates with `$finish`. Common system tasks include:

```verilog
$display  // Display one-time value of variables/strings
$write    // Same as display, without newline
$monitor  // Display variables whenever a value changes
$time     // Display current simulation time
$finish   // Terminate simulation
```
