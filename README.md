
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
   python secret_santa.py
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
