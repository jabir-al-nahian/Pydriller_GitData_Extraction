# Pydriller_GitData_Extraction
Markdown

# Pydriller Git Data Extraction

This project uses the [Pydriller](https://pydriller.readthedocs.io/en/latest/) library to extract detailed information from a Git repository's history. It then processes this data using [Pandas](https://pandas.pydata.org/) and saves it into a CSV file.

## Installation

To use this script, you need to have Python installed on your system. You can install the necessary libraries using pip:

python Pydriller_GitData_Extraction.py
Upon successful execution, the script will print: Data Extraction Successful.
Output CSV File: The extracted data will be saved in a CSV file named numpy_commit_data.csv in the same directory where you ran the script.

**Data Output**
The numpy_commit_data.csv file will contain the following columns for each modified file in each commit:

commit_id: The unique hash of the commit.
author: The name of the commit author.
timestamp: The date and time when the commit was authored.
commit_message: The message associated with the commit.
file_path: The path of the modified file (new path if renamed).
file_type: The extension of the modified file.
insertions: The number of lines added in the file in that commit.
deletions: The number of lines removed from the file in that commit.
lines_changed: The total number of lines changed (insertions + deletions) in the file in that commit.
file_count: The total number of files modified in that commit.
Functionality
The script performs the following actions:

Imports Libraries: Imports the necessary libraries: Repository from pydriller, pandas for data manipulation, and os for file path operations.
Defines extract_commit_data Function:
Takes the repository URL as input.
Initializes an empty list data to store the extracted information.
Uses Repository(repo_url).traverse_commits() to iterate through each commit in the repository's history.
For each commit:
Calculates the total number of modified files in the commit.
Iterates through each modified file (m) in the commit.
Determines the correct file path, handling cases where files are renamed.
Extracts the file extension.
Appends a dictionary containing relevant commit and file information to the data list.
Prints "Data Extraction Successful." upon completion.
Returns the data list.
Runs Data Extraction: Calls the extract_commit_data function with the specified repository URL.
Creates Pandas DataFrame: Converts the extracted data list into a Pandas DataFrame for easy analysis and manipulation.
Saves to CSV: Saves the DataFrame to a CSV file named numpy_commit_data.csv without the DataFrame index.
This script provides a foundation for analyzing various aspects of a Git repository's evolution, such as code churn, author contributions, and file-specific changes over time.
