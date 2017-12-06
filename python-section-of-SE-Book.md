# Python
## PitFalls of Python
It is important to first note the pitfalls that the language Python has. 

- Do not use == for None checking. Use "is" instead "if val isn't None".


You need to understand swallow/deep copy.
- avoid "a = b = c" because when one is modified, then the others will be modified as well. To remedy this, invoke a deepcopy function.

There are no keywords such as private, final, constant
- You can't prevent other's access or changes to objects.

Be careful misuing expressions as defaults for function arguments.
Say we have this code.
-  def foo(bar=[]):        # bar is optional and defaults to [] if not specified
- bar.append("hello")    # but this line could be problematic, as we'll see...
- return bar
And then we call foo() over and over again. Say we run it 3 times. It would end up being: ["hello"] after first call, ["hello", "hello"] after second, and then ["hello", "hello", "hello"]. We would've thought that it would've just created a new list each time, because we thought that it would default each time since we didn't pass any arguments. But, in python, the default value for a function argument is only evaluated once, at the time that the function is defined. This is where we would add in the "if bar is None:" case, to fix this. 

Python is also very very slow. 

## Structure of Python
Python follows the Lisp idea of the traidional core & library structure. The core written in C, is open sourced. Python also has its own parsing system. The majority of the Python libraries are written in Python.
If 3rd party libraries are being used with Python then the problem becomes more complex. To remedy this, a virtual environment (VirtualEnv) is used so that the 3rd party libraries are separated and not contaminating other libraries. For example, in our Wiki project we need virtualenv because Flask is being used, and Flask would contaminate the other directories if not used with virtualenv.


## Decorators
Decorators can be used to wrap a function, thereby modifying its behavior. They are a way for us to more conviently alter functions and methods. 

## My Experiences with Python
In our Software Engineering class this semester we were tasked with creating a wiki system that combined the powers of WTF-flask, Jinja2 and Python. We quickly learned how complex things were able to become. I think part of the reason is because we were pretty much reverse engineering the whole thing.. 
