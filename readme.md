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