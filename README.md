# Sentiment Analysis Project

## Overview
This project demonstrates sentiment analysis using machine learning techniques to classify text data into positive or negative sentiments. The implementation uses a deep learning approach with a bidirectional LSTM neural network architecture.

## Dataset
The dataset consists of 50,000 text reviews with binary sentiment labels:
- Training set: 40,000 samples
- Test set: 5,000 samples
- Validation set: 5,000 samples

Data distribution is well-balanced with:
- Positive samples: 24,884
- Negative samples: 24,698

## Project Structure
```
sentiment_analysis/
├── data/
│   ├── Train.csv
│   ├── Test.csv
│   └── Valid.csv
├── sentiment_analysis.ipynb
├── License
└── README.md
```

## Requirements
- Python 3.x
- TensorFlow
- Pandas
- NumPy
- NLTK
- TextBlob
- Matplotlib
- Seaborn
- WordCloud

## Implementation Details

### 1. Data Preprocessing
- Text cleaning (removing HTML tags, special characters)
- Lowercasing
- Stopword removal
- Tokenization
- Sequence padding

### 2. Model Architecture
```
Model: Sequential
├── Embedding Layer (128 dimensions)
├── Bidirectional LSTM (64 units, return sequences=True)
├── Bidirectional LSTM (32 units)
├── Dense Layer (64 units, ReLU activation)
├── Dropout (0.5)
└── Dense Layer (1 unit, Sigmoid activation)
```

### 3. Training Configuration
- Optimizer: Adam (learning_rate=0.001)
- Loss: Binary Crossentropy
- Batch Size: 32
- Epochs: 5

## Results
- Test Accuracy: 89.44%
- Test Loss: 0.323

## Visualizations
The notebook includes various visualizations:
- Word count distributions
- Average review length by sentiment
- Top 20 words in positive/negative reviews
- Word clouds for both sentiments
- Training history (accuracy and loss curves)

## Usage
To use the trained model for sentiment prediction:

```python
def predict_sentiment(text):
    sequence = tokenizer.texts_to_sequences([text])
    padded = tf.keras.preprocessing.sequence.pad_sequences(
        sequence, 
        maxlen=200, 
        padding='post'
    )
    prediction = model.predict(padded)
    return (prediction > 0.5).astype(int)
```

## Future Improvements
1. Experiment with different model architectures
2. Implement cross-validation
3. Add data augmentation techniques
4. Try different preprocessing steps
5. Implement model deployment functionality

## License
MIT License

## Contact
elsayedghoonaim@gmail.com
