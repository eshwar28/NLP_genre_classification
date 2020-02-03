# Multilabel classification of research paper genres

# Requirements:
* Numpy
* Pandas
* nltk(Natural Language Toolkit)
* gensim
* re(for Regular Expression Operations)
* ast(Abstract Syntax Trees)

#D ata:
* The data here is from the articles published on arXiv in the Astrophysics domain.
* The Data_Train.csv file has the columns:
 * 'Title': The title of the articles.
 * 'Date': The date the article was first posted to the arXiv.
          In Data_Train.csv the dates are all before May 2019, and in Data_Test.csv the dates
          are all greater than or equal to May 1, 2019.
 * 'Abstract': The abstract of the article.
 * 'Subjects': The subject of the article, as described by the author. This field is only present in
              Data_Train.csv.

# Aim:
To predict the number of articles in each subject for articles in Data_Test.csv and also 
to predict the number of articles in each subject in every month of Data_Test.csv

# About:
* After loading of the train data we converted the string representation of a list to list 
  in the 'Subjects' column and then applied One Hot Encoding to the subjects using MultiLabelBinarizer.
* Various pre-processing of the different columns was done and the text was cleaned by 
  clean_text() function and applying 'lambda' function to the column for cleaning.
* Stopwords such as 'the' 'and' etc. were removed to focus on the other words which could be more useful
  and their frequencies were plotted. 
* tfidf vectorizer was used to create top 10000 most important words and create a feature vector out of these selected words.
* Porter Stemming was used to link a specific word to its root of words .
* Finally this dataset was trained on an SVM model and 'F1' score was used as a metric to get the score.

# How to Use:
Clone the current repository and navigate into Accrete-AI.ipynb notebook to run it.
# Result:
Finally we got F1 score of 0.758 on our test data.
