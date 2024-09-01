# Stock-profit_loss-calculator
I got this in a company test for internship

# Investment Profit/Loss Calculator

This project extracts investment data from a PDF, processes it to calculate profit or loss for each stock, and summarizes the results by stock symbol.

## Table of Contents

- [Requirements](#requirements)
- [Usage](#usage)
- [Code Explanation](#code-explanation)
- [Output](#output)
- [Notes](#notes)

## Requirements

Ensure you have the following Python libraries installed:

```bash
pip install tabula-py pandas PyPDF2
```

- **tabula-py**: To convert PDF tables into CSV.
- **pandas**: For data manipulation.
- **PyPDF2**: For reading PDF files and extracting text.

## Usage

1. Place your investment PDF file in the specified path.
2. Update the `file_path` variable in the script with the path to your PDF file.
3. Run the script.

```python
python your_script.py
```

4. The script will print the net profit or loss for each stock in the specified format.

## Code Explanation

1. **PDF to CSV Conversion:**
   - The script uses `tabula.convert_into` to convert the PDF containing investment data into a CSV file.

2. **Header Extraction:**
   - The script uses `PyPDF2` to extract the header names from the first line of the PDF, assuming each column header consists of two words.

3. **Data Processing:**
   - The extracted CSV data is loaded into a pandas DataFrame.
   - Missing 'Date Sold' values are filtered out.
   - Profit or loss is calculated for each sold stock based on the difference between the sale price and purchase price multiplied by the number of shares.

4. **Grouping and Summarizing:**
   - The data is grouped by the stock symbol, and the net profit or loss for each stock is calculated.

5. **Output:**
   - The result is printed in the format: `Stock Symbol, Net Profit/Loss (PnL)`.

## Output

The script will output the net profit or loss for each stock symbol in the following format:

```
AAPL,2950.0
MSFT,2325.0
TSLA,3140.0
AMZN,1600.0
GOOG,1700.0
NFLX,900.0
NVDA,475.0
```

## Notes

- Ensure the PDF file is formatted correctly for accurate header extraction.
- Modify the file paths as necessary to match your directory structure.
- This script assumes that each column header in the PDF is two words long. Adjustments may be necessary for different formats.
