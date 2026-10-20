# Day 4: Batch Machine Learning vs Online Machine Learning

## Batch Machine Learning (Offline Learning)

- The model learns from a **fixed dataset** (data is already collected).
- Training is done **in one go** (like studying from a full book before the exam).
- Once training is done, the model is ready. It **doesn't update automatically** with new data.

### How it works

```
┌──────┐   put in   ┌─────────┐              ┌──────────┐
│ Data │ ─────────► │  Model  │ ───────────► │   Test   │
└──────┘            └─────────┘              └────┬─────┘
                  (model gets trained)   (checks whether the
                                          model is trained or not)
                                                  │
                                                  ▼
                                            ┌──────────┐
                                            │  Server  │
                                            └──────────┘
                                          (only predicts)
```

- After testing, the model is deployed on a **server**, where it **only predicts**.
- It then makes the predictions that users want.

---

### Pros

- **Stability:** Because you train on the full data, updates are less noisy (the model sees everything together).
- Easier to find the best solution, as the whole dataset is visible.
- Simpler to implement when data is fixed.

### Cons

- Doesn't adapt to new incoming data immediately.
- If data is too large, training is slow and expensive.
- Not good for real-time systems, as it needs retraining if data changes.

---

## Quick Summary

| | Batch / Offline Learning |
|---|---|
| **Data** | Fixed dataset, already collected |
| **Training** | All at once, in one go |
| **After training** | Model doesn't update with new data |
| **Pros** | Stable, easy to find the best solution, simple when data is fixed |
| **Cons** | Doesn't adapt quickly, slow and costly on large data, poor for real-time systems |
| **Think** | Studying a full book before the exam |

---

*Part of my Machine Learning journey, Day 4.*
