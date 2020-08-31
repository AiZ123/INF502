1. Write a function with the following signature: pythagoreanTheorem(length_a, length_b)

2. Write a function with the following signature: list_mangler(list_in)

3. Write a function with the following signature: grade_calc(grades_in, to_drop)

4. Write a function with the following signature: odd_even_filter(numbers)

description:

First, we generate an empty list to store two arrays: even and odd numbers. Then we use "if" to determine whether it is an even number.
If it is true, we can put the even number in the first sublist. Otherwise it is an odd number, and put it into the second sublist.


code:

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
    
result:

>>> odd_even_filter([1, 2, 3, 4, 5, 6, 7, 8, 9])
[[2, 4, 6, 8], [1, 3, 5, 7, 9]]
>>> odd_even_filter([98, 82, 56, 7, 77, 6, 333])
[[98, 82, 56, 6], [7, 77, 333]]
>>> odd_even_filter([3, 9, 43, 7])
[[], [3, 9, 43, 7]]
