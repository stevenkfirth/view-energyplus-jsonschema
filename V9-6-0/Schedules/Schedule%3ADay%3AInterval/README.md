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
                "interpolate_to_timestep": {
                    "type": "string",
                    "note": "when the interval does not match the user specified timestep a Average choice will average between the intervals request (to timestep resolution. A No choice will use the interval value at the simulation timestep without regard to if it matches the boundary or not. A Linear choice will interpolate linearly between successive values.",
                    "enum": [
                        "",
                        "Average",
                        "Linear",
                        "No"
                    ],
                    "default": "No"
                },
                "data": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "time": {
                                "type": "string",
                                "note": "\"until\" includes the time entered.",
                                "units": "hh:mm"
                            },
                            "value_until_time": {
                                "type": "number"
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
            "time": {
                "field_name": "Time",
                "field_type": "a"
            },
            "value_until_time": {
                "field_name": "Value Until Time",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "schedule_type_limits_name",
            "interpolate_to_timestep"
        ],
        "alphas": {
            "fields": [
                "name",
                "schedule_type_limits_name",
                "interpolate_to_timestep"
            ],
            "extensions": [
                "time"
            ]
        },
        "numerics": {
            "fields": [],
            "extensions": [
                "value_until_time"
            ]
        },
        "extensibles": [
            "time",
            "value_until_time"
        ],
        "extension": "data"
    },
    "type": "object",
    "memo": "A Schedule:Day:Interval contains a full day of values with specified end times for each value Currently, is set up to allow for 10 minute intervals for an entire day.",
    "min_fields": 5.0,
    "extensible_size": 2.0
}
```
