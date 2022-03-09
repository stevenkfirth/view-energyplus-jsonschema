```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "schedule_type_limits_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleTypeLimitsNames"
                    ]
                },
                "hourly_value": {
                    "type": "number",
                    "default": 0.0
                }
            }
        }
    },
    "group": "Schedules",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "ScheduleNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "schedule_type_limits_name": {
                "field_name": "Schedule Type Limits Name",
                "field_type": "a"
            },
            "hourly_value": {
                "field_name": "Hourly Value",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "schedule_type_limits_name",
            "hourly_value"
        ],
        "alphas": {
            "fields": [
                "name",
                "schedule_type_limits_name"
            ]
        },
        "numerics": {
            "fields": [
                "hourly_value"
            ]
        }
    },
    "type": "object",
    "memo": "Constant hourly value for entire year.",
    "format": "singleLine"
}
```
