# HW1
### 1. Rounding Scores

**Function name::**  `round_scores(student_scores)` 
**Description:**  This function should take in an input list and return a new list with all the scores converted to integers. The order of the scores in the resulting list is not important.

## Implementation:

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
## Output:
```csharp
[90, 40, 55, 70, 31, 25, 80, 95, 39, 40]
```

### 2. Non-Passing Students
**Function Name:** count_failed_students
**Description:**  This function counts the number of students with scores below the passing threshold (40) and returns the count as an integer.
## Implementation:


```python
def count_failed_students(student_scores):
    # Initialize a counter for failed students
    failed_student_number = 0
    
    # Iterate over elements of `student_scores`
    for element_score in student_scores:
        # Check if the score is less than or equal to 40
        if element_score <= 40:
            # Increase the counter by 1 if the score is less than or equal to 40 points 
            failed_student_number = failed_student_number + 1
    
    # Return the count of failed students
    return failed_student_number

# Call'count_failed_students and print results
count_failed_students(student_scores=[90,40,55,70,30,25,80,95,38,40])
```
## Output:
```csharp
[5]
```
### 3. The "Best"

**Function Name:** `above_threshold`
**Description:** This function takes a list of student scores and a threshold as parameters. It returns a list of scores that are greater than or equal to the specified threshold.

## Implementation: 
```python
def letter_grades(highest):
    # Calculate the grade intervals based on the highest score
    Grade_F_threshold = 40  # 40 is the lowest score
    Grade_D_threshold = 40 + ((highest - 40) / 4)  # even intervals based on highest and score 40
    Grade_C_threshold = 40 + (((highest - 40) / 4) * 2)
    Grade_B_threshold = 40 + (((highest - 40) / 4) * 3)
    Grade_A_threshold = 40 + (((highest - 40) / 4) * 4)

    # Return the list of lower score thresholds for each grade interval
    return [int(Grade_F_threshold), int(Grade_D_threshold), int(Grade_C_threshold), int(Grade_B_threshold), int(Grade_A_threshold)]
# Call `above_threshold` and print the result
print(above_threshold(student_scores=[90, 40, 55, 70, 30, 68, 70, 75, 83, 96], threshold=75))
```

## Output:
```csharp
[90, 75, 83, 96]
```

### 4. Calculating Letter Grades

**Function Name:** `letter_grades(highest)` 
**Description:** This function takes the "highest" score on the exam as an argument and returns a list of lower score thresholds for each "American style" grade interval: ["D", "C", "B", "A"].

## Implementation:

```python
def letter_grades(highest):
    # Calculate the grade intervals based on the highest score
    Grade_F_threshold = 40  # 40 is the lowest score
    Grade_D_threshold = 40 + ((highest - 40) / 4)  # even intervals based on highest and score 40
    Grade_C_threshold = 40 + (((highest - 40) / 4) * 2)
    Grade_B_threshold = 40 + (((highest - 40) / 4) * 3)
    Grade_A_threshold = 40 + (((highest - 40) / 4) * 4)

    # Return the list of lower score thresholds for each grade interval
    return [int(Grade_D_threshold), int(Grade_C_threshold), int(Grade_B_threshold), int(Grade_A_threshold)]

# Call `letter_grades` and print the result
print(letter_grades(highest=100))
print(letter_grades(highest=88))
```
## Output:
```csharp
[40, 55, 70, 85, 100]
[40, 52, 64, 76, 88]
```

### 5. Matching Names to Scores

**Function Name:** `student_ranking(student_scores, student_names)` 
**Description:** This function matches each student name on the `student_names` list with their score from the `student_scores` list. The function assumes each argument list is sorted from the highest score(er) to the lowest score(er). It returns a list of strings with the format `<rank>. <student name>: <student score>`.

## Implementation:

```python
def student_ranking(student_scores, student_names):
    # Get the length of the lists
    number_of_students = len(student_scores)
    
    # Generate the ranking strings
    rankings = [f"{i+1}. {student_names[i]}: {student_scores[i]}" for i in range(number_of_students)]
    
    return rankings
​
# Call `student_ranking` and print the result for test
student_scores = [99, 77, 75, 55, 44, 33, 20]
student_names = ['Jake', 'Emma', 'Jess', 'Iris', 'Joe', 'Haley', 'Ben']
​
print(student_ranking(student_scores, student_names))
```

## Output:
```csharp
['1. Jake: 99', '2. Emma: 77', '3. Jess: 75', '4. Iris: 55', '5. Joe: 44', '6. Haley: 33', '7. Ben: 20']
```
### 6. A "Perfect" Score

**Function Name:** `perfect_score(student_info)` 
**Description:** This function takes a list of lists containing the name and score of each student (`student_info`). It returns the first `["name", score]` pair of the student who scored 100 on the exam. If no 100 scores are found in `student_info`, an empty list `[]` is returned.

## Implementation:

```python
def perfect_score(student_info):
    # Get the length of the list of number of students
    number_of_students = len(student_info)
    
    # Initialize an empty list where 100% score information will be held
    perfect_score_pair = []
    
    # Iterate through each element index of the list for names and scores
    for i in range(number_of_students):
        name, score = student_info[i]
        
        # Check if the score is 100
        if score == 100:
            perfect_score_pair.append([name, score])
            break  # Stop iterating after the first perfect score is found
            
    return perfect_score_pair
​
# Test
student_info = [["Jake", 60], ["Lester", 55], ["Adam", 100]]
result = perfect_score(student_info)
print(result)
```
## Output:
```csharp
[['Adam', 100]]
```


