## **Detecting Toxicity with Deep Learning**

### Ryan Solava

#### Abstract
In this project, we use deep learning to determine
if a social media comment is online harassment or not. The recurrent neural
networks with pre-trained embedding perform the best, and outperform the
baseline NLP models.


#### Design

Online harassment is a serious concern. The CDC reported in 2019 that 15.7% of
high schoolers experienced online harassment in a 12 month period. Online platforms
bare some responsibility for dealing with this issue. While some moderation can
be done by hand, a way to detect if text constitutes online harassment automatically
would be useful. While natural language processing could be used for this problem,
we found that deep learning methods outperformed those models.



#### Data
The first dataset is a collection of approximately 3,500 YouTube comments.
Each comment has been tagged as online harassment or not.

The second dataset is a collection of comments from a variety of platforms. There
are approximately 150,000 comments, which have also been tagged as online
harassment or not.

Both datasets can be found at the following link.
[here](https://data.mendeley.com/datasets/jf4pzyvnpj/1).

Additionally, the Google News pre-trained embedding was used for transfer learning.


#### Algorithms

* The baseline model was a NLP model. TFIDF was used to create the document term
matrix, and LDA was used for used for matrix decomposition. These topics were then
fed into an XGBoost tree model.
* The topics were also used in a simple feed forward neural network.
* A simple RNN with bidirectional LSTM was trained without transfer learning.
* A variety of RNN's were trained with transfer learning. The best performing model
began with the pretrained embedding followed by
an LSTM layer with 100 nodes and then two dense layers with 50 and 20 nodes.

#### Tools

* **Python, Pandas, and Numpy** for standard data science tools
* NLP Tools:
  * **sklearn** for TFIDF and LDA
  * **spaCy** for preprocessing
  * **scattertext** for visualization
* Keras for deep learning models


#### Communication

A summary of my project and results can be found on my slides, and were discussed
in my presentation. Also, my code and visualizations are posted to my
[personal GitHub](https://github.com/rsolava/comment_filter). Specically, you can find
a scattertext visualization showing which words are common in each type of comment.
Note that this visualization contains profanity and hate speech, since these
are common in online harassment.
