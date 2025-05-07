# **Attention is All you need**
- The attention mechanism allows models to focus on different parts of the input sequence for each output token.

- `Q`, `K`, `V` = `Query`, `Key`, `value`
- Q/K/V logic is universal in all LLMs

## **Steps in Attention**
1. Tokenizing sentence.
2. Embedding token.
3. Project Q,K,V
    - Calculate each Q, k, and V in 3 seperate Linear layer.
4. Calculate Equation Attention 
    - Compute Attention score
    - Apply Softmax to scores
    - Multiply weights with V
5. Concatenate heads (if it multi-head attention)
6. Add Norm
7. Pass to FNN
8. Loss + Backpropagation
