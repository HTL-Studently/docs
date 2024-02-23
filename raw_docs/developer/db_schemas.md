# DB Schemas

This page shows how various objects and data is saved in the database.

    DO NOT use these schemas in the body of API requests

## Student

Used to hold a student user in the StudentDB

### Student Class

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

### Student Example

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

## SClass

## ClassHead

## Payment

Used to assign a payment assignment to a student.

### Payment Class

```python
class Payment(BaseModel):
    disabled: bool
    id: str = str(uuid.uuid4())
    name: str
    author: str | Student | ClassHead
    target: str | list[str] # Student ID, Class ID
    product: Any = None
    confirmation: str | None
    payed: bool = False
    cost: float
    iban: str
    bic: str
    start_date: datetime = datetime.now()
    due_date: datetime
    expires: datetime = datetime.now() + timedelta(days=365)
```

### Payment Example

```json
{
  "access_token": "",
  "disabled": false,
  "name": "SupaLizenz3000",
  "author": "string",
  "target_type": "",
  "target": "5AHITS",
  "product": "SupaLizenz3000",
  "confirmation": "string",
  "payed": false,
  "cost": 0,
  "iban": "AT452070604600063657",
  "bic": "KSPKAT2KXXX",
  "start_date": "2024-02-22T23:37:03.486Z",
  "due_date": "2024-02-22T23:37:03.486Z",
  "expires": "2025-02-21T23:36:40.823700"
}
```


## Payment Confirmation

Used to hold a file that confirms a payment made by a student.

### Payment Confirmation Class

```python
class PaymentConfirmation(BaseModel):
    disabled: bool = False
    author: str
    expires: None | datetime = datetime.now() + timedelta(days=365)
    created: datetime = datetime.now()
    filedata: any
```

### Payment Confirmation Example

```json

```



## Admin

## License

## LicenseGroup

## PaymentConfirmation
