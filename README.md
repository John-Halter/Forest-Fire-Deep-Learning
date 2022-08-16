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
### 2. Model Creation
___
The model was created in the Forest_Fire_Deep_Learning notebook. To create this single input with a multi-output model I used the keras functional API. This allows me to link a logistic regression model and a linear regresison model using the same inputs. After some data scaling and outlier removal I created each individual model and then with the functional API I can specify the outputs I want. 
### 3. Results
___
After tweaking and making several iterations of the model above the final results are shown below:
<p align="center">
  <img src="https://github.com/John-Halter/Image_Classification/blob/main/images/model_accuracy_loss_plot40.png" width="700" />
</p>
From the image shown the model reached an average accuracy of ~85% over 40 iterations. The reason for so many iterations is to 
compensate for the lack of data. The regression lines help clear some of the variability of the inital plots.
From these plots it still looks to seem that they are trending upward. Increasing the number of iterations can show that

<p align="center">
  <img src="https://github.com/John-Halter/Forest-Fire-Deep-Learning/blob/main/double_model.png" width="700" />
</p>

With the number of epochs increased to 50 we see more of a plateau in the average accuracy of ~90%. 
Meaning that 40-50 epochs is probably the most effective number for accuracy with this dataset. 


### How To Use Project
___
IF you just run the condition *sample_dataset* then it will run the cnn model and should output similar results to the ones posted. 

If you want to see the functionality of each function then beginning with the first condition *download_images* and set this to True while the others conditions are False.
Then continue through the conditions setting each one to True and the others False until you reach *run_cnn*
If done right the pictures will be downloaded, then the user will want to verify the images, the dataset will be split,
Then the model will be run. The file *CONSTANTS* is used to adjust several parameters used throughout the code. 

### Improvements To Be Made
___

- [ ] Increase number of images for the dataset
- [ ] Add more visualizations for multiple iterations of running model
- [ ] Change split_train_test to keep images in initial directories too
