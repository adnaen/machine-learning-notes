# **Decoder**

- Decoder block is similar to encoder but slightly different.

Main different is ,
- It uses Masked attention layer (for predict the next token).
- It uses right shifted input

## **Workflow**
1. Right Shifted Input 
2. Embedding.
3. Positional Encoding.
4. Masked-Multi-Head Attention
5. Add/Norm
6. Multi-Head Attention
7. Add/Norm
8. FFN
9. Add/Norm

