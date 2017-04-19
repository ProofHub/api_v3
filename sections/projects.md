Projects
====================

* [Get all projects](#get-all-projects)
* [Get project](#get-project)
* [Create project](#create-project)
* [Update project](#update-project)
* [Delete project](#delete-project)


Get all projects
----------------

* `GET v3/projects` will return all the projects.

```json
[
    {
        "id":23423233,
        "title":"PH Marketing",
        "description":"Project description goes here",
        "archived":false,
         "color":"#41236D",
         "start_date":"2016-12-10",
        "end_date":"2016-12-15",
        "template": false,
        "sample_project": false,
        "favourite": false,
        "favourite_sort": null,
        "category": {
        "id": 65707070
    },
        "creator": {
        "id": 11765082
    },
        "assigned": [
                     12009183,
                     11679192,
                     ],
        "manager": {
        "id": 11679192
    },
       "created_at": "2016-06-24T12:18:26+00:00",
       "modified_at": "2016-06-24T12:18:26+00:00"
    },
     {
        "id":23423234,
        "title":"Rockwall Phase II",
        "description":"Develop and execute the 2016 plan",
        "archived":false,
         "color":"#41236D",
         "start_date":"2016-12-10",
        "end_date":"2016-12-15",
        "template": false,
        "sample_project": false,
        "favourite": false,
        "favourite_sort": null,
        "category": {
        "id": 65707070
    },
        "creator": {
        "id": 12009183
    },
        "assigned": [
                     12009183,
                     11679192,
                     ],
        "manager": {
        "id": 11679192
    },
       "created_at": "2016-06-24T12:18:26+00:00",
       "modified_at": "2016-06-24T12:18:26+00:00"
    },
]
```

Get project
----------------

* `GET v3/projects/23423233` will return project specified.

```json
{
       "id":23423233,
        "title":"PH Marketing",
        "description":"Project description goes here",
        "archived":false,
         "color":"#41236D",
         "start_date":"2016-12-10",
        "end_date":"2016-12-15",
        "template": false,
        "sample_project": false,
        "favourite": false,
        "favourite_sort": null,
        "category": {
        "id": 65707070
    },
        "creator": {
        "id": 12009183
    },
        "assigned": [
                     12009183,
                     11679192,
                     ],
        "manager": {
        "id": 11679192
    },
       "created_at": "2016-06-24T12:18:26+00:00",
       "modified_at": "2016-06-24T12:18:26+00:00"
    }
```
Create project
----------------

* `POST v3/projects` will create a new project to the account.

```json
{
	"title":"To the moon",
	"description":"DBX's campaign",
	"category":651073331,
	"start_date":"2016-12-10",
	"end_date":"2016-12-15",
    "assigned": [
                     12009183,
                     11679192,
                     ],
    "manager": 11679192,
}
```

You can get the category from the [categories API](https://github.com/sdplabs/proofhub-api/blob/master/sections/categories.md).

`201 Created` will be returned along with the JSON of the project ([Get project](#get-project)) if the record is added. `You have reached the project limit` will be returned if the account has reached the project limit. `403 Forbidden` will be returned in case of invalid access.


Update project
----------------

* `PUT v3/projects/23423233` will update the project from the parameters passed.

```json
{
	"title":"To the moon 2014",
	"description":"DBX's campaign",
    "archived":false,
	"category":651073331,
	"start_date":"2016-12-10",
	"end_date":"2016-12-15",
    "assigned": [
                     12009183,
                     11679192,
                     ],
     "manager": 11679192,
}
```
`200 OK` will be returned along with the JSON of the project ([Get project](#get-project)) if the record is updated. `403 Forbidden` will be returned in case of invalid access.


Delete project
----------------

* `DELETE v3/projects/23423233` will delete the project.

`204 No Content` will be returned if the record is deleted. `403 Forbidden` will be returned in case of invalid access.




