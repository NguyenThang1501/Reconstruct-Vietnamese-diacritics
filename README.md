---

# Vietnamese Diacritics Restoration

This project aims to restore diacritics in Vietnamese text using a character-based approach. The model is trained to predict the correct diacritics for a given word or sentence, starting with a dataset of text from various news articles. The process involves two main stages: dataset creation and model building.

## 1. Dataset Creation

The initial dataset consists of 11 folders, each corresponding to a specific category of news from the VNExpress website. These categories are:

- doi-song (Lifestyle)
- du-lich (Travel)
- giai-tri (Entertainment)
- giao-duc (Education)
- khoa-hoc (Science)
- kinh-doanh (Business)
- phap-luat (Law)
- suc-khoe (Health)
- the-gioi (World)
- the-thao (Sports)
- thoi-su (Current Affairs)

Each folder contains text files, each representing a single article. The process of creating the dataset involves the following steps:

1. **Sentence Splitting**: Articles are split into individual sentences.
2. **Diacritics Removal**: The diacritics are removed from each sentence to create the training data. The result is a dataset with pairs of sentences: one with diacritics and one without.

This dataset will be used to train a model to restore the diacritics on the input sentences.

## 2. Approach

The model follows a **character-based approach**, where each sentence is treated as a sequence of characters, and the goal is to restore the original diacritics for each character.

## 3. Model Architecture

Two models are built for this task:

### Initial Model:
The first model consists of three layers:
- **Embedding Layer**: Transforms input characters into dense vectors.
- **LSTM Layer**: Processes the sequence of characters and captures dependencies between characters.
- **Dense Layer**: Outputs the predicted diacritics for each character.

### Improved Model:
The second model builds upon the first by adding two additional layers:
- **Additional LSTM Layer**: Enhances the model's ability to predict by processing the data in more depth.
- **Dropout Layer**: Helps prevent overfitting, especially as the complexity of the model increases.

