Events
====================

* [Get all events](#get-all-events)
* [Get event](#get-event)
* [Create event](#create-event)
* [Update event](#update-event)
* [Delete event](#delete-event)

Get all events
----------------

* `GET v3/projects/23423233/events?view=all&startDate=2019-02-25&endDate=2019-03-31` will return all events and milestones for this project. 
* View filter is mandatory 
* To get only milestones use: view=milestones
* To get only events use: view=events
* Start date and end date filters are optional


```json
[
    {
        "id":643515557,
        "title":"Coming soon",
        "start":"2016-12-28 00:00",
        "end":"2016-12-28 23:59",
        "all_day":false,
        "reminder":null,
        "milestone":false,
        "private":false,
        "completed":false,
        "assigned":[
            242125851
        ],
        "description":"Details will follow",
        "updated_at":"2016-12-27T07:46:24+00:00",
        "created_at":"2016-12-27T07:46:24+00:00",
        "by_me":true,
        "creator":{
            "id":242125851
        },
        "project":{
            "id":857779124,
            "name":"PH Marketing"
        }
    },
    {
        "id":643501988,
        "title":"Target completed",
        "start":"2016-12-27 00:00",
        "end":"2016-12-27 23:59",
        "all_day":true,
        "reminder":null,
        "milestone":true,
        "private":false,
        "completed":false,
        "assigned":[
            242125851
        ],
        "description":null,
        "updated_at":"2016-12-27T06:07:53+00:00",
        "created_at":"2016-12-27T06:07:53+00:00",
        "by_me":true,
        "creator":{
            "id":242125851
        },
        "project":{
            "id":857779124,
            "name":"PH Marketing"
        }
    }
]
```

Get event
----------------

* `GET v3/projects/23423233/events/643515557` will return the specified event.

```json
{
    "id":643515557,
    "title":"Coming soon",
    "start":"2016-12-28 00:00",
    "end":"2016-12-28 23:59",
    "all_day":false,
    "reminder":null,
    "milestone":false,
    "private":false,
    "completed":false,
    "assigned":[
        242125851
    ],
    "description":"Details will follow",
    "updated_at":"2016-12-27T07:46:24+00:00",
    "created_at":"2016-12-27T07:46:24+00:00",
    "by_me":true,
    "creator":{
        "id":242125851
    },
    "project":{
        "id":857779124,
        "name":"PH Marketing"
    }
}
```

Create event
----------------

* `POST /projects/23423233/events` will create a new event from the parameters passed. 
* The `start` and `end` are either dates if the event is an all day affair or times with timezones if they're not.
* Set the `milestone` to `true` if you want to set any event as a milestone.
* The assigned array is an optional list of people IDs that you can get from the [people API](https://github.com/ProofHub/api_v3/blob/master/sections/people.md). 
* Proofhub will send a reminder email to all the assigned users if `reminder` is set. `reminder` is the number of minutes before the event is going to occur or at the start time of event.

```json
{
    "title":"Milestone type event",
    "description":"Details to follow",
    "start":"2016-04-20",
    "private":true,
    "milestone":true,
    "assigned":[5895623, 4634893]
}
```

```json
{
    "title":"Single-day event",
    "description":"Details to follow",
    "start":"2016-04-20",
    "all_day":true,
    "private":false,  
    "assigned":[5895623, 4634893]
}
```

```json
{
    "title":"Multi-day event",
    "description":"Details to follow",
    "start":"2016-04-20",
    "end":"2016-04-22",
    "private":false,
    "all_day":true,
    "assigned":[5895623, 4634893]
}
```

```json
{
    "title":"Timed event",
    "description":"Details to follow",
    "start":"2016-04-20T15:30:00-05:00",
    "end":"2016-04-20T16:30:00-05:00",
    "private":false,
    "all_day":false,
    "reminder":30,
    "assigned":[5895623, 4634893]
}
```

`201 Created` will be returned along with the JSON of the event ([Get event](#get-event)) if the record is added. `403 Forbidden` will be returned in case of invalid access.

Update event
----------------

* `PUT v3/projects/23423233/events/789456` will update the event from the parameters passed.

```json
{
    "title":"Timed event",
    "description":"Details to follow",
    "start":"2016-04-20T15:30:00-05:00",
    "end":"2016-04-20T18:30:00-05:00",
    "private":true,
    "all_day":false,
    "assigned":[5895623, 4634893]
}
```

`200 OK` will be returned along with the JSON of the event ([Get event](#get-event)) if the record is updated. `403 Forbidden` will be returned in case of invalid access.

Complete milestone
----------------

* `PUT v3/projects/23423233/events/845875` with the following JSON to complete a milestone. You can pass `false` to incomplete the milestone.
* Only milestone type events can be completed.

```json
{
    "completed":true
}
```

`200 OK` will be returned along with the JSON of the event ([Get event](#get-event)) if the record is updated. `403 Forbidden` will be returned in case of invalid access.

Delete event
----------------

* `DELETE v3/projects/23423233/events/789456` will delete the event.

`204 No Content` will be returned if the record is deleted. `403 Forbidden` will be returned in case of invalid access.
