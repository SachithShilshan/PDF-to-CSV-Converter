# PDF to CSV Converter

## Overview
This project provides a simple GUI-based tool for extracting tabular data from PDF files and saving it as CSV. It uses `pdfplumber` for extracting tables from PDFs and `pandas` for data processing. The application is built using `tkinter` and is packaged as an executable for user convenience.

## Features
- Extract tables from PDFs automatically
- Data cleaning and transformation to structure extracted tables properly
- Saves the output as a CSV file
- User-friendly GUI for selecting PDF files and saving extracted data
- Packaged as an executable for ease of use

## Requirements
### Python Dependencies
Ensure you have the following Python libraries installed before running the script:

```bash
pip install pdfplumber pandas tkinter
```

## Usage
### Running the Script
1. Run the Python script:
   ```bash
   python pdf_to_csv_converter.py
   ```
2. Click the **Upload PDF** button to select a PDF file.
3. The script extracts tabular data and prompts you to save it as a CSV file.
4. Choose a save location, and the extracted data will be saved successfully.

### Running the Executable
If you have the EXE version:
1. Double-click on the `pdf_to_csv_converter.exe` file.
2. Follow the same steps as above.

## Data Extraction & Transformation Logic
### Step 1: Extracting Tables from PDFs
- The script uses `pdfplumber` to read each page of the PDF and extract tables.
- Extracted tables are stored as Pandas DataFrames.

### Step 2: Structuring the Data
- All extracted tables are concatenated into a single DataFrame.
- A new column **Category** is created to categorize data based on specific conditions.
- Rows containing the keyword **Level** are marked under **Category** as `LevelX`.
- The **Category** column is forward-filled to ensure proper labeling.

### Step 3: Identifying Relevant Data
- The script scans specific columns (5-9) to identify keywords like **Color** and **Description**.
- A new column **Custom** is created to classify rows as `ColorX` or `DescriptionX`.
- The column **ColoNo** stores the detected column index for further processing.
- Forward-fill is applied to maintain proper indexing and alignment.

### Step 4: Extracting Description Data
- Rows categorized as `DescriptionX` are processed separately.
- The first row is promoted as column headers.
- Rows where **Level = 1** are retained.
- Irrelevant columns (empty, `LevelX`, `DescriptionX`, etc.) are dropped.

### Step 5: Extracting and Cleaning Color Data
- Rows categorized as `ColorX` are processed in a loop from columns 4-9.
- Data is transposed, ensuring correct alignment and removing irrelevant entries.
- Extra spaces are trimmed, and missing values are replaced.
- Data is re-transposed to restore the original table structure.
- The first row is promoted as column headers again.
- Only rows where **Level = 1** are retained.

### Step 6: Merging Data
- Both extracted datasets (`Description` and `Color`) are standardized by renaming columns.
- They are merged using columns like **Level, Item Part, Item Part Comments, Main Material, Product**.
- The final transformed DataFrame is ready for export.

## Converting Python Script to Executable
If you want to generate an EXE file from the Python script, use `pyinstaller`:

```bash
pip install pyinstaller
pyinstaller --onefile --windowed pdf_to_csv_converter.py
```
This will create an executable file inside the `dist/` directory.

## License
This project is licensed under the MIT License. Feel free to modify and distribute it as needed.

## Author
Sachith Shilshan

## Contributions
Contributions are welcome! If you find any issues or have suggestions, feel free to open an issue or submit a pull request on GitHub.

