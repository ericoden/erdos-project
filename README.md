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
