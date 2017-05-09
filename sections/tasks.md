Tasks
====================

* [Get all tasks](#get-all-tasks)
* [Get task](#get-task)
* [Create task](#create-task)
* [Update task](#update-task)
* [Delete task](#delete-task)
* [Get all subtasks](#get-all-subtasks)
* [Get subtask](#get-subtask)
* [Create subtask](#create-subtask)
* [Update subtask](#update-subtask)
* [Delete subtask](#delete-subtask)
* [Get all comments](#get-all-comments)
* [Get comment](#get-comment)
* [Create comment](#create-comment)
* [Update comment](#update-comment)
* [Delete comment](#delete-comment)
* [Get task history](#get-task-history)
* [Get task history detail](#get-task-history-details)
* [Get all labels](#get-all-labels)
* [Get label](#get-label)
* [Create label](#create-label)
* [Update label](#update-label)
* [Delete label](#delete-label)

Get all tasks
----------------

* `GET v3/projects/23423233/todolists/13964085/tasks` will return task for this todolist.

```json
[
    {
        "id":13966758,
        "title":"Update the template document for the training material.",
        "description":null,
        "start_date":"2016-11-10",
        "due_date":"2016-11-10",
        "estimated_hours":10,
        "estimated_mins":null,
        "logged_hours":null,
        "logged_mins":null,
        "updated_at":"2016-11-10T11:41:44+00:00",
        "created_at":"2016-11-10T11:41:44+00:00",
        "completed":false,
        "assigned":[
            12009183,
            11679192
        ],
        "labels":[
            12254912
        ],
        "sub_tasks":0,
        "task_history":null,
        "percent_progress":0,
        "attachments":[

        ],
        "comments":0,
        "by_me":true,
        "template":false,
        "project":{
            "id":23423233,
            "name":"ProofHub marketing"
        },
        "creator":{
            "id":12009183
        },
        "list":{
            "id":13964085,
            "name":"Training material on marketing"
        }
    },
    {
        "id":13966759,
        "title":"Get the completed document reviewed and approved by each and every person responsible.",
        "description":"Get the completed document reviewed and approved in detail.",
        "start_date":null,
        "due_date":null,
        "estimated_hours":20,
        "estimated_mins":30,
        "logged_hours":20,
        "logged_mins":30,
        "updated_at":"2016-11-10T11:42:58+00:00",
        "created_at":"2016-11-10T11:42:58+00:00",
        "completed":true,
        "assigned":[

        ],
        "labels":[

        ],
        "sub_tasks":1,
        "task_history":"Marked as <i>complete</i>  on 10 Nov, 2016 11:52 PM by  Chris Wagleys<br>",
        "percent_progress":100,
        "completed_at":"2016-11-10T11:52:39+00:00",
        "completed_by":12009183,
        "attachments":[

        ],
        "comments":2,
        "by_me":true,
        "template":false,
        "project":{
            "id":23423233,
            "name":"ProofHub marketing"
        },
        "creator":{
            "id":12009183
        },
        "list":{
            "id":13964085,
            "name":"Training material on marketing"
        }
    }
]

```

Get task
----------------

* `GET v3/projects/23423233/todolists/13964085/tasks/13966758` will return the specified task.

```json
{
    "id":13966758,
    "title":"Get the completed document reviewed and approved by each and every person responsible.",
    "description":"Get the completed document reviewed and approved in detail.",
    "start_date":null,
    "due_date":null,
    "estimated_hours":20,
    "estimated_mins":30,
    "logged_hours":20,
    "logged_mins":30,
    "updated_at":"2016-11-10T11:42:58+00:00",
    "created_at":"2016-11-10T11:42:58+00:00",
    "completed":true,
    "assigned":[

    ],
    "labels":[

    ],
    "sub_tasks":1,
    "task_history":"Marked as <i>complete</i>  on 10 Nov, 2016 11:52 PM by  Chris<br>",
    "percent_progress":100,
    "completed_at":"2016-11-10T11:52:39+00:00",
    "completed_by":12009183,
    "attachments":[

    ],
    "comments":2,
    "by_me":true,
    "template":false,
    "project":{
        "id":23423233,
        "name":"ProofHub marketing"
    },
    "creator":{
        "id":12009183
    },
    "list":{
        "id":13964085,
        "name":"Training material on marketing"
    }
}
```
Create task
----------------

* `POST v3/projects/23423233/todolists/13964085/tasks` will create a new task from the parameters passed. 
* The assigned array is an optional list of people IDs that you can get from the [people API](https://github.com/ProofHub/api_v3/blob/master/sections/people.md). 

```json
{
    "title": "Get it signed",
    "description": "Need to get it signed off immediately",
    "start_date": "2016-11-10",
    "due_date": "2016-11-10",
    "estimated_hours": 5,
    "estimated_mins": 30,
    "assigned": [
        12009183
    ],
    "labels": [
        12254912
    ]
}
```

`201 Created` will be returned along with the JSON of the task ([Get task](#get-task)) if the record is added. `403 Forbidden` will be returned in case of invalid access.

**Attaching files**

Attaching files to a task requires both the token and the name of the attachment. The token is obtained from the [Create attachments](
https://github.com/ProofHub/api_v3/blob/master/sections/attachemnts.md#create-attachment) endpoint, which you must hit first before creating an upload. The name parameter must be a valid filename with an extension. Multiple attachments are allowed. Set folder to `0` if you don't want to upload file in any folder.

```json
{
	"title":"Get it signed",
    "description":"Need to get it signed off immediately",
	"start_date":"2013-12-31",
	"due_date":"2013-12-31",
	"estimated_hrs":"2",
	"attachments":[
		{
			"token":"eUhSL2psVCtWaXU1aG0rOXNCMk1Vdz09",
			"name":"document.doc",
			"folder":0
		}
	],
	"assigned":[12009183, 5895623],
	"labels":[12254912, 12254913]
}
```

Update task
----------------

* `PUT v3/projects/23423233/todolists/13964085/tasks/13966758` will update the task from the parameters passed.

```json
{
	"description":"Get it signed off",
	"start_date":"2013-12-31",
	"due_date":"2013-12-31"
}
```

Complete task
----------------

* `PUT v3/projects/23423233/todolists/13964085/tasks/13966758` with the following JSON to complete a task. You can pass `false` to mark the task as incomplete.

```json
{
	"completed":true
}
```

`200 OK` will be returned along with the JSON of the task ([Get task](#get-task)) if the record is updated. `403 Forbidden` will be returned in case of invalid access.

Delete task
----------------

* `DELETE v3/projects/23423233/todolists/13964085/tasks/13966758` will delete the task.

`204 No Content` will be returned if the record is deleted. `403 Forbidden` will be returned in case of invalid access.


Get all subtasks
----------------

* `GET v3/projects/23423233/todolists/13964085/tasks` will return subtasks for this task.

```json
[
    {
        "id": 13966722,
        "title": "Create a new document for client",
        "description": null,
        "start_date": "2016-11-15",
        "due_date": "2016-11-20",
        "estimated_hours": 10,
        "estimated_mins": 30,
        "logged_hours": null,
        "logged_mins": null,
        "updated_at": "2016-11-10T11:41:44+00:00",
        "created_at": "2016-11-10T11:41:44+00:00",
        "completed": false,
        "assigned": [
            12009183,
            11679192
        ],
        "labels": [
            12254912
        ],
        "task_history": null,
        "percent_progress": 0,
        "attachments": [
        ],
        "comments": 0,
        "by_me": true,
        "template": false,
        "project": {
            "id": 23423233,
            "name": "ProofHub marketing"
        },
        "creator": {
            "id": 12009183
        },
        "list": {
            "id": 13964085,
            "name": "Training material on marketing"
        }
    },
    {
        "id": 13966759,
        "title": "Send the created document to all the people responsible.",
        "description": null",
        "start_date": null,
        "due_date": null,
        "estimated_hours": 20,
        "estimated_mins": 30,
        "logged_hours": 20,
        "logged_mins": 30,
        "updated_at": "2016-11-10T11:42:58+00:00",
        "created_at": "2016-11-10T11:42:58+00:00",
        "completed": true,
        "assigned": [
        ],
        "labels": [
        ],
        "task_history": "Marked as <i>complete</i>  on 10 Nov, 2016 11:52 PM by  Chris Wagleys<br>",
        "percent_progress": 100,
        "completed_at": "2016-11-10T11:52:39+00:00",
        "completed_by": 12009183,
        "attachments": [
        ],
        "comments": 2,
        "by_me": true,
        "template": false,
        "project": {
            "id": 23423233,
            "name": "ProofHub marketing"
        },
        "creator": {
            "id": 12009183
        },
        "list": {
            "id": 13964085,
            "name": "Training material on marketing"
        }
    }
]

```

Get subtask
----------------

* `GET v3/projects/23423233/todolists/13964085/tasks/13966758/subtasks/13966722` will return the specified subtask.

```json
 {
    "id": 13966722,
    "title": "Create a new document for client",
    "description": null,
    "start_date": "2016-11-15",
    "due_date": "2016-11-20",
    "estimated_hours": 10,
    "estimated_mins": 30,
    "logged_hours": null,
    "logged_mins": null,
    "updated_at": "2016-11-10T11:41:44+00:00",
    "created_at": "2016-11-10T11:41:44+00:00",
    "completed": false,
    "assigned": [
        12009183,
        11679192
    ],
    "labels": [
        12254912
    ],
    "task_history": null,
    "percent_progress": 0,
    "attachments": [
    ],
    "comments": 0,
    "by_me": true,
    "template": false,
    "project": {
        "id": 23423233,
        "name": "ProofHub marketing"
    },
    "creator": {
        "id": 12009183
    },
    "list": {
        "id": 13964085,
        "name": "Training material on marketing"
    }
}

```
Create subtask
----------------

* `POST v3/projects/23423233/todolists/13964085/tasks/13966758/subtasks` will create a new subtask from the parameters passed. 
* The assigned array is an optional list of people IDs that you can get from the [people API](https://github.com/sdplabs/proofhub-api/blob/master/sections/people.md). 

```json
{
    "title": "Get the document ready",
    "description": "Document should be ready for the client approval",
    "start_date": "2016-11-10",
    "due_date": "2016-11-10",
    "estimated_hours": 5,
    "estimated_mins": 30,
    "assigned": [
        12009183
    ],
    "labels": [
        12254912
    ]
}
```

`201 Created` will be returned along with the JSON of the subtask ([Get subtask](#get-subtask)) if the record is added. `403 Forbidden` will be returned in case of invalid access.

**Attaching files**

Attaching files to a task requires both the token and the name of the attachment. The token is obtained from the [Create attachments](
https://github.com/sdplabs/proofhub-api/blob/master/sections/attachemnts.md#create-attachment) endpoint, which you must hit first before creating an upload. The name parameter must be a valid filename with an extension. Multiple attachments are allowed. Set folder to `0` if you don't want to upload file in any folder.

```json
{
    "title":"Get it signed",
    "description":"Need to get it signed off immediately",
    "start_date":"2013-12-31",
    "due_date":"2013-12-31",
    "estimated_hrs":"2",
    "attachments":[
        {
            "token":"eUhSL2psVCtWaXU1aG0rOXNCMk1Vdz09",
            "name":"document.doc",
            "folder":0
        }
    ],
    "assigned":[12009183, 5895623],
    "labels":[12254912, 12254913]
}
```

Update subtask
----------------

* `PUT v3/projects/23423233/todolists/13964085/tasks/13966758/subtasks/13966722` will update the subtask from the parameters passed.

```json
{
    "description":"Get it signed off",
    "start_date":"2013-12-31",
    "due_date":"2013-12-31"
}
```

Complete subtask
----------------

* `PUT v3/projects/23423233/todolists/13964085/tasks/13966758/subtasks/13966722` with the following JSON to complete a subtask. You can pass `false` to mark the task as incomplete.

```json
{
    "completed":true
}
```

`200 OK` will be returned along with the JSON of the subtask ([Get subtask](#get-subtask)) if the record is updated. `403 Forbidden` will be returned in case of invalid access.

Delete subtask
----------------

* `DELETE v3/projects/23423233/todolists/13964085/tasks/13966758/subtasks/13966722` will delete the subtask.

`204 No Content` will be returned if the record is deleted. `403 Forbidden` will be returned in case of invalid access.



Get all task comments
----------------

* `GET v3/projects/23423233/todolists/13964085/tasks/13966758/comments` will return all the comments of specified task.

```json
[
    {
        "id":30438075,
        "description":"Meeting with the client",
        "created_at":"2016-11-11T08:11:10+00:00",
        "by_me":true,
        "comments_count":2,
        "list":{
            "id":13964085
        },
        "project":{
            "id":23423233
        },
        "creator":{
            "id":12009183
        },
        "task":{
            "id":13966758
        }
    },
    {
        "id":30438076,
        "description":"Meeting postponed",
        "created_at":"2016-11-11T08:15:40+00:00",
        "by_me":true,
        "comments_count":2,
        "list":{
            "id":13964085
        },
        "project":{
            "id":23423233
        },
        "creator":{
            "id":12009183
        },
        "task":{
            "id":13966758
        }
    }
]

```


Get comment
----------------

* `GET v3/projects/23423233/todolists/13964085/tasks/13966758/comments/30438075` will return the specified comment.

```json
{
    "id":30438075,
    "description":"Meeting with the client",
    "created_at":"2016-11-11T08:11:10+00:00",
    "by_me":true,
    "comments_count":2,
    "list":{
        "id":13964085
    },
    "project":{
        "id":23423233
    },
    "creator":{
        "id":12009183
    },
    "task":{
        "id":13966758
    }
}
```

Create comment
----------------

* `POST v3/projects/23423233/todolists/13964085/tasks/13966758/comments` will create a new comment in the specified task from the parameters passed.

```json
{
	"description":"Call with client"
}
```

Update comment
----------------

* `PUT v3/projects/23423233/todolists/13964085/tasks/13966758/comments/30438075` will update the task comment from the parameters passed.

```json
{
	"description":"Call with client"
}
```


Delete comment
----------------

* `DELETE v3/projects/23423233/todolists/13964085/tasks/13966758/comments/30438075` will delete the task comment.

204 No Content will be returned if the record is deleted. 403 Forbidden will be returned in case of invalid access.


Get task history
----------------

* `GET v3/projects/23423233/todolists/13964085/tasks/13966758/history` will return the history of activities happened in task specified.


```json
[
    {
        "id":31383136,
        "user_id":13592923,
        "activity":"2017-03-22T10:02:51+00:00",
        "date":"2017-03-22",
        "action":"Updated"
    },
    {
        "id":31382865,
        "user_id":13592923,
        "activity":"2017-03-22T10:02:46+00:00",
        "date":"2017-03-22",
        "action":"Updated"
    },
    {
        "id":31382724,
        "user_id":13592923,
        "activity":"2017-03-22T10:02:38+00:00",
        "date":"2017-03-22",
        "action":"Updated"
    }
]
```


Get task history detail
----------------

* `GET v3/projects/23423233/todolists/13964085/tasks/13966758/history/31383136` will return the specified activity happened in task specified.

```json
{
    "content": "<b>Previous:</b> <br>Time estimate: '0' hours '0' mins <br><br><b>New:</b> <br>Time estimate: '100' hours '0' mins <br><br>"
}
```

Get all labels
----------------

* `GET v3/labels` will return all the labels.

```json
[
    {
        "id":12254912,
        "name":"Medium",
        "color":"#FBB008"
    },
    {
        "id":12254913,
        "name":"Low",
        "color":"#999999"
    },
    {
        "id":12254914,
        "name":"Urgent",
        "color":"#FF6600"
    },
    {
        "id":12254915,
        "name":"Pending",
        "color":"#E07798"
    },
    {
        "id":12254916,
        "name":"high",
        "color":"#BF0000"
    }
]
```


Get label
----------------

* `GET v3/labels/12254912` will return the specified label.

```json
{
    "id": 12254912,
    "name": "high",
    "color": "#BF0000"
}
```

Create label
----------------

* `POST v3/labels` will create a new label from the parameters passed.

```json
{
	"name": "In-progress"
}
```

Update label
----------------

* `PUT v3/labels/12254912` will update the task from the parameters passed.

```json
{
	"name": "high"
}
```


Delete label
----------------

* `DELETE v3/labels/12254912` will delete the label.

204 No Content will be returned if the record is deleted. 403 Forbidden will be returned in case of invalid access.
