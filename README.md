# TAMU-PETE-689-ML
Final project for the Class PETE-689-Machine Learning and Data Science during Spring-2022 semester is shared below.

Final Project:
+ Objective: Predict well deliverables and economic metrics by using python-based ML/DA workflow
+ Task: Develop regression model that effectively predicts key well deliverables from available data (well_data). 
Use the following regression techniques: 
1. Elastic Net
2. Support Vector Regressor
3. Random forest
4. Gradient Boosting Regressor
5. Neural Network

+ Dataset and Tasks
Dataset is an excel file with two sheets:
- Data1_Completion
The dataset comprises of well completion variables (features) such as: permeability, pay thickness, fluid Intensity, sand Intensity, number of stages, perforation clusters, fracture conductivity etc.
- Data2 
The dataset comprises of different well deliverables and economic metrics. Data-driven model needs to be built to predict these deliverables/metrics.

+ As general Conclusions we found:

 - The established pre-processing workflow has reduced the number of features from 15 to 7 features that have direct relationships to the well deliverables and economic metrics.
   
- All of the implemented regressors are acceptable since they all yielded high memorization and generalization R2 scores with least differences betweem them. This is due to the successful implementation of the pre-processing strategies applied to the raw data, and the attentive selection of the important features through collinearity and quantity association analysis between the features and the targets.
  
- Elastic Net regressor is the simplest data-driven model among the other models, and it is considered as a benchmark model in this study.

- Due to the complex nature of the completion data and the heterogeneity that exists intrinsically in unconventional reservoirs, the high-complexity regressors were the ones that performed the best in predicting the well deliverables and economic metrics; with Gradient Boosting regressor being the best regressor with astounding results to be the most generalizable data-driven model, then the neural network regressor with a single hidden layer and 120 neurons is the second best after the GB regressor, then lastly the support vector regressor is the third best model to establish a better relationship between the features and the targets that facilitates the predictability of the model.

+ On the models deployment:
- Four important parameters that concern completion engineers are investigated in this section to make the comparisons between their performances on well deliverables and economic metrics, these parameters are Perforation Clusters, Number of Stages, Well Spacing, and Sand Intensity (Proppant Concentration).

- It can be observed that all regressors agree on the same predictions of well deliverables and economic metrics, except for the support vector regressor where it underestimates the total well cost compared to gradient boosting and neural network regressors, and that is due to the low memorization and generalization R2 scores during the training and testing stages in Notebook 1.

- However, due to the absence of well deliverables and economic metrics in the current dataset (deployment dataset), it is hard to substantiate whether any of the regressors made the right predictions on total well cost.
  
- It is difficult to establish general trends and relationships between well deliverables and completion parameters from the given number of wells (500 - 600), we need more data on more wells to be able to make decisions based on data-driven models predictions. 

+ Other secondary conclusions:
  Regarding feature engineering:

- From descriptive statistics: We can conclude that the true verical depth (TVD), injection rates, and permeability can be dropped from the dataset since they have a standard deviation of zero, and hence, they are not descriptive parameters to predict well deliverables and economic metrics.

- From collinearity analysis: Most of the parameters in the target dataset (well deliverables and economic metrics) have high collinearity, and hence, they are highly correlated to each other, and predicting one parameter will directly predict the other. Therefore, we only consider as target parameters:  Well deliverables: IP90 Gas, Gas (EUR); Economics metrics: Total Well Cost, Effective IRR and Recycle Ratio.

-  From collinearity analysis: Among features that are collinear lateral length is removed since this parameter can be obtainined from number of stages and cluster spacing. Also, fluid intensity is removed since it can be related to fracture half-length and fracture conductivity along with proppant intensity.
  
- From association tests (F-tests and MI-tests): The desired targets have very low quantity association with LL multi, sand concentration model, and pay thickness. And therefore, we can remove these features from the completion dataset.
