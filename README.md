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
