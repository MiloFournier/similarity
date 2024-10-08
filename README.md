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
- N-gram

It is a word-based similarity metric.
```py
def ngrams(input, n):

    input = input.lower().split(' ')

    output = []

    for i in range(len(input)-n+1):
        output.append(tuple(input[i:i+n]))

    return output

def ngram_sim(text1, text2, n):

    ng1 = set(ngrams(text1, n))
    ng2 = set(ngrams(text2, n))
    
    common_ngrams = ng1.intersection(ng2)

    return (2*len(common_ngrams))/(len(ng1)+len(ng2))
```
- Edit distance
- Edit score 

It takes into account the length of the text and normalizes it.
```py
def edit_score(text1, text2):

    return 1 - (editdistance.eval(text1, text2) / max(len(text1), len(text2)))
```
- Combined Syntaxic Similarity (CSS)
```py
(ngram_similarity + edit_sim) / 2
```

---
### 3. How to use
- Step 1: Run the Metrics Functions cells
- Step 2: Run the Print Params cells
- Step 3: Run on Scraped Data and compare to Test Data

---
### 4. Results
The results of the Jupyter Notebook are not correctly displayed from Github web.

You should clone the repository and run the Notebook.
