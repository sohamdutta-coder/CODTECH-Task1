import tkinter as tk
from tkinter import messagebox

def button_click(value):
    current = entry.get()
    entry.delete(0, tk.END) 
    entry.insert(0, current + value) 

# Function to evaluate the expression
def evaluate():
    try:
        result = eval(entry.get())  
        entry.delete(0, tk.END)
        entry.insert(0, str(result))
    except Exception as e:
        messagebox.showerror("Error", "Invalid Expression")

def clear():
    entry.delete(0, tk.END)

def backspace():
    current = entry.get()
    entry.delete(len(current)-1, tk.END)

# Creating the main window
root = tk.Tk()
root.title("Simple Calculator")
root.geometry("400x500")
root.config(bg="#ffffff")  # Background color


entry = tk.Entry(root, font=("Arial", 24), bg="#ffffff", fg="#000000", bd=10, relief="flat", justify="right")
entry.grid(row=0, column=0, columnspan=4, padx=20, pady=20)


button_style = {
    'font': ("Arial", 18),
    'width': 4,
    'height': 2,
    'bd': 1,
    'relief': "flat",
    'bg': "#ff8c00",  
    'fg': "#ffffff",  
    'activebackground': "#e67e00",  
    'activeforeground': "#ffffff"
}


number_button_style = {
    'font': ("Arial", 18),
    'width': 4,
    'height': 2,
    'bd': 1,
    'relief': "flat",
    'bg': "#d3d3d3",  
    'fg': "#000000",  
    'activebackground': "#a9a9a9",  
    'activeforeground': "#000000"
}

# Buttons for digits and operators
buttons = [
    ('7', 1, 0), ('8', 1, 1), ('9', 1, 2), ('/', 1, 3),
    ('4', 2, 0), ('5', 2, 1), ('6', 2, 2), ('*', 2, 3),
    ('1', 3, 0), ('2', 3, 1), ('3', 3, 2), ('-', 3, 3),
    ('0', 4, 0), ('.', 4, 1), ('+', 4, 2), ('=', 4, 3)
]


for (text, row, col) in buttons:
    if text == "=":
        button = tk.Button(root, text=text, **button_style, command=evaluate)
    elif text in ['+', '-', '*', '/', '=', '.']:
        button = tk.Button(root, text=text, **button_style, command=lambda value=text: button_click(value))
    else:
        button = tk.Button(root, text=text, **number_button_style, command=lambda value=text: button_click(value))
    button.grid(row=row, column=col, padx=5, pady=5, sticky="nsew")


clear_button = tk.Button(root, text="C", font=("Arial", 18), bg="#ff8c00", fg="#ffffff", bd=1, relief="flat", command=clear)
clear_button.grid(row=5, column=0, columnspan=2, padx=5, pady=5, sticky="nsew")

backspace_button = tk.Button(root, text="<-", font=("Arial", 18), bg="#ff8c00", fg="#ffffff", bd=1, relief="flat", command=backspace)
backspace_button.grid(row=5, column=2, columnspan=2, padx=5, pady=5, sticky="nsew")


for i in range(6):
    root.grid_rowconfigure(i, weight=1)
    root.grid_columnconfigure(i, weight=1)


root.mainloop()
