# "Hogwarts Student Sorter: CSV-Based House Assignment and Grade Calculation"

#### Video Demo:

#### Description:

## Overview

This project processes a CSV file containing student data, categorizing each student into a Hogwarts house based on their characteristics and calculating their grade level based on their birthdate. The processed data is then written to a new CSV file.

## File Structure

The project consists of the following files:

1. **project.py**: The main script that handles reading the input CSV file, processing the data, and writing the output CSV file.
2. **test_project.py**: Contains unit tests for the functions in `project.py` using the `pytest` framework.

## Requirements

- Python 3.6+
- `pytest` for running tests

## Setup and Installation

1. **Clone the repository**:

   ```bash
   git clone https://github.com/code50/168655717/blob/30665fbca3c80673a29865e1d03b073ba32c8871/project
   ```

2. **Install dependencies** (if any):

   ```bash
   pip install pytest
   ```

## Usage

### Running the Script

To run the script, use the following command:

```bash
python project.py input.csv output.csv
```

Replace `input.csv` with the path to your input CSV file and `output.csv` with the desired path for the output CSV file.

### Input File Format

The input CSV file should have the following columns:

- `name`: The name of the student.
- `characteristic`: A characteristic that determines the student's house.
- `birthdate`: The birth year of the student.

Example:

```csv
name,characteristic,birthdate
Hannah Abbott,patience,2005
Katie Bell,courage,2008
```

### Output File Format

The output CSV file will contain the following columns:

- `name`: The name of the student.
- `house`: The house assigned to the student.
- `grade`: The grade level of the student.

Example:

```csv
name,house,grade
Hannah Abbott,Hufflepuff,Grade 12
Katie Bell,Gryffindor,Grade 9
```

## Functions

### `main()`

This is the main function that orchestrates the entire process. It performs the following tasks:
- Validates the command-line arguments.
- Reads the input CSV file.
- Processes each row to determine the house and grade.
- Writes the processed data to the output CSV file.

### `check_correct_args()`

This function checks the command-line arguments to ensure the correct number and format. It exits the program with an appropriate message if the arguments are invalid.

### `select_house(char)`

This function determines the house for a student based on their characteristic. The mapping is as follows:
- Gryffindor: courage, loyalty, adventure
- Hufflepuff: dedication, patience, honesty
- Ravenclaw: wisdom, creativity, perfectionism
- Slytherin: ambition, competitive, leadership

If the characteristic does not match any of the predefined ones, it returns "No House".

### `select_grade(year)`

This function calculates the grade level of a student based on their birth year. The formula used is:
- `age = 2022 - birth_year`
- `grade = age - 5`

The resulting grade is returned as a string in the format "Grade X".

## Testing

Unit tests are provided in the `test_project.py` file. The tests cover the following functions:

- `check_correct_args()`
- `select_house()`
- `select_grade()`

To run the tests, use the following command:

```bash
pytest test_project.py
```

### Example Test Cases

#### `test_check_correct_args()`

This test ensures that the function correctly identifies invalid command-line arguments and raises a `SystemExit` exception.

#### `test_select_house()`

This test checks that the `select_house` function correctly assigns houses based on characteristics.

#### `test_select_grade()`

This test verifies that the `select_grade` function correctly calculates the grade level based on the birth year.

## Example

Given the following input CSV file:

```csv
name,characteristic,birthdate
Hannah Abbott,patience,2005
Katie Bell,courage,2008
```

The script will produce the following output CSV file:

```csv
name,house,grade
Hannah Abbott,Hufflepuff,Grade 12
Katie Bell,Gryffindor,Grade 9
```

## Conclusion

This project provides a simple yet effective way to process student data, categorizing them into Hogwarts houses and determining their grade levels. The modular structure of the code and the provided tests ensure reliability and ease of maintenance.
