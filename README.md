# Fall 2021 Erdös Institute Bootcamp Project

[Project description](https://drive.google.com/file/d/1ykcpZqmNYM0kdiwBdGjKAsH6VgHvs5_o/view?usp=sharing)

Given a financial forum of our choice, we must predict the interest of a post. We must define what "interest" means, and it should be something directly related to the post itself. Selecting the subreddit [**r/personalfinance**](https://www.reddit.com/r/personalfinance/), one readily available measure of the interest is the score (# upvotes - # downvotes). 

Our work is partitioned into the following steps, with corresponding Jupyter Notebooks:

* Data Collection
* Data Exploration
* Data Preparation
* Machine Learning

## Data Collection

We download data a year's worth of posts from **r/personalfinance** (around 130K posts total). We collect the following information about each post:

* id
* user
* title text
* body text
* date
* time
* number of comments
* score
* when the author created their account
* number of comments the author had made prior to the post
* number of submissions the author had made prior to the post
* max and median scores of the author's comments prior to the post
* max and median scores of the author's submissions prior to the post

## Data Exploration

We create plots concerning

* Basic Statistics of Score and Number of Comments
* The Relationship between Score and Number of Comments
* Temporal Data

## Data Preparation

Along with cleaning the data, we add the following derived features:
* title length (number of characters)
* body text length
* account age (days)
* minutes into the day the post was made
* day of week
* whether it is the morning
* whether it is the weekend

## Machine Learning

The notebook we used to experiment with various models.

We use a pretrained word2vec model (GoogleNews) to generate 300-dimensional "document vectors" for each title and each body text. We then use Principle Components Analysis to convert these to 15-dimensional vectors. We thus add 30 columns to the data, attempting to capture semantic information in the posts. We then experiment with various algorithms, with the most success coming from XGBoost.

