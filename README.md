# Twitter Sentiment Analysis Project (Task 4)
This project focused on applying natural language processing (NLP) techniques to the Twitter validation dataset to perform sentiment analysis and text visualization.

# Data Handling and Cleaning
The process began by loading the twitter_validation.csv dataset, which contained 999 entries. An initial inspection confirmed the data's quality, as all columns were found to have 999 non-null counts, meaning no missing values were present.
A crucial data preparation step was the application of a custom clean_text function to the relevant text column . This function performed several key cleaning operations to standardize the text for analysis:
-It removed URLs and web links.
-It stripped Twitter mentions (@\w+) and hashtag symbols (#).
-It removed all characters except English letters and spaces.
-It converted all remaining text to lowercase.

# Sentiment Analysis Implementation
The cleaned text was then processed using the TextBlob library to derive sentiment scores.
-Polarity Calculation: The get_sentiment function calculated a numerical polarity score for each text entry, which ranges from -1.0 (highly negative) to +1.0 (highly positive).
-Sentiment Classification: A sentiment_label function was used to categorize the numerical polarity score into three discrete labels: 'Positive' (score > 0), 'Negative' (score < 0), and 'Neutral' (score = 0) .

# Results and Visualization
The final sentiment analysis revealed a highly uniform distribution of sentiments across the dataset.
-Sentiment Distribution: The key finding was that 100.0% of the 999 analyzed entries were classified as 'Neutral'.
-Polarity Visualization: This finding was visually reinforced by a lineplot of the polarity over the tweet index, which showed a completely flat line at 0.0.
-Word Cloud: A Word Cloud was generated from the cleaned text classified as 'Neutral' . The dominant words displayed were primarily brand names and titles of games such as google, amazon, csgo, fifa, grandtheftautogta, and microsoft . The highly specific nature of the cleaned text (which often reduced the tweets to single or compounded product names) likely caused the TextBlob library to assign a 0.0 polarity score, leading to the uniform 'Neutral' classification for the entire dataset .
