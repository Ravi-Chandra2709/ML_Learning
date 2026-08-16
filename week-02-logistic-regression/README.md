# Week 2: Logistic Regression (Yes/No Questions)

## What happened in our call

We covered:
- How to check if a model's predictions are actually good (errors, squared errors, MSE, RMSE)
- Why linear regression breaks when the answer is "yes or no" instead of a number
- Logistic regression: a model built specifically for yes/no questions, using an S-shaped curve that always stays between 0 and 1
- How to evaluate a classification model: accuracy, and a confusion matrix
- A few small but useful pandas tools: making a new column from a condition, `value_counts()`, and filtering rows

If you want to look back at exactly what we ran on the call, `live_session_notebook.ipynb` in this folder is the notebook we used together.

## Your homework this week

**Dataset:** `data/led_current_burnout.csv` — two columns: `current_mA` (the current running through an LED) and `burnout` (1 if the LED burned out, 0 if it didn't).

**Scenario:** LEDs have a maximum safe current. Push too much current through one for too long, and it burns out. Your job: build a model that predicts whether a given current level will cause burnout.

Open `homework_notebook.ipynb` in this folder. It follows the exact same pattern as our call today, just with less pre-written code this time. In a few places you'll only need to change a variable name or a column name. In a couple of places you'll write a bit more yourself, but every step tells you clearly what to do.

Same rule as always: if you get stuck, write down where, and bring it to our next call instead of looking it up.

## Before next call, be ready to explain

1. In your own words, why doesn't linear regression work well for a yes/no question like this one?
2. What does the S-shaped curve in logistic regression actually represent?
3. What was your model's accuracy, and what did the confusion matrix tell you beyond just the accuracy number?
4. Pick one row your model got wrong. Why do you think it got that one wrong?
