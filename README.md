# This is a capstone project done during Data Science Immersive Bootcamp at General Assembly for academic purposes only.

# Introduction
Consumer reviews are abundant in today’s e-commerce setting. Yet not all reviews are perceived equally. Some seem to be more influential than the others, and are more relevant to a user’s purchasing decision. It will be helpful to understand what constitutes a helpful review. Different from sentiment analysis, this task can be difficult even for a human agent. Two reviews may both look informative, but often one was perceived as helpful and the other was not. We would like to evaluate the performance of NLP and deep learning on such task. In our problem setting, we examine Amazon reviews data, which provides an option for helpfulness votes. If choose to, a user can upvote or downvote a review on its helpfulness. For example 3=5 would mean that three people thought the review was helpful and two thought otherwise. There might be many more who saw the review but did not express their views. We approach the problem by casting it as a classification problem. Each review is labeled as “helpful” or “unhelpful”; we then predict the labels by various algorithms. Here we will use TF-IDF based Random Forest as a baseline. In addition, we ran simple-MLP and LSTM on the data and compare the outcome.

Those reviews(no votes) are increasing information value of the base data towards being non helpful which otherwise would have been dripped altogether from the analysis.The idea of this data pre processing is taking away the preferential bias of reviews which have already been marked helpful. Since a review once voted helpful will attract more helpful votes and one which has not been voted helpful may not attract any helpful votes altogether which may not actually be the Case.
Random forest and models need a ground truth to do correct classification .

This exercise helped us to set up a ground truth so that out models have higher discriminatory power to classify helpful and non helpful.

# Why this Project is Unique 
The strength of this project is its generality and implementation This is more like an end to end project for any e-commerce portal, hotel booking website, music/movie recommendation service, which captures the end users feedback in a textual form apart from some sort of star rating mechanism.
Traditionally the recommendations are driven by the explicit feedback ratings (like the 1-5 star rating) but this approach comes up with a novel approach which captures the implicit features from review text along with the actual ratings to calculate a score called average rating. 
As already mentioned, the entire project can be split into 2 main components- 
1) Predicting whether the review is helpful or not 
2) Using that information to calculate the average_rating of the product/item to make product recommendations

To tackle the problem of different scales for Predicted_Helpful(0-1), Review_Helpful(0-1) and overall rating(1-5), we have come up with weights which help in determining how to prioritize each of these quantities to calculate our final score. Finally a scaling logic has been used that translates the combination of these three quantities to a real number score between 1-5.
The selection of these weights was an empirical process since there were no live users interacting with the data and no real updates to the user preferences.
Also the data window is historical so there is always a possibility that actually the product has gone out of stock or reviews/ratings have changed since then. But after many iterations these weights were found to be giving closest recommendations that made more sense than a traditional recommendation engine when review helpfulness was also taken into account.
I have intentionally kept the stopwords intact since by removing them the accuracy was impacted significantly and this makes practical sense since small words like not, from, for can alter the meaning for 1-gram  word vectors.

# Files
review_eda.ipynb - Exploratory Data Analysis
DL_Amazon_AMI_full_model_v5.ipynb - Full Model and Recommendation of products using average calculated rating and star rating
amazon_cellphone_recommendation.pdf - Presentation 
