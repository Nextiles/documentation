# Nextiles API Documentation
The following documentation talks about how one can leverage Nextiles API and get the raw stream of data from Nextiles' servers. 

To access the API you:
1. would need to have a user registered
2. access key


## Use Cases
1. Integrate the API within your application by just invoking the following endpoint and get the raw stream, which can be filtered, analyzed and optimized

## Get Endpoint
```http
GET https://68a9g89ek2.execute-api.us-east-1.amazonaws.com/alpha/trainingdata
```
### Implementation

Here is an example of invoking the endpoint via **curl command**


```bash
curl -X GET -H "x-api-key: <access-key>" 'https://68a9g89ek2.execute-api.us-east-1.amazonaws.com/alpha/trainingdata/?role_type=Athlete&username=TestingUniqueUsername'
```

Another example of the api with passing the range, `start_range` as `20210325180053` (`March 25th, 2021, 18:00:53`) and `end_range` as `20210529180000` (`May 29th,2021,18:00:00`) :

```bash
curl -X GET -H "x-api-key: <access-key>" 'https://68a9g89ek2.execute-api.us-east-1.amazonaws.com/alpha/trainingdata/?role_type=Athlete&username=TestingUniqueUsername&start_range=20210325180053&end_range=20210529180000'
```


## Authorization
You will need the api-key which Nextiles provide and add it to the Headers.

```http
Headers
x-api-key : <access-key-given-by-Nextiles>
```

| Parameters    | Type          | Description  |
| ------------- |:-------------:| :-----|
| username      | String | Required. Unique username |
| role_type     | String |  Required. Role type of the user. What exactly the user's role is. For ex.: Athlete, Guest, Tester, etc.|
| organization  | String | What organization the user belongs to|
| start_range| String | format: `YYYYmmddHHMMSS`, is the starting point for the range, where you want to look specifically|
|end_range| String| format: `YYYYmmddHHMMSS`, is the ending point for the range.|

**Note: If start_range and end_range is not available, then API returns all of the data available.**
**If end_range is not available, API returns all of the data starting from the start_range**

## Responses

Response is in the json format. Data format is an array of objects and raw Nextiles data.

### Example

```json
{
 "2021-06-02": {
        "12:29:09": {
            "12:29:09": "time,measurement,value,field,type,BLE Device,Product Type\n12:29:09:8650,IMU,161,ax,acceleration,NX2,SLEEVE\n......"
             },
        "14:02:47": {
            "14:02:47":"time,measurement,value,field,type,BLE Device,Product Type\n14:02:48:2010,IMU,33,ax,acceleration,NX2,SLEEVE\n14:02:48:2010,IMU,-3,ay,acceleration,NX2,SLEEVE\n......"
            },
    }
}
```

## Status Codes

| Status Code    | Description  |
| ------------- |:-----:|
| 200      | Ok |
| 400     | BAD REQUEST/ Invalid Parameters |
| 403   | Forbidden|
| 500  | INTERNAL SERVER ERROR |
