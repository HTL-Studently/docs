# API/DB Schemas

## Student

### Python Class

```python
class Student(BaseModel):
    disabled: bool = True
    identifier: str
    username: str
    firstname: str
    lastname: str
    email: str
    expires: datetime = datetime.now() + timedelta(days=365)
    created: datetime = datetime.now()
    sclass: str
    type: str = "student"
    owned_objects: list = []

    def return_dict(self):
        return {
            "disabled": str(self.disabled),
            "identifier": str(self.identifier),
            "username": str(self.username),
            "firstname": str(self.firstname),
            "lastname": str(self.lastname),
            "email": str(self.email),
            "expires": str(self.expires),
            "created": str(self.created),
            "sclass": str(self.sclass),
            "type": str(self.type),
            "owned_objects": str(self.owned_objects),
        }
```

### Example
```json
{
    "disabled": False ,
    "identifier": "96ec350d-ea90-406b-a6c6-94463948c77d",
    "username": "SIMĆIĆ Erik, 5AHITS",
    "firstname": "Erik",
    "lastname": "SIMĆIĆ",
    "email": "erik.simcic@edu.htl-villach.at",
    "expires": datetime.datetime(2025, 1, 24, 21, 19, 56, 159000),"created": datetime.datetime(2024, 1, 25, 21, 19, 56, 159000),
    "sclass": "5AHITS",
    "type": "Student",
    "owned_objects": [],
}
```