# Before You Start Task 1: How to Think About the Problem

This task may look big at first, but it is only built from basic Python concepts.

You do not need advanced Python to solve it.

You only need to understand:

- Variables
- Input and output
- Conditions
- Loops
- Lists
- Dictionaries
- Functions

---

## 1. Understand the Main Idea

The program is about storing data for many students.

Each student has:

- Name
- ID
- Marks for 5 subjects
- Average
- Status
- Grade

So the main problem is:

> How can we store student data, calculate useful results, and print a report?

---

## 2. Think About One Student First

Before thinking about many students, start with one student only.

Example:

```python
name = "Ahmad"
student_id = "2024001"

marks = {
    "Math": 90,
    "Programming": 85,
    "English": 80,
    "Physics": 70,
    "Problem Solving": 95
}
```

Now ask yourself:

- How do I calculate the average?
- How do I know if the student passed?
- How do I give the student a grade?

---

## 3. Why Do We Use a Dictionary?

A dictionary helps us store related information together.

Example:

```python
student = {
    "name": "Ahmad",
    "id": "2024001",
    "marks": {
        "Math": 90,
        "Programming": 85,
        "English": 80,
        "Physics": 70,
        "Problem Solving": 95
    }
}
```

This is useful because now all information about Ahmad is inside one variable.

To access the name:

```python
student["name"]
```

To access the Programming mark:

```python
student["marks"]["Programming"]
```

---

## 4. Why Do We Use a List?

We use a list because we have many students.

Example:

```python
students = []
```

Each time we create a student dictionary, we add it to the list:

```python
students.append(student)
```

So the final structure looks like this:

```python
students = [
    {
        "name": "Ahmad",
        "id": "2024001",
        "marks": {
            "Math": 90,
            "Programming": 85,
            "English": 80,
            "Physics": 70,
            "Problem Solving": 95
        }
    },
    {
        "name": "Omar",
        "id": "2024002",
        "marks": {
            "Math": 50,
            "Programming": 60,
            "English": 45,
            "Physics": 55,
            "Problem Solving": 70
        }
    }
]
```

---

## 5. How to Calculate the Average

If marks are stored in a dictionary, you can get all marks using:

```python
marks.values()
```

Example:

```python
marks = {
    "Math": 90,
    "Programming": 85,
    "English": 80,
    "Physics": 70,
    "Problem Solving": 95
}

average = sum(marks.values()) / len(marks)
```

The idea is simple:

```text
Average = total marks / number of subjects
```

---

## 6. How to Determine Pass or Fail

A student passes if the average is 50 or more.

```python
if average >= 50:
    status = "Pass"
else:
    status = "Fail"
```

---

## 7. How to Determine the Grade

Use conditions from highest to lowest.

```python
if average >= 90:
    grade = "A"
elif average >= 80:
    grade = "B"
elif average >= 70:
    grade = "C"
elif average >= 60:
    grade = "D"
elif average >= 50:
    grade = "E"
else:
    grade = "F"
```

Important note:

You do not need to write:

```python
average >= 80 and average < 90
```

Because if the average was 90 or more, Python already entered the first condition.

---

## 8. Why Do We Use Functions?

Functions help us split the big task into small tasks.

Instead of writing everything in one place, we write small functions.

Example:

```python
def calculate_average(marks):
    return sum(marks.values()) / len(marks)
```

Now whenever we need the average, we just call:

```python
average = calculate_average(marks)
```

This makes the code cleaner and easier to debug.

---

## 9. Input Validation

The user may enter a wrong mark like:

```text
-10
150
abc
```

Your program should not crash.

You need to keep asking until the mark is valid.

The idea:

```python
while True:
    mark = input("Enter mark: ")

    if mark is valid:
        return mark
    else:
        print("Invalid mark, try again.")
```

Important:

`input()` always gives you a string.

So you must convert the input to a number:

```python
mark = float(mark)
```

But if the user enters text like `"abc"`, this will cause an error.

So you may need to use:

```python
try:
    mark = float(input("Enter mark: "))
except ValueError:
    print("Please enter a number.")
```

---

## 10. How to Find the Top Student

The top student is the student with the highest average.

Think like this:

1. Assume the first student is the top student.
2. Loop through all students.
3. If you find a student with a higher average, update the top student.

Example idea:

```python
top_student = students[0]

for student in students:
    if student["average"] > top_student["average"]:
        top_student = student
```

---

## 11. How to Print Failed Students

Loop through the students list.

For each student, check the status.

```python
for student in students:
    if student["status"] == "Fail":
        print(student["name"])
```

You also need to handle this case:

```text
No failed students.
```

So you can use a flag:

```python
found_failed = False
```

If you find one failed student, change it to:

```python
found_failed = True
```

At the end, if it is still False, print:

```python
No failed students.
```

---

## 12. How to Calculate Subject Statistics

You need statistics for each subject:

- Highest mark
- Lowest mark
- Average mark

Example for Math:

```python
math_marks = []

for student in students:
    math_marks.append(student["marks"]["Math"])
```

Then:

```python
highest = max(math_marks)
lowest = min(math_marks)
average = sum(math_marks) / len(math_marks)
```

You can repeat this idea for each subject.

Better idea:

Store subjects in a list:

```python
subjects = ["Math", "Programming", "English", "Physics", "Problem Solving"]
```

Then loop over subjects:

```python
for subject in subjects:
    subject_marks = []

    for student in students:
        subject_marks.append(student["marks"][subject])
```

---

## 13. How to Search by Student ID

The user enters an ID.

You loop through all students.

If the ID matches, print the student.

```python
for student in students:
    if student["id"] == search_id:
        print("Student found")
```

If no student matches, print:

```text
Student not found.
```

Again, you can use a flag or return the student from a function.

---

## 14. Recommended Solving Order

Do not solve the whole task at once.

Follow this order:

### Step 1

Create the subjects list.

```python
subjects = ["Math", "Programming", "English", "Physics", "Problem Solving"]
```

### Step 2

Write a function to get a valid mark.

### Step 3

Write a function to calculate the average.

### Step 4

Write a function to return Pass or Fail.

### Step 5

Write a function to return the grade.

### Step 6

Enter one student and test your code.

### Step 7

Use a loop to enter many students.

### Step 8

Print the full report.

### Step 9

Find the top student.

### Step 10

Print failed students.

### Step 11

Print subject statistics.

### Step 12

Add search by ID.

### Step 13

Try the bonus menu only after finishing the main task.

---

## 15. Common Mistakes

### Mistake 1: Storing marks separately

Bad idea:

```python
math1 = 90
programming1 = 80
math2 = 70
programming2 = 60
```

This becomes messy.

Better idea:

```python
student["marks"]["Math"]
```

---

### Mistake 2: Writing all code without functions

Bad idea:

```python
# 200 lines of code in one place
```

Better idea:

```python
def calculate_average(marks):
    ...
```

---

### Mistake 3: Not validating input

Your program should not accept marks less than 0 or greater than 100.

---

### Mistake 4: Confusing list and dictionary

A list uses index numbers:

```python
students[0]
```

A dictionary uses keys:

```python
student["name"]
```

---

## 16. Final Advice

When you feel stuck, do not ask:

> How do I solve the whole task?

Ask smaller questions:

- How do I store one student?
- How do I calculate one average?
- How do I loop over all students?
- How do I search for one ID?

Big programs are only small problems connected together.

---

## Important Rule

Do not start with the menu system before finishing the normal version of the program.
