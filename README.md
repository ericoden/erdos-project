# Fall 2021 Erdös Institute Bootcamp Project

[Project description from Susquehanna International Group](https://drive.google.com/file/d/1ykcpZqmNYM0kdiwBdGjKAsH6VgHvs5_o/view?usp=sharing)

Given a financial forum of our choice, we must predict the interest of a post. We must define what "interest" means, and it should be something directly related to the post itself. Selecting the subreddit [**r/personalfinance**](https://www.reddit.com/r/personalfinance/), one readily available measure of the interest is the score (# upvotes - # downvotes). 

We download data a year's worth of posts from **r/personalfinance** (around 130K posts total). We collect the following information about each post:

* id
* user
* title text
* body text
* date
* time
* number of comments
* score

The resulting data frame has a little over 100MiB of data. Selecting some threshold based on the score and/or number of comments, we can partition the data into viral and nonviral posts. Then, based on the temporal, language, user, and network features, we hope to develop a machine learning model that can predict whether a post will go viral.

