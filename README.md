TASK2-Stock-Portfolio-Tracker
portfolio = {}

def add_stock(name, qty, cost):
    name = name.upper()
    portfolio[name] = [qty, cost]
    print(f"{qty} shares of {name} added at ${cost} each.")

def delete_stock(name):
    name = name.upper()
    if name in portfolio:
        del portfolio[name]
        print(f"{name} removed from portfolio.")
    else:
        print(f"{name} not found.")

def show_stocks():
    total_value = 0
    print("\nCurrent Portfolio:")
    for stock, (qty, cost) in portfolio.items():
        value = qty * cost
        print(f"{stock}: {qty} × ${cost} = ${value}")
        total_value += value
    print("Portfolio Total: $", total_value)

while True:
    choice = input("\nEnter a command (add / delete / show / exit): ").lower()

    if choice == "add":
        n = input("Stock name: ")
        q = int(input("Quantity: "))
        c = float(input("Cost per share: "))
        add_stock(n, q, c)
    elif choice == "delete":
        n = input("Stock name to delete: ")
        delete_stock(n)
    elif choice == "show":
        show_stocks()
    elif choice == "exit":
        print("Goodbye!")
        break
    else:
        print("Unknown command, try again.")
