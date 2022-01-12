# Balances

In this document:

- [Balance Values](#balance-values)

Related

- [Single position](../positions.md#single-position)

## Balance Values

Get hourly balance and vaccation balance for a given date.

All working hours attributes (target_working_hours, actual_working_hours and working_hours_balance)
are returned from the beginning of the year until the given input date.

All vacation attributes (total_vacation_hours_in_year, planned_vacation_hours_in_year, remaining_vacation_hours_in_year) are returned from the entire year.

### Request

#### Endpoint

```
/api/v1/positions/:position_id/balances
```

#### Params

| Param          | Description                                         |
| -------------- | --------------------------------------------------- |
| `:position_id` | ID of a position (see [Positions](../positions.md)) |
| `date`         | Date in format ISO 8601 `2021-05-31`                |

#### Example

```
curl GET https://app.pia-planer.ch/api/v1/positions/:position_id/balances?date=2021-05-31 \
   -H 'Authorization: Business YOUR_API_KEY'
```

### Response

Response is an `Object`.

```json
{
  "target_working_hours": 560.25,
  "actual_working_hours": 555.0,
  "working_hours_balance": -5.25,
  "total_vacation_hours_in_year": 200.0,
  "planned_vacation_hours_in_year": 180.5,
  "remaining_vacation_hours_in_year": 19.5
}
```

#### Item attributes

| Key                                | Type     | Can be null? | Description                                                    | Example values |
| ---------------------------------- | -------- | ------------ | -------------------------------------------------------------- | -------------- |
| `target_working_hours`             | `number` | no           | Target working hours as decimal number                         | `560.25`       |
| `actual_working_hours`             | `number` | no           | Actual working hours as decima number                          | `555.00`       |
| `working_hours_balance`            | `number` | no           | Difference of target and actual working hours                  | `-5.25`        |
| `total_vacation_hours_in_year`     | `number` | no           | Total vacation hours in year as decimal number             | `200.00`       |
| `planned_vacation_hours_in_year`   | `number` | no           | Planned vacations in year in hours as decimal number           | `180.5`        |
| `remaining_vacation_hours_in_year` | `number` | no           | Difference of planned vacations and vacations in year in hours | `19.5`         |
