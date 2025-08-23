

def calculator():
    first_number = float(input("Enter the first number: "))
    operator = input("Enter an operator (*, -, +, /): ")
    second_number = float(input("Enter the second number: "))

    if operator == '+':
        result = first_number + second_number
    elif operator == '-':
        result = first_number - second_number
    elif operator == '*':
        result = first_number * second_number
    elif operator == '/':
        if second_number != 0:
            result = first_number / second_number
        else:
            result = "Error! Division by zero."
    else:
        result = "Invalid operator!"

    print("The result is:", result)

calculator()
