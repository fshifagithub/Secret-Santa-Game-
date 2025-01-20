
# Secret Santa Game 

The company "Acme" has decided to organize a Secret Santa event for its employees. This program automates the process of assigning "Secret Children" to each employee while adhering to certain rules and constraints, ensuring a fair and enjoyable experience.





## Features

- Reads employee data and past Secret Santa results from CSV files.
- Randomly assigns a "Secret Child" to each employee while adhering to specific constraints.
- Outputs the results in a new CSV file.
- Handles file-related and data-related errors gracefully.




## Installation

1. Ensure you have Python 3.7 or later installed.
2. Install the required libraries using pip:
   pip install pandas

## Input Files

1. 'Employee-List - Copy.csv':
   - The file should have at least two columns: Employee_Name, Employee_EmailID.
2. 'Secret-Santa-Game-Result-2023 - Copy.csv':
   - The file should have at least four columns: Employee_Name, Employee_EmailID, Secret_Child_Name, Secret_Child_EmailID.


## Usage

1. Run the script:
   python secret_santa_game.ipynb
2. The program reads the input files, performs the Secret Santa assignments, and generates an output file:
   - 'secret-santa-result.csv': Contains the Secret Santa assignments.


## Error Handling

1.Handles FileNotFoundError, EmptyDataError, and other exceptions related to file input/output.

2.Ensures valid Secret Child assignments by checking constraints.

## Example Input & output

Employee-List - Copy.csv:
| Employee_Name | Employee_EmailID    |
|---------------|---------------------|
| Alice         | alice@example.com   |
| Bob           | bob@example.com     |

Secret-Santa-Game-Result-2023 - Copy.csv:

| Employee_Name | Employee_EmailID    | Secret_Child_Name | Secret_Child_EmailID  |
|---------------|---------------------|-------------------|-----------------------|
| Alice         | alice@example.com   | Bob               | bob@example.com       |


secret-santa-result.csv:
| Employee_Name | Employee_EmailID    | Secret_Child_Name | Secret_Child_EmailID  |
|---------------|---------------------|-------------------|-----------------------|
| Alice         | alice@example.com   | john              | john@example.com       |
| Bob           | bob@example.com     | benny            | benny@example.com     |


## working

This script implements a Secret Santa assignment program using Python and pandas. The purpose is to randomly assign each employee a "Secret Child"  while respecting certain constraints.

- load_csv(file_path)
Purpose: Reads a CSV file into a pandas DataFrame.
Error Handling: If the file is not found, it returns None and logs an error.

-get_random(rows_as_list, previous_data, email, assigned_emails)

Purpose: Finds a random "Secret Child" for a given employee based on the following constraints:
The "Secret Child" was not the same as the one assigned in the previous year.
The "Secret Child" is not the same as the employee themselves.
The "Secret Child" has not already been assigned.
Logic: Loops through previous data to avoid assigning the same child as last year. It uses a while loop to ensure a valid child is chosen.

-secret_santa()

 - Convert excel files into csv
 - Load Input Files: Two CSV files are loaded:
 - Employee-List - Copy.csv: Contains the current list of employees.
 - Secret-Santa-Game-Result-2023 - Copy.csv: Contains the previous year's assignments.
   


Initialize a dictionary data to store the new assignments.
Assign Secret Children:  For each employee, call get_random to select a valid Secret Child.  Append the results to the data dictionary.
Log a warning if no valid Secret Child is found.

Save Results:
Convert the data dictionary to a pandas DataFrame.
Save the results as a CSV file named secret-santa-result.csv.

