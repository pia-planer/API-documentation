# Absences

In this document:

- [All absences](#all-absences)


Related

- [Single position](../positions/#single-position)


## All Absences

Get all Absences of given Position.

### Request

#### Endpoint

```
/api/v1/absences
```

#### Params

| Param          | Description                                         |
|----------------|-----------------------------------------------------|
| `:position_id` | ID of a position (see [Positions](../positions.md)) |

#### Example

```
curl GET https://app.pia-planer.ch/api/v1/positions/:position_id/absences \
   -H 'Authorization: Business YOUR_API_KEY'
```

### Response

Response is an `Array` of Absences ordered by `start_time` chronologically.

```json
[
  {
    "id": 1,
    "name": "Pfingsten",
    "position_id": 1,
    "business_id": 1,
    "start_time": "2020-10-11T09:40:25.039Z",
    "end_time": "2020-10-11T10:40:25.039Z",
    "created_at": "2020-10-11T09:40:25.039Z",
    "updated_at": "2020-10-11T09:40:25.039Z",
    "template_type": "weekly"
    "authored_by_id": 1,
    "deleted": "2020-10-11T09:40:25.039Z",
    "template_enddate": "2021-05-01",
    "parent_id": 2,
    "template_startdate": "2021-02-01",
    "reason": 'feast_day',
  }
]
```

#### Item attributes

| Key                  | Type     | Can be null?| Description                                                                 | Example values                       |
|----------------------|----------|-------------|-----------------------------------------------------------------------------|--------------------------------------|
| `id`                 | `number` | no         | ID                                                                          |   `1`                                |
| `name`               | `string`  | no         | Name                                                                        | `Pfingsten`                          |
| `start_time`         | `string`  | no         | Datetime in format `yyyy-mm-dd HH:MM:SS.XXXXXXXXX +0000`                    | `2021-04-19 12:00:00.000000000 +0000`|
| `end_time`           | `string`  | no         | Datetime in format `yyyy-mm-dd HH:MM:SS.XXXXXXXXX +0000`                    | `2021-04-19 12:00:00.000000000 +0000`|
| `created_at`         | `string`  | no         | Datetime in format `yyyy-mm-dd HH:MM:SS.XXXXXXXXX +0000`                    | `2021-04-19 12:00:00.000000000 +0000`|
| `updated_at`         | `string`  | no         | Datetime in format `yyyy-mm-dd HH:MM:SS.XXXXXXXXX +0000`                    | `2021-04-19 12:00:00.000000000 +0000`|
| `template_type`      | `string`  | yes        | For recurring absences, possible values: `weekly`, `biweekly`               | `weekly`                             |
| `authored_by_id`     | `string`  | no         | Created/Updated by user                                                     | `1`                                  |
| `deleted`            | `boolean` | yes        | Shows if a recurring absence is deleted in a specific week                  | `true`                               |
| `template_enddate`   | `string`  | no         | Enddate of a recurring absence, if it is endless the value is `2100-12-31`  | `2100-12-31`                         |
| `parent_id`          | `number` | yes        | Id of the template, if the absence is modified for a specific week          | `1`                                  |
| `template_startdate` | `string`  | yes        | Startdate of a recurring absence                                            | `2000-02-03`                         |
| `reason`             | `string`  | no         | The reason of the absence                                                   | `feast_day`                          |


