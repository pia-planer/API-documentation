# Working Hour Labels

In this document:

- [All labels of given working hour](#all-working-Hours)

Related

- [Working hours](../working_hours.md)

## All labels of given working hour

Get all labels of given working hour.

### Request

#### Endpoint

```
/api/v1/positions/:position_id/working_hours/:working_hour_id/labels
```

#### Params

| Param              | Description                                         |
|--------------------|-----------------------------------------------------|
| `:position_id`     | ID of a position (see [Positions](../../positions.md)) |
| `:working_hour_id` | ID of a working hour (see [Working hours](../working_hours.md)) |

#### Example

```
curl GET https://app.pia-planer.ch/api/v1/positions/:position_id/working_hours/:working_hour_id/labels \
   -H 'Authorization: Business YOUR_API_KEY'
```

### Response

Response is an `Array` of Working Hour Labels ordered by `technical_name` and `name` alphabetically.

**Note**: A label may appear twice or more.

```json
[
  {
    "name": "Lunch, CHF 13",
    "technical_name": "lunch"
  }
]
```

#### Item attributes

| Key              | Type     | Can be null? | Description                                       | Example values |
|------------------|----------|--------------|---------------------------------------------------|----------------|
| `name`           | `string` | yes          | A natural, user friendly description of the label | `Lunch, CHF`   |
| `technical_name` | `string` | yes          | A technical identifier of the label               | `lunch`        |
