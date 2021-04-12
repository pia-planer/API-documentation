# Working Hours

## `GET /api/v1/positions/:position_id/working_hours`

Get all Working Hours of given Position.

### Request

```
curl GET https://app.pia-planer.ch/api/v1/positions/:position_id/working_hours \
   -H 'Authorization: Business YOUR_API_KEY'
```

#### Params

| Param          | Description                                        |
|----------------|----------------------------------------------------|
| `:position_id` | ID of a position (see [Positions](../positions.md)) |

### Response

Response is ordered by `date`, `startetime`.

```json
[
  {
    "date": "2020-02-01",
    "starttime": "10:15",
    "endtime": "12:45"
  },
  {
    "date": "2020-02-02",
    "starttime": "15:30",
    "endtime": "18:40"
  },
  {
    "date": "2020-08-25",
    "starttime": "12:00",
    "endtime": "19:00"
  }
]
```

#### Attributes

| Key              | Type     | Description                 | Example values |
|------------------|----------|-----------------------------|----------------|
| `date`           | `string` | Date in format `yyyy-mm-dd` | `2020-02-02`   |
| `starttime`      | `string` | Time in format `HH:MI`      | `21:45`        |
| `endtime`        | `string` | Date in format `HH:MI`      | `21:45`        |
