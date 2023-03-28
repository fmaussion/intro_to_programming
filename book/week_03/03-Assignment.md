# Assignment 03

*Due date: 29.03.2023*


```{important}

This week's assignment has to be returned in the form of one (1) python script **OR** one (1) jupyter notebook. Don't forget the [instructions](../assignments)!

- Exercise 1 and Exercise 2 are independent from one another. 
- Exercise 3 uses the functions you wrote in Exercise 1 and 2 in a small program.
```

## Exercise 1: write two temperature conversion functions

Write a function called `fahrenheit_to_celsius`, which accepts a `float` or `int` as **input parameter** and returns the temperature value converted to degrees celsius. Here are some examples of the function's execution:

```python
print(fahrenheit_to_celsius(100))
37.77777777777778
```

```python
print(fahrenheit_to_celsius(68))
20.0
```

Now, write a second function called `celsius_to_fahrenheit`, which does the opposite. Here are some examples:

```python
print(celsius_to_fahrenheit(38))
100.4
```

```python
print(celsius_to_fahrenheit(0))
32.0
```

```{important}

A few things to note here:
- these functions are **fruitful functions**: they returns a value
- these functions **do not print anything**: there is no `print` statement in these functions
- these functions have one input parameter only

If you are unsure about what I mean with "fruitful" or "input parameter", go back to the [lecture notes](https://www.py4e.com/html3/04-functions).

```

## Exercise 2: write two user input checking functions

Write a new function with the following signature:

```python
def valid_temperature_input(min_value):
    <your code here>
    return number
```

This function uses python's `input` to ask for the temperature value to convert, and then decides:
- if the value can be converted to a number and this number is above the parameter `min_value`, return this number
- if the value cannot be converted to a number or is below the specified limit print a message to the user and ask them to enter a new value.
- this program never ends until a valid value is entered.

Examples:

```none
print(valid_temperature_input(0))
Please enter a temperature value: 10
10.0
```

```none
print(valid_temperature_input(0))
Please enter a temperature value: ups
This value is not valid! Try again.
Please enter a temperature value: -2
This value is below the specified limit! Try again.
Please enter a temperature value: 12.3
12.3
```

Now, write a second input function with the following signature:

```python
def valid_conversion_input():
    <your code here>
    return number
```

This function asks the user what kind of conversion they want to do, and validates the input (if needed, asking again if the value is not correct). Examples:


```none
print(valid_conversion_input())
What conversion do you want to do? Type:
1 for Celsius to Farenheit
2 for Farenheit to Celsius
3 for doing nothing
Your input: 1
1
```

```none
print(valid_conversion_input())
What conversion do you want to do? Type:
1 for Celsius to Farenheit
2 for Farenheit to Celsius
3 for doing nothing
Your input: 3
3
```

```none
print(valid_conversion_input())
What conversion do you want to do? Type:
1 for Celsius to Farenheit
2 for Farenheit to Celsius
3 for doing nothing
Your input: ups
Not valid! Try again.
Your input: 4
Not valid! Try again.
Your input: 2
2
```

The function always returns one of 1, 2, 3 and never ends until the user gives a valid input.


```{important}

A few things to note here:
- these functions are **fruitful functions**: they returns a value
- these functions **do print something**: there are `print` statements in these functions
- these functions have **no input parameter**. 
- these functions use `input()` internally.

If you are unsure about what I mean with "fruitful" or "input parameter", go back to the [lecture notes](https://www.py4e.com/html3/04-functions).

```

## Exercise 3: write a temperature conversion program

Now, **rely on your hard work and the functions you just created to write a full program** (in a python file or a notebook). The program:
- asks the user what they want to do (convert or do nothing)
- if convert, ask the user for the value to convert. The minimum acceptable value depends on the conversion function to use (indeed, the value in °C or °F cannot be below the absolute minimum, 0 Kelvin)
- convert the value to the other unit and print it on screen

**This program should use the functions you wrote in exercise 1 and 2**, and therefore have only little code other than calling the functions.

Example output for a °C to °F conversion:

```none
0°C are converted to 32.0°F
```

## Exercise 4 (optional): design a test function

In addition to your program, write a function called `test_conversion()` with no arguments, and no output (a *void function* in the book).

When run, this function checks that some given values are converted properly. You can pick a few examples from [this table](https://www.rapidtables.com/convert/temperature/celsius-to-fahrenheit.html) here. If the value is not the expected one, print a message saying that there is a problem.

Furthermore, the function should check that for **10** random numbers selected between 0 and 100, the following test is True:

```python
value = 89.2  # or any random number
output = celsius_to_fahrenheit(fahrenheit_to_celsius(value))
value == output  # Should be true
```

**Important:** if you run these tests often enough, you will see that they do not always pass!!! Actually, they fail quite often. Don't panic and accept it: the reason for this problem (and how to overcome it) will be explained later.
