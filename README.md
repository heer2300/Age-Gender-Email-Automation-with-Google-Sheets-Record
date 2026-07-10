Age & Gender Email Automation with Google Sheets Record
Overview

This n8n workflow collects user information through an n8n form, evaluates the submitted data using a Switch node, sends an automated email based on the conditions, and stores both the submission details and the email reply in Google Sheets.

Features
Collects user information using an n8n Form.
Validates the user's age.
Checks the user's gender.
Sends personalized emails automatically.
Records every submission in Google Sheets.
Saves the exact email reply sent to the user.
Workflow
1. Form Submission

The user submits:

Age
Gender
Email Address
2. Switch Node

The workflow processes the submission using the following conditions:

Condition 1: Age < 10
Sends an email informing the user that they are underage.
Records the submission in Google Sheets.
Reply saved in the sheet:
Under Age
Condition 2: Gender = Male
Sends an email with the message:
I don't like boys
Records the submission in Google Sheets.
Reply saved in the sheet:
I don't like boys
Condition 3: Gender = Female
Sends an email with the message:
Heyy, how are you amor
Records the submission in Google Sheets.
Reply saved in the sheet:
Hello Girl



Workflow Structure
Form Trigger
      │
      ▼
   Switch Node
      │
      ├── Age < 10
      │      ├── Send Email
      │      └── Google Sheets (Reply: Under Age)
      │
      ├── Male
      │      ├── Send Email
      │      └── Google Sheets (Reply: I don't like boys)
      │
      └── Female
             ├── Send Email
             └── Google Sheets (Reply: Hello Girl)


             
Technologies Used
n8n
n8n Form Trigger
Switch Node
Gmail
Google Sheets
Google Sheets Record


Age	  Gender	Email	            Reply
8     Male	  user@example.com	Under Age
21	  Male	  user@example.com	I don't like boys
20	  Female	user@example.com	Hello Girl



Outcome

The workflow automatically evaluates each form submission, sends the appropriate email, and logs the user's information along with the exact reply sent. This creates a complete audit trail of every interaction in Google Sheets.
