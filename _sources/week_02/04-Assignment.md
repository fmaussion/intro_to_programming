# Assignment 02

*Due date: 23.03.2022*

This week's assignment has to be returned in the form of two python scripts. Have a look at the [instructions](../assignments) first!

## Exercise 1 

Write a program that uses `input` to prompt a user for their name and preferred language, and then welcomes them. 

```none
Enter your name: Sophie
Enter your language: FR
Bonjour Sophie!
```

The allowed languages are `EN` (English), `DE` (German), `FR` (French), and a fourth language of your choice. 
If the language is not one of these three options, the program should print an error message and exit.


## Exercise 2 

Write a program that computes the probability of fog according to user input. The user first has to
enter the relative humidity (a number between 0 and 100), and then, depending on the situation,
the user will be asked in what season the prediction needs to be made.

The rules of fog formation are pretty simple:
- if relative humidity is below 50%, then the probability of fog is 1%
- if relative humidity is above or equal 50%, then the probability of fog depends on the season:
    - in summer, the probability of fog is equal to the relative humidity divided by 10
    - in winter, the probability of fog is equal to the relative humidity divided by 2

If the relative humidity is not between 0 and 100, or not a number, then the program should print a message and exit.

Here are a few examples of program execution:

```none
Enter the relative humidity: 30
The probability of fog is: 1%
```

```none
Enter the relative humidity: 51
What is the season? (winter or summer): winter
The probability of fog is: 26%
```

```none
Enter the relative humidity: 91
What is the season? (winter or summer): summer
The probability of fog is: 9%
```

```none
Enter the relative humidity: 101
The entered value is not valid.
```

```none
Enter the relative humidity: ups
The entered value is not valid.
```

**Tip:** to convert your computed probability number to a string, please use the following command: `str(round(number))`. 
This command starts by rounding the number with `round()` then converts the output to a string with `str()`.
