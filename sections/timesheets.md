Timesheets
====================

* [Get timesheets](#get-timesheets)
* [Get timesheet](#get-timesheet)
* [Create timesheet](#create-timesheet)
* [Update timesheet](#update-timesheet)
* [Delete timesheet](#delete-timesheet)

Get timesheets
----------------

* `GET v3/projects/23423233/timesheets` will return timesheets for this project.

```json
[
    {
    "id": 23570135,
    "title": "Prepare training material",
    "estimated_hours": 100,
    "estimated_mins": null,
    "logged_hours": 10,
    "logged_mins": 30,
    "billable_hours": null,
    "billable_mins": null,
    "billed_hours": null,
    "billed_mins": null,
     "creator": {
      "id": 65707070
    },
    "project": {
      "id": 23423233
    },
    "assigned": [
      12009183,
      11679192
    ],
    "private": true,
    "archived": false,
    "created_at": "2016-09-30T05:12:09+00:00",
    "updated_at": "2016-09-30T05:26:41+00:00",
     "by_me": true
    },
    
    {
    "title":"Sample timesheet",
    "estimated_hours": 100,
    "estimated_mins": null,
    "logged_hours": 10,
    "logged_mins": 30,
    "billable_hours": 5,
    "billable_mins": 5,
    "billed_hours": null,
    "billed_mins": null,
    "creator":{
      "id": 12009183
      },
    "project": {
      "id": 23423233
    },
    "assigned":[
    ],
    "private": false,
    "archived": false,
    "created_at": "2016-09-30T05:11:36+00:00",
    "updated_at": "2016-09-30T05:41:11+00:00",
    "by_me": true
    }
  ]
```

Get timesheet
----------------

* `GET v3/projects/23423233/timesheets/23570135` will return the specified timesheet along with the time entries made in it.

```json
[
 {
    "id": 23570135,
    "title": "Prepare training material",
    "estimated_hours": 100,
    "estimated_mins": null,
    "logged_hours": 10,
    "logged_mins": 30,
    "billable_hours": null,
    "billable_mins": null,
    "billed_hours": null,
    "billed_mins": null,
     "creator": {
      "id": 12009183
    },
    "project": {
      "id": 23423233
    },
    "assigned": [
      12009183,
      11679192
    ],
    "private": true,
    "archived": false,
    "created_at": "2016-09-30T05:12:09+00:00",
    "updated_at": "2016-09-30T05:26:41+00:00",
     "by_me": true
    }
]    
```
Create timesheet
----------------

* `POST v3/projects/23423233/timesheets` will create a new timesheet from the parameters passed. 

```json
{
    "title":"Training intern",
    "estimated_hours":"50",
    "estimated_mins":"30",
    "private":true,
    "assigned":[
    12009183,
    11679192
  ]
}
```

`201 Created` will be returned along with the JSON of the timesheet ([Get timesheet](#get-timesheet)) if the record is added. `403 Forbidden` will be returned in case of invalid access.

Update timesheet
----------------

* `PUT v3/projects/23423233/timesheets/23570135` will update the timesheet from the parameters passed.

```json
{
	"title":"Training the interns",
    "estimated_hours": "20",
    "estimated_mins": "30"
}
```

`200 OK` will be returned along with the JSON of the timesheet ([Get timesheet](#get-timesheet)) if the record is updated. `403 Forbidden` will be returned in case of invalid access.

Delete timesheet
----------------

* `DELETE v3/projects/23423233/timesheets/23570135` will delete the timesheet.

`204 No Content` will be returned if the record is deleted. `403 Forbidden` will be returned in case of invalid access.
