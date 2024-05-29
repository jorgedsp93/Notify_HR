# Notify_HR
This script detects new rows added to a Google Sheet, logs the date and time in the row, and emails HR to notify them of the new employee, prompting timely onboarding actions.

This Google Apps Script automatically detects when a new row is added to a Google Sheet and performs two main actions: it stamps the current date and time in designated cells of the new row, and sends an automated email to the HR department notifying them of the new employee added to the system. The script ensures that HR is promptly informed and can initiate the necessary onboarding processes efficiently.

The Google Sheet is structured into various sections that track employee onboarding requests and confirmations, neatly divided into rows and columns for clarity and organization.

Rows
Each row represents a single employee's information and onboarding requirements.
Example: The row for "Johnny Doe" contains all relevant data about his start date, department, and the resources he requires.
Columns
The columns are grouped into categories, making it easier to understand what type of information is being recorded:

Employee Info:

Columns A and B: Contain the first and last names of the employee. Example: "Johnny Doe".
Column C: Shows the start date of the employee. Example: "2022-01-15".
Column D: Indicates the department the employee is joining. Example: "Human Resources".
Request:

Columns E to J: These columns are checklists indicating what the employee needs as part of their job. This includes whether they need items like a laptop, phone, vehicle, gas card, Home Depot card, and a security fob. Each column represents one item, marked as TRUE if needed, FALSE if not.
Confirmation:

Columns K to N: These columns are used to track if various departments have confirmed the employee's request. They include columns for admin, accounting, and IT confirmations. Each column is marked TRUE once the respective department has processed and confirmed the request.
Timestamps:

Columns O to U: These columns record specific dates and times relevant to the onboarding process, such as the date the employee was onboarded, the time they were onboarded, when the request was made, and when it was completed by admin, accounting, and IT.
This structured format ensures that all necessary details are captured and tracked efficiently, allowing for a smooth transition for new employees into their roles while ensuring that all their needs are met and verified by the relevant departments.
