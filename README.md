# Countdown Application

This project is a simple Python-based countdown application built as part of the **Automation with Python** module in the TechWorld with Nana course. It accepts user input in two formats:

1. **Goal and deadline input** (e.g., `learn python:10.01.2030`) — calculates how much time remains until the deadline.
2. **Number of days and unit** (e.g., `10:hours`) — converts days to hours or minutes.

## 🚀 Technologies Used

- **Python 3.13**
- **PyCharm IDE** (Community Edition)
- **Git** and **GitHub** for version control

---

## 📁 Project Structure

```
my-python-project/
├── main.py                 # Handles user input for converting days
├── helper.py               # Contains logic for validation and conversion
├── time-till-deadline.py   # Calculates time remaining until a deadline
```

---

## 🧠 Logic Summary

### main.py

- Prompts user for a number of days and the desired unit (`hours` or `minutes`)
- Splits and stores input into a dictionary
- Calls helper functions to validate and compute the result

### helper.py

- Converts days to hours or minutes
- Validates input (checks if numeric and positive)
- Returns informative messages on invalid input

### time-till-deadline.py

- Accepts goal and deadline in the format `goal:DD.MM.YYYY`
- Uses Python's `datetime` module to calculate the remaining time
- Outputs the remaining time in **hours**

Example:

```
Input: learn python:10.01.2030
Output: Dear user! Time remaining for your goal: learn python is 42432 hours
```

---

## ⚠️ Note

If you input a **past date**, the result will be negative, such as:

```
Dear user! Time remaining for your goal: learn python is -8866960 hours
```

---

## ✅ How to Run the Application

Make sure Python 3 is installed.

```bash
cd my-python-project
python3 time-till-deadline.py
```

or for main/helper interaction:

```bash
python3 main.py
```

---

## ✅ Nana's Final Remarks

- Python scripts should be modular and split into logical units.
- Good naming conventions and separation of concerns improve reusability.
- Use the `datetime` module when working with deadlines or time logic.
- Try various test inputs to see how your program responds.

---

## 🌐 Author

**GitHub**: [shlaskin101](https://github.com/shlaskin101)

## 🏁 License

This project is for educational and demonstration purposes. No license restrictions apply.
