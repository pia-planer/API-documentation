# Working Hours

In this document:

- [All Working Hours](#all-working-Hours)


Related

- [Single position](../positions/#single-position)


## All Working Hours

Get all Working Hours of given Position.

### Request

#### Endpoint

```
/api/v1/positions
```

#### Params

| Param          | Description                                         |
|----------------|-----------------------------------------------------|
| `:position_id` | ID of a position (see [Positions](../positions.md)) |

#### Example

```
curl GET https://app.pia-planer.ch/api/v1/positions/:position_id/working_hours \
   -H 'Authorization: Business YOUR_API_KEY'
```

### Response

Response is an `Array` of Working Hours ordered by `date` chronologically, `startetime` chronologically.

```json
[
  {
    "date": "2020-02-01",
    "starttime": "10:15",
    "endtime": "12:45"
  }
]
```

#### Item attributes

| Key              | Type     | null? | Description                 | Example values |
|------------------|----------|-------|-----------------------------|----------------|
| `date`           | `string` | false | Date in format `yyyy-mm-dd` | `2020-02-02`   |
| `starttime`      | `string` | false | Time in format `HH:MM`      | `21:45`        |
| `endtime`        | `string` | false | Time in format `HH:MM`      | `21:45`        |
