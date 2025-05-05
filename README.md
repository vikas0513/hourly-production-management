# hourly-production-management
This Python script processes and visualizes hourly production data for an automotive parts manufacturing plant. It supports data loading from either a MySQL database or an Excel file, performs key metric calculations, exports processed data for Power BI use, and generates interactive charts for quick insights.

Features
Flexible Data Input:

Load production data from MySQL or an Excel file.

Automated Metrics:

Calculate production efficiency, defect rate, and downtime impact.

Data Export:

Export processed data to Excel for reporting (e.g., Power BI dashboards).

Visualization (Optional):

Generate interactive line and bar charts using Plotly.

Requirements
Python 3.8+

Required libraries:

pandas

plotly

mysql-connector-python

Install dependencies via:


pip install pandas plotly mysql-connector-python
Configuration
Edit the following variables in the script as needed:

USE_SQL = False  # Set to True to use MySQL; False for Excel input
SQL_PASSWORD = "your_password"  # Your MySQL root password
EXCEL_INPUT_PATH = r"C:\path\to\your\hourly_data_input.xlsx"
EXCEL_OUTPUT_PATH = "hourly_data_processed.xlsx"
How It Works
Load Data:

If USE_SQL = True, connects to the MySQL database production_db and queries joined production and shift data.

If USE_SQL = False, reads from the specified Excel file.

Process Data:

Calculates:

Efficiency (%) = (Actual Output / Target Output) * 100

Defect Rate (%) = (Defects / Actual Output) * 100

Downtime Impact (%) = (Downtime Minutes / 60) * 100

Export:

Saves the processed data to a new Excel file for further use in tools like Power BI.

Visualization:

Optionally previews:

Hourly efficiency (line chart)

Defect rate by hour (bar chart)

Downtime impact (line chart)

Running the Script
To execute:


python hourly\ production\ management.py
You’ll see a message confirming the processed Excel file save path, and if using the visualization step, Plotly charts will open in your browser.

Notes
The script currently targets data for a fixed date (2025-04-21) and shift (Morning) when querying from SQL. You can modify the SQL query section to parameterize this as needed.

Make sure your Excel input file has the following columns:

MachineID

Hour

TargetOutput

ActualOutput

CumulativeOutput

Defects

DowntimeMinutes

Date

Shift

OperatorName

ProductName

DowntimeReason

OperatorRemarks

License
This project is open-source and available for personal or professional use. Attribution is appreciated.

