# Heart-Disease-Prediction

#### Goal: To create a POC using Flask, HTML and CSS for predicting whether a person is suffering from Heart Disease or not, implementing Machine Learning algorithm.

### About the Data set: 
This is a machine learning project where we will predict whether a person is suffering from heart disease or not. 
The dataset was downloaded from [Kaggle](https://www.kaggle.com/ronitf/heart-disease-uci). The dataset has 13 independent features like:
1. age
2. sex
3. chest pain type (4 values)
4. resting blood pressure
5. serum cholestoral in mg/dl
6. fasting blood sugar > 120 mg/dl
7. resting electrocardiographic results (values 0,1,2)
8. maximum heart rate achieved
9. exercise induced angina
10. oldpeak = ST depression induced by exercise relative to rest
11. the slope of the peak exercise ST segment
12. number of major vessels (0-3) colored by flourosopy
13. thal: 3 = normal; 6 = fixed defect; 7 = reversable defect 

The target column says whether the person is having the disease or not based on the above features.
The target has two values 1(having the diease) and 0(not having the disease). A binary classification problem statement.

### Project Description:
After loading the dataset("heart.csv") the first step was to perform an extensive Exploratory Data Analysis(EDA).
The EDA part comprises of creating countplots for the target feature to check whether the dataset is balanced or not.
It was a balanced dataset. Density plots were made to check the distribution of each features.
Similarly, histograms were made for the same purpose. Boxplots were created for outliers detection. Some amount of outliers present in few features.
Then, a correlation heatmap was made to check the correlation between all the features.
Kernel density estimator plots were made for having a better visualization about the data distribution.
Scatter plots and distplots were among the others plots that was also helpful.

The second step was to perform Feature Engneering. The initial step was to check for null values. Then, the data was divided into categorical and numerical features and One hot encoding was performed on the categorical features.
Feature Scaling using Sklearn's Standard Scaler was performed on features 'trestbps', 'chol', 'thalach'. 

The third step was Feature Selection. As the dataset had only 13 idependent features, features were selected manually based on domain knowledge.
'cp', 'trestbps', 'chol', 'fbs', 'restecg', 'thalach', 'exang' were the features that got selected.

The Forth step was Model Building. The dataset was divided into independent(X) and dependent(y) features. Train test split was performed for getting the train and test datasets.
KNearestNeighbors classifier was applied on the training data after testing with other Machine Learning algorithmns. Initially the k value was set to 1. Predicton and validaion was performed on the test dataset.

The fifth step was to perform Hyperparameter Optimization on our model. A range of k values was set and based on error and accuracy rate the best k value was selected.
The main aim was to reduce the False Positives and the False Negatives. Model performed really good and validated based on classification report, confusion matrix and accuracy score.

The final step was to save the model as a pickle file to reuse it again for the Deployment purpose. Joblib was used to dump the model at the desired location.

The "Heart Disease Prediction.ipynb" file contains all these informations.

### Deployment Architecture:
The model was deployed locally (port: 5000). The backend part of the application was made using Flask and for the frotend part HTML and CSS was used.
I have not focussed much on the frontend as I am not that good at it. The file "app.py" contains the entire flask code and inside the templates folder, "heart.html" contains the homepage and "result.html" contains the result page. 

### Installation:
The Code is written in Python 3.7.3 If you don't have Python installed you can find it [here](https://www.python.org/downloads/). If you are using a lower version of Python you can upgrade using the pip package, ensuring you have the latest version of pip. To install the required packages and libraries, run this command in the project directory after [cloning](https://www.howtogeek.com/451360/how-to-clone-a-github-repository/) the repository:

##### 1. First create a virtual environment by using this command:
```bash
conda create -n myenv python=3.7
```
##### 2. Activate the environment using the below command:
```bash
conda activate myenv
```
##### 3. Then install all the packages by using the following command
```bash
pip install -r requirements.txt
```
##### 4. Then, in cmd or Anaconda prompt write the following code:
```bash
python app.py
```
##### Make sure to change the directory to the root folder.  

### A Glimpse of the application:
![Screenshot (149)](https://user-images.githubusercontent.com/75041273/133073173-c67f9e00-9ffc-42a5-83d0-04f69eda3f04.png)
![Screenshot (150)](https://user-images.githubusercontent.com/75041273/133073205-e421f491-1db9-45e7-9c4d-52d4acf151b8.png)
![Screenshot (151)](https://user-images.githubusercontent.com/75041273/133073229-94ea67ca-905a-4dc2-b73b-c90f6c251390.png)

### Further Changes to be Done:
- [ ] Including more features in the model, that might increase accuracy. 
- [ ] Deploying the Web Application on Cloud.
     - [ ] Google Cloud 
     - [ ] Azure
     - [ ] Heroku
     - [ ] AWS

### Technology Stack:

<img src="https://img.shields.io/badge/Python-FFD43B?style=for-the-badge&logo=python&logoColor=darkgreen" /> <img src="https://img.shields.io/badge/Numpy-777BB4?style=for-the-badge&logo=numpy&logoColor=white" /> <img src="https://img.shields.io/badge/Pandas-2C2D72?style=for-the-badge&logo=pandas&logoColor=white" /> ![Seaborn](https://img.shields.io/badge/Seaborn-%230C55A5.svg?style=for-the-badge&logo=seaborn&logoColor=%white)  <img src="https://img.shields.io/badge/scikit_learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white" /> <img src="https://img.shields.io/badge/Jupyter-F37626.svg?&style=for-the-badge&logo=Jupyter&logoColor=white" /> <img src="https://img.shields.io/badge/conda-342B029.svg?&style=for-the-badge&logo=anaconda&logoColor=white"/> <img src="https://img.shields.io/badge/Kaggle-20BEFF?style=for-the-badge&logo=Kaggle&logoColor=white" />  <img src="https://img.shields.io/badge/matplotlib-342B029.svg?&style=for-the-badge&logo=matplotlib&logoColor=white"/> <img src="https://img.shields.io/badge/Flask-000000?style=for-the-badge&logo=flask&logoColor=white" /> <img src="https://img.shields.io/badge/Spyder-838485?style=for-the-badge&logo=spyder%20ide&logoColor=maroon" />

REQUIREMENTS:
numpy
pandas
matplotlib
seaborn
scikit-learn
flask
template-render

