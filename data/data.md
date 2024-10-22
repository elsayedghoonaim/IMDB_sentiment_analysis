# Data Download Instructions

## Option 1: Direct Download from Kaggle
1. Visit the [IMDB Dataset (Sentiment Analysis) in CSV format](https://www.kaggle.com/datasets/columbine/imdb-dataset-sentiment-analysis-in-csv-format) on Kaggle
2. Click the "Download" button
3. Place the downloaded files in the `data/` directory of this project

## Option 2: Using Python and kagglehub

```python
import kagglehub

# Download latest version
path = kagglehub.dataset_download("columbine/imdb-dataset-sentiment-analysis-in-csv-format")
print("Path to dataset files:", path)
```

### Prerequisites for kagglehub method:
1. Install kagglehub:
```bash
pip install kagglehub
```

## Dataset Structure
After downloading, ensure your data directory looks like this:
```
data/
├── Train.csv
├── Test.csv
└── Valid.csv
```

## Dataset Information
- Total samples: 50,000
- Format: CSV
- Columns:
  - `text`: Review text
  - `label`: Sentiment (0 for negative, 1 for positive)
- Split:
  - Training: 40,000 samples
  - Testing: 5,000 samples
  - Validation: 5,000 samples

## Data Usage Terms
Please refer to the [Kaggle dataset license](https://www.kaggle.com/datasets/columbine/imdb-dataset-sentiment-analysis-in-csv-format/metadata) for terms of use.
