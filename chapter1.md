---
title: 'Types of Data'
description: 'Chapter description goes here.'
---

## Variable types lecture

```yaml
type: VideoExercise
key: ab1a5203c7
xp: 50
```

`@projector_key`
11614ef99ebdf40b629637458e8ee6b2

---

## Classify variables

```yaml
type: DragAndDropExercise
key: 2ae86346f2
xp: 100
```

<!-- Guidelines for contexts: https://instructor-support.datacamp.com/en/articles/2375526-course-coding-exercises. -->

`@instructions`
<!-- Guidelines for instructions https://instructor-support.datacamp.com/en/articles/2375526-course-coding-exercises. -->
- Instruction 1
- Instruction 2

`@hint`
<!-- Examples of good hints: https://instructor-support.datacamp.com/en/articles/2379164-hints-best-practices. -->
- This is an example hint.
- This is an example hint.

`@solution`
```{python}
# Edit or remove this code to create your own exercise.
# This is 1 type of drag and drop exercise, there are 2 other types. See documentation:
# http://instructor-support.datacamp.com/en/articles/3039539-course-drag-drop-exercises

# Make sure you only use SPACES, NOT TABS in front of each line.

# Drag zone that holds all the options.
# Specify an ID for this zone to use in SCTs.
- id: variables
  title: "Variables" # Title of your zone This is not shown with more than 2 zones.

# You can keep adding drop zones to sort to.
# This example has 2 zones.
- id: quant_cont
  title: "Quantitative Continuous"
  items: # Each drop zone has a list of items it contains. These will be shown in a random fashion.
    - content: "Height in meters" # Name of an item. Feel free to use markdown.
      id: height_m # ID of the item. This can be used in the SCTs.
    - content: "Height in feet"
      id: height_ft

- id: quant_disc
  title: "Quantitative Discrete"
  items:
    - content: "Height in meters, when stored on computer"
      id: height_comp
    - content: "Price of tea in a specific store in Beijing, in Yuan"
      id: tea_china
      
- id: cat_ordinal
  title: "Categorical Ordinal"
  items:
    - content: "Rank in the military"
      id: rank
    - content: "Letter grade"
      id: grade
      
 - id: cat_nominal
   title: "Categorical Nominal"
   items:
     - content: "Country name"
       id: country
     - content: "Name of currency"
       id: currency
```

`@sct`
```{python}
checks: # Individual checks and custom messages per item. This is optional. Without it, it will check that the options are as in the solution code.
  - condition: check_target(height_m) == quant_cont 
    incorrectMessage: "No, a physical quantity such as height is a continuous quantitative variable" 
  - condition: check_target(height_ft) == quant_cont 
    incorrectMessage: "No, a physical quantity such as height is a continuous quantitative variable"    
  - condition: check_target(height_comp) == quant_disc 
    incorrectMessage: "A value on a computer is always discrete. When you use n bits to store a value, you can only have 2^n distinct values."         
  - condition: check_target(tea_china) == quant_disc
    incorrectMessage: "A yuan is divided into 100 fen (similar to how a dollar is divided into a hundred cents), but as there are no coins smaller than one fen, the price would always be an integer number of fens. An integer number is a discrete quantity"
  - condition: check_target(rank) == cat_ordinal
    incorrectMessage: "Military ranks have an order. A general outranks a captain, which outranks a sergeant, which outranks a private"
- condition: check_target(grade) == cat_ordinal
    incorrectMessage: "A letter grade of A is better than B, which is better than C, etc."
- condition: check_target(country) == cat_nominal
    incorrectMessage: "Names don't have an inherent order, so it is categorical nominal"
- condition: check_target(currency) == cat_nominal
    incorrectMessage: "Names don't have an inherent order, so it is categorical nominal"
    
successMessage: "Congratulations" # Message shown when all is correct.
failureMessage: "Try again!" # Message shown when there are errors (and there is no specific error available).
isOrdered: false # Should the items in the zones be ordered as in the solution code?
```

---

## Read data

```yaml
type: NormalExercise
key: 2b3a3c607d
xp: 100
```

<!-- Guidelines for contexts: https://instructor-support.datacamp.com/en/articles/2375526-course-coding-exercises. -->

`@instructions`
<!-- Guidelines for instructions https://instructor-support.datacamp.com/en/articles/2375526-course-coding-exercises. -->
- Instruction 1
- Instruction 2

`@hint`
<!-- Examples of good hints: https://instructor-support.datacamp.com/en/articles/2379164-hints-best-practices. -->
- This is an example hint.
- This is an example hint.

`@pre_exercise_code`
```{python}
import pandas as pd
import io
import requests
url="https://drive.google.com/file/d/1r5jalTyVczE5VCFND0VHpNxlnpjyJjDd"
s=requests.get(url).content
c=pd.read_csv(io.StringIO(s.decode('utf-8')))

```

`@sample_code`
```{python}

```

`@solution`
```{python}

```

`@sct`
```{python}
# Examples of good success messages: https://instructor-support.datacamp.com/en/articles/2299773-exercise-success-messages.
```
