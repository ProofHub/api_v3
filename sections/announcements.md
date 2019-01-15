Announcements
====================
* [Get announcements](#get-announcements)
* [Get announcement](#get-announcement)
* [Create announcement](#create-announcement)
* [Update announcement](#update-announcement)
* [Delete announcement](#delete-announcement)
* [Get all comments](#get-all-comments)
* [Get comment](#get-comment)
* [Create comment](#create-comment)
* [Update comment](#update-comment)
* [Delete comment](#delete-comment)

Get all announcements
----------------

* `GET v3/announcements` will return all announcements in an account.

```json
[
     {
            "id": 29965434,
            "title": "Celebrate christmas event",
            "description": "",
            "assigned": [
                5317500,
                2877438
            ],
            "created_at": "2019-01-15T12:21:40+00:00",
            "updated_at": "2019-01-15T12:21:40+00:00",
            "created_by": 53175005,
            "updated_by": 53175005,
            "deleted": false,
            "deleted_by": null,
            "deleted_source": null,
            "valid_till": {
                "date": "2019-01-16T12:21:40+00:00",
                "text": "24hours"
            },
            "comments_allowed": true,
            "hide_subscribers": false,
            "pinned": false,
            "attachments": [],
            "seen": [],
            "comments": {
                "count": 0
            }
        },
     {
            "id": 29965434,
            "title": "Birthday celebration",
            "description": "",
            "assigned": [
                53175005,
                42018808,

            ],
            "created_at": "2019-01-15T12:21:40+00:00",
            "updated_at": "2019-01-15T12:21:40+00:00",
            "created_by": 531750057,
            "updated_by": 531750057,
            "deleted": false,
            "deleted_by": null,
            "deleted_source": null,
            "valid_till": {
                "date": "2019-01-16T12:21:40+00:00",
                "text": "forever"
            },
            "comments_allowed": true,
            "hide_subscribers": false,
            "pinned": false,
            "attachments": [],
            "seen": [],
            "comments": {
                "count": 0
            }
        }
]
```

Get announcement
----------------

* `GET v3/announcements/3628560` will return the specified request form.

```json
  {
            "id": 29965434,
            "title": "Celebrate christmas event",
            "description": "",
            "assigned": [
                5317500,
                2877438
            ],
            "created_at": "2019-01-15T12:21:40+00:00",
            "updated_at": "2019-01-15T12:21:40+00:00",
            "created_by": 53175005,
            "updated_by": 53175005,
            "deleted": false,
            "deleted_by": null,
            "deleted_source": null,
            "valid_till": {
                "date": "2019-01-16T12:21:40+00:00",
                "text": "24hours"
            },
            "comments_allowed": true,
            "hide_subscribers": false,
            "pinned": false,
            "attachments": [],
            "seen": [],
            "comments": {
                "count": 0
            }
        }
```

Create announcement
----------------

* `POST v3/announcements` will create a new announcement.

```json
    {
    	"title":"Celebrate christmas event",
	    "assigned": [
                5317500,
                2877438
            ],
          "valid_till":"24hours"
    }
```

`200 OK` will be returned along with the JSON of the announcement ([Get announcement](#get-announcements)) if the record is added. 


Update announcement
----------------

* `PUT v3/announcement/3628560` will update the announcement.

```json
    {
	    "title":"Christmas celebration for this year"
    }
```

`200 OK` will be returned along with the JSON of the announcement ([Get announcements](#get-announcements)) if the record is updated. `403 Forbidden` will be returned in case of invalid access.

Delete announcement
----------------

* `DELETE v3/announcement/3628560` will delete the announcement specified.

`204 No Content` will be returned if the record is deleted. `403 Forbidden` will be returned in case of invalid access.


Get all announcement comments
----------------

* `GET v3/announcements/3628560/comments` will return all the comments of specified announcement.

```json
[
    {
            "id": 4475533,
            "description": "Celebrations will start from next week",
            "announcement": 29965434,
            "created_at": "2019-01-15T12:50:46+00:00",
            "updated_at": "2019-01-15T12:50:46+00:00",
            "created_by": 53175005,
            "updated_by": 53175005,
            "attachments": []
        },
        {
            "id": 44768902,
            "description": "Here are the screenshots for celebration",
            "announcement": 29965434,
            "created_at": "2019-01-15T12:50:57+00:00",
            "updated_at": "2019-01-15T12:50:57+00:00",
            "created_by": 531750057,
            "updated_by": 531750057,
            "attachments": [
                {
                    "id": 2041111053,
                    "name": "Christmas.png",
                    "byte_size": 62156,
                    "created_at": "2019-01-15T12:50:55+00:00",
                    "updated_at": "2019-01-15T12:50:55+00:00",
                    "source": "upload",
                    "approved_by_me": false,
                    "approved_count": 0,
                    "approved_by": null,
                    "by_me": true,
                    "file_type": "png",
                    "proof_count": 0,
                    "url": {
                        "download": "https://yourcompany.proofhub.com/files/download/chat.php?94077609/a61744e1a00749156169e285086dd24e1547556655gz/726db883fb386fe904f39a6f6b7457a74fd2d8e9/Screen+Shot+2019-01-08+at+4.30.51+PM.png",
                        "thumbnail": "https://yourcompany.proofhub.com/files/view/chat.php?width=350&image=94077609/a61744e1a00749156169e285086dd24e1547556655gz.png",
                        "image": "https://yourcompany.proofhub.com/files/view/chat.php?image=94077609/a61744e1a00749156169e285086dd24e1547556655gz.png",
                        "share": "https://yourcompany.proofhub.com/go?nqWurw"
                    },
                    "creator": {
                        "id": 53175005
                    },
                    "updated_by": 53175005,
                    "version_main": 2041111053,
                    "version_count": 0,
                    "current_version": true,
                    "proof_version": 1,
                    "connected_with": "announcement_comment",
                    "connected_id": 4476890,
                    "notify": null,
                    "project": {
                        "id": 1959608
                    },
                    "connected": {
                        "id": 44768902,
                        "with": "announcement_comment"
                    },
                    "folder": {
                        "id": 0
                    },
                    "version": {
                        "count": 0,
                        "current": true
                    }
                }
            ]
        }
]

```


Get comment
----------------

* `GET v3/announcements/3628560/comments/4475533` will return the specified comment.

```json
{
            "id": 4475533,
            "description": "Celebrations will start from next week",
            "announcement": 29965434,
            "created_at": "2019-01-15T12:50:46+00:00",
            "updated_at": "2019-01-15T12:50:46+00:00",
            "created_by": 53175005,
            "updated_by": 53175005,
            "attachments": []
        }
```

Create comment
----------------

* `POST v3/announcements/3628560/comments/4475533` will create a new comment in the specified announcement from the parameters passed.

```json
{
	"description":"All employees participation is required"
}
```

`200 OK` will be returned along with the JSON of the comment ([Get comment](#get-comment)) if the record is added. `403 Forbidden` will be returned in case of invalid access.

Update comment
----------------

* `PUT v3/announcements/3628560/comments/4475533` will update the announcement comment from the parameters passed.

```json
{
	"description":"Call with client"
}
```

`200 OK` will be returned along with the JSON of the comment ([Get comment](#get-comment)) if the record is updated. `403 Forbidden` will be returned in case of invalid access.


Delete comment
----------------

* `DELETE v3/announcements/3628560/comments/4475533` will delete the announcement comment.

204 No Content will be returned if the record is deleted. 403 Forbidden will be returned in case of invalid access.


