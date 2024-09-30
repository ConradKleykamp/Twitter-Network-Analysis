# Twitter-Network-Analysis
Building network graphs from Twitter API data to gain insights into connections between consumers and brands and connections between commonly used words

![image](https://github.com/user-attachments/assets/c99f4de8-5c14-4d76-9a3d-fbcd86069b61)

--- 

### Objective
This project was completed as the final project for CU Boulder's DTSA 5800 Network Analysis for Marketing Analytics course in the MS-DS program. The overarching goal of the project is to leverage network graphs to gain insight into how consumers interact with and talk about three competing brands: Nike, Adidas, and Lululemon. More specifically, by constructing network graphs based upon Twitter tweets, this project will first analyze the connections created from Twitter mentions. These mentions, e.g., @nike, @adidas, @lululemon, are typically from consumers of the brands interacting with either the brands themselves or adjacent entities. These mentions graphs will assist in identifying the users that are most centrally related to the brand. Next, this project will also create semantic network graphs, which will reveal what words in the tweets are most commonly associated with eachother. This may provide further insight into what consumers are saying about each brand. Overall, this project provided a great opportunity to learn about the development of network graphs, namely by using NetworkX.

---

### Methods
Libraries Used
- pandas
- numpy
- math
- datetime
- networkx
- pyvis
- matplotlib
- seaborn
- nltk

Twitter Mentions Network
- Creating a dictionary of all unique users
- Filtering users to include users who interact with nike, lululemon, or adidas
- Filtering users to include users who have 2+ tweets and > 100,000 followers
- Using networkx to create graphs and subgraphs of Twitter mentions network

Semantic Network
- Applying natural language processing to Twitter data
    - Removing URLs
    - Tokenizing the text
    - Reducing the number of repeated words
    - Removing stopwords
    - Feature reduction (graphing only root words)
    - Removing punctuation
    - Filtering out certain parts of speech
    - Identifying and graphing unique words

 ---

### General Results

Twitter Mentions Network

Out of the 175,077 tweets in the dataset, there were 131,663 unique users. This implies that many of the users engaged at least once with one or more of the major brands. To filter down this large number of users, only users with 2 or more tweets and at least 100,000 followers were selected. This resulted in a group of only 198 users. This concentrated group of users represents the individuals who are most active and who have the largest following on Twitter. Overall, the reduction of users resulted in a user group of 0.15% of the initial population.

By pulling the userid's of the three major brands, we can gain quick insight into which brands have the most mention activity. Nike had the vast majority of interactions, with 120,125 mentions. Following this, Adidas had 36,654 and Lululemon had only 6,294. From this, one could definitely postulate that Nike appears to be the most popular brand amongst the Twitter users. Alternatively, Nike could be the most active/engaging on this particular social media platform.

Semantic Network

Out of the 175,077 tweets in the dataset, there were 77,718 unique words. The top 10 most frequently used words were:
- 'nike'
- 'adidas'
- 'sneakerscouts'
- 'eneskanter'
- 'xbox'
- 'available'
- 'day'
- 'air'
- 'china'
- 'kingjames'

For the sake of reducing the large number of unique words, only the words that appeared more than 250 times were included. This resulted in 908 unique words, which makes up only ~1.16% of the original number of unique words.

The full, initial graph contained 908 nodes (reflecting the number of unique words) and 207,401 edges. To reduce the impact on this notebook's RAM, a function was used to only include edges of a minimum weight. As a result, the cleaned semantic network graph contained only 39,967 edges.
 
