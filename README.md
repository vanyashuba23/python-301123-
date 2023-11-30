expenses = []

def add_expense():
    amount = float(input("Enter the amount: "))
    category = input("Enter the category: ")
    description = input("Enter the description: ")
    new_expense = {'amount': amount, 'category': category, 'description': description}
    expenses.append(new_expense)

def display_categories():
    print("Categories: Food, Entertainment, Utilities, Other")

def generate_report():
    for expense in expenses:
        print(f"Amount: ${expense['amount']}, Category: {expense['category']}, Description: {expense['description']}")

def generate_category_report(category):
    category_expenses = [expense for expense in expenses if expense['category'].lower() == category.lower()]
    for expense in category_expenses:
        print(f"Amount: ${expense['amount']}, Description: {expense['description']}")

while True:
    command = input("Enter a command (add/report/quit): ")

    if 'add' in command:
        add_expense()
    elif 'report' in command:
        category_filter = input("Enter a category to filter (leave blank for all categories): ")
        if category_filter:
            generate_category_report(category_filter)
        else:
            generate_report()
    elif 'quit' in command:
        break
    else:
        print("Invalid command. Please try again.")
