Everything
===========

* [Get all tasks](#get-all-tasks)

Get all tasks
----------------

* `GET v3/alltodo?start=0&limit=100` will return all tasks for the account as per the starting position and limit sent in the request.

```json
[
    {
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
    },
    {
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

```

**Optional Parameters**

`projects=<comma separated project id(s)>`  to get tasks for specified projects only.

`labels=<comma separated label id(s)>` or send `labelsl=none` to get only unlabelled tasks.

`include_subtasks=<true/false>` Subtasks are included if this parameter is not sent in the request. Set this to false to remove subtasks in the response.

`assigned=<comma separated user id(s)>` Set this parameter to get tasks assigned to specific users. Set it as `assigned=all_assigned` to get only those tasks which are assigned to any users. All assigned & unassigned tasks are returned if this parameter is not included in the request.

`include_unassigned=true` Set this parameter if unassigned tasks are required in the response. Set as `include_unassigned=false` if unassigned tasks are not required in the response.  Unassigned tasks are included if this parameter is not sent in the request.

`completed=<true/false>` Set this parameter to true to get a list of all completed tasks as well as open tasks. Only open tasks are sent if this parameter is not sent in the request. 

`start=0` This parameter can be used in subsequent requests to offset the result and get the next set of data. Records starting from position 0 will be returned if this parameter is not sent in the request.

`limit=100` If this parameter is not sent in the request, 100 records are returned. Any value lower than 100 can be sent. If this parameter is set to more than 100, it is ignored and 100 records are returned.

**Example with all optional parameters**

`GET v3/alltodo?projects=23423233,23423234&labels=12254912,12254913&include_subtasks=true&asssigned=12009813,11679192&include_unassigned=true&completed=false&start=0&limit=100`

