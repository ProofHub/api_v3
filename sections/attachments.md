Attachments
====================

Uploading files to ProofHub is a two step process:

* Create the attachment, receive a attachment id verifying the upload was successful.
* Attach the file to a topic, comment, task or file section. See the following endpoints for attaching:
	* [Create topic](https://github.com/ProofHub/api_v3/blob/master/sections/topics.md#create-topic)
	* [Create comment](https://github.com/ProofHub/api_v3/blob/master/sections/comments.md#create-comment)
	* [Create task](https://github.com/ProofHub/api_v3/blob/master/sections/tasks.md#create-task)
	* [Create file](https://github.com/ProofHub/api_v3/blob/master/sections/files.md#create-file)


Create attachments
----------------

* `POST /files/upload` uploads a file. The request body should be the binary data of the attachment. Make sure to set the Content-Type header. Here is an example:

```shell
curl --data-binary @sample.png --data project = 23423233 -H 'X-API-KEY: YOUR API KEY, User-Agent: AppName (name@example.com)' https://files.proofhub.com/files/upload
```

Once the upload is successful, you'll get a 200 OK response, and we'll give you an attachment id back that you'll need to save locally to attach the file.

```json
{
  "file_id": 10890757
}
```
