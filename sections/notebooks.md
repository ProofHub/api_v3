Notebooks
====================

* [Get all notebooks](#get-all-notebooks)
* [Get notebook](#get-notebook)
* [Create notebook](#create-notebook)
* [Update notebook](#update-notebook)
* [Delete notebook](#delete-notebook)

Get all notebooks
----------------

* `GET v3/projects/23423233/notebooks` will return notebooks for this project.

```json
[
    {
        "id":412467490,
        "title":"Book having requirements",
        "created_at":"2016-12-27T12:08:57+00:00",
        "updated_at":"2016-12-27T12:11:08+00:00",
        "pinned":false,
        "by_me":true,
        "project":{
            "id":"857779124"
        },
        "creator":{
            "id":242125851
        }
    },
    {
        "id":412467490,
        "title":"Blog writing",
        "created_at":"2016-12-27T12:08:57+00:00",
        "updated_at":"2016-12-27T12:11:08+00:00",
        "pinned":false,
        "by_me":true,
        "project":{
            "id":"857779124"
        },
        "creator":{
            "id":242125851
        }
    }
]
```

Get notebook
----------------

* `GET v3/projects/23423233/notebooks/13964085196` will return the specified notebook.

```json
{
    "id":412467490,
    "title":"Book having requirements",
    "created_at":"2016-12-27T12:08:57+00:00",
    "updated_at":"2016-12-27T12:11:08+00:00",
    "pinned":false,
    "by_me":true,
    "project":{
        "id":"857779124"
    },
    "creator":{
        "id":242125851
    }
}
```

Create notebook
----------------

* `POST v3/projects/23423233/notebooks` will create a new notebook from the parameters passed. 


```json
{
  
    "title": "Book having requirements"
}
```

`201 Created` will be returned along with the JSON of the notebook ([Get notebook](#get-notebook)) if the record is added. `403 Forbidden` will be returned in case of invalid access.

Update notebook
----------------

* `PUT v3/projects/23423233/notebooks/1396408546` will update the notebook from the parameters passed.

```json
{
  
    "title": "Book having requirements for new website"
}
```

`200 OK` will be returned along with the JSON of the notebook ([Get notebook](#get-notebook)) if the record is updated. `403 Forbidden` will be returned in case of invalid access.

Delete notebook
----------------

* `DELETE v3/projects/23423233/notebook/1396408546` will delete the notebook.

`204 No Content` will be returned if the record is deleted. `403 Forbidden` will be returned in case of invalid access.
