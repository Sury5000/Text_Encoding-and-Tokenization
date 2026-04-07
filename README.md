# Text Encoding and Tokenization Techniques in NLP

---

# Objective

* Understand how raw text is converted into tokens
* Explore different tokenization techniques
* Compare BPE, WordPiece, Unigram, and Byte-Level encoding
* Learn padding, truncation, and attention masks
* Use Hugging Face tokenizers for real-world NLP

---

# Dataset

* IMDB movie review dataset

* Contains:

  * Text (review)
  * Label (0 = negative, 1 = positive)

* Split into:

  * Training set
  * Validation set
  * Test set

---

# Basic Tokenization Setup

* Used Hugging Face `tokenizers` library

* Defined special tokens:

  * `<pad>`
  * `<unk>`

* Pre-tokenization:

  * Whitespace splitting

---

# Byte Pair Encoding (BPE)

* Built tokenizer using BPE model
* Vocabulary size limited to 1000

Observed:

* Words split into subwords
* Unknown tokens replaced with `<unk>`
* Each token mapped to unique ID

Additional:

* Offsets show start and end positions of tokens
* Batch encoding supported

---

# Padding and Truncation

* Enabled padding to fixed length
* Used truncation for long sequences

Outputs:

* Token IDs
* Attention mask

Learning:

* Padding ensures equal sequence length
* Attention mask ignores padded tokens

---

# Byte-Level BPE

* Used ByteLevel pre-tokenizer

Observed:

* Spaces preserved using special symbols
* Handles emojis and special characters
* Works with UTF-8 encoding

Learning:

* Suitable for multilingual and complex text

---

# WordPiece Tokenization

* Used WordPiece model

Observed:

* Uses subword tokens with `##` prefix
* Splits rare words into meaningful parts

Learning:

* Based on probability scores
* Widely used in transformer models like BERT

---

# Unigram Tokenization

* Built using Unigram model

Observed:

* Removes tokens iteratively
* Keeps most useful tokens

Learning:

* Uses probabilistic approach
* Different from BPE (top-down instead of bottom-up)

---

# Decoding

* Converted token IDs back to text

Observed:

* Special tokens may be removed by default
* Formatting adjustments needed for clean output

---

# Pretrained Tokenizers

## GPT-2 Tokenizer

* Uses Byte-Level BPE
* Handles raw text efficiently
* No explicit word boundaries

---

## BERT Tokenizer

* Uses WordPiece encoding
* Supports:

  * Padding
  * Truncation
  * Tensor outputs

Outputs:

* input_ids
* attention_mask

---

## ALBERT Tokenizer

* Uses SentencePiece (underscore-based splitting)
* Fast tokenizer implementation

Learning:

* Efficient for large-scale models

---

# Hugging Face Integration

* Converted custom tokenizer into Hugging Face format
* Used PreTrainedTokenizerFast

Learning:

* Custom tokenizers can be integrated into pipelines
* Enables compatibility with transformer models

---

# Key Learnings

* Tokenization is the first step in NLP pipelines
* Different algorithms split text differently
* BPE builds vocabulary using frequent subwords
* WordPiece uses probability-based merging
* Unigram removes less useful tokens
* Byte-level encoding handles complex text better
* Padding and attention masks are essential for batching
* Pretrained tokenizers simplify real-world usage

---

# Conclusion

This project provides a strong foundation in text encoding and tokenization by exploring multiple techniques and comparing their behavior. It highlights how different tokenization strategies impact text representation and prepares for advanced NLP tasks using transformer-based models.

---
