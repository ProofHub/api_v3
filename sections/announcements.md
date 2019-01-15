Announcements
====================
* [Get announcements](#get-announcements)
* [Get announcement](#get-announcements)
* [Create announcement](#create-announcements)
* [Update announcement](#update-announcements)
* [Delete announcement](#delete-announcements)

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
