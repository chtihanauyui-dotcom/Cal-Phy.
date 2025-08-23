import tkinter as tk


def calculate(operation):
    global current_input
    if operation == "C":
        current_input = ""
    elif operation == "=":
        try:
            current_input = str(eval(current_input))
        except Exception as e:
            current_input = "Error"
    else:
        current_input += str(operation)
    display_var.set(current_input)


root = tk.Tk()
root.title("Simple Calculator")


current_input = ""


display_var = tk.StringVar()
display = tk.Entry(root, textvariable=display_var, font=('Arial', 24), borderwidth=5, relief="ridge")
display.grid(row=0, column=0, columnspan=4)


buttons = [
    'C', '/', '*', '7',
    '8', '9', '-', '4',
    '5', '6', '+', '1',
    '2', '3', '0', '.',
    '=',
]

row_val = 1
col_val = 0
for button in buttons:
    b = tk.Button(root, text=button, font=('Arial', 18), command=lambda b=button: calculate(b))
    b.grid(row=row_val, column=col_val, sticky="nsew", ipadx=10, ipady=10, padx=5, pady=5)
    col_val += 1
    if col_val > 3:
        col_val = 0
        row_val += 1


for i in range(5):
    root.grid_rowconfigure(i, weight=1)
    root.grid_columnconfigure(i, weight=1)


root.mainloop()
