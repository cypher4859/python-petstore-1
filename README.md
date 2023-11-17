# Python PetStore Exercise 1

## Goals
- Create the base classes for the store.
- Interact with the classes by making some objects and running basic logic on them.
- Learn how to make a console app wait for certain input before exiting a loop.

## Instructions
1. Clone this repo. Ensure that you have a `main.py` that contains an empty `main()`.
1. Add the entrypoint for running your `main.py` by adding the following to the bottom of the file: 
    ```py
    if __name__ == "__main__":
        main()
    ```
1. Add a class to your project called `Product`. You can add it directly into the `main.py` file if you want to; remember it needs to be outside of `main()`. This class will be what's called a _base_ class or a _parent_ class.  This will be the most basic class that all product classes will inherit from. Ref: [Python docs on classes](https://docs.python.org/3/tutorial/classes.html#a-first-look-at-classes)
1. Add a constructor to your `Product` class by creating a method inside called `__init__` by doing: `def __init__(self):`.
    * Note: Remember that `self` must be the first parameter for your constructor. This allows the single instance to reference it's own variables and methods, i.e. "When one cat meows, not all cats meow."
1. Add the following parameters to your `__init__()` constructor:
   - name - Type `str`
   - price - Type `float`
   - quantity - Type `int`
   - description - Type `str`
   Example is as follows:
   ```py
   def foo(bar1: str, bar2: float, bar3: int):
        ...
   ```
1. Inside your `__init__()` constructor please assign the passed arguments to instance variables; this will make sure the arguments you pass in are available in the instance:
    ```py
    def foo(bar1: str, bar2: float, ...):
        self.bar1 = bar1
        ...
    ```
1. Add another class called `CatFood`.  Make this class _inherit_ from the base class `Product`. Example:
    ```py
    # FooClass inherits from BarClass
    class FooClass(BarClass):
        ...
    ```
1. Please give `CatFood` a few _Properties_. You can do so by following the same process of building a constructor `__init__()` inside of `CatFood` and assigning it's arguments to instance variables as you did with `Product`.
   - WeightPounds - Type `float`
   - KittenFood- Type `bool`
1. Make another class called `DogLeash` and have it inherit from `Product` as well. Give it a the following _Properties_ 
   - LengthInches - Type `int`
   - Material - Type `str`

### Looping
Now we want to get this app to run until the user decides to end it.  We will do this by using a `while` loop.  Loops require 3 things: an inital condition, check in condition, and a change in condition.  Our inital condition is going to be our first input from the user.  Our check is what is in the while loop.  Our change is going to be what the user inputs after an action has been complete.  So, let's get started with the initial condition.
1. Inside our `main()` in `main.py`, add the following lines: `print("Press 1 to add a product")` and below that add `print"Type 'exit' to quit")`.
1. Add this line of code directly below your `print()` lines: `userInput = str(input("Option: "))`.  This will get what the user enters before hitting enter.
1. Now add your while loop which typically in the form of `while( <some conditional expression> )`, e.g. `while(some_variable < 5)`.  The condition in the loop should be something like this: `userInput.lower() != "exit"`.  We use the method `lower()` just in case the user enters "Exit" instead of "exit".
1. Inside the body of the while loop, at the bottom of the loop, add this line `userInput = str(input("Option: "))`. This is our change in condition.  We will add code before this though, so it will make more sense after that. Add the instructions for the console app above that line again: `print("Press 1 to add a product")` and `print("Type 'exit' to quit")`. 
1. Inside of the while loop, above the latest `print()` and `input()` lines you added in the previous step, add an `if` statement.  This if statment will check the input of the user a second time to see if they wanted to add a product. We told them to enter "1" to add a product, so check for that in the if statment.  Remember, the input is a `str` type, not an `int`.
1. Create a new object.  It should be `CatFood` or `DogLeash`, not the base class `Product`. Ref: [An example code snippet on making classes & objects](https://docs.python.org/3/tutorial/classes.html#class-objects)
1. Since we don't really have a database, when we add a product, we're going to just create that object and print it to the console.  Use `print()` and `input()` to get data from the user and then add it to the object you just created.
1. To make printing the object easier, we'll use `json.dumps()` and `print()`. You don't need to know all the ins and outs of how this works right now, but basically it will just convert our object to a json object.  Add the following line to your code: `print(json.dumps(dogLeash))`.  You will replace `dogLeash` with whatever you named your object.
1. Now, all you have to do is test it!  Run the application and see if everything works properly.