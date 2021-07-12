# Working Hours

In this document:

- [All Working Hours](#all-working-Hours)


Related

- [Single position](../positions.md#single-position)

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
| `from`         | Startdate in format ISO 8601 `2021-05-03`           |
| `to`           | Enddate in format ISO 8601 `2021-05-03`             |

#### Example

```
curl GET https://app.pia-planer.ch/api/v1/positions/:position_id/working_hours?from=2021-05-03 \
   -H 'Authorization: Business YOUR_API_KEY'
```

### Response

Response is an `Array` of Working Hours ordered by `date` chronologically, `starttime` chronologically.

```json
[
  {
    "date": "2020-02-01",
    "starttime": "10:15",
    "endtime": "12:45",
    "pauses_duration": "01:15",
  }
]
```

#### Item attributes

| Key              | Type     | Can be null? | Description                 | Example values |
|------------------|----------|--------------|-----------------------------|----------------|
| `date`           | `string` | yes          | Date in format `yyyy-mm-dd` | `2020-02-02`   |
| `starttime`      | `string` | yes          | Time in format `HH:MM`      | `21:45`        |
| `endtime`        | `string` | yes          | Time in format `HH:MM`      | `21:45`        |
| `pauses_duration`| `string` | no           | Duration in format `HH:MM`  | `01:15`        |
