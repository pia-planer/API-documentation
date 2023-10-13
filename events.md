# Events

In this document:

- [Events](#2-events)

## Events

Get all events of a time range.

### Request

#### Endpoint

```
/api/v1/events
```

#### Params

| Param  | Description                               |
| ------ | ----------------------------------------- |
| `from` | Startdate in format ISO 8601 `2021-05-01` |
| `to`   | Enddate in format ISO 8601 `2021-05-31`   |

#### Example

```
curl GET https://app.pia-planer.ch/api/v1/events?from=2021-05-01&to=2021-05-31 \
   -H 'Authorization: Business YOUR_API_KEY'
```

### Response

Response is an `Array` ordered chronologically by startdate.

```json
[
  {
    "id": "2456",
    "name": "Konzert",
    "startdate": "2020-06-22",
    "enddate": "2020-06-22",
    "description": "First concert after corona",
    "created_at": "2023-09-16T04:59:08.845Z",
    "updated_at": "2023-09-16T04:59:08.845Z",
    "starttime_in_hh_mm": "20:00",
    "endtime_in_hh_mm": "22:00"
  }
]
```

## Attributes

| Key                  | Type     | Can be null? | Description                                              | Example values                          |
| -------------------- | -------- | ------------ | -------------------------------------------------------- | --------------------------------------- |
| `id`                 | `number` | no           | ID                                                       | `1`                                     |
| `name`               | `string` | no           | Event name                                               | `"Konzert"`                             |
| `startdate`          | `string` | no           | Begin as date in format `yyyy-mm-dd`                     | `"2020-06-22"`                          |
| `enddate`            | `string` | no           | End as date in format `yyyy-mm-dd`                       | `"2020-06-22"`                          |
| `description`        | `string` | yes          | A description of the event                               | `"Mit Eintritt"`                        |
| `created_at`         | `string` | no           | Datetime in format `yyyy-mm-dd HH:MM:SS.XXXXXXXXX +0000` | `"2021-04-19 12:00:00.000000000 +0000"` |
| `updated_at`         | `string` | no           | Datetime in format `yyyy-mm-dd HH:MM:SS.XXXXXXXXX +0000` | `"2021-04-19 12:00:00.000000000 +0000"` |
| `starttime_in_hh_mm` | `string` | yes          | Starttime in format `HH:MM`                              | `"20:00"`                               |
| `endtime_in_hh_mm`   | `string` | yes          | Endtime in format `HH:MM`                                | `"22:30"`                               |
