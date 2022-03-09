```
{
    "RunPeriodControl:SpecialDays": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "start_date": {
                        "type": "string",
                        "note": "Dates can be several formats: <number>/<number>  (month/day) <number> <Month> <Month> <number> <Nth> <Weekday> in <Month) Last <WeekDay> in <Month> <Month> can be January, February, March, April, May, June, July, August, September, October, November, December Months can be the first 3 letters of the month <Weekday> can be Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday <Nth> can be 1 or 1st, 2 or 2nd, etc. up to 5(?)"
                    },
                    "duration": {
                        "type": "number",
                        "units": "days",
                        "minimum": 1.0,
                        "maximum": 366.0,
                        "default": 1.0
                    },
                    "special_day_type": {
                        "type": "string",
                        "note": "Special Day Type selects the schedules appropriate for each day so labeled",
                        "enum": [
                            "",
                            "CustomDay1",
                            "CustomDay2",
                            "Holiday",
                            "SummerDesignDay",
                            "WinterDesignDay"
                        ],
                        "default": "Holiday"
                    }
                },
                "required": [
                    "start_date"
                ]
            }
        },
        "group": "Location and Climate",
        "name": {
            "type": "string",
            "is_required": true
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "start_date": {
                    "field_name": "Start Date",
                    "field_type": "a"
                },
                "duration": {
                    "field_name": "Duration",
                    "field_type": "n"
                },
                "special_day_type": {
                    "field_name": "Special Day Type",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "start_date",
                "duration",
                "special_day_type"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "start_date",
                    "special_day_type"
                ]
            },
            "numerics": {
                "fields": [
                    "duration"
                ]
            }
        },
        "type": "object",
        "memo": "This object sets up holidays/special days to be used during weather file run periods. (These are not used with SizingPeriod:* objects.) Depending on the value in the run period, days on the weather file may also be used. However, the weather file specification will take precedence over any specification shown here. (No error message on duplicate days or overlapping days).",
        "min_fields": 4.0
    }
}
```
