# Verilog Basics
## Introduction
Verilog models composes of keywords such as ```module, endmoudle, input, output, wire``` and et cetera.\\  
Comments on verilog code files are given after ```//```, while multi-line comments begin with ```/*``` and terminates with ```*/```\\
Blank psaces cannot appear within the text of a keyword, identifier, operator or representation of a number.\\
Verilog is case sensitive.
## Module decelration
A module is a fundamental component in verilog, it is declared by the keyword ```module``` and must always be terminated by ```endmodule```. ```ports``` are the inputs and outputs of the module. Objects within a module are given identifiers so they can be referenced in other parts of the model. The following syntax is used to declare a module:\\
```module identifier(port, port ...) 
// your code
endmodule 
```\\
identifiers are composed of alphanumerical characters and ```_```

