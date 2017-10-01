# Language Translation using Tensorflow's new seq2seq Library
Given that Tensorflow 1.2 has recently released a new library for sequence to sequence models and has made some of the old codes obsolete, this is an attempt to redo the Udacity Deep Learning Nanodegree Assigment 4 - Language Translation from English to French using the new seq2seq library. 

Some changes were: 
- old APIs (simple_decoder_fn_train and dynamic_rnn_decoder) were replaced
- new APIs (TrainingHelper/GreedyEmbeddingHelper, BasicDecoder and dynamic_decode) to create the training and inference decoders
- additional placeholders needed to support the new APIs (source_sequence_length and target_sequence_length)

I also added some additional features to make this model seem more like the model in the paper [Neural Machine Translation by Jointly Learning to Align and Translate](https://arxiv.org/abs/1409.0473) by introducing:
- Bidirectional LSTMs and
- Bahdanau attention (additive)

To do (if I have time):
- add beam search decoder instead of the current greedy decoding (where the output word is just chosen based on max probability). In this way, we consider top K contenders at each position instead of the top contender only. This makes more sense as the top word for position 1 may not be the top word for the entire sequence generated. It might be the second or third from top instead. See this [link](https://www.quora.com/Why-is-beam-search-required-in-sequence-to-sequence-transduction-using-recurrent-neural-networks) for more details.
- train on bigger corpus (need GPU hours though)


