# Backend API Documentation

# Profile

## POST /profile

Get the profile of a user. Includes Students and Classheads.  

### Requires:
- access_token: str - Access Token

```json
    {
    "access_token": "<Access Token>"
    }
```

### Returns

```json
    {
    "code": 200,
    "message": {
        "profile": [
        {
            "_id": "<ID>",
            "disabled": <True/False>,
            "identifier": "<ID>",
            "username": "<displayName>",
            "firstname": "<Firstname>",
            "lastname": "<Lastname>",
            "email": "<mail>",
            "expires": "<date>",
            "created": "<date>",
            "sclass": "<sclass>",
            "type": "<Student/>",
            "owned_objects": []
        }
        ]
    }
    }
```

### Example

```json
    {
    "code": 200,
    "message": {
        "profile": [
        {
            "_id": "96ec350d-ea90-406b-a6c6-94463948c77d",
            "disabled": false,
            "identifier": "96ec350d-ea90-406b-a6c6-94463948c77d",
            "username": "SIMĆIĆ Erik, 5AHITS",
            "firstname": "Erik",
            "lastname": "SIMĆIĆ",
            "email": "erik.simcic@edu.htl-villach.at",
            "expires": "2025-01-24T21:19:56.159000",
            "created": "2024-01-25T21:19:56.159000",
            "sclass": "5AHITS",
            "type": "Student",
            "owned_objects": []
        }
        ]
    }
    }
```



# Payments

## POST /payment
Creates a payment object. 

### Requires:

- access_token: str - Access Token

- name: str

- author: str

- target: Student | SClass | list[Student|SClass]

- product: Any = None

- cost: float

- iban: str

- start_date: datetime = datetime.now

- due_date: datetime

- expires: datetime = datetime.now() + timedelta(days=365)

```json
{
"access_token": "string",
"name": "string",
"author": "string",
"target": {
    "disabled": true,
    "identifier": "string",
    "username": "string",
    "firstname": "string",
    "lastname": "string",
    "email": "string",
    "expires": "2025-02-19T19:18:33.693290",
    "created": "2024-02-20T19:18:33.693295",
    "sclass": "string",
    "type": "student",
    "owned_objects": []
},
"product": "string",
"cost": 0,
"iban": "string",
"start_date": "2024-02-20T19:18:41.553Z",
"due_date": "2024-02-20T19:18:41.553Z",
"expires": "2025-02-19T19:18:33.702061"
}
```

### Returns 


### Example

#### Input

```json
{
  "access_token": "string",
  "name": "string",
  "author": "string",
  "target": {
    "disabled": true,
    "identifier": "string",
    "username": "string",
    "firstname": "string",
    "lastname": "string",
    "email": "string",
    "expires": "2025-02-19T19:18:33.693290",
    "created": "2024-02-20T19:18:33.693295",
    "sclass": "string",
    "type": "student",
    "owned_objects": []
  },
  "product": "string",
  "cost": 0,
  "iban": "string",
  "start_date": "2024-02-20T19:18:41.553Z",
  "due_date": "2024-02-20T19:18:41.553Z",
  "expires": "2025-02-19T19:18:33.702061"
}
```

#### Return - 200

```json
```




# Class
