# Predicting-GPU-Memory-Clock
Predicting GPU Memory Clock with Data Cleansing, Standard EDA, Data Visualization, and Ridge Reggresion.

# Data
The data used in this repository is an GPU Specs dataset available at Kaggle through this [link](https://www.kaggle.com/code/anishthere/gpu-specs).

# Result
## From visualization, here is the dominance of GPU :
1. NVIDIA
2. AMD
3. ATI
4. INTEL

## Top 5 Product with the Best GPU Memory Performance
1. Radeon Instinct MI250
2. Radeon Instinct MI250X
3. A100 PCIe 80 GB
4. A100 SXM4 80 GB
5. H100 SXM5	

## Predicting Memory Clock Wiht Ridge Reggression
### Result Find The Best Lambda using RSME
Here the result :
1. RMSE of Ridge regression model with alpha = 0.01 is 255.7631996155254
2. RMSE of Ridge regression model with alpha = 0.1 is 255.76319842672984
3. RMSE of Ridge regression model with alpha = 1.0 is 255.76318654834023
4. RMSE of Ridge regression model with alpha = 10 is 255.7630687205319
I choose the best lambda based on the smallest value. So the lambda is 10

## interpretation Coefficient
![Project Guardian](https://user-images.githubusercontent.com/102755372/171420870-b3e28eed-d7f5-4a0d-953d-3a2250acf4ad.jpg)

MemoryClock = 435.429586 + 14.984059memSize -0.229589memBusWidth + 0.678453gpuClock + 3.318339rop

Which means that if there is an increase in the value of 1 in the MemoryClock variabel by assuming the value of other variabels constant, the MemSize will increase by 14.984059, the memBusWidth variabel decrase by 0.229589 and applies to all other variables

## R-square
R-squared for training data is 0.6184346914667324 
R square shows that the relationship between the influence of the independent and dependent variables is 0.6184346914667324  or 61% This indicates that the relationship between variables is strong. because it's more than 50%

## Residual Plot
![RESIDUAL PLOT](https://user-images.githubusercontent.com/102755372/171423102-ba0d19de-348e-4897-8ec1-d092dc002d0d.jpg)
1. Linear Variable = Yes
2. Variance Stable = No
3. Independent Residual = Yes because there is a pattern that have a closer distance with another pattern

## QQ-Plot
![QQ-PLOT](https://user-images.githubusercontent.com/102755372/171424157-98c386ef-3666-4f7c-ac1f-fc805e9b8b96.jpg)
The picture show that the variable have a linear with the line

## Testing Erorr
1. RMSE for testing data is 243.78581537564236
2. MAE for testing data is 189.07587441454473
3. MAPE for testing data is 0.1905878856633155

which mean that MAE with 189.07 means that the average prediction misses/deviates from the target variable is 189.07
and MAPE 0.19 means that further deviation of 189.07 is equivalent to 19% relative deviation from the actual data value
