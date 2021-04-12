## pia API Documentation

- [Entities](#entities)

- [Authentication](#authentication)


### Overview

- Data is sent as JSON (Content-Type: application/json) to pia
- The requests have to be authenticated with a token from a pia business

### Entities

- [Business](business.md)

- [Positions](positions/positions.md)


### Authentication

You need an API-Token of your pia business to access the API. You can find it on the main page of your business in the section "Integration in Umsysteme". 

Example usage:

```
curl GET https://app.pia-planer.ch/api/v1/positions.json \
   -H 'Authorization: Business YOUR_API_KEY'
```
