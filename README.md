# similarity

### Summary

| Section | Description |
| ------- | ----------- |
| 1. Project Description | Quick introduction |
| 2. Functions | Quick overlook |
| 3. How to Use | 3 steps |
| 4. Results | From web |

---
### 1. Project Description
Multiple similarity functions have been implemented to compare article titles between them and article texts between them.

A simple web scraper has been used to demonstrate how the similarity functions are used. It should be replaced by a more powerful one.

---
### 2. Functions
- N-gram (optimized to learn the best n for both titles and texts)
- Edit distance
- Edit score
```py
def edit_score(text1, text2):

    return 1 - (editdistance.eval(text1, text2) / max(len(text1), len(text2)))
```
- Combined Syntaxic Similarity (CSS)

Either
```py
(ngram_similarity + edit_sim) / 2
```
or
```py 
(ngram_similarity + edit_sim + cos_sim) / 3
```
- Cosine
- Jaccard

---
### 3. How to use
- Step 1: Run the Metrics Functions cells
- Step 2: Run the Print Params cells
- Step 3: Run on Scraped Data and compare to Test Data

---
### 4. Results
The results of the Jupyter Notebook are not correctly displayed from Github web.

You should clone the repository and run the Notebook.
