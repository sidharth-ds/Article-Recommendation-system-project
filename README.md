# Building an Article-Recommendation-system:
* It involves building recommendation system which recomends similar articles to the readers.

### Dataset:
* It involves 2 features:
   * 1st : Article - entire content of the article 
   * 2nd : Tile - title of the article

### Methodology:
* using TEXT SIMILARITY to determine how the two text documents close to each other in terms of their context or meaning. 
    * text similarity metrics are Cosine similarity, Euclidean distance and Jaccard Similarity,...
* The common way to compute the Cosine similarity :
    * First we need to count the word occurrence in each document. 
    * To count the word occurrence in each document, we can use CountVectorizer or TfidfVectorizer functions that are provided by Scikit-Learn library.
    * cosine similarity values -- 0: less similar, 1: more similar

### Steps:
* Dump all the articles in a single list:
    * data["Article"].tolist()
* Do Vectorization: Convert a collection of raw documents to a matrix of TF-IDF features:
    * from sklearn.feature_extraction import text
    * vectorization = text.TfidfVectorizer(input=articles, stop_words="english")
    * X = vectorization.fit_transform(articles)
* Applying Cosine similarity:
    * from sklearn.metrics.pairwise import cosine_similarity
    * cos_sim = cosine_similarity(X)

### Creating a Recommendation column(new):
* choosing the top 4 more correlated articles.
* using argsort() : sorted + gets the corresponding Index of the values
* data["Title"].loc[[1, 33, 21, 5, 7]] : gets the corresponding title of the Index. 

### Conclusion:
* To create an articles recommendation system, we need to focus on "content" rather than user interest.
* Cosine similarity is a method of building recommendation systems based on the content.
* It is used to "find similarities" between two different pieces of "text" documents.
