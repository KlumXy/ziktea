# calculator.py
def add(a, b):
    return a + b

def subtract(a, b):
    return a - b

def multiply(a, b):
    return a * b

def divide(a, b):
    if b == 0:
        raise ValueError("Cannot divide by zero.")
    return a / b

def calculator():
    print("Welcome to Kiddo Calculator!")
    print("Choose an operation:")
    print("1. Add (+)")
    print("2. Subtract (-)")
    print("3. Multiply (*)")
    print("4. Divide (/)")
    print("5. Exit")

    while True:
        choice = input("Enter choice (1-5): ").strip()
        if choice == "5":
            print("Goodbye!")
            break
        if choice not in {"1", "2", "3", "4"}:
            print("Please enter a number from 1 to 5.")
            continue

        try:
            x = float(input("Enter first number: ").strip())
            y = float(input("Enter second number: ").strip())
        except ValueError:
            print("Oops! Use numbers only (like 2.5 or 3).")
            continue

        result = None
        try:
            if choice == "1":
                result = add(x, y)
                op = "+"
            elif choice == "2":
                result = subtract(x, y)
                op = "-"
            elif choice == "3":
                result = multiply(x, y)
                op = "*"
            elif choice == "4":
                result = divide(x, y)
                op = "/"

            print(f"{x} {op} {y} = {result}")
        except Exception as e:
            print("Error:", e)

if __name__ == "__main__":
    calculator()
