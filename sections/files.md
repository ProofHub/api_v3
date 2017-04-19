Files
====================

* [Get files](#get-files)
* [Create file](#create-file)
* [Delete file](#delete-file)

Get files
----------------

* `GET /projects/23423233/files.json` will shows all files for this project with file metadata, urls, and associated attachables (Tasks, Topics, or Comments) with a 200 OK response.

```json
[
    {
        "id":1254836,
        "name":"sample.png",
        "byte_size":11830,
        "created_at":"2013-12-31T07:29:58+00:00",
        "source":"upload",
        "url":"https://companyurl.proofhub.com/files/thumb/user/image.png",
        "creator":{
            "id":5895623,
            "name":"Stella Altois",
            "image_url":"https://companyurl.proofhub.com/files/thumb/user/image.png"
        },
        "attachable":null
    },
    {
        "id":4512451,
        "name":"logo.png",
        "byte_size":"13598",
        "created_at":"2013-12-31T09:26:46+00:00",
        "source":"upload",
        "url":"https://companyurl.proofhub.com/files/thumb/user/image.png",
        "creator":{
            "id":4634893,
            "name":"Chris Wagleys",
            "image_url":null
        }
    }
]
```

Create file
----------------

* `POST /projects/23423233/files.json` will create a new entry in the "Files" section for the given project, with the given attachment token. Attaching files requires both the token and the name of the attachment. The token is returned from the Create attachments endpoint, which you must hit first before creating a file. The name parameter must be a valid filename with an extension. Multiple attachments are allowed. Set folder to `0` if you don't want to upload file in any folder.

```json
{
	"attachments":[
		{
			"token":"alJ0TmxZM1JUU3ViL2wyYUg1SzZ2UT09",
			"name":"sample_logo.png",
			"folder":7292113
		}
	]
}
```

`201 Created` will be returned along with the JSON of the attachment if the record is added. `403 Forbidden` will be returned in case of invalid access.

Delete file
----------------

* `DELETE /projects/23423233/files/1254836.json` will delete the file specified.

`204 No Content` will be returned if the record is deleted. `403 Forbidden` will be returned in case of invalid access.
