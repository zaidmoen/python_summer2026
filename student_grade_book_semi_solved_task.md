# Python Task: Student Grade Book - Semi Solved

## Goal

Complete the missing parts in the code below.

This program saves student grades inside a file called:

```txt
grades.txt
```

The program should allow the user to:

1. Add a new grade
2. Show all grades
3. Search for a student
4. Calculate average grade
5. Show highest grade
6. Exit

---

## What You Need To Complete

Inside the code, you will find comments like:

```python
# TODO
```

You must complete these parts only.

---

## Starter Code

```python
FILE_NAME = "grades.txt"


def add_grade():
    name = input("Enter student name: ").strip()
    subject = input("Enter subject: ").strip()

    if name == "" or subject == "":
        print("Name and subject cannot be empty.")
        return

    grade = input("Enter grade: ")

    # TODO 1:
    # Check if grade is a number.
    # If it is not a number, print an error message and return.

    grade = int(grade)

    # TODO 2:
    # Check if grade is between 0 and 100.
    # If not, print an error message and return.

    with open(FILE_NAME, "a") as file:
        file.write(f"{name},{subject},{grade}\n")

    print("Grade added successfully!")


def show_all_grades():
    try:
        with open(FILE_NAME, "r") as file:
            lines = file.readlines()

        if len(lines) == 0:
            print("No grades found.")
            return

        print("\n===== All Grades =====")

        for line in lines:
            data = line.strip().split(",")

            name = data[0]
            subject = data[1]
            grade = data[2]

            print(f"Name: {name} | Subject: {subject} | Grade: {grade}")

    except FileNotFoundError:
        print("No grades found.")


def search_student():
    search_name = input("Enter student name to search: ").strip().lower()

    found = False

    try:
        with open(FILE_NAME, "r") as file:
            lines = file.readlines()

        for line in lines:
            data = line.strip().split(",")

            name = data[0]
            subject = data[1]
            grade = data[2]

            # TODO 3:
            # Compare the searched name with the student name.
            # The search should not be case-sensitive.
            # If they match, print the student data and set found = True.

        if found == False:
            print("Student not found.")

    except FileNotFoundError:
        print("No grades found.")


def calculate_average():
    total = 0
    count = 0

    try:
        with open(FILE_NAME, "r") as file:
            lines = file.readlines()

        for line in lines:
            data = line.strip().split(",")

            grade = int(data[2])

            # TODO 4:
            # Add grade to total.
            # Increase count by 1.

        if count == 0:
            print("No grades to calculate.")
        else:
            average = total / count
            print(f"Average grade: {average:.2f}")

    except FileNotFoundError:
        print("No grades found.")


def show_highest_grade():
    highest_grade = -1
    highest_name = ""
    highest_subject = ""

    try:
        with open(FILE_NAME, "r") as file:
            lines = file.readlines()

        if len(lines) == 0:
            print("No grades found.")
            return

        for line in lines:
            data = line.strip().split(",")

            name = data[0]
            subject = data[1]
            grade = int(data[2])

            # TODO 5:
            # Check if this grade is higher than highest_grade.
            # If yes, update highest_grade, highest_name, and highest_subject.

        print("\n===== Highest Grade =====")
        print(f"Name: {highest_name}")
        print(f"Subject: {highest_subject}")
        print(f"Grade: {highest_grade}")

    except FileNotFoundError:
        print("No grades found.")


def menu():
    while True:
        print("\n===== Student Grade Book =====")
        print("1. Add new grade")
        print("2. Show all grades")
        print("3. Search student")
        print("4. Calculate average grade")
        print("5. Show highest grade")
        print("6. Exit")

        choice = input("Enter your choice: ")

        if choice == "1":
            add_grade()

        elif choice == "2":
            show_all_grades()

        elif choice == "3":
            search_student()

        elif choice == "4":
            calculate_average()

        elif choice == "5":
            show_highest_grade()

        elif choice == "6":
            print("Goodbye!")
            break

        else:
            # TODO 6:
            # Print invalid choice message.
            pass


menu()
```

---

## Example File Content

After adding some students, the file should look like this:

```txt
Ahmad,Math,88
Sara,Python,95
Omar,English,76
```

---

## Required Output Example

When choosing option 2:

```txt
===== All Grades =====
Name: Ahmad | Subject: Math | Grade: 88
Name: Sara | Subject: Python | Grade: 95
Name: Omar | Subject: English | Grade: 76
```

---

## Hints

### Hint for TODO 1

You can use:

```python
grade.isdigit()
```

Example idea:

```python
if not grade.isdigit():
    print("Grade must be a number.")
    return
```

---

### Hint for TODO 2

After converting grade to integer, check the range:

```python
if grade < 0 or grade > 100:
    print("Grade must be between 0 and 100.")
    return
```

---

### Hint for TODO 3

You need to compare:

```python
name.lower()
```

with:

```python
search_name
```

Example idea:

```python
if name.lower() == search_name:
    print(f"Name: {name} | Subject: {subject} | Grade: {grade}")
    found = True
```

---

### Hint for TODO 4

You need to do two things:

```python
total = total + grade
count = count + 1
```

---

### Hint for TODO 5

Think about this condition:

```python
if grade > highest_grade:
```

Inside the condition, update the highest student information.

---

### Hint for TODO 6

Print this message:

```python
print("Invalid choice. Please try again.")
```

---

## Bonus Challenge

Add a new option:

```txt
7. Delete student
```

The program should ask for a student name and remove all records for that student from the file.

---

## Submission

Submit:

1. Your Python file
2. The grades.txt file
3. A screenshot showing your program running

Good luck!
