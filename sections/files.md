Files
====================

* [Get files](#get-files)
* [Create file](#create-file)
* [Delete file](#delete-file)

Get files
----------------

* `GET /projects/996424247/folders/130798955/files` will shows all files for this project with file metadata, urls, and associated attachables (Tasks, Topics, or Comments) with a 200 OK response.

```json
[
    {
        "id":1254836,
        "name":"sample.png",
        "byte_size":11830,
        "created_at":"2013-12-31T07:29:58+00:00",
        "updated_at": "2017-10-03T09:36:48+00:00",
        "source":"upload",
	"approved_by_me": false,
        "approved_count": 0,
        "approved_by": null,
        "by_me": true,
        "file_type": "png",
        "proof_count": 0,
        "url":"https://companyurl.proofhub.com/files/thumb/user/image.png",
        "creator":{
            "id":58956234
        },
    },
    {
        "id":4512451,
        "name":"logo.png",
        "byte_size":"13598",
        "created_at":"2013-12-31T09:26:46+00:00",
        "updated_at": "2017-10-03T09:36:48+00:00",
        "source":"upload",
	"approved_by_me": false,
        "approved_count": 0,
        "approved_by": null,
        "by_me": true,
        "file_type": "png",
        "proof_count": 0,
        "url":"https://companyurl.proofhub.com/files/thumb/user/image.png",
        "creator":{
            "id":58956234
        },
    }
]
```

Create file
----------------

* `POST /projects/23423233/folders/13261847/files` will create a new entry in the "Files" section for the given project, with the given attachment id. Attaching files requires the attachment id. The attachment id is returned from the Create attachments endpoint, which you must hit first before creating a file. Multiple attachments are allowed.

```json
{
	"attachments":[
		{
			"attachments": [10966416],
                        "folder": 1326184710
		}
	]
}
```

`201 Created` will be returned along with the JSON of the attachment if the record is added. `403 Forbidden` will be returned in case of invalid access.

Delete file
----------------

* `DELETE /projects/23423233/folders/13261847/files/10966416` will delete the file specified.

`204 No Content` will be returned if the record is deleted. `403 Forbidden` will be returned in case of invalid access.
