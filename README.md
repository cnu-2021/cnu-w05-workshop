# Week 5 workshop: Code review

This week, you will be practising your code review skills in small groups.

The examples below focus on specific aspects of writing "good code". Review them as a group; then, when you have finished, review **each other's submissions for CR1**.

## Code comments

Code comments are **essential**, not only if other people read your code (to help them understand what you are doing), but also for yourself! When coming back to a piece of code, even after just a few days, it can be surprisingly difficult to remember what you were doing by just reading the code -- having comments annotating your script is immensely helpful.

From now on, all your work for this course (and beyond!) must be sufficiently commented. This means that any step in your code that is not trivial should be **explained** (not simply *described!*) by a brief code comment.

🚩 Consider the code example below. Are the comments useful for you to understand how the code works? If not, what is the problem, and how would you improve them?

```python
def fibonacci(n):
    '''
    Returns the Fibonacci sequence up to xn,
    starting with x0 = 1, x1 = 1, as a list.
    '''
    # Set x as [1, 1]
    x = [1, 1]
    
    # Loop over a range from 0 to n-2
    for i in range(n-1):
        # Append x[i] + x[i+1] to the list x
        x.append(x[i] + x[i+1])
    
    # Return x
    return x

# Display fibonacci(5)
print(fibonacci(5))
```

## Code style

Generally, the structure, variable name, spacing, and commenting choices are referred to as the **style** of your code. Style is important for code readability, and for consistency when working as part of a team. You may wish to take a look at different style guides, such as e.g. [the official guide for Python developers](https://www.python.org/dev/peps/pep-0008).

For the purpose of this course, don't worry too much about following these guidelines too strictly. The important points to take away is that your code should aim to be **easily readable**, and **consistently styled**.

### Whitespace

One particular practice I would recommend to adhere to is featured in the [Whitespace in Expressions and Statements](https://www.python.org/dev/peps/pep-0008/#whitespace-in-expressions-and-statements) section of PEP-8. To summarise it:

```python
import numpy as np

#Some not very easily readable code...
a=(np.sqrt(5))
a +=2 *np.exp(4*np.pi)-np.sin (a**2)
s='I am a string!'
print(s[ 3 ])


# A little better...
a = np.sqrt(5)
a += 2 * np.cos(4 * np.pi**2) - np.sin(a**2)

s = 'I am a string!'
print(s[3])
```

### Naming conventions

When writing small, simple code snippets (like many of the examples you have seen so far in these worksheets), using single-letter variable or function names is usually OK. However, for more complex code, it is usually a better idea to name your variables in a way that keeps your code easily understandable.

Take a look at the PEP-8 section on [variable names](https://www.python.org/dev/peps/pep-0008/#descriptive-naming-styles).

🚩 The following code finds the roots of the quadratic polynomial p(x) = ax^2 + bx + c. However, the author wrote it in a hurry. What can you do to improve it?

```python
a=2
b=.5
c=- 9

import numpy
x1=(-b-numpy.sqrt(b**2 -4*a*c)) / (2*a)
x2=(-b+numpy.sqrt(b**2 -4*a*c)) / (2*a)
a*x1**2+b*x1+c
```

## Your turn!

Now, with whatever time remains, discuss each other's solutions to CR1. You can use the assessment criteria to help discussion if you wish, or you could discuss your solutions in broader terms. For example, here are some of the things you could discuss:
- Have you all used similar approaches to solve the task, or are they very different?
- How did you design your tests? Are they sufficient to fully test the function?
- Time how long each of your functions takes to run on a large matrix of random numbers. Which is the quickest? (You'll have to test this on the same computer -- you could use this repo to share your code with each other, for instance.)
- Are the code comments useful? Is there a docstring?
- Could the code style be improved?

Note that the people in your Zoom breakout room today are very likely not the same people you will review on STACK.

### Learn more

If you'd like to learn more about code review, and more generally what we mean by writing "good code", I would recommend [this worksheet from MIT](https://web.mit.edu/6.005/www/fa15/classes/04-code-review/#reading_4_code_review). The code examples use Java, not Python, but should still be understandable; the general principles are the same in any language.
