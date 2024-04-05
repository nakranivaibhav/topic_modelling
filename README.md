# Topic Modelling on QAnon Posts

## Introduction
This project focuses on topic modelling of QAnon posts from various social media platforms. The goal is to understand the discourse and trends within the QAnon community over time.

## Data Collection
The data for this project was collected from three different sources:
1. A dataset provided by the university conducting the test.
2. QAnon tweets from 2020-2021.
3. QAnon posts from 2017-2020, sourced from various social media platforms such as Reddit, 4chan, and 8chan.

Due to storage limitations, the combined CSV file containing data from all sources is being uploaded from Google Drive.

## Topic Modelling Approaches

### Classic Topic Modelling
In the `classic_topic_modelling` notebook, we explored two popular topic modelling techniques: Latent Dirichlet Allocation (LDA) and Non-Negative Matrix Factorization (NMF).

- LDA did not yield satisfactory results for this dataset.
- NMF, on the other hand, provided good results in identifying coherent topics.

### BERTopic Modelling
The `topic_modelling` notebook showcases the use of BERTopic, a state-of-the-art topic modelling approach.

- BERTopic demonstrated excellent performance in capturing the discourse of QAnon believers from 2017 to 2021.
- The notebook includes a temporal analysis of topics using BERTopic, allowing us to observe the evolution of discussions over time.
- Further improvements can be made by fine-tuning the various hyperparameters involved in BERTopic, as it incorporates six different models for topic modelling.

## Toxicity Analysis (Pending)
The `toxicity` notebook aims to classify each post as either toxic or non-toxic using pre-trained models from the Hugging Face Transformers library.

- The first model will label each post as toxic or non-toxic.
- The second model will further categorize toxic posts into six levels of toxicity.
- Due to limited hardware resources, this part of the project has not been implemented yet and will be completed during the internship.

## Future Enhancements
To further improve and expand this project, the following steps can be taken:

1. Fetch recent QAnon-related posts from multiple data sources to keep the analysis up to date.
2. Expand the existing pipeline to handle both real-time and batch processing, enabling online BERTopic modelling with a steady stream of data.
3. Refine the topic modeling (LDA, NMF, BERTopic) and hate speech detection models for improved accuracy and insights.
4. Develop a dashboard to visualize trends and alert on emerging threats within the QAnon community.
5. Provide recommendations for debunking conspiracies and educating users to combat the spread of misinformation.

By implementing these enhancements, we can create a more comprehensive and proactive system for monitoring and understanding the QAnon movement.
