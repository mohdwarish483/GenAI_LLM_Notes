### Notes on Transformer Models and Their Use in NLP Tasks

#### Overview of Transformer Architecture
- **Translation Task Example**:
  - **Input**: French phrase tokenized using the same tokenizer as the model.
  - **Encoder Side**:
    - Tokens are embedded and fed into multi-headed attention layers.
    - Outputs are passed through a feed-forward network.
    - Encoder produces a deep representation of the input sequence’s structure and meaning.
  - **Decoder Side**:
    - Representation from the encoder influences the decoder’s self-attention mechanisms.
    - Start-of-sequence token triggers the decoder to predict the next token.
    - Process continues in a loop until an end-of-sequence token is predicted.
    - Sequence of tokens is detokenized to produce the output phrase.

#### Key Concepts
- **Encoder**:
  - Converts input sequences into a meaningful representation.
  - Consists of embedding layers, multi-headed attention layers, and feed-forward networks.
- **Decoder**:
  - Generates new tokens based on encoder’s output and previous tokens.
  - Uses self-attention layers and feed-forward networks, ending with a softmax output layer.

#### Transformer Model Variations
- **Encoder-Only Models**:
  - **Example**: BERT.
  - Used for tasks like sentiment analysis and classification.
  - Input and output sequences are of the same length.
- **Encoder-Decoder Models**:
  - **Examples**: BART, T5.
  - Suitable for sequence-to-sequence tasks (e.g., translation).
  - Input and output sequences can be different lengths.
  - Can be scaled for general text generation tasks.
- **Decoder-Only Models**:
  - **Examples**: GPT family, BLOOM, Jurassic, LLaMA.
  - Commonly used today for a variety of tasks.
  - Focus on generating text based on input prompts.

#### Key Processes
- **Tokenization**:
  - The process of converting words into tokens using a tokenizer.
- **Embedding**:
  - Mapping tokens into dense vectors of fixed size.
- **Multi-Headed Attention**:
  - Allows the model to focus on different parts of the input sequence simultaneously.
- **Feed-Forward Networks**:
  - Apply non-linear transformations to the attention outputs.
  - ### Why Do We Use Feed-Forward Layers in Transformer Models?

#### 1. **Non-Linearity Introduction**
- **Enhancing Model Expressiveness**:
  - The attention mechanism is primarily linear. By introducing non-linear transformations through feed-forward layers, the model can learn more complex patterns and representations.
  - Non-linear functions, like ReLU (Rectified Linear Unit) used in these layers, help the network capture and represent complex relationships within the data.

#### 2. **Feature Transformation**
- **Independent Processing of Each Token**:
  - After the attention mechanism has mixed the information from different tokens, the feed-forward layer applies the same transformation to each token independently.
  - This allows the model to process and refine the features of each token individually, enhancing the overall representation of the sequence.

#### 3. **Enhancing the Representational Power**
- **Learning Complex Patterns**:
  - By combining the output of the attention mechanism with feed-forward networks, the model can learn more nuanced and complex patterns in the data.
  - This combination helps in building a rich representation that captures both the relationships among tokens (via attention) and the individual token features (via feed-forward layers).

#### 4. **Efficiency and Parallelism**
- **Parallel Processing**:
  - Feed-forward layers enable efficient parallel processing of tokens. Unlike RNNs (Recurrent Neural Networks), which process tokens sequentially, transformers process tokens in parallel.
  - This parallelism significantly speeds up training and inference, making transformers more efficient for handling large datasets.

#### 5. **Layer Normalization and Stability**
- **Stabilizing Training**:
  - Feed-forward layers are often followed by layer normalization, which helps stabilize and speed up the training process.
  - Layer normalization ensures that the outputs of the feed-forward layers have a consistent scale, improving the overall stability of the model.
- **Self-Attention**:
  - Mechanism within the decoder that helps the model predict the next token based on previous tokens and encoder’s output.
- **Softmax Layer**:
  - Produces probabilities for each possible next token.

#### Important Notes
- **Prompt Engineering**:
  - Crafting prompts in natural language to interact with transformer models.
  - No need to understand all details of the underlying architecture to create effective prompts.
- **Sequence Generation Loop**:
  - Continues until an end-of-sequence token is reached.
  - Each generated token is fed back into the decoder to predict the next token.
