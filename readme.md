# Build a CBOW Model

This model changed from skip-gram model which on the tensor flow website.

The main difference has two part.

The first is, this repo encapsulate all file operation into text_helper.py file.

The second is, based on CBOW concept, I exchanged the input and target.

The input is the sum of all context words embedding vector.

The target word is the middle word in the context words. This part of code in the following graph.