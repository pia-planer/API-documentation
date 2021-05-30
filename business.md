# Business

In this document:

- [Business](#2-business)

Also Related:

- [Positions](positions.md)

## Business

Get details about own business.

### Request

#### Endpoint

```
/api/v1/business
```

#### Params

(none)

#### Example

```
curl GET https://app.pia-planer.ch/api/v1/business \
   -H 'Authorization: Business YOUR_API_KEY'
```

### Response

Response is an `Object`.

```json
{
  "name": "Pia",
  "email": "info@pia-planer.ch",
  "street": "Bahnhofstrasse",
  "plz": "8000",
  "city": "Zurich"
}
```

## Attributes

| Key              | Type     | Can be null? | Description          | Example values       |
|------------------|----------|--------------|----------------------|----------------------|
| `name`           | `string` | no           | Business name        |                      |
| `email`          | `string` | no           | Business email       |                      |
| `street`         | `string` | yes          | Street               |                      |
| `plz`            | `string` | yes          | ZIP Code             |                      |
| `city`           | `string` | yes          | City                 |                      |
