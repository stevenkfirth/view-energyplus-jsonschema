```
{
    "Schedule:Compact": {
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
                    "data": {
                        "type": "array",
                        "items": {
                            "properties": {
                                "field": {
                                    "anyOf": [
                                        {
                                            "type": "number"
                                        },
                                        {
                                            "type": "string"
                                        }
                                    ]
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
                "field": {
                    "field_name": "Field",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "schedule_type_limits_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "schedule_type_limits_name"
                ],
                "extensions": [
                    "field"
                ]
            },
            "numerics": {
                "fields": []
            },
            "extensibles": [
                "field"
            ],
            "extension": "data"
        },
        "type": "object",
        "memo": "Irregular object. Does not follow the usual definition for fields. Fields A3... are: Through: Date For: Applicable days (ref: Schedule:Week:Compact) Interpolate: Average/Linear/No (ref: Schedule:Day:Interval) -- optional, if not used will be \"No\" Until: <Time> (ref: Schedule:Day:Interval) <numeric value> words \"Through\",\"For\",\"Interpolate\",\"Until\" must be included.",
        "min_fields": 5.0,
        "extensible_size": 1.0,
        "format": "compactSchedule"
    }
}
```
