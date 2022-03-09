```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "sunday_schedule_day_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "DayScheduleNames"
                    ]
                },
                "monday_schedule_day_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "DayScheduleNames"
                    ]
                },
                "tuesday_schedule_day_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "DayScheduleNames"
                    ]
                },
                "wednesday_schedule_day_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "DayScheduleNames"
                    ]
                },
                "thursday_schedule_day_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "DayScheduleNames"
                    ]
                },
                "friday_schedule_day_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "DayScheduleNames"
                    ]
                },
                "saturday_schedule_day_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "DayScheduleNames"
                    ]
                },
                "holiday_schedule_day_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "DayScheduleNames"
                    ]
                },
                "summerdesignday_schedule_day_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "DayScheduleNames"
                    ]
                },
                "winterdesignday_schedule_day_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "DayScheduleNames"
                    ]
                },
                "customday1_schedule_day_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "DayScheduleNames"
                    ]
                },
                "customday2_schedule_day_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "DayScheduleNames"
                    ]
                }
            },
            "required": [
                "sunday_schedule_day_name",
                "monday_schedule_day_name",
                "tuesday_schedule_day_name",
                "wednesday_schedule_day_name",
                "thursday_schedule_day_name",
                "friday_schedule_day_name",
                "saturday_schedule_day_name",
                "holiday_schedule_day_name",
                "summerdesignday_schedule_day_name",
                "winterdesignday_schedule_day_name",
                "customday1_schedule_day_name",
                "customday2_schedule_day_name"
            ]
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
            "sunday_schedule_day_name": {
                "field_name": "Sunday Schedule:Day Name",
                "field_type": "a"
            },
            "monday_schedule_day_name": {
                "field_name": "Monday Schedule:Day Name",
                "field_type": "a"
            },
            "tuesday_schedule_day_name": {
                "field_name": "Tuesday Schedule:Day Name",
                "field_type": "a"
            },
            "wednesday_schedule_day_name": {
                "field_name": "Wednesday Schedule:Day Name",
                "field_type": "a"
            },
            "thursday_schedule_day_name": {
                "field_name": "Thursday Schedule:Day Name",
                "field_type": "a"
            },
            "friday_schedule_day_name": {
                "field_name": "Friday Schedule:Day Name",
                "field_type": "a"
            },
            "saturday_schedule_day_name": {
                "field_name": "Saturday Schedule:Day Name",
                "field_type": "a"
            },
            "holiday_schedule_day_name": {
                "field_name": "Holiday Schedule:Day Name",
                "field_type": "a"
            },
            "summerdesignday_schedule_day_name": {
                "field_name": "SummerDesignDay Schedule:Day Name",
                "field_type": "a"
            },
            "winterdesignday_schedule_day_name": {
                "field_name": "WinterDesignDay Schedule:Day Name",
                "field_type": "a"
            },
            "customday1_schedule_day_name": {
                "field_name": "CustomDay1 Schedule:Day Name",
                "field_type": "a"
            },
            "customday2_schedule_day_name": {
                "field_name": "CustomDay2 Schedule:Day Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "sunday_schedule_day_name",
            "monday_schedule_day_name",
            "tuesday_schedule_day_name",
            "wednesday_schedule_day_name",
            "thursday_schedule_day_name",
            "friday_schedule_day_name",
            "saturday_schedule_day_name",
            "holiday_schedule_day_name",
            "summerdesignday_schedule_day_name",
            "winterdesignday_schedule_day_name",
            "customday1_schedule_day_name",
            "customday2_schedule_day_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "sunday_schedule_day_name",
                "monday_schedule_day_name",
                "tuesday_schedule_day_name",
                "wednesday_schedule_day_name",
                "thursday_schedule_day_name",
                "friday_schedule_day_name",
                "saturday_schedule_day_name",
                "holiday_schedule_day_name",
                "summerdesignday_schedule_day_name",
                "winterdesignday_schedule_day_name",
                "customday1_schedule_day_name",
                "customday2_schedule_day_name"
            ]
        },
        "numerics": {
            "fields": []
        }
    },
    "type": "object",
    "memo": "A Schedule:Week:Daily contains 12 Schedule:Day:Hourly objects, one for each day type.",
    "min_fields": 13.0
}
```
