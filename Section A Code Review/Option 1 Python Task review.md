HyperionDev Code Reviewer Take-Home Test(Option 1: Python Task)
---

correction
---
Your code is great however
Indentation is a very important concept of Python, all the statements with the same space to the right, 
 belong to the same code block. 
 Line 2, the indentation is incorrect which leads to IndentationError
 decrease space to the right on line 2 so that line 2 is a Tab away from line 1.
    
line 5, sorted() function must take in at least one parameter.
    i should be the parameter to have sorted(i).

Test cases:
---
cases 1: [""]

cases 2: ["eat", "tea", "tan", "ate", "nat", "bat"]

cases 3: ["", "eat", "tea", "tan", "ate", "nat", "bat", ""]

cases 4: ["ems","mes"]

cases 5: ["tem","Met","EMT"]

Expected answers:

cases 1: [[""]]

cases 2: [["tan","nat"],["eat","tea","ate"],["bat"]]

cases 3: [["",""],["tan","nat"],["eat","tea","ate"],["bat"]]

cases 4: [["ems","mes"]]

cases 5: [['tem', 'met', 'emt']]

all cases pass exept case 5, Strings does not consists of lowercase English letters.
To correct this, we should add i = i.lower() below line 4.   


Efficiency
---

Time Complexity: Let there be N-words and each word has a maximum of M characters. The upper bound is O(NM).

Space Complexity: Let there be N-words and each word has maximum M characters, therefore max. storage space 
for each word with at max. M characters will be O(M), therefore for max N-words, it will be O(N*M). Therefore,
the upper bound is O(NM).

There a data structure called defaultdict that helps you avoid checking for the key in the dictionary.
 And can reduce time complaxity and with less effort.

style
---
You used a good practice, white space style which enhance code readability.
 
Indentation styles assist in identifying control flow and blocks of code, let's make sure we perfect it 
  (use tabs to create white space).
  
Variable naming is an important aspect in making your code readable. Naming variables follow a simple 
  idea: Create variables that describe their function and which follow a consistent theme throughout your code. 

Documentation
---
Your code is readable however to increase readability, comments are the primary (if not only)
form of project documentation and they make code reusable and easy to deburg. 
For this reason, it's very important do it and get it right.
 
 Corrected Code
 ---
```class Solution:
   def groupAnagrams(self, strs):
      result = {}
      for i in strs:
         x = "".join(sorted(i))
         if x in result:
            result[x].append(i)
         else:
            result[x] = [i]
      return list(result.values())
ob1 = Solution()
print(ob1.groupAnagrams(["eat", "tea", "tan", "ate", "nat", "bat"]))
```
