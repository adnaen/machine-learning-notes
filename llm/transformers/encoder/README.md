# **Encoder**

Encoder is a block of modern Transformer architecture.
Which is mainly calculate the contextual embedding of the input.

1. Encoder is stacked block with
    - Multi-Head Attention
    - Feed Forward Neural Network
    - Residual
    - Layer Norm

2. Flow of Encoder block
    - Embedded Input
    - Positional Encoding
    - Multi-Head Attention (which calculate attention score)
    - Apply Residual/Add (nothing. just add the input embedding
      with the new contextual embedding)
    - Apply Layer Norm
    - Pass Through Feed Forward Layer (2 Layer MLP)
    - Again Apply Residual and Layer Norm
