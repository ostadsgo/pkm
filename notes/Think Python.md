A statement is a unit of code that has an
effect, but no value. 

When you call a function, the expression in parentheses is called an argument. Normally I would explain why, but in this case the technical meaning of a term has
almost nothing to do with the common meaning of the word, so I won’t even try.

Good variable names can reduce the need for comments, but long names can make
complex expressions hard to read, so there is a trade-off

Three kinds of **errors** can occur in a program: **syntax** errors, **runtime** errors, and
**semantic** errors
runtime errors also called **exceptions**
The third type of error is “semantic,” which means related to meaning.

The first line of the function definition is called the header—the rest is called the
body.

Defining a function creates a function object

When it gets to the end of the body, it loops back around to the header, which is why
this statement is called a loop.

Wrapping a piece of code up in a function is called encapsulation. 

Adding a parameter to a function is called generalization because it makes the func‐
tion more general

These are sometimes called “named arguments” because they include the parameter
names. But in Python they are more often called keyword arguments

This use of the assignment operator, =, is a reminder about how arguments and
parameters work—when you call a function, the arguments are assigned to the
parameters.

Changes like this, which improve the code without changing its behavior, are
called refactoring.

A development plan is a process for writing programs. The process we used in this
chapter is “encapsulation and generalization.” The steps of this process are:

A Development Plan
A development plan is a process for writing programs. The process we used in this
chapter is “encapsulation and generalization.” The steps of this process are:
1. Start by writing a small program with no function definitions.
2. Once you get the program working, identify a coherent piece of it, encapsulate
the piece in a function, and give it a name. Copy and paste working code to avoid
retyping (and re-debugging).
1. Generalize the function by adding appropriate parameters.
2. Repeat steps 1 through 3 until you have a set of working functions.
3. Look for opportunities to improve the program by refactoring. For example, if
you have similar code in several places, consider factoring it into an appropriately
general function.

The design of a function has two parts:
interface
How the function is used, including its name, the parameters it takes, and what
the function is supposed to do
implementation
How the function does what it’s supposed to do

‍‍‍‍‍These two functions have the same interface—they take the same parameters and do
the same thing—but they have different implementations.

```python
def circle(radius):
	circumference = 2 * math.pi * radius
	n = 30
	length = circumference / n
	polygon(n, length)

def circle(radius):
	arc(radius, 360)
```

An interface is like a contract between a function and a caller. The caller agrees to
provide certain arguments and the function agrees to do certain work.

These requirements are called preconditions because they are supposed to be true
before the function starts executing. Conversely, conditions at the end of the function
are postconditions. Postconditions include the intended effect of the function (like
drawing line segments) and any side effects (like moving the turtle or making other
changes).
Preconditions are the responsibility of the caller. If the caller violates a precondition
and the function doesn’t work correctly, the bug is in the caller, not the function.
If the preconditions are satisfied and the postconditions are not, the bug is in the
function. If your pre- and postconditions are clear, they can help with debugging.


