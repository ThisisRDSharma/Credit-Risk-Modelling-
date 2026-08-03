

from tabulate import tabulate

print(tabulate(df, headers="keys", tablefmt="grid", showindex=False))


import pandas as pd

columns = pd.MultiIndex.from_tuples([
    ("Employee", "Name"),
    ("Employee", "ID"),
    ("Performance", "Q1"),
    ("Performance", "Q2"),
    ("Performance", "Q3"),
])

data = [
    ["Alice", 101, 85, 90, 88],
    ["Bob", 102, 78, 82, 80],
]

df = pd.DataFrame(data, columns=columns)

print(df)


import pandas as pd

# Create hierarchical (grouped) column headers
columns = pd.MultiIndex.from_tuples([
    ("Employee", "Name"),
    ("Employee", "ID"),
    ("Sales", "Q1"),
    ("Sales", "Q2"),
    ("Sales", "Q3"),
    ("Sales", "Q4"),
    ("Expenses", "Q1"),
    ("Expenses", "Q2"),
    ("Expenses", "Q3"),
    ("Expenses", "Q4"),
])

# Sample data
data = [
    ["Alice", 101, 120, 135, 150, 160, 60, 65, 70, 75],
    ["Bob", 102, 110, 125, 140, 155, 55, 60, 68, 72],
    ["Charlie", 103, 130, 145, 155, 170, 62, 67, 73, 78],
]

# Create DataFrame
df = pd.DataFrame(data, columns=columns)

# Display in console
print(df)

# Save to Excel (headers will appear as grouped columns)
df.to_excel("grouped_table.xlsx", index=False)

print("\nTable saved as 'grouped_table.xlsx'")

from tabulate import tabulate

print(tabulate(df, headers="keys", tablefmt="grid", showindex=False))
