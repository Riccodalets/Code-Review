HyperionDev Code Reviewer Take-Home Test(Option 1: Python Task)
---

correction
---
there are some few error to lookup to

Indentation is a very important concept of Python, all the statements with the same space to the right, 
belong to the same code block.
the first error is in line 4, we have IndentationError. Increase space to the right on line 4 using a Tab key.

The second error, is in line 11, we have Misspelling errors. You wrote reversd **instead**

The third error, is in line 13, we have semantic error. While trying to checking if number has reached 0, there we should write num != 0.

and lasty you forgot to close the function **def is_palindrome(x)**. 
Test cases:
---
cases 1: 121

cases 2: 2356

cases 3: 0

cases 4: -121

weakness cases 5: -0

Expected answers:
---

cases 1: true

cases 2: false

cases 3: true

cases 4: false

weaakness cases 5: true

all cases pass exept case 5,    


Efficiency
---

Time Complexity: Let there be N-number and each word has a maximum of M characters. The upper bound is O(NM).

Space Complexity: Let there be N-words and each word has maximum M characters, therefore max. storage space 
for each word with at max. M characters will be O(M), therefore for max N-words, it will be O(N*M). Therefore,
the upper bound is O(NM).



style
---
 
Indentation styles assist in identifying control flow and blocks of code, let's make sure we perfect it 
  (use tabs to create white space).
 
Your Variable naming is very good and meaningful, keep it up.

Documentation
---
you have done a good work code is commented but please consider short and brief comments like i did in the blow code snippet.
 
 Corrected Code
 ---
```
def is_palindrome(x)
    if x < 0  #for all negetive integers return false
        false

    else 
        reversed = 0
        #store a copy of this number
        num = x  
        #calculate reverse of this number
        while num != 0
            #extract last digit of this number
            extracted = num%10
             #append this digit in reveresed number
            reversed = reversed*10 + extracted 
            #floor divide the number leave out the last digit from number
            num=num/10
        end
        #compare reverse to original number return false if not equal else true
        if reversed != x
            false
        else
            true
        end
    end
end
```
