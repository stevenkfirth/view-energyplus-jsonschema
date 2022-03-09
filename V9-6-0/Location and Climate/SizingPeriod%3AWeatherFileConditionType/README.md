```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "period_selection": {
                    "type": "string",
                    "retaincase": true,
                    "note": "Following is a list of all possible types of Extreme and Typical periods that might be identified in the Weather File. Not all possible types are available for all weather files.",
                    "enum": [
                        "AutumnTypical",
                        "DrySeason",
                        "NoDrySeason",
                        "NoDrySeasonMax",
                        "NoDrySeasonMin",
                        "NoWetSeason",
                        "NoWetSeasonMax",
                        "NoWetSeasonMin",
                        "SpringTypical",
                        "SummerExtreme",
                        "SummerTypical",
                        "TropicalCold",
                        "TropicalHot",
                        "WetSeason",
                        "WinterExtreme",
                        "WinterTypical"
                    ]
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
                "period_selection"
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
        "note": "user supplied name for reporting"
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "period_selection": {
                "field_name": "Period Selection",
                "field_type": "a"
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
            "period_selection",
            "day_of_week_for_start_day",
            "use_weather_file_daylight_saving_period",
            "use_weather_file_rain_and_snow_indicators"
        ],
        "alphas": {
            "fields": [
                "name",
                "period_selection",
                "day_of_week_for_start_day",
                "use_weather_file_daylight_saving_period",
                "use_weather_file_rain_and_snow_indicators"
            ]
        },
        "numerics": {
            "fields": []
        }
    },
    "type": "object",
    "memo": "Use a weather file period for design sizing calculations. EPW weather files are created with typical and extreme periods created heuristically from the weather file data. For more details on these periods, see AuxiliaryPrograms document."
}
```
