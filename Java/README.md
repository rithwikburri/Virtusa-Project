# Password Validator

## Overview

The Password Validator is a Java console application that validates a user's password based on predefined security rules. The program repeatedly prompts the user until a valid password is entered.

---

## Features

- Checks minimum password length.
- Verifies the presence of at least one uppercase letter.
- Verifies the presence of at least one digit.
- Displays appropriate error messages for invalid passwords.
- Continues prompting until a valid password is entered.

---

## Password Validation Rules

A valid password must satisfy all of the following conditions:

- Minimum **8 characters** long.
- Contains **at least one uppercase letter (A–Z)**.
- Contains **at least one numeric digit (0–9)**.

---

## Program Flow

1. User enters a password.
2. The program checks:
   - Password length
   - Uppercase letter
   - Numeric digit
3. If any condition fails, an error message is displayed.
4. The user is prompted to enter another password.
5. When all conditions are satisfied, the program displays a success message.

---

## Technologies Used

- Java
- Scanner Class
- Loops
- Conditional Statements
- Methods
- Character Class (`Character.isUpperCase()`, `Character.isDigit()`)

---

## Project Structure

### Class

```
PasswordValidator
```

### Methods

#### `isValid(String password)`

Checks whether the entered password satisfies all validation rules.

**Returns:**
- `true` if the password is valid.
- `false` otherwise.

#### `main(String[] args)`

- Accepts user input.
- Calls the validation method.
- Repeats until a valid password is entered.

---

## Sample Input and Output

### Example 1

```
Enter password: hello
Password too short (min 8 characters)
Try again.
```

---

### Example 2

```
Enter password: password123
Missing uppercase letter
Try again.
```

---

### Example 3

```
Enter password: Password
Missing digit
Try again.
```

---

### Example 4

```
Enter password: Password123
Password is valid!
```

---

## Validation Logic

The program performs the following checks:

1. Password length must be at least 8 characters.
2. Loop through each character.
3. Check for:
   - Uppercase letters
   - Digits
4. Return `true` only if all conditions are satisfied.

---

## Requirements

- Java JDK 8 or above
- Any Java IDE (IntelliJ IDEA, Eclipse, VS Code) or Command Prompt

---

## How to Run

### Compile

```bash
javac PasswordValidator.java
```

### Execute

```bash
java PasswordValidator
```

---

## Expected Outcome

The application ensures that users create passwords meeting the basic security requirements by validating:

- Password length
- Uppercase letters
- Numeric digits

The program only terminates after a valid password is entered.

---

## Future Enhancements

- Require at least one lowercase letter.
- Require at least one special character.
- Prevent common or weak passwords.
- Display password strength (Weak, Medium, Strong).
- Hide password input while typing.

---

## Author

**Rithwik Burri**
```
