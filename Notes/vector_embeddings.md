# Vector/Embeddings

In the context of Large Language Models (LLMs), a vector (often called an embedding) is a long list of numbers that represents the meaning of text, an image, or a sound in a mathematical way. Because AI models only understand math, vectors translate words into numerical coordinates where similar meanings are grouped closely together

## How Vectors (Embeddings) WorkTranslating Meaning

An LLM reads a piece of text and assigns it coordinates across thousands of "dimensions" (e.g., tone, context, historical relevance).

## Measuring Relationships 

By calculating the mathematical distance between two vectors (using methods like Cosine Similarity), the LLM can determine if two words or sentences mean the same thing. For example, the vector for "kitten" will be positioned very close to the vector for "puppy," but far away from the vector for "tractor."