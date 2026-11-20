# 🧍 BRIHA · Gender Identification from Names

![Part of BRIHA](https://img.shields.io/badge/Part_of-BRIHA-8B5CF6?style=for-the-badge&labelColor=0B1024)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white) ![pandas](https://img.shields.io/badge/pandas-150458?style=flat-square&logo=pandas&logoColor=white) ![REST API](https://img.shields.io/badge/REST_API-1F6FEB?style=flat-square) ![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white)

> ⚡ **Part of [BRIHA](https://github.com/asad110abbas)** · Briha Research, built by Syed Asad Abbas.

Enriches a customer dataset with a **predicted gender for each name** using the NamSor name-classification API.
It processes thousands of rows in **rate-limited batches** and writes the results back to Excel.

## How it works
1. Load the dataset (Excel) with pandas
2. Take the first name from each `fullname`, skipping invalid or empty rows
3. Call the NamSor API in **batches of 200** with throttling to respect rate limits
4. Store `likelyGender` in a new column and export the enriched file

## Run
```bash
pip install pandas requests openpyxl
export NAMSOR_API_KEY="your-key"      # Windows: set NAMSOR_API_KEY=your-key
```
Open `Gender_Identification.ipynb`, point it to your Excel file and run.

> The API key is read from the environment and never hard-coded.
