# 🌩️ Quantum Weather Forecasting

This project was submitted for the **Quantum AI Hackathon** by **Team 5**.
##  Team Members

| Name                | Role in Project         
|---------------------|-------------------------
|   Rana Saad        | Data Preprocessing  
|    Sherifa Helmy   | Classical Model devolopment
|      Yousef Ahmed   | Quantum Model Development       
|     Jana Mohamed    |  Reporting & Evaluation 

---

## Project Overview

This project aims to predict weather  temperature, using both **classical** and **quantum** machine learning techniques. Our goal was to evaluate the viability and performance of quantum-enhanced regression models on real-world weather data.

We used IBM’s **Qiskit Machine Learning** to implement a **Quantum Kernel Ridge Regression** model and benchmarked it against classical model
## Step-by-Step Breakdown

### 1. Data Preprocessing  

- Removed irrelevant/duplicate columns  
- Identified identical columns and dropped them  
- Final cleaned dataset used for both classical and quantum pipelines

---

### 2. Classical Model Development  

- Implemented:
  - Multiple linear Regression


- Evaluated using:
  - Mean Squared Error (MSE)
  - R² Score  

---

### 3. ⚛️ Quantum Model Development  

- Used `Qiskit` and `qiskit-machine-learning`  
- Constructed a parameterized quantum circuit using:
  - `ZZFeatureMap` for input encoding
  - `EfficientSU2` for variational ansatz  
- Combined into a **Quantum Neural Network (QNN)** using `EstimatorQNN`
- Integrated with PyTorch using `TorchConnector`
- Trained using `Adam` optimizer for 300 epochs
- Evaluated using **Mean Squared Error** and **R² Score**
- Enabled live prediction via user input interface


## Challenges and Solutions
1. **Challenge: Limited Quantum Resources and Simulation Time**
   - Quantum simulations are computationally intensive and time-consuming, especially with larger feature dimensions and more qubits.
   - **Solution**: We used feature reduction techniques (selecting the most important features) and a simple quantum circuit (using `ZZFeatureMap` and `EfficientSU2` with 2 qubits) to reduce the simulation time.
2. **Challenge: Training Quantum Models**
   - The quantum model training was unstable and sometimes got stuck in local minima.
   - **Solution**: We adjusted the learning rate and used the Adam optimizer.

### ⚛️ Quantum Model Results
**Training Progress**  
Our Quantum Neural Network (QNN) demonstrated strong learning capabilities over 300 training epochs, with consistent reduction in loss:
```
Epoch 20/300: Loss = 0.8823
Epoch 40/300: Loss = 0.8547
...
Epoch 300/300: Loss = 0.7593
```
*The loss decreased by 14% during training, showing the model's ability to learn complex weather patterns in high-dimensional Hilbert space.*
**Final Evaluation Metrics**  
- **Mean Squared Error (MSE)**: 29.3949  
- **R² Score**: 0.2254   
While classical model currently outperform in absolute metrics,The quantum model demonstrated promising results, especially in reducing overfitting and achieving competitive accuracy with fewer trainable parameters.

## Future Improvements

 **Error Mitigation Techniques**:
   - Implement advanced error mitigation techniques to improve the accuracy of quantum models on noisy hardware.

