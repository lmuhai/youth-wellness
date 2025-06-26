# Exploring Youth Wellness Through Social Media: A Cross-Platform Content Analysis

## Introduction

This research project investigates youth mental health trends and harmful behavioral patterns across major online platforms. By analyzing user-generated content from Reddit, YouTube Shorts, and TikTok, we aim to uncover how young people express and engage with issues related to mental and physical well-being in digital spaces.

## Table of Contents
- [Topic Modeling](#topic-modeling)
  - [Topic Similarity Matrix](#topic-similarity-matrix)
- [Topic Clusters](#topic-clusters)
    - [Hierarchical Topic Clustering](#hierarchical-topic-clustering)
    - [Embedding Centroids by Topic](#embedding-centroids-by-topic)
- [Sentiment Analysis](#sentiment-analysis)
    - [Sentiment Score Distribution by Subreddit](#sentiment-score-distribution-by-subreddit)
    - [Sentiment Score Distribution by Topic](#sentiment-score-distribution-by-topic)
---

## Topic Modeling

### Topic Similarity Matrix

The similarity matrices below visualizes how closely related different topic clusters are based on their content embeddings, with darker blue indicating higher similarity and lighter green indicating lower similarity. The diagonal dark blue line represents each topic compared to itself with a similarity score of 1, while off-diagonal values reveal relationships between different themes. 

The presence of both tightly connected clusters and weakly related topics suggests that youth online discussions span diverse but sometimes intersecting themes. These overlaps can indicate how multifaceted youth wellness is, with discussions about food, identity, and control appearing across both physical and psychological domains.

#### Figure 1.1: Reddit
<img src="figures/reddit_topic_similarity_matrix.png" width="1000">

Topics like “calories_exercise_weight_miles” and “weight_calories_deficit_week” show significant similarity (around 0.8), suggesting overlapping discussions around diet and physical health. Similarly, topics like “west_immigrants_migrants_nations” and “dose_effects_dph_doses” have no similarities, hence a lighter green color with a score of 0.


#### Figure 1.2: TikTok
<img src="figures/tiktok_topic_similarity_matrix.png" width="1000">

Since most of our TikTok data was scraped from hashtags like #skinnytok and #eat, it's unsurprising that many topic pairs show high similarity scores (above 0.5). These popular tags drive recurring language, trends, and shared users across videos, making it hard to cleanly partition TikTok into distinct communities.

There is one noticeable dark blue square that does not lie on the diagonal. It represents two topics made up of entirely empty captions/transcripts. This highlights a limitation of unsupervised topic modeling, minimal or missing text can form misleading clusters.

While this graph helps quantify text based relationships between different topics, it is important to interpret it cautiously, since it is based solely off of the text in the captions and transcripts of the videos and may not the videos' true context.

#### Figure 1.3 YouTube Shorts
<img src="figures/youtube_topic_similarity_matrix.png" width="1000">

> Note: Image quality is reduced for now; a higher-resolution version will be added soon.

## Topic Clusters 

### Hierarchical Topic Clustering

The graphs below show hierarchical topic clusters on a dendrogram based on semantic similarity. At a high level, it shows distinct groupings of youth wellness-related conversational topics. 

#### Figure 2.1: Reddit
<img src="figures/reddit_hierarchical_topic_clustering.png" width="1000">

In the Reddit topic hierarchy, topics about diet, exercise, and food are tightly linked, forming a cohesive branch. The diagram also unexpected links, for instance, a cluster that combines "vaccine_covid_trump_vaccines" with "cancer_fasting_chemo_glucose" suggests that youth discussions science, health, and systemic distrust often overlap. 

#### Figure 2.2: TikTok
<img src="figures/tiktok_hierarchical_topic_clustering.png" width="1000">

In the dendrogram, notably, the "chromebook" stands alone yet sits surprisingly clost to clusters driven by #skinnytok content. A distinct black branch of topics focuses on eating behaviors, containing keywords like "calories" and "protein," while a yellow branch highlights gym culture with terms such as "bodybuilding" and "bulking." The maroon cluster centered on the #brutaltruth hashtag unexpectedly aligns with both the empty caption and transcript group and a Slavic modeling cluster. Finally, an orange branch pertaining to discussions of larger body sizes remains seperate from a green cluster including the keywords "pregnant", "plussize", and "chubby."

#### Figure 2.3 YouTube Shorts
<img src="figures/youtube_hierarchical_topic_clustering.png" width="1000">

### Embedding Centroids by Topic

In the reduced embedding centroid graphs, the proximity of two topic centroids indicates that on average, documents in one topic are more similar in terms of their text to documents in a nearby topic. 

#### Figure 2.4: Reddit
<img src="figures/reddit_reduced_embedding_centroids_by_topic.png" width="1000">

The largest cluster on the Reddit centroid graph, “weight_eat_food_eating,” contains 6810 documents of the 18808 documents. Its nearest neighbors, “stalking_gang_gangstalking_gang stalking,” “proof_satire_evidence_ignorance,” and “sub_posts_comments_reddit,” reveal that despite very different themes, these groups share similar language patterns with general weight and eating discussions.

On the contrary, subtopics “weight_eating_binge_eat,” “weight_calories_deficit_week,” “eat_food_eating_meals,” and “calories_exercise_weight_miles” form a nutrition focused cluster centered on eating behaviors and disorders. This suggests that while the broad “weight_eat_food_eating” topic spans a wide variety of conversations, the adjacent subtopics represent a more content specific, semantically cohesive community.

#### Figure 2.5: TikTok
<img src="figures/tiktok_reduced_embedding_centroids_by_topic.png" width="1000">

The largest topic on the TikTok centroid graph is the topic “gonna_skinny_okay_weight,” containing 293 documents out of 1,438 documents. A majority of other topics are tightly clustered around “gonna_skinny_okay_weight”, suggesting a broad overlap in language, subject matter, and content. 

Interestingly, the “brutal truth” topics are included in this, suggesting that the “brutal truths” topics may focus more on body image or eating behaviors like the other topics. In contrast, the two empty topics, “don know___” on the far right, and “bebig__” at the top left, stand well apart, underscoring their disconnection from all other themes. 

Equally distinct is the large orange cluster, “chromebook_school_chromebooks_viral,” which naturally separates from the predominantly food and body focused topics, since it lacks overlapping keywords or subject matter.

#### Figure 2.6: YouTube Shorts
<img src="figures/youtube_reduced_embedding_centroids_by_topic.png" width="1000">

## Sentiment analysis

### Sentiment Score Distribution by Subreddit

#### Figure 3.1
<img src="figures/reddit_sentiment_score_distribution_by_subreddit.png" width="1000">

This violin plot shows how compound sentiment scores are distributed across subreddits. Each colored "violin" embeds a box plot and its width reflects the density of posts at each score. For example, r/conspiracy peaks at around zero, indicating a a mostly neutral tone, while r/loseit skewed toward +1, indicating generally positive content.

Comparing communities, the multimodal shapes of r/EDAnonymous, r/mentalhealth, and r/depression underscoring complex, mixed emotions around eating disorders and mental health. In contrast, the narrower violins for r/conspiracy and r/gangstalking suggest more uniform sentiment. Overall, this plot highlights varying emotional tones across topics and where discussions may offer support or carry greater risk for younger audiences.

### Sentiment Score Distribution by Topic


#### Figure 3.2: Reddit
<img src="figures/reddit_sentiment_score_distribution_by_topic.png" width="1000">

#### Figure 3.3: TikTok
<img src="figures/tiktok_sentiment_score_distribution_by_topic_1.png" width="1000">
<img src="figures/tiktok_sentiment_score_distribution_by_topic_2.png" width="1000">

#### Figure 3.4: YouTube Shorts
<img src="figures/youtube_sentiment_score_distribution_by_topic.png" width="1000">

> Note: Image quality is reduced for now; a higher-resolution version will be added soon.