# Backend API Documentation

## /profile

Get the profile of a user. Includes Students and Classheads.  

### Requires:
access_token - Access Token

    {
    "access_token": "<Access Token>"
    }

### Returns

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


### Example

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