# Installation

# Environment

### Backend .env 

```json
CLOUD_INSTANCE="https://login.microsoftonline.com/"
TENANT_ID="<TENANT-ID>"
CLIENT_ID="<CLIENT-ID>"
CLIENT_SECRET="<CLIENT-SECRET>"
REDIRECT_URI="http://localhost:5173/callback"
```

All these values are needed for the MS authentication process. These values have to be copied from the Microsoft Portal

# Starting the Webapp

### Normal Start (WIP)

```
docker compose up
```

### Verbose Version (Not Implemented)

### With additional statistic pages (Not Implemented)