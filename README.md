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
#
class Solution:
    def strStr(self, haystack: str, needle: str) -> int:
        haystack1=haystack.lower()
        neddle1=needle.lower()
        pos=haystack1.find(neddle1)
        return pos
#
1️⃣ What is s[:]?

s[:] is a slice that selects the entire list or string s.

For example:

s = [1, 2, 3, 4]
print(s[:])  # Output: [1, 2, 3, 4]


It creates a shallow copy of the entire list. But more importantly, when you use it on the left-hand side of an assignment, it modifies the original list in-place rather than creating a new list.

2️⃣ What does s[::-1] do?

s[::-1] is a slice that reverses the list or string.

Example:

s = [1, 2, 3, 4]
print(s[::-1])  # Output: [4, 3, 2, 1]

3️⃣ Why use s[:] = s[::-1] instead of s = s[::-1]?

s = s[::-1] creates a new list and makes s point to it.

s[:] = s[::-1] modifies the original list in place. This is important if other references point to the same list.

Example:

s = [1, 2, 3]
t = s  # t references the same list as s
s[:] = s[::-1]  # reverse in-place
print(s)  # [3, 2, 1]
print(t)  # [3, 2, 1] -> t sees the change too


If we had done s = s[::-1]:

s = [1, 2, 3]
t = s
s = s[::-1]  # s now points to a new list
print(s)  # [3, 2, 1]
print(t)  # [1, 2, 3] -> t remains unchanged


✅ So s[:] = s[::-1] is used when you want to reverse a list in-place, preserving references to the original list.

If you want, I can make a tiny visual diagram to show the difference between s = s[::-1] and s[:] = s[::-1] — it makes this concept super clear.

