Jupyter Notebook consists of all the data processing.

## Run Instructions
- Clone the git repository onto your system. (I usually do it from git cmd, you can look it up on your desktop search menu)
- Use 'git clone https://github.com/divija-annedi/Data-Engineering-Assessment.git'
- Type in 'pwd', this will show you your current directory that the cloned folder is in.
- Since it's an ipynb, open jupyter notebook on your desktop and go to the directory that the cloned folder is located in.
- Run all cells in the ipynb. It should not show up an error as the input files are also in the same directory.

## Input
Input is taken from the three sheets from "Copy of Data Import Assignment.xlsx"

## Output
The project produces two output CSV files:
Output CueBox Constituents.csv
Output CueBox Tags.csv

## Assumptions & Reasoning
1.	“Person” or “Company”
Assuming it is a Person by default, and is a Company if the first name, last name are not present and Company’s name is present.
It is a Person if first name and last name are absent along with Company's name.
Reasoning: Minimizing the risk of classifying a patron as company when the person's details are present in the data. I chose to consider it as a individual donation than by a company.

2. Total unique patrons vs final patrons in the output
Across the three input sheets together, there are 102 unique patron ids in total.
But for the final output only 99 patrons are considered (patrons that are present in input constituents).
Assuming 3 patrons don’t have their constituent profile setup, there is no point considering them as the rest of the data for them is going to be empty.

3.	Primary email in Constituents page is assumed as Email 1 and anything else from Emails sheet is assumed as Email 2, If email1 already exists.
  
4. 	Mr. and Mrs. salutations are also considered as “ ”, since only 4 valid titles are mentioned in the instructions.

## Questions for Client Success Manager
1. Should I have considered having the 3 patrons that i mentioned in Assumption no.2 into the dataset? These would be patrons with only a email/donation with no profile. (1 of them has only an email, the other 2 have only donations). Would the client still care about it if it's just Patron ID:Email/Donation without any other information?

## QA Processes

- Compared row counts after merging the 3 different datasets.
- Manually inspected a couple of records to confirm proper linkage.
- Verified column names and formatting against the instructions.
- Restarted the kernel and ran all cells to check reproducibility.
- Validated if all the final patron ids produced are unique.

## AI Usage
Used AI to check for clarity on pandas syntax. Discovered the use of 'assert' keyword for validating unique ids.
All the core work, including logic, implementation, decision-making, assumptions were done by me. I am completely able to explain, modify and defend my outputs produced.
