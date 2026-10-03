# Conclusion

Our analysis examined language patterns in 50,000 IMDb movie reviews to determine which features are useful for distinguishing positive and negative sentiment.

Positive and negative reviews were very similar in length. Negative reviews averaged about 229.5 words, while positive reviews averaged about 232.8 words. This suggests that review length alone is not a strong indicator of sentiment and that the words used in the reviews are more useful to examine.

We compared Word Count and TF-IDF using 5-fold cross-validation on the training data. Word Count achieved an average accuracy of 81.66%, while TF-IDF achieved 86.02%. Since TF-IDF performed better, it was selected for the final logistic regression model.

The final logistic regression model was evaluated on the 25,000 testing reviews. It achieved 87.95% accuracy, 87.72% precision, 88.26% recall, and an F1 score of 87.99%. The model exceeded our original goal of at least 85% test accuracy.

The confusion matrix shows that the model correctly classified most positive and negative reviews. It correctly predicted 10,955 negative reviews and 11,032 positive reviews, while 3,013 reviews were misclassified. This shows that the model performed similarly across both sentiment groups.

The word analysis showed clear differences between the two sentiment groups. Words such as "great," "excellent," "perfect," and "wonderful" were strongly associated with positive reviews. Words such as "worst," "waste," "awful," and "boring" were strongly associated with negative reviews.

Overall, the results show that positive and negative IMDb reviews contain distinguishable language patterns. Review length was very similar between the groups, while specific word usage provided more useful information for identifying sentiment. TF-IDF performed better than raw Word Count, and the final logistic regression model achieved 87.95% accuracy on the test data. These results support our conclusion that word usage is useful for distinguishing positive and negative IMDb movie reviews.
