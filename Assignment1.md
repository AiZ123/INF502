# Assignment 1: Python Basics
**1. Write a function with the following signature:** `pythagoreanTheorem(length_a, length_b)`

### code:
```
import math

def pythagoreanTheorem(length_a, length_b):

    length = math.hypot(length_a,length_b)
    return length
```
### result:
```
> pythagoreanTheorem(2, 2)
2.8284271247461903
> pythagoreanTheorem(3, 4)
5.0
> pythagoreanTheorem(5, 12)
13.0
```



2. Write a function with the following signature: list_mangler(list_in)

description:

First, we generate a new list, and then determine whether the number is even or not, and put the new result into the new list.

code:

def list_mangler(list_in):

    list_out=[]
    for x in list_in:
       if (x%2 == 0):
          list_out.append(x*2)
       else:
          list_out.append(x*3)
    return list_out

result:

> list_mangler([1, 2, 3, 4])
[3, 4, 9, 8]

> list_mangler([4, 6, 9, 12])
[8, 12, 27, 24]

> list_mangler([31, 22, 11, 9])
[93, 44, 33, 27]




3. Write a function with the following signature: grade_calc(grades_in, to_drop)

description:

First, we sort the list from lower to higher, then drop the lower scores, and then put the new result into our list.
Next, we can calculate the average scores of the rest of the list and compare the scores with the letter grade.

code:

from numpy import *

def grade_calc(grades_in, to_drop):

    grades_in.sort()
    grades_in = grades_in[to_drop:]
    grades = mean(grades_in)

    if grades >= 90:
        letter_grade = 'A'
    elif grades >= 80:
        letter_grade = 'B'
    elif grades >= 70:
        letter_grade = 'C'
    elif grades >= 60:
        letter_grade = 'D'
    else:
        letter_grade = 'F'

    return letter_grade


result:

> grade_calc([100, 90, 80, 95], 2)
'A'

> grade_calc([80, 90, 85, 75, 87, 88], 3)
'B'

> grade_calc([75, 85, 65, 87, 58], 1)
'C'




4. Write a function with the following signature: odd_even_filter(numbers)

description:

First, we generate an empty list to store two arrays: even and odd numbers. Then we use "if" to determine whether it is an even number.
If it is true, we can put the even number in the first sublist. Otherwise it is an odd number, and put it into the second sublist.


code:
‘’‘
def odd_even_filter(numbers):

    odd_numbers=[]
    even_numbers=[]
    out=[even_numbers, odd_numbers]

    for x in numbers:
       if (x%2 == 0):
          even_numbers.append(x)
       else:
          odd_numbers.append(x)

    return out
’‘’    
result:
‘’‘
> odd_even_filter([1, 2, 3, 4, 5, 6, 7, 8, 9])
[[2, 4, 6, 8], [1, 3, 5, 7, 9]]

> odd_even_filter([98, 82, 56, 7, 77, 6, 333])
[[98, 82, 56, 6], [7, 77, 333]]

> odd_even_filter([3, 9, 43, 7])
[[], [3, 9, 43, 7]]
’‘’
