```js
var FormData = require('form-data');
setTimeout(async () => {
    const form = new FormData();
    form.append('title', '[A] Stack_Overflowfgfgf()...');
    form.append('description', `\`\`\`\nError: Connection lost: The server closed the connection.\n\`\`\``);
    form.append('category', 'Important');
    form.append('versions', '1.9, 1.9.3');
    form.append('file', fs.createReadStream('./error.json'));

    let checkres = await axios({
        method: 'post',
        url: `http://localhost:3000/api/feedback/1`,
        headers: {
            'Authorization': 'test',
            ...form.getHeaders()
        },
        data: form
    }).catch(function(err) {
        throw err;
    });
    console.log(checkres.status)
}, 5000);
```

---

*[Improve this page](https://github.com/FAXES/Documentation/tree/main/Product%20Documentation/FaxTrack)*
