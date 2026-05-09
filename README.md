# IMDB-review---Sentiment-Analysis
Comprehensive text mining pipeline implementing TF-IDF analysis, Locality-Sensitive Hashing (LSH), Bloom Filters, Collaborative Filtering, and DGIM algorithm for movie review sentiment analysis and recommendation.

## Algorithms Implemented

### 1. **TF-IDF (Term Frequency-Inverse Document Frequency)**
- Feature extraction for identifying most significant words in reviews
- Preprocessing: lowercase conversion, punctuation removal, stopword elimination, lemmatization
- Identifies key terms like "masterpiece," "mindbending," "intricate" with highest scores
- Used for review importance ranking and feature engineering

### 2. **LSH (Locality-Sensitive Hashing)**
- Near-duplicate review detection using shingling and min-hashing
- **Parameters:** 100 hash functions, 20 bands, 5 rows per band
- Identifies similar review pairs using Jaccard similarity
- Detects plagiarism and duplicate reviews across 8,000+ reviews

### 3. **Bloom Filter**
- Space-efficient probabilistic data structure for movie membership testing
- **Size:** 100,000-bit array with 3 hash functions (using mmh3)
- Fast lookup for movie existence checking
- Calculates and ranks top movies by average rating

### 4. **Collaborative Filtering (K-Nearest Neighbors)**
- User-based recommendation system using cosine similarity
- Generates personalized movie recommendations based on user ratings
- Implemented for 5 movies: Shawshank Redemption, The Godfather, The Matrix, Interstellar, Inception
- Predicts ratings for unwatched movies using weighted neighbor ratings

### 5. **DGIM (Datar-Gionis-Indyk-Motwani) Algorithm**
- Streaming algorithm for counting positive/negative reviews in data stream
- Memory-efficient sentiment tracking over sliding windows (k=10)
- Real-time sentiment statistics aggregation per movie
- Handles unbounded review streams with bounded memory

## Dataset
**IMDB Movie Reviews Dataset**
- Source: Custom aggregated IMDB dataset
- Movies analyzed: Shawshank Redemption, The Godfather, The Matrix, Interstellar, Inception, + more
- Fields: `review_movie_title`, `review_username`, `review_rating`, `review_comment`
- Preprocessing: Dropped NaN values, removed duplicates, cleaned text


##Output
| Module / Task                | Metric / Output       | Result / Configuration                   |
| ---------------------------- | --------------------- | ---------------------------------------- |
| **Sentiment Classification** | Accuracy              | **81.2%** using Logistic Regression      |
| **LSH Similarity**           | Similarity Measure    | Max Jaccard Similarity                   |
|                              | Output                | Detected near-duplicate pairs            |
| **Bloom Filter**             | Filter Size           | 100,000 bits                             |
|                              | Hash Functions        | 3 hash functions                         |
| **Collaborative Filtering**  | Recommendation Output | Top-2 personalized movie recommendations |
| **DGIM Algorithm**           | Window Size           | ( k = 10 ) (streaming counts)            |



