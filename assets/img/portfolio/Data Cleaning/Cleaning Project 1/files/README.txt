Data Source: https://www.kaggle.com/datasets/faresashraf1001/supermarket-sales

Excel Data Cleaning Challenge

Project Overview:
	This is a demonstration for my data collection and cleaning skill. The project can be summarize in a few sentences. I have collected a dirty dataset from Kaggle ( the online data science community ). I used multiple data cleaning strategies to clean this dataset and make it ready for further analysis. I used Microsoft Excel for this task.




Data Cleaning Steps:


- Inspection & Understanding of the Data

	Opened the data set and used data filter to view unique values in key columns such as (Branch, City, 	Customer type, Product line).
	created a separate sheet to note down column descriptions, data types, expected ranges (this became my 	mini data dictionary).


- Note on Dataset Quality

	During the inspection phase, it was observed that the dataset was already in a well-maintained state, with 	no missing values, duplicates, or major inconsistencies.
	This provided an opportunity to validate the dataset’s cleanliness and confirm data integrity.
	Even though minimal correction was required, I systematically applied all standard data cleaning checks — 	such as verifying data types, formatting columns, checking business logic, and standardizing categorical 	fields — to ensure the dataset’s readiness for future analysis and visualization.


- Removing Duplications

	Checked for duplicates and found none


- Standardize Date & Time Columns

	Ensured the Date column is in a consistent date format: I selected the date column → Home → Number Format → Short DateSimilarly for time column. I selected it → 	Home → Number → Time


- Fixing Text Casing & Whitespace Issues

	Used =Trim() function to remove extra leading or trailing spaces.
	Used =PROPER() or =UPPER() functions as needed to standardize capitalization.
	Double-checked values in columns like “Gender”, “Customer type” that may have variations (e.g., “female”, “Female”, “FEMALE”) and use Find & Replace and 	formula to standardize.


- Handling Missing / Blank Values

	Used Filter to check for blanks in each column.	I found no blank columns.
	So, I used conditional formatting just to double check. It was confirmed that the dataset has no blank columns


- Validation of Numeric Columns & Data Types

	Made sure numeric columns such as “Unit price”, “Quantity”, “Tax”, “Total”, “COGS”, “Gross income” are formatted as 	Number (or Currency).


- Checked for Outliers / Inconsistent Values

	Used Insert → PivotTable or Filter + Sort to find min and max values in numeric columns (e.g., a “Total” value that 	seems too low or too high)
	Used Conditional Formatting → Highlight Cell Rules → Greater Than / Less Than to highlight potential outliers.
	

- Standardized Categorical Values & Correct Typos
	
	Inspected unique values (via Filter) in categorical columns (e.g., “Product line”, “Payment”, “Branch”).
	Used Find & Replace to correct typo variants (e.g., “Food and beverages” vs “Food & Beverages”).
	Used Vertical Lookup aka =VLOOKUP() function to look for specific typos and misspellings.

- Created Derived Columns

	Example: From “Date” derived “Month” and “Day of week” using =TEXT([Date],"mmmm") or =TEXT([Date],"dddd").
	From “Time” I derived “Part of day” using the formula: 
	=IF(VALUE(TEXT(A2,"hh:mm AM/PM"))<VALUE("12:00 PM"),"Morning",IF(VALUE(TEXT(A2,"hh:mm AM/PM"))<VALUE("06:00 PM"),"Afternoon","Evening"))


- Validated Business Logic & Relationships

	Example: Checked if Total = Unit price * Quantity + Tax . Used a formula to compute expected and compare: =IF([Total] = [Unit Price]*[Quantity] + [Tax], "OK", 	"Check").


- Business Logic Validation
	
To ensure data integrity beyond formatting checks, several logical relationships were tested within the dataset:

	Verified that Sales = Unit Price × Quantity + Tax 5% using Excel formulas.

	Confirmed that Tax 5% = COGS × 0.05, ensuring the tax field was correctly derived.

	Checked that Gross Income = Tax 5% and Gross Margin Percentage = 4.76% across all rows.

	Validated that Ratings fell between 1 and 10, and Quantities and Sales were greater than zero.

	Used conditional formatting to visually flag any anomalies or mismatched rows.

	All validation checks returned “OK”, confirming that the dataset adhered to expected business rules and was logically consistent.


- Outcome

	The dataset was verified to be clean, consistent, and analysis-ready.
	This exercise demonstrated structured data validation and documentation practices, confirming that the 	dataset adheres to professional standards of data quality.