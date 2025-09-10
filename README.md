# VedaBot
This project utilizes a Retrieval-Augmented Generation (RAG) system integrating a local Large Language Model and an external API to deliver contextual answers from the four Vedas, utilizing NLP and prompt engineering. The Vedas, as ancient and foundational scriptures of Hinduism, offer profound insights into philosophy, rituals, and the human condition, making this project significant for accessing and understanding their vast knowledge.

_________________________________________________________________________________________________________________________________________________________________

## Features:

### Automated NLTK Data Management: 
Automatically checks for and downloads necessary NLTK data (punkt, wordnet, stopwords) upon the first run, streamlining setup.

### Robust Text Preprocessing: 
Cleans and prepares the raw text by converting to lowercase, removing non-alphabetic characters, tokenizing words, and applying both general and custom English stop word removal (including terms like 'thou', 'veda', 'hymn' relevant to the Vedas). It also performs lemmatization to reduce words to their base form.

### Basic Text Statistics:
Provides foundational insights into the corpus, including total word count, unique word count, and a list of the most frequently occurring words after preprocessing.

### Topic Modeling with LDA: 
Utilizes Latent Dirichlet Allocation (LDA) to identify underlying themes and topics present across the hymns, offering a high-level understanding of the text's content.

### TF-IDF Keyword Extraction:
Pinpoints important keywords for individual hymns (documents) using the TF-IDF (Term Frequency-Inverse Document Frequency) method, highlighting unique vocabulary for each section.

### Collocation Analysis: 
Discovers frequently co-occurring word pairs (bigrams) and triplets (trigrams), revealing significant phrases and idiomatic expressions within the text.

### Contextual Explanations:
Integrates with the Google Gemini API to generate detailed cultural, religious, or ritualistic explanations for identified collocations, providing deeper insights into their meaning within the Vedic context.
___________________________________________________________________________________________________________________________________________________________________

## Prerequisites:

Before running the script, ensure you have the following:

Python 3.x

### Required Python Libraries: 
You can install these using pip:

pip install nltk scikit-learn gensim google-generativeai pandas numpy

### Vedic Text File: 
A text file named Four-Vedas-English-Translation.txt must be placed in the same directory as the script. This is the primary input for the analysis.

### Google Gemini API Key: 
To utilize the AI explanation feature, you'll need a Google Gemini API key.

Obtain your API key from Google AI Studio.
_________________________________________________________________________________________________________________________________________________________________

## Configuration:

You can easily modify certain parameters within the script:

### Input File: 
Change file_path = 'Four-Vedas-English-Translation.txt' to analyze a different text file.

### Number of Topics (LDA): 
Adjust num_topics = 5 to vary the number of themes LDA attempts to discover.

### Custom Stop Words: 
Modify the custom_stopwords set to refine the list of words excluded from analysis.

### Collocation Frequency Filters: 
The apply_freq_filter values for bigram_finder (currently 5) and trigram_finder (currently 3) can be changed to set the minimum occurrences for a collocation to be considered.

### Gemini Model: 
The script uses gemini-1.5-flash. While generally suitable, in advanced use cases, you might explore other compatible models if listed by the API.
_________________________________________________________________________________________________________________________________________________________________
## Troubleshooting:

### FileNotFoundError: 
Double-check that Four-Vedas-English-Translation.txt (or your specified file_path) is correctly placed in the script's directory.

### MemoryError during LDA: 
If you encounter memory issues, especially with large texts, try reducing the num_topics or increasing the passes value in the LdaModel parameters.

Gemini API Errors (404, etc.): Ensure your API key is correct and has the necessary permissions. Also, confirm that the model name (gemini-1.5-flash) is current and supported by the API.
