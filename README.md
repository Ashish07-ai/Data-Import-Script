# Data-Import-Script
import os
import requests
import tarfile

# Define the URLs for downloading the datasets
urls = {
    "unprocessed": "https://www.cs.jhu.edu/~mdredze/datasets/sentiment/unprocessed.tar.gz",
    "processed_acl": "https://www.cs.jhu.edu/~mdredze/datasets/sentiment/processed_acl.tar.gz",
    "processed_stars": "https://www.cs.jhu.edu/~mdredze/datasets/sentiment/processed_stars.tar.gz"
}

# Create a directory to store the dataset
data_dir = "multi_domain_sentiment_dataset"
os.makedirs(data_dir, exist_ok=True)

def download_and_extract(url, directory):
    """Download and extract a tar.gz file."""
    response = requests.get(url)
    tar_path = os.path.join(directory, os.path.basename(url))

    # Write the tar file
    with open(tar_path, 'wb') as file:
        file.write(response.content)

    # Extract the tar file
    with tarfile.open(tar_path, "r:gz") as tar:
        tar.extractall(path=directory)
    print(f"Downloaded and extracted: {url}")

# Download and extract all datasets
for name, url in urls.items():
    download_and_extract(url, data_dir)

# Example of preprocessing the data
def preprocess_data(data_directory):
    """Preprocess the reviews to create a structured dataset for BERT."""
    processed_data = []
    
    for domain in os.listdir(data_directory):
        domain_path = os.path.join(data_directory, domain)
        if os.path.isdir(domain_path):
            # Read the processed.review.balanced file
            processed_file_path = os.path.join(domain_path, "processed.review.balanced")
            if os.path.isfile(processed_file_path):
                with open(processed_file_path, 'r') as f:
                    for line in f:
                        # The last token in each line is the label
                        parts = line.strip().split(' ')
                        label = parts[-1].split(':')[-1]  # Get label from the last token
                        text = ' '.join(parts[:-1])  # Join the rest as the review text
                        processed_data.append((text, label))

    return processed_data

# Preprocess the dataset
preprocessed_reviews = preprocess_data(data_dir)

# Show a sample of the preprocessed data
for review, label in preprocessed_reviews[:5]:
    print(f"Review: {review}\nLabel: {label}\n")
