# Tokens and tokenizers

## What is a token?
A token is the most fundamental data unit in a text document, essential for enabling AI to understand and process information. In Natural Language Processing (NLP), tokenization refers to breaking down larger texts into smaller, manageable pieces called tokens. Depending on the method, these tokens can be words, parts of words, or phrases. Before an AI model processes any input, it divides the text into these units, making it easier to analyze and generate responses.

## Common tokenization techniques
Word tokenization splits text into individual words. It’s a straightforward method that makes it easy to process simple language tasks. For instance, the sentence “Natural Language Processing is exciting” would become [“Natural,” “Language,” “Processing,” “is,” “exciting”].

This technique works well for tasks like sentiment analysis, text classification, and information retrieval. However, it can struggle with compound words, abbreviations, and languages without clear word boundaries, like Chinese.

### Character tokenization
Character tokenization breaks text into individual characters, capturing fine-grained details. For example, “Natural Language Processing” would be tokenized as [“N,” “a,” “t,” “u,” “r,” “a,” “l,” “L,” “a,” “n,” “g,” “u,” “a,” “g,” “e,” “P,” “r,” “o,” “c,” “e,” “s,” “s,” “i,” “n,” “g”].

This technique is effective for spelling correction, password analysis, and non-standard text input processing. It’s also useful for languages without clear word boundaries and models that learn from character-level inputs.

### Subword tokenization
Subword tokenization splits words into smaller, meaningful units, such as prefixes, suffixes, or syllables. For “unbreakable,” this might be [“un,” “break,” “able”]. This method helps models handle out-of-vocabulary (OOV) words by recognizing parts of them, even if the full word is unfamiliar. Subword tokenization is popular in modern language models like BERT and GPT. It’s particularly useful for morphologically rich languages or when training on a limited vocabulary.

[Nebius reference](https://nebius.com/blog/posts/what-is-token-in-ai)

---

The size and boundaries of a token are defined by a pre-computed vocabulary list and a specific mathematical algorithm, not by fixed rules about words or letters. Here is exactly how token amounts and boundaries are determined:

1. The Tokenizer and Vocabulary
-> Fixed Vocabulary: AI models use a companion program called a tokenizer. 
-> Size Limits: The tokenizer contains a fixed list of allowed tokens (usually 32,000 to 100,000+ tokens).
-> The Rule: If a sequence of characters is in that vocabulary list, it can be a single token.

2. Frequency-Based Splitting
-> Common Words: Words used frequently in training data (like the, and, house) get their own single token.
-> Rare Words: Uncommon or complex words (like subcompartment) are chopped into smaller pieces.Example: subcompartment might break into sub, part, and ment.

3. The Core Algorithms
Tokenizers use specific mathematical compression algorithms to build their vocabulary
-> Byte Pair Encoding (BPE): Starts with individual letters. It iteratively merges the most frequent pairs of characters found in text until the vocabulary list is full.
-> WordPiece/Unigram: Starts with whole words and progressively breaks them down into smaller pieces based on how much information is lost.

4. Character-Level Fallbacks
-> Unique Text: If a model encounters a completely new word, a typo, or a rare symbol (like a foreign character or emoji), it falls back to the smallest unit.
-> Individual Letters: It will break that specific section down into individual letters or bytes so it can still read it.