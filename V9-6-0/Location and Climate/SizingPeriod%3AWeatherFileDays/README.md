```
{
    "SizingPeriod:WeatherFileDays": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "begin_month": {
                        "type": "number",
                        "minimum": 1.0,
                        "maximum": 12.0
                    },
                    "begin_day_of_month": {
                        "type": "number",
                        "minimum": 1.0,
                        "maximum": 31.0
                    },
                    "end_month": {
                        "type": "number",
                        "minimum": 1.0,
                        "maximum": 12.0
                    },
                    "end_day_of_month": {
                        "type": "number",
                        "minimum": 1.0,
                        "maximum": 31.0
                    },
                    "day_of_week_for_start_day": {
                        "type": "string",
                        "note": "=[|Sunday|Monday|Tuesday|Wednesday|Thursday|Friday|Saturday|SummerDesignDay|WinterDesignDay| |CustomDay1|CustomDay2]; if you use SummerDesignDay or WinterDesignDay or the CustomDays then this will apply to the whole period; other days (i.e., Monday) will signify a start day and normal sequence of subsequent days",
                        "default": "Monday",
                        "enum": [
                            "",
                            "CustomDay1",
                            "CustomDay2",
                            "Friday",
                            "Monday",
                            "Saturday",
                            "SummerDesignDay",
                            "Sunday",
                            "Thursday",
                            "Tuesday",
                            "Wednesday",
                            "WinterDesignDay"
                        ]
                    },
                    "use_weather_file_daylight_saving_period": {
                        "type": "string",
                        "note": "If yes or blank, use daylight saving period as specified on Weatherfile. If no, do not use the daylight saving period as specified on the Weatherfile.",
                        "default": "Yes",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ]
                    },
                    "use_weather_file_rain_and_snow_indicators": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "Yes"
                    }
                },
                "required": [
                    "begin_month",
                    "begin_day_of_month",
                    "end_month",
                    "end_day_of_month"
                ]
            }
        },
        "group": "Location and Climate",
        "name": {
            "type": "string",
            "reference": [
                "RunPeriodsAndDesignDays"
            ],
            "is_required": true,
            "note": "user supplied name for reporting"
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "begin_month": {
                    "field_name": "Begin Month",
                    "field_type": "n"
                },
                "begin_day_of_month": {
                    "field_name": "Begin Day of Month",
                    "field_type": "n"
                },
                "end_month": {
                    "field_name": "End Month",
                    "field_type": "n"
                },
                "end_day_of_month": {
                    "field_name": "End Day of Month",
                    "field_type": "n"
                },
                "day_of_week_for_start_day": {
                    "field_name": "Day of Week for Start Day",
                    "field_type": "a"
                },
                "use_weather_file_daylight_saving_period": {
                    "field_name": "Use Weather File Daylight Saving Period",
                    "field_type": "a"
                },
                "use_weather_file_rain_and_snow_indicators": {
                    "field_name": "Use Weather File Rain and Snow Indicators",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "begin_month",
                "begin_day_of_month",
                "end_month",
                "end_day_of_month",
                "day_of_week_for_start_day",
                "use_weather_file_daylight_saving_period",
                "use_weather_file_rain_and_snow_indicators"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "day_of_week_for_start_day",
                    "use_weather_file_daylight_saving_period",
                    "use_weather_file_rain_and_snow_indicators"
                ]
            },
            "numerics": {
                "fields": [
                    "begin_month",
                    "begin_day_of_month",
                    "end_month",
                    "end_day_of_month"
                ]
            }
        },
        "type": "object",
        "memo": "Use a weather file period for design sizing calculations."
    }
}
```
