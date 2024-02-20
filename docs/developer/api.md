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