Folders
====================

* [Get folders](#get-folders)
* [Create folder](#create-folder)
* [Update folder](#update-folder)
* [Delete folder](#delete-folder)

Get folders
----------------

* `GET v3/projects/23423233/folders` will return folders and subfolders for the specified project.

```json
[
    {
        "id":67811577,
        "level":1,
        "name":"Phase 1 documents",
        "reply_email":"f+107184987-855716680-678115778@mail.proofhub.com",
        "created_at":"2016-12-06T07:06:45+00:00",
        "updated_at":"2016-12-06T07:15:37+00:00",
        "parent_id":"root",
        "type":"folder",
        "project":{
            "id":23423233
        }
    },
    {
        "id":67811578,
        "level":1,
        "name":"Analysis Documents",
        "reply_email":"f+107184987-855716680-678115778@mail.proofhub.com",
        "created_at":"2016-12-06T07:06:45+00:00",
        "updated_at":"2016-12-06T07:15:37+00:00",
        "parent_id":"root",
        "type":"folder",
        "project":{
            "id":23423233
        }
    }
]
```

Create folder
----------------

* `POST v3/projects/23423233/folders` will create a new folder for the parameter passed.

```json
{
    "name": "Phase II Document"
}
```

`201 Created` will be returned along with the JSON of the folder if the record is added. `403 Forbidden` will be returned in case of invalid access.


Update folder
----------------

* `PUT v3/projects/23423233/folders/67811578` will update the folder for the parameter passed.

```json
{
	"name": "Phase 2 Documents"
}
```

`200 OK` will be returned along with the JSON of the folder if the record is updated. `403 Forbidden` will be returned in case of invalid access.

Delete folder
----------------

* `DELETE v3/projects/23423233/folders/67811578` will delete the folder and its subfolders specified.

`204 No Content` will be returned if the record is deleted. `403 Forbidden` will be returned in case of invalid access.
