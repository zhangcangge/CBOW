# Build a CBOW Model

This model changed from skip-gram model which on the tensor flow website.

The main difference has two part.

The first is, this repo encapsulate all file operation into text_helper.py file.

The second is, based on CBOW concept, I exchanged the input and target.

The input is the sum of all context words embedding vector.

The target word is the middle word in the context words. This part of code in the following graph.

<img src="https://github.com/zhangcangge/CBOW/blob/master/image/kernel_change.jpg" width="600" height="300" />

This program use a different way to embedding words.

After the program download the corpus, it chose the most common 2000 words, and create dictionary based on their appearance probability. For example, if "love" is the most common word, then the key of love will be "0". if "near" is the second common word, then the key of love will be "1"......

Then the program create a 2000 * 200 Matrix. Each row correspond one word. For example, if the key of "love" in dictionary is "0", then the row 0 of the Matrix correspond to word "love". All the context words and the target words have a corresponding row in the Matrix. We build a neuro network to train this Matrix. In this program after 50000 generation, it stop training. The result Matrix is my embedding Matrix. I can use it to calculate similarity between words.