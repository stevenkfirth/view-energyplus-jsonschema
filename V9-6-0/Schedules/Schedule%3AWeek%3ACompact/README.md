```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "data": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "daytype_list": {
                                "type": "string",
                                "note": "\"For\" is an optional prefix/start of the For fields. Choices can be combined on single line if separated by spaces. i.e. \"Holiday Weekends\" Should have a space after For, if it is included. i.e. \"For Alldays\""
                            },
                            "schedule_day_name": {
                                "type": "string",
                                "data_type": "object_list",
                                "object_list": [
                                    "DayScheduleNames"
                                ]
                            }
                        },
                        "type": "object",
                        "required": [
                            "daytype_list",
                            "schedule_day_name"
                        ]
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
            "WeekScheduleNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "daytype_list": {
                "field_name": "DayType List",
                "field_type": "a"
            },
            "schedule_day_name": {
                "field_name": "Schedule:Day Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name"
        ],
        "alphas": {
            "fields": [
                "name"
            ],
            "extensions": [
                "daytype_list",
                "schedule_day_name"
            ]
        },
        "numerics": {
            "fields": []
        },
        "extensibles": [
            "daytype_list",
            "schedule_day_name"
        ],
        "extension": "data"
    },
    "type": "object",
    "memo": "Compact definition for Schedule:Day:List",
    "min_fields": 3.0,
    "extensible_size": 2.0
}
```
