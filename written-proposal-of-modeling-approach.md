# Written Proposal of Modeling Approach

## Our Task

We have chosen to pursue the challenge posed by Susquehanna International Group (SIG). From the [project description](https://drive.google.com/file/d/1ykcpZqmNYM0kdiwBdGjKAsH6VgHvs5_o/view): 
> Given a financial forum of your choice, your task is to predict the interest of a post. What signals cause certain posts to explode in popularity, while others quickly fade away? For this project, you will also choose how to measure "interest." We strongly recommend selecting a metric that is directly related to the post itself.

To complete this fairly open-ended task, we have decided to develop a machine learning algorithm to predict the popularity of a post to the [r/personalfinance](reddit.com/r/personalfinance) subreddit.

## Data

We have downloaded data for all posts to the subreddit r/personalfinance from October 1, 2020 to October 1, 2021. For each post, we collect the following information:

* The title text of the post
* The body text of the post
* The date and time the post was submitted
* The number of comments
* The score (the number of upvotes - the number of downvotes)
* When the author created their account
* The number of comments the author had made prior to the post
* The number of submissions the author had made prior to the post
* The max and median scores of the author's comments prior to the post
* The max and median scores of the author's submissions prior to the post

## Definition of "Interest"

We decided to measure the interest of a post as a linear combination of the score and the number of comments. Specifically, we calculate the mean score over the data set, $\mu_s$ and the mean number of comments over the data set, $\mu_c$, and then, for each post, with score $s$ and number of comments $c$, the "virality score" is defined:

$$\frac{s}{\mu_s} + \frac{c}{\mu_c}$$


## Model

We shall develop a regression model which uses the collected features (excepting the score and number of comments) to estimate the virality score of a post. Our measure of performance will be the root mean squared error of the prediction.

We must find a way to represent the textual data. We have explored using a "bag-of-words" approach, as well as using a pre-trainined word2vec model. We plan to continue our experimentation with the efficacy of various text-encoding approaches. Some approaches will give rise to high-dimensional data (e.g., Google's pretrained word2vec model embeds a word into a 300-dimensional space), in which case it may be advantageous (in the sense of both computational and model performance) to apply dimensionality reduction techniques such as Principle Components Analysis (PCA). 

Based on our exploration of the data, we observe no evidence of a linear relationship between any of our features and the virality score. Therefore, we will explore a variety of popular machine learning algorithms which can capture nonlinear relationships (e.g., Random Forests, XGBoost, etc.). Furthermore, we shall as perform careful hyperparameter tuning, with an aim at optimizing the performance of the model. 
