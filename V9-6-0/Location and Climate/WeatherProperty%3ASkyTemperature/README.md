```
{
    "WeatherProperty:SkyTemperature": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "calculation_type": {
                        "type": "string",
                        "note": "The field indicates that the sky temperature will be imported from external schedules or calculated by alternative methods other than default.",
                        "enum": [
                            "",
                            "BerdahlMartin",
                            "Brunt",
                            "ClarkAllen",
                            "DifferenceScheduleDewPointValue",
                            "DifferenceScheduleDryBulbValue",
                            "Idso",
                            "ScheduleValue"
                        ],
                        "default": "ClarkAllen"
                    },
                    "schedule_name": {
                        "type": "string",
                        "note": "if name matches a SizingPeriod:DesignDay, put in a day schedule of this name if name is for a SizingPeriod:WeatherFileDays, SizingPeriod:WeatherFileConditionType or RunPeriod, put in a full year schedule that covers the appropriate days. Required if Calculation Type is ScheduleValue, DifferenceScheduleDryBulbValue or DifferenceScheduleDewPointValue.",
                        "data_type": "object_list",
                        "object_list": [
                            "DayScheduleNames",
                            "ScheduleNames"
                        ]
                    },
                    "use_weather_file_horizontal_ir": {
                        "type": "string",
                        "note": "If yes or blank, use Horizontal IR values from weather file when present, otherwise use the specified sky model. If no, always use the specified sky model and ignore the horizontal IR values from the weather file. For Calculation Type = ScheduleValue, DifferenceScheduleDryBulbValue or DifferenceScheduleDewPointValue, this field is ignored and the scheduled values are used.",
                        "default": "Yes",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ]
                    }
                }
            }
        },
        "group": "Location and Climate",
        "name": {
            "type": "string",
            "note": "blank in this field will apply to all run periods (that is, all objects= SizingPeriod:WeatherFileDays, SizingPeriod:WeatherFileConditionType or RunPeriod otherwise, this name must match one of the environment object names.",
            "data_type": "object_list",
            "object_list": [
                "RunPeriodsAndDesignDays"
            ]
        },
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "calculation_type": {
                    "field_name": "Calculation Type",
                    "field_type": "a"
                },
                "schedule_name": {
                    "field_name": "Schedule Name",
                    "field_type": "a"
                },
                "use_weather_file_horizontal_ir": {
                    "field_name": "Use Weather File Horizontal IR",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "calculation_type",
                "schedule_name",
                "use_weather_file_horizontal_ir"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "calculation_type",
                    "schedule_name",
                    "use_weather_file_horizontal_ir"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "memo": "This object is used to override internal sky temperature calculations."
    }
}
```
