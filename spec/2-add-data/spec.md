# Feature :: Add a new data (เพิ่มเอกสารการประชุม)
- route = /add-data

## UI HTML Template
* use from file `add.html`


## User flow
1. User logs in and is redirected to dashboard page, click link "เพิ่มเอกสาร" to go to add new document page.
2. User fill in the form and click submit button
   - Validate input data, if any required field is empty, show error message and do not submit the form.
   - Show error message next to the field that has an error, and highlight the field with red border.
3. If all required fields are filled, submit the form and save the data to the database
   - default status = "Draft"
   - Save to file `data/data.json` in section "Recent Meeting Documents"

## Data model for a document
show in table format with the following columns:
| Field Name | Data Type | Required | Description |
|------------|-----------|----------|-------------|
| Meeting Name  (ชื่อการประชุม)    | string    | Yes      | The title of the document |   
| Date (วันที่) | date | Yes | The date of the meeting |
| Department name (หน่วยงาน) | ID, ui with dropdown | Yes | The department that created the document |
| Person in Charge (employee name) (ผู้รับผิดชอบ) | ID, ui with dropdown | Yes | The employee responsible for the document |
| รายละเอียดการประชุม | string | No | The details of the meeting |
| Uploaded file | file | No | The file uploaded by the user |

## Input validation rules
- Meeting Name: required, max length = 100 characters
- Date: required, must be a valid date in the format YYYY-MM-DD
- Department name: required, max length = 50 characters
- Person in Charge (employee name): required, max length = 50 characters
- รายละเอียดการประชุม: optional, max length = 500 characters
- Uploaded file: optional, must be a valid file type (pdf only)

Show error message in table format with the following columns:
| Field Name | Case name | Error Message |
|------------|-----------|---------------|
| Meeting Name | empty | "Meeting Name is required" |
| Meeting Name | too long | "Meeting Name must not exceed 100 characters" |
| Date | empty | "Date is required" |
| Date | invalid format | "Date must be in the format YYYY-MM-DD" |
| Department name | empty | "Department name is required" |
| Department name | too long | "Department name must not exceed 50 characters" |
| Person in Charge (employee name) | empty | "Person in Charge is required" |
| Person in Charge (employee name) | too long | "Person in Charge must not exceed 50 characters" |
| รายละเอียดการประชุม | too long | "รายละเอียดการประชุม must not exceed 500 characters" |
| Uploaded file | invalid type | "Uploaded file must be a PDF" |