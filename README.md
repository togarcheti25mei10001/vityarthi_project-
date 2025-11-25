class BudgetAdvisor:
    """
    A class to manage and advise on a college student's monthly budget.
    Implements three functional modules: Input/Data Processing, Budget Calculation, and Financial Reporting.
    """

    def __init__(self):
        # FIX: Changed _init_ to __init__ (double underscores)
        self.income = 0.0
        self.expenses = {}
        self.total_expenses = 0.0
        self.leftover = 0.0
        self.savings_goal = {"name": "", "amount": 0.0}

    # === Functional Module 1: Data Input & Processing ===
    def _collect_financial_data(self):
        """Collects the user's monthly income and detailed expenses."""
        print("\n--- 💰 Module 1: Data Input & Processing ---")
        
        while True:
            try:
                self.income = float(input("Enter your total monthly income (job, allowance, etc.): $"))
                if self.income < 0:
                    raise ValueError
                break
            except ValueError:
                print("Invalid input. Please enter a positive number for income.")

        print("\nEnter your monthly expenses:")
        expense_categories = {
            "Rent / Housing": "rent",
            "Food / Groceries": "food",
            "Transportation": "transportation",
            "Utilities / Phone / Internet": "utilities",
            "Entertainment / Eating Out": "entertainment",
            "Other personal expenses": "others"
        }
        
        for name, key in expense_categories.items():
            while True:
                try:
                    amount = float(input(f"  {name}: $"))
                    if amount < 0:
                        raise ValueError
                    self.expenses[key] = amount
                    break
                except ValueError:
                    print("Invalid input. Please enter a positive number for the expense.")

    # === Functional Module 2: Budget Calculation ===
    def _calculate_budget(self):
        """Calculates total expenses and the leftover balance."""
        print("\n--- 🧮 Module 2: Budget Calculation ---")
        
        self.total_expenses = sum(self.expenses.values())
        self.leftover = self.income - self.total_expenses

    # === Functional Module 3: Financial Reporting & Savings Advice ===
    def _generate_report_and_advice(self):
        """Generates the budget summary, financial advice, and savings goal planner."""
        print("\n--- 📊 Module 3: Financial Reporting & Advice ---")
        
        # Budget Summary
        print("\n--- Monthly Budget Summary ---")
        print(f"Total Income:     ${self.income:,.2f}")
        print(f"Total Expenses:   ${self.total_expenses:,.2f}")
        print(f"Money Left Over:  ${self.leftover:,.2f}")

        # Financial Advice
        print("\n--- Financial Advice ---")

        if self.leftover > 0:
            print("✅ Great! You are spending less than you earn.")

            # Savings recommendation based on 50/30/20 rule
            recommended_savings = self.income * 0.20
            print(f"- Based on the 20% rule, you should aim to save: ${recommended_savings:,.2f} per month.")

            if self.leftover < recommended_savings:
                print("⚠ Warning: Your current leftover amount is less than the 20% savings target.")
            else:
                 print("Good job! You meet the 20% savings target.")

        elif self.leftover == 0:
            print("⚠ Caution: You are breaking even. Try lowering some non-essential expenses.")
        else:
            print("❌ Warning: You are spending MORE than you earn! (Deficit: ${:.2f})".format(abs(self.leftover)))
            print("Action Needed: Try cutting down discretionary expenses or finding additional income.")
            
        self._plan_savings_goal()
        
    def _plan_savings_goal(self):
        """Handles the savings goal planning feature."""
        print("\n--- Savings Goal Planner ---")
        self.savings_goal["name"] = input("Enter a savings goal (e.g., laptop, emergency fund): ")
        
        while True:
            try:
                self.savings_goal["amount"] = float(input("Goal amount ($): "))
                if self.savings_goal["amount"] < 0:
                    raise ValueError
                break
            except ValueError:
                print("Invalid input. Please enter a positive goal amount.")

        if self.leftover > 0:
            # Calculation using LaTeX context for clarity in thought
            # Time = Goal / MonthlySavings
            months_needed = self.savings_goal["amount"] / self.leftover
            print(f"At your current leftover amount (${self.leftover:,.2f}/mo), you can reach your '{self.savings_goal['name']}' goal in about *{months_needed:.1f} months*.")
        else:
            print("You currently cannot save toward your goal because you have no leftover funds.")

    # === Main Execution Method ===
    def run_advisor(self):
        print("\n--- Welcome to the College Student Budget & Savings Advisor ---")
        self._collect_financial_data()
        self._calculate_budget()
        self._generate_report_and_advice()
        print("\n--- End of Report ---\n")


# Execution block
if __name__ == "__main__":
    # FIX: Changed _name_ and _main_ to __name__ and __main__
    advisor = BudgetAdvisor()
    advisor.run_advisor()
