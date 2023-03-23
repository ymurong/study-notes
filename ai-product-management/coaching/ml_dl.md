# when to use ML vs DL

## ML 
ML leverages the statistics.
It help machines to learn patterns by feeding a lot of examples (features)


## DL
When features are highly impossible to manually define

use DL to automatically learn those features (representations)
- typical use cases: images, text, audio, video

DL is composed of neural networks which are composed of linear regressions and non-linear transformations (much more parameters)

## Key Considerations

1. Data Available 
   1. DL needs much more data, otherwise its performance would be equal or even worse than ML (DL has much more parameters)
   2. DL: more time consuming, technically complex, expensive to run 
2. Hardware
   1. ML can run very well on CPU 
   2. DL needs expensive GPU 
3. Training (parameters)
   1. ML less time
   2. DL more time
4. Explainability Tradeoff
   1. ML needs domain experts to define features with better exp
   2. DL can figure out the features themselves but hardly explainable (local explainability)


### Examples (Hiring):
ML: 
    HR specialist help with feature selection
DL:
    No need HR specialist but hardly explainable -> also problem of fairness (blackbox problem)










