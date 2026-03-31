# 🏀 NBA Game Outcome Predictor

> Built and compared three ML architectures to predict NBA game win/loss outcomes. Best model averaged **7.0/10 correct** per 10-game stretch with a Celtics-specific RNN hitting **75.57% accuracy** — well above the 66% baseline.

**By: Ryan Wolfe, James Hu, Jack Hertz, Edward Jeong** · [📖 Read the full write-up on Medium](https://medium.com/@jjhertz/predicting-nba-game-outcomes-bd5efddb6894)

---

## Results

| Model | Accuracy | Avg Correct / 10-game chunk |
|---|---|---|
| FFNN v1 (win % only) | 67.77% | 7.0 / 10 |
| Logistic Regression | 67.98% | 6.84 / 10 |
| Celtics RNN (rolling win %) | **75.57%** | **7.33 / 10** |
| Baseline (pick higher win %) | 66% | — |

---

## Model Architectures

### Feedforward Neural Network
![FFNN Structure](blog_figures/basicFFNNStruc.png)

### RNN Structure (Best Performer)
![RNN Structure](blog_figures/RNNstruc1.png)

---

## Training Results

### FFNN Accuracy Over Epochs
![FFNN Accuracy](blog_figures/accuracyOfFFNN1.png)

### Larger RNN Results (Celtics-specific)
![Larger RNN Results](blog_figures/largerRNNResults.png)

---

## 10-Game Chunk Predictions

### Feedforward Neural Network
![FFNN Chunks](blog_figures/10GameChunksFFNN.png)

### Logistic Regression
![LogReg Chunks](blog_figures/10GameChunksLogReg.png)

### Recurrent Neural Network
![RNN Chunks](blog_figures/10GameChunksRNN.png)

---

## Data

![Data Frame](blog_figures/dFramepic1.png)

Pulled from [nba.com](https://www.nba.com/stats) via the `nba_api` Python package. Covered 2021–2024 regular seasons. Rest days feature engineered manually from game date gaps.

![Expanded Data Frame](blog_figures/addingMoreStatsDFrame.png)

---

## Key Takeaway

> Data relevance beats model complexity. Adding more layers didn't improve accuracy — what mattered was having the *right* features. Without injury data, lineup changes, or travel fatigue, no amount of architecture improvements could generate that signal.

---

## Tech Stack
`Python` `Keras` `TensorFlow` `pandas` `numpy` `scikit-learn` `nba_api`
