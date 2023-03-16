# Syllabus

German: *Lehrveranstaltungskonzept*. Please read it carefully at the beginning of the class, and return to it as often as necessary.

```{warning}
It is the first time I'm giving this class. The syllabus is likely change in the course of the semester, but each change will be communicated in class. 
```

## Learning outcomes

After successful completion of the course, you will:
- be able to read and write programs in the Python programming language.
- understand how to use basic programming control flows (branches and loops) and data structures (numbers and collections).
- know how to write and structure programs of several dozens of lines of code, including scripts and functions.
- be able to read commonly used data formats in atmospheric sciences (csv, NetCDF), process the data for simple analyses (averages, quality filter), and plot the results of your analyses.
- have a basic knowledge of formal code testing (pytest, asserts).
- know how to install a programming environment with appropriate additional packages on your own computer, and use it to solve common programming tasks of the atmospheric sciences. 

Most importantly: **you will be able to expand and deepen your programming skills independently**!

## Prerequisites

The targeted audience for this lecture are **students at the bachelor level without previous experience in programming**. I assume a background in atmospheric sciences (introduction lecture), with some knowledge of math and physics, and some interest for scientific analysis and number crunching!

## Organisation of the class

The class is taught in English. It is okay to ask questions in German!

This class follows the [flipped classroom](https://en.wikipedia.org/wiki/Flipped_classroom) model. You will acquire new knowledge at home by reading online materials (and watching videos when appropriate). We will then use the time together in class to discuss the materials and write code.

The semester is 15 weeks long. **Each week will always be organised as such**:
- On Wednesdays (after the assignments presentation class), you will receive instructions for the week to come (which materials to read/watch, and one homework assignment). You study them at home during the week.
- On Tuesdays (08h15-10h00), we meet for a discussion class. We will start the hour with a short, individual online assessment, for you to check if you understood the materials correctly. Based on your own assessment, you pick the topics and questions you would like to discuss in class. We work on the assignments together.
- On Wednesdays (08h15-09h00), we meet to discuss the assignment solutions (assignments are mandatory but not graded, see "Grading" below)
- New week: start again!


```{important}
The class grants you 5 ECTS if successfully passed: in theory, this represents 8 to 10 hours work per week (not including holidays). For this course, it means that you will spend at least twice as much time doing homework than sitting in class.

I strongly recommend to work regularly for the class. Programming is quite different to other disciplines, and "doing nothing for a few months" cannot be replaced by a "no-sleep-48-hours-push" at the end of semester. Programming is a bit like learning how to ski or climb: it is best learned by doing, and you will notice that regular practice will make you better each week.
```

## Grading 

The lecture will be graded based on four elements:
1. **participation to the weekly assignments** (mandatory but not graded)
1. **mid-term exam: 10%** (Tue 2023-05-02)
2. **a programming project at the end of the semester: 30%** (in group)
3. **final exam at the end of the semester: 60%** (Tue 2023-06-27)

A positive evaluation of each of these elements is mandatory to pass the class!

**Weekly assignments**

Each Wednesday, we will discuss the weekly assignment solutions together. Before the class, each student will have to upload their solution to OLAT (deadline 08h00). I will then select one or two solutions (at random) as a basis for the class discussion. This assignment is **not** graded, and it's okay (or even expected!) to make mistakes. However, it is mandatory to upload your solution each week (you have two "jokers" that you may use at your wish during the semester). You can also decide to stay anonymous if you prefer your name not to be attached to your solution during discussion. The mandatory exercises start at week 02.

**Programming project**

At the end of the semester, you will be given a programming project to realize over several weeks. Ideally, it will be a project that raises your interest: plotting climate or (live) weather data, etc. The grading will be explained once the project starts.

**Mid-term exam**

The mid-term exam (~45', OLAT-exam with presence in class) will take place on **Tue 2023-05-02 at 08:15**.

**Exam**

The final exam (~90', OLAT-exam with presence in class) will take place on **Tue 2023-06-27 at 08:15**.

**Bonus points**

There will be bonus points for anyone pointing me to typos / mistakes / broken links / incomprehensible or difficult passages in the lecture notes. [Send me an email](https://fabienmaussion.infointro) or [open an issue](https://github.com/fmaussion/intro_to_programming/issues) on GitHub!

## Weekly lesson plan 

The first half of the class will be heavily based on the "[Python for Everybody (PY4E)](https://www.py4e.com)" online textbook, which will teach us most of the fundamentals. Towards the second half of the semester, we will shift our focus towards **scientific python**, which can be seen as a special "branch" of the language.

- Week 01 (07.03.23 - 14.03.23)
    - Welcome! Motivation & syllabus
    - [Installing Python](week_01/01-Installation)
    - [PY4E: Why program](https://www.py4e.com/lessons/intro)
- Week 02 (15.03.23 - 21.03.23)
    - [PY4E: Variables, expressions and statements](https://www.py4e.com/lessons/memory)
    - [PY4E: Conditional Execution](https://www.py4e.com/lessons/logic)
    - [Using Jupyter](week_02/02-Intro-jupyter)
- Week 03 (22.03.23 - 28.03.23)
    - [Using Jupyter Notebooks](week_03/01-Intro-notebooks)
    - [PY4E: Functions](https://www.py4e.com/lessons/functions)
    - [PY4E: Loops and Iterations](https://www.py4e.com/lessons/loops)
- Week 04 (29.03.23 - Easter Break - 18.04.23)
    - [Python functions and doctests](week_04/01-documenting-functions)
    - [PY4E: Strings](https://www.py4e.com/lessons/strings)
    - [PY4E: Files](https://www.py4e.com/lessons/files)
    - [PY4E: Lists](https://www.py4e.com/lessons/lists)
 
**Mid-term exam: 02.05.2023**

- Week 05 (19.04.23 - exam learning week - 02.05.2023)
    - [Installing Packages](week_05/01-install-packages)
    - [More on jupyter notebooks](week_05/02-jupyter-dos)
    - [Introduction to numpy and matplotlib](week_05/03-numpy)
- Week 06 (03.05.23 - 09.05.23)
    - [Python tuples](week_06/01-tuples)
    - [numpy - continued: computations](week_06/02-computations)
- Week 07 (10.05.23 - 16.05.23)
    - [numpy - continued: numerics](week_07/01-numerics)
- Week 08 (17.05.23 - 23.05.23)
    - [python dictionaries](week_08/01-dictionaries)
    - [Pandas - manipulating tabular data](week_08/02-pandas)

**Start projects: 24.05.2023. Submission deadline: 13.06.2023.**
    
- Week 09 (31.05.23 - 06.06.23)
    - [numpy - continued: multi dimensional arrays](week_09/01-multidim-numpy)
- Week 10 (07.06.23 - 14.06.23)
    - [Scientific python](week_10/01-scientific-python)
    - [Recipes](cookbook/intro)
    
**Final exam: 27.06.2023**

You will notice that there are 12 weekly units for a 15 weeks long semester: this is expected since some weeks contain holidays or I am traveling. Furthermore, some weeks will be kept free to work on your projects or learn for the exams.
