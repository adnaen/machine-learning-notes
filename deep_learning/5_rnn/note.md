# How to Train an RNN Model

## 1. Prepare Input Data

> ⚡ **Important Note:**  
> In order to use `nn.Embedding()`, we need to manually convert all tokens (words) into their corresponding vocabulary IDs.  
> **Because:**  
> `nn.Embedding()` only understands numbers, not text!  
> **Vocabulary (Vocab)** means: all the unique words the model can recognize. It is like the model's "brain" — if a word is not in the vocab, the model doesn't know it exists.

### Example:

- First, build a vocabulary:

```plain text
VOCAB = {"hello": 0, "dog": 1, "cat": 2, "tiger": 3, "cow": 4}
```
- Then, encode your corpus:

```plane text
corpus = ("hello dog", "hello cat", "hello tiger", "hello cow")
corpus_indexed = ([0, 1], [0, 2], [0, 3], [0, 4])
```
## 2. Convert to Embeddings

- After encoding the words into integers, pass them to nn.Embedding() to map each token ID to a fixed-size vector.

- Suppose the embedding_dim = 2. Then each word will be represented like this:

```plane text

embeddings = (
  [[0.12, 0.32], [0.10, 0.50]],    # "hello dog"
  [[0.12, 0.32], [0.40, 0.89]],    # "hello cat"
  [[0.12, 0.32], [0.43, 0.51]],    # "hello tiger"
  [[0.12, 0.32], [0.90, 0.01]]     # "hello cow"
)
```
- Now each word is represented as a vector of shape (2,).


## 3. Feed into RNN

- After converting words into embeddings, pass them into your nn.RNN model.
- Example RNN:

```python
rnn = nn.RNN(input_size=2, hidden_size=4)

```
- Here:
    - input_size=2 → (same as embedding_dim)
    - hidden_size=4 → the size of the hidden memory vector that RNN maintains.


