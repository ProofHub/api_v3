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
		"url":"https://assets.proofhub.com/thumb/user/index.php/thumb_sample.png?width=1000&height=800&image=2176707/47659038/812b4ba287f5ee0bc9d43bbf5bbe87fb1388474998pd/3ffc91b37825807f0b232f25c2434d64/sample.png",
		"creator":{
	        "id":5895623,
	        "name":"Stella Altois",
	        "image_url":"https://assets.proofhub.com/thumb/user/index.php?width=80&height=80&cropratio=1:1&image=123456/812b4ba287f5ee0bc9d43bbf5bbe87fb1370073119.jpg"
	    },
		"attachable":null
	},
	{
		"id":4512451,
		"name":"logo.png",
		"byte_size":"13598",
		"created_at":"2013-12-31T09:26:46+00:00",
		"source":"upload",
		"url":"https://assets.proofhub.com/thumb/user/index.php/thumb_zoom.png?width=1000&height=800&image=2176707/47659038/812b4ba287f5ee0bc9d43bbf5bbe87fb1388482006a1/9e2e7017902acb7999b66589efca3639/logo.png",
		"creator":{
			"id":4634893,
	        "name":"Chris Wagleys",
	        "image_url":null
		},
		"attachable":{
			"id":852369,
			"type":"Comment",
			"url":"https://api.proofhub.com/v1/projects/23423233/topics/123456/comments/852369.json"
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
