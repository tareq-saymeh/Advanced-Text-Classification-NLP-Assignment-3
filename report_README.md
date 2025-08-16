methodology:

Data Preprocessing:

1- Reading Documents: The first step involved reading documents from the specified folder paths using the read_documents function each documents content was extracted along with its class label
2-Tokenization: The NLTK library was used to tokenize the text data into individual words.
3-Stemming: Porter stemming was applied to reduce words to their root form aiming to normalize the text data.
4-Filtering Tokens: Tokens were filtered based on certain criteria such as removing digits, short tokens, and non-alphabetic characters to enhance the quality of features.
5-Normalization: Slash characters were replaced with spaces to handle any inconsistencies in the data.
6-Feature Encoding: Two feature encoding techniques were utilized:
    TF-IDF Vectorization: This technique converts text documents into numerical vectors based on the frequency of terms in the document relative to the entire corpus.
    Word2Vec Embeddings: Pretrained Word2Vec embeddings from the Google News dataset were used to represent each document as a vector by averaging the word embeddings of all words present in the document
7-Scaling: min-max scaling was applied to normalize the word2Vec document vectors to ensure consistency in feature scales

Model Selection: i used TF-IDF and Word2Vec on 3 deffrent models Naive Bayes Classifier ,Support Vector Machine (SVM) and Random Forest Classifier

and the results were as follows : 
Naive Bayes:
 TF-IDF :0.037
 Word2Vec :0.030

SVM :
TF-IDF :0.239 
Word2Vec :0.164

Random Forest:
TF-IDF:0.196
Word2Vec: 0.154

Discussion:

TF-IDF vs. Word2Vec: Across all three classifiers tf_idf encoding consistently outperformed Word2Vec encoding. tf_idf focusing on term frequency and document specificity proved more effective in capturing relevant features for text classification tasks. In contrast Word2Vec embeddings, despite their ability to capture semantic meanings failed to translate into improved classification performance in this context

modl Performance: While SVM and Random Forest classifiers demonstrated superior performance with tf_idf features Naive Bayes struggled regardless of the encoding scheme This suggests that the inherent assumptions of Naive Bayes particularly its independence assumption may not hold well for the text data in this study

feature Representation: The results underscore the importance of feature representation in text classification tasks. tf_idf-IDF encoding, focusing on the frequency and importance of terms appears more suitable for this dataset compared to Word2Vec embeddings which may not adequately capture document-specific information

model Selection: The choice of classifier significantly impacted performance with svc and Random Forest outperforming Naive Bayes future investigations could explore more sophisticated models or ensemble techniques to further improve classification accuracy

overall, the results highlight the intricate interplay between feature encoding model selection and classification performance in text analysis tasks
While TF-IDF encoding emerged as the preferred choice for this dataset further experimentation and fine-tuning may be necessary to optimize performance for specific use cases


Suggestions for Future Work:

hyperparameter tuning: Further optimization of model hyperparameters could enhance classification performance Techniques like grid search or random search could be employed to systematically explore the hyperparameter space

Ensemble methods: Investigating ensemble methods such as stacking or boosting could potentially improve classification results. Combining the predictions of multiple models often leads to better generalization and robustness