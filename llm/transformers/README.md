# **Attention Mechanism in Transformers**

- The attention mechanism allows models to focus on different parts
of the input sequence for each output token.

- `Q`, `K`, `V` = `Query`, `Key`, `value`
- Q/K/V logic is universal in all LLMs

## **Type of Attentions**

|Type | Use |
|----|-----|
| Self-Attention | Used in encoders and decoders (e.g., BERT, GPT) |
| Cross-Attention | Used in encoder-decoder setups (e.g., translation) |
| Multi-Head Attention| Runs multiple attention layers in parallel |
| Casual (Masked) Attention| Ensures no peeking into the future (e.g., GPT) |
