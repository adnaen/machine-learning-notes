# **Self-Attention**

## **Steps**
1. Tokenizing sentence.
2. Embedding token.
    - The model only use embedding in first phase, after first attention calculation it generate new contextual embedding with sentence in each word.
3. Project Q,K,V
    - Calculate each Q, k, and V in 3 seperate Linear layer.
    - Use case:
        ```python
        sentence = "love you"
        # since sentence has only 2 word we have 2 case

        # case-1
        Query = "love"
        # it calculate relation between each word with it include itself.
        # Each token are consider a key, and the Query compares itself with each key to get relation
        # here
        Q("love") = K("love"), K("you")

        # case-2
        Query = "you"
        Q("you") = K("love"), K("you")

        # Each word now have a contextualized embedding
        # e.g. now the 'love' are more relate to 'YOU'.
        # This contextual embedding is used in next layer

        ```
4. Calculate Equation Attention 
    - Compute attention scores using dot product: Q · Kᵗ
    - Scale by √dₖ to prevent extreme values (helps gradient flow)
    - Apply softmax to get attention weights
    - Multiply these weights with V to get output vectors
