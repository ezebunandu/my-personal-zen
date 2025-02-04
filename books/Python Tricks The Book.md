# Python Tricks The Book
- The with statement can make code that deals with system resources more readable. It also helps you avoid bugs or leaks by making it practically impossible to forget to clean up or release a resource when it’s no longer needed.
- That’s why the with statement is so useful. It makes properly acquiring and releasing resources a breeze.
- The underscore prefix is meant as a hint to tell another programmer that a variable or method starting with a single underscore is intended for internal use. This
- The underscore prefix is meant as a hint to tell another programmer that a variable or method starting with a single underscore is intended for internal use.
- Single underscores are a Python naming convention that indicates a name is meant for internal use. It is generally not enforced by the Python interpreter and is only meant as a hint to the programmer
- Sometimes the most fitting name for a variable is already taken by a keyword in the Python language. Therefore, names like class or def cannot be used as variable names in Python. In this case, you can append a single underscore to break the naming conflict:
- In summary, a single trailing underscore (postfix) is used by convention to avoid naming conflicts with Python keywords. This convention is defined and explained in PEP 8.
- names that have both leading and trailing double underscores are reserved for special use in the language. This rule covers things like __init__ for object constructors, or __call__ to make objects callable.
- the best use case for template strings is when you’re handling format strings generated by users of your program. Due to their reduced complexity, template strings are a safer choice
- The more complex formatting mini-languages of other string formatting techniques might introduce security vulnerabilities to your programs. For example, it’s possible for format strings to access arbitrary variables in your program.
- Errors should never pass silently.
- A variable pointing to a function and the function itself are really two separate concerns.
- The ability to pass function objects as arguments to other functions is powerful. It allows you to abstract away and pass around behavior in your programs.
- Functions that can accept other functions as arguments are also called higher-order functions. They are a necessity for the functional programming style.
- Functions that do this are called lexical closures (or just closures, for short). A closure remembers the values from its enclosing lexical scope even when the program flow is no longer in that scope.
- What’s a lexical closure? It’s just a fancy name for a function that remembers the values from the enclosing lexical scope even when the program flow is no longer in that scope.
- Lambda functions should be used sparingly and with extraordinary care.
- closures and decorators are some of the most difficult concepts to understand in Python.
- I’d recommend that you use functools.wraps in all of the decorators you write yourself.
- The @ syntax is just a shorthand for calling the decorator on an input function. Multiple decorators on a single function are applied bottom to top (decorator stacking).
- *args collects extra positional arguments as a tuple. **kwargs collects the extra keyword arguments as a dictionary.
- Putting a * before an iterable in a function call will unpack it and pass its elements as separate positional arguments to the called function.
- This technique works for any iterable, including generator expressions. Using the * operator on a generator consumes all elements from the generator and passes them to the function:
- This happened because there are actually two dunder methods that control how objects are converted to strings in Python 3. The first one is __str__, and you just learned about it. The second one is __repr__, and the way it works is similar to __str__, but it is used in different situations.
- calling the parameters args and kwargs is simply a naming convention. The previous example would work just as well if you called them *parms and **argv. The actual syntax is just the asterisk (*) or double asterisk (**), respectively.
- you can use it to extend the behavior of a parent class without having to replicate the full signature of its constructor in the child class.
- if a function doesn’t specify a return value, it returns None by default.
- the proper use of assertions is to inform developers about unrecoverable errors in a program. Assertions are not intended to signal expected error conditions, like a File-Not-Found error, where a user can take corrective actions or just try again.
- Python’s assert statement is a debugging aid, not a mechanism for handling run-time errors. The goal of using assertions is to let developers find the likely root cause of a bug more quickly. An assertion error should never be raised unless there’s a bug in your program
- it becomes extremely dangerous to use assert statements as a quick and easy way to validate input data.
- Don't use assert statements to validate input data.
- never use assertions to do data validation. Instead, we could do our validation with regular if-statements and raise validation exceptions if necessary
- Most source control systems are line-based and have a hard time highlighting multiple changes to a single line.
- In Python, you can place a comma after every item in a list, dict, or set constant, including the last item. That way, you can just remember to always end your lines with a comma and thus avoid the comma placement juggling that would otherwise be required.
- a with statement allows you to abstract away most of the resource handling logic.
- all you need to do is add __enter__ and __exit__ methods to an object if you want it to function as a context manager
- wildcard imports should be avoided as they make it unclear which names are present in the namespace
- A double underscore prefix causes the Python interpreter to rewrite the attribute name in order to avoid naming conflicts in subclasses.
- Name mangling affects all names that start with two underscore characters (“dunders”) in a class context
- Sometimes the most important skills for a programmer are “pattern recognition” and knowing where to look things up. If you feel a little overwhelmed at this point, don’t worry.
- Sometimes the most important skills for a programmer are “pattern recognition” and knowing where to look things up
- name mangling is not applied if a name starts and ends with double underscores. Variables surrounded by a double underscore prefix and postfix are left unscathed by the Python interpreter:
- Behind the scenes, formatted string literals are a Python parser feature that converts f-strings into a series of string constants and expressions. They then get joined up to build the final
- Python’s functions are first-class objects. You can assign them to variables, store them in data structures, pass them as arguments to other functions, and even return them as values from other functions
- Because functions are objects, you can pass them as arguments to other functions.
- In practical terms, this means not only can functions return behaviors but they can also pre-configure those behaviors.
- Everything in Python is an object, including functions. You can assign them to variables, store them in data structures, and pass or return them to and from other functions (first-class functions.)
- Executing a lambda function evaluates its expression and then automatically returns the expression’s result, so there’s always an implicit return statement.
- Python’s decorators allow you to extend and modify the behavior of a callable (functions, methods, and classes) without permanently modifying the callable itself.
- Any sufficiently generic functionality you can tack on to an existing class or function’s behavior makes a great use case for decoration
- Functions can be defined inside other functions—and a child function can capture the parent function’s local state (lexical closures)
- Decorators allow you to define reusable building blocks that can change or extend the behavior of other functions
- Decorators allow you to define reusable building blocks that can change or extend the behavior of other functions. And, they let you do that without permanently modifying the wrapped function itself. The function’s behavior changes only when it’s decorated.
- So what’s the with statement good for? It helps simplify some common resource management patterns by abstracting their functionality and allowing them to be factored out and reused.
- All data in a Python program is represented by objects or relations between objects.1 Things like strings, lists, modules, and functions are all objects. There’s nothing particularly special about functions in Python. They’re also just objects.
- This means not only can functions accept behaviors through arguments but they can also return behaviors. How cool is that?
- Not only can functions return other functions, these inner functions can also capture and carry some of the parent function’s state with
- Not only can functions return other functions, these inner functions can also capture and carry some of the parent function’s state with them.
- Objects aren’t functions. But they can be made callable, which allows you to treat them like functions in many cases.
- Using the @ syntax is just syntactic sugar and a shortcut for this commonly used pattern.
- Note that using the @ syntax decorates the function immediately at definition time. This makes it difficult to access the undecorated original without brittle hacks. Therefore you might choose to decorate some functions manually in order to retain the ability to call the undecorated function as well.
- When it comes to writing clean and maintainable code, surprising behavior is rarely a good sign.
- The == operator compares by checking for equality
- The is operator, however, compares identities
- Python is telling us that c and a are pointing to two different objects, even though their contents might be the same.
- __str__ is one of Python’s “dunder” (double-underscore) methods and gets called when you try to convert an object into a string through the various means that are available
- inspecting an object in a Python interpreter session simply prints the result of the object’s __repr__.
- With __repr__, the idea is that its result should be, above all, unambiguous. The resulting string is intended more as a debugging aid for developers. And for that it needs to be as explicit as possible about what this object is
- always add at least a __repr__ method to your classes
- if key order is important for your algorithm to work, it’s best to communicate this clearly by explicitly using the OrderedDict class.
- The defaultdict class is another dictionary subclass that accepts a callable in its constructor whose return value will be used if a requested
- The defaultdict class is another dictionary subclass that accepts a callable in its constructor whose return value will be used if a requested key cannot be found.5 This can save you some typing and make the programmer’s intentions more clear, as compared to using the get() methods or catching a KeyError exception in regular dictionaries. >>> from collections import defaultdict >>> dd = defaultdict(list) # Accessing a missing key creates it and # initializes it using the default factory, # i.e. list() in this example: >>> dd['dogs'].append('Rufus') >>> dd['dogs'].append('Kathrin') >>> dd['dogs'].append('Mr Sniffles') >>> dd['dogs'] ['Rufus', 'Kathrin', 'Mr Sniffles'] 5.1.4 collections.ChainMap – Search Multiple Dictionaries as a Single Mapping The collections.ChainMap data structure groups multiple dictionaries into a single mapping.6 Lookups search the underlying mappings one by one until a key is found. Insertions, updates, and deletions only affect the first mapping added to the chain. >>> from collections import ChainMap >>> dict1 = {'one': 1, 'two': 2} >>> dict2 = {'three': 3, 'four': 4}
- The defaultdict class is another dictionary subclass that accepts a callable in its constructor whose return value will be used if a requested key cannot be found
- all elements in a tuple must be defined at creation time.
- Arrays created with the array.array class are mutable and behave similarly to lists, except for one important difference—they are “typed arrays” constrained to a single data type
- Python’s iterator protocol: Objects that support the __iter__ and __next__ dunder methods automatically work with for-in loops.
