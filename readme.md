# STL-VMD Secondary Decomposition + Informer-LSTM Parallel Prediction Model

1. Introduction
Traditional time series prediction models, such as ARIMA and single LSTM, are limited in their performance when faced with multi-scale features (e.g., long cycles, short cycles, noise mixed) and nonlinear dynamics (e.g., sudden changes, trend drift). Particularly, they perform poorly in the following scenarios:
Strong noise interference: High-frequency noise in industrial sensor signals obscures the true patterns.
Multi-seasonality and trend coupling: For example, power load data (daily cycle + weekly cycle + holiday trend).
To address these issues, this issue proposes a parallel prediction model based on STL+VMD secondary decomposition and Informer-LSTM. This innovative model achieves multi-level modeling of complex time series through secondary decomposition and hybrid architecture, providing a new technical path for high-precision predictions.
1. Innovation Model Overview
1.1 Model Evaluation:
1.2 Predictive Visualization:
1.3 Data Set Feature Analysis—Visualization:
We also provide detailed materials, instructional documents, and video explanations, including how to replace your own dataset, tutorials on parameter adjustments, and replacement tasks for predictive tasks, code commented line by line, with detailed introductions to parameters:
● Data Sets: Wind farm wind power dataset, power dataset, wind speed dataset, etc.
● Environment Framework: Python 3.9, PyTorch 2.1 and above versions can run.
● Single Step Prediction Model Score: Test set 0.99
● Usage Object: Paper requirements, graduation design requirements.
● Code Guarantee: Code comments are detailed, ready to run without modification.
2. Innovation Points of the Model
2.1 Secondary Decomposition Strategy
STL First Decomposition: Extract explicit trends (Trend) and seasonality;
VMD Secondary Decomposition: Residual is subjected to variational mode decomposition to separate the implicit multi-scale sub-signals (IMF).
2.1 \tCombine the Advantages of Informer and RNN
Informer: Expert in handling longitudinal sequences, capable of parallel computation, enhancing computational efficiency and predictive performance. Informer has been improved on the basis of Transformer to better suit time-series data, especially for sequences with long-term dependencies.
BiLSTM: Outstanding in capturing both short-term and long-term dependencies of sequence data, effectively managing temporal relationships within sequences.
By parallelly using these two models, patterns at different temporal scales can be captured more effectively, improving prediction accuracy and robustness.
2.2 Parallel Model Architecture: By parallelly using Informer and LSTM, learning through two branches allows the model to extract and process information at different temporal scales:
Informer part: Processes global time-series patterns, effectively handling longitudinal sequence data.
LSTM part: Processes local time-series patterns, effectively capturing short-term dependencies and dynamic changes in sequence data.
This architecture comprehensively captures the characteristics of time-series data, enhancing the model's predictive performance.
2.3 Model Fusion: Concatenating the outputs of Informer and LSTM, a fully connected layer is used to fuse the features from different models. This fusion approach enables the model to simultaneously utilize the global information extraction capability of Informer and the local time-series relationship modeling capability of LSTM.
2.4 Efficient Computation: The use of Informer significantly improves the computational efficiency of longitudinal sequences, while the use of LSTM ensures the full utilization of local time-series information. This combination not only guarantees efficient computation but also enhances prediction accuracy and reliability.
3 Secondary Decomposition and Data Set Production:
STL separates explicit trends/seasonal terms, VMD refines nonlinear residuals to avoid pattern confusion.
3.1 Importing Data
3.2 STL Decomposition
3.3 VMD Decomposition
\tThe residual term is decomposed into K IMFs to solve the problem of insufficient nonlinear residual decomposition in STL.
Parameter selection: Adaptively determine the number of IMFs (K) through center frequency observation method.
3.4 Dataset Preparation and Preprocessing
For detailed information, please refer to the provided documents!
4. Parallel Prediction Model Based on STL-VMD Secondary Decomposition + Informer-LSTM
4.1 Define the Informer-LSTM Parallel Prediction Network Model
4.2 Set parameters and train the model
50 epochs, MSE is 0.000879. The performance of STL-VMD secondary decomposition + Informer-LSTM parallel prediction is significant. The model can fully utilize the long-term dependency modeling capability of Informer and the short-term dependency capturing ability of LSTM. It converges quickly, has excellent performance, high prediction accuracy, and can further improve its predictive performance by appropriately adjusting model parameters.
5 Results Visualization and Model Evaluation
5.1 Visualization of Prediction Results
5.2 Model Evaluation
The forecast results show that under the STL-VMD secondary decomposition + Informer-LSTM parallel prediction model, the fitting effect is good. Through this design, we can fully utilize the advantages of Informer and LSTM to achieve efficient and accurate time series prediction, with a significant combined prediction effect!
Click to download: Complete original data, Python code
Previously Featured Content:
Time Series Forecasting: Analysis and comparison of LSTM, ARIMA, Holt-Winters, SARIMA models
Wind Speed Prediction (Part 1) Data Set Introduction and Preprocessing
Wind Speed Prediction (II) EMD-LSTM Model Based on Pytorch
Wind Speed Prediction (III) EMD-LSTM-Attention Model
Wind Speed Prediction (IV) EMD-Transformer Model Based on Pytorch
Wind Speed Prediction (5) EMD-CNN-LSTM Model Based on PyTorch
Wind Speed Prediction (6) EMD-CNN-GRU Parallel Model Based on PyTorch
CEEMDAN + Combination Prediction Model (BiLSTM-Attention + ARIMA)
CEEMDAN + Combination Prediction Model (CNN-LSTM + ARIMA)
CEEMDAN + Combination Prediction Model (Transformer - BiLSTM + ARIMA)
CEEMDAN + Combination Prediction Model (CNN-Transformer + ARIMA)
Multi-Feature Variable Sequence Prediction (1) - CNN-LSTM Wind Speed Prediction Model
Multi-Feature Variable Sequence Prediction (2) - CNN-LSTM-Attention Wind Speed Prediction Model
Multi-Feature Variable Sequence Prediction (3) - CNN-Transformer Wind Speed Prediction Model
Multi-Feature Variable Sequence Prediction (4) - Transformer-BiLSTM Wind Speed Prediction Model
Multi-Feature Variable Sequence Prediction (5) - CEEMDAN+CNN-LSTM Wind Speed Prediction Model
Multi-Feature Variable Sequence Prediction (6) - CEEMDAN+CNN-Transformer Wind Speed Prediction Model
Prediction Model Based on SSA Optimized by Sparrow - CEEMDAN-BiLSTM-Attention
Prediction Model Based on SSA Optimized by Sparrow - CEEMDAN-Transformer-BiGRU
Superior Prediction Model: Secondary Decomposition-Combination Prediction
Multi-Feature Variable Sequence Prediction (7) - CEEMDAN+Transformer-BiLSTM Prediction Model
Multi-Feature Variable Sequence Prediction (8) - Prediction Model Based on SSA Optimized by Sparrow - CEEMDAN-SSA-BiLSTM Prediction Model
Multi-feature variable sequence prediction (11) - Pytorch-based TCN-GRU prediction model  
VMD + CEEMDAN secondary decomposition, CNN-LSTM prediction model  
VMD + CEEMDAN secondary decomposition, CNN-Transformer prediction model  
VMD + CEEMDAN secondary decomposition, Transformer-BiGRU prediction model  
Prediction model based on the Penghu optimization algorithm SSA - complete code kit  
Superior combination prediction model!
High innovation | CEEMDAN + SSA-TCN-BiLSTM-Attention prediction model  
Superior combination prediction model!
Lowest price online | continuous updates for the whole family!  
| Based on TCN-SENet + BiGRU-GlobalAttention parallel prediction model
Secondary decomposition - innovative model prediction full kit  
BiTCN-BiGRU-CrossAttention integrated spatiotemporal features high innovation prediction model  
Combination prediction update | Superior combination prediction model!  
Spatiotemporal feature integration BiTCN-Transformer parallel prediction model  
| Based on multi-level attention mechanism parallel prediction model
CEEMDAN-CNN-GRU-GlobalAttention + XGBoost combination prediction  
Multi-step prediction series | LSTM, CNN, Transformer, TCN, serial, parallel models collection  
END  
\t2. Friends who like can click to follow, give the article a "like", share on WeChat or discuss groups

## Images

<!-- PAYMENT_BLOCK -->

## Get this dataset

- Payment link (Stripe): [Buy now](https://buy.stripe.com/3cs8yP7sY87d0vu9AB)
- Payment QR code: ![Payment QR code](pay.png)

<!-- /PAYMENT_BLOCK -->
