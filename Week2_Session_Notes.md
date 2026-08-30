# Week 2 Session Notes (30 minutes, live with X)

Files for this session: `Week2_Live_Session_Calculations.xlsx` (open and screen share, mostly just click into cells) and `live_session_notebook.ipynb` (open in Colab, run top to bottom).

---

## 1. Reconnect and review (5 min)

Just talk. Let her walk you through Week 1 in her own words.

- "Tell me what you did this week. Walk me through it like you're explaining it to someone who hasn't seen it."
- Listen for whether she actually understands the from-scratch part or just ran the cells. If it sounds shaky, don't stop and re-teach it now, just note it and keep an eye on it going forward.
- Quick gut check: "In one sentence, what does a slope and an intercept mean to you now?"

Then bridge into today: "Okay so last week we built a line that predicts voltage. Today we're going to ask two things. One, how do we actually know if that line is any good? And two, what happens when the question we're asking isn't 'what number' but 'yes or no'?"

---

## 2. Errors and evaluation metrics (7 min)

Open the Excel file, sheet "Linear Regression Errors."

Say something like: "So last week we found a line. But we never actually checked if it's a *good* line. Turns out the same squared-error idea from the least squares formula we did by hand is exactly how we check that."

Walk down the columns on screen:
- Point at the `error` column: "For every point, this is just actual minus predicted. Some are positive, some are negative."
- Point at `squared_error`: "This is the exact same squaring trick from last week. Squaring stops the positives and negatives from cancelling out, and punishes big mistakes more."
- Scroll to the bottom: "If I add up every squared error, I get this number. If I average it, that's called Mean Squared Error, MSE. That's literally the number least squares was minimizing last week without us realizing it."
- Click into the RMSE cell, show it's just the square root of MSE: "I take the square root just to bring it back into normal voltage units, so I can say it out loud: on average we're off by about this many volts."

Switch to the notebook briefly, run the MSE/RMSE cells there too, and point out `mean_squared_error` from sklearn gives the identical number. "So this whole idea has a name and a one-line shortcut, but you already know what's happening underneath it."

---

## 3. The pivot: what if the answer isn't a number? (5 min)

This is the fun part, keep it conversational, don't rush it.

"Okay here's a scenario. Same kind of component we've been working with. Let's say there's a safety rule: if the current gets too high, it overheats and becomes unsafe. I want a model that tells me yes or no, is this current level unsafe."

Ask her directly: "Before I tell you anything else, what do you think, is that a classification problem or a regression problem? And why?"

Let her answer. Whatever she says, confirm or gently correct, then say: "Right, classification, because the answer is a category, yes or no, not a number on a scale."

"So here's the question. We already know how to do regression. Could we just reuse linear regression for this, and treat 'unsafe' as 1 and 'safe' as 0?"

Let her guess. Then: "Let's actually try it and see what breaks."

---

## 4. Showing the limitation, then introducing logistic regression (8 min)

Switch to the notebook, Part 2. Run the cell that fits linear regression on the 0/1 target and plots it.

"Look at the line out at the edges. It's predicting things like negative point two, or one point three. But our answer can only ever be zero or one. Negative point two doesn't mean anything here. That's the actual limitation. Linear regression has no idea it's only allowed to output 0 or 1."

"So we need something built specifically for yes or no questions. That's logistic regression. Instead of a straight line, it fits an S-shaped curve that's squeezed so it can never go below 0 or above 1. And instead of predicting the answer directly, it predicts a probability, like 'this is 80% likely to be unsafe,' and then we pick a cutoff, usually 50%, to turn that into a final yes or no."

Run the logistic regression cell and the S-curve plot. Let her actually look at it for a few seconds before moving on.

---

## 5. Evaluation metrics for classification (5 min)

"Same question as before. How do we know if this model is any good? RMSE doesn't really make sense anymore since we're not predicting a number. For classification the simplest one is accuracy, just what percent did we get exactly right."

Run the accuracy cell.

Then switch to the Excel file, sheet "Classification Metrics." Point at the probability column formula bar: "This formula here is the actual logistic regression math, written out by hand, same as we did with least squares last week. And down here is a confusion matrix, it just breaks accuracy down further, out of the times we predicted unsafe, how many actually were, and same for safe."

Click through the confusion matrix cells, show the COUNTIFS formulas, point at the accuracy formula at the bottom.

"Accuracy alone can hide things. A confusion matrix tells you *what kind* of mistakes the model is making, not just how many."

---

## 6. Quick pandas recap (3 min)

Back in the notebook, Part 3. Run through the three small cells quickly, don't dwell.

"These three are just useful tools you'll want for homework. Making a new column based on a condition, counting how many rows fall into each category, and filtering rows down to just the ones you care about. Nothing new conceptually, just good to have in your toolkit."

---

## 7. Wrap up and assign homework (2 min)

"Okay, that's everything for today. Homework this week is the exact same pattern, just a new dataset and a new scenario, LEDs this time instead of the resistor. It's in the week-02 folder, same as always, `git pull` to get it. The homework notebook has a bit less pre-written code than last week since you've done this shape once already, but every step still tells you what to do."

"Same as always, if you get stuck, write down where and bring it to next week's call instead of looking it up."

Point her to the README.md in `week-02-logistic-regression` for the four questions she should be ready to explain next time.
