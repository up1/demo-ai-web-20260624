# Feature :: Dashboard
- route = /dashboard

## UI HTML Template
* use from file `dashboard.html`



## User flow
1. User logs in and is redirected to the dashboard page.
2. User can view data in dashboard widgets that read from JSON data
   - Total Documents in this month
   - Number of Documents by Department
   - List of Recent Meeting Documents
3. Filter by department name and status for the list of recent meeting documents.
4. Show with pagination for the list of recent meeting documents
   - page size = 10

## Data model for Total Documents in this month and Number of Documents by Department
JSON Format
```
{
    "Total Documents in this month": 0,
    "Number of Documents by Department": {
        "Department Name 1": 0,
        "Department Name 2": 0,
        "Department Name 3": 0
    }
}
```

## Data model for List of Recent Meeting Documents
JSON Format
- Meeting Name	
- Date	
- Department name	
- Person in Charge (employee name)
- Status
```
[
    {
        "Meeting Name": "",
        "Date": "23 Oct 2023",
        "Department name": "",
        "Person in Charge (employee name)": "",
        "Status": "Complete|Draft|Reviewing"
    },
    {
        "Meeting Name": "",
        "Date": "23 Oct 2023",
        "Department name": "",
        "Person in Charge (employee name)": "",
        "Status": "Complete|Draft|Reviewing"
    }
]
```

## Provide data for tesing
- Total Documents in this month = 10
- Number of Documents by Department
```
{
    "Department Name 1": 5,
    "Department Name 2": 3,
    "Department Name 3": 2
}
```
List of Recent Meeting Documents
```
[
    {
        "Meeting Name": "Meeting 1",
        "Date": "23 Oct 2023",
        "Department name": "Department Name 1",
        "Person in Charge (employee name)": "Employee 1",
        "Status": "Complete"
    },
    {
        "Meeting Name": "Meeting 2",
        "Date": "22 Oct 2023",
        "Department name": "Department Name 2",
        "Person in Charge (employee name)": "Employee 2",
        "Status": "Draft"
    },
    {
        "Meeting Name": "Meeting 3",
        "Date": "21 Oct 2023",
        "Department name": "Department Name 3",
        "Person in Charge (employee name)": "Employee 3",
        "Status": "Reviewing"
    }
]
``` 

