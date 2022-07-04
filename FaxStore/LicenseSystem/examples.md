- [V2 - Node.Js](#v2---node-js)
- [V1 - Node.Js](#v1---node.js)
- [V2 - Lua](#v2---lua)
- [V1 - Lua](#v1---lua)


## V2 - Node JS

```js
var options = {
    hostname: 'license.example.com',
    port: 443,
    path: '/api/check/PRODUCT_ID',
    method: 'POST',
    headers: {
         'Content-Type': 'application/x-www-form-urlencoded',
         'Authorization': 'LICENSE_KEY',
    }
};
var req = https.request(options, (res) => {
    res.on('data', (d) => {
        console.log(d);
    });
});
```

## V1 - Node.Js

```js
const axios = require("axios");
const options = {
    productId: 1,
    licenseKey: "phfn2408g02hg04g0230iog",
    log: false,
    info: "Information to add to the request."
}


let licensecheck = axios({
method: 'post',
url: `https://license.your.domain/api/checkitem/${options.productId}`,
    headers: {
        Accept: 'application/json, text/plain, */*',
        'User-Agent': '*',
        'authorization': options.licenseKey,
    },
    params: {
        info: options.info,
        log: options.log
    }
});

if(licensecheck.data.pass) {
    console.log('the license system has passed.');
} else {
    console.log('the license system has failed.');
}
```

## V2 - Lua
```lua
local productId = 1;
local licenseKey = 'ABC_123';

PerformHttpRequest("https://license.example.com/api/check/" .. productId, function(errorCode, resultData, resultHeaders)
    local data = json.decode(resultData)
    if data['pass'] then        
        print('^2Authorisation completed!^7')            
    else
        print('^1' .. data.details .. '^7')
        os.exit(0)
    end
end, "POST", "", {
    ["Accept"] = "application/json, text/plain, */*",
    ["User-Agent"] = "*",
    ["Authorization"] = licenseKey
});
```

## V1 - Lua

```lua
local productId = 1
local licenseKey = "ABC_123"
PerformHttpRequest("https://yourlinkhere/api/checkitem/" .. productId, function(code, data, headers)
    print("Return code: " .. code)
    print("Return data: " .. data)
    print("Return headers: " .. headers)
end, "POST", "", {
    ["Accept"] = "application/json, text/plain, */*",
    ["User-Agent"] = "*",
    ["authorization"] = licenseKey
})  
```
