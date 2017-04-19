Todolists
====================

* [Get all todolists](#get-all-todolists)
* [Get todolist](#get-todolist)
* [Create todolist](#create-todolist)
* [Update todolist](#update-todolist)
* [Delete todolist](#delete-todolist)

Get all todolists
----------------

* `GET v3/projects/23423233/todolists` will return todolists for this project.

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
        "show_in_kanban":true,
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
        "show_in_kanban":true,
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

Get todolist
----------------

* `GET v3/projects/23423233/todolists/13964085` will return the specified todolist.

```json
{
    "id":13964085,
    "title":"Training material on technology and its use in IT sector",
    "private":false,
    "archived":false,
    "completed_count":0,
    "remaining_count":8,
    "time_tracking":false,
    "show_in_gantt":false,
    "show_in_kanban":true,
    "updated_at":"2016-11-08T10:30:05+00:00",
    "created_at":"2016-11-08T07:49:15+00:00",
    "assigned":[
        12009183
    ],
    "associate_milestone":false,
    "by_me":true,
    "reply_email":"td+107184987-13150719-13964085196@mail.proofhub.com",
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
}
```

Create todolist
----------------

* `POST v3/projects/23423233/todolists` will create a new todolist from the parameters passed. 
* The assigned array is an optional list of people IDs that you can get from the [people API](https://github.com/ProofHub/api_v3/blob/master/sections/people.md). 

```json
{
    "title":"Proposal for campaign",
    "private":false,
    "time_tracking":false,
    "show_in_gantt":true,
    "show_in_kanban":true,
    "assigned":[
        12009183
    ]
}
```

`201 Created` will be returned along with the JSON of the todolist ([Get todolist](#get-todolist)) if the record is added. `403 Forbidden` will be returned in case of invalid access.

Update todolist
----------------

* `PUT v3/projects/23423233/todolists/13964085` will update the todolist from the parameters passed.

```json
{
	"title":"Proposal for campaign",
	"private":true
}
```

`200 OK` will be returned along with the JSON of the todolist ([Get todolist](#get-todolist)) if the record is updated. `403 Forbidden` will be returned in case of invalid access.

Delete todolist
----------------

* `DELETE v3/projects/23423233/todolists/13964085` will delete the todolist.

`204 No Content` will be returned if the record is deleted. `403 Forbidden` will be returned in case of invalid access.
