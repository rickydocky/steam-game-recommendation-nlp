# Game Recommendation System Based on Steam User Review Sentiment Analysis

## Project Introduction

With the rapid development of digital game platforms, players face an increasing number of game choices. Steam, as one of the world's largest digital game platforms, possesses a massive amount of user reviews, which contain genuine feedback from players regarding game quality, gameplay experience, and overall satisfaction. However, due to the sheer volume of reviews, players find it difficult to efficiently extract valuable information in a short period, thus impacting game selection efficiency.

This project focuses on the real-world problem of "how to use Natural Language Processing (NLP) technology to help players more efficiently filter high-quality games." Based on Steam user review data, it constructs a game recommendation system that combines sentiment analysis and a recommendation mechanism. By analyzing the emotional tendencies of user review texts, the project automatically determines players' true attitudes towards games and further generates game recommendation lists to demonstrate the practical application value of NLP technology in game recommendation scenarios.

## Project Goals and Methods Overview

The core goal of this project is to mine game reputation information from user review texts and use this information to assist in game recommendations. To achieve this goal, we first cleaned and preprocessed the Steam user review data, including removing missing values, cleaning invalid characters, and standardizing the text format. Subsequently, the TF-IDF method was used to convert the comment text into numerical features that could be processed by the machine learning model.

For sentiment classification, this project selected two classic traditional machine learning models: Logistic Regression and Naive Bayes. These two methods were chosen because they offer good efficiency and interpretability in text classification tasks and are suitable for the small-scale experimental environment required by the course project. By comparing the performance of the two models on metrics such as accuracy, precision, recall, and F1-score, we selected the superior model as the final sentiment prediction model.

For recommendation, this project aggregates user sentiment information according to the game dimension based on the comment prediction results and comprehensively considers the proportion of positive comments, model prediction confidence, and the number of comments to generate the final game recommendation list.

## Dataset Description

This project uses the Steam platform user comment dataset. The dataset includes game IDs, game names, user comment text, platform recommendation tags, and comment usefulness voting information. Steam provides built-in tags for user recommendations of games, with "recommended" tagged as positive and "disliked" as negative. This allows this project to directly leverage existing platform tags for supervised learning tasks without additional manual annotation.

Compared to traditional rating data, user-generated review text more accurately reflects players' actual experiences, making it more suitable for natural language processing analysis and recommendation research.

## Project Implementation Process

The entire project implementation process consists of four main stages: data preprocessing, text feature extraction, model training and evaluation, and recommendation result generation.

In the data preprocessing stage, we first read the raw review data and remove records with missing key fields. Then, we map the platform's recommendation tags to binary classification target variables and clean the review text, including removing URLs, HTML tags, special characters, and extra spaces, thereby improving text quality.

In the feature extraction stage, we use the TF-IDF method to vectorize the review text. TF-IDF effectively highlights distinctive keywords in reviews while reducing the interference of common words on the model, making it very suitable for short text sentiment analysis tasks.

During model training, we used Logistic Regression and Naive Bayes separately, and evaluated the models based on training and test set splits. Accuracy, Precision, Recall, and F1-score were used as the main evaluation metrics, along with confusion matrix analysis to assess the model's performance in classifying positive and negative reviews.

In the recommendation generation phase, we predicted review sentiment based on the best model and aggregated the predictions for all reviews by game dimension. Finally, we combined the proportion of positive reviews, average prediction confidence, and the number of reviews to generate a more valuable game recommendation list.

## Project Output Results

The final outputs of this project include model performance comparison results, review-level prediction results, a game recommendation list, and a confusion matrix.

The model performance comparison results demonstrate the performance of different classification models across multiple evaluation metrics, providing a basis for model selection. The review-level prediction results record the predicted label and probability for each review, which can be used for further error case analysis. The game recommendation list reflects the practical application value of this project, helping players more intuitively understand which games are more worthy of recommendation. The confusion matrix is ​​used to illustrate the specific error distribution of the model in classification tasks.

## Project Operation Instructions

This project was developed and experimented on in the Kaggle Notebook environment. To run it, you first need to upload the Steam review dataset to the Kaggle input directory, and then run each part of the code sequentially according to the preset stages in the Notebook, including data reading, cleaning, sampling, model training, result evaluation, and recommendation generation.

The main Python libraries required for the project include pandas, numpy, scikit-learn, and matplotlib.

## Project Limitations and Future Improvements

Although this project has achieved good results in game review sentiment analysis and recommendation tasks, certain limitations remain.

First, traditional machine learning models have limited ability to understand contextual semantics. Methods such as TF-IDF and Logistic Regression mainly rely on word frequency information, making it difficult to effectively capture negation relationships, ironic expressions, and slang and internet slang in game reviews, which may lead to some reviews being misjudged.

Second, because the experiments use sampled data, the recommendation results may still be affected by sample distribution bias. While this project reduced small sample bias by introducing comment quantity weights, the recommendation results still have room for further optimization.

In the future, more advanced deep learning models such as BERT could be considered to enhance the understanding of contextual semantics. Simultaneously, incorporating more user behavior data, such as game time and purchase history, can further improve the accuracy and practicality of the recommendation system.

## Project Team Composition

This project was completed collaboratively by team members. Member A was primarily responsible for preliminary background research, literature analysis, and writing the first half of the report; Member B was responsible for project code implementation, model training, and experimental design; Member C was responsible for experimental result analysis, organizing the second half of the report, and preparing the project presentation content.

## Project Significance

This project demonstrates the practical application potential of natural language processing technology in user comment analysis and game recommendation scenarios. By automatically analyzing massive amounts of user comments, this project can help players obtain valuable information more efficiently, while also providing a feasible approach for intelligent recommendations on digital platforms.
