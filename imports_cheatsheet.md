# My Imports Cheat Sheet

Note to self: I don't need to memorize these. Even senior people google imports
all day. I just need to know which "department" a thing lives in, then I can find it.
Figure out the JOB first → the job tells me the library.

---

## pandas → my data tables (import as pd)
This is my go-to whenever I'm dealing with a data file or a table.

import pandas as pd

pd.read_csv("file.csv")      # open a CSV into a table
df.head()                    # peek at first 5 rows
df.info()                    # quick summary of the whole table
df.shape                     # how many rows & columns
df.dtypes                    # what type each column is
df.corr()                    # correlations between columns
df.drop('col', axis=1)       # drop a column (axis=1 means column)
df['col'].value_counts()     # count each value (I used this for class balance)
df['col'].median()           # middle value
df['col'].fillna(value)      # fill in missing values
df['col'].replace(0, np.nan) # turn fake zeros into real "missing" markers

---

## numpy → number/math stuff (import as np)
I barely touched this so far — mostly just needed np.nan.

import numpy as np

np.nan   # the official "this value is missing" marker

---

## matplotlib → basic charts (import as plt)
The plain drawing tool. I use this for histograms and to set up my plots.

import matplotlib.pyplot as plt

df.hist(figsize=(12,10), bins=30)  # histograms of everything at once
plt.figure(figsize=(10,8))         # set the chart size
plt.subplot(2,4,i+1)               # put a chart in a grid spot
plt.title("My Title")              # heading
plt.tight_layout()                 # stop charts from overlapping
plt.show()                         # actually show it

---

## seaborn → prettier charts (import as sns)
Sits on top of matplotlib. I used this for my heatmap and boxplots.

import seaborn as sns

sns.heatmap(df.corr(), annot=True, cmap="coolwarm", fmt=".2f")  # correlation heatmap
sns.boxplot(x='Outcome', y=col, data=df)                        # boxplot split by group

---

## sklearn → machine learning (the big one)
This one's split into "rooms." I just figure out what I'm doing, then grab from
the right room. Reminder to me: "from X import Y" reads like an address —
"from sklearn's linear_model room, grab LogisticRegression."

# splitting data / cross-validation
from sklearn.model_selection import train_test_split
# train_test_split(X, y, test_size=0.20, stratify=y, random_state=42)

# logistic regression (my first model!)
from sklearn.linear_model import LogisticRegression
# model = LogisticRegression(max_iter=1000)

# the baseline / "lazy doctor"
from sklearn.dummy import DummyClassifier
# baseline = DummyClassifier(strategy="most_frequent")

# scoring my model
from sklearn.metrics import accuracy_score
# accuracy_score(y_test, predictions)

---

## When I don't know an import (which is often, and that's fine)
1. Just search the task: "sklearn random forest import" → the docs hand me the line.
2. Steal the import lines from the top of any tutorial doing what I want.
3. Remember it reads like an address: from [library].[room] import [tool].

The common ones are already sticking just from using them every day. The rare
ones I'll look up forever — apparently everyone does.

---

## Quick lookup for future-me

| I want to... | grab it from |
|---|---|
| handle a data table | import pandas as pd |
| math / NaN | import numpy as np |
| basic chart | import matplotlib.pyplot as plt |
| pretty chart | import seaborn as sns |
| split train/test | from sklearn.model_selection import train_test_split |
| logistic regression | from sklearn.linear_model import LogisticRegression |
| baseline model | from sklearn.dummy import DummyClassifier |
| score a model | from sklearn.metrics import accuracy_score |

Keep adding to this every time I learn a new one. — Tuba
