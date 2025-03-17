# PDF-to-CSV-Converter

## Overview
This project provides a simple GUI-based tool for extracting tabular data from PDF files and saving it as CSV. It uses `pdfplumber` for extracting tables from PDFs and `pandas` for data processing. The application is built using `tkinter` and is packaged as an executable for user convenience.

## Features
- Extract tables from PDFs automatically
- Data cleaning and processing to structure extracted tables
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
[Your Name]

## Contributions
Contributions are welcome! If you find any issues or have suggestions, feel free to open an issue or submit a pull request on GitHub.

