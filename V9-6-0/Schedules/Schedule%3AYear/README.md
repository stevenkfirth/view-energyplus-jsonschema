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
                "schedule_weeks": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "schedule_week_name": {
                                "type": "string",
                                "data_type": "object_list",
                                "object_list": [
                                    "WeekScheduleNames"
                                ]
                            },
                            "start_month": {
                                "type": "number",
                                "minimum": 1.0,
                                "maximum": 12.0
                            },
                            "start_day": {
                                "type": "number",
                                "minimum": 1.0,
                                "maximum": 31.0
                            },
                            "end_month": {
                                "type": "number",
                                "minimum": 1.0,
                                "maximum": 12.0
                            },
                            "end_day": {
                                "type": "number",
                                "minimum": 1.0,
                                "maximum": 31.0
                            }
                        },
                        "type": "object",
                        "required": [
                            "end_day",
                            "end_month",
                            "schedule_week_name",
                            "start_day",
                            "start_month"
                        ]
                    },
                    "minItems": 1,
                    "maxItems": 53
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
            "schedule_week_name": {
                "field_name": "Schedule:Week Name",
                "field_type": "a"
            },
            "start_month": {
                "field_name": "Start Month",
                "field_type": "n"
            },
            "start_day": {
                "field_name": "Start Day",
                "field_type": "n"
            },
            "end_month": {
                "field_name": "End Month",
                "field_type": "n"
            },
            "end_day": {
                "field_name": "End Day",
                "field_type": "n"
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
                "schedule_week_name"
            ]
        },
        "numerics": {
            "fields": [],
            "extensions": [
                "start_month",
                "start_day",
                "end_month",
                "end_day"
            ]
        },
        "extensibles": [
            "schedule_week_name",
            "start_month",
            "start_day",
            "end_month",
            "end_day"
        ],
        "extension": "schedule_weeks"
    },
    "type": "object",
    "memo": "A Schedule:Year contains from 1 to 52 week schedules",
    "min_fields": 7.0,
    "extensible_size": 5.0
}
```
