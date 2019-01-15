Request forms
====================
* [Get request forms](#get-requestform)
* [Get request form](#get-requestform)
* [Create request form](#create-requestform)
* [Update requestform](#update-requestform)
* [Delete request form](#delete-requestform)

Get all request forms
----------------

* `GET v3/requestform` will return all request forms in an account.

```json
[
    {
       "id":3628560,
        "title":"Accepting all requests for training",
        "description":"Submit your training material requests here",
        "company_id":940776,
        "project_id":18397034,
        "list_id":3993104933,
        "list_name":"Training material on technology and its use in IT sector",
        "list_status":"active",
        "labels":[
        ],
        "url":"https:\/\/yourcompany.proofhub.com\/link\/form?token=d47e49ca76a73916e022560ad9e6c019ef311f",
        "type":"task",
        "status":"enabled",
        "created_at":"2019-01-14T11:17:43+00:00",
        "updated_at":"2019-01-14T11:17:43+00:00",
        "updated_by":531750057,
        "redirect_url":"",
        "deleted":0,
        "deleted_by":195960,
        "deleted_source":null
        }
    },
    {
       "id":3628560,
        "title":"Request form for marketing department",
        "description":"",
        "company_id":940776,
        "project_id":23423233,
        "list_id":399310493,
        "list_name":"Training material on marketing",
        "list_status":"active",
        "labels":[
        ],
        "url":"https:\/\/yourcompany.proofhub.com\/link\/form?token=d47e49ca76a73916e022560ad9e6c019ef311f",
        "type":"task",
        "status":"enabled",
        "created_at":"2019-01-14T11:17:43+00:00",
        "updated_at":"2019-01-14T11:17:43+00:00",
        "updated_by":5317500,
        "redirect_url":"https://www.myapplication.com",
        "deleted":0,
        "deleted_by":195960,
        "deleted_source":null
        }
    }
]
```

Get request form
----------------

* `GET v3/requestform/3628560` will return the specified request form.

```json
 {
       "id":3628560,
        "title":"Accepting all requests for training",
        "description":"Submit your training material requests here",
        "company_id":940776,
        "project_id":18397034,
        "list_id":3993104933,
        "list_name":"Training material on technology and its use in IT sector",
        "list_status":"active",
        "labels":[
        ],
        "url":"https:\/\/yourcompany.proofhub.com\/link\/form?token=d47e49ca76a73916e022560ad9e6c019ef311f",
        "type":"task",
        "status":"enabled",
        "created_at":"2019-01-14T11:17:43+00:00",
        "updated_at":"2019-01-14T11:17:43+00:00",
        "updated_by":531750057,
        "redirect_url":"",
        "deleted":0,
        "deleted_by":195960,
        "deleted_source":null
    }
```

Create request form
----------------

* `POST v3/requestform` will create a new request form.

```json
    {
    	"title":"Submit your training material requests here",
	    "project_id":18397034,
	    "list_id":3993104933
    }
```

`200 OK` will be returned along with the JSON of the request form ([Get requestform](#get-requestform)) if the record is added. 


Update request form
----------------

* `PUT v3/requestform/3628560` will update the request form.

```json
    {
	    "title":"Call with client"
    }
```

`200 OK` will be returned along with the JSON of the request form ([Get quickies](#get-requestform)) if the record is updated. `403 Forbidden` will be returned in case of invalid access.

Delete request form
----------------

* `DELETE v3/requestform/3628560` will delete the request form specified.

`204 No Content` will be returned if the record is deleted. `403 Forbidden` will be returned in case of invalid access.
