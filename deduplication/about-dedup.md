- [Content of Table](#content-of-table)
  - [Challenges of Deduplications](#challenges-of-deduplications)
    - [No single metric could work 100%](#no-single-metric-could-work-100)
    - [$N^2$ problem](#n2-problem)
  - [How dedup works](#how-dedup-works)
    - [Blocking rules](#blocking-rules)
    - [Scoring](#scoring)


# Content of Table
## Challenges of Deduplications
### No single metric could work 100%
levenshtein ratio (one similarity metric)
- different entities could have larger value than same entities that have different notations (length)
### $N^2$ problem
naively comparing each pair of strings using a similarity metric blows up quickly
- for n entities, need to compare $\frac{n(n-1)}{2}$

## How dedup works
[dedup documentation](https://docs.dedupe.io/en/latest/)
### Blocking rules
- The first step is to apply a large list of blocking rules to the data
    - same first word
    - same first three characters
    - same integers
    - ....
- only pairs within the same blocks are considered 
- we could use recordlinkage lib

### Scoring
- normalised affine gap distance
- conditional random field distance (CRF)
  - [Conditional Random Fields : Data Science Concepts](https://www.youtube.com/watch?v=rI3DQS0P2fk&t=189s)
