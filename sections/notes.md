Notes
====================

* [Get notes](#get-notes)
* [Get note](#get-note)
* [Create note](#create-note)
* [Update note](#update-note)
* [Delete note](#delete-note)
* [Get all note comments](#get-all-comments)
* [Get comment](#get-comment)
* [Create comment](#create-comment)
* [Update comment](#update-comment)
* [Delete comment](#delete-comment)
* [Resolve comment](#resolve-comment)
* [Re-open comment](#re-open-comment)

Get notes
----------------

* `GET v3/projects/23423233/notebooks/41246749/notes` will return notes added in this project.

```json
[
	{
      "id": 80731707,
      "title": "Requirements for launch party",
      "content": null,
      "color": "4A4A4A",
      "private": false,
      "assigned": [
        12009183
      ],
      "updated_by": 12009183,
      "created_at": "2016-12-27T12:10:37+00:00",
      "updated_at": "2016-12-27T12:11:08+00:00",
      "comments": 0,
      "project": {
        "id": 23423233
      },
      "creator": {
        "id": 12009183
      },
      "notebook": {
        "id": 41246749
      }
    },
	{
      "id": 80731708,
      "title": "Launch of the New Website",
      "content": "A post on our Blog ...",
      "color": "4A4A4A",
      "private": false,
      "assigned": [
        12009183
      ],
      "updated_by": 12009183,
      "created_at": "2016-12-27T12:10:37+00:00",
      "updated_at": "2016-12-27T12:11:08+00:00",
      "comments": 0,
      "project": {
        "id": 23423233
      },
      "creator": {
        "id": 12009183
      },
      "notebook": {
        "id": 41246749
      }
    }
]
```

Get note
----------------

* `GET v3/projects/23423233/notebooks/41246749/notes/80731708` will return the specified note.

```json
{
      "id": 80731708,
      "title": "Launch of the New Website",
      "content": "A post on our Blog ...",
      "color": "4A4A4A",
      "private": false,
      "assigned": [
        12009183
      ],
      "updated_by": 12009183,
      "created_at": "2016-12-27T12:10:37+00:00",
      "updated_at": "2016-12-27T12:11:08+00:00",
      "comments": 0,
      "project": {
        "id": 23423233
      },
      "creator": {
        "id": 12009183
      },
      "notebook": {
        "id": 41246749
      }
    }
```
Create note
----------------

* `POST v3/projects/23423233/notebooks/41246749/notes` will create a new note from the parameters passed. 
* The assigend array is an optional list of people IDs that you can get from the [people API](https://github.com/sdplabs/proofhub-api/blob/master/sections/people.md). 

```json
{
	"title": "Requirements",
	"description":"Requirements for designing",
	"content":"Mention all that will be required for designing a LOGO for the client.",
	"private":true,
	"assigned":[12009183, 11679192]
}
```

`201 Created` will be returned along with the JSON of the note ([Get note](#get-note)) if the record is added. `403 Forbidden` will be returned in case of invalid access.

Update note
----------------

* `PUT v3/projects/23423233/notebooks/41246749/notes/80731709` will update the note from the parameters passed.

```json
{
	"title": "Requirements",
	"description":"Requirements for designing the LOGO ",
	"content":"Mention all that will be required for designing a LOGO for the client.",
	"private":false,
}
```

`200 OK` will be returned along with the JSON of the note ([Get note](#get-note)) if the record is updated. `403 Forbidden` will be returned in case of invalid access.

Delete note
----------------

* `DELETE v3/projects/23423233/notebooks/41246749/notes/80731708` will delete the note.

`204 No Content` will be returned if the record is deleted. `403 Forbidden` will be returned in case of invalid access.

Get all note comments
----------------

* `GET v3/projects/23423233/notebooks/41246749/notes/80731708/comments` will return all the comments of specified note.

```json
[
  {
    "id": 36215469,
    "description": "Design of website completed",
    "status": "open",
    "updated_at": "2016-12-27T13:30:53+00:00",
    "created_at": "2016-12-27T13:30:53+00:00",
    "by_me": true,
    "project": {
      "id": 23423233
    },
    "creator": {
      "id": 12009183
    },
    "note": {
      "id": 80731708
    }
  },
  {
    "id": 36215467,
    "description": "Content updated",
    "status": "open",
    "updated_at": "2016-12-28T04:55:47+00:00",
    "created_at": "2016-12-28T04:55:47+00:00",
    "by_me": false,
    "project": {
      "id": 23423233
    },
    "creator": {
      "id": 12009183
    },
    "note": {
      "id": 80731708
    }
  }
]

```


Get comment
----------------

* `GET v3/projects/23423233/notebooks/41246749/notes/80731708/comments/36215469` will return the specified comment.

```json
{
    "id": 36215469,
    "description": "Design of website completed",
    "status": "open",
    "updated_at": "2016-12-27T13:30:53+00:00",
    "created_at": "2016-12-27T13:30:53+00:00",
    "by_me": true,
    "project": {
      "id": 23423233
    },
    "creator": {
      "id": 12009183
    },
    "note": {
      "id": 80731708
    }
  }
```

Create comment
----------------

* `POST v3/projects/23423233/notebooks/41246749/notes/13966758232/comments` will create a new comment in the specified note from the parameters passed.

```json
{
	"description":"Meeting with the client"
}
```

Update comment
----------------

* `PUT v3/projects/23423233/notebooks/41246749/notes/13966758232/comments/30438075` will update the note comment from the parameters passed.

```json
{
	"description":"Call with client"
}
```

`200 OK` will be returned along with the JSON of the comment if the record is updated. `403 Forbidden` will be returned in case of invalid access.



Delete comment
----------------

* `DELETE v3/projects/23423233/notebooks/41246749/notes/13966758232/comments/30438075` will delete the note comment.
```
`204 No Content` will be returned if the record is deleted. `403 Forbidden` will be returned in case of invalid access.



Resolve comment
----------------

* `PUT v3/projects/23423233/notebooks/41246749/notes/13966758232/comments/30438075` will change the status of specified comment to resolved

```json
{
	"status":"resolved"
}
```

`200 OK` will be returned along with the JSON of the comment if the record is updated. `403 Forbidden` will be returned in case of invalid access.

Re-open comment
----------------

* `PUT v3/projects/23423233/notebooks/41246749/notes/13966758232/comments/30438075` will change the status of specified comment to re-opened

```json
{
	"status":"open"
}
```

`200 OK` will be returned along with the JSON of the comment if the record is updated. `403 Forbidden` will be returned in case of invalid access.



