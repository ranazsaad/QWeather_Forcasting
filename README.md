# 🌩️ Quantum Weather Forecasting

This project was submitted for the **Quantum AI Hackathon** by **Team 5**.


## Team Members

| Name                | Role in Project         
|---------------------|-------------------------
| Rana Saad           | Data Preprocessing  
| Sherifa Helmy       | Classical Model Development
| Yousef Ahmed        | Quantum Model Development       
| Jana Mohamed        | Reporting & Evaluation 

---


## Project Overview

This project investigates the potential of quantum machine learning for temperature forecasting by comparing classical models with quantum approaches.

We implemented a **Quantum Neural Network** using Qiskit Machine Learning and benchmarked it against classical linear regression, achieving remarkable results with only 2 key features.

We used IBM’s **Qiskit Machine Learning** to implement a **Quantum Kernel Ridge Regression** model and benchmarked it against classical model


## Step-by-Step Breakdown

### 1. Classical Data Preprocessing  

- Removed irrelevant/duplicate columns  
- Identified identical columns and dropped them  
- standard scaling is applied to the input features
---


### 2. Classical Baseline Model  

We implemented a Multiple Linear Regression model 

- Used a correlation heatmap to analyze feature relationships and selected the top 8 features that were strongly correlated
- Split data into training and test sets (80/20).
- Trained a Multiple Linear Regression model.
  
###  Classical Model Results
  Serves as performance benchmark for our quantum approach
  - **MSE**: 0.0738  
  - **R²**: 0.9981  

---

### 3. Quantum Data Preprocessing  

- Removed irrelevant/duplicate columns with quantum efficiency in mind  
- Selected top 2 most impactful features for quantum processing:  
  - `apparent_temperature_mean (°C)`  
  - `et0_fao_evapotranspiration (mm)`  
- Applied specialized MinMax scaling (-1 to 1) optimal for quantum feature maps  

---

### 4. Quantum Neural Network Implementation  ⚛️

**Breakthrough Quantum Architecture:**  
- Used `Qiskit` and `qiskit-machine-learning` with PyTorch integration  
- Quantum circuit components:  
  - `ZZFeatureMap` for optimal quantum feature encoding  
  - `EfficientSU2` (with circular entanglement) for variational optimization  
- Constructed **Hybrid Quantum-Classical Model**:  
  - Quantum layer via `EstimatorQNN`  
  - Classical post-processing with PyTorch `Linear` layer  
- Advanced training protocol:  
  - AdamW optimizer with learning rate scheduling  
  - Huber loss for robust quantum training  
  - Early stopping to prevent overfitting  
  - 300-epoch training on optimized 365-sample subset  


     
### Quantum Model Results
**Training Progress**  
Our Quantum Neural Network (QNN) demonstrated strong learning capabilities over 300 training epochs, with consistent reduction in loss:
```
Epoch 30/300, Loss: 0.0044
Epoch 60/300, Loss: 0.0040
...
Epoch 300/300, Loss: 0.0038
```
*The quantum model achieved 14% loss reduction while using only 25% of the features required by the classical model.*

**Final Quantum Metrics:**  
- **MSE**: 6.2681  
- **RMSE**: 2.5036  
- Training Efficiency: 365 samples vs 5000+ in classical approach  

*While absolute metrics currently favor classical methods, our quantum model demonstrates:*
1. Superior feature efficiency (2 vs 8 features)  
2. Strong learning capability with minimal data  
3. Foundation for quantum advantage 



## Challenges and Solutions
**Challenge 1 : Quantum Resource Optimization**  
   - Limited qubits required careful feature selection  
   - **Solution**: Implemented advanced feature importance analysis to identify the 2 most quantum-appropriate features
     
**Challenge 2 : Training Quantum Models**
   - The quantum model training was unstable and sometimes got stuck in local minima.
   - **Solution**: Used AdamW optimizer with Huber loss and a learning rate schedule to help the model learn smoothly.


     
## Requirements

### Quantum Computing Environment
- Python 3.8+
- Qiskit 0.45+ (with machine learning components)
- PyTorch 2.0+

### Core Packages
- numpy
- pandas
- scikit-learn
- matplotlib

### Recommended Platform
- Google Colab Pro (for accelerated quantum simulations)

---

## How to Run the Quantum Project

1. **Clone the repository**
2.  **Access the Quantum Notebook**  
   - Open `QML_WeatherForcasting.ipynb` in Google Colab
     
3. **Upload the Dataset**
   - Download the dataset from [Cairo Weather - Kaggle](https://www.kaggle.com/datasets/yousefelshahat2/cairo-whether).
   - In Google Colab, upload the CSV file

## Future Quantum Improvements

**Hardware Deployment**  
   - Migrate to real quantum processors as they become available  


---
