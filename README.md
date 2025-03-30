# Huffman-Shannon_fano
Consider a discrete memoryless source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} for its output. 
Apply the Huffman and Shannon-Fano to this source. 
Show that draw the tree diagram, the average code word length, Entropy, Variance, Redundancy, Efficiency.
# Aim
To compute the Average Codeword Length, Entropy, Efficiency, Redundancy, and Variance for a discrete memoryless source 
using Huffman and Shannon-Fano coding based on the given probabilities and codeword lengths.

## Tools required
Python: A versatile programming language used for scientific computing and signal processing.
NumPy: A powerful numerical library in Python for performing array-based operations and mathematical computations.
Matplotlib: A plotting library for generating high-quality graphs and visualizations of data, essentialfor demonstrating the sampling process.
      
## Program
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

## Output   

![Screenshot 2025-03-30 100704](https://github.com/user-attachments/assets/0755dc15-329b-401d-a659-a40d4984f403)


# calculations:

![WhatsApp Image 2025-03-30 at 13 10 38_2ccfdf47](https://github.com/user-attachments/assets/6c212589-c9d1-4cbb-babe-baa91e18e9e5)
![WhatsApp Image 2025-03-30 at 13 10 38_b4cd39c7](https://github.com/user-attachments/assets/976c8527-54a5-4a41-a31c-c82df587fe7f)
![WhatsApp Image 2025-03-30 at 13 10 39_05b00b96](https://github.com/user-attachments/assets/ce6c9069-8bbf-4c4c-a95f-4bca4641a67b)
![WhatsApp Image 2025-03-30 at 13 10 39_8dbec3a7](https://github.com/user-attachments/assets/a1ec96c2-7aec-4087-99e0-2bf22f4de6c2)
![WhatsApp Image 2025-03-30 at 13 10 39_af8a287a](https://github.com/user-attachments/assets/9bab40ca-be99-40b0-8070-74eeb0c47c4c)
![WhatsApp Image 2025-03-30 at 13 10 39_c2aa3361](https://github.com/user-attachments/assets/f2ebb0f2-419f-4f86-8225-1afea748b9e5)




## Result 
For the given probabilities 
0.125,0.0625,0.25,0.0625,0.125,0.125,0.25

Average Codeword Length is : 2.625
Entropy is : 2.625
Efficiency is : 100.0 %
Redudancy is : 0.0
Variance is : 0.484

