
# 6-To-Do-List-Tkinter-GUI-
from tkinter import *

# Create window
root = Tk()
root.title("To-Do List")
root.geometry("400x500")

# Functions
def add_task():
    task = task_entry.get()

    if task != "":
        task_listbox.insert(END, task)
        task_entry.delete(0, END)

def delete_task():
    selected = task_listbox.curselection()

    if selected:
        task_listbox.delete(selected)

# Heading
heading = Label(root, text="To-Do List App", font=("Arial", 20, "bold"))
heading.pack(pady=10)

# Entry box
task_entry = Entry(root, width=30, font=("Arial", 14))
task_entry.pack(pady=10)

# Add button
add_button = Button(root, text="Add Task", width=15, command=add_task)
add_button.pack(pady=5)

# Delete button
delete_button = Button(root, text="Delete Task", width=15, command=delete_task)
delete_button.pack(pady=5)

# Listbox
task_listbox = Listbox(root, width=40, height=15, font=("Arial", 12))
task_listbox.pack(pady=20)

# Intern ID label
intern_label = Label(root, text="Intern ID: CITS1138", font=("Arial", 10))
intern_label.pack(side=BOTTOM, pady=10)

# Run app
root.mainloop()
