# Topic Modelling on QAnon Posts

## Introduction
This project focuses on topic modelling of QAnon posts from various social media platforms. The goal is to understand the discourse and trends within the QAnon community over time.

## Data Collection
The data for this project was collected from three different sources:
1. A dataset provided by the university conducting the test.
2. QAnon tweets from 2020-2021, obtained from [Qtweets](https://purr.purdue.edu/projects/qtweets).
3. QAnon posts from 2017-2020, sourced from various social media platforms such as Reddit, 4chan, and 8chan, available on [Zenodo](https://zenodo.org/records/3758479).

Due to storage limitations, the combined CSV file containing data from all sources is being uploaded from [Google Drive]([https://drive.google.com/file/d/your-file-id/view?usp=sharing](https://drive.google.com/file/d/1DcWCYXWuFmWNqlqfJT8L1OpaYuuzaI9e/view?usp=drive_link)).

There is also a very large dataset available on [Zenodo](https://zenodo.org/records/5559972) that contains a significant amount of QAnon and other social media posts. However, due to memory constraints, this dataset was not modelled in this project.

## Data Preprocessing
Before applying topic modelling techniques, the text data undergoes a comprehensive preprocessing pipeline. The [`clean_text`](https://github.com/your-repo/blob/main/preprocessing.py#L10) function performs the following steps:

1. Converts the input text to lowercase.
2. Removes emojis using regular expressions.
3. Removes double quotation marks.
4. Removes mentions (@username) using regular expressions.
5. Removes single letters and numbers using regular expressions.
6. Removes punctuation marks.
7. Removes stop words.
8. Keeps only words that are present in the English language.
9. Removes specific words related to QAnon that were found to be less informative during iterative topic modelling (defined in the `sxt` list).
10. Applies lemmatization to reduce words to their base or dictionary form.

The `sxt` list, which contains words like 'q', 'qresearch', 'qanon', 'trump', etc., was refined through multiple iterations of topic modelling. Words that did not contribute significantly to the identified topics were removed to improve the quality of the results.

## Topic Modelling Approaches

### Classic Topic Modelling
In the [`classic_topic_modelling`]([https://github.com/your-repo/blob/main/classic_topic_modelling.ipynb](https://github.com/nakranivaibhav/topic_modelling/blob/main/classic_topic_model.ipynb)) notebook, I explored two popular topic modelling techniques: Latent Dirichlet Allocation (LDA) and Non-Negative Matrix Factorization (NMF).

- LDA did not yield satisfactory results for this dataset.
- NMF, on the other hand, provided good results in identifying coherent topics.

### BERTopic Modelling
The [`topic_modelling`]([https://github.com/your-repo/blob/main/topic_modelling.ipynb](https://github.com/nakranivaibhav/topic_modelling/blob/main/topic_model.ipynb)) notebook showcases the use of BERTopic, a state-of-the-art topic modelling approach.

- BERTopic demonstrated excellent performance in capturing the discourse of QAnon believers from 2017 to 2021.
- The notebook includes a temporal analysis of topics using BERTopic, allowing me to observe the evolution of discussions over time.
- Further improvements can be made by fine-tuning the various hyperparameters involved in BERTopic, as it incorporates six different models for topic modelling.

The repository also includes a [`topic_lists`]([https://github.com/your-repo/blob/main/topic_lists.txt](https://github.com/nakranivaibhav/topic_modelling/blob/main/topics_list.txt)) file that contains pre-defined topics. These topics can be used as priors for modelling topics in a zero-shot setting using BERTopic.

## Toxicity Analysis (Pending)
The [`toxicity`]([https://github.com/your-repo/blob/main/toxicity.ipynb](https://github.com/nakranivaibhav/topic_modelling/blob/main/toxicity.ipynb)) notebook aims to classify each post as either toxic or non-toxic using pre-trained models from the Hugging Face Transformers library.

- The first model will label each post as toxic or non-toxic.
- The second model will further categorize toxic posts into six levels of toxicity.
- Due to limited hardware resources, this part of the project has not been implemented yet and will be completed during the internship.

## Dependencies
A `requirements.txt` file is provided in the repository, listing all the necessary dependencies for running the code in this project.

## Future Enhancements
To further improve and expand this project, the following steps can be taken:

1. Fetch recent QAnon-related posts from multiple data sources to keep the analysis up to date.
2. Expand the existing pipeline to handle both real-time and batch processing, enabling online BERTopic modelling with a steady stream of data.
3. Refine the topic modeling (LDA, NMF, BERTopic) and hate speech detection models for improved accuracy and insights.
4. Develop a dashboard to visualize trends and alert on emerging threats within the QAnon community.
5. Provide recommendations for debunking conspiracies and educating users to combat the spread of misinformation.

By implementing these enhancements, a more comprehensive and proactive system for monitoring and understanding the QAnon movement can be created.
