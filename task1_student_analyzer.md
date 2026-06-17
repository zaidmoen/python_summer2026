# Task 1: Student Performance Analyzer

## Goal

Build a Python console program that manages students' marks and analyzes their performance.

You are **NOT** allowed to use:

- pandas
- numpy
- classes / OOP
- external libraries
- AI-generated full solutions

You should use only Python basics:

- variables
- input / print
- if statements
- loops
- lists
- dictionaries
- functions
- string formatting

---

## Program Requirements

Your program should allow the user to enter data for multiple students.

For each student, ask for:

1. Student name
2. Student ID
3. Marks for 5 subjects:
   - Math
   - Programming
   - English
   - Physics
   - Problem Solving

Each mark must be between **0 and 100**.

If the user enters an invalid mark, ask again until the input is valid.

---

## Required Features

### 1. Add Students

The program should ask how many students the user wants to enter.

Example:

```text
How many students do you want to enter? 3
```

Then enter the data for each student.

---

### 2. Calculate Average

For each student, calculate the average mark.

Example:

```text
Average: 82.4
```

---

### 3. Determine Status

A student passes if the average is greater than or equal to 50.

Status should be:

```text
Pass
```

or

```text
Fail
```

---

### 4. Determine Grade

Use the following grading system:

| Average Range | Grade |
|--------------|-------|
| 90 - 100     | A     |
| 80 - 89      | B     |
| 70 - 79      | C     |
| 60 - 69      | D     |
| 50 - 59      | E     |
| Below 50     | F     |

---

### 5. Find Top Student

After entering all students, print the student with the highest average.

Example:

```text
Top Student:
Name: Ahmad
ID: 2024001
Average: 91.2
Grade: A
```

---

### 6. Find Weak Students

Print all students who failed.

If no one failed, print:

```text
No failed students.
```

---

### 7. Subject Statistics

For each subject, calculate and print:

- Highest mark
- Lowest mark
- Average mark

Example:

```text
Math:
Highest: 98
Lowest: 44
Average: 76.5
```

---

### 8. Search by Student ID

After printing the report, ask the user to enter a student ID to search for.

If the ID exists, print all information about that student.

If not, print:

```text
Student not found.
```

---

## Required Functions

Your solution must contain at least these functions:

```python
get_valid_mark(subject_name)
calculate_average(marks)
get_status(average)
get_grade(average)
print_student_report(student)
find_top_student(students)
print_failed_students(students)
print_subject_statistics(students)
search_student_by_id(students, student_id)
```

You may add more functions if needed.

---

## Data Structure Hint

Each student can be stored as a dictionary:

```python
student = {
    "name": "Ahmad",
    "id": "2024001",
    "marks": {
        "Math": 90,
        "Programming": 85,
        "English": 78,
        "Physics": 88,
        "Problem Solving": 92
    },
    "average": 86.6,
    "status": "Pass",
    "grade": "B"
}
```

All students should be stored inside a list:

```python
students = []
```

---

## Example Output

```text
===== Student Performance Analyzer =====

How many students do you want to enter? 2

Enter data for student 1
Name: Ahmad
ID: 2024001
Math mark: 90
Programming mark: 95
English mark: 80
Physics mark: 85
Problem Solving mark: 100

Enter data for student 2
Name: Omar
ID: 2024002
Math mark: 40
Programming mark: 55
English mark: 45
Physics mark: 50
Problem Solving mark: 35

===== Full Report =====

Name: Ahmad
ID: 2024001
Average: 90.0
Status: Pass
Grade: A

Name: Omar
ID: 2024002
Average: 45.0
Status: Fail
Grade: F

===== Top Student =====
Name: Ahmad
ID: 2024001
Average: 90.0
Grade: A

===== Failed Students =====
Omar - 2024002 - Average: 45.0

===== Subject Statistics =====
Math:
Highest: 90
Lowest: 40
Average: 65.0

Programming:
Highest: 95
Lowest: 55
Average: 75.0

English:
Highest: 80
Lowest: 45
Average: 62.5

Physics:
Highest: 85
Lowest: 50
Average: 67.5

Problem Solving:
Highest: 100
Lowest: 35
Average: 67.5

Enter student ID to search: 2024001

Student Found:
Name: Ahmad
ID: 2024001
Average: 90.0
Status: Pass
Grade: A
```

---

## Bonus Challenge

Add a menu system:

```text
1. Add students
2. Show full report
3. Show top student
4. Show failed students
5. Show subject statistics
6. Search by ID
7. Exit
```

The program should keep running until the user chooses **Exit**.

---

## Submission Requirements

Submit:

1. Python file: `task1_student_analyzer.py`
2. A screenshot of the program running
3. A short README file answering:
   - What was the hardest part?
   - Which function did you write first?
   - What bugs did you face?
   - How did you solve them?

---

## Evaluation

| Criteria                | Marks |
|------------------------|-------|
| Correct input handling | 15    |
| Functions usage        | 20    |
| Correct calculations   | 20    |
| Clean code and names   | 15    |
| Full report output     | 15    |
| Search feature         | 10    |
| README explanation     | 5     |

**Total: 100 marks**

---

## Suggested Work Plan

### Day 1

Finish student input and data storage.

### Day 2

Add average, status, and grade calculations.

### Day 3

Add top student, failed students, and subject statistics.

### Day 4

Add search by ID and try the bonus menu system.
