## تغییر نوع داده ای Mutable
در صورتی که متدی در نوع داده ای Mutable ساختار داده را تغییر دهد نتیجه برگشت داده نشده و None برگشت داده می شود. این یک تصمیم گیری طراحی در پایتون هست.
```python
numbers = [1, 2, 3]
r = numbers.append(4)
print(r) # None

```

به جای استفاده از جملات پیچیده بهتر هست از توابع توکار استفاده شود
```python
transposed = []
for i in range(4):
    # the following 3 lines implement the nested listcomp
    transposed_row = []
    for row in matrix:
        transposed_row.append(row[i])
    transposed.append(transposed_row)

# or
[row[i] for row in matrix] for i in range(4)]

# use this
list(zip(*matrix))
```

با استفاده از متد remove می توان یک عنصر را بر اساس محتوای آن حذف کرد و با استفاده از دستور del می توان یک عنصر را بر اساس شماره ایندکس آن حذف کرد.
