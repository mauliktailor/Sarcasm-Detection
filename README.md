# Tokenization and Stop-Word Removal-NLP

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

## Stop Word Removal

The process of converting data to something a computer can understand is referred to as pre-processing. One of the major forms of pre-processing is to filter out useless data. In natural language processing, useless words (data), are referred to as stop words.

We would not want these words to take up space in our database, or taking up valuable processing time. For this, we can remove them easily, by storing a list of words that you consider to stop words. THe stop word removal is done in *stop_word_removal.ipynb*. The following is the list of stopwords:
```python
stopwords = [ "a", "about", "above", "after", "again", "against", "all", "am", "an", "and", "any", "are", "as", "at", "be", "because", "been", "before", "being", "below", "between", "both", "but", "by", "could", "did", "do", "does", "doing", "down", "during", "each", "few", "for", "from", "further", "had", "has", "have", "having", "he", "he'd", "he'll", "he's", "her", "here", "here's", "hers", "herself", "him", "himself", "his", "how", "how's", "i", "i'd", "i'll", "i'm", "i've", "if", "in", "into", "is", "it", "it's", "its", "itself", "let's", "me", "more", "most", "my", "myself", "nor", "of", "on", "once", "only", "or", "other", "ought", "our", "ours", "ourselves", "out", "over", "own", "same", "she", "she'd", "she'll", "she's", "should", "so", "some", "such", "than", "that", "that's", "the", "their", "theirs", "them", "themselves", "then", "there", "there's", "these", "they", "they'd", "they'll", "they're", "they've", "this", "those", "through", "to", "too", "under", "until", "up", "very", "was", "we", "we'd", "we'll", "we're", "we've", "were", "what", "what's", "when", "when's", "where", "where's", "which", "while", "who", "who's", "whom", "why", "why's", "with", "would", "you", "you'd", "you'll", "you're", "you've", "your", "yours", "yourself", "yourselves" ]



```
