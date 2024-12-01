# French Date Extractor

A Python project to extract publication dates from French PDF documents and their corresponding URLs.

## Project Goal

The main objective is to accurately extract publication dates from French documents by:
1. Processing the first pages of PDF documents
2. Extracting dates from associated URLs
3. Comparing extracted dates with human-annotated (gold) dates

## Challenges

### 1. PDF Processing Challenges
- **Mixed PDF Types**: Documents can be either digitally created or scanned
- **Complex Layouts**: PDFs may contain tables, headers, footers, and multiple columns
- **Quality Issues**: Scanned documents may have varying quality levels
- **Text Extraction**: Different PDFs require different extraction methods:
  - Text-based extraction for digital PDFs
  - OCR for scanned documents
  - Table extraction for structured documents

### 2. Date Extraction Challenges
- **Multiple Date Formats**: French date formats can vary:
  - DD/MM/YYYY
  - DD.MM.YYYY
  - DD-MM-YYYY
  - etc.
- **Multiple Dates**: Documents often contain multiple dates (creation date, publication date, revision date)
- **Context Understanding**: Need to identify which date represents the actual publication date

### 3. URL Date Extraction Challenges
- **Inconsistent Patterns**: URLs may contain dates in various formats and locations:
  - In the path: `/2024/03/01/`
  - In the filename: `document-18.12.2023.pdf`
- **False Positives**: Numbers in URLs that look like dates but aren't
- **Multiple Dates**: URLs might contain multiple dates (e.g., update date vs. creation date)

## Project Structure

```
French-Date-Extractor/
├── notebooks/          # Contains Jupyter notebooks with solution implementations
├── requirements.txt    # List of required Python packages
└── README.md           # Project documentation
```

## Installation and Running the Project

To set up the project environment and run the notebooks:

1. **Create a Virtual Environment**:
   ```bash
   python -m venv venv
   ```

2. **Activate the Virtual Environment**:
   - On Unix or macOS:
     ```bash
     source venv/bin/activate
     ```
   - On Windows:
     ```bash
     venv\Scripts\activate
     ```

3. **Install Required Packages**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Run a Jupyter Notebook**:
   ```bash
   jupyter notebook
   ```
   This will open the Jupyter interface in your browser. Navigate to the `notebooks/` directory and select the desired notebook to run.

## Methods Used

We employed the following methods to extract publication dates:

1. **Trellis API**: Utilized Trellis's API for date extraction.
2. **SparkNLP**: Applied natural language processing techniques using SparkNLP.
3. **Prompt Engineering with LLaMA via Ollama**: Implemented prompt engineering with the LLaMA language model running locally through Ollama.
4. **Prompt Engineering using LangChain and GPT Models**: Leveraged LangChain in conjunction with GPT models for prompt-based date extraction.

## Accuracy of Methods

| Method                                     | Accuracy |
|--------------------------------------------|----------|
| Trellis API                                | 77%      |
| Prompt Engineering using LangChain and GPT | 64%      |
| Prompt Engineering with LLaMA via Ollama   | 51%      |

This table summarizes the accuracy achieved by each method in extracting publication dates.
