Everything
===========

* [Get all tasks](#get-all-tasks)
* [Get all time](#get-all-time)

Get all tasks
----------------

* `GET v3/alltodo?start=0&limit=100` will return all tasks for the account as per the starting position and limit sent in the request.

```json
{
    "total_count": 416,
    "todos": [
        {
		   "ticket": "1532",

			"id":13964085,

			"title":"Training material on technology and its use in IT sector",

			"private":false,

			"archived":false,

			"completed_count":0,

			"remaining_count":8,

			"time_tracking":false,

			"show_in_gantt":false,

			"updated_at":"2016-11-08T10:30:05+00:00",

			"created_at":"2016-11-08T07:49:15+00:00",

			"assigned":[

				12009183
			],
			"associate_milestone":false,
			"by_me":true,
			"reply_email":"td+3984374-13150719-252049372@mail.proofhub.com",
			"project":{

				"id":23423233
			},
			"timesheet":{
				"id":null
			},
			"milestone":{
				"id":null
			},
			"creator":{
				"id":12009183
			}
			"custom_fields": [
				{
					"id": 2585222499,
					"title": "Reviewed By",
					"description": "",
					"type": "Text",
					"value": "Alison"
				}
				{
					"id": 953429949,
					"title": "Review Date",
					"description": "",
					"type": "Date",
					"value": "2022-05-07"
				}
			]
		},
		{
			"ticket": "1533",
			"id":13965645,
			"title":"Training material on marketing",
			"private":false,
			"archived":false,
			"completed_count":2,
			"remaining_count":0,
			"time_tracking":true,
			"show_in_gantt":true,
			"updated_at":"2016-11-10T10:02:00+00:00",
			"created_at":"2016-11-10T06:41:04+00:00",
			"assigned":[
			],
			"associate_milestone":true,
			"by_me":true,
			"reply_email":"td+3984374-13150719-253479335@mail.proofhub.com",
			"project":{
				"id":23423233
			},
			"timesheet":{
				"id":23570135
			},
			"milestone":{
				"id":63034033
			},
			"creator":{
				"id":12009183
			}
		}
	]
}

```

**Optional Parameters**

`projects=<comma separated project id(s)>`  to get tasks for specified projects only.

`labels=<comma separated label id(s)>` or send `labelsl=none` to get only unlabelled tasks.

`include_subtasks=<true/false>` Set this to false to remove subtasks in the response. Subtasks are included if this parameter is not sent in the request. 

`assigned=<comma separated user id(s)>` Set this parameter to get tasks assigned to specific users. Set it as `assigned=all_assigned` to get only those tasks which are assigned to any users. All assigned & unassigned tasks are returned if this parameter is not included in the request.

`include_unassigned=true` Set this parameter if unassigned tasks are required in the response. Set as `include_unassigned=false` if unassigned tasks are not required in the response.  Unassigned tasks are included if this parameter is not sent in the request.

`completed=<true/false>` Set this parameter to true to get a list of all completed tasks as well as open tasks. Only open tasks are sent if this parameter is not sent in the request. 

`start=0` This parameter can be used in subsequent requests to offset the result and get the next set of data. Records starting from position 0 will be returned if this parameter is not sent in the request. If the value is set greater than the number of records available in the result, an empty response will be sent.

`limit=100` If this parameter is not sent in the request, 100 records are returned. Any value lower than 100 can be sent. If this parameter is set to more than 100, it is ignored and 100 records are returned.

**Example with all optional parameters**

`GET v3/alltodo?projects=23423233,23423234&labels=12254912,12254913&include_subtasks=true&asssigned=12009813,11679192&include_unassigned=true&completed=false&start=0&limit=100`

Get all time
----------------

* `GET v3/alltime?start=0&limit=100` will return all time entries for the account as per the starting position and limit sent in the request.

```json
{
[
    {
        "by_me": true,
        "id": 123456789
        "status": "none",
        "description": null,
        "date": "2020-06-02",
        "created_at": "2020-06-02T11:23:34+00:00",
        "logged_hours": 12,
        "logged_mins": null,
        "timer": false,
        "sort": 0,
        "timesheet": {
            "id": 51654376543,
            "title": "timesheet for client billing",
            "assigned": [],
            "private": false,
            "logged_hours": 62,
            "logged_mins": null,
            "archived": false,
            "estimated_hours": null,
            "estimated_mins": null,
            "timesheet_logged_hours": null,
            "timesheet_logged_mins": null,
            "creator": 15654365
        },
        "task": null,
        "project": 36765436543,
        "project_name": "Customer Acme",
        "creator": 1565432654
    },
    {
        "by_me": true,
        "id": 12987658765,
        "status": "billed",
        "description": "time entry for work done",
        "date": "2021-02-24",
        "created_at": "2021-02-24T07:14:38+00:00",
        "logged_hours": 50,
        "logged_mins": null,
        "timer": false,
        "sort": 0,
        "timesheet": {
            "id": 518768765,
            "title": "timesheet for client billing",
            "assigned": [],
            "private": false,
            "logged_hours": 62,
            "logged_mins": null,
            "archived": false,
            "estimated_hours": null,
            "estimated_mins": null,
            "timesheet_logged_hours": null,
            "timesheet_logged_mins": null,
            "creator": 15876547654
        },
        "task": {
            "list_id": 127657654,
            "list_name": "Acme website worklist",
            "task_id": 12765476543,
            "task_name": "website wireframe design",
            "subtask_id": null,
            "subtask_name": null,
            "stage": 3576547654,
            "ticket": "81654"
        },
        "project": 3676547654,
        "project_name": "Customer Acme",
        "creator": 157654765
    }
]
}

```

**Optional Parameters**

`group_by=date`  to get time entries grouped by date. Other values for this parameter can be `person_name`, `project` or `timesheet`.

`order_by=asc`  to get time entries in ascending order. Other value for this parameter can be `desc`.

`user_id=1598765476`  to get time entries only for a specific user.

`status=billable`  to get time entries of any status. Other values for this parameter can be `billed`, `non-billable`, `void` or `none`.

`from_date=2019-08-01`  to get time entries after specific date. Specified date is included. Supported format is `YYYY-MM-DD`.

`to_date=2019-08-14`  to get time entries before specific date. Specified date is included. Supported format is `YYYY-MM-DD`.

`project_id=36676546`  to get time entries for specific project. Multiple projects can be included by sending comma separated project ids.

