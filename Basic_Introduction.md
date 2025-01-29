# If-Else
Given an integer, n, perform the following conditional actions:
If n is odd, print Weird
If n is even and in the inclusive range of 2 to 5, print Not Weird
If n is even and in the inclusive range of 6 to 20, print Weird
If n is even and greater than 20, print Not Weird

```python 3
n = int(input())                        # reads an integer "int()" input "input()" and stores it as n
if n % 2 != 0:                          # when n is divided by 2, if the remainder (%) is not (!=) 0 (i.e. n is odd), then:
    print("Weird")                      # print "Weird"
if n % 2 == 0 and n >= 2 and n <= 5:    # when n is divided by 2, if the remainder (%) is (==) 0 (i.e. n is even), and n is between 2 and 5 then:
    print("Not Weird")                  # print "Not Weird"
if n % 2 == 0 and n >= 6 and n <= 20:   # when n is divided by 2, if the remainder is 0, and n is between 6 and 20 then:
    print("Weird")                      # print "Weird"
if n % 2 == 0 and n > 20:               # when n is divided by 2, if the remainder is 0, and n above 20 then:
    print("Not Weird")                  # print "Not Weird"
```

---
# Arithmetic Operators
The provided code stub reads two integers from STDIN, a and b. Add code to print three lines where:
  The first line contains the sum of the two numbers.
  The second line contains the difference of the two numbers (first - second).
  The third line contains the product of the two numbers.

```python 3
a = int(input())                        # reads an integer "int()" input "input()" and stores it as a
b = int(input())                        # reads an integer "int()" input "input()" and stores it as b

print(a + b)                            # print the sum of "a" and "b"
print(a - b)                            # print the difference of "a" and "b"
print(a * b)                            # print the product of "a" and "b"
```

---
# Division
The provided code stub reads two integers, a and b, from STDIN. 
Add logic to print two lines. The first line should contain the result of integer division,  // . The second line should contain the result of float division,  / .
No rounding or formatting is necessary.

```python 3
a = int(input())                        # reads an integer "int()" input "input()" and stores it as a
b = int(input())                        # reads an integer "int()" input "input()" and stores it as b

print(a // b)                           # print the result of integer division (//)
print(a / b)                            # print the result of float division (/)
```

---
# Loops
The provided code stub reads an integer, n, from STDIN. For all non-negative integers i < n, print i^2.

```python 3
n = int(input())                        # reads an integer "int()" input "input()" and stores it as n

for i in range(n):                      # for each integer "i" in the range "0-n":
    print(i**2)                         # print i^2 (i squared, or i**2)
```

---
# Write a Function
An extra day is added to the calendar almost every four years as February 29, and the day is called a leap day. It corrects the calendar for the fact that our planet takes approximately 365.25 days to orbit the sun. A leap year contains a leap day.
In the Gregorian calendar, three conditions are used to identify leap years:
  The year can be evenly divided by 4, is a leap year, unless:
  The year can be evenly divided by 100, it is NOT a leap year, unless:
  The year is also evenly divisible by 400. Then it is a leap year.
This means that in the Gregorian calendar, the years 2000 and 2400 are leap years, while 1800, 1900, 2100, 2200, 2300 and 2500 are NOT leap years.
Given a year, determine whether it is a leap year. If it is a leap year, return the Boolean True, otherwise return False.
Note that the code stub provided reads from STDIN and passes arguments to the is_leap function. It is only necessary to complete the is_leap function.

```python 3
def is_leap(year):                      # defines the function "is_leap" with the input "(year)" as the following:
    if year % 400 == 0:                 # if year can be divided by 400 without a remainder (%)
        leap = True                     # then the year is a leap and the function "is_leap(year)" should return True
    elif year % 100 == 0:               # if the year can be divided by 400 evenly (elif), but it can also be divided by 100 evenly:
        leap = False                    # then the year is not a leap and the function should return False
    elif year % 4 == 0:                 # if the year can be divided by 400 evenly and 100 evenly (elif), but it can also be divided by 4 evenly:
        leap = True                     # then the year is a leap and the function should return True.
    else:                               # all other conditions are not leap years therefore
        leap = False                    # the function returns False.
    return leap                         # leap has been defined as True or False in all our If/Elif/Else statements, so this returns the proper Boolean

year = int(input())                      # reads an integer "int()" input "input()" (a year in this case) and stores it as year
print(is_leap(year))                     # prints a Boolean (True or False) for the year provided: True if year is a leap, False if year is not a leap.
```

---
# Print a Function
The included code stub will read an integer, n, from STDIN. Without using any string methods, try to print the following: 123...n
Note that "..." represents the consecutive values in between.

```python 3
n = int(input())                        # reads an integer "int()" input "input()" (a number in this case) and stores it as n
    
for i in range (1, n+1):                # for each integer (i) in the range (1, n+1) (the +1 is necessary to include n):
    print(i, end="")                    # print i (which has already been defined as the range from 1 to n. end="" ensures that it prints with no spaces and no new lines. 
```