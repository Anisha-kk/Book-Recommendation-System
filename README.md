## Overview
This project creates a Content based Book Recommendation System in Python. Given a book title, features such as genre, author, setting, characters etc are used to find and recommend similar books.
### Recommendation System
A recommendation system is an intelligent algorithm designed to suggest items based on similarity. <br>

Recommendation systems can be broadly divided into two categories:<br>

**Content-Based Filtering:** Suggests items similar to those a user has already liked. Uses features such as genre, author etc of the item selected by the user is used for finding similar items.<br>

**Collaborative Filtering:** Recommends items by analyzing the behavior of many users - methods that are based solely on the past interactions recorded between users and items in order to produce new recommendations. These interactions are stored in the so-called “user-item interactions matrix”. This method assumes that users with similar tastes will like similar items.
## Dataset
https://zenodo.org/records/4265096
## Algorithm
1. Collect the data
2. Data Cleaning - dealing with missing values, removing unwanted fields etc
3. Feature engineering - combining fields, creating new fields from existing data
4. Encoding of non numeric fields <br>
  4.1) For feature such as ISBN with numeric characters, convert directly to integer <br>
  4.2) For features such as genre which holds a list of values per row (For eg. Harry Potter and the Philosopher's Stone can belong to all of these genres - fiction,adventure,magic,children) use multi hot encoding <br>
   4.3) For features with high cardinality, encoding is done by creating embeddings using the Sentence Transformer library which is buid on BERT <br>
5. All the encodings as well as the numeric columns (after normalising) are concatenated to create a single vector for each row
6. Cosine Similarity function is used to find the similarity between the vectors and choose the top k similar titles for the given book.
## Result 
<img width="1749" height="492" alt="Screenshot (4994)" src="https://github.com/user-attachments/assets/2d429d0f-0a81-47b5-b41e-6a7615334444" />









