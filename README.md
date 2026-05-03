# ⚡ Neural Network Explorer — Streamlit Dashboard

A fully interactive dashboard for 6 real neural networks trained from scratch in pure NumPy.

## Quick Start

```bash
# 1. Install dependencies
pip install streamlit plotly numpy scikit-learn pandas

# 2. Run the dashboard
streamlit run app.py
```

Opens at **http://localhost:8501**

---

## What's Inside

| Model | Task | Key Metric |
|-------|------|-----------|
| **MSE** | House price regression | Live slider inference |
| **Perceptron** | AND gate (binary) | 100% accuracy in 5 epochs |
| **Backprop** | XOR classification | Decision surface heatmap |
| **RNN** | Sine wave forecasting | R²=86%, 20-step forecast |
| **LSTM** | Stock price prediction | 15-day forecast |
| **CNN** | MNIST digit classification | 93.9% test accuracy |

---

## Features per Model

### 📊 MSE — Linear Regression
- Scatter plot with real house data + animated regression line
- Residual lines showing prediction error
- **Live inference**: drag a slider to predict any house size
- Loss curve over 60 epochs

### ○ Perceptron — AND Gate
- Decision boundary visualization with epoch slider
- Watch the boundary converge in real time
- **Live inference**: pick x₁, x₂ → get AND output instantly
- Full truth table with predictions

### ◈ Backprop — XOR MLP
- Decision surface heatmap at Epoch 1 / 50 / 100
- Gradient norm ‖∇W‖ over training
- **Live inference**: classify any (0/1, 0/1) XOR input
- Probability output from trained sigmoid

### ⟳ RNN — Sine Wave
- Full 150-timestep actual vs predicted overlay
- 20-step forecast region
- **Live inference**: enter your own 10-value window
- Configurable view range slider

### ⊞ LSTM — Stock Prices
- Stock price chart: actual + predicted + 15-day forecast confidence band
- Gate-by-gate explanation panel
- **Live inference**: enter 10 recent prices → next-day prediction
- 15-day forecast detail cards

### ⊡ CNN — Digit Classification
- 10×10 confusion matrix heatmap
- 8 learned conv filter visualizations
- 4 feature map outputs (post-conv activations)
- Sample digit images with true/predicted labels
- **Live inference**: select sample index → see digit + classification result

---

## File Structure

```
nn_dashboard/
├── app.py               ← Main Streamlit app
├── requirements.txt     ← pip dependencies
├── README.md
└── models/              ← Pre-trained model data (JSON)
    ├── out_mse.json
    ├── out_perceptron.json
    ├── out_backprop.json
    ├── out_rnn.json
    ├── out_lstm.json
    └── out_cnn.json
```

---

## Notes

- All models trained **from scratch in pure NumPy** — no PyTorch or TensorFlow
- Model JSON files contain trained weights + training history
- Inference runs client-side in Python — no server calls needed
- Plotly charts are fully interactive (zoom, hover, pan)
