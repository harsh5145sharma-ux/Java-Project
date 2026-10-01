# Student Registration Form – Java Swing

A simple desktop GUI application for student registration built using **Java Swing**.

## Features

- Student Name input
- Roll Number input
- Gender selection using radio buttons
- Branch input
- Terms & Conditions checkbox
- Submit button with input validation
- Reset button to clear the form
- Registration-success dialog displaying submitted details

## Technologies Used

- Java
- Java Swing
- AWT Event Handling

## Project Structure

```text
Student-Registration-Swing/
├── src/
│   └── StudentRegistration.java
├── README.md
└── .gitignore
```

## How to Run

Make sure Java JDK is installed.

### Compile

```bash
javac src/StudentRegistration.java
```

### Run

```bash
java -cp src StudentRegistration
```

## Validation

The application checks that:

1. Student name is entered.
2. Roll number is entered.
3. Gender is selected.
4. Branch is entered.
5. Terms & Conditions are accepted.

After successful validation, a registration-success message displays the entered details.

## GitHub Upload

```bash
git init
git add .
git commit -m "Add Java Swing student registration form"
git branch -M main
git remote add origin YOUR_GITHUB_REPOSITORY_URL
git push -u origin main
```

## Learning Outcome

This project demonstrates basic Java Swing GUI development, event handling with `ActionListener`, form validation, radio-button grouping, checkbox handling, and dialog messages.
