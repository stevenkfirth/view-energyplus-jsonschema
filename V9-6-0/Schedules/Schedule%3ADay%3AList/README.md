```
{
    "Schedule:Day:List": {
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
                    "interpolate_to_timestep": {
                        "type": "string",
                        "note": "when the interval does not match the user specified timestep a \"Average\" choice will average between the intervals request (to timestep resolution. A \"No\" choice will use the interval value at the simulation timestep without regard to if it matches the boundary or not. A \"Linear\" choice will interpolate linearly between successive values.",
                        "enum": [
                            "",
                            "Average",
                            "Linear",
                            "No"
                        ],
                        "default": "No"
                    },
                    "minutes_per_item": {
                        "type": "number",
                        "note": "Must be evenly divisible into 60",
                        "minimum": 1.0,
                        "maximum": 60.0
                    },
                    "extensions": {
                        "type": "array",
                        "items": {
                            "properties": {
                                "value": {
                                    "type": "number",
                                    "default": 0.0
                                }
                            },
                            "type": "object"
                        }
                    }
                }
            }
        },
        "group": "Schedules",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "DayScheduleNames"
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
                "interpolate_to_timestep": {
                    "field_name": "Interpolate to Timestep",
                    "field_type": "a"
                },
                "minutes_per_item": {
                    "field_name": "Minutes per Item",
                    "field_type": "n"
                },
                "value": {
                    "field_name": "Value",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "schedule_type_limits_name",
                "interpolate_to_timestep",
                "minutes_per_item"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "schedule_type_limits_name",
                    "interpolate_to_timestep"
                ]
            },
            "numerics": {
                "fields": [
                    "minutes_per_item"
                ],
                "extensions": [
                    "value"
                ]
            },
            "extensibles": [
                "value"
            ],
            "extension": "extensions"
        },
        "type": "object",
        "memo": "Schedule:Day:List will allow the user to list 24 hours worth of values, which can be sub-hourly in nature.",
        "min_fields": 5.0,
        "extensible_size": 1.0
    }
}
```
