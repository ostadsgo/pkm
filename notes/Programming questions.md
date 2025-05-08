1. How many seconds are there in 42 minutes 42 seconds?
2. How many miles are there in 10 kilometers? Hint: there are 1.61 kilometers in a
mile.
3. If you run a 10 kilometer race in 42 minutes 42 seconds, what is your average
pace in seconds per mile?
4. What is your average pace in minutes and seconds per mile?
5. What is your average speed in miles per hour?

1
``` python
seconds = 42 * 60 + 42
```

2
```python
km = 10
mile = km / 1.61
```

3
```python
ave_sec = seconds / mile  # 412.482
# every 412 second ran a mile
```

4
```python
minutes = ave_sec / 60
seconds = ave_sec % 60
# each mile 6 minute 52 seconds
```

5
```python
an_hour_sec = 60 * 60
mile_per_h = an_hour_sec / ave_sec
# 8.73 miles
```