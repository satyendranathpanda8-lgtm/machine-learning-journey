# Day 6: Instance-Based vs Model-Based Learning

## 1. Instance-Based Learning (IBL)

- The model doesn't really "learn" a general rule.
- It **memorizes all training examples** (instances).
- When a new input comes, it **compares it to stored examples** to make a prediction.
- Also called **"Lazy Learning"**, because the model delays processing until a query appears.

### Example: KNN Algorithm

| IQ | CGPA | Placement |
|----|------|-----------|
| 80 | 8 | Yes |
| 70 | 7 | No |
| 75 | (new student) | **?** |

```
 CGPA
  │        ✕ = Yes     ⊗ = No
  │
  │   ⊗                        ✕  ✕
  │     ✕ ✕                   ✕ ✕ ✕
  │   ⊗ ✕                    ✕ ◉ ✕
  │     ✕                    ⊗
  └──────────────────────────────── IQ
```

- When a new data point comes, it looks at its surrounding **3 or 5 neighbours**.
- Whichever class has more points among those neighbours, the new point is assigned to that class.

### Pros

- Simple and easy to implement
- Good for problems where rules are hard to define
- Can adapt quickly as you add new data

### Cons

- Slow for large datasets
- Needs lots of memory
- Sensitive to irrelevant features or noise

---

## 2. Model-Based Learning

- Instead of memorizing data (like instance-based), the algorithm **learns a general model** from the training data.
- This model captures **patterns / relationships** in the data.
- Once trained, you can use this model to make predictions on new data, without storing all examples.
- **Think:** "Don't remember every past case, just learn the rules."

### Example: IQ, CGPA and Placement

| IQ | CGPA | Placement |
|----|------|-----------|
| ... | ... | Yes / No |

```
 CGPA
  │                 Yes (✕)
  │    ╭───╮          ✕
  │  ╭─╯   ╰╮
  │  │  ✕    ╰╮
  │  ╰╮       │
  └───┴───────┴──────────── IQ
```

- It draws a **boundary**: points above the boundary are getting placements, and points below the boundary are not.
- Here you don't need any help from the training points, unlike instance-based learning.

### Examples of Model-Based Algorithms

- Linear Regression
- Logistic Regression
- Decision Trees
- Neural Networks
- Support Vector Machines (SVMs)

### Pros

- Fast prediction (after training)
- Doesn't need to store all training data
- Works well on large datasets
- More interpretable in some cases (e.g. regression models)

### Cons

- If the model is too simple, it may **underfit** (miss patterns)
- If it is too complex, it may **overfit** (memorize instead of generalize)
- Needs retraining if data changes a lot

---

## Difference

| Model-Based Learning | Instance-Based Learning |
|----------------------|-------------------------|
| Prepare the data for model training | Prepare the data for model training (no difference) |
| Train models from training data to estimate model parameters, i.e. discover patterns | Do not train a model. Pattern discovery is postponed until a scoring query is received |
| Store the model in a suitable form | There is no model to store |
| Generalize the rules in the form of a model, even before scoring an instance using the model | No generalization before scoring. Only generalizes for each scoring instance individually, as and when seen |
| Predict for an unseen scoring instance using the model | Predict for an unseen scoring instance using the training data |
| Can throw away input/training data after model training | Input/training data must be kept, since each query uses part or the full set of training observations |
| Requires a known model form | May not have an explicit model form |
| Storing models generally requires less storage | Storing training data generally requires more storage |

---

## Quick Summary

| | Instance-Based | Model-Based |
|---|----------------|-------------|
| **Also called** | Lazy learning | Eager learning |
| **How it works** | Memorizes data and compares new input to stored examples | Learns a general model (rules) from the data |
| **Example** | KNN | Linear Regression, Logistic Regression, Decision Trees, Neural Networks, SVMs |
| **Training data after training** | Must be kept | Can be thrown away |
| **Think** | Remember every past case | Just learn the rules |

---

*Part of my Machine Learning journey, Day 6.*
