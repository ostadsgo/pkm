### Grid like widget
The problem is when we use two frames one in the above containing let say buttons and one 
in the below say entries if the default width of the widgets where equal they may appear like grid.
But if we different widgets in one row they width are different so they are not going to match with
the widgets above. 
To make widgets to match regardless of there width we use `uniform` arguement in `columnconfigure` or `rowconfigure`.

If we don't use `uniform` we must use one frame for header and data part in table example

```python
from tkinter import ttk
import tkinter as tk

row = 1
def create_row(table):
    global row
    ttk.Combobox(table).grid(row=row, column=0, sticky="we")
    ttk.Combobox(table).grid(row=row, column=1, sticky="we")
    ttk.Entry(table).grid(row=row, column=2, sticky="we")
    ttk.Entry(table).grid(row=row, column=3, sticky="we")
    row += 1

def create_header(table):
    for i in range(4):
        ttk.Button(table, text=f"Header {i+1}").grid(row=0, column=i, sticky="we")
        table.columnconfigure(i, weight=1)

def main():
    root = tk.Tk()
    root.geometry("400x300")

    table = ttk.Frame(root)
    table.grid(row=0, column=0, sticky="news")

    action = ttk.Frame(root)
    action.grid(row=1, column=0, sticky="s")

    create_header(table)
    
    table.columnconfigure(0, weight=1)
    ttk.Button(action, text="Add row", command=lambda: create_row(table)).grid(row=0, column=0)


    root.rowconfigure(0, weight=1)
    root.columnconfigure(0, weight=1)

    root.mainloop()

main()
```

### Using `uniform`
With using `uniform` every widget get the same width.
for example in row_frame every combo and entry get the same width.
Header contains buttons they are same size we don't need usin `uniform`
So `uniform` used usally in columnconfigure when we want unify widgets width.

```python
from tkinter import ttk
import tkinter as tk

row_num = 0

def header(mainframe):
    hf = ttk.Frame(mainframe)
    hf.grid(row=0, column=0, sticky="we")
    checkbutton = ttk.Checkbutton(hf)
    checkbutton.grid(row=0, column=0)
    for i in range(1, 9):
        ttk.Button(hf, text="Header" + str(i)).grid(row=0, column=i, sticky="we")
        hf.columnconfigure(i, weight=1)

def data(mainframe):
    df = ttk.Frame(mainframe)
    df.grid(row=1, column=0, sticky="news")
    df.columnconfigure(0, weight=1)
    for i in range(1, 9):
        df.columnconfigure(i, weight=1, uniform="a")  # Configure columns for the data frame
    return df

def create_row(df):
    global row_num
    row_frame = ttk.Frame(df)
    row_frame.grid(row=row_num, column=0, sticky="we")
    row_num += 1  # Corrected to increment the row_num
    checkbutton = ttk.Checkbutton(row_frame)
    checkbutton.grid(row=0, column=0)
    for i in range(1, 9):
        if i > 5:
            ttk.Entry(row_frame).grid(row=0, column=i, sticky="we")
        else:
            ttk.Combobox(row_frame).grid(row=0, column=i, sticky="we")

        row_frame.columnconfigure(i, weight=1, uniform="a")  # Configure columns for the row frame

def mainframe(root):
    mf = ttk.Frame(root, padding=5, relief="sunken")
    mf.grid(row=0, column=0, padx=5, pady=5, sticky="news")

    mf.rowconfigure(0, weight=1)
    mf.rowconfigure(1, weight=99)
    mf.columnconfigure(0, weight=1)

    # Header
    header(mf)

    # Data
    df = data(mf)

    ttk.Button(mf, text="Click", command=lambda: create_row(df)).grid(row=2, column=0)

def app():
    root = tk.Tk()
    root.geometry("700x400")

    # mainframe
    mainframe(root)

    root.rowconfigure(0, weight=1)
    root.columnconfigure(0, weight=1)

    root.mainloop()

app()

