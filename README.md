# ASLIRI PASSIVE LIVENESS WEB
Passive Liveness by ASLIRI for your web apps. You can verification your client.

## Get Started
Before integrating ASLIRI Passive Liveness Web, you need to have an authorization for credentials. Please contact [ASLIRI](https://asliri.id) to get credentials. You will get:
1. **api-create-session**
2. **verification-url**
3. **token-sdk**

## How does the ASLIRI OTP Web process work?

### VERIFICATION

1. Hit the **api-create-session** API with header **token-sdk**.
2. Our side will give you the **req_id**.
3. Your side can redirect to the **verification-url** with **req_id**, **app_session**, & **callback** parameter.
4. The verification process runs.
5. If successful our side will redirect to the **callback** url you sent earlier and add the **verify_status** parameter.


## How do I integrate ASLIRI Passive Liveness Web ?

### VERIFICATION
#### 1. Hit the API Create Session

URL : **{api-create-session}**
Method: POST JSON

Sample Header Request:
```
Content-Type: "application/json" // json request
token-sdk: "1Z234567A" // token-sdk
```

Sample JSON Body Request:
```json
{
	"app_id": "APP001",
	"user_id": "USER001",
	"callback_url": "http://localhost:3000",
	"app_session": "SESSION002"
}
```

Sample Response:
```json
{
    "code": 200, // status code
    "message": "success", // message
    "result": { // result reqid
        "req_id": "hyjxPh5RXuds5Y4F3FMQ%2FBDYFnF8%2F4qvhlog6MzhAnCR%2BA6Uhkqwv17feZm7FCkWYaCQOc1NDhBI42oA95%2BiEc%2FT8aglujzX4%2BDJWAlqe4%2BUMIm275WITfJEeKTKUdn26ubLf0ePUrsu3Jg5"
    }
}
```

*Please note: only code **200** is success*

#### 2. Redirect to Verification URL
Your side need redirect to verification url.
Sample :
http://verification-url.id?req_id=hyjxPh5RXuds5Y4F3FMQ%2FBDYFnF8%2F4qvhlog6MzhAnCR%2BA6Uhkqwv17feZm7FCkWYaCQOc1NDhBI42oA95%2BiEc%2FT8aglujzX4%2BDJWAlqe4%2BUMIm275WITfJEeKTKUdn26ubLf0ePUrsu3Jg5&callback=http%3A%2F%2Flocalhost%3A3000&app_session=SESSION002

*Please note: the **callback** must be **UrlEncoded** as example*

#### 3. Verification Process runs
<img src="./pics/img1.png" width=500>

*Image: allow camera*

<img src="./pics/img2.png" width=500>

*Image: verification passive liveness*

<img src="./pics/img3.png" width=500>

*Image: success verification and will be redirect to **callback** .*

Sample redirect:

http://localhost:3000?verify_status=true


Done.

