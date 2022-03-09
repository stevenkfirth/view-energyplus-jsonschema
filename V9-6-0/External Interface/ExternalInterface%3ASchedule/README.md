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
                "initial_value": {
                    "type": "number",
                    "note": "Used during warm-up and system sizing."
                }
            },
            "required": [
                "initial_value"
            ]
        }
    },
    "group": "External Interface",
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
            "initial_value": {
                "field_name": "Initial Value",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "schedule_type_limits_name",
            "initial_value"
        ],
        "alphas": {
            "fields": [
                "name",
                "schedule_type_limits_name"
            ]
        },
        "numerics": {
            "fields": [
                "initial_value"
            ]
        }
    },
    "type": "object",
    "memo": "A ExternalInterface:Schedule contains only one value, which is used during the warm-up period and the system sizing.",
    "min_fields": 3.0
}
```
