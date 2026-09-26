# Group-5-DS-4002
Contains Project 1 work for DS 4002 Group 5 Fall 2026

Members: Samuel Bromberg, Inmar Chavarria, Angelika Baloy 

## Analyzing Language Patterns of IMDb Reviews 

We are using data from Stanford's Large Movie Reviews Dataset:

Maas, Andrew L. and Daly, Raymond E. and Pham, Peter T. and Huang, Dan and Ng, Andrew Y. and Potts, Christopher, “Learning Word Vectors for Sentiment Analysis,” Proceedings of the 49th Annual Meeting of the Association for Computational Linguistics: Human Language Technologies, p.142, June 2011. Available: http://www.aclweb.org/anthology/P11-1015.

## Software and platform
We are using Python and Google Colab for this project. Packages required for this analysis are numpy, pandas, matplotlib, seaborn, sklearn's Logistic Regression, and RegEx (re). 

## Documentation 
* README.md
* LICENSE.md
* SCRIPTS folder
    * IMDb_Reviews_Project.ipynb
* DATA folder
    * README.md
    * Access_Data
* OUTPUT folder
    * confusion_matrix
    * top_positive_words
    * top_negative_words
    * final_lr_model_performance
    * word_count_v_tfidf
    * review_length_by_sentiment

## Instructions for reproducing results 
1. Access the data by opening the Access_Data file in the Data folder. The first link is to the original study that used this data. The second link is to a Google
   Drive containing the original zip file from Maas et al. and the .csv file we used for our project, which is just the zip file in csv form. Download the .csv file. 
3. Access the Colab script in the Scripts folder. Load in the necessary packages (numpy, pandas, matplotlib, seaborn, and re) by running the first code chunk.
4. Load in imdb_reviews.csv by using pandas and read_csv. 
5. Clean data by running the Clean dataset chunk. We removed special characters (including punctuation marks), HTML tags, and extra spaces to streamline our feature analysis. Read the comments inside the chunk and verify that the data was cleaned. 
6. Inspect the data by running the Data Validation Check chunk. Check that there are no missing values in the dataset using .isna().sum() on the review column. Check that there are no duplicates using .duplicated().sum() on the review column.
7. There should be an even number of positive and negative sentiment labels. Check this using .value_counts() on the sentiment column. There should be 25000 negative and 25000 positive reviews.
8. Likewise, there should be an even number of test and train reviews. Check this by using .value_counts() on the split column.
9. Verify that the cleaning went as expected. Pick a review using the .iloc[] function from the review_clean column and verify that the review text is all lowercase with no other characters but letters.
10. Now that the data has been processed, it is ready for analysis. Create text features by running the Create Text Features chunk. Make sure to import the required packages for analysis. Separate training and testing data based on the split and based on sentiment. You should end up with 12,500 reviews per sentiment group. Negative reviews are labeled 0 and positive reviews as 1. 
11. Run the Approach 1: Word Count chunk. The CountVectorizer keeps only the top 5000 most frequent words that appear in at least 5 reviews. The word can also appear in at most 80% of the reviews. Common articles are also removed. This is fitted on the training data. View the sample words it found. 
12. Run the Approach 2: TF-IDF chunk. This is Term Frequency-Inverse Document Frequency, which gives more importance to useful words and less importance to more common words. Keep negation, as this can change the meaning of the words. Set up the TfidfVectorizer and fit on training data again.
13. Compare the approaches by running the next chunk, Compare Word Count vs TF-IDF. We compare the accuracy of the models using Logistic Regression. Observe the 5-fold cross-validation accuracies of each approach. TF-IDF performs (slightly) better.
14. Run the next chunk for the final model. This uses TF-IDF for all 25,000 training reviews.
15. Run the next chunk to use the final TF-IDF model on the test reviews. We will now move on to assessing the model's performance. 
16. Run the Evaluate Final Model chunk. Gather accuracy, precision, recall, and f1 score from the model. 
17. The next chunk creates a confusion matrix based on the model's performance.
18. Find the most important words in the reviews by running the next chunk. This should print the 20 words most associated with negative reviews as well as the 20 words most associated with positive reviews.
19. The next chunk helps visualize the top positive words by creating a bar chart. Bar size represents the size of the positive coefficients.
20. The next chunk helps visualize the top negative words by creating a bar chart. Bar size represents the size of the negative coefficients.
21. Run the next chunk to visualize the final model performance in a bar chart.
22. Visualize Word Count and TF-IDF performance by running the next chunk.
23. Observe the review length (word count) distribution by running the last chunk. Notice that there are not huge differences in word count across sentiment.
24. Read the summary at the end of the Colab notebook. The end!
