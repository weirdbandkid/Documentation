This is a quick example for using the API within FaxTrack. These examples use the  `form-data` NPM package to send files through the request. This is not required though.

> The 'title' field is required in all requests.


### Create Issue

```js
var FormData = require('form-data');
const form = new FormData();
form.append('title', 'TITLE');
form.append('description', `DESCRIPTION_SUPPORTS_MARKDOWN`);
form.append('category', 'CATEGORY_NAME');
form.append('versions', 'AFFECTED_VERSIONS');
form.append('labels', 'LABELS');
form.append('links', 'LINKS_COMMA_SEPERATED');
form.append('file', fs.createReadStream('./PATH_TO_FILE'));

let checkres = await axios({
    method: 'post',
    url: `https://bugs.example.com/api/issue/PROJECT_ID`,
    headers: {
        'Authorization': 'API_TOKEN_HERE',
        ...form.getHeaders()
    },
    data: form
}).catch(function(err) {
    throw err;
});
console.log(checkres.status)
```

### Create Feedback

```js
var FormData = require('form-data');
const form = new FormData();
form.append('title', 'TITLE');
form.append('description', `DESCRIPTION_SUPPORTS_MARKDOWN`);
form.append('labels', 'LABELS');
form.append('links', 'LINKS_COMMA_SEPERATED');
form.append('file', fs.createReadStream('./PATH_TO_FILE'));

let checkres = await axios({
    method: 'post',
    url: `https://bugs.example.com/api/feedback/PROJECT_ID`,
    headers: {
        'Authorization': 'API_TOKEN_HERE',
        ...form.getHeaders()
    },
    data: form
}).catch(function(err) {
    throw err;
});
console.log(checkres.status)
```

---

*[Improve this page](https://github.com/FAXES/Documentation/tree/main/Product%20Documentation/FaxTrack)*
