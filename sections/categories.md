Categories
====================

* [Get Categories](#get-categories)
* [Get Category](#get-category)
* [Create Category](#create-category)
* [Update Category](#update-category)
* [Delete Category](#delete-category)

Get Categories
----------------

* `GET v3/categories` will return all account Categories.

```json
[
	{
		"id":65707070,
		"name":"Marketing Projects",
		"default":false
	},
	{
		"id":65707071,
		"name":"Uncategorized",
		"default":true
	}
]
```

Get Category
----------------

* `GET v3/categories/65707070` will return the specified Category.

```json
{
	"id":65707070,
	"name":"Marketing Projects",
	"default":false
}
```

Create Category
----------------

* `POST v3/categories` will create a new Category.

```json
{
	"name": "Rockwall Phase I"
}
```

`201 Created` will be returned along with the JSON of the category ([Get Category](#get-category)) if the record is added. 


Update Category
----------------

* `PUT v3/categories/65707070` will update the category.

```json
{
	"name": "Rockwall Phase II"
}
```

`200 OK` will be returned along with the JSON of the category ([Get Category](#get-category)) if the record is updated. `403 Forbidden` will be returned in case of invalid access.

Delete Category
----------------

* `DELETE v3/categories/65707070` will delete the category specified.

`204 No Content` will be returned if the record is deleted. `403 Forbidden` will be returned in case of invalid access.
