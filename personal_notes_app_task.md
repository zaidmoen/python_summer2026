# Task: Personal Notes App

## Overview

In this task, you will build a simple **Personal Notes App** using Python.

The program will allow the user to:

- Add a new note
- Show all saved notes
- Search for a word inside the notes
- Clear all notes
- Exit the program

All notes will be saved inside a text file called:

```text
notes.txt
```

---

## Why Are We Doing This Task?

So far, most programs you wrote stored data only while the program was running.

For example, if you create a variable:

```python
name = "Zaid"
```

The value exists only while the program is open.

When the program stops, the value is gone.

In this task, you will learn a new and important idea:

> How to save data permanently using files.

That means when the user writes a note, the note will still exist even after closing the program.

---

## New Concept: File Handling

File handling means working with files using Python.

Python can:

- Create files
- Write data into files
- Read data from files
- Clear files

In this task, we will use a file called:

```text
notes.txt
```

---

## File Modes You Need

When using `open()`, Python needs to know what you want to do with the file.

### 1. Append Mode

Append mode is used when you want to add new content without deleting old content.

```python
file = open("notes.txt", "a")
file.write("This is a new note\n")
file.close()
```

The `"a"` means append.

Use this when adding a new note.

---

### 2. Read Mode

Read mode is used when you want to read content from a file.

```python
file = open("notes.txt", "r")
content = file.read()
file.close()
```

The `"r"` means read.

Use this when showing all notes or searching inside notes.

---

### 3. Write Mode

Write mode is used when you want to write new content into a file.

But be careful:

> Write mode deletes the old content first.

```python
file = open("notes.txt", "w")
file.close()
```

The `"w"` means write.

Use this when clearing all notes.

---

## Required Program Name

Submit one Python file:

```text
notes_app.py
```

---

# Program Requirements

## 1. Add a New Note

Create a function called:

```python
add_note()
```

This function should:

1. Ask the user to enter a note
2. Save the note inside `notes.txt`
3. Print a success message

Example:

```text
Enter your note: Today I learned file handling.
Note saved successfully.
```

---

## 2. Show All Notes

Create a function called:

```python
show_notes()
```

This function should:

1. Open `notes.txt`
2. Read all notes
3. Print them to the user

Example output:

```text
===== Your Notes =====
Today I learned Python.
I need to practice more.
File handling is useful.
```

If there are no notes, print:

```text
No notes found.
```

---

## 3. Search in Notes

Create a function called:

```python
search_notes()
```

This function should:

1. Ask the user to enter a word
2. Search for that word inside `notes.txt`
3. Print matching notes

Example:

```text
Enter word to search: Python

Found:
Today I learned Python.
Python is useful.
```

If there are no matches, print:

```text
No matching notes found.
```

---

## 4. Clear All Notes

Create a function called:

```python
clear_notes()
```

This function should:

1. Open `notes.txt` in write mode
2. Clear all old notes
3. Print a message

Example:

```text
All notes have been cleared.
```

---

## 5. Main Menu

The program should keep running until the user chooses Exit.

Example menu:

```text
===== Personal Notes App =====
1. Add Note
2. Show All Notes
3. Search Notes
4. Clear All Notes
5. Exit

Enter your choice:
```

---

# Rules

- Use functions.
- Use file handling.
- Do not use lists.
- Do not use dictionaries.
- Do not use classes.
- The program should not stop after one operation.
- Use clear variable names.
- Handle wrong choices.
- Your code should be clean and readable.

---

# Suggested Functions

Your program should contain these functions:

```python
add_note()
show_notes()
search_notes()
clear_notes()
main()
```

---

# Starter Code

Use this starter code to begin.

Do not copy-paste a full solution from anyone.

Try to complete each function by yourself.

```python
def add_note:
    # Ask the user to enter a note
    # Open notes.txt in append mode
    # Write the note inside the file
    # Close the file
    # Print success message
    pass


def show_notes():
    # Open notes.txt in read mode
    # Read the content
    # If content is empty, print "No notes found."
    # Otherwise, print the notes
    pass


def search_notes():
    # Ask the user to enter a word
    # Open notes.txt in read mode
    # Read the file line by line or read all content
    # Print notes that contain the searched word
    pass


def clear_notes():
    # Open notes.txt in write mode
    # Close the file
    # Print success message
    pass


def main():
    while True:
        print("===== Personal Notes App =====")
        print("1. Add Note")
        print("2. Show All Notes")
        print("3. Search Notes")
        print("4. Clear All Notes")
        print("5. Exit")

        choice = input("Enter your choice: ")

        if choice == "1":
            add_note()
        elif choice == "2":
            show_notes()
        elif choice == "3":
            search_notes()
        elif choice == "4":
            clear_notes()
        elif choice == "5":
            print("Goodbye!")
            break
        else:
            print("Invalid choice. Please try again.")


main()
```

---

# Important Note About the Starter Code

There is one small syntax issue in the starter code that you must fix before running it.

Look carefully at this line:

```python
def add_note:
```

A function definition in Python needs parentheses.

So it should be:

```python
def add_note():
```

---

# Helpful Hints

## Hint 1: Add a New Note

When adding a note, use append mode:

```python
file = open("notes.txt", "a")
file.write(note + "\n")
file.close()
```

Why do we add `"\n"`?

Because it moves the next note to a new line.

Without it, all notes may appear on the same line.

---

## Hint 2: Show Notes

You can read the full file like this:

```python
file = open("notes.txt", "r")
content = file.read()
file.close()
```

Then check if the file is empty:

```python
if content == "":
    print("No notes found.")
else:
    print(content)
```

---

## Hint 3: Search Notes

You can read the file line by line:

```python
file = open("notes.txt", "r")

for line in file:
    if word in line:
        print(line)

file.close()
```

This checks each note one by one.

---

## Hint 4: Case Sensitivity

Python is case-sensitive.

That means:

```text
Python
```

and

```text
python
```

are not the same.

To make search easier, you can convert both to lowercase:

```python
if word.lower() in line.lower():
    print(line)
```

---

## Hint 5: Clear Notes

To clear the file:

```python
file = open("notes.txt", "w")
file.close()
```

This opens the file in write mode and deletes its content.

---

# Common Mistakes

## Mistake 1: Forgetting to Close the File

Wrong:

```python
file = open("notes.txt", "a")
file.write("Hello")
```

Better:

```python
file = open("notes.txt", "a")
file.write("Hello\n")
file.close()
```

---

## Mistake 2: Using Write Mode When Adding Notes

Wrong:

```python
file = open("notes.txt", "w")
file.write(note)
file.close()
```

This deletes old notes every time.

Correct:

```python
file = open("notes.txt", "a")
file.write(note + "\n")
file.close()
```

---

## Mistake 3: Program Stops After One Choice

Your menu should be inside a `while True` loop.

```python
while True:
    # show menu
    # ask for choice
```

To exit the loop, use:

```python
break
```

---

## Mistake 4: Searching Only One Line

If you want to search all notes, you must check every line in the file.

Use a loop:

```python
for line in file:
    # check this line
```

---

# Example Program Flow

```text
===== Personal Notes App =====
1. Add Note
2. Show All Notes
3. Search Notes
4. Clear All Notes
5. Exit

Enter your choice: 1
Enter your note: I learned file handling today.
Note saved successfully.

===== Personal Notes App =====
1. Add Note
2. Show All Notes
3. Search Notes
4. Clear All Notes
5. Exit

Enter your choice: 2

===== Your Notes =====
I learned file handling today.
```

---

# Testing Checklist

Before submitting, make sure your program can do all of these:

- [ ] Add one note
- [ ] Add more than one note
- [ ] Show all notes
- [ ] Search for an existing word
- [ ] Search for a word that does not exist
- [ ] Clear all notes
- [ ] Show notes after clearing
- [ ] Exit the program
- [ ] Handle invalid menu choices

---

# Bonus Challenge

Add date and time before each note.

Example:

```text
[2026-06-23 10:30] Today I learned file handling.
```

You can use:

```python
from datetime import datetime
```

Example:

```python
current_time = datetime.now()
```

To format the date and time:

```python
formatted_time = current_time.strftime("%Y-%m-%d %H:%M")
```

Then save the note like this:

```python
file.write("[" + formatted_time + "] " + note + "\n")
```

---

# Final Submission

Submit:

```text
notes_app.py
```

The file should run without errors.

Good luck!
