Quickies
====================
* [Get quickies](#get-quickies)
* [Get quickie](#get-quickie)
* [Create quickie](#create-quickie)
* [Update quickie](#update-quickie)
* [Delete quickie](#delete-quickie)
* [Complete quickie](#complete-quickie)

Get all quickies
----------------

* `GET v3/quickies` will return all quickies of specified user.

```json
[
    {
        "id":84050329,
        "due_date":"2016-11-25",
        "type":"quickie",
        "title":"Make notes regarding meeting",
        "completed":false,
        "created_at":"2016-10-26T07:46:12+00:00",
        "completed_at":"2016-11-03T08:14:48+00:00",
        "creator":{
            "id":12009183
        }
    },
    {
        "id":84050327,
        "due_date":null,
        "type":"shortcut",
        "title":"First topic",
        "completed":false,
        "created_at":"2016-11-24T09:41:35+00:00",
        "completed_at":null,
        "creator":{
            "id":12009183
        }
    }
]
```

Get quickie
----------------

* `GET v3/quickies/84050329` will return the specified quickie.

```json
{
    "id": 840503292,
    "due_date": "2016-11-25",
    "type": "quickie",
    "title": "Make notes regarding meeting",
    "completed": false,
    "created_at": "2016-10-26T07:46:12+00:00",
    "completed_at": "2016-11-03T08:14:48+00:00",
    "creator": {
        "id": 12009183
    }
}
```

Create quickie
----------------

* `POST v3/quickies` will create a new quickie.

```json
{
	"title":"Prepare notes for meeting"
}
```

`201 Created` will be returned along with the JSON of the quickie ([Get quickies](#get-quickies)) if the record is added. 


Update quickie
----------------

* `PUT v3/quickies/84050329` will update the quickie.

```json
{
	"title":"Call with client"
}
```

`200 OK` will be returned along with the JSON of the quickie ([Get quickies](#get-quickies)) if the record is updated. `403 Forbidden` will be returned in case of invalid access.

Complete quickie
----------------

* `PUT v3/quickies/84050329` will mark the quickie as complete.

```json
{
	"completed": true
}
```

`200 OK` will be returned along with the JSON of the quickie ([Get quickies](#get-quickies)) if the record is updated. `403 Forbidden` will be returned in case of invalid access.

Delete quickie
----------------

* `DELETE v3/quickies/84050329` will delete the quickie specified.

`204 No Content` will be returned if the record is deleted. `403 Forbidden` will be returned in case of invalid access.
