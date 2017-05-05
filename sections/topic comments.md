Discussion Comments
====================

* [Get comments](#get-comments)
* [Get comment](#get-comment)
* [Create comment](#create-comment)
* [Update comment](#update-comment)
* [Delete comment](#delete-comment)

Get comments
----------------

* `GET v3/projects/23423233/topics/25299755/comments` will return comments for the specified topic. 

```json
[
    {
        "id":25299972,
        "updated_at":"2016-12-28T05:54:59+00:00",
        "created_at":"2016-12-28T05:54:59+00:00",
        "proofed":false,
        "description":"Very informative with plenty of examples of good and not-so-good Web marketing",
        "creator":{
            "id":12009183
        },
        "project":{
            "id":23423233
        },
        "topic":{
            "id":25299755
        },
        "by_me":true,
        "attachments":null
    },
    {
        "id":25299973,
        "updated_at":"2016-12-28T05:59:33+00:00",
        "created_at":"2016-12-28T05:59:33+00:00",
        "proofed":false,
        "description":"This was a nice discovery session. I got lots of ideas for marketing on the Web.",
        "creator":{
            "id":12009183
        },
        "project":{
            "id":23423233
        },
        "topic":{
            "id":25299755
        },
        "by_me":true,
        "attachments":[
            {
                "id":50085572,
                "name":"sample.jpg",
                "byte_size":17100,
                "created_at":"2016-12-28T05:59:31+00:00",
                "updated_at":"2016-12-28T05:59:31+00:00",
                "source":"upload",
                "approved_by_me":false,
                "approved_count":0,
                "approved_by":null,
                "file_type":"jpg",
                "proof_count":0,
                "url":{
                    "view":"https://assets.proofhub.com/files/thumb/?image=107184987/857657006/7349029dfd97a1861bdbcc913734aacf1482904771y4/654f4f5455e40915c08cfc87e86bcd9d/%23added%24%25%40%21%5E%5E.jpg",
                    "proofing":"https://assets.proofhub.com/files/proof/display?1/5008543805/857657006/107184987/1482896136/1482904779/",
                    "download":"https://assets.proofhub.com/files/download/?107184987/857657006/7349029dfd97a1861bdbcc913734aacf1482904771y4/654f4f5455e40915c08cfc87e86bcd9d/%23added%24%25%40%21%5E%5E.jpg",
                    "share":"https://assets.proofhub.com/go?BcvX2f"
                },
                "version_main":50085438,
                "notify":[
                    12009183
                ],
                "project":{
                    "id":23423233
                },
                "connected":{
                    "id":25299972,
                    "with":"discussion_comment"
                },
                "creator":{
                    "id":12009183
                },
                "folder":{
                    "id":1946039
                },
                "version":{
                    "count":0,
                    "current":true
                },
                "proofed":false,
                "current_proof_count":0
            }
        ]
    }
]
```

* `GET v3/projects/23423233/topics/25299755/comments/25299972` will return specified comment of the topic. 

```json
{
    "id":25299972,
    "updated_at":"2016-12-28T05:54:59+00:00",
    "created_at":"2016-12-28T05:54:59+00:00",
    "proofed":false,
    "description":"Very informative with plenty of examples of good and not-so-good Web marketing",
    "creator":{
        "id":12009183
    },
    "project":{
        "id":23423233
    },
    "topic":{
        "id":25299755
    },
    "by_me":true,
    "attachments":null
}
```


Create comment
----------------

* `POST v3/projects/23423233/topics/25299755/comments` will create a new comment from the parameters passed for the specified topic.
```json
{
	"description":"The seminar was very user-friendly. Provided very specific and useful info"
}

```
 
`201 Created` will be returned along with the JSON of the comment if the record is added. `403 Forbidden` will be returned in case of invalid access.

**Attaching files**

Attaching files to a topic comment requires both the token and the name of the attachment. The token is obtained from the [Create attachments](
https://github.com/ProofHub/api_v3/blob/master/sections/attachemnts.md#create-attachment) endpoint, which you must hit first before creating an upload. The name parameter must be a valid filename with an extension. Multiple attachments are allowed. Set folder to `0` if you don't want to upload file in any folder.

```json
{
	"description":"The seminar was very user-friendly. Provided very specific and useful info",
	"attachments":[
		{
			"token":"MnF5aVk3clllbEhUNGo1NllwdCtRUT09",
			"name":"senimar_report.xls",
			"folder":7292113
		}
	]
}
```

Update comment
----------------

* `PUT v3/projects/23423233/topics/25299755/comments/25299972` will update the comment from the parameters passed for the specified topic. 

```json
{
	"description":"The seminar was very user-friendly, provided very specific and useful info."
}
```

`200 OK` will be returned along with the JSON of the comment if the record is updated. `403 Forbidden` will be returned in case of invalid access.

Delete comment
----------------

* `DELETE v3/projects/23423233/topics/25299755/comments/25299972` will delete the comment for the section specified. 

`204 No Content` will be returned if the record is deleted. `403 Forbidden` will be returned in case of invalid access.
