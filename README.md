# vityarthi_project-
project on collge student budget advisor
📘 College Student Budget Advisor

1. Project Title

College Student Budget Advisor

2. Problem Definition

College students often struggle to manage their monthly expenses due to limited income, unpredictable spending habits, and lack of financial planning. This leads to overspending, debt, and difficulty saving money.
The goal of this project is to build a simple digital advisor that helps students track their income, monitor expenses, set budgets, and receive alerts or suggestions to improve financial discipline.

3. Objectives

Help students track monthly income and categorize expenses.

Provide a clear overview of spending patterns.

Enable users to set monthly budgets for each category.

Notify when spending exceeds the budget limit.

Improve financial awareness and planning habits among students.

4. Expected Outcomes

A working budget advisor tool with simple and intuitive usage.

Monthly summary of expenses, savings, and overspending.

Graphs or tables showing spending patterns (optional).

Better financial planning for college students.

5. Requirement Analysis

Functional Requirements

Add income and expense entries.

Categorize expenses (food, travel, hostel, books, entertainment, etc.).

Set monthly budget limits.

Generate summary (remaining balance, total expenses, savings).

Store data in files (JSON/CSV).


Non-Functional Requirements

Usability: Easy for students to use daily.

Performance: Fast calculations and quick access to data.

Maintainability: Easy to update categories or logic.

Portability: Should run on any system that supports Python.


6. System Design (Top-Down Method)

Top-Down Breakdown

Budget Advisor System
│
├── Data Input Module
│       ├── Add Income
│       ├── Add Expense
│
├── Budget Management Module
│       ├── Set Monthly Budget
│       ├── Track Category Limits
│
├── Analysis Module
│       ├── Calculate total expenses
│       ├── Compare budget vs expenses
│       ├── Generate summary
│
└── Storage Module
        ├── Save data to file
        ├── Load previous records


7. Algorithm

Basic Budget Calculation Algorithm

1. Start


2. Input total monthly income


3. Input expenses (amount + category)


4. Add each new expense to the category total


5. Compare category spending with category budget


6. If spending > budget → show alert


7. At end of month:

Total expenses = sum of all categories

Savings = Income − Total expenses



8. Display summary report


9. End


8. Implementation Details

Programming Language

Python


Libraries Used

json for data storage

csv (optional)

matplotlib (optional for graphs)


Project Structure

college-budget-advisor/
│
├── README.md
├── report.pdf
├── src/
│    ├── main.py
│    ├── budget_manager.py
│    ├── storage.py
│
├── screenshots/
└── recordings/

9. How to Run the Project

git clone <your-repository-link>
cd college-budget-advisor
python src/main.py

10. Screenshots

Screenshots of the project output and execution are available in the /screenshots folder.

11. Recordings

Any demo videos are located in the /recordings folder.


---

12. Conclusion

The College Student Budget Advisor helps students efficiently manage their money by tracking income and expenses, enforcing budget limits, and providing clear summaries. This tool promotes financial discipline and helps students develop responsible spending habits.
