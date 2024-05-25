import tkinter as tk
from tkinter import messagebox
import datetime

def submit_form():
    username = entry_username.get().strip()
    password = entry_password.get()
    confirm_password = entry_confirm_password.get()
    email = entry_email.get().strip()
    date_of_birth = entry_date_of_birth.get().strip()

    
    if not username:
        messagebox.showerror("Error", "Username is required")
        return
    if len(password) < 8:
        messagebox.showerror("Error", "Password must be at least 8 characters")
        return
    if password != confirm_password:
        messagebox.showerror("Error", "Passwords do not match")
        return
    if "@" not in email or "." not in email:
        messagebox.showerror("Error", "Enter a valid email address")
        return
    if not valid_date(date_of_birth):
        messagebox.showerror("Error", "Enter a valid date in format YYYY-MM-DD")
        return
    
    
    messagebox.showinfo("Success", "Registration successful!")
    window.destroy()

def valid_date(date_str):
    try:
        datetime.datetime.strptime(date_str, '%Y-%m-%d')
        return True
    except ValueError:
        return False

window = tk.Tk()
window.title("Registration Form")
window.geometry('700x800')


frame = tk.Frame(window)
frame.pack(padx=10, pady=10)

label_username = tk.Label(frame, text="Username:")
label_username.grid(row=0, column=0, sticky="w")
entry_username = tk.Entry(frame, width=30)
entry_username.grid(row=0, column=1)

label_password = tk.Label(frame, text="Password:")
label_password.grid(row=1, column=0, sticky="w")
entry_password = tk.Entry(frame, width=30, show="*")
entry_password.grid(row=1, column=1)

label_confirm_password = tk.Label(frame, text="Confirm Password:")
label_confirm_password.grid(row=2, column=0, sticky="w")
entry_confirm_password = tk.Entry(frame, width=30, show="*")
entry_confirm_password.grid(row=2, column=1)

label_email = tk.Label(frame, text="Email:")
label_email.grid(row=3, column=0, sticky="w")
entry_email = tk.Entry(frame, width=30)
entry_email.grid(row=3, column=1)

label_date_of_birth = tk.Label(frame, text="Date of Birth (YYYY-MM-DD):")
label_date_of_birth.grid(row=4, column=0, sticky="w")
entry_date_of_birth = tk.Entry(frame, width=30)
entry_date_of_birth.grid(row=4, column=1)

submit_button = tk.Button(frame, text="Submit", command=submit_form)
submit_button.grid(row=5, column=0, columnspan=2)

window.mainloop()
