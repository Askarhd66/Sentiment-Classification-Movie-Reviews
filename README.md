<h1>🧠 Sentiment Classification Using Wordlists & Naive Bayes</h1>

<h2>🎯 Project Overview</h2>
This project investigates sentiment analysis techniques for movie reviews, classifying them as <b>Positive</b> or <b>Negative</b>.  
It compares two approaches:

- A <b>Wordlist Classifier</b> built from content words extracted from training data  
- A <b>Naive Bayes Classifier</b> constructed from token frequency distributions  

The project includes data preprocessing, content‑word extraction, classifier construction, evaluation, and experimentation with wordlist length.

<h2>🛠 Languages & Libraries</h2>
<ul>
  <li>Python</li>
  <li>NLTK</li>
  <li>NumPy</li>
  <li>Matplotlib</li>
  <li>Jupyter Notebook</li>
</ul>

<h2>📊 Dataset Overview</h2>
The dataset consists of movie reviews labeled as <b>positive</b> or <b>negative</b>.  
Each review is tokenized, normalized, and lemmatized before analysis.

Key preprocessing steps:
- Stopword removal (NLTK + extended custom list)
- Lemmatization
- Removal of punctuation, numbers, and movie‑specific neutral terms
- Normalization of training and testing data

<h2>📝 1. Identifying Content Words</h2>

<b>Positive content words (Top 10):</b>  
<code>['good', 'great', 'love', 'fun', 'interesting', 'perfect', 'beautiful', 'pretty', 'classic', 'humor']</code>

<b>Negative content words (Top 10):</b>  
<code>['bad', 'worst', 'wrong', 'boring', 'poor', 'worse', 'hell', 'waste', 'dull', 'terrible']</code>

<b>Explanation:</b>  
Content words were extracted by:
- Normalizing all tokens  
- Removing stopwords and irrelevant terms  
- Using positive/negative lexicons  
- Computing frequency distributions within each sentiment class  

These words form the basis of the wordlist classifier.

<h2>🧮 2. Wordlist Classifier</h2>

A simple classifier was built using the extracted positive and negative wordlists.

<b>How it works:</b>
- For each review, a sentiment score is computed  
- Positive word occurrences increase the score  
- Negative word occurrences decrease the score  
- Score > 0 → <b>Positive</b>, otherwise <b>Negative</b>

This classifier is lightweight and interpretable but limited by vocabulary coverage.

<h2>📈 3. Classifier Performance Evaluation</h2>

Confusion Matrix:
- <b>TN:</b> 78  
- <b>FP:</b> 222  
- <b>FN:</b> 18  
- <b>TP:</b> 282  

<b>Performance Metrics:</b>
- <b>Accuracy:</b> 60.0%  
- <b>Precision:</b> 55.95%  
- <b>Recall:</b> 94.0%  
- <b>F1 Score:</b> 70.15%  

<b>Is accuracy a reasonable metric?</b>  
Accuracy is useful for balanced datasets, but misleading for imbalanced ones.  
Example: In medical diagnosis, predicting all patients as “healthy” may yield high accuracy but catastrophic recall.

<h2>🤖 4. Naive Bayes Classifier</h2>

A custom Naive Bayes classifier was implemented using:
- Vocabulary extraction  
- Prior probability estimation  
- Conditional probabilities with Laplace smoothing  
- Posterior probability calculation for classification  

<b>Performance:</b>
- <b>Accuracy:</b> 81.33%</b>
- <b>Precision:</b> 80.52%</b>
- <b>Recall:</b> 82.67%</b>
- <b>F1 Score:</b> 81.58%</b>

<b>Comparison:</b>
- Naive Bayes significantly outperforms the wordlist classifier  
- Wordlist classifier has high recall but very low precision  
- Naive Bayes is more balanced, robust, and scalable  

<h2>📊 5. Experiment: Impact of Wordlist Length</h2>

An experiment was conducted by varying the number of top content words (between 29 and 174).

<b>Findings:</b>
- Accuracy increases as wordlist length increases  
- Gains diminish after a certain threshold  
- Example:  
  - 35 words → 0.62 accuracy  
  - 99 words → 0.65 accuracy  

<b>Conclusion:</b>  
Longer wordlists improve performance, but only up to a point.  
Beyond that, additional words add noise rather than value.

<h2>🏆 5b. Final Recommendation</h2>

<b>I recommend using the Naive Bayes classifier for future work.</b>

Reasons:
- Much higher accuracy (81% vs 60–65%)  
- Probabilistic and robust  
- Uses full vocabulary instead of a fixed wordlist  
- Scales well to larger datasets  
- Better balance between precision and recall  

<h2>📁 Repository Structure</h2>

<pre>
📦 sentiment-classification-movie-reviews
│
├── README.md
├── notebook/
│   └── sentiment_analysis.ipynb
├── data/
│   ├── training/
│   └── testing/
└── resources/
    ├── positive-words.txt
    └── negative-words.txt
</pre>

<h2>📌 Summary</h2>
This project demonstrates:
- Effective extraction of sentiment-bearing content words  
- Construction of a simple interpretable classifier  
- Implementation of a full Naive Bayes model  
- Comparative evaluation  
- Experimental analysis of wordlist size  

The Naive Bayes classifier is the superior approach for sentiment classification tasks.
