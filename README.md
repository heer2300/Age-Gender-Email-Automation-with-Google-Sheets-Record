# Age & Gender Email Automation with n8n

An automated workflow built with **n8n** that collects user information through a form, evaluates the submission based on age and gender, sends a personalized email, and records the submission in Google Sheets.

---

## Features

- Form-based user input
- Conditional routing using the **Switch** node
- Automated email notifications using Gmail
- Google Sheets integration for data storage
- Dynamic email responses based on user input
- Automatic logging of the reply sent to each user

---

## Workflow

```text
Form Trigger
      │
      ▼
   Switch Node
      │
      ├── Age < 10
      │      ├── Send "Under Age" Email
      │      └── Append Row to Google Sheets
      │
      ├── Gender = Male
      │      ├── Send "I don't like boys" Email
      │      └── Append Row to Google Sheets
      │
      └── Gender = Female
             ├── Send "Heyy, how are you amor" Email
             └── Append Row to Google Sheets
```

---

## Workflow Logic

### 1. Form Submission

The workflow starts with an **n8n Form Trigger** that collects:

- Age
- Gender
- Email Address

---

### 2. Age Validation

If the user's age is **less than 10**:

- An email is sent informing the user that they are underage.
- The submission is recorded in Google Sheets.
- Reply recorded:
  ```
  Under Age
  ```

---

### 3. Male User

If the user is **Male**:

- An email is sent with the message:
  ```
  I don't like boys
  ```
- The submission is recorded in Google Sheets.
- Reply recorded:
  ```
  I don't like boys
  ```

---

### 4. Female User

If the user is **Female**:

- An email is sent with the message:
  ```
  Heyy, how are you amor
  ```
- The submission is recorded in Google Sheets.
- Reply recorded:
  ```
  Hello Girl
  ```

---

## Technologies Used

- n8n
- Gmail
- Google Sheets
- Form Trigger
- Switch Node

---

## Project Structure

```
Age-Gender-Email-Automation/
├── README.md
├── LICENSE
├── .gitignore
├── workflow/
│   └── age-gender-email-automation.json
├── screenshots/
│   ├── workflow-overview.png
│   ├── form-trigger.png
│   ├── switch-node.png
│   ├── gmail-node.png
│   ├── google-sheets.png
│   ├── form-submission.png
│   └── google-sheet-record.png
└── docs/
    ├── workflow-explanation.md
    └── setup-guide.md
```

---

## Sample Google Sheets Record

| Age | Gender | Email | Reply |
|-----:|--------|-------|----------------------|
| 8 | Male | user@example.com | Under Age |
| 21 | Male | user@example.com | I don't like boys |
| 20 | Female | user@example.com | Hello Girl |

---

## Setup

1. Clone this repository.

```bash
git clone https://github.com/yourusername/Age-Gender-Email-Automation.git
```

2. Import the workflow from the `workflow/` folder into n8n.

3. Configure your credentials:
   - Gmail OAuth2
   - Google Sheets OAuth2

4. Update the Google Sheet ID.

5. Activate the workflow.

6. Submit the form and test the automation.

---

## Screenshots

### Workflow Overview

Add an image here:

```
screenshots/workflow-overview.png
```

### Form Trigger

```
screenshots/form-trigger.png
```

### Switch Node

```
screenshots/switch-node.png
```

### Gmail Node

```
screenshots/gmail-node.png
```

### Google Sheets Output

```
screenshots/google-sheet-record.png
```

WELL WELL WELL SCREENSHOTS NAMES ARE NOT SAME COZ I'M BORED< YK WHAT I MEAN HEHEHEHEH 

---

## Learning Outcomes

- Building automated workflows with n8n
- Using conditional logic with the Switch node
- Sending dynamic emails with Gmail
- Recording workflow data in Google Sheets
- Integrating multiple services into a single automation pipeline

---

## License

This project is licensed under the MIT License.
