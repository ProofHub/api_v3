Topics
====================

* [Get topics](#get-topics)
* [Get topic](#get-topic)
* [Create topic](#create-topic)
* [Update topic](#update-topic)
* [Delete topic](#delete-topic)

Get all topics
----------------

* `GET v3/projects/23423233/topics` will return topics for this project.

```json
[
    {
        "id":25299755,
        "title":"Introduction",
        "description":"Introduction for discussing the marketing process",
        "private":false,
        "archived":false,
        "comments":{
            "count":0
        },
        "attachments":null,
        "updated_at":"2016-10-17T05:58:34+00:00",
        "created_at":"2016-10-17T05:58:34+00:00",
        "reply_email":"c+284134590-851876733-25299755465@mail.proofhub.com",
        "updated_by": 12009183,
        "assigned":[
            12009183,
            11679192
        ],
        "creator":{
            "id":12009183
        },
        "project":{
            "id":23423233
        },
        "by_me":true
    },
    {
        "id":25299972,
        "title":"Marketing Strategy",
        "description":"Topic to discuss the marketing strategy for PH",
        "comments":{
            "count":2
        },
        "attachments":2,
        "updated_at":"2016-10-17T10:41:11+00:00",
        "created_at":"2016-10-17T10:40:57+00:00",
        "reply_email":"c+284134590-851876733-25299972565@mail.proofhub.com",
        "updated_by": 12009183,
        "assigned":[
            1176508223
        ],
        "creator":{
            "id":12009183
        },
        "project":{
            "id":23423233
        },
        "by_me":true
    }
]
```

Get topic
----------------

* `GET v3/projects/23423233/topics/25299972` will return the specified topic.

```json
{
    "id":25299972,
    "title":"Marketing Strategy",
    "description":"Topic to discuss the marketing strategy for PH",
    "private":false,
    "archived":false,
    "comments":{
        "count":2
    },
    "attachments":[
        {
            "id":50085572,
            "name":"sample.png",
            "byte_size":844902,
            "created_at":"2016-12-28T07:18:23+00:00",
            "updated_at":"2016-12-28T07:18:23+00:00",
            "source":"upload",
            "approved_by_me":false,
            "approved_count":0,
            "approved_by":null,
            "file_type":"png",
            "proof_count":0,
            "url":{
                "view":"https://assets.proofhub.com/files/thumb/?image=107184987/857657006/7349029dfd97a1861bdbcc913734aacf1482909503ky/7affbafe96af69db97c8dd0289069e6a/3.png",
                "proofing":"https://assets.proofhub.com/files/proof/display?1/5008557374/857657006/107184987/1482900878/1482909521/",
                "download":"https://assets.proofhub.com/files/download/?107184987/857657006/7349029dfd97a1861bdbcc913734aacf1482909503ky/7affbafe96af69db97c8dd0289069e6a/3.png",
                "share":"https://assets.proofhub.com/go?29yX2f"
            },
            "version_main":50085573,
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
            }
        }
    ],
    "updated_at":"2016-10-17T10:41:11+00:00",
    "created_at":"2016-10-17T10:40:57+00:00",
    "reply_email":"c+284134590-851876733-25299972565@mail.proofhub.com",
    "updated_by": 12009183,
    "assigned":[
        1176508223
    ],
    "creator":{
        "id":12009183
    },
    "project":{
        "id":23423233
    },
    "by_me":true
}
```
Create topic
----------------

* `POST v3/projects/23423233/topics` will create a new topic from the parameters passed. 
* The assigned array is an optional list of people IDs that you can get from the [people API](https://github.com/ProofHub/api_v3/blob/master/sections/people.md). 

```json
{
	"title":"New topic for discussion",
	"description":"Topic content...",
	"private":true,
	"assigned":[12009183, 11679192]
}
```

`201 Created` will be returned along with the JSON of the topic ([Get topic](#get-topic)) if the record is added. `403 Forbidden` will be returned in case of invalid access.

**Attaching files**

Attaching files to a topic requires both the token and the name of the attachment. The token is obtained from the [Create attachments](
https://github.com/ProofHub/api_v3/blob/master/sections/attachemnts.md#create-attachment) endpoint, which you must hit first before creating an upload. The name parameter must be a valid filename with an extension. Multiple attachments are allowed. Set folder to `0` if you don't want to upload file in any folder.

```json
{
	"title":"New topic for discussion",
	"description":"Topic content...",
	"private":true,
	"attachments":[
		{
			"token":"WSt5b0JZdFZjRjNST1BXblhQRnk5QT09",
			"name":"sample.jpg",
			"folder":72921132
		},
		{
			"token":"UVBEbHZkc2puN3h3VHB2cDlZQ3JWdz09",
			"name":"graphs.png",
			"folder":0
		}
	],
	"assigned":[12009183, 11679192]
}
```

Update topic
----------------

* `PUT v3/projects/23423233/topics/25299755` will update the topic from the parameters passed.

```json
{
	"title":"Modify the topic for discussion",
	"description":"Topic content...",
	"private":true,
    "assigned":[12009183, 11679192]
}
```

`200 OK` will be returned along with the JSON of the topic ([Get topic](#get-topic)) if the record is updated. `403 Forbidden` will be returned in case of invalid access.

Delete topic
----------------

* `DELETE v3/projects/23423233/topics/25299755` will delete the topic.

`204 No Content` will be returned if the record is deleted. `403 Forbidden` will be returned in case of invalid access.
