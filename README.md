# Restaurant Recommendation System based on Yelp Dataset

## Link to view the project slides: https://github.com/27saniya/Restaurant-Recommendation-System/blob/main/Restaurant_Recommendation.pdf
## Installation
Download the zipped folder and navigate to the root folder. 

## For data extraction. Please be patient it might take some time to download the data.
Run - python setup.py extract

## Create a Virtual Environment to install dependencies

#### For Mac, run the following command 

1. python3 -m venv myenv
2. source myenv/bin/activate

#### For windows, run the following command
1. python -m venv myenv
2. myenv\Scripts\activate


## Project Dependencies
1. After activating the enviroment, run the following command
`pip install -r requirements.txt`



## For EDA and Preprocessing dataset (We already performed EDA on given dataset and cleaned dataset provided in data folder), run the following command
python source/data_preprocessing.py

## Development
We have implemented 4 model to  explore all dimension of yelp dataset. Each model using different set of data to recommend restaurant.

--------------------------------------------------------------------------------------

## 1. Review Base Model
### Restaurant Recommendation based on query ex. "I want to for pizza place"
Run - python source/review_rec.py "I want to go for pizza place"

### For Train Model (We already trained our model and pickle file is in data folder)
python source/train_review_model.py

## 2.Restaurant Recommendation system with Memory Based Collaborative Filtering
Memory based Collabortaive Filtering filters the items in a collaborative way for a user, based on the preferences of similar users. In this system cosine similarity method is used to find the top 10 recommended businesses for a user based on the features.

### To run the memory based recommender, execute the following command in your terminal:
python source/memory_based_recommendor.py

The script will download the required data files if they don't already exist and then prompt you to choose between different options.

### Usage
When you run the recommender, you will be presented with the following options:

1. Recommend restaurants for a user
2. Find RMSE for User-based Recommendation system (WARNING: This will take about 2 minutes)
3. Exit


###  Recommend restaurants for a user
To recommend restaurants for a user,choose option 1. You will then be prompted to select a user ID from the sample user IDs or enter a user ID manually (You can select the sample user at option 1 to get the same restaurant recommendations as in the report). The system will generate a list of the top 10 recommended restaurants for the selected user based on their preferences.

### Finding RMSE for User-based Recommendation System
To find the Root Mean Squared Error (RMSE) for the User-based Recommendation system, choose option 2. Please note that this process may take about 2 minutes to complete. The RMSE is a measure of the accuracy of the recommendation system based on the test data.

### Exiting the Recommender
To exit the recommender, choose option 3. Thank you for using the Restaurant Recommender!

--------------------------------------------------------------------------------------
## 3. Restaurant Recommendation System - Content Based Filtering

Content-based modeling in restaurant recommendation systems is a technique used to provide personalized recommendations to users based on the characteristics of the restaurants and the preferences of the users.
<br>

## Run
`python source/content_recommendation.py`

##### If you face version error in pytorch then please install pytorch using below commands for your OS. Else it is not required.
For MacOS : `pip3 install torch torchvision torchaudio` <br>
For Windows: `pip3 install torch torchvision torchaudio` <br>
For Linux: `pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cpu`


## Usage:
1. Enter the Restaurant Name (Ex: Starbucks) for Getting the Recommendation
2. Enter the Number of Recommendations which you find Relevant
3. Enter q to exit or enter business name for new recommendation.

<br>
--------------------------------------------------------------------------------------

## 4. Hybrid Model (Knowledge Based Filtering+ Content Filtering using LDA + User-Item based Collaborative Filtering using SVD)

A hybrid approach recommendation systemleverages the strengths of different recommendation methods to overcome their limitations. Here, we are randomly selected the userid, in real scenario we can get recommendation for specific username or userid.

### For Restaurant recommmendation for Chinese restaurant in Philadelphia, run the following command. This file takes the trained svd model pickle file.

python source/hybrid_recommendation.py

### For Restaurant recommendation based on specific cuisine and city, run the following command with specific cuisine and city name:

python source/hybrid_training_model.py [cuisinename] [cityname]

For eg, python source/hybrid_training_model.py italian Norristown

This will model uses knowledge based filtering provided by the user and then trained the model with relevant data, it takes 3-4 minutes to get the recommendations.

<br>

--------------------------------------------------------------------------------------

## Future Enhancements

- To integrate all Models and Design of a graphical user interface (GUI)

---------------------------------------------------------------------------------------

## Built With
- pandas - Data manipulation and analysis library
- NumPy - Numerical computing library
- scikit-learn - Machine learning library
- gdown - Downloading files from Google Drive



