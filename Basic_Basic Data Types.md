# Lists
Consider a list (list = []). You can perform the following commands:
  1. insert i e: Insert integer e at position i.
  2. print: Print the list.
  3. remove e: Delete the first occurrence of integer e.
  4. append e: Insert integer e at the end of the list.
  5. sort: Sort the list.
  6. pop: Pop the last element from the list.
  7. reverse: Reverse the list.
Initialize your list and read in the value of n followed by n lines of commands where each command will be of the 7 types listed above. 
Iterate through each command in order and perform the corresponding operation on your list.

```python 3
a = []                                  # creates an empty list named "a"
n = int(input())                        # reads an integer "int()" inputs "input()" and stores it as n

for _ in range (n):                     # for all items the range n
    command = input().split()           # takes the input and splits its elements "input().split()" and names it "command"

    if command[0] == "insert":          # if the first element "[0]" in command is like "==" the string "insert":
        i = int(command[1])               # then convert the second element into an integer "int(command[1])" and store it as "i"
        e = int(command[2])               # then convert the third element into an integer "int(command[2])" and store it as "e"
        a.insert(i, e)                    # and insert "e" at position "i" in list "a"
    elif command[0] == "print":         # then if the first element of command is like "print" then:
        print(a)                          # print list "a"
    elif command[0] == "remove":        # then if the first element of command is like "remove":
        e = int(command[1])               # then convert the second element into an integer "int(command[1])" and store it as "e"
        a.remove(e)                       # and remove the first occurence of "e" from list "a"
    elif command[0] == "append":        # then if the first element of command is like "append" then:
        e = int(command[1])               # then convert the second element into an integer "int(command[1])" and store it as "e"
        a.append(e)                       # and add "e" to the end of the list "a"
    elif command[0] == "sort":          # then if the first element of command is like "sort" then:
        a.sort()                          # sort list "a"
    elif command[0] == "pop":           # then if the first element of command is like "pop" then:
        a.pop()                           # remove the last element from the list "a"
    elif command[0] == "reverse":       # then if the first position of command is like "reverse" then:
        a.reverse()                       # reverse list "a" in-place
```

---
# List Comprehensions
Let's learn about list comprehensions! You are given three integers x, y and z representing the dimensions of a cuboid along with an integer n. 
Print a list of all possible coordinates given by (i, j, k) on a 3D grid where the sum of i + j + k is not equal to n. 
Here, 0 <= i <= x; 0 <= j <= y; 0 <= k <= z. Please use list comprehensions rather than multiple loops, as a learning exercise.

```python 3
x = int(input())                        # reads an integer "int()" input "input()" (a number in this case) and stores it as x
y = int(input())                        # reads an integer "int()" input "input()" (a number in this case) and stores it as y
z = int(input())                        # reads an integer "int()" input "input()" (a number in this case) and stores it as z
n = int(input())                        # reads an integer "int()" input "input()" (a number in this case) and stores it as n
          
coordinates = [                         # define a list named "coordinates" as:
  [i, j, k]                             # consisting of i, j, and k
  for i in range(x + 1)                 # where i is a range of integers defined as 0 to x (x + 1 is needed to include x)
  for j in range(y + 1)                 # where j is a range of integers defined as 0 to y (y + 1 is needed to include y)
  for k in range(z + 1)                 # where k is a range of integers defined as 0 to z (z + 1 is needed to include z)
  if i + j + k != n                     # so long as i + j + k does not equal (!=) n
]
    
print(coordinates)                      # prints coordinates
```

---
# Find the Runner-Up Score!
Given the participants' score sheet for your University Sports Day, you are required to find the runner-up score. 
You are given n scores. Store them in a list and find the score of the runner-up.

```python 3
n = int(input())                        # reads an integer "int()" input "input()" (the participant's scores in this case) and stores it as n
arr = map(int, input().split())         # splits the input into a list of strings "input().split()", converts each element of the input into an integer "map(int, " and stores them in a map object (iterator) "arr ="
    
scores = list(set(arr))                 # demoves duplicates "set()", turns the map object into a list "list()", and defines that list as "scores"
scores.sort(reverse = True)             # sorts scores ".sort()" in descending order "reverse = True"
print(scores[1])                        # prints the second position (i.e. index) "[1]" in scores.
```

---
# Nested Lists
Given the names and grades for each student in a class of N students, store them in a nested list and print the name(s) of any student(s) having the second lowest grade.
Note: If there are multiple students with the second lowest grade, order their names alphabetically and print each name on a new line.

```python 3
students = []                           # creates an empty list "[]" named "students"
n = int(input())                        # reads an integer "int()" input "input()" (a bunch of name, grade pairs) and stores it as n

for _ in range(n):                      # for the range n (all of the names and grades):
  name = input().strip()                # take the input before/after a space (.strip) and create a variable of that input called "name"
  grade = float(input())                # take the float input (float(input()) and create a variable of that input called "grade"
  students.append([name, grade])        # to the students list add (.append) two lists: "name" and "grade"

unique_grades = sorted(set(grade for name, grade in students))    # removes the duplicate "set()" grades "grade" for each of the pairs in the lsit "for name, grade in students", creates a new sorted list and names it "unique_grades = sorted()"
second_lowest_grade = unique_grades[1]                            # defines a new variable "second_lowest_grade" as the second position "[1]" in the list "unique_grades"

second_lowest_students = [name for name, grade in students        # defines a new list "second_lowest_students = " as the name "name for name, grade" in the list "in students",
if grade == second_lowest_grade]                                  # if their grade is equal to the variable second_lowest_grade. 

for student in sorted(second_lowest_students):                    # goes through the alphabetically ordered list "sorted(second_lowest_students)" and:
  print(student)                                                  # prints the list student
```

---
# Find the Percentage
The provided code stub will read in a dictionary containing key/value pairs of name:[marks] for a list of students. 
Print the average of the marks array for the student name provided, showing 2 places after the decimal.

```python 3
n = int(input())                        # reads an integer "int()" input "input()" (a bunch of name, grade pairs) and stores it as n
student_marks = {}                      # creates an empty dictionary "{}" called "student_marks"

for _ in range(n):                      # for the range n (all of the names and grades): 
  name, *line = input().split()         # splits the input elements "input().split()" and create two lists of that input called "name" and "line"
  scores = list(map(float, line))       # changes the items in the line list to floats "map(float, line)" and creates a list of that called scores "scores = list()"
  student_marks[name] = scores          # adds the student's name and corresponding scores to the "student_marks" dictionary

query_name = input()                    # reads an input "input()" (the name of the student we are querying in this case) and stores it as query_name

marks = student_marks[query_name]       # creates a list named marks for the queried student
average = sum(marks) / len(marks)       # averages the total marks of the student

print(f"{average:.2f}")                 # formats the average into a string with (f"{average:), as a floating-point number with 2 decimal places (.2f}"), and prints.
```

---
# Tuples
Given an integer, n, and n space-separated integers as input, create a tuple, t, of those n integers. Then compute and print the result of hash(t).
Note: hash() is one of the functions in the __builtins__ module, so it need not be imported.
Note: this needs to be run on Python 2, not Python 3, as the hash function changes in Python 3. 

```python 3
n = int(raw_input())                            # reads an integer "int()" from the input "raw_input()" and stores it as "n".
integer_list = map(int, raw_input().split())    # splits the elements of the input string by spaces "raw_input().split()", converts the elements to integers "map(int, ... )", and stores it as "integer_list"
t = tuple(integer_list)                         # converts the "integer_list" to a tuple and stores it as "t"

print(hash(t))                                  # prints the hash of the tuple "t"
```