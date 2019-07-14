# word2vec skipgram model

Let's break skipgram model into steps to see how it converts words into vectors

 - Step 1
  - Slide predefined windows to find match word pairs. The relationship should be 1 to 1 and let's assume there are totally m pairs in the form of (target word, close word).


 - Step 2
  - Create input matrix X where X.shape is (m, vocab_size). Each row in X should be one hot encoding because it represents the target word.

- Step 3
  - The hidden matrix is basically the word embedding matrix we try to generate, denoted as H. H.shape should be (vocab_size, embedding_size). The embeding_size could be anything ranging from 100 to 300, but research has shown large embedding_size may degrade the model performance.


- Step 4
  - The matrix between hidden layer and output has shape (embedding_size, m). It output a layer of dimension m whose dimension is same as close word. This is making sense because they will be used to compute cross entropy loss after go through softmax function.


- Step 5
  - Train the NN and the embedding matrix with shape (vocab_size, embedding_size) will be generated!


- Step 6
  - Convert a word into one hot encoding with dimension (1,m) and then dot product matrix H is basically the desired vector that word represents in embedding_size space.
