## DATA INGESTION RULES

1. FILE NAMING (CRITICAL)
   The engine extracts the stock ticker directly from the filename. 
   You MUST place the ticker in brackets, regardless of its position in the file name.
   
   * Correct: *Turkish Airlines (THYAO).csv*
   * Correct: *(THYAO) Turkish Airlines Historical Data.csv*
   * Incorrect: *THYAO Historical Data.csv* [Engine will fail]

2. COLUMN STRUCTURE
   Input CSVs must strictly match the schema defined in `Data_Dictionary.csv`.
   (Must have the following columns in order: Date | Price | Open | High | Low | Vol. | Change %)

3. REGISTERING NEW STOCKS
   The system does not automatically detect the sector of new files.
   Before refreshing, you MUST add the new [TICKER] and its Industry/Sector 
   to the `Industry_Map.csv` file.

####   Note on Scalability:
The Correlation Matrix is pre-configured for the core BIST 30 index. If you add more than 30 assets to the dataset, the dynamic headers will update automatically, but you must manually drag the correlation formula (Cell AE31) down and across to cover the new range.