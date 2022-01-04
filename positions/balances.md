# Balances

In this document:

- [Balance Values](#balance-values)

Related

- [Single position](../positions.md#single-position)

## Balance Values

Get hourly balance and vaccation balance for a given date.
If no date is given, it returns the balance of today.

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
[
  {
    "effective_target_hours": "560.25",
    "sum_of_working_hours": "555.00",
    "hourly_balance": "-5.25",
    "vacations_in_year": "200.00",
    "planned_vacations_in_year": "180.5",
    "remaining_vacations": "19.5"
  }
]
```

#### Item attributes

| Key                         | Type     | Can be null? | Description                                            | Example values |
| --------------------------- | -------- | ------------ | ------------------------------------------------------ | -------------- |
| `effective_target_hours`    | `number` | no           | Effective target hours as decimal number               | `560.25`       |
| `sum_of_working_hours`      | `number` | no           | Sum of working hours as decima number                  | `555.00`       |
| `hourly_balance`            | `number` | no           | Difference of working hours and effective target hours | `-5.25`        |
| `vacations_in_year`         | `number` | no           | Vacations in year in hours as decimal number           | `200.00`       |
| `planned_vacations_in_year` | `number` | no           | Planned vacations in year as decimal number            | `180.5`        |
| `remaining_vacations`       | `number` | no           | Difference of planned vacations and vacations in year  | `19.5`         |
