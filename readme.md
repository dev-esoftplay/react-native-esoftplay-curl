# Esoftplay Curl
A Curl with esoftplay configuration

#### Instalation
1. install the npm package
```
npm install --save react-native-esoftplay-curl
```
2. Create class extends EsoftplayCurl
3. override any variables or functions you want
4. set main url
```
export default class Curl extends EsoftplayCurl {
  url = config.url
}
```
5. done

#### Usage

###### Structured output json
```
new Curl(uri, post, onDone, onFailed, debug)
```
Arguments
- uri (string) - uri or url 
- post (object) - post with key-value to post
- onDone(callback) - callback with 2 param (result , message)
  - result: result of curl
  - message: message of curl
- onFailed(callback) - callback with 1 param (message) 
  - message: message of curl
- debug(0|1) : console log curl process default 0

###### Unstructured output json
```
new Curl().custom(uri, post, onDone, debug)
```
Arguments
- uri (string) - uri or url 
- post (object) - post with key-value to post
- onDone(callback) - callback with 1 param (result )
  - result: result of curl
- debug(0|1) : console log curl process default 0

###### Upload Image or File
```
new Curl().upload(uri, key ,fileUri, mimeType, onDone, onFailed, debug)

```
Arguments
- uri (string) - uri or url 
- key (string) - key for post fileupload
- fileUri (string) - uri from local file
- mimeType (string) - mimeType of file | default : 'image/jpeg '
- onDone(callback) - callback with 2 param (result , message)
  - result: result of curl
  - message: message of curl
- onFailed(callback) - callback with 1 param (message) 
  - message: message of curl
- debug(0|1) : console log curl process default 0


#### Examples

###### GET
```
new Curl('movies', null,
  (result, message){
  	//do your stuf	
  },
  (message){
  	//do your stuf
  }
)
```

###### POST
```
var post ={
  key1:value1,
  key2:value2
}

new Curl('movies', post,
  (result, message){
  	//do your stuf	
  },
  (message){
  	//do your stuf
  }
)
```
