Question 1:
(a) (1 point) (written) In Assignment 4 we used 256-dimensional word embeddings (eword = 256), while in this assignment, it turns out that a character embedding size of 50 suffices (echar = 50). In 1-2 sentences, explain one reason why the embedding size used for character-level embeddings is typically lower than that used for word embeddings.

Ans: Character vocab size(say 100) is much lesser than word vocab size(say 1MM). We don't need more dimensions to represent concrete chars

(b) (1 point) (written) Write down the total number of parameters in the character-based embedding model (Figure 2), then do the same for the word-based lookup embedding model (Figure 1). Write each answer as a single expression (though you may show working) in terms of echar, k, eword, Vword (the size of the word-vocabulary in the lookup embedding model) and Vchar (the size of the character-vocabulary in the character-based embedding model).
Given that in our code, k = 5, Vword ≈ 50,000 and Vchar = 96, state which model has more parameters, and by what factor (e.g. twice as many? a thousand times as many?).

Ans: ?

(c) (2 points) (written) In step 3 of the character-based embedding model, instead of using a 1D con- vnet, we could have used a RNN instead (e.g. feed the sequence of characters into a bidirectional LSTM and combine the hidden states using max-pooling). Explain one advantage of using a con- volutional architecture rather than a recurrent architecture for this purpose, making it clear how the two contrast. Below is an example answer; you should give a similar level of detail and choose a different advantage.
When a 1D convnet computes features for a given window of the input, those features depend on the window only – not any other inputs to the left or right. By contrast, a RNN needs to compute the hidden states sequentially, from left to right (and also right to left, if the RNN is bidirectional). Therefore, unlike a RNN, a convnet’s features can be computed in parallel, which means that convnets are generally faster, especially for long sequences.

Ans: A convnet can capture multiple features & patterns(using multiple filters) by considering different window sizes 

(d) (4 points) (written) In lectures we learned about both max-pooling and average-pooling. For each pooling method, please explain one advantage in comparison to the other pooling method. For each advantage, make it clear how the two contrast, and write to a similar level of detail as in the example given in the previous question.

Ans: 
Max pooling

Adv: captures the strongest pattern in data
Disadv: discard most info in the data

Avg pooling

Adv: captures/preserves most of the info from data
Disadv: strongest signals in data get diluted, but we get relatively smaller results
