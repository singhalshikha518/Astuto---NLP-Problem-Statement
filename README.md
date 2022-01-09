# Astuto---NLP-Problem-Statement

Problem Statement : Analyze Ecommerce Customers Review Dataset. Enhance extraction of most important Keywords/ Keyphrases which are being discussed in the review. Also, predict the Sentiment/Polarity of the text.

Approach:
Step 1: Data Gathering - Download Link to ecommerce reviews data
https://www.kaggle.com/nicapotato/womens-ecommerce-clothing-reviews/version/1?select=Womens+Clothing+ECommerce+Reviews.csv

This dataset includes 23486 rows and 10 feature variables. Each row corresponds to a customer review, and includes the variables:

1) Clothing ID: Integer Categorical variable that refers to the specific piece being reviewed.
2) Age: Positive Integer variable of the reviewers age.
3) Title: String variable for the title of the review.
4) Review Text: String variable for the review body.
5) Rating: Positive Ordinal Integer variable for the product score granted by the customer from 1 Worst, to 5 Best.
6) Recommended IND: Binary variable stating where the customer recommends the product where 1 is recommended, 0 is not recommended.
7) Positive Feedback Count: Positive Integer documenting the number of other customers who found this review positive.
8) Division Name: Categorical name of the product high level division.
9) Department Name: Categorical name of the product department name.
10) Class Name: Categorical name of the product class name.

Step 2: Data Preparation - 
1) Handling Missing Values - Removing rows where Review Text is null and Fill NA with blank in Title Column
2) Creating new column in dataset by Concatenating Title and Review Text

Step 3: KeyWord Extraction-
Used three approaches to Extract Keywords/Keyphrases. Below are the details:
1) TF-IDF - TF-IDF can actually be used to extract important keywords from a document to get a sense of what characterizes a document. These keywords can be used as a very simple summary of the document, it can be used for text-analytics, as candidate labels for a document and more. For TF-IDF keyword extraction code please have a look at TF-IDF_keywords.ipynb file
2) Yake - Yet Another Keyword Extractor - It is a novel feature-based system for multi-lingual keyword extraction, which supports texts of different sizes, domain or languages. Unlike other approaches, Yake! does not rely on dictionaries nor thesauri, neither is trained against any corpora. Instead, it follows an unsupervised approach which builds upon features extracted from the text, making it thus applicable to documents written in different languages without the need for further knowledge. For TF-IDF keyword extraction code please have a look at Yake_KeyWord_Extraction.ipynb
3) KeyBert - KeyBERT is a minimal and easy-to-use keyword extraction technique that leverages BERT embeddings to create keywords and keyphrases that are most similar to a document. For Key Bert Keyword Extraction code please have a look at KeyWordExtraction_KeyBert.ipynb file
  In KeyBert i used "use_maxsum=True" Parameter. This is Max Sum Similarity - To diversify the results, it takes the 2 x top_n most similar words/phrases to the document. Then, it take all top_n combinations from the 2 x top_n words and extract the combination that are the least similar to each other by cosine similarity.
  
 Out of alll three Approaches KeyBert Gave good results.
 
 Step 4: Output - Saved the output data frames as Excel File in Output Folder.
