# Sequence Models

## Introduction

Models like Recurrent Neural Networks, or RNNs, have transformed speech recognition, natural language processing, and other areas. 

A few examples of what sequence models can be used for : Music generation
is example of a problem with sequence data. In this case, only the output, y, is a
sequence. The input can be the empty set, or it can be a single integer, maybe referring to the
genre of music you want to generate, or maybe the first few notes of the piece of music you want.


## RNN Model
The earliest neural approaches to language used recurrent neural networks, which processed text one word at a time, passing information forward from each word to the next through a hidden state vector. By the time the network reached the end of a long sentence or paragraph, the representation of words from the beginning had been diluted or lost entirely. This made it very hard to capture relationships between words that were far apart in a text.

## LSTM
Long Short-Term Memory networks, or LSTMs, addressed this through gating mechanisms that allowed the network to selectively remember and forget information. LSTMs were a genuine improvement, enabling the seq2seq models used in early machine translation systems to handle longer sequences more reliably. But they still processed text sequentially, which meant they could not be parallelized effectively during training. Every word depended on the processing of every previous word, creating a fundamental bottleneck in computational efficiency.


## Backpropagation

## Different Types of RNNs

## Language Model and Sequence Generation
