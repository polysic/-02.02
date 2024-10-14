# MDK 02.02
# forms.py

import tkinter as tk

class MainForm(tk.Tk):
    def __init__(self):
        super().__init__()
        self.title("Main Form")
        self.label = tk.Label(self, text="Main Form", font=("Arial", 16))
        self.label.pack(pady=20)
        self.button = tk.Button(self, text="Go to Second Form", command=self.open_second_form)
        self.button.pack()
    def open_second_form(self):
        SecondForm(self)

class SecondForm(tk.Toplevel):
    def __init__(self, master):
        super().__init__(master)
        self.title("Second Form")
        self.label = tk.Label(self, text="Second Form", font=("Arial", 16))
        self.label.pack(pady=20)
        self.button = tk.Button(self, text="Close", command=self.destroy)
        self.button.pack()

if __name__ == "__main__":
    main_form = MainForm()
    main_form.mainloop()

