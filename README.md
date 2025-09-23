# Experiment 16: Exception Handling in C++

## AIM
To understand and implement **exception handling** in C++ using the `try`, `throw`, and `catch` mechanism through the following programs:
- Division of two numbers (with division by zero check)  
- Marks validation (checking if the student is eligible for admission)  

---

## OBJECTIVES
- Learn how C++ handles runtime errors gracefully.  
- Understand the use of `try`, `throw`, and `catch` blocks.  
- Practice throwing exceptions of different data types.  
- Explore exception handling as an alternative to traditional error handling using conditions.  
- Ensure program safety and reliability during abnormal situations.  

---

## THEORY

### What is Exception Handling?
- Exception handling is a mechanism to **detect and handle runtime errors** in a structured way.  
- Instead of abruptly terminating the program, exceptions allow the program to **“catch”** the error and respond properly.  

### Need for Exception Handling
- Runtime errors such as **division by zero, invalid input, file not found, out-of-range access** can cause program crashes.  
- Traditional error handling (using `if-else`) may not be sufficient in complex programs.  
- Exception handling provides a **cleaner and safer** approach.  

### Components of Exception Handling
- **`try` block** → Code where an exception might occur.  
- **`throw` statement** → Signals an exception has occurred (can throw any type: int, float, string, object).  
- **`catch` block** → Handles the exception thrown. Different catch blocks can handle different types.  

### Advantages
- Improves program **reliability and security**.  
- Separates **error-handling** from **normal logic**.  
- Prevents crashes during unexpected events.  
- Handles **multiple error types** in one program.  

---

## Exception Handling vs Normal Error Handling

| Feature              | Normal Error Handling (if-else) | Exception Handling (try-throw-catch) |
|----------------------|---------------------------------|--------------------------------------|
| Style                | Mixes error checks with logic   | Separates logic and error-handling   |
| Flexibility          | Limited                        | Handles multiple error types easily  |
| Runtime Errors       | May cause crash if unhandled   | Prevents crash with safe handling    |
| Readability          | Can become lengthy and complex | Cleaner and structured               |

---

## COMPARISON TABLE

| Program            | Exception Condition      | Exception Type | Example Input      | Example Output                        | Concept Focus             |
|--------------------|--------------------------|----------------|--------------------|---------------------------------------|---------------------------|
| Division Program   | If denominator = 0       | `float`        | n1 = 10, n2 = 0    | `ERROR: Division by 0`                 | Mathematical error check  |
| Marks Validation   | If marks < 50            | `int`          | marks = 45         | `You are not eligible for admission.`  | Input validation          |

---

## ALGORITHMS

### Division Program (Division by Zero Check)
1. Start.  
2. Input two numbers: numerator and denominator.  
3. Begin a `try` block.  
4. If denominator = 0 → `throw` an exception.  
5. Else → perform division and display result.  
6. In the `catch` block → display `"ERROR: Division by 0"`.  
7. Stop.  

### Marks Validation Program (Admission Eligibility)
1. Start.  
2. Input marks.  
3. Begin a `try` block.  
4. If marks < 50 → `throw` an exception (not eligible).  
5. Else → display `"You are eligible for admission."`.  
6. In the `catch` block → display `"You are not eligible for admission."`.  
7. Stop.  

---

## PROGRAM DESCRIPTIONS

### Division Program
- **Aim**: Perform division of two numbers with exception handling for division by zero.  
- **Logic**:  
  - Input two numbers.  
  - If denominator = 0 → `throw` exception.  
  - Else → perform division.  
- **Focus**: Runtime error handling in math operations.  

### Marks Validation Program
- **Aim**: Validate marks using exception handling.  
- **Logic**:  
  - Input marks.  
  - If marks < 50 → `throw` exception.  
  - Else → display eligibility message.  
- **Focus**: Input validation with exceptions.  

---

## PROGRAMS

### Division Program (C++)
```cpp
#include <iostream>
using namespace std;

int main() {
    float num, den, result;
    cout << "Enter numerator: ";
    cin >> num;
    cout << "Enter denominator: ";
    cin >> den;

    try {
        if (den == 0) {
            throw den;
        }
        result = num / den;
        cout << "Result = " << result << endl;
    }
    catch (float d) {
        cout << "ERROR: Division by 0" << endl;
    }

    return 0;
}
