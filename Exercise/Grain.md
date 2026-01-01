https://exercism.org/tracks/python/exercises/grains

### My approach
----
```python
def square(n):
    if n not in range(1, 65):
        raise ValueError("square must be between 1 and 64")

    return 2 ** (n - 1)


def total():
    return sum(square(n) for n in range(1, 65)) 
```

### Approach: Exponentiation
```python
def square(number): 
	if number < 1 or number > 64: 
		raise ValueError('square must be between 1 and 64') 
	return 2 ** (number - 1)
	
def total(): 
	return 2 ** 64 - 1
```

### Approach: Bit-shifting
```python
def square(number): 
	if number < 1 or number > 64: 
		raise ValueError('square must be between 1 and 64') 
	return 1 << number - 1 
	
def total(): 
	return (1 << 64) - 1
```

