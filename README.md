# 🧠 System Identification of a Second-Order Filter Using Neural Networks

This project models the behavior of a classical second-order dynamic system (spring-mass-damper or low-pass filter) using a supervised learning approach. A synthetic dataset is generated from the second-order differential equation, and a feedforward neural network is trained to predict the system output.

---

## 📌 Objective

To train an artificial neural network (ANN) to learn the dynamics of a second-order system given a history of system inputs and outputs. The model is intended to approximate a physical system's response — similar to control systems or signal filtering applications.

---

## ⚙️ Simulation Details

### System Equation:

\[
\ddot{y}(t) + 2ζω_n \dot{y}(t) + ω_n^2 y(t) = ω_n^2 u(t)
\]

This represents a second-order system where:
- `y(t)` is the output (e.g., displacement or signal)
- `u(t)` is the input (e.g., force or control signal)
- `ωₙ` is the natural frequency
- `ζ` is the damping ratio

### Numerical Method:
- Solved using **Euler integration** with `dt = 0.01 s`
- Generated `5000` data samples with random inputs `u(t)`

---

## 🧪 Machine Learning Pipeline

| Step | Description |
|------|-------------|
| **Feature Vector** | `[y(t-1), y(t-2), u(t-1), u(t-2)]` |
| **Target** | `y(t)` |
| **Normalization** | Inputs and outputs scaled using `MinMaxScaler` |
| **Model Architecture** | Feedforward ANN with 2 hidden layers (20 neurons each), `tanh` activation |
| **Loss Function** | Mean Squared Error (MSE) |
| **Optimizer** | Adam (`lr = 0.001`) |
| **Training** | 80/20 train-test split, trained for 100 epochs |

---

## 📈 Results

The trained model accurately tracks the system’s response on unseen data. The predicted output closely matches the true simulated output from the second-order system.

📊 **Output Comparison Plot:**

![Model vs True Output](output.png)

---

## 🧰 Tools & Technologies

- Python
- NumPy
- Matplotlib
- Scikit-learn
- TensorFlow / Keras

---

## 🧠 Key Learnings

- Learned to simulate physical systems using differential equations
- Understood the ANN's ability to learn time-dependent behavior from data
- Applied ML to classical control-system-like scenarios

---

## 🔮 Future Improvements

- Implement RNN/LSTM for better time-series prediction
- Add input noise or disturbance for robustness testing
- Use Runge-Kutta for higher-accuracy system simulation

---

> ⚠️ *This project was built for educational purposes and does not use real-world experimental data.*

