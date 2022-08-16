# Forest-Fire-Deep-Learning
#### A classification and prediction forest fire model using Tensorflow, Keras and Pycharm
#### Created by John Halter

## Description of Project
___
The following project uses a multi-output neural network to classify and predict whether there is a fire and how much a fire may spread.
The reasons I wanted to make this type of project was to gain experience working with supervised learning models.
To form my dataset I combined two datasets, one taken from Portugal and the other Algeria. I wanted  to use Keras and Tensorflow to create a
single neural network that could classify and predict. After the random fire that enraged through Superior and Lousiville Colorado I wanted to see if there was a simple way to see how one could know if there would be a forest fire and if so how much one could spread. I would have liked to use Colorado data for this but there arent easily accessible datasets for Colorado.

## Software Used
___
- Python 3.10
- Jupyter Lab

## Project Structure:

### 1. Dataset Creation
___
The dataset was created by combining the two forest fire datasets. This was done in the Data_Cleaning Jupyter Notebook. The combination involved removing columns that differed from one another and combine the columns that matched. Any null values were treated by removal of the row. This process was done using pandas and the final dataframe consisted of columns Temperature, Wind, Humidity, Rain, Initial Spread Index, Actual Fire. 

### 2. Machine Learning Approach
___
Something I wanted to include in this project was a machine learning approach to both of the types of regression. The reason I did this was to determine whether a deep learning or machine learning approach provided more accuracy. For each type of regression I created a model and then verified the model using their respective assumptions. On top of this I also described the accuracy/results within each notebook. The logistic regression is in the Logistic_Regression notebook and the linear regression is in the Multivariant_Regression notebook.

### 2. Deep Learning Approach
___
The model was created in the Forest_Fire_Deep_Learning notebook. To create this single input with a multi-output model I used the keras functional API. This allows me to link a logistic regression model and a linear regresison model using the same inputs. After some data scaling and outlier removal I created each individual model and then with the functional API I linked and specified the outputs I want. The outline of the model is shown below:
<p align="center">
  <img src="https://github.com/John-Halter/Forest-Fire-Deep-Learning/blob/main/double_model.png" width="600" />
</p>
Using this model I also used KFold selection to increase the trainign and testing on the dataset since we have a small amount of data. This allowed us to get a better idea at how the model was doing for both types of regressions.
### 3. Results
___
From the machine learning approach we saw a classifying accuracy of ~60% from the logistic regression and as for the linear regression we acheived an R-Squared value of ~0.27-0.32 based on the type of selection used. The logistic regression was very similar to the machine leanring approach achieving ~60% accuracy. Although the logistic regression was similar among approaches the linear regresison was not. The deep learning approach got a 0.87 R-Squared value as opposed to ~0.27-0.32. This gives us hope that using this single model we can classify and predict at  the same time saving time and resources allowing us to better fight forest fires.

### How To Use Project
___

The project spans out using several Jupyter Notebooks. The first one that should be used is the Data_Cleaning notebook. With this ran, any of the other three notebooks can be used.

### Improvements To Be Made
___

- [ ] Use on a larger dataset
