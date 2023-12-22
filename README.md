# Abstract
This study confronts the crucial challenge of monitoring the State of Health (SOH) of Lithium-Ion Batteries (LIBs) in response to the escalating demand for renewable energy systems and the imperative to reduce CO2 emissions. 
Our research introduces innovative deep learning (DL) models, namely E-LSTM and CNN-LSTM, each tailored to forecast battery SOH.
E-LSTM integrates an encoder for dimensionality reduction and a Long Short-Term Memory (LSTM) model to capture data dependencies for precise SOH prediction. 
CNN-LSTM, on the other hand, employs Convolutional Neural Network (CNN) layers for encoding followed by LSTM layers. 
Significantly, we prioritize model interpretability by employing a game theoretic approach known as SHapley Additive exPlanations (Shap) to elucidate the output of our models. Furthermore, we develop a method based on pattern mining, synergizing with our model, to identify patterns contributing to abnormal SOH deterioration. These insights are presented through informative plots. Our proposed approach relies on the battery dataset published by the Massachusetts Institute of Technology (MIT) and showcases promising results in accurately predicting SOH values.
This contribution significantly enhances the robust and reliable monitoring of battery health within renewable energy systems, underscoring the potential impact of our approach in addressing current challenges in the field.

## Introduction
This repo contains code for the paper A Dual Approach for SOH Prediction and Event Detection
```latex
@article{slimane2024,
  title={A Dual Approach for SOH Prediction and Event Detection},
  author={Slimane Arbaoui, Ahmed Samet, Ali Ayadi, Tedjani Mesbahi, Romuald Boné},
  journal={Energy and AI:2666-5468},
  year={2024}
}
```
### Requirements

* python>=3.10.10
* tensorflow==2.11.1
* keras==2.11.0
* h5py==3.7.0


## How to Use
#### 1. Load the MIT Battery Dataset
- Download the following three files from the provided link [MIT](https://data.matr.io/1/projects/5c48dd2bc625d700019f3204):
     + '2017-05-12_batchdata_updated_struct_errorcorrect.mat'
     + '2017-06-30_batchdata_updated_struct_errorcorrect.mat'
     + '2018-04-12_batchdata_updated_struct_errorcorrect.mat'
     
     
- Execute the 'loading_data_MIT.ipynb' notebook, ensuring that the 'path_to_file' variable is set to the repository containing the downloaded files.

#### 2. Prepare the Data
Execute the 'data_preparing_MIT.ipynb' notebook to create an encoder for your data. This step is crucial for data preprocessing and dimensionality reduction.

#### 3. Generate Models
Execute the 'model_generating_MIT.ipynb' notebook to train the E-LSTM and CNN-LSTM models. After completing this step, run the 'combined_model_MIT.ipynb' notebook to integrate the LSTM model with the encoder.

#### 4. SHap Values Calculation
To gain insights into model predictions and enhance interpretability, execute the 'SHap_explaining.ipynb' notebook to calculate SHapley Additive exPlanations (Shap) values.

#### 5. Abnormal SOH Drop Detection
In this phase, we use the E-LSTM model to detect abnormal decreases in SOH. Follow the instructions in the 'Abnormal_SOH_Detection.ipynb' notebook. This notebook will leverage pattern mining techniques to identify and visualize patterns contributing to abnormal SOH deterioration.

