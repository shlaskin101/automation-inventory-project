# Automation with Python: Inventory Spreadsheet Project

This project is part of the **Automation with Python** module in the TechWorld with Nana course. It focuses on automating Excel-based inventory reporting using the `openpyxl` library.

---

## 🧰 Technologies Used

- **Python 3.x**
- **openpyxl** (for reading/writing Excel files)
- **PyCharm IDE** (Community Edition)
- **Git** for version control

---

## 📝 Project Description

This Python application reads an Excel spreadsheet (`inventory.xlsx`) and performs the following automation tasks:

### 🔍 Exercises Implemented

- **List each company with respective product count**
- **List products with inventory less than 10**
- **List each company with respective total inventory value**
- **Write to spreadsheet: calculate and write inventory value for each product**

---

## 📂 File: `main.py`

```python
import openpyxl

inv_file = openpyxl.load_workbook("inventory.xlsx")
product_list = inv_file["Sheet1"]

products_per_supplier = {}
total_value_per_supplier = {}
products_under_10_inv = {}

for product_row in range(2, product_list.max_row + 1):
    supplier_name = product_list.cell(product_row, 4).value
    inventory = product_list.cell(product_row, 2).value
    price = product_list.cell(product_row, 3).value
    product_num = product_list.cell(product_row, 1).value
    inventory_price = product_list.cell(product_row, 5)

    if supplier_name in products_per_supplier:
        products_per_supplier[supplier_name] += 1
    else:
        products_per_supplier[supplier_name] = 1

    if supplier_name in total_value_per_supplier:
        total_value_per_supplier[supplier_name] += inventory * price
    else:
        total_value_per_supplier[supplier_name] = inventory * price

    if inventory < 10:
        products_under_10_inv[int(product_num)] = int(inventory)

    inventory_price.value = inventory * price

print(products_per_supplier)
print(total_value_per_supplier)
print(products_under_10_inv)

inv_file.save("inventory_with_total_value.xlsx")
```

---

## 📦 How to Install Dependencies

To install the required spreadsheet library:

```bash
pip install openpyxl
```

---

## ✅ How to Run

```bash
python main.py
```

This will output three dictionaries in the terminal and generate a new Excel file: `inventory_with_total_value.xlsx`

---

## 📊 Sample Output

```
{'Supplier A': 5, 'Supplier B': 3, 'Supplier C': 7}
{'Supplier A': 2240.0, 'Supplier B': 910.0, 'Supplier C': 3375.0}
{2345: 5, 3456: 3, 9876: 9}
```

---

## 💬 Nana's Final Remarks

- The project showcases **real-world automation** using Python.
- We used `openpyxl`, an external library tailor-made for working with Excel spreadsheets — far more practical than Python’s built-in file modules for this use case.
- We executed business logic, **updated cells**, and **generated a new output file** programmatically.
- These types of automations are especially useful in companies that manually manage Excel files regularly.

---

## 🌐 Author

**GitHub:** [shlaskin101](https://github.com/shlaskin101)

---

## 🏁 License

This project is for educational and demonstration purposes.
