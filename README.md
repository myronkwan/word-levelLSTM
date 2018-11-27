# word-levelLSTM
text generation with multi-layer LSTM model and word-level embedding layer in keras. Scraped the full text of The Two Towers by Tolkien and used that as training data.

For training data I used n-grams of up to size of 5 predictors for 1 label. At each index of the input data, all predictor sequences of length 1-5 were generated as training data, and then pre-padded to make them all the same length.

ex) I am sam green eggs and ham
gram of 2 predictors: [i,am]=[sam]
gram of 3 predictors:[i, am, sam]=[green]

I tried model with 2 LSTM layers and 3 LSTM layers, but it seemed 3 LSTM layers produced better results.
At around 100+ epochs, the data began to overfit too much and large blocks of text from different areas of the book were chained together.
I found a sweet spot around 30 to 50 epochs, where the text did not overfit too much and smaller parts of the text were chained together. Sometimes, sentence loops still occur. 
