# Report transcription

Text extracted from the author-provided course report. Figures are not reproduced and tables may lose formatting. Student identifiers and institutional email addresses are removed.

## Page 1

• Yeager Ye, Penn MCIT
Group Contributors
• Jiaqi Li, Penn MSE-AI
• Ning Qi, Penn MCIT

## Page 2

Defining the Problem: Track 2-Popularity Prediction
Given a song’s features, can you estimate its What are the key features that influence a song’s How can artists and producers use these insights
popularity score? popularity on the platform? to shape their musical decisions and increase
the likelihood of success on the platform?

## Page 3

Data collection and preparation
• Briefly describe the data used for the
analysis and outline the data
preparation process

## Page 4

Data Intro: The dataset used in this analysis is a collection of song data, likely sourced from theSpotify API, given the nature of the audio features and
metadata it contains. It represents a broad sample of tracks available on the platform.
Data Used for Analysis
-The dataset contains 114,000 rows and 21 columns initially.
-It includes both numeric and categorical features related to songs, such as:
• `song_id`, `artists`, `album_name`, `song_name`
• Audio features: `danceability`, `energy`, `loudness`, `speechiness`, `acousticness`, `instrumentalness`
• Metadata: `popularity`, `duration_ms`, `explicit`, `key`, `time_signature`, `song_genre`
Data Preparation Process
1. Removed Unnamed Column: Dropped the first column if it was an unnamed index.
2. Handled Missing Values: Removed rows with missing values (only 1 row was dropped).
3. Deduplicated Data: Removed duplicate songs based on `song_id`, resulting in 89,740 unique songs.
4. Feature Engineering:
-Created new features:
• `duration_min`: song length in minutes
• `energy_loudness`: combined energy and loudness
• `dance_valence`: combined danceability and valence
5. Encoding Categorical Variables:
-One-hot encoded `song_genre` and `explicit` columns.
6. Feature Selection:
-Used `SelectKBest` with `f_regression` to select the top 15 features for modeling.

## Page 5

Data exploration
• Briefly discuss how initial data exploration
was conducted
• Did you identify any patterns or trends in the
data? Share descriptive analytics and any
initial insights.

## Page 6

How Initial Exploration Was Conducted
- Distribution Analysis: Histogram and boxplot of `popularity` to understand its spread and outliers.
- Correlation Analysis: Heatmap of numeric features to identify relationships with popularity.
- Categorical Analysis: Compared average popularity between explicit and non-explicit songs. Analyzed top 15 genres by
average popularity.
Patterns and Trends Identified
- Popularity Distribution: Most songs have low to medium popularity (0–60), with fewer highly popular songs.
- Correlation with Popularity:
- Features like `loudness`, `energy`, and `danceability` showed weak positive correlations with popularity.
- `Acousticness` and `speechiness` had weak negative correlations.
- Categorical Insights:
- Explicit songs tend to have slightly higher average popularity than non-explicit ones.
- Certain genres (e.g., `iranian`, `romance`, `k-pop`) showed higher average popularity, suggesting genre-specific
trends.
Descriptive Analytics & Initial Insights
- The dataset is heavily skewed toward less popular songs.
- Audio features like energy and loudness may play a role in popularity, but the relationships are not strong.
- Genre and explicit content are potential influencers of song popularity and should be considered in modeling.

## Page 7

Application of statistical and machine learning techniques
Modeling approach(es)
Which model(s) worked
best for the project’s
Techniques used for the
objectives and why?
analysis

## Page 8

Modeling techniques applied: Random Forest Regressor is the best-
Four supervised regression models were trained and performing model for this project’s objectives.
compared: • It captures nonlinear relationships between
Linear Regression – baseline model, interpretable features and song popularity better than
but limited in capturing nonlinear relationships. Linear Regression.
Decision Tree Regressor – simple tree model with a • It’s less prone to overfitting compared to a
max depth of 7. single Decision Tree.
Random Forest Regressor – ensemble of decision • Random Forest is usually more robust and
trees to reduce variance and improve predictive requires less hyperparameter tuning, which
accuracy. makes it a good choice when interpretability
Gradient Boosting Regressor – sequential boosting and stability are needed.
of weak learners, typically strong in • Feature importance plots confirmed
structured/tabular datasets. meaningful predictors (like danceability,
Evaluation metrics: loudness, valence, and tempo), aligning
Models were evaluated using MSE (Mean Squared Error), with domain expectations in music
MAE (Mean Absolute Error), and R² (Coefficient of analytics.
Determination) on a held-out test set.
Model interpretation:
Feature importance and SHAP values were used for
interpretability, especially for tree-based models.

## Page 9

Interpretation of results
• Share key insights from the analysis and
discuss how the findings can help solve the
problem(s) and/or answer the business
question(s)
• What is the proposed solution(s) and/or
recommendation(s)?

## Page 10

Correlation with popularity
(sorted):
• popularity 1.000000
• loudness 0.071674
• danceability 0.064275
• time_signature 0.036898
• energy 0.013725
• tempo 0.007280
• key 0.003441
• valence -0.011508
• liveness -0.013857
• duration_ms -0.023157
• acousticness -0.038828
• speechiness -0.047086
• instrumentalness -0.127477

## Page 11



## Page 12

Popularity in relations to loudness and danceability (Top 15 Genre)
•Danceability vs
Popularity : Songs
with moderate tp
high danceability
tend to score higher.
The genre - ambient
score the most
•Loudness vs
Popularity: Songs
with moderate to
high loudness tend
to score higher. The
genre - ambient
score the most

## Page 13

• Danceability vs Popularity →
Songs with moderate–high
danceability tend to score higher.
• Energy vs Popularity → More
energetic songs usually lean toward
higher popularity.
• Valence vs Popularity → Positive
mood (valence) has a mild upward
trend with popularity.
• Tempo vs Popularity → No strong
trend, though extreme high/low
tempos appear less popular.

## Page 14

Key Findings
Popularity is strongly
influenced by measurable
features.
Top drivers:
• Energy & Danceability → lively,
upbeat tracks do better.
• Mood (Valence) → positive,
“feel-good” songs are more
popular.
• Loudness & Tempo → higher
audience engagement.
• Genre & Explicit label matter
for specific audiences.

## Page 15

Recommendations
• 1. Focus on high impact features for
popularity: danceability, energy, loud
ness
• 2. Optimize song length (~3-4 minute
s) and feature combinations (e.g., da
nce_valence)
• 3. Target explicit/non-explicit content
based on audience preferences
• 4. Prioritize promotion for genres with
high predicted popularity
• 5. Use predictive modeling to test fea
ture combinations before release
