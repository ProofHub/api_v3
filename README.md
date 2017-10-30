ProofHub API
====================
This RESTful API is an interface to the resources in ProofHub e.g. Projects, Discussions, Tasks, Files, Notes, People etc. 

If you are new to REST, you can understand the basics at http://en.wikipedia.org/wiki/REST. ProofHub's RESTful API accepts and returns JSON for serialisation.

Getting an API key
----------------
Any user can get their own API key by visiting the Manage profile dropdown and clicking 5 times on the profile picture. The API key of the logged in user will be displayed in the pop up window opened.

Making a request
----------------
All URLs (Base url) start with `https://companyurl.proofhub.com/api/v3/` (No HTTP, only HTTPS). You'll also need to include the `User-Agent` header to identify your app with every request.

**Here is a curl based example:**

```shell
curl -H 'X-API-KEY: YOUR API KEY' -H 'User-Agent: AppName (name@example.com)' https://companyurl.proofhub.com/api/v3/projects
```

To create something, it's the same deal except you also have to include the `Content-Type` header and the JSON data:

```shell
curl -H 'X-API-KEY: YOUR API KEY' -H 'Content-Type: application/json' -H 'User-Agent: AppName (name@example.com)' -X POST -d '{ "name": "New project!" }' https://companyurl.proofhub.com/api/v3/projects
```

API endpoints
----------------

* [Projects](https://github.com/ProofHub/api_v3/blob/master/sections/projects.md)
* [Categories](https://github.com/ProofHub/api_v3/blob/master/sections/categories.md)
* [Groups](https://github.com/ProofHub/api_v3/blob/master/sections/groups.md)
* [People](https://github.com/ProofHub/api_v3/blob/master/sections/people.md)
* [Roles](https://github.com/ProofHub/api_v3/blob/master/sections/roles.md)
* [Topics](https://github.com/ProofHub/api_v3/blob/master/sections/topics.md)
* [Topic Comments](https://github.com/ProofHub/api_v3/blob/master/sections/topic%20comments.md)
* [Todolists](https://github.com/ProofHub/api_v3/blob/master/sections/tododlists.md)
* [Tasks](https://github.com/ProofHub/api_v3/blob/master/sections/tasks.md)
* [Files](https://github.com/ProofHub/api_v3/blob/master/sections/files.md)
* [Attachments](https://github.com/ProofHub/api_v3/blob/master/sections/attachments.md)
* [Events and milestones](https://github.com/ProofHub/api_v3/blob/master/sections/events%20and%20milestones.md)
* [Notebooks](https://github.com/ProofHub/api_v3/blob/master/sections/notebooks.md)
* [Notes](https://github.com/ProofHub/api_v3/blob/master/sections/notes.md)
* [Folders](https://github.com/ProofHub/api_v3/blob/master/sections/folders.md)
* [Timesheets](https://github.com/ProofHub/api_v3/blob/master/sections/timesheets.md)
* [Time](https://github.com/ProofHub/api_v3/blob/master/sections/time.md)
* [Quickies](https://github.com/ProofHub/api_v3/blob/master/sections/quickies.md)



Things to remember
----------------
* **JSON Format**

  We support JSON for receiving and sending the data. You must include `Content-Type: application/json` header with every POST and PUT request. Requests with invalid formats will be returned with `415` response. 

* **Identify your app**

  You must include the `User-Agent: AppName (name@example.com)` header with every request. If this header is not supplied, request will be returned with `400` response. 

* **Rate Limits**

  API calls are subject to rate limiting. Exceeding any rate limits will result in requests returning a status code of 429 (Too Many Requests). Rate limits are 50 requests per 10 second for the same account from the same IP. Check the Retry-After header to learn how many seconds to wait before retrying the request.

* **Handling errors**

  Error codes 500 Internal Server Error, 502 Bad Gateway, 503 Service Unavailable, or 504 Gateway Timeout means an error has occurred at our end. Re-trying in some time should solve the problem.
