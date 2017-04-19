Groups
====================

* [Get groups](#get-groups)
* [Get group](#get-group)
* [Create group](#create-group)
* [Update group](#update-group)
* [Delete group](#delete-group)

Get groups
----------------

* `GET v3/groups` will return all account groups.

```json
[
    {
        "id":1946039,
        "name":"All people",
        "assigned":[
            1176508223,
            1201610344,
            1202234505,
            1202254505,
            1202234598
        ]
    },
    {
        "id":33838231,
        "name":"RockWall",
        "assigned":[
            12009183,
            11679192
        ]
    }
]
```

Get group
----------------

* `GET v3/groups/33838231` will return the specified group.

```json
{
	"id":33838231,
	"name":"abc",
	"assigned": [
        12009183,
        11679192,
		13829833,
        13592923
    ]
}
```

Create group
----------------

* `POST v3/groups` will create a new group.

```json
{
	"name": "Executives",
	"assigned": [
        12009183,
        11679192
    ]
}
```

`201 Created` will be returned along with the JSON of the group ([Get group](#get-group)) if the record is added. 


Update group
----------------

* `PUT v3/groups/33838231` will update the group.

```json
{
	"name": "Old Clients",
	"assigned": [
        12009183
    ]
}
```

`200 OK` will be returned along with the JSON of the group ([Get group](#get-group)) if the record is updated. `403 Forbidden` will be returned in case of invalid access.

Delete group
----------------

* `DELETE v3/groups/33838231` will delete the group specified.

`204 No Content` will be returned if the record is deleted. `403 Forbidden` will be returned in case of invalid access.
