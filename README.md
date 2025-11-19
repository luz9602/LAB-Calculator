# Exercise Calculator
To complete this lab, we will work in two phases. Do not begin phase #2 without completing phase #1

**Phase 1: MVP**
- You must write the four basic functions in your script.js file.
- Each operation (addition, subtraction, multiplication, division) must have its own function.
- The functions must receive two parameters (ex., a and b).
- Test: Call your functions using clean numbers (ex., add(5, 5)) and print the result outside the function.

**Phase 2: Shielding against the user (Extra)**

*In the real world, users enter data through HTML forms, and that data always arrives as text (strings).*
- Simulate this by creating test variables with quotes: `let number1 = "10";` and `let number2 = "20";`.
- Try adding them together. Did you get 30 or 1020?

**Your mission:** Modify your functions to use `parseFloat()`, converting the parameters to real numbers before performing operations on them.

## Specifications of the problem

*For the solution to be valid and professional, the code must strictly comply with these specifications:*
- **Modularity** (use of functions): Writing calculations directly in the global code is prohibited. You must encapsulate each operation in its own function.
- **Correct mathematics:** The calculator must be able to add numerical texts ("5" + "5") and give a mathematical result (10), not a concatenation ("55").

**Golden Rule: Return vs. Console.log (IMPORTANT)**
- **WITHIN** the function: Strictly prohibited to use console.log. The function must use return to return the raw numeric result.\
- **OUTSIDE** the function: It is mandatory to use console.log to display the result that the function returned.

## The algorithm

1. Start process
2. Start loop while the user wishes to continue
3. Ask the user to select the type of operation to perform (+, -, *, /). Validate that the entered operation belongs to the allowed symbols; if not, display an error.
4. Ask for the first value (must be an integer or floating-point number; letters are not accepted).
5. Ask for the second value (must be an integer or floating-point number; letters are not accepted). In case of an error in the values, decide whether to ask for the number again or stop the process.
6. Validate that both entered values ​​are numbers; if not, display an error.
7. Determine which operation corresponds to the entered symbol.
8. If the operation is division, validate that the divisor is not 0. If so, display an error to the user.
9. Perform the corresponding operation.
10. Display the result to the user.
11. Give the user the option to perform another operation (yes/no or 1/0).
12. End of loop.
13. End process.


## Pseudocode

START

    repeat ← "YES"   // works as a switch for the loop

    WHILE repeat = "YES" DO

        WRITE "Select an operation (+, -, *, /):"
        READ operation

        // Validate operation
        IF operation ≠ "+" AND operation ≠ "-" AND operation ≠ "*" AND operation ≠ "/" THEN
            WRITE "Error: invalid operation"
            CONTINUE
        END IF

        WRITE "Enter the first number:"
        READ num1

        IF num1 IS NOT NUMERIC THEN
            WRITE "Error: the value entered is not a number"
            CONTINUE
        END IF

        WRITE "Enter the second number:"
        READ num2

        IF num2 IS NOT NUMERIC THEN
            WRITE "Error: the value entered is not a number"
            CONTINUE
        END IF

        IF operation = "/" THEN
            IF num2 = 0 THEN
                WRITE "Error: division by 0 is not allowed"
                CONTINUE
            END IF
        END IF

        SWITCH operation
            CASE "+"
                result ← num1 + num2
            CASE "-"
                result ← num1 - num2
            CASE "*"
                result ← num1 * num2
            CASE "/"
                result ← num1 / num2
        END SWITCH

        WRITE "The result is: ", result

        WRITE "Do you want to perform another operation? (YES/NO):"
        READ repeat

    END WHILE

END