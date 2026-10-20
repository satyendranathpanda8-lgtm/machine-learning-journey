# Day 5: Online Machine Learning

## What is Online Machine Learning?

- **Definition:** Online machine learning is a type of machine learning where the model learns **continuously** as new data arrives, without needing to be retrained from scratch.
- **Key concept:** The model updates itself **incrementally** with each new data point, making it adaptable to changes over time.

---

## How to Implement

### Libraries

1. **Scikit-learn (sklearn)**
2. **River**
   - River is a Python library for online machine learning.
   - It is the best result of a merger between **creme** and **scikit-multiflow**.
   - River's ambition is to be the go-to library for doing machine learning on streaming data.
3. **Vowpal Wabbit**

### Learning Rate

- A correct learning rate is important.
- It decides how frequently we train on our data.

### Out-of-Core Learning

- Used when you have a much larger dataset that batch learning can't train on all at once.
- The data is split into chunks, and the model is trained on one chunk at a time.

```
┌─────────────┐        ┌───────┐      ┌─────────┐      ┌──────┐
│ Large data  │ ─────► │ Chunk │ ───► │  Model  │ ───► │ Test │
│ (offline)   │        │ Chunk │      └─────────┘      └──┬───┘
└─────────────┘        │ Chunk │                          │
                       └───────┘                          ▼
                                                     ┌────────┐
                                                     │ Server │
                                                     └────────┘
```

- Here, online learning is used, but only the work is done **offline**.
- It works in batches (mini-batches), and after every batch the model gets improved.
- The training is mainly done on the online server, but it can also be done offline.

### How it works (on the server)

```
┌──────┐        ┌─────────┐        ┌──────┐
│ Data │ ─────► │  Model  │ ─────► │ Test │
└──────┘        └─────────┘        └──┬───┘
                                      │
                                      ▼
                  New data ──►   ┌────────┐
                                 │ Server │
                                 └────────┘
                              (predict & learn)
```

---

## When to Use

1. **Where there is concept drift:** where data is very volatile and changes all the time.
2. **Cost effective:** costs less, as it works in chunks.
3. **Faster solution:** training is very fast, as it is done in chunks.

---

## Disadvantages

### 1. Tricky to use

- Making changes is very complicated, because we train the model directly on the server.

### 2. Risky

- It is risky because the model depends on incoming data. If someone feeds in biased or unwanted data (for example, a spammer), the whole system will get biased.
- If someone controls the incoming data, they can create problems.
- **Solution:** Build a **monitoring system** that informs you whenever an anomaly appears.

---

## Offline Learning vs Online Learning

| Feature | Offline Learning | Online Learning |
|---------|------------------|-----------------|
| **Complexity** | Less complex, as the model is constant | Dynamic complexity, as the model keeps evolving over time |
| **Computational power** | Fewer computations; single-time, batch-based training | Continuous data ingestion results in ongoing model refinement, which is computationally demanding |
| **Use in production** | Easier to implement | Difficult to implement and manage |
| **Application** | Image classification or anything related to machine learning where data patterns remain constant, without sudden concept drift | Used in finance, economics and health, where new data patterns are constantly emerging |
| **Tools** | Industry-proven tools, e.g. Scikit-learn, TensorFlow, PyTorch, Keras, Spark MLlib | Active research / new project tools, e.g. MOA, SAMOA, scikit-multiflow, StreamDM |

---

*Part of my Machine Learning journey, Day 5.*
