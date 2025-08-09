# ShiftAssignments (german term Schichten)

In this document:

- [ShiftAssignments](#2-shift_assignments)

## ShiftAssignments

Get all _released_ shift_assignemnts of a given time range.

### Request

#### Endpoint

```
/api/v1/shift_assignments
```

#### Params

| Param   | Required | Description                               |
| ------- | -------- | ----------------------------------------- |
| `from`  | true     | Startdate in format ISO 8601 `2021-05-01` |
| `to`    | true     | Enddate in format ISO 8601 `2021-05-31`   |

#### Example

```
curl GET https://app.pia-planer.ch/api/v1/shift_assignments?from=2021-05-01&to=2021-05-31 \
   -H 'Authorization: Business YOUR_API_KEY'
```

### Response

Response is an `Array` ordered chronologically by date.

```json
[
  {
    "id": 883204427,
    "date": "2020-02-03",
    "position_id": 981563218,
    "created_at": "2023-09-18T13:24:34.594Z",
    "updated_at": "2023-09-18T13:24:34.594Z",
    "unique_abbrv": "Ns-c",
    "posted_on_market_on": "2023-09-20",
    "shifttype": {
      "id": 51464031,
      "name": "Nachtschicht",
      "starttime": "16:00",
      "endtime": "02:00",
      "responsability_id": 926244353,
      "remark": "A remark",
      "prefix": "Ns",
      "color": "#111111",
      "plannable_category_id": 157620113,
      "applowance_rules": [
        {
          "id": 54625,
          "name": "Nachtzulage",
          "calculation_method": "multiplier",
          "calculation_value": 1.2,
          "affects_hours_balance": false,
          "salary_type": {
            "name": "Nacht-Lohnart",
            "technical_name:" "na_2202"
          },
          "created_at": "2023-09-18T13:24:34.605Z",
          "updated_at": "2023-09-18T13:24:34.605Z",
        }
      ],
      "pauses": [
        {
          "id": 288754210,
          "starttime": "22:00",
          "endtime": "22:15"
        }
      ],
      "pauses_duration": 0.25,
      "pauses_duration_in_hh_mm": "00:15",
      "working_duration": 9.75,
      "working_duration_in_hh_mm": "09:45",
      "created_at": "2023-09-18T13:24:34.605Z",
      "updated_at": "2023-09-18T13:24:34.605Z"
    }
  }
]
```

## Item attributes

| Key                   | Type     | Can be null? | Description                                                             | Example values                          |
| --------------------- | -------- | ------------ | ----------------------------------------------------------------------- | --------------------------------------- |
| `id`                  | `number` | no           | ID                                                                      | `1`                                     |
| `date`                | `string` | no           | Date of the assignment in format `yyyy-mm-dd`                           | `"2020-06-06"`                          |
| `position_id`         | `number` | yes          | ID of the employee                                                      | `232`                                   |
| `created_at`          | `string` | no           | Datetime in format `yyyy-mm-dd HH:MM:SS.XXXXXXXXX +0000`                | `"2021-04-19 12:00:00.000000000 +0000"` |
| `updated_at`          | `string` | no           | Datetime in format `yyyy-mm-dd HH:MM:SS.XXXXXXXXX +0000`                | `"2021-04-19 12:00:00.000000000 +0000"` |
| `posted_on_market_on` | `string` | yes          | Date of the day when shift_assignment was posted on market `yyyy-mm-dd` | `"2020-06-22"`                          |
| `unique_abbrv`        | `string` | yes          | A unique abbreviation of the shift_assignment                           | `"NS-a"`                                |
| `shifttype`           | `object` | no           | The type of the shift_assignment                                        | (See below)                             |

## Shifttype

| Key                         | Type     | Can be null? | Description                                                       | Example values                          |
| --------------------------- | -------- | ------------ | ----------------------------------------------------------------- | --------------------------------------- |
| `id`                        | `number` | no           | ID                                                                | `1`                                     |
| `name`                      | `string` | yes          | Name                                                              | `"Nachtschicht"`                        |
| `starttime`                 | `string` | no           | Starttime of the shifttype in format `HH:MM`                      | `"17:15"`                               |
| `endtime`                   | `string` | no           | Endtime of the shifttype in format `HH:MM`                        | `"01:00"`                               |
| `remark`                    | `string` | yes          | The remark                                                        | `"Mit abrechnen"`                       |
| `prefix`                    | `string` | yes          | The abbreviation                                                  | `"NS"`                                  |
| `color`                     | `string` | yes          | The color                                                         | `"#105020"`                             |
| `allowance_rules`           | `array`  | yes          | A list of allowance_rule items, ordered by `name` alphabetically  | (See below)                             |
| `pauses`                    | `array`  | yes          | A list of Pause items                                             | (See below)                             |
| `pauses_duration`           | `number` | no           | Duration of all pauses as decimal number                          | `0.25`                                  |
| `pauses_duration_in_hh_mm`  | `string` | no           | Duration of all pauses in format `HH:MM`                          | `"00:15"`                               |
| `working_duration`          | `number` | no           | Duration of the working time as decimal number                    | `8.5`                                   |
| `working_duration_in_hh_mm` | `string` | no           | Duration of the working time in format `HH:MM`                    | `"08:30"`                               |
| `created_at`                | `string` | no           | Datetime in format `yyyy-mm-dd HH:MM:SS.XXXXXXXXX +0000`          | `"2021-04-19 12:00:00.000000000 +0000"` |
| `updated_at`                | `string` | no           | Datetime in format `yyyy-mm-dd HH:MM:SS.XXXXXXXXX +0000`          | `"2021-04-19 12:00:00.000000000 +0000"` |

##### Allowance Rule item

```json
{
  "id": 54625,
  "name": "Nachtzulage",
  "calculation_method": "multiplier",
  "calculation_value": 1.2,
  "affects_hours_balance": false,
  "salary_type": {
    "name": "Lohnart Nacht",
    "technical_name:" "na_2202"
  },
  "created_at": "2023-09-18T13:24:34.605Z",
  "updated_at": "2023-09-18T13:24:34.605Z",
}
```

| Key                     | Type     | Can be null? | Description                                                                                | Example values                          |
| ----------------------- | -------- | ------------ | ------------------------------------------------------------------------------------------ | --------------------------------------- |
| `name`                  | `string` | no           | A natural, user friendly description for the AllowanceRule                                 | `"Nachtzulage"`                         |
| `calculation_method`    | `string` | no           | The method of calculating the allowance, possible values: `multiplier`, `fixed`, `counter` | `multiplier`                            |
| `calculation_value`     | `number` | no           | The value used by the calculation_method                                                   | `1.2`                                   |
| `affects_hours_balance` | `boolean`| no           | Describes if the allowance affects the balance value                                       | `true`                                  |
| `created_at`            | `string` | no           | Datetime in format `yyyy-mm-dd HH:MM:SS.XXXXXXXXX +0000`                                   | `"2021-04-19 12:00:00.000000000 +0000"` |
| `updated_at`            | `string` | no           | Datetime in format `yyyy-mm-dd HH:MM:SS.XXXXXXXXX +0000`                                   | `"2021-04-19 12:00:00.000000000 +0000"` |
| `salary_type`           | `object` | yes          | The salary type of the allowance_rule                                                      | (See below)                             |

##### Pause item

```json
{
  "id": 288754210,
  "starttime": "22:00",
  "endtime": "22:15"
}
```

| Key         | Type     | Can be null? | Description                              | Example values |
| ----------- | -------- | ------------ | ---------------------------------------- | -------------- |
| `id`        | `number` | no           | ID                                       | `1`            |
| `starttime` | `string` | no           | Starttime of the pause in format `HH:MM` | `"18:15"`      |
| `endtime`   | `string` | no           | Endtime of the pause in format `HH:MM`   | `"18:30"`      |

##### Salary Type item

```json
{
  "name": "Nacht-Lohnart",
  "technical_name:" "na_2202"
}
```

| Key              | Type     | Can be null? | Description                                              | Example values    |
| ---------------- | -------- | ------------ | -------------------------------------------------------- | ----------------- |
| `name`           | `string` | no           | A natural, user friendly description for the salary type | `"Lohnart Nacht"` |
| `technical_name` | `string` | no           | A technical identifier for the salary type               | `"la_2022"`       |
