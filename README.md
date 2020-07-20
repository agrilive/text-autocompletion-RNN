# Text Autocompletion with RNN

The aim of this project is to create a text autocompletion model using Word and Character-level RNNs. In other words, we are trying to predict the next character/word in a user's search query. This project can be used as part of a messaging application, such as emails, or even a search engine where users type in their queries.

## Dataset

I used two datasets to identify if the training dataset size affects the autocompletion model. The smaller dataset is retrieved by exporting my personal Outlook email. It contains approximately 200 emails (which translates to about 170 sentences). On the other hand, the larger dataset is a sample of Enron's email dataset [available on Kaggle](https://www.kaggle.com/wcukierski/enron-email-dataset). This sample contains 2.5k emails (which translates to about 17k sentences).

## Steps

1. Data cleaning 
   - Notebook: [preprocessing_dataCleaning.ipynb](https://github.com/agrilive/text-autocompletion-RNN/blob/master/preprocessing_dataCleaning.ipynb)
2. Training and testing RNN model 
    - Word RNN notebook: [autocompletion_wordRNN.ipynb](https://github.com/agrilive/text-autocompletion-RNN/blob/master/autocompletion_wordRNN.ipynb)
    - Character RNN notebook: [autocompletion_charRNN.ipynb](https://github.com/agrilive/text-autocompletion-RNN/blob/master/autocompletion_charRNN.ipynb)
    
## Results

### Word-level RNN

Testing the next word prediction for "business meetings".

```
Enter string: business meetings are
Output: business meetings are expected to rise on the

Enter string: business meetings
Output: business meetings as exodus documents to manage
```

### Character-level RNN

Testing if model is able to predict the word "discussion".

```
Enter string: discuss
Output: discuss   c a n a

Enter string: discussio
Output: discussio n e m a r
```

Overall, the larger dataset gave a better prediction than the smaller dataset. The word-level RNN model gives a better prediction than the character-level RNN. Given the promising results, an even larger dataset can be used to train the model. However, on top of the time-consuming nature of training the RNN models, one needs to note that the data cleaning process is quite time-consuming as well.

In addition, it will be interesting to find out if both the character-level and word-level RNN can be combined to give both character and word predictions.
