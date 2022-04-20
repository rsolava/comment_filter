## **MVP**

### Filtering comments for online harassment
### Ryan Solava

The goal of this project is to classify youtube comments as online harassment or not, using deep learning methods.
The following results are on a dataset of 159686 comments from a variety of
platforms.

For this initial stage, I  used some NLP techniques to get a set of 20 topics based on the text of the comment. (Cleaned and lemmatized the text, used TFIDF to get the document term matrix, used LDA to do dimensionality reduction down to 20 topics.)

From this feature, I compared two models.  As a baseline, I build a classifier using the tree based, XGBoost model. It performed with a .673 F2-score. The other model was a simple feed forward model with no transfer learning with 2 hidden layers, each with 4 nodes. This model achieved an F2-score of .709. Even with simple models, the deep learning method was an improvement over the tree based model.

Additionally, an RNN with an LSTM layer with 5 nodes and a dense layer with 5 nodes was trained
on the word sequences directly. This model performed less well, with an F2-score
of only .377. By leveraging transfer learning or a more complex RNN, I am hopeful
the RNN will outperform the other models.

The ROC for these three models are shown below.

The next step is to improve the RNN model by using transfer learning.

![ROC for tree methods vs. Deep Learning methods](model_comparison2.png)
