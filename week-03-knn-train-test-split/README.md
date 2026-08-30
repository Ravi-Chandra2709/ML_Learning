# Week 3: Train/Test Split and K-Nearest Neighbors (KNN)

## What happened in our call

We covered:
- Why grading a model on the same data it trained on can be misleading (the "studying off the answer key" problem)
- Train/test split: holding back part of the data so we can grade the model honestly, on data it has never seen
- K-Nearest Neighbors (KNN): classify a new point by finding its K closest neighbors and letting them vote, using the same distance formula as the Pythagorean theorem from geometry class
- Why K=1 always looks perfect on training data (a point's nearest neighbor is always itself), and why that's a textbook example of overfitting
- How training accuracy and test accuracy change as K goes up

If you want to look back at exactly what we ran on the call, `live_session_notebook.ipynb` in this folder is the notebook we used together. `Week3_Live_Session_KNN_Calculations.xlsx` has the hand-calculated distance and voting example, plus the K=1 overfitting numbers, if you want to see the raw math again.

## Your homework this week

**Dataset:** `data/homework_fan_control.csv` — two features, `cpu_temperature_C` and `cpu_load_percent`, and a target, `fan_on` (1 = fan turned on, 0 = fan stayed off).

**Scenario:** Every laptop has a cooling fan that kicks in based on how hot the CPU is and how hard it's working. Build a KNN model that predicts whether the fan turns on.

Open `homework_notebook.ipynb` in this folder. Same pattern as the call: split the data, try K=1 to see the overfitting trap yourself, try a few different K values, pick the best one, and check it honestly on the test set.

Same rule as always: if you get stuck, write down where, and bring it to our next call.

## Before next call, be ready to explain

1. Why did K=1 look perfect on training data but worse on test data?
2. What does "K" actually control in KNN? What happens if K is way too big, like K=45?
3. What K did you pick as your best, and why?
4. For your own made-up prediction in Step 6, does the result make physical sense to you? Why or why not?
