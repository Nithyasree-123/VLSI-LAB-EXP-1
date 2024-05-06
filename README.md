# VLSI-LAB-EXPERIMENTS
AIM: To simulate and synthesis Logic Gates,Adders and Subtractor using Xilinx ISE.

APPARATUS REQUIRED: Xilinx 14.7 Spartan6 FPGA

PROCEDURE: STEP:1 Start the Xilinx navigator, Select and Name the New project. STEP:2 Select the device family, device, package and speed. STEP:3 Select new source in the New Project and select Verilog Module as the Source type. STEP:4 Type the File Name and Click Next and then finish button. Type the code and save it. STEP:5 Select the Behavioral Simulation in the Source Window and click the check syntax. STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table. STEP:7 Select the Implementation in the Sources Window and select the required file in the Processes Window. STEP:8 Select Check Syntax from the Synthesize XST Process. Double Click in the Floorplan Area/IO/Logic-Post Synthesis process in the User Constraints process group. UCF(User constraint File) is obtained. STEP:9 In the Design Object List Window, enter the pin location for each pin in the Loc column Select save from the File menu. STEP:10 Double click on the Implement Design and double click on the Generate Programming File to create a bitstream of the design.(.v) file is converted into .bit file here. STEP:12 Load the Bit file into the SPARTAN 6 FPGA STEP:11 On the board, by giving required input, the LEDs starts to glow light, indicating the output.

## Logic Diagram :

Logic Gates:
![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/ee17970c-3ac9-4603-881b-88e2825f41a4)


## Half Adder:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/0e1ecb96-0c25-4556-832b-aeeedfdfe7b9)


## Full adder:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/9bb3964c-438f-469d-a3de-c1cca6f323fb)


## Half Subtractor:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/731470b7-eb4e-49f8-8bb7-2994052a7184)



## Full Subtractor:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/d66f874b-c1f2-44b3-a035-7149b56430c1)



## 8 Bit Ripple Carry Adder:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/7385a408-40a5-4203-8050-b72818622d79)



## VERILOG CODE:
## Logic gates:
```
module logic(a,b,andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate );

input a,b;

output andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate;

and(andgate,a,b);

or(orgate,a,b);

xor(xorgate,a,b);

nand(nandgate,a,b);

nor(norgate,a,b);

xnor(xnorgate,a,b);

not(notgate,a);

endmodule
```
## half adder:
```
module HalfAdder(a,b,sum,carry);

input a,b;

output sum,carry;

xor (sum,a,b);

and (carry,a,b);

endmodule
```
## half subtractor:
```
module halfsubtractor(a,b,diff,borrow);

input a,b;

output diff,borrow;

xor g1(diff,a,b);

and g2(borrow,~a,b);

endmodule
```

## full adder:
```
module FA(a,b,cin,sum,cout);

input a,b,cin;

output sum,cout;

wire w1,w2,w3;

xor g1(w1,a,b);

and g2(w2,w1,cin);

and g3(w3,a,b);

xor g4(sum,w1,cin);

or g5(cout,w2,w3);

endmodule
```
## full subtractor:
```
module full_sub(a,b,bin,diff,borrow);

input a,b,bin;

output diff,borrow;

wire w1,w2,w3;

xor g1(w1,a,bin);

and g2(w2,~a,b);

xor g3(diff,w1,bin);

or g4(borrow,w2,w3);

and g5(w3,~w1,bin);

endmodule
```
## 8 bit ripple carry adder:
```

module fa(a,b,c,sum,carry);

input a,b,c;

output sum,carry;

assign sum = a^b^c;

assign carry=(a&b)|(b&c)|(c&a);

endmodule

module rca(a,b,cin,sum,cout);

input [7:0]a,b;

input cin;

output [7:0]sum;

output cout;

wire c1,c2,c3,c4,c5,c6,c7;

fa fa1(a[0],b[0],cin,sum[0],c1);

fa fa2(a[1],b[1],c1,sum[1],c2);

fa fa3(a[2],b[2],c2,sum[2],c3);

fa fa4(a[3],b[3],c3,sum[3],c4);

fa fa5(a[4],b[4],c4,sum[4],c5);

fa fa6(a[5],b[5],c5,sum[5],c6);

fa fa7(a[6],b[6],c6,sum[6],c7);

fa fa8(a[7],b[7],c7,sum[7],cout);

endmodule
```
# OUTPUT:
## LOGIC GATES:
<img width="855" alt="316595945-d5fd1f18-75b7-4c70-9baf-6734d3a2322f" src="https://github.com/Nithyasree-123/VLSI-LAB-EXP-1/assets/164908713/fd958c7f-8167-4c13-b89d-703d69f415b6">

## HALF ADDER:
<img width="809" alt="316596089-1707f843-4915-488b-a8da-097d6d18dd1c" src="https://github.com/Nithyasree-123/VLSI-LAB-EXP-1/assets/164908713/c1d30921-1189-477e-aafa-5b32d447a9f0">

## HALF SUBSTRACTOR:

<img width="785" alt="316600529-80becf5d-5fb9-428c-9d73-5f58ca738113" src="https://github.com/Nithyasree-123/VLSI-LAB-EXP-1/assets/164908713/e3211efa-837a-4bb6-af22-a78d90b8bfbe">

## FULL ADDER:
![316596287-7624a78b-8766-42d4-aeba-43d1f44bff71](https://github.com/Nithyasree-123/VLSI-LAB-EXP-1/assets/164908713/7beaaabd-810b-4c19-bfad-5be0e13e6e2b)

## FULL SUBSTRACTOR:
<img width="1280" alt="316600739-45f9b76a-97fb-4082-a82f-e463e8675e62" src="https://github.com/Nithyasree-123/VLSI-LAB-EXP-1/assets/164908713/8c1fd5d0-dbab-4030-997a-25fc52e8a0cb">

## 8 BIT RIPPLE CARRY ADDER:

<img width="752" alt="316600882-f9882fac-e3b9-479b-89dc-4297909fe241" src="https://github.com/Nithyasree-123/VLSI-LAB-EXP-1/assets/164908713/3a59c97d-6b2d-4223-8c49-7420934fc44d">



## RESULT:
Hence Logic Gates,Adders and Subtractor are simulated and synthesised using Xilinx ISE.


