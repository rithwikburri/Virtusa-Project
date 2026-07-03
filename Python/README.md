# Ride Fare Calculator

## Overview
The Ride Fare Calculator is a Python program that calculates the fare for a ride based on:
- Distance travelled
- Vehicle type
- Time of the ride

The program also applies surge pricing (50% extra) during peak hours (5 PM to 8 PM).

---

## Features
- Calculates fare based on distance.
- Supports multiple vehicle types.
- Applies peak hour surge pricing.
- Validates user inputs.
- Displays a ride receipt.
- Handles invalid inputs using exception handling.

---

## Vehicle Rates

| Vehicle Type | Rate per km |
|--------------|-------------|
| Economy | ₹10 |
| Premium | ₹18 |
| SUV | ₹25 |

---

## Peak Hour Pricing

If the ride time is between **17:00 (5 PM)** and **20:00 (8 PM)**, the fare is increased by **50%**.

Example:

Base Fare = ₹200

Peak Hour Fare = ₹200 × 1.5 = ₹300

---

## Requirements

- Python 3.x

No external libraries are required.

---

## How to Run

1. Save the program as:

```
fare_calculator.py
```

2. Open Terminal or Command Prompt.

3. Navigate to the project folder.

4. Run:

```bash
python fare_calculator.py
```

---

## Sample Input

```
Enter distance (km): 12
Enter vehicle type (Economy/Premium/SUV): Premium
Enter hour (0-23): 18
```

---

## Sample Output

```
----- Ride Receipt -----
Distance: 12.0 km
Vehicle: Premium
Time: 18
Total Fare: ₹324.00
```

---

## Input Validation

The program checks for:

- Distance must be greater than 0.
- Vehicle type must be Economy, Premium, or SUV.
- Hour must be between 0 and 23.
- Invalid numeric inputs are handled using `try-except`.

---

## Program Structure

### Function

```python
calculate_fare(km, vehicle_type, hour, rates)
```

Calculates the ride fare using:
- Distance
- Vehicle rate
- Peak hour surcharge

Returns the final fare.

---

## Technologies Used

- Python
- Functions
- Dictionary
- Conditional Statements
- Exception Handling

---

## Author

Developed by **Rithwik Burri**
