Attachments
====================

Uploading files to ProofHub is a two step process:

* Create the attachment, receive a attachment id verifying the upload was successful.
* Attach the file to a topic, comment, task or file section. See the following endpoints for attaching:
	* [Create topic](https://github.com/ProofHub/api_v3/blob/master/sections/topics.md#create-topic)
	* [Create task](https://github.com/ProofHub/api_v3/blob/master/sections/tasks.md#create-task)
	* [Create file](https://github.com/ProofHub/api_v3/blob/master/sections/files.md#create-file)


Create attachments
----------------

* `POST /files/upload` uploads a file. The request body should be the binary data of the attachment. Make sure to set the Content-Type header.

```File uploading via API is a two-step process.

1. First, you need to get the file ID using the request URL: 

POST /files/upload.php  

In the headers, you need to pass the x-api-key and in the body (form data) you need to pass the project id and upload the file as:

pid:<project id>
file:<select the file>

In the response of this request, you'll get the "file_id".

2. The next step is to attach the file with the help of "file_id" you have received.

The request URL would be,

POST  /api/v3/projects/<project_id>/folders/<folder_id>/files"

Headers:

x-api-key
Content-type:Application/JSON


```json
{
  "folder": <folder id>
  "attachments": <file_id>
}

If the folder parameter is not specified, the file will be uploaded in "All files".
```

