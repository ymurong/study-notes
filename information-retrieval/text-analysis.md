
- [Content of Table](#content-of-table)
  - [Statistical properties of text](#statistical-properties-of-text)
    - [Zipf’s law](#zipfs-law)
    - [Heap’s law](#heaps-law)
  - [Text Analysis pipeline](#text-analysis-pipeline)
    - [Pipeline](#pipeline)
    - [Stop-word removal](#stop-word-removal)
    - [Stemming](#stemming)


# Content of Table
## Statistical properties of text
### Zipf’s law
- Word Frequency **Probability**(P_r) is inversely proportional to **Ranking**.
- $Rank * P_r$ = Const' (stable to a value)
- English's const' $\approx$ 0.1
- Top frequency words would slightly deviate from the law
- Low frequency words would slightly deviate from the law
  

###  Heap’s law
- \# unique words is sub-linear to \# words in a collection
- the more words -> not that much more unique words
- vocab = k * $words^\beta$ (10<=k<=100, $\beta \approx 0.5$)

## Text Analysis pipeline

### Pipeline
- Remove white-spaces and punctuation
- Lower-case
- Remove stop-words
- Stemming
- Deal with phrases
- Apply language-specific precessing rules

### Stop-word removal
- Frequency-based
    - Set a frequency threshold f 
    - Remove words with the frequency higher than f
- Dictionary-based
  - create a dictionary of stop-words
  - remove words that occur in this dictionary 

### Stemming