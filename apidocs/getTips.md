
---
### [getTips](https://github.com/iotaledger/iri/blob/dev/src/main/java/com/iota/iri/service/API.java#L671)
 [AbstractResponse](https://github.com/iotaledger/iri/blob/dev/src/main/java/com/iota/iri/service/dto/AbstractResponse.java) getTipsStatement()

Returns the list of tips.

<Tabs> 

<Tab language="Python">

<Section type="request">

```Python
import urllib2
import json

command = {"command": "getTips"}

stringified = json.dumps(command)

headers = {
    'content-type': 'application/json',
    'X-IOTA-API-Version': '1'
}

request = urllib2.Request(url="http://localhost:14265", data=stringified, headers=headers)
returnData = urllib2.urlopen(request).read()

jsonData = json.loads(returnData)

print jsonData
```
</Section>

<Section type="response">

```json
{"duration": "408", "hashes": ["P9KFSJVGSPLXAEBJSHWFZLGP9GGJTIO9YITDEHATDTGAFLPLBZ9FOFWWTKMAZXZHFGQHUOXLXUALY9999", "P9KFSJVGSPLXAEBJSHWFZLGP9GGJTIO9YITDEHATDTGAFLPLBZ9FOFWWTKMAZXZHFGQHUOXLXUALY9999"]}
```
</Section>

<Section type="error">

```json
{"error": "'command' parameter has not been specified"}
```
</Section>

<Tab language="NodeJS">

<Section type="request">

```javascript
var request = require('request');

var command = {"command": "getTips"}

var options = {
  url: 'http://localhost:14265',
  method: 'POST',
  headers: {
    'Content-Type': 'application/json',
		'X-IOTA-API-Version': '1',
    'Content-Length': Buffer.byteLength(JSON.stringify(command))
  },
  json: command
};

request(options, function (error, response, data) {
  if (!error && response.statusCode == 200) {
    console.log(data);
  }
});
```
</Section>

<Section type="response">

```json
{"duration": "202", "hashes": ["P9KFSJVGSPLXAEBJSHWFZLGP9GGJTIO9YITDEHATDTGAFLPLBZ9FOFWWTKMAZXZHFGQHUOXLXUALY9999", "P9KFSJVGSPLXAEBJSHWFZLGP9GGJTIO9YITDEHATDTGAFLPLBZ9FOFWWTKMAZXZHFGQHUOXLXUALY9999"]}
```
</Section>

<Section type="error">

```json
{"error": "'command' parameter has not been specified"}
```
</Section>

<Tab language="cURL">

<Section type="request">

```bash
curl http://localhost:14265 
-X POST 
-H 'Content-Type: application/json' 
-H 'X-IOTA-API-Version: 1' 
-d '{"command": "getTips"}'
```
</Section>

<Section type="response">

```json
{"duration": "393", "hashes": ["P9KFSJVGSPLXAEBJSHWFZLGP9GGJTIO9YITDEHATDTGAFLPLBZ9FOFWWTKMAZXZHFGQHUOXLXUALY9999", "P9KFSJVGSPLXAEBJSHWFZLGP9GGJTIO9YITDEHATDTGAFLPLBZ9FOFWWTKMAZXZHFGQHUOXLXUALY9999"]}
```
</Section>

<Section type="error">

```json
{"error": "'command' parameter has not been specified"}
```
</Section>
</Tabs<





***

Returns [GetTipsResponse](https://github.com/iotaledger/iri/blob/dev/src/main/java/com/iota/iri/service/dto/GetTipsResponse.java)

|Return | Description |
|--|--|
| duration | The duration it took to process this command in milliseconds |
| hashes | The list of current tips |
***