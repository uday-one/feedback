### README
# Keyword Extraction and Tag Suggestion System
This project aims to extract keywords from RSS feed articles and suggest relevant tags based on a predefined repository of tags.

## Features
Fetch and Parse XML: Retrieves XML content from an RSS feed and parses it to extract articles.
Text Preprocessing: Cleans the text by removing HTML entities, URLs, special characters, and extra whitespace.
Stopwords Removal: Utilizes SpaCy to eliminate common stopwords and non-alphabetic tokens from the text.
Keyword Extraction: Implements TF-IDF vectorization to identify the most significant keywords within the text.
Tag Suggestion: Suggests relevant tags by comparing text against a repository of predefined tags, considering both similarity and the number of associated articles.

## Requirements
Python 3.6+
Required libraries:
    - xml.etree.ElementTree
    re
    requests
    html
    spacy
    scikit-learn
    pandas
    Setup
    Install Dependencies:
    Ensure you have Python installed, then install the required libraries using pip.

Download SpaCy Model:
Download the SpaCy model for English to enable stopwords removal and text processing.

## Usage
Define File Paths:
Ensure that updated_tags.txt and num_articles.txt files are available in your working directory. These files contain the predefined tags and the number of articles associated with each tag, respectively.

Run the Script:
Execute the script to fetch, process, and analyze the RSS feed articles. The script will print the extracted keywords and suggested tags for each article.

## Code Overview
Preprocess Text:

Cleans the text by removing unwanted characters and HTML entities.
Strips extra whitespace to normalize the content.
Remove Stopwords:

Uses SpaCy's language model to filter out common stopwords and retain meaningful words.
Extract Keywords:

Applies TF-IDF vectorization to extract the most significant keywords from the text.
Read Tags and Articles:

Reads tags and their associated article counts from provided files to create a reference DataFrame.
Suggest Tags:

Vectorizes both the combined text and repository tags.
Uses cosine similarity to suggest the most relevant tags based on the predefined repository.

## Example Usage:

Fetches and parses the RSS feed.
Processes each article to extract keywords and suggest tags.
Prints the extracted and suggested tags for each article.
Error Handling
Invalid XML Content: The script catches and reports XML parsing errors to prevent crashes and ensure smooth execution.
Request Errors: Handles HTTP request failures gracefully, providing informative error messages.

## Sample Output
For each article, the script will output the following information:

Title: The title of the article.
Link: The URL of the article.
Summary: A brief summary of the article.
Original Tags: Tags originally assigned to the article.
Extracted Keywords: Keywords identified by the TF-IDF vectorizer.
Suggested Tags: Relevant tags suggested based on similarity and the number of articles.
Content: The cleaned and processed content of the article.
By following this guide, you should be able to set up and run the keyword extraction and tag suggestion system on your own data.
