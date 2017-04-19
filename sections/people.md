People
====================

* [Get people](#get-people)
* [Get person](#get-person)
* [Create person](#create-person)
* [Update person](#update-person)
* [Delete person](#delete-person)

Get people
----------------

* `GET v3/people` will return all people.

```json
[
	{
       "id": 12009183,
       "first_name": "Chris",
       "last_name": "Wagley",
       "title": "Manager",
       "email": "chris@email.com",
       "role": {
      "id": 903912753
    },
       "groups": [
         33838231,
         33838232
       ],
       "timezone": 8,
       "initials": "N",
       "image_url": null,
       "profile_color": "#781f1f",
       "language": "en",
       "suspended": false,
       "send_invite": true,
       "last_active": "2016-09-19T06:17:22+00:00",
       "created_at": "2016-09-16T10:39:25+00:00",
       "updated_at": "2016-09-16T10:39:25+00:00",
       "projects": [
         23423233,
         23423234
       ]
     },

	{
       "id": 11679192,
       "first_name": "Stella",
       "last_name": "Altois",
       "title": "Manager",
       "email": "stella@email.com",
       "role": {
      "id": 90391275
    },
       "groups": [
         33838231,
         33838232
       ],
       "timezone": 10,
       "initials": "C",
       "image_url": null,
       "profile_color": "#781f1f",
       "language": "en",
       "suspended": false,
       "send_invite": true,
       "last_active": "2016-09-19T06:17:22+00:00",
       "created_at": "2016-09-16T10:39:25+00:00",
       "updated_at": "2016-09-16T10:39:25+00:00",
       "projects": [
       23423233,
       23423234
       ]
     }
]
```

Get person
----------------

* `GET v3/people/11679192` will return the specified person.

```json
{
       "id": 11679192,
       "first_name": "Stella",
       "last_name": "Altois",
       "title": "Manager",
       "email": "stella@email.com",
       "role": {
      "id": 90391275
    },
       "groups": [
         33838231,
         33720182
       ],
       "timezone": 10,
       "initials": "C",
       "image_url": null,
       "profile_color": "#781f1f",
       "language": "en",
       "suspended": false,
       "send_invite": true,
       "last_active": "2016-09-19T06:17:22+00:00",
       "created_at": "2016-09-16T10:39:25+00:00",
       "updated_at": "2016-09-16T10:39:25+00:00",
       "projects": [
       23423233,
       23423234
       ]
     }
```

Create person
----------------

* `POST v3/people` will add a new person to the account.

```json
{
    "first_name":"Stella",
    "last_name":"Altois",
    "email":"stella.altois@email.com",
    "role":"90391275",
    "language":"en"
}
```

Language includes `en`, `fr`. You can get the group from the [groups API](https://github.com/sdplabs/proofhub-api/blob/master/sections/groups.md).

`201 Created` will be returned along with the JSON of the person ([Get person](#get-person)) if the record is added. New people can also be invited directly to the [projects](https://github.com/sdplabs/proofhub-api/blob/master/sections/projects.md#assign-people-to-project).

Update person
----------------

* `PUT v3/people/11679192` will update the person.

```json
{
    "first_name":"Stella",
    "last_name":"Altois",
    "email":"stella.altois@email.com",
    "role":"90391275",
    "language":"en"
}
```

`200 OK` will be returned along with the JSON of the person ([Get person](#get-person)) if the record is updated. `403 Forbidden` will be returned in case of invalid access.

Delete person
----------------

* `DELETE v3/people/11679192` will delete the person specified.

`204 No Content` will be returned if the record is deleted. `403 Forbidden` will be returned in case of invalid access.
