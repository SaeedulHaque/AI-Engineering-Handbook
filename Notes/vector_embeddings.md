# Vectors/Embeddings

In the context of Large Language Models (LLMs), a vector (often called an embedding) is a long list of numbers that represents the meaning of text, an image, or a sound in a mathematical way. Because AI models only understand math, vectors translate words into numerical coordinates where similar meanings are grouped closely together

## How Vectors (Embeddings) Work Translating Meaning

An LLM reads a piece of text and assigns it coordinates across thousands of "dimensions" (e.g., tone, context, historical relevance).

## Measuring Relationships 

By calculating the mathematical distance between two vectors (using methods like Cosine Similarity), the LLM can determine if two words or sentences mean the same thing. For example, the vector for "kitten" will be positioned very close to the vector for "puppy," but far away from the vector for "tractor."

## Why LLMs Use Vectors
LLMs don’t understand language the way we do. They don’t work with words or sentences in the way a person thinks about them. What they do is represent chunks of language as vectors. Once the words are numbers, the model can do math on them.

There are three important things LLMs do with vectors:

1. Embeddings
2. Input-output
3. Similarity search

### 1. Embeddings

An embedding is how an LLM represents a piece of text as a vector.

When you give it a sentence, the first thing it does is split the sentence into tokens. Tokens are pieces of words. Sometimes they’re entire words. Sometimes they’re just a few letters. [More about tokens](tokenizer.md)

Then it converts each token into a vector. These vectors aren’t random. They’re created in a way that tries to capture the meaning of the token, based on all the text the model saw during training.

So instead of the word “apple,” the model works with something like [0.13, -0.04, 8.01, …]. This allows the model to work with text as if it were math. That’s what makes LLMs different from old-fashioned text systems that relied on keywords or string matching.

When you feed text into an LLM, the first thing it does is convert words into vectors. This is called an embedding.

The model breaks the text into tokens (words or parts of words).
Each token gets mapped to a high-dimensional vector.
These vectors capture meaning — words with similar meanings end up close together in vector space.
This is why LLMs can understand relationships between words. “King” minus “man” plus “woman” might land near “queen.”

2. Input-Output Operations

You’ve probably used this without knowing it.

When you give a prompt to an LLM like ChatGPT, here’s what happens under the hood:

Your prompt is split into tokens.
Each token is turned into a vector (an embedding).
The model takes that sequence of vectors and processes it.
Then it creates a new sequence of vectors in response.
Finally, it turns those vectors back into tokens, and then into text.
The entire conversation is just vectors flowing through the model.

3. Similarity Search

This is how LLMs find relevant information.

Imagine you’re building a chatbot that answers questions using a library of documents. When someone asks a question, you want the bot to find the most relevant passages from the library.

Subscribe to the Medium newsletter
When an LLM retrieves relevant information, it’s often comparing vectors.

-> Your prompt gets embedded into a vector.
-> The model compares it to stored vectors (e.g., documents in a database).
-> It measures similarity using something like cosine similarity — calculating the angle between vectors.
-> The closest matches get used to generate a response.
This is how search engines and chatbots find relevant answers.

[text](https://medium.com/@tahirbalarabe2/vectors-in-large-language-models-4731d8be349d)