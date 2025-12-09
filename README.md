# 🌡️ Room Temperature Prediction

Dataset source: https://github.com/IoTsec/Room-Climate-Datasets

This repository contains a regression model for **predicting next-timestamp room temperature**.

### **Model Inputs**
- Temperature  
- Relative Humidity  
- Light Sensor 1  
- Light Sensor 2  
Target label: **Temperature of next timestamp** (`TempNext`)

### **Data Preparation**
- Combined CSV logs into a unified dataset  
- Checked missing values & datatypes  
- Added shifted temperature column (`TempNext`)  
- Train/Val/Test split: **70% / 15% / 15%**  
- StandardScaler normalization applied  

### **Baseline Model**
- 2 hidden layers, 64 neurons each  
- ReLU activation  
- L2 regularization  
- Dropout  
- Optimizer: Adam  
- Loss: MSE  

### 📉 **Training Analysis**
Training & validation curves show:

- Rapid improvement in first epochs  
- Stable convergence  
- Validation MAE < training MAE → **no overfitting**  

The model generalizes well.

### 🔧 Hyperparameter Tuning
Adjustments:
- More neurons  
- Stronger L2  
- Higher dropout  
- Added batch normalization  

**Result:**  
Validation MSE increased → tuning **did not improve** performance.

### 🧪 Test Set Evaluation
Tuned model:
- Test MSE: **0.2576**  
- Test MAE: **0.3594**  
- R² negative (underperforming)  

The baseline model outperformed the tuned version. Further tuning may be necessary to improve the model's accuracy and generalization. 

---