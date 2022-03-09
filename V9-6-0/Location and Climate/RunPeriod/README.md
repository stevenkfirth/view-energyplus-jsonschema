```
{
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
                "begin_year": {
                    "type": "number",
                    "note": "Start year of the simulation, if this field is specified it must agree with the Day of Week for Start Day If this field is blank, the year will be selected to match the weekday, which is Sunday if not specified"
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
                "end_year": {
                    "type": "number",
                    "note": "end year of simulation, if specified"
                },
                "day_of_week_for_start_day": {
                    "type": "string",
                    "note": "=[Sunday|Monday|Tuesday|Wednesday|Thursday|Friday|Saturday]; If no year is input, this field will default to Sunday If a year is input and this field is blank, the correct weekday is determined",
                    "enum": [
                        "Friday",
                        "Monday",
                        "Saturday",
                        "Sunday",
                        "Thursday",
                        "Tuesday",
                        "Wednesday"
                    ]
                },
                "use_weather_file_holidays_and_special_days": {
                    "type": "string",
                    "note": "If yes or blank, use holidays as specified on Weatherfile. If no, do not use the holidays specified on the Weatherfile. Note: You can still specify holidays/special days using the RunPeriodControl:SpecialDays object(s).",
                    "default": "Yes",
                    "enum": [
                        "",
                        "No",
                        "Yes"
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
                "apply_weekend_holiday_rule": {
                    "type": "string",
                    "note": "if yes and single day holiday falls on weekend, \"holiday\" occurs on following Monday",
                    "enum": [
                        "",
                        "No",
                        "Yes"
                    ],
                    "default": "No"
                },
                "use_weather_file_rain_indicators": {
                    "type": "string",
                    "enum": [
                        "",
                        "No",
                        "Yes"
                    ],
                    "default": "Yes"
                },
                "use_weather_file_snow_indicators": {
                    "type": "string",
                    "enum": [
                        "",
                        "No",
                        "Yes"
                    ],
                    "default": "Yes"
                },
                "treat_weather_as_actual": {
                    "type": "string",
                    "enum": [
                        "",
                        "No",
                        "Yes"
                    ],
                    "default": "No"
                },
                "first_hour_interpolation_starting_values": {
                    "type": "string",
                    "note": "When the weather data timestep is longer than the simulation timestep, weather data is interpolated. For the first hour of the simulation, this field specifies which values from the first day of the run period to use as the interpolation starting point. This same interpolation will be used for repeated warmup days.",
                    "enum": [
                        "",
                        "Hour1",
                        "Hour24"
                    ],
                    "default": "Hour24"
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
        "is_required": true,
        "reference": [
            "RunPeriodsAndDesignDays"
        ],
        "note": "descriptive name (used in reporting mainly) Cannot be not blank and must be unique"
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
            "begin_year": {
                "field_name": "Begin Year",
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
            "end_year": {
                "field_name": "End Year",
                "field_type": "n"
            },
            "day_of_week_for_start_day": {
                "field_name": "Day of Week for Start Day",
                "field_type": "a"
            },
            "use_weather_file_holidays_and_special_days": {
                "field_name": "Use Weather File Holidays and Special Days",
                "field_type": "a"
            },
            "use_weather_file_daylight_saving_period": {
                "field_name": "Use Weather File Daylight Saving Period",
                "field_type": "a"
            },
            "apply_weekend_holiday_rule": {
                "field_name": "Apply Weekend Holiday Rule",
                "field_type": "a"
            },
            "use_weather_file_rain_indicators": {
                "field_name": "Use Weather File Rain Indicators",
                "field_type": "a"
            },
            "use_weather_file_snow_indicators": {
                "field_name": "Use Weather File Snow Indicators",
                "field_type": "a"
            },
            "treat_weather_as_actual": {
                "field_name": "Treat Weather as Actual",
                "field_type": "a"
            },
            "first_hour_interpolation_starting_values": {
                "field_name": "First Hour Interpolation Starting Values",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "begin_month",
            "begin_day_of_month",
            "begin_year",
            "end_month",
            "end_day_of_month",
            "end_year",
            "day_of_week_for_start_day",
            "use_weather_file_holidays_and_special_days",
            "use_weather_file_daylight_saving_period",
            "apply_weekend_holiday_rule",
            "use_weather_file_rain_indicators",
            "use_weather_file_snow_indicators",
            "treat_weather_as_actual",
            "first_hour_interpolation_starting_values"
        ],
        "alphas": {
            "fields": [
                "name",
                "day_of_week_for_start_day",
                "use_weather_file_holidays_and_special_days",
                "use_weather_file_daylight_saving_period",
                "apply_weekend_holiday_rule",
                "use_weather_file_rain_indicators",
                "use_weather_file_snow_indicators",
                "treat_weather_as_actual",
                "first_hour_interpolation_starting_values"
            ]
        },
        "numerics": {
            "fields": [
                "begin_month",
                "begin_day_of_month",
                "begin_year",
                "end_month",
                "end_day_of_month",
                "end_year"
            ]
        }
    },
    "type": "object",
    "memo": "Specify a range of dates and other parameters for a simulation. Multiple run periods may be input, but they may not overlap.",
    "min_fields": 7.0
}
```
