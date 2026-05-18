# Expense Tracker System

expenses = []
def add_expense():
    date = input("Enter date (DD-MM-YYYY): ")
    category = input("Enter category (Food, Travel, etc): ")
    amount = float(input("Enter amount: "))

    expense = {
        "date": date,
        "category": category,
        "amount": amount
    }

    expenses.append(expense)
    print("Expense added successfully.\n")



def view_expenses():
    if not expenses:
        print("No expenses recorded.\n")
        return

    print("\nAll Expenses:")
    for i, expense in enumerate(expenses, start=1):
        print(f"{i}. Date: {expense['date']}, Category: {expense['category']}, Amount: {expense['amount']}")
    print()

def total_expense():
    total = sum(expense["amount"] for expense in expenses)
    print(f"Total Expense: {total}\n")



def menu():
    while True:
        print("\n===== EXPENSE TRACKER MENU =====")
        print("1. Add Expense")
        print("2. View Expenses")
        print("3. View Total Expense")
        print("4. Exit")

        choice = input("Enter your choice: ")

        if choice == "1":
            add_expense()
        elif choice == "2":
            view_expenses()
        elif choice == "3":
            total_expense()
        elif choice == "4":
            print("Exiting program...")
            break
        else:
            print("Invalid choice. Try again.\n")


menu()
