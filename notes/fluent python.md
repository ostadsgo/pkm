### intro
This book is not an A-to-Z exhaustive reference of Python. Its emphasis is on the lan‐
guage features that are either unique to Python or not found in many other popular
languages. This is also mostly a book about the core language and some of its libra‐
ries. 

### ch01
Python Data Model, and it is the API
that we use to make our own objects play well with the most idiomatic language
features.

You can think of the data model as a description of Python as a framework. It formal‐
izes the interfaces of the building blocks of the language itself, such as sequences,
functions, iterators, coroutines, classes, context managers, and so on.

Users of your classes don’t have to memorize arbitrary method names for stan‐
dard operations. (“How to get the number of items? Is it .size(), .length(), or
what?”)

Just by implementing the __getitem__ special method, our deck is also iterable:

Because our __getitem__ delegates to the [] operator of self._cards, our deck
automatically supports slicing. 

Iteration is often implicit. If a collection has no __contains__ method, the in opera‐
tor does a sequential scan. Case in point: in works with our FrenchDeck class because
it is iterable.