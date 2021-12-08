# Working Hours

In this document:

- [All Working Hours](#all-working-Hours)

Related

- [Single position](../positions.md#single-position)
- [Working Hour Labels](working_hours/labels.md)

## All Working Hours

Get all Working Hours of given Position.

### Request

#### Endpoint

```
/api/v1/positions/:position_id/working_hours
```

#### Params

| Param          | Description                                         |
| -------------- | --------------------------------------------------- |
| `:position_id` | ID of a position (see [Positions](../positions.md)) |
| `from`         | Startdate in format ISO 8601 `2021-05-01`           |
| `to`           | Enddate in format ISO 8601 `2021-05-31`             |

#### Example

```
curl GET https://app.pia-planer.ch/api/v1/positions/:position_id/working_hours?from=2021-05-01&to=2021-05-31 \
   -H 'Authorization: Business YOUR_API_KEY'
```

### Response

Response is an `Array` of Working Hours ordered by `date` chronologically, `starttime` chronologically.

```json
[
  {
    "starttime": "2020-02-01T10:04:00+01:00",
    "endtime": "2020-02-01T19:04:00+01:00",
    "pauses_duration": "1.25",
    "pauses_duration_in_hh_mm": "01:15",
    "working_duration": "7.75",
    "working_duration_in_hh_mm": "07:45",
    "remarks": "Started earlier",
    "labels": "[\"Mittagessen, 12 CHF\", \"Nachtzulage\"]",
    "confirmed": false
  }
]
```

#### Item attributes

| Key                         | Type      | Can be null? | Description                                                | Example values               |
| --------------------------- | --------- | ------------ | ---------------------------------------------------------- | ---------------------------- |
| `starttime`                 | `string`  | no           | Time in format `YYYY-MM-DDThh:mm:ss±hh:mm`                 | `2020-02-01T10:04:00+01:00`  |
| `endtime`                   | `string`  | no           | Time in format `YYYY-MM-DDThh:mm:ss±hh:mm`                 | `2020-02-01T18:04:00+01:00`  |
| `pauses_duration`           | `number`  | no           | Pauses duration as decimal number                          | `1.25`                       |
| `pauses_duration_in_hh_mm`  | `string`  | no           | Pauses duration in format `HH:MM`                          | `"01:15"`                    |
| `working_duration`          | `number`  | no           | Working hour duration excluding pauses as a decimal number | `7.75`                       |
| `working_duration_in_hh_mm` | `string`  | no           | Working hour duration excluding pauses in format `HH:MM`   | `"07:45"`                    |
| `remarks`                   | `string`  | yes          | A comment concerning the working_hour                      | `Started earlier`            |
| `lables`                    | `array`   | yes          | A json array containing labels as strings                  | `'["String a", "String b"]'` |
| `confirmed`                 | `boolean` | no           | Indicates if working_hour is confirmed                     | `true`                       |
