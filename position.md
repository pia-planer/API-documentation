# Positions (Employees, german term MitarbeiterInnen)

## `GET /api/v1/positions`

Get all positions of business.

### Request

```
curl GET https://app.pia-planer.ch/api/v1/positions \
   -H 'Authorization: Business YOUR_API_KEY'
```

### Response

```json
[
  {
    // see Response for /positions/:id
  }
]
```

## `GET /positions/:id`

Get a single position of business.

### Request

```
curl GET https://app.pia-planer.ch/api/v1/positions/:id \
   -H 'Authorization: Business YOUR_API_KEY'
```

#### Params

| Param | Description      |
|-------|------------------|
| `:id` | ID of a position |

### Response

```json
{
  "id": 456,
  "firstname": "Peter",
  "lastname": "Meier",
  "phone": "844040404",
  "abbrv": "PM",
  "email": "peter.meier@pia-planer.ch",
  "role": "staff",
  "business_id": 77,
  "number_of_free_wishes": -1,
  "position_group_id": 90,
  "deleted_at": null,
  "income_per_hour": 30.0,
  "team_order_no": 0,
  "ahv_no": "1234.123.12.12",
  "created_at": "2020-10-11T09:40:25.039Z",
  "updated_at": "2020-10-25T06:58:34.899Z"
}
```

#### Attributes

| Key                     | Type      | Descripition                             | Example values                            |
|-------------------------|-----------|------------------------------------------|-------------------------------------------|
| `id`                    | `integer` | Unique identifier                        |                                           |
| `firstname`             | `string`  | Firstname                                |                                           |
| `lastname`              | `string`  | Lastname                                 |                                           |
| `phone`                 | `string`  | Phone number                             |                                           |
| `abbrv`                 | `string`  | Abbreviation                             |                                           |
| `email`                 | `string`  | Email                                    |                                           |
| `role`                  | `string`  | Authorization role                       | staff, admin                              |
| `business_id`           | `integer` | ID of business                           |                                           |
| `number_of_free_wishes` | `integer` | Numbers of days to request off (monthly) | `-1`: unlimited, `others`: Number of days |
| `position_group_id`     | `integer` | ID of Team                               |                                           |
| `income_per_hour`       | `float`   | Income per hour                          |                                           |
| `team_order_no`         | `integer` | Order number within team                 |                                           |
| `ahv_no`                | `string`  | AHV number                               |                                           |
| `created_at`            | `string`  | Created at timestamp                     |                                           |
| `updated_at`            | `string`  | Last updated at timestamp                |                                           |





