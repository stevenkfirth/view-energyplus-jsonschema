```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "start_date": {
                    "type": "string"
                },
                "end_date": {
                    "type": "string",
                    "note": "Dates can be several formats: <number>/<number>  (month/day) <number> <Month> <Month> <number> <Nth> <Weekday> in <Month) Last <WeekDay> in <Month> <Month> can be January, February, March, April, May, June, July, August, September, October, November, December Months can be the first 3 letters of the month <Weekday> can be Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday <Nth> can be 1 or 1st, 2 or 2nd, etc. up to 5(?)"
                }
            },
            "required": [
                "start_date",
                "end_date"
            ]
        }
    },
    "group": "Location and Climate",
    "legacy_idd": {
        "field_info": {
            "start_date": {
                "field_name": "Start Date",
                "field_type": "a"
            },
            "end_date": {
                "field_name": "End Date",
                "field_type": "a"
            }
        },
        "fields": [
            "start_date",
            "end_date"
        ],
        "alphas": {
            "fields": [
                "start_date",
                "end_date"
            ]
        },
        "numerics": {
            "fields": []
        }
    },
    "type": "object",
    "maxProperties": 1,
    "memo": "This object sets up the daylight saving time period for any RunPeriod. Ignores any daylight saving time period on the weather file and uses this definition. These are not used with SizingPeriod:DesignDay objects. Use with SizingPeriod:WeatherFileDays object can be controlled in that object.",
    "min_fields": 2.0
}
```
