Todolists
====================

* [Get all todolists](#get-all-todolists)
* [Get todolist](#get-todolist)
* [Create todolist](#create-todolist)
* [Update todolist](#update-todolist)
* [Delete todolist](#delete-todolist)
* [Copy todolist](#copy-todolist)
* [Move todolist](#move-todolist)

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

Get todolist
----------------

* `GET v3/projects/23423233/todolists/13964085` will return the specified todolist.
* This API also returns any custom fields created on this todolist.

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
        "id":866559183
    },
    "workflow":{
           "id": 8767866337,
           "name": "Flow of work"
       },
       "custom_fields": [
           {
               "id": 76672841,
               "title": "Tags",
               "description": "Select more than one option from the following:",
               "options": [
                   {
                       "id": 8569745,
                       "color": "#F95569",
                       "order": 1,
                       "title": "#work"
                   },
                   {
                       "id": 84759883,
                       "color": "#8F7EE6",
                       "order": 4,
                       "title": "#experience"
                   },
                   {
                       "id": 94859020,
                       "color": "#FFFFFF",
                       "order": 5,
                       "title": "#instaposts"
                   },
                   {
                       "id": 94759589,
                       "color": "#FFFFFF",
                       "order": 3,
                       "title": "#reelit"
                   },
                   {
                       "id": 84598158,
                       "color": "#6CDE43",
                       "order": 6,
                       "title": "#feelit"
                   }
                ],
               "type": "Tags",
               "todolist_id": 947599134746,
               "extra_info": null
           },
           {
               "id": 847596409,
               "title": "% Mark",
               "description": "Add the approx. % of tasks done in a day",
               "options": [],
               "type": "Percentage",
               "todolist_id": 84748134746,
               "extra_info": null
           },
           {
               "id": 947499978,
               "title": "Money",
               "description": "",
               "options": [],
               "type": "Currency",
               "todolist_id": 94747134746,
               "extra_info": {
                   "currency": "custom",
                   "customValue": "USD"
               }
           },
           {
               "id": 948440684,
               "title": "Drop Down Selection",
               "description": "Select only one option from the list",
               "options": [
                   {
                       "id": 947486745,
                       "color": "#FFD501",
                       "order": 1,
                       "title": "option 2"
                   },
                   {
                       "id": 94746020,
                       "color": "#30BFBF",
                       "order": 5,
                       "title": "option 4"
                   }
                ],
               "type": "Dropdown",
               "todolist_id": 83748134746,
               "extra_info": null
           },
           {
               "id": 749474253,
               "title": "Single line value",
               "description": "",
               "options": [],
               "type": "Text",
               "todolist_id": 84649434746,
               "extra_info": null
           },
           {
               "id": 9373846822,
               "title": "Large Content",
               "description": "Add paragraph to the field",
               "options": [],
               "type": "Textarea",
               "todolist_id": 693630134746,
               "extra_info": null
           },
           {
               "id": 538464390,
               "title": "Numeric field",
               "description": "Add any numeric value in this field,",
               "options": [],
               "type": "Numbers",
               "todolist_id": 593624134746,
               "extra_info": null
           },
           {
               "id": 93794097,
               "title": "Submission date",
               "description": "add the dates",
               "options": [],
               "type": "Date",
               "todolist_id": 9254943134746,
               "extra_info": null
           }
       ]
}
```

Create todolist
----------------

* `POST v3/projects/23423233/todolists` will create a new todolist from the parameters passed. 
* The assigned array is an optional list of people IDs that you can get from the [people API](https://github.com/ProofHub/api_v3/blob/master/sections/people.md). 
* Custom fields cannot be created via API

```json
{
    "title":"Proposal for campaign",
    "private":false,
    "time_tracking":false,
    "show_in_gantt":true,
    "assigned":[
        12009183
    ]
}
```

`201 Created` will be returned along with the JSON of the todolist ([Get todolist](#get-todolist)) if the record is added. `403 Forbidden` will be returned in case of invalid access.

Update todolist
----------------

* `PUT v3/projects/23423233/todolists/13964085` will update the todolist from the parameters passed.
* Custom fields cannot be updated via API

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

Copy todolist
----------------

* `POST v3/projects/23423233/todolists` will create a duplicate copy of selected todolist from the parameters passed. A todolist can be copied into same project and different project as well. 

```json
{
    "title":"Copy of second",
    "project":145454545,
    "copy_stages":true,
    "copy_assignees":true,
    "copy_dates":true,
    "copy_comments":true,
    "copy_list":13964085
}
```

`201 Created` will be returned along with the JSON of the todolist ([Get todolist](#get-todolist)) if the record is added. `403 Forbidden` will be returned in case of invalid access.

Move todolist
----------------

* `PUT v3/projects/23423233/todolists/13964085` will move selected todolist from the parameters passed. A todolist can be moved into different project. 

```json
{
    "title":"Copy of second",
    "project":145454545,
    "move_stages":true,
    "move_people":true,
    "move_dates":true,
    "proof_comment":true,
    "id":13964085,
    "move_list":true
}
```

`200 OK` will be returned if the record is moved. `403 Forbidden` will be returned in case of invalid access.
