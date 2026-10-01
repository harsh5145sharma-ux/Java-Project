# Calculator using Java Swing - MVC Architecture

A simple GUI-based calculator developed using **Java Swing** and the **MVC (Model-View-Controller) architecture**.

## Project Objective

The application performs basic arithmetic operations while separating the application into three components:

- **Model** - Contains calculation/business logic.
- **View** - Contains the Swing GUI.
- **Controller** - Handles button events and connects the View with the Model.

The project is based on the supplied practical document, which demonstrates addition, subtraction, multiplication and division using MVC. fileciteturn1file0L5-L14

## Features

- Addition
- Subtraction
- Multiplication
- Division
- Java Swing GUI
- MVC architecture
- Button click event handling
- Result displayed in a non-editable field

## Technologies Used

- Java
- Java Swing
- AWT Event Handling
- MVC Architecture

## Project Structure

```text
Calculator-MVC-Java-Swing/
├── src/
│   ├── CalculatorModel.java
│   ├── CalculatorView.java
│   ├── CalculatorController.java
│   └── Main.java
├── README.md
└── .gitignore
```

## MVC Flow

```text
View (Swing GUI)
       |
       v
Controller (ActionListener)
       |
       v
Model (Calculations)
       |
       v
Result -> View
```

The supplied document describes the same separation: the Model contains calculations, the View contains GUI components, and the Controller reads input, calls the Model and displays the result. fileciteturn1file0L21-L43

## How to Run

Make sure Java JDK is installed.

### Compile

```bash
javac src/*.java
```

### Run

```bash
java -cp src Main
```

## Example

Input:

```text
First Number: 25
Second Number: 10
Operation: +
```

Output:

```text
Result: 35.0
```

## GitHub Upload

Create a GitHub repository named:

**Calculator-MVC-Java-Swing**

Then run:

```bash
git init
git add .
git commit -m "Add Java Swing MVC calculator"
git branch -M main
git remote add origin YOUR_GITHUB_REPOSITORY_URL
git push -u origin main
```

## Viva Topics

The source document includes viva questions covering MVC architecture, Model/View separation, ActionListener, JFrame vs JPanel, setEditable(false), Swing packages, division by zero, event-driven programming and MVC advantages. fileciteturn1file0L188-L198
