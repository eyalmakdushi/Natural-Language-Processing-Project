# NLP Project: Intelligent System for Question Answering

### Author: Eyal Makdushi (208879718)

## Project Description

This project focuses on developing an intelligent system that responds to inquiries or provides relevant details from textual data. The system utilizes two techniques:

1. **Seq2Seq LSTM Model**: Trained using the AG News Classification Dataset to handle questions across various subjects.
2. **GPT-2 Fine-tuning**: OpenAI's GPT-2 model fine-tuned on the same dataset to improve precision in answering questions.

## Data Overview

- **Dataset**: AG News Classification Dataset.
- **Categories**: The dataset contains news articles classified into four categories: World, Sports, Business, and Sci/Tech.
- **Features**: Each article includes a `Title` and a `Description`.
- **Preprocessing**: Tokenization, lemmatization, and removal of stop-words and special characters.

## Model Overview, Metrics, and Outcomes

### 1. **Seq2Seq LSTM Model**

- **Architecture**:
  - Encoder: Processes the input sequence (Title and Description) using an LSTM layer and converts it into a context vector.
  - Decoder: Utilizes the context vector to predict the output sequence (Description).
- **Training**: The model aligns input (Title) with desired output (Description) using a seq2seq framework, with cross-entropy loss and the Adam optimizer. Teacher forcing is applied during training.
- **Tests**:
  - 500 test / 1000 train
  - 800 test / 2000 train
  - 1000 test / 5000 train
  - 2000 test / 10000 train
- **Learning Rate Tests**:
  - 2000 test / 10000 train / 0.01 learning rate
  - 2000 test / 10000 train / 0.1 learning rate
- **Epochs**: Increasing epochs from 10 to 50 showed diminishing returns after 10 epochs.

### 2. **GPT-2 Fine-tuning**

- **Model Structure**: Based on the transformer architecture, GPT-2 generates text based on input context. Fine-tuning is done using the AG News dataset for answering questions.
- **Training**: The pre-trained GPT-2 model is fine-tuned using a language modeling objective, adjusting parameters with the AdamW optimizer and learning rate scheduler.
- **Performance**: Tested on datasets to assess the accuracy of answers.

## Comparison and Assessment

Both models are evaluated based on their ability to answer questions and extract information. Each model's architecture and training processes are tailored to their specific goals.

### Accuracy Graph
- A graph comparing the accuracy of both the Seq2Seq LSTM model and the GPT-2 model.

## Future Improvements

1. **User Access**: Build a user-friendly interface for model interaction.
2. **Incorporating Attention**: Add attention mechanisms to the Seq2Seq model for better context understanding.
3. **Model Stacking**: Combine model predictions for improved accuracy.
4. **Fine-tuning Larger Models**: Explore fine-tuning GPT-3 for higher accuracy.
5. **Increasing Data**: Add more news articles to enhance generalization.

