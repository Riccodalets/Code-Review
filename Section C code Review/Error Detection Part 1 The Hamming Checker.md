Error Detection Part 1: The Hamming Checker
---
Test cases:
---
cases 1: hamming_checker("0100100100010010")

cases 2: hamming_checker("0011011010100110")

cases 3: hamming_checker("0010101011111111") 

Expected Results:
---

cases 1: "0100100000010010"

cases 2: "0010011010100110"

cases 3: "0010101011111111"


CODE
---
```
import numpy as np
from functools import reduce

def hamming_checker(block):
    # data block
	blockbit= np.array(list(block), dtype=int) 
	#Pair each data block bits with a corresponding index from 0 up to 15 and then pull position 
	#where the corresponding bit is turned and XOR them together to get error postion
	error_position=reduce(lambda x,y:x^y,[i for i,bit in enumerate(blockbit) if bit])
	
	#if position is 0 return or ginal message
	if(error_position==0):
		return block
	else:
	    #fix code using error position
		blockbit[error_position]= not blockbit[error_position]
		#convert from array to string
		block = ''.join(str(x) for x in blockbit)
		#Rturn Corrected message bits
		return block 
```
```
Return the Remainder from Two Numbers

function remainder(x, y) {
	return x%y
}
```