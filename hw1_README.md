# Exam Results Calculator

## Overview

This set of functions is designed to assist teaching assistants in managing and calculating exam results for a class. The primary function included is `round_scores`, which rounds floating-point scores to integers.

## Instructions

### 1. Rounding Scores

You have the flexibility to give "partial credit" on exam questions, but overall exam scores must be integers. Utilize Python's built-in `round()` function to achieve this.

Create the function `round_scores(student_scores)` that takes a list of student scores. This function should consume the input list and return a new list with all the scores converted to integers. The order of the scores in the resulting list is not important.

#### Example:

```python
# Define `student_scores`
student_scores = [90.33, 40.5, 55.44, 70.05, 30.55, 25.45, 80.45, 95.3, 38.7, 40.3]

# Call `round_scores()` and print the result
print(round_scores(student_scores))
# Define `student_scores`
student_scores = [90.33, 40.5, 55.44, 70.05, 30.55, 25.45, 80.45, 95.3, 38.7, 40.3]

# Define `round_scores(list_of_floats)`
def round_scores(student_scores):
    # Initialize an empty list
    rounded_scores = []
    # Iterate over the elements of `student_scores`
    for score in student_scores:
        # Round each element and then append it to `rounded_scores`
        rounded_scores.append(round(score))
    # Return `rounded_scores`
    return rounded_scores

# Call `round_scores()` and print the result
print(round_scores(student_scores))

```
### Output
```python
[90, 40, 55, 70, 31, 25, 80, 95, 39, 40]

```


### 2. Non-Passing Students
As you were grading the exam, you noticed some students weren't performing as well as you had hoped. But you were distracted, and forgot to note exactly how many students.

Create the function count_failed_students(student_scores) that takes a list of student_scores. This function should count up the number of students who don't have passing scores and return that count as an integer. A student needs a score greater than 40 to achieve a passing grade on the exam.

