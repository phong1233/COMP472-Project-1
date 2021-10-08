# Task 1: Text Classification

1. Download the BBC dataset provided on Moodle. The dataset, created by [Greene and Cunningham, 2006],
is a collection of 2225 documents from the BBC news website already categorized into 5 classes: business,
entertainment, politics, sport, and tech.

2. Plot the distribution of the instances in each class and save the graphic in a file called BBC-distribution.pdf.
You may want to use matplotlib.pyplot and savefig to do this. This pre-analysis of the data set will
allow you to determine if the classes are balanced, and which metric is more appropriate to use to evaluate
the performance of your classifier.

3. Load the corpus using load files and make sure you set the encoding to latin1. This will read the file
structure and assign the category name to each file from their parent directory name.

4. Pre-process the dataset to have the features ready to be used by a multinomial Naive Bayes classifier. This
means that the frequency of each word in each class must be computed and stored in a term-document
matrix. For this, you can use feature extraction.text.CountVectorizer.

5. Split the dataset into 80% for training and 20% for testing. For this, you must use train test split with
the parameter random state set to None.

6. Train a multinomial Naive Bayes Classifier (naive bayes.MultinomialNB) on the training set using the
default parameters and evaluate it on the test set.

7. In a file called bbc-performance.txt, save the following information: (to make it easier for the TAs, make
sure that your output for each sub-question below is clearly marked in your output file, using the headings
(a), (b) . .. )
    - (a) a clear separator (a sequence of hyphens or stars) and string clearly describing the model (e.g. “Multi-
nomialNB default values, try 1”)
    - (b) the confusion matrix (you can use confusion matrix)
    - (c) the precision, recall, and F1-measure for each class (you can use classification report)
    - (d) the accuracy, macro-average F1 and weighted-average F1 of the model (you can use accuracy score
and f1 score)
    - (e) the prior probability of each class
    - (f) the size of the vocabulary (i.e. the number of different words1)
    - (g) the number of word-tokens in each class (i.e. the number of words in total2)
    - (h) the number of word-tokens in the entire corpus
    - (i) the number and percentage of words with a frequency of zero in each class
    - (j) the number and percentage of words with a frequency of zero one in the entire corpus
    - (k) your 2 favorite words (that are present in the vocabulary) and their log-prob

8. Redo steps 6 and 7 without changing anything (do not redo step 5, the dataset split). Change the
model name to something like “MultinomialNB default values, try 2” and append the results to the file
bbc-performance.txt.

9. Redo steps 6 and 7 again, but this time, change the smoothing value to 0.0001. Append the results at the
end of bbc-performance.txt.

10. Redo steps 6 and 7, but this time, change the smoothing value to 0.9. Append the results at the end of
bbc-performance.txt.

11. In a separate plain text file called bbc-discussion.txt, explain in 1 to 2 paragraphs:
    - (a) what metric is best suited to this dataset/task and why (see step (2))
    - (b) why the performance of steps (8-10) are the same or are different than those of step (7) above.
In total, you should have 3 output files for task 1: bbc-distribution.pdf, bbc-performance.txt, and
bbc-discussion.txt.