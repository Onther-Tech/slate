---
title: Tokyo API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - javascript

toc_footers:
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# 들어가는말

안녕하세요. 온더의 도쿄 프로젝트 API문서입니다.

# 인증

도쿄 프로젝트는 별도의 API키를 사용하지 않습니다.

# 유저

## 특정 유저 조회하기

> 요청 예제

```javascript
//https://github.com/request/request
const request = require('request');

request(
  {
    method : 'GET',
    uri : 'http://onther.io/api/user/<user_id>'
  }, (error, response, body) => {
    if(error){
      console.log(response.statusCode);
    } else {
      console.log(body);
    }
  }
);
```

> 응답 예제

```json
{
  "error" : 0,
  "result" : "<user_id>"
}
```
user_id를 가진 유저가 있는지 여부를 확인합니다.

### HTTP Request

`GET http://onther.io/api/user/<user_id>`

### URL Parameters

Parameter |  Description
--------- |  -----------
user_id |  2^256의 랜덤값을 통해서 만들어진 이더리움 주소


<aside class="success">
유저값이 반환되면 해당 유저는 존재합니다!
</aside>

## 유저 생성하기

> 요청 예제

```javascript
//https://github.com/request/request
const request = require('request');

request(
  {
    method : 'POST',
    uri : 'http://onther.io/api/user'
  }, (error, response, body) => {
    if(error){
      console.log(response.statusCode);
    } else {
      console.log(body);
    }
  }
);
```

> 응답예제

```json
{
  "error": 0,
  "result": "<user_id>"
}
```

이 요청은 유저의 계정을 생성해 반환합니다.

### HTTP Request

`POST http://onther.io/api/user`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

## Delete a Specific Kitten

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete
