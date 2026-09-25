# Group-5-DS-4002
Contains Project 1 work for DS 4002 Group 5 Fall 2026

Members: Samuel Bromberg, Inmar Chavarria, Angelika Baloy 

## Analyzing Language Patterns of IMDb Reviews 

## Software and platform
We are using Python and Google Colab for this project. Packages required for this analysis are numpy, pandas, matplotlib, seaborn, sklearn's Logistic Regression, and RegEx (re). 

## Documentation 
* README.md
* LICENSE.md
* SCRIPTS folder
    * IMDb_Reviews_Project.ipynb
* DATA folder
    * README.md
    * aclImdb_reviews.zip
         * test
         * train
* OUTPUT folder
    * confusion_matrix
    * top_positive_words
    * top_negative_words
    * final_lr_model_performance
    * word_count_v_tfidf
    * review_length_by_sentiment

## Instructions for reproducing results 
1. Download raw data from aclImdb_reviews.zip located in the Data folder.
3. Access the Colab script in the Scripts folder. Load in the necessary packages (numpy, pandas, matplotlib, seaborn, and re).
4. Load in the data by using pandas and read_csv. The file name is imdb_reviews.csv. 
5. Clean data by running the "Clean dataset" chunk. We removed special characters (including punctuation marks), HTML tags, and extra spaces to streamline our feature analysis. Read the comments inside the chunk and verify that the data was cleaned. 
6. Check that there are no missing values in the dataset using .isna().sum() on the review column. Check that there are no duplicates using .duplicated().sum() on the review column.
7. There should be an even number of positive and negative sentiment labels. Check this using .value_counts() on the sentiment column. There should be 25000 negative and 25000 positive reviews.
8. Likewise, there should be an even number of test and train reviews. Check this by using .value_counts() on the split column.
9. Verify that the cleaning went as expected. Pick a review using the .iloc[] function from the review_clean column and verify that the review text is all lowercase with no other characters but letters.
10. Now that the data has been processed, it is ready for analysis. Create text features by running the "Create Text Features" chunk. Make sure to import the required packages for analysis. 
