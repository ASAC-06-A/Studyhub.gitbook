# user

## User Actions

## 로그인

<mark style="color:green;">`POST`</mark> `/users/signin`

로그인 요청 API

**Headers**

| Name         | Value              |
| ------------ | ------------------ |
| Content-Type | `application/json` |

**Body**

| Name       | Type   | Description  |
| ---------- | ------ | ------------ |
| `email`    | string | 이메일과 아이디로 쓰임 |
| `password` | string | 비밀번호         |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
    "success": true,
    "message": "로그인 성공",
    "body": {
        "userId": 1,
        "status": 200
    }
}
```
{% endtab %}

{% tab title="400" %}
```json
{
    "status": 401,
    "error": "Invalid Credentials",
    "message": "이메일 또는 패스워드 불일치"
}
```
{% endtab %}

{% tab title="400" %}
```json
{
    "status": 400,
    "error": "Email or Password is null.",
    "message": "이메일또는 비밀번호가 비었습니다. 로그인을 위해 입력해주세요"
}
```
{% endtab %}

{% tab title="500" %}
```json
{
    "status": 500,
    "error": "Internal Server Error",
    "message": "서버나 DB가 매우 열심히 일하다 지쳐쓰러진 상태!, 조금 쉬었다가 다시 일할게요"
}
```
{% endtab %}
{% endtabs %}



## Create a new user

<mark style="color:green;">`POST`</mark> `/users`

회원가입 요청 API

**Headers**

| Name         | Value              |
| ------------ | ------------------ |
| Content-Type | `application/json` |

**Body**

| Name       | Type   | Description |
| ---------- | ------ | ----------- |
| `userName` | string | 사용자 닉네임     |
| `email`    | string | 이메일         |
| `password` | string | 비밀번호        |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
    "success": true,
    "message": "회원가입 성공",
    "body": {
        "userId": 3,
        "status": 201
    }
}
```


{% endtab %}

{% tab title="400" %}
```json
{
    "success": false,
    "message": "잘못된 입력 값입니다",
    "body": [
        {
            "field": "userName",
            "message": "공백일 수 없습니다"
        }
    ]
}
```
{% endtab %}
{% endtabs %}









