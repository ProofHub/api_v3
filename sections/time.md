Time
====================

* [Get time](#get-time) 
* [Create time](#create-time)
* [Update time](#update-time)
* [Delete time](#delete-time)
* [Start timer](#start-timer)
* [Pause timer](#pause-timer)
* [Stop timer](#stop-timer)

Get time
----------------

* `GET v3/projects/23423233/timesheets/23570135/time` will return all time entries of specified timesheet

```json
[
    {
        "id":80870831,
        "status":"billable",
        "description":"Brainstorm session with potential users",
        "date":"2016-10-05",
        "created_at":"2016-10-05T08:19:01+00:00",
        "logged_hours":2,
        "logged_mins":30,
        "timer":false,
        "today":1475625600,
        "sort":0,
        "by_me":true,
        "project":{
            "id":23423233,
            "name":"PH Marketing"
        },
        "creator":{
            "id":12009183
        },
        "task":null,
        "timesheet":{
            "id":23570135,
            "title":"Prepare training material",
            "assigned":[

            ],
            "private":false,
            "logged_hours":null,
            "logged_mins":null,
            "archived":false,
            "estimated_hours":null,
            "estimated_mins":null
        }
    },
    {
        "id":80870832,
        "status":"none",
        "description":null,
        "date":"2016-10-05",
        "created_at":"2016-10-05T08:24:30+00:00",
        "logged_hours":1,
        "logged_mins":20,
        "timer":true,
        "today":1475625600,
        "sort":0,
        "by_me":true,
        "project":{
            "id":23423233,
            "name":"PH Marketing"
        },
        "creator":{
            "id":12009183
        },
        "task":null,
        "timesheet":{
            "id":23570135,
            "title":"Sample timesheet",
            "assigned":[

            ],
            "private":false,
            "logged_hours":10,
            "logged_mins":null,
            "archived":false,
            "estimated_hours":20,
            "estimated_mins":30
        }
    }
]
```

Create time
----------------

* `POST v3/projects/23423233/timesheets/23570135/time` will create a new time entry to the timesheet from the parameters passed. 

```json
{
    "date":"2016-10-05",
    "logged_hours":"1",
    "logged_mins":"40",
    "status":"billable",
    "description":"Brainstorm session with potential users"
}
```

`200 OK` will be returned along with the JSON of the time entry if the record is added. `403 Forbidden` will be returned in case of invalid access.

Update time
----------------

* `PUT v3/projects/23423233/timesheets/23570135/time/80870831` will update the tim entry from the parameters passed.

```json
{
    "date":"2016-10-05",
    "logged_hours":"1",
    "logged_mins":"40",
    "status":"billable",
    "description":"Brainstorm session with potential users"
}
```

`200 OK` will be returned along with the JSON of the time entry if the record is updated. `403 Forbidden` will be returned in case of invalid access.

Delete time
----------------

* `DELETE v3/projects/23423233/timesheets/23570135/time/80870831` will delete the time entry.

`204 No Content` will be returned if the record is deleted. `403 Forbidden` will be returned in case of invalid access.


Start timer
----------------

* `PUT v3/timer` will start automatic timer for the user.

```json
{
    "project_id":23423233,
    "timesheet_id":23570135,
    "timer_status":"start",
}
```

`200 OK` will be returned along with the JSON of the time entry if the record is added. `403 Forbidden` will be returned in case of invalid access.


Pause timer
----------------

* `PUT v3/timer/2357013` will pause if automatic timer is running for the user.

```json
{
    "pause_time":"05:02:21",
    "timer_status":"pause",
}
```

`200 OK` will be returned along with the JSON of the time entry if the record is updated. `403 Forbidden` will be returned in case of invalid access.

Stop timer
----------------

* `DELETE v3/timer/2357013` will delete if automatic timer is running for the user.

`204 No Content` will be returned if the record is deleted. `403 Forbidden` will be returned in case of invalid access.
