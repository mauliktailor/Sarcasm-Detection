# Tokenization-on-different-datasets-NLP-

In this repository, I have performed the basic preprocessing task on any text dataset.

Tokens are the building blocks of Natural Language. Tokenization is a way of separating a piece of text into smaller units called tokens. Here, tokens can be either words, characters, or subwords. Hence, tokenization can be broadly classified into 3 types – word, character, and subword (n-gram characters) tokenization.

In this repository I have performed the word level tokenization using Keras in TensorFlow 2.0 by using Tokenizer and pad_sequences in Keras. 

## Tokenizer (from tensorflow.keras.preprocessing.text import Tokenizer)
1) **fit_on_texts:** Updates internal vocabulary based on a list of texts. This method creates the vocabulary index based on word frequency. So if you give it something like, "The cat sat on the mat." It will create a dictionary s.t. word_index["hello"] = 1; word_index["world"] = 2. It is word -> index dictionary so every word gets a unique integer value. 0 is reserved for padding. So lower integer means more frequent word (often the first few are stop words because they appear a lot).
2) **texts_to_sequences:** Transforms each text in texts to a sequence of integers. So it basically takes each word in the text and replaces it with its corresponding integer value from the word_index dictionary. Nothing more, nothing less, certainly no magic involved.

## pad_sequences Method (from tensorflow.keras.preprocessing.sequence import  pad_sequences)
This function transforms a list (of length *num_samples*) of sequences (lists of integers) into a 2D Numpy array of shape (*num_samples*, *num_timesteps*). num_timesteps is either the *maxlen* argument if provided, or the length of the longest sequence in the list.

Sequences that are shorter than *num_timesteps* are padded with value until they are *num_timesteps* long. Sequences longer than *num_timesteps* are truncated so that they fit the desired length.

To run the Tokenization setp by step:
1) Download the sarcasm.json file and change the path in the *open('/content/sarcasm.json')* in Tokenization NLP.ipynb
2) Run each cell of *Tokenization NLP.ipynb* setp by step.
