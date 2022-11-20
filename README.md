# Experiment-08- Encoders-and-decoders 
## AIM: To implement 8 to 3 Encoder and  3to8 Decoder using verilog and validate its outputs
## HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
## SOFTWARE REQUIRED:   Quartus prime
## THEORY 

## Encoders
Binary code of N digits can be used to store 2N distinct elements of coded information. This is what encoders and decoders are used for. Encoders convert 2N lines of input into a code of N bits and Decoders decode the N bits into 2N lines.

1. Encoders –
An encoder is a combinational circuit that converts binary information in the form of a 2N input lines into N output lines, which represent N bit code for the input. For simple encoders, it is assumed that only one input line is active at a time.

As an example, let’s consider Octal to Binary encoder. As shown in the following figure, an octal-to-binary encoder takes 8 input lines and generates 3 output lines.

![image](https://user-images.githubusercontent.com/36288975/171543588-bc0746df-a173-4b35-989e-5fb7d385fe8a.png)
## Figure -01 3 to 8 Encoder 


Implementation –

X = D4 + D5 + D6 + D7
Y = D2 +D3 + D6 + D7
Z = D1 + D3 + D5 + D7 
Hence, the encoder can be realised with OR gates as follows:


![image](https://user-images.githubusercontent.com/36288975/171543740-68403b82-aa93-4c98-9343-f32b14885a2e.png)
## Figure -02 3 to 8 Encoder implenentation 

 ### Decoders 
A decoder does the opposite job of an encoder. It is a combinational circuit that converts n lines of input into 2n lines of output.

Let’s take an example of 3-to-8 line decoder.
Implementation –
D0 is high when X = 0, Y = 0 and Z = 0. Hence,

D0 = X’ Y’ Z’ 
Similarly,

D1 = X’ Y’ Z
D2 = X’ Y Z’
D3 = X’ Y Z
D4 = X Y’ Z’
D5 = X Y’ Z
D6 = X Y Z’
D7 = X Y Z 


![image](https://user-images.githubusercontent.com/36288975/171543978-ee2d0671-2846-40a1-8705-507fd6287a49.png)
## Figure -03 8 to 3 Decoder 



![image](https://user-images.githubusercontent.com/36288975/171543866-5a6eace6-8683-49d7-9c4f-a7cb30ec3035.png)
## Figure -04 8 to 3 Decoder implementation 

## Procedure
Step-1: create module encoder and decoder.

Step-2: Get inputs and outputs for encoders and decoders.

Step-3: perform or operation for encoder and and logic for decoders.

Step-4: perform RTL LOGIC and get waveform.

Step-5: End the module.

## PROGRAM 
```
Program for Endocers and Decoders  and verify its truth table in quartus using Verilog programming.
Developed by: Haridharshini S
RegisterNumber: 212221230033
```
## ENCODER:
```
module EX7(a,b,c,d0,d1,d2,d3,d4,d5,d6,d7);
output a,b,c;
input d0,d1,d2,d3,d4,d5,d6,d7;
or(a,d4,d5,d6,d7);
or(b,d2,d3,d6,d7);
or(c,d1,d3,d5,d7);
endmodule
```
## DECODER:
```
module EX7(d0,d1,d2,d3,d4,d5,d6,d7,a,b,c);
input a,b,c;
output d0,d1,d2,d3,d4,d5,d6,d7;
assign d0 = (~a&~b&~c);
assign d1 = (~a&~b&c);
assign d2 = (~a&b&~c);
assign d3 = (~a&b&c);
assign d4 = (a&~b&~c);
assign d5 = (a&~b&c);
assign d6 = (a&b&~c);
assign d7 = (a&b&c);
endmodule
```
## RTL LOGIC  
### ENCODER:
![201480828-81080553-588b-44dc-a652-0bb566f81ab2](https://user-images.githubusercontent.com/94168395/202907393-02337293-ac5a-4d32-829b-18de7b8198f7.png)

### DECODER:
![201480837-7db0b6cc-e7d8-4d2d-8509-ba247ed2f000](https://user-images.githubusercontent.com/94168395/202907421-a6645c33-e565-4da3-a5c6-122e65f914ed.png)

## TIMING DIGRAMS  
### ENCODER:
![201480843-3b04c3ea-9df1-4746-852d-b7b0337119f2](https://user-images.githubusercontent.com/94168395/202907492-87088cac-0b92-4461-b99f-5a832384a8d7.png)

### DECODER:
![201480849-07fb9b44-fc4c-4f76-8087-68b4524fd1b1](https://user-images.githubusercontent.com/94168395/202907499-60d0c335-f457-43ab-8590-a81c7b654421.png)

## TRUTH TABLE 
### ENCODER:
![201480858-4167f5a5-3759-4e85-84e7-abbe0509f5c9](https://user-images.githubusercontent.com/94168395/202907502-95eb6395-b6b8-4496-ada8-7d5b4e346f27.png)

### DECODER:
![201480864-f1d7a808-448f-4a96-8082-7283a70228a2](https://user-images.githubusercontent.com/94168395/202907514-baae7eb9-3245-4292-9ef2-2ae2e2756b70.png)

## RESULTS 

Thus the program to desing encoder and decoder is completed.
