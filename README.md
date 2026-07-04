# Human Activity Recognition Using Hidden Markov Models

A Python-based pipeline that collects smartphone sensor data and uses Hidden Markov Models (HMMs) to classify four human activities: **Still**, **Standing**, **Walking**, and **Jumping**.

---

## Project Structure

```
├── data/
│   ├── train/
│   │   ├── still/
│   │   ├── standing/
│   │   ├── walking/
│   │   └── jumping/
│   └── test/
│       ├── still/
│       ├── standing/
│       ├── walking/
│       └── jumping/
├── HMM_Activity_Recognition.ipynb
├── raw_signals.png
├── transition_matrices.png
├── decoded_sequence.png
├── confusion_matrix.png
├── feature_distributions.png
└── README.md
```

---

## Data Collection

- **App:** Sensor Logger (iOS)
- **Sensors:** Accelerometer + Gyroscope
- **Sampling Rate:** ~100 Hz (resampled to 50 Hz)
- **Activities:** Still, Standing, Walking, Jumping (~10 seconds each)

Each recording produces two CSV files (`Accelerometer.csv` and `Gyroscope.csv`) which are automatically paired and merged by the notebook.

Place training recordings under `data/train/<activity>/` and unseen test recordings under `data/test/<activity>/`.

---

## How to Run

1. **Install dependencies:**
   ```bash
   pip install hmmlearn scikit-learn pandas numpy matplotlib seaborn scipy
   ```

2. **Organise your data** into the folder structure above.

3. **Open and run** `HMM_Activity_Recognition.ipynb` top to bottom.

If no `data/` folder is found, the notebook automatically runs on synthetic data so you can verify everything works first.

---

## Results

| Activity | Sensitivity | Specificity |
|----------|-------------|-------------|
| Still    | 1.000       | 1.000       |
| Standing | 1.000       | 1.000       |
| Walking  | 0.000       | 1.000       |
| Jumping  | 1.000       | 0.625       |

**Overall Accuracy: 72.2%**

---

## Dependencies

- Python 3.10+
- `hmmlearn`, `scikit-learn`, `pandas`, `numpy`, `scipy`, `matplotlib`, `seaborn`