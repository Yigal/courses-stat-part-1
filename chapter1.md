---
title: 'Types of Data'
description: 'Chapter description goes here.'
---

## Statistics

```yaml
type: VideoExercise
key: 75c243fa1a
xp: 50
```

`@projector_key`
d80450da7d4ea87ecfde8aa82367a3a7

---

## Introduction

```yaml
type: NormalExercise
key: efbf8e2f51
xp: 100
```

Welcome to Statistics Online Course

First we will introduce the system

`@instructions`
**Data Camp Platform**
- This platform incorporates both video lectures exercises and hosted python kernel.
- To familiarise yourself with the python platform lets start with an easy excessive.
- You are given a python list that contains 5 floating-point objects and your goal is to calculate the mean
- The list is initiated by the following code
```
calculate_mean = [num1,num2,num3,num4,num5]
```

`@hint`
<!-- Examples of good hints: https://instructor-support.datacamp.com/en/articles/2379164-hints-best-practices. -->
- Simply add into a summation variable and divide by the size in the script on the top-right (not in the Shell) and hit 'Submit Answer'.

- This is an example hint.

`@pre_exercise_code`
```{python}
calculate_mean = [6, 7, 8, 9, 13]

```

`@sample_code`
```{python}
for x in calculate_mean:
  print(x)
```

`@solution`
```{python}
sum_of_numbers = 0
for x in calculate_mean:
  sum_of_numbers += x
mean_of_numbers = sum_of_numbers /= len(calculate_mean)
```

`@sct`
```{python}
# Examples of good success messages: https://instructor-support.datacamp.com/en/articles/2299773-exercise-success-messages
Ex().has_printout(1, not_printed_msg = "__JINJA__:Have you used `{{sol_call}}` to print out the sum of 7 and 10?")
success_msg("Great! On to the next one!")

```

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
Classify the variables

`@hint`
- Quantitative variables are numbers
  - Continuous variables have a meaningful value between any two values
  - Discrete variables have values that are "next to each other" without any meaningful value in the middle
- Categorical variables may be represented by numbers, but can just as easily be represented by other means
  - Ordinal variables have a natural order. 
  - Nominal variables can only be checked for equality or lack thereof.

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

## Interval vs. ratio lecture

```yaml
type: VideoExercise
key: bf6e9857d5
xp: 50
```

`@projector_key`
9489802b0c0bc69fb9994eeb781831d3

---

## Interval vs. ratio classification

```yaml
type: DragAndDropExercise
key: 35391f1492
xp: 100
```

<!-- Guidelines for contexts: https://instructor-support.datacamp.com/en/articles/2375526-course-coding-exercises. -->

`@instructions`
Classify the variables

`@hint`
- Ratio variables can be divided (A is twice as heavy as B, so weight is a ratio variable)
- Interval variables cannot be divided, but can be subtracted (such as the output of `new Date().getTime()` in JavaScript)
- Categorical variables cannot even be subtracted

`@solution`
```{python}

# Drag zone that holds all the options.
# Specify an ID for this zone to use in SCTs.
- id: variables
  title: "Variables" # Title of your zone This is not shown with more than 2 zones.

- id: ratio
  title: "Ratio"
  items: # Each drop zone has a list of items it contains. These will be shown in a random fashion.
    - content: "Height in meters" # Name of an item. Feel free to use markdown.
      id: height_m # ID of the item. This can be used in the SCTs.
    - content: "Height in feet"
      id: height_ft

- id: interval
  title: "Interval"
  items:
    - content: "Temperature in Centrigrade"
      id: temp_c
    - content: "Year that a country gained independence"
      id: year
      
- id: categorical
  title: "Categorical (Nominal or Ordinal)"
  items:
    - content: "[Country by population rank](https://www.cia.gov/library/publications/the-world-factbook/fields/335rank.html) (China first, then India, etc.)"
      id: pop_rank
```

`@sct`
```{python}
checks: # Individual checks and custom messages per item. This is optional. Without it, it will check that the options are as in the solution code.
  - condition: check_target(height_m) == ratio 
    incorrectMessage: "You can meaningfully say that somebody is twice as high as somebody else"
  - condition: check_target(height_ft) == ratio 
    incorrectMessage: "You can meaningfully say that somebody is twice as high as somebody else"
  - condition: check_target(temp_c) == interval 
    incorrectMessage: "There is no meaningful zero in centigrade, so it is an interval variable"
  - condition: check_target(year) == interval 
    incorrectMessage: "There is no meaningful year zero, so it is an interval variable"    
  - condition: check_target(pop_rank) == categorical 
    incorrectMessage: "Subtraction is meaningless, the difference between the US and India is not the same as the difference between India and China"    
successMessage: "Congratulations" # Message shown when all is correct.
failureMessage: "Try again!" # Message shown when there are errors (and there is no specific error available).
isOrdered: false # Should the items in the zones be ordered as in the solution code?
```

---

## Thinking exercise

```yaml
type: PureMultipleChoiceExercise
key: 84cfed756b
xp: 50
```

What variable type is the difference between two interval variables? For example, the change in temperature between one day and the next?

`@hint`
Interval variables can be meaningfully subtracted from each other, but not meaningfully divided, and there is no meaningful zero. Ratio variables have a meaningful zero and can be divided.

`@possible_answers`
- [Ratio]
- Interval
- Ordinal
- Nominal

`@feedback`
<!-- Examples of good feedback messages: https://instructor-support.datacamp.com/en/articles/2299773-exercise-success-messages.  -->
- Exactly
- Change always has a meaningful zero, no change - so it is a ratio variable, not an interval one.
- It's a quantitative variable, not a categorical one
- It's a quantitative variable, not a categorical one

---

## Nominal variables and machine learning

```yaml
type: VideoExercise
key: b5fe58bcde
xp: 50
```

`@projector_key`
c3aacd4eb60490e726dbd49a9094d9ec

---

## Convert Nominal Variable to Separate Variables

```yaml
type: NormalExercise
key: 3d69de0630
xp: 100
```



`@instructions`
A pandas data frame with two nominal variables (`city` and `country`) is provided in the variable `locations`. Use the pandas method [`get_dummies`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.get_dummies.html) to create a data frame called `analyze_locs` with both nominal variables separated into different values.

`@hint`


`@pre_exercise_code`
```{python}
import pandas as pd

locations = pd.DataFrame(data={'city': ['New York', 'Los Angeles', 'Haifa', 'Tel Aviv', 'London', 'Paris'],
                              'country':['US', 'US', 'Israel', 'Israel', 'UK', 'France']})


```

`@sample_code`
```{python}

```

`@solution`
```{python}
analyze_locs = pd.get_dummies(locations)
```

`@sct`
```{python}
Ex().check_object("analyze_locs").has_equal_value()
```

---

## Time variables

```yaml
type: VideoExercise
key: aeba89526c
xp: 50
```

`@projector_key`
5bb70b1c97c7381acaa8eff897394c9a

---

## Time series calculation

```yaml
type: MultipleChoiceExercise
key: 1d376955a1
xp: 50
```

The variable `power_usage` contains a pandas dataframe with the power used at different points in time. The points at in chronological order, but at different intervals. Assuming that the power is constant between measurements and that before the first measurement and after the last measurement no power was used, what was the total power consumption in kWh? Round to the nearest integer.

`@possible_answers`
- 2259
- [2592]
- 2952
- 2529
- 5292

`@hint`


`@pre_exercise_code`
```{python}
import pandas as pd

power_usage = pd.DataFrame(data={
  'time': ['2019-10-01 02:00:00', '2019-10-01 03:15:00', '2019-10-01 08:03:15', '2019-10-01 14:12:55', '2019-10-01 17:11:45', '2019-10-01 20:00:15'],
  'kW': [50, 100, 150, 175, 215, 75]})

"""
The solution: 

import pandas as pdimport functoolspower_usage['t_start'] = pd.to_datetime(power_usage['time'])temp = power_usage['t_start'].values.tolist()[1::]temp.append(temp[-1::][0])power_usage['t_end'] = pd.to_datetime(temp)power_usage['t_diff'] = power_usage['t_end'] - power_usage['t_start']power_usage['t_diff_h'] = power_usage['t_diff'].values.astype(float)/(3600*1e9)power_usage['kWh'] = power_usage['t_diff_h']*power_usage['kW']functools.reduce(lambda a,b : a+b, power_usage['kWh'])

"""
```

`@sct`
```{python}
# Check https://instructor-support.datacamp.com/en/articles/2375523-course-multiple-choice-with-console-exercises on how to write feedback messages for this exercise.
```

---

## Read a CSV and classify the variables

```yaml
type: TabExercise
key: f5d243d6e2
xp: 100
```

In this exercise you read housing price data and classify the field types using the `pandas` package.

`@pre_exercise_code`
```{python}
url = "https://assets.datacamp.com/production/repositories/5459/datasets/fa19780a7b011d9b009e8bff8e99922a8ee2eb90/housing_prices_data.csv"
```

***

```yaml
type: NormalExercise
key: cb246fe64e
xp: 15
```

`@instructions`
The URL for the information is in the variable `url`. In this step you read this information from that URL to a pandas data frame called `housingData`. The procedure to do this is [documented here](https://stackoverflow.com/questions/32400867/pandas-read-csv-from-url). After you read it, print the data frame.

`@hint`


`@sample_code`
```{python}

```

`@solution`
```{python}
from io import StringIO

import pandas as pd
import requests
s = requests.get(url).text

housingData = pd.read_csv(StringIO(s))
```

`@sct`
```{python}
Ex().check_object("housingData").has_equal_value()
```

***

```yaml
type: NormalExercise
key: dbd92105cd
xp: 15
```

`@instructions`
The next step is to get the list of variables, the list of elements in `housingData`. Create a dictionary (`housingColumns`) whose keys are the column names and the values the types (identified by pandas' `infer_types`).

`@hint`
Use the pandas documentation. 

- To get [the list of columns](https://pandas.pydata.org/pandas-docs/stable/reference/frame.html#function-application-groupby-window)
- To [infer the data type](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.api.types.infer_dtype.html)

`@sample_code`
```{python}

```

`@solution`
```{python}
from io import StringIO

import pandas as pd
import requests
s = requests.get(url).text

housingData = pd.read_csv(StringIO(s))

housingColumns = {}

cols = housingData.columns
for col in cols:
  housingColumns[col] = pd.api.types.infer_dtype(housingData[col])
  
 
```

`@sct`
```{python}
Ex().check_object("housingColumns").has_equal_value()
```

***

```yaml
type: MultipleChoiceExercise
key: 33082a4544
xp: 15
```

`@question`
The pandas library can tell us if a variable is an `integer`, a `string`, etc. However, to identify what type of variable it is (and therefore what types analysis we can do on it) we need domain knowledge. Use your domain knowledge and the information you obtained to identify what types of variable is `TotalBsmtSF`.

`@possible_answers`
- Quantitative continuous ratio
- Quantitative continuous interval
- Quantitative discrete ratio
- Quantitative discrete interval
- Categorical ordinal
- Categorical nominal

`@hint`


`@sct`
```{python}
Ex().has_chosen(1)
```

***

```yaml
type: MultipleChoiceExercise
key: 586dac5f22
xp: 15
```

`@question`
What type of variable is `Id`?

`@possible_answers`
- Quantitative continuous ratio
- Quantitative continuous interval
- Quantitative discrete ratio
- Quantitative discrete interval
- Categorical ordinal
- [Categorical nominal]

`@hint`


`@sct`
```{python}
Ex().has_chosen(6)
```

***

```yaml
type: MultipleChoiceExercise
key: 42a8ae4164
xp: 15
```

`@question`
What type of variable is `YearBuilt`?

`@possible_answers`
- Quantitative continuous ratio
- Quantitative continuous interval
- Quantitative discrete ratio
- [Quantitative discrete interval]
- Categorical ordinal
- Categorical nominal

`@hint`


`@sct`
```{python}
Ex.has_chosen(4)
```

***

```yaml
type: MultipleChoiceExercise
key: 308debd851
xp: 15
```

`@question`
What type of variable is `BsmtExposure`?

`@possible_answers`
- Quantitative continuous ratio
- Quantitative continuous interval
- Quantitative discrete ratio
- Quantitative discrete interval
- [Categorical ordinal]
- Categorical nominal

`@hint`


`@sct`
```{python}
Ex.has_chosen(5)
```

***

```yaml
type: MultipleChoiceExercise
key: cb7676efe4
xp: 10
```

`@question`
What type of variable is `CentralAir`?

`@possible_answers`
- Quantitative continuous ratio
- Quantitative continuous interval
- Quantitative discrete ratio
- Quantitative discrete interval
- Categorical ordinal
- [Categorical nominal]

`@hint`


`@sct`
```{python}
Ex.has_chosen(6)
```
