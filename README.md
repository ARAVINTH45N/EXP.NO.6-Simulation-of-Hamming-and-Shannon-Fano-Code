#HUFFMAN AND SHANNON_FANO
Consider a discrete memoryless source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} for its output. Apply the Huffman and Shannon-Fano to this source.

## AIM:
To compute the Average Codeword Length, Entropy, Efficiency, Redundancy, and Variance for a discrete memoryless source using Huffman and Shannon-Fano coding based on the given probabilities and codeword lengths.

## TOOLS REQUIRED :
Python: A versatile language for scientific computing and signal processing. NumPy & Matplotlib: Libraries for numerical operations and high-quality visualizations, essential for demonstrating sampling.

## PROGRAM:
```
import numpy as np
import math 
L  = 0
hs = 0
p = []
lk = []
n = int(input("Enter the number of Samples : "))
for i in range (n): 
    pr = float(input(f"Enter the probability of sample values {i + 1}: "))  
    p.append(pr)
for j in range (n): 
    l = float(input(f"Enter the length of the sample values {j + 1}: "))  
    lk.append(l)

for k in range (n):
    Avg1 = p[k] * lk[k]
    L = L + Avg1

for k in range (n):
    e = p[k] * math.log(1 / p[k], 2)
    hs = hs + e
hs = round(hs,3)

eff = hs / L
eff = round(eff,3)

red =  round(1 - eff,3) 

var = 0
for k in range(n):
    var1 = p[k] * (lk[k]-L)**2
    var = var + var1
var = round(var,3)
print()
print(f"Average Codeword Length is : {L}")
print(f"Entropy is : {hs}")
print(f"Efficiency is : {eff*100} %")
print(f"Redudancy is : {red}")
print(f"Variance is : {var}")
```
## OUTPUT:
![image](https://github.com/user-attachments/assets/e4b8560d-c478-4783-b792-edcd6f8f842d)



## CALCULATIONS:
![image](https://github.com/user-attachments/assets/a8151be9-0fc4-42d3-9abc-a8ccefc78a94)
![image](https://github.com/user-attachments/assets/ec250ab3-982b-42bd-a0ca-7001bbfc17a4)
![image](https://github.com/user-attachments/assets/fa35e572-f5e6-4443-9c96-cda0d7b60e20)



## RESULT:
For the given probabilities 0.125,0.0625,0.25,0.0625,0.125,0.125,0.25. Average Codeword Length is : 2.625 Entropy is : 2.625 Efficiency is : 100.0 % Redudancy is : 0.0 Variance is : 0.484.
