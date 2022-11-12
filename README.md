# Experiment--04-Implementation-of-combinational-logic-using-universal-gates
Implementation of combinational logic using universal-gates
 
## AIM:
To implement the given logic function using NAND and NOR gates and to verify its operation in Quartus using Verilog programming.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')' using NAND gate

F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')' using NOR gate
## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime


## Theory
Logic gates are electronic circuits which perform logical functions on one or more inputs to produce one output. 

## Using NAND gates
NAND gate is actually a combination of two logic gates i.e. AND gate followed by NOT gate. So its output is complement of the output of an AND gate.This gate can have minimum two inputs, output is always one. By using only NAND gates, we can realize all logic functions: AND, OR, NOT, X-OR, X-NOR, NOR. So this gate is also called as universal gate. First note that the entire expression is inverted and we have three terms ANDed. This means that we must use a 3-input NAND gate. Each of the three terms is, itself, a NAND expression. Finally, negated single terms can be generates with a 2-input NAND gate acting as an inverted.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')'

## Using NOR gates
NOR gate is actually a combination of two logic gates: OR gate followed by NOT gate. So its output is complement of the output of an OR gate. This gate can have minimum two inputs, output is always one. By using only NOR gates, we can realize all logic functions: AND, OR, NOT, Ex-OR, Ex-NOR, NAND. So this gate is also called universal gate. Designing a circuit with NOR gates only uses the same basic techniques as designing a circuit with NAND gates; that is, the application of deMorgan’s theorem. The only difference between NOR gate design and NAND gate design is that the former must eliminate product terms and the later must eliminate sum terms.

F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')'

## Program:
/*
Program to implement the given logic function using NAND and NOR gates and to verify its operations in quartus using Verilog programming.

Developed by: S.LOKESH SAI DILEEP

RegisterNumber: 212221230111 
*/

## Using NAND:

module comblogic(a,b,c,d,f);

input a,b,c,d;

output F;

wire f1,f2,f3;

assign f1 = (~c&~b&~a);

assign f2 = (~d&~c&~a);

assign f3 = (c&~(~b)&~a);

assign F= f1&~f2&~f3;

endmodule

## Using NOR Gate:

module comblogic(a,b,c,d,f);

input a,b,c,d;

output F;

wire f1,f2,f3,f4;

assign f1 = c&(~b)&a;

assign f2 = d&(~c)&a;

assign f3 = c&(~b)&a;

assign f4 = ~(f1|f2|f3);

not(F,f4);

endmodule

## Output:
## RTL
![image](https://user-images.githubusercontent.com/94883079/201469075-35f41fcd-b7b5-4304-8268-48a8e5dacf18.png)

## Timing Diagram:
![image](https://user-images.githubusercontent.com/94883079/201469092-9642828e-3cbe-4c0c-968d-2609ccce78bb.png)

## Truth table:

![image](https://user-images.githubusercontent.com/94883079/201469130-6c898a4d-f9af-4508-a11e-76dbb39937ce.png)

## Program 2:
## RTL:
![image](https://user-images.githubusercontent.com/94883079/201469186-55f3d37a-10e2-468c-ae98-820894c6ced6.png)

## Timing Diagram:
![image](https://user-images.githubusercontent.com/94883079/201469200-e6933889-9504-490e-bb03-b96d6a9bbda2.png)

## Truth Table:
![image](https://user-images.githubusercontent.com/94883079/201469223-7332823a-a25c-4723-acf8-d6311e86a9ed.png)

## Result:
Thus the given logic functions are implemented using NAND and NOR gates and their operations are verified using Verilog programming.
