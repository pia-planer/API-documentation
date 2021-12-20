# Positions (Employees, german term MitarbeiterInnen)

In this document:

- [All positions](#all-positions)
- [Single position](#single-position)

Also Related:

- [Positions/Working Hours](positions/working_hours.md)

## All positions

Get **all** positions of a business.

### Request

#### Endpoint

```
/api/v1/positions
```

#### Params

(none)

#### Example

```shell
curl GET https://app.pia-planer.ch/api/v1/positions \
   -H 'Authorization: Business YOUR_API_KEY'
```

### Response

Response is an `Array` of positions, ordered by `lastname` alphabetically.

```json
[
  {
    // see Response for /positions/:id
  }
]
```

## Single Position

Get a **single** position of business.

### Request

#### Endpoint

```
/api/v1/positions/:id
```

#### Params

| Param | Description      |
| ----- | ---------------- |
| `:id` | ID of a position |

#### Example

```shell
curl GET https://app.pia-planer.ch/api/v1/positions/:id \
   -H 'Authorization: Business YOUR_API_KEY'
```

### Response

Response is an `Object`.

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
  "external_id": "PN_123456",
  "created_at": "2020-10-11T09:40:25.039Z",
  "updated_at": "2020-10-25T06:58:34.899Z"
}
```

#### Attributes

| Key                     | JSON Type | Can be null? | Descripition                             | Example values                            |
| ----------------------- | --------- | ------------ | ---------------------------------------- | ----------------------------------------- |
| `id`                    | `number`  | no           | Unique identifier                        |                                           |
| `firstname`             | `string`  | no           | Firstname                                |                                           |
| `lastname`              | `string`  | no           | Lastname                                 |                                           |
| `phone`                 | `string`  | yes          | Phone number                             |                                           |
| `abbrv`                 | `string`  | yes          | Abbreviation                             |                                           |
| `email`                 | `string`  | no           | Email                                    |                                           |
| `role`                  | `string`  | no           | Authorization role                       | staff, admin                              |
| `business_id`           | `number`  | no           | ID of business                           |                                           |
| `number_of_free_wishes` | `number`  | no           | Numbers of days to request off (monthly) | `-1`: unlimited, `others`: Number of days |
| `position_group_id`     | `number`  | yes          | ID of Team                               |                                           |
| `income_per_hour`       | `number`  | no           | Income per hour                          |                                           |
| `team_order_no`         | `number`  | no           | Order number within team                 |                                           |
| `ahv_no`                | `string`  | yes          | AHV number                               |                                           |
| `external_id`           | `string`  | yes          | Id for identification in other systems   |                                           |
| `created_at`            | `string`  | no           | Created at timestamp                     |                                           |
| `updated_at`            | `string`  | no           | Last updated at timestamp                |                                           |
