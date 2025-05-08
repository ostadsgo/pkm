what options are exists in a ttk.Style for a widget how we find out of it?
using `style.layout` method

```python
style = ttk.Style()
# TFrame is example it could be TButton, TLabel, ect.
style.layout("TFrame")
```

How we find class name of the widget?
using `widget.winfo_class()`

```python
b = ttk.Button(root, text="hello")
b.pack()

b.winfo_class()
# TButton
```

Also we can use `style.lookup(widget, style)` to find out if a style support by the 
widget or not

```python 
style = ttk.Style()
style.lookup("TFrame", "padding")
#=> ''  : which mean padding doesn't support by frame
```


