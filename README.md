# Multi-Domain Sentiment Dataset Preprocessing for BERT

## Overview
This project aims to download, preprocess, and prepare the Multi-Domain Sentiment Dataset for use with the BERT model. The dataset contains product reviews from various domains, and the preprocessing script formats the data for NLP tasks, particularly sentiment analysis.

## Dataset
The Multi-Domain Sentiment Dataset is designed for domain adaptation in sentiment classification. It contains product reviews from Amazon.com, covering multiple domains such as books, DVDs, and electronics. Each review is labeled with a star rating that can be converted into binary labels.

- **Download Links:**
  - [Unprocessed Data (unprocessed.tar.gz)](https://www.cs.jhu.edu/~mdredze/datasets/sentiment/unprocessed.tar.gz) (1.5 G)
  - [Processed Data (processed_acl.tar.gz)](https://www.cs.jhu.edu/~mdredze/datasets/sentiment/processed_acl.tar.gz) (19 M)
  - [Processed Stars Data (processed_stars.tar.gz)](https://www.cs.jhu.edu/~mdredze/datasets/sentiment/processed_stars.tar.gz) (33 M)

## Requirements
- Python 3.6 or higher
- Requests library

You can install the required libraries using pip:

```bash
pip install requests


Here's the final README file in a single snippet for you to copy and paste:

markdown
Copy code
# Multi-Domain Sentiment Dataset Preprocessing for BERT

## Overview
This project aims to download, preprocess, and prepare the Multi-Domain Sentiment Dataset for use with the BERT model. The dataset contains product reviews from various domains, and the preprocessing script formats the data for NLP tasks, particularly sentiment analysis.

## Dataset
The Multi-Domain Sentiment Dataset is designed for domain adaptation in sentiment classification. It contains product reviews from Amazon.com, covering multiple domains such as books, DVDs, and electronics. Each review is labeled with a star rating that can be converted into binary labels.

- **Download Links:**
  - [Unprocessed Data (unprocessed.tar.gz)](https://www.cs.jhu.edu/~mdredze/datasets/sentiment/unprocessed.tar.gz) (1.5 G)
  - [Processed Data (processed_acl.tar.gz)](https://www.cs.jhu.edu/~mdredze/datasets/sentiment/processed_acl.tar.gz) (19 M)
  - [Processed Stars Data (processed_stars.tar.gz)](https://www.cs.jhu.edu/~mdredze/datasets/sentiment/processed_stars.tar.gz) (33 M)

## Requirements
- Python 3.6 or higher
- Requests library

You can install the required libraries using pip:

```bash
pip install requests
Setup
Clone this repository or download the script file.
Ensure you have Python and the necessary libraries installed.
Usage
Run the script to download and preprocess the dataset:
bash
Copy code
python download_and_preprocess.py
The script will create a directory named multi_domain_sentiment_dataset and download the datasets into it. The processed reviews will be stored in a structured format suitable for BERT.

You can view the preprocessed data by examining the output printed by the script, which displays sample reviews along with their labels.

Code Structure
download_and_preprocess.py: The main script that handles downloading and preprocessing the dataset.
multi_domain_sentiment_dataset/: Directory containing the downloaded and extracted datasets.
Example Output
The script will print a sample of the preprocessed reviews and labels, like so:
Review: This book was a fantastic read, very engaging!
Label: positive

Review: I found this product to be quite disappointing.
Label: negative
Notes
Ensure that you have enough disk space, as the unprocessed dataset is approximately 1.5 GB in size.
The preprocessed data is formatted to be compatible with BERT, making it easier to integrate into your NLP models.
License
This project is licensed under the MIT License. Feel free to use and modify the code as needed.

Contact
For any questions or issues regarding this project, please reach out to Ashish Thapa at ashish.thapa2@students.mq.edu.au





