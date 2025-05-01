# How To

1. **Tokenize word in LLM**
A: Unlike Traditional NLP, it don't with whitespace or punctuation.
It tokenize text with based on statistics measures and intelligence

```plane text
e.g. 
text = "I am playing"
# in tradational NLP
tokens = ["i", "am", "playing"]

# in LLM
tokens = ["i", "am", "play", "ing"]
```

> It help to reduce vocab size 100k -> 30k.

- **Most of LLM Mainly Uses 3 Tokenizing Technique**    
    - Byte Pair Encoding (BPE) : gpt-2
    - WordPiece : BERT
    - SentencePiece : T5, ALBERT


