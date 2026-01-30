# leetcodeprb
Zip in python:-
Let’s understand zip() very simply, because it’s super useful for strings, lists, and problems like isomorphic.

✅ What is zip() ?

👉 zip() combines two (or more) sequences position-by-position

It makes pairs.

🔥 Basic Example
a = [1, 2, 3]
b = [4, 5, 6]

print(list(zip(a, b)))

Output:
[(1,4), (2,5), (3,6)]


👉 index-wise pairing

✅ With strings (your case)
s = "egg"
t = "add"

print(list(zip(s, t)))

Output:
[('e','a'), ('g','d'), ('g','d')]


So it pairs:

e ↔ a
g ↔ d
g ↔ d


Exactly what we need for isomorphic!


Problem:
     class Solution:
    def isIsomorphic(self, s: str, t: str) -> bool:
        maps={}
        mapt={}
        for i,j in zip(s,t):
            if i in maps and maps[i]!=j:
                return False
            if j in mapt and mapt[j]!=i:
                return False
            maps[i]=j
            mapt[j]=i
        return True
#problem2
Let’s clearly understand find() in Python — very simple and very useful for strings.

✅ What is find() ?

👉 find() is used to find first occurrence of substring

Syntax:
string.find(substring)

✅ What it returns?
Case	Output
found	index
not found	-1
🔥 Basic example
s = "sadbutsad"

print(s.find("sad"))


Output:

0


Because "sad" starts at index 0

✅ Not found case
print(s.find("xyz"))


Output:

-1


So no need to manually return -1 👍

✅ Multiple occurrences
s = "sadbutsad"
print(s.find("sad"))


Output:

0


Even though "sad" appears twice,
👉 returns first occurrence only

✅ Start searching from index
s = "sadbutsad"

print(s.find("sad", 1))


Output:

6


Starts search from index 1.

✅ Difference between find() and index()
Method	Not found
find()	-1
index()	Error ❌
