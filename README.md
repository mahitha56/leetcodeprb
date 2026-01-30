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
