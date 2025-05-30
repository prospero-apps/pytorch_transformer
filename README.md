# pytorch_transformer
The architecture of the Transformer model

# Transformer Model: A Deep Dive

Welcome to a journey into the heart of one of the most influential neural network architectures of recent years: the Transformer. Revolutionizing fields from natural language processing to computer vision, Transformers have become the backbone of state-of-the-art models like BERT, GPT, and many others. But what makes them so powerful?

In this notebook, we'll peel back the layers of this fascinating architecture, starting with the foundational components that allow it to process and understand sequential data, particularly text. We'll explore how we convert words into a language the model can understand and how we inject a sense of order into its parallel processing.

## Transformer Overall Architecture

An overview of the Transformer model's architecture as described in the original "Attention is All You Need" paper, highlighting the encoder-decoder structure and its key components like attention mechanisms and feed-forward networks.

The architecture of the Transformer model was described in the 2017 "[Attention is All You Need](https://arxiv.org/abs/1706.03762)" paper. Here's a brief summary:

The Transformer model has an encoder-decoder structure.

1.  **Encoder**: The encoder stack processes the input sequence. It consists of multiple identical layers. Each layer has two main sub-layers:
    *   **Multi-Head Self-Attention**: This sub-layer allows the encoder to weigh the importance of different parts of the input sequence relative to each other when processing each token.
    *   **Position-wise Feed-Forward Networks**: A simple fully connected feed-forward network applied independently to each position in the sequence.
    *   Each of these sub-layers has a residual connection around it, followed by layer normalization.

2.  **Decoder**: The decoder stack generates the output sequence (e.g., in machine translation, it generates the target language sentence). It also consists of multiple identical layers. Each decoder layer has three main sub-layers:
    *   **Masked Multi-Head Self-Attention**: Similar to the encoder's self-attention, but it is masked to prevent attending to future tokens in the output sequence during training (ensuring the model only uses information available up to the current position).
    *   **Multi-Head Attention over Encoder Output**: This sub-layer allows the decoder to attend to the output of the encoder stack, enabling it to focus on relevant parts of the input sequence when generating each token of the output sequence.
    *   **Position-wise Feed-Forward Networks**: Similar to the encoder's feed-forward network.
    *   Again, each of these sub-layers has a residual connection and is followed by layer normalization.

3.  **Positional Encoding**: Since the model processes sequences in parallel, positional encodings are added to the input embeddings at both the encoder and decoder to inject information about the relative and absolute position of tokens.

4.  **Output Layer**: The output of the decoder stack passes through a linear layer and a softmax layer to produce the probability distribution over the vocabulary, from which the next token in the output sequence is predicted.

In essence, the Transformer replaces the recurrent and convolutional layers found in previous sequence models with stacks of self-attention and point-wise, fully connected layers. This architecture, particularly the multi-head attention mechanism, is key to its ability to effectively capture long-range dependencies and its parallelizability.

You can see the structure of the Transformer model in the image below. This is the original image from the abovementioned paper.

![image](https://github.com/user-attachments/assets/911a4278-7d74-4761-842e-cd81d259a0da)


## Input Embeddings

This section will cover how input tokens (like words) are converted into numerical representations (embeddings) that the model can process.

## Positional Encoding Implementation

This section will explain and implement the positional encoding mechanism, which adds information about the position of tokens in a sequence.

## Attention Mechanism

This section will delve into the core attention mechanism, explaining how the model can weigh the importance of different parts of the input when processing a specific token.

## Multi-Head Attention

This section will describe and implement the multi-head attention mechanism, which allows the model to jointly attend to information from different representation subspaces at different positions.

## Feed-Forward Networks

This section will cover the simple, fully connected feed-forward networks applied independently to each position in the sequence within the encoder and decoder layers.

## Encoder Layer

This section will combine the multi-head self-attention and feed-forward network with residual connections and layer normalization to create a single encoder layer.

## Decoder Layer

This section will build a decoder layer, incorporating masked multi-head self-attention, multi-head attention over the encoder output, and a feed-forward network with residual connections and layer normalization.

## Putting It All Together

This section will demonstrate how to assemble the individual components (embeddings, positional encoding, encoder layers, decoder layers) to form the complete Transformer model.

## How to Run the Notebook

Instructions on how to access and execute the code in the notebook.

1.  Clone the repository to your local machine.
2.  Open the notebook in Google Colab or a Jupyter environment.
3.  Run the cells sequentially.
