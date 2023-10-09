# Absences

In this document:

- [All absences](#all-absences)

Related

- [Single position](../positions.md#single-position)

## All Absences

Get all Absences of given Position.

### Request

#### Endpoint

```
/api/v1/positions/:position_id/absences
```

#### Params

| Param          | Description                                         |
| -------------- | --------------------------------------------------- |
| `:position_id` | ID of a position (see [Positions](../positions.md)) |
| `from`         | Startdate in format ISO 8601 `2021-05-01`           |
| `to`           | Enddate in format ISO 8601 `2021-05-31`             |

#### Example

```
curl GET https://app.pia-planer.ch/api/v1/positions/:position_id/absences?from=2021-05-01&to=2021-05-31 \
   -H 'Authorization: Business YOUR_API_KEY'
```

### Response

Response is an `Array` of Absences ordered by `start_time` chronologically.

```json
[
  {
    "id": 1,
    "name": "Pfingsten",
    "start_time": "2020-10-11T09:40:25.039Z",
    "end_time": "2020-10-11T10:40:25.039Z",
    "created_at": "2020-10-11T09:40:25.039Z",
    "updated_at": "2020-10-11T09:40:25.039Z",
    "authored_by_admin": true,
    "reason": "feast_day",
    "target_hours_multiplier": 0.5
  }
]
```

#### Item attributes

| Key                       | Type      | Can be null? | Description                                              | Example values                          |
| ------------------------- | --------- | ------------ | -------------------------------------------------------- | --------------------------------------- |
| `id`                      | `number`  | no           | ID                                                       | `1`                                     |
| `name`                    | `string`  | no           | Name                                                     | `"Pfingsten"`                           |
| `start_time`              | `string`  | no           | Datetime in format `yyyy-mm-dd HH:MM:SS.XXXXXXXXX +0000` | `"2021-04-19 12:00:00.000000000 +0000"` |
| `end_time`                | `string`  | no           | Datetime in format `yyyy-mm-dd HH:MM:SS.XXXXXXXXX +0000` | `"2021-04-19 12:00:00.000000000 +0000"` |
| `created_at`              | `string`  | no           | Datetime in format `yyyy-mm-dd HH:MM:SS.XXXXXXXXX +0000` | `"2021-04-19 12:00:00.000000000 +0000"` |
| `updated_at`              | `string`  | no           | Datetime in format `yyyy-mm-dd HH:MM:SS.XXXXXXXXX +0000` | `"2021-04-19 12:00:00.000000000 +0000"` |
| `authored_by_admin`       | `boolean` | no           | Flag if authored by admin                                | `1`                                     |
| `reason`                  | `string`  | no           | The reason of the absence                                | `"feast_day"`                           |
| `target_hours_multiplier` | `number`  | no           | A value between 0 and 1                                  | `1`                                     |

#### Values of the attribute `reason`

- accident
- accident_at_work
- sickness
- maternity_leave
- national_service
- education
- feast_day
- holiday
- shorttime_work
- other
