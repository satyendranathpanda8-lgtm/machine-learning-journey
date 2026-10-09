# Day 3: Types of Machine Learning

```
                      Types of ML
                           │
     ┌───────────────┬─────┴──────────┬─────────────────┐
 Supervised     Unsupervised     Semi-supervised    Reinforcement
     │               │
     ├─ Regression   ├─ Clustering
     └─ Classification├─ Dimensionality Reduction
                     ├─ Anomaly Detection
                     └─ Association Rule Learning
```

---

## 1. Supervised Learning

- Data has **questions + answers**.
- The computer learns from those answers.
- **Example:** You give it pictures of cats (labeled "cat") and dogs (labeled "dog"), and it learns to identify them.
- **Think:** A teacher teaching with an answer key.

### Types

#### (a) Regression

- Predicts **numerical** data.
- **Examples:** Predicting house price, predicting temperature

| House size | Bedrooms | Price |
|------------|----------|-------|
| given | given | **predict** |

- **Think:** "What will the value be?"

#### (b) Classification

- Predicts a **categorical** value.
- **Examples:** Cat vs Dog, Pass vs Fail, Yes vs No
- **Think:** "Which group does it belong to?"

---

## 2. Unsupervised Learning

- Data has only questions, not answers.
- The computer finds patterns on its own.
- **Example:** Grouping customers who shop in similar ways.
- **Think:** Students figuring out groups without a teacher.

### Types

#### (a) Clustering

- Groups similar data points together.
- **Example:** Customer segmentation in marketing
- **Think:** Put similar things in the same bucket.

#### (b) Dimensionality Reduction

- Reduces the number of features (columns) while keeping important information.
- Helps in speeding up training and visualizing data.
- **Example:** From 100 features, reduce to 2 or 3 for plotting.
- **Think:** Summarize data without losing meaning.

#### (c) Anomaly Detection

- Finds unusual or rare data points that don't fit the pattern.
- **Examples:** Fraud detection in banking, detecting defective items in manufacturing
- **Think:** Spot the odd one out.

#### (d) Association Rule Learning

- Finds relationships between items in a dataset.
- **Example:** "People who buy milk often also buy bread."
- **Famous algorithm:** Apriori
- **Think:** If this happens, that also happens.

---

## 3. Semi-Supervised Learning

- Data has a **few answers + many questions**.
- The computer uses the few answers to guide learning on the rest.
- **Example:** Out of 1,000 photos, only 50 are labeled as "cat/dog". The rest are not.
- **Example:** Google Photos: if you label one photo, it will label all photos of that person.
- **Think:** The teacher gives you hints, and you figure out the rest yourself.

---

## 4. Reinforcement Learning

- The computer learns by **trial and error**.
- It gets **rewards** for good actions and **penalties** for bad ones.
- **Examples:** Teaching a robot to walk, or an AI to play chess
- **Example:** Self-driving cars
- **Think:** Like playing a video game, you learn by the points you score.

---

## Quick Summary

| Type | Data | Goal | Think |
|------|------|------|-------|
| **Supervised** | Questions + answers | Predict values or categories | Teacher with answer key |
| **Unsupervised** | Questions only | Find patterns on its own | Students grouping without a teacher |
| **Semi-supervised** | Few answers + many questions | Use a few labels to learn the rest | Teacher gives hints |
| **Reinforcement** | Rewards and penalties | Learn the best actions | Playing a video game |

---

*Part of my Machine Learning journey, Day 3.*
