```
{
    "Site:Precipitation": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "precipitation_model_type": {
                        "type": "string",
                        "enum": [
                            "ScheduleAndDesignLevel"
                        ]
                    },
                    "design_level_for_total_annual_precipitation": {
                        "type": "number",
                        "note": "meters of water per year used for design level",
                        "units": "m/yr"
                    },
                    "precipitation_rates_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "Schedule values in meters of water per hour values should be non-negative"
                    },
                    "average_total_annual_precipitation": {
                        "type": "number",
                        "note": "meters of water per year from average weather statistics",
                        "minimum": 0.0,
                        "units": "m/yr"
                    }
                }
            }
        },
        "group": "Location and Climate",
        "legacy_idd": {
            "field_info": {
                "precipitation_model_type": {
                    "field_name": "Precipitation Model Type",
                    "field_type": "a"
                },
                "design_level_for_total_annual_precipitation": {
                    "field_name": "Design Level for Total Annual Precipitation",
                    "field_type": "n"
                },
                "precipitation_rates_schedule_name": {
                    "field_name": "Precipitation Rates Schedule Name",
                    "field_type": "a"
                },
                "average_total_annual_precipitation": {
                    "field_name": "Average Total Annual Precipitation",
                    "field_type": "n"
                }
            },
            "fields": [
                "precipitation_model_type",
                "design_level_for_total_annual_precipitation",
                "precipitation_rates_schedule_name",
                "average_total_annual_precipitation"
            ],
            "alphas": {
                "fields": [
                    "precipitation_model_type",
                    "precipitation_rates_schedule_name"
                ]
            },
            "numerics": {
                "fields": [
                    "design_level_for_total_annual_precipitation",
                    "average_total_annual_precipitation"
                ]
            }
        },
        "type": "object",
        "memo": "Used to describe the amount of water precipitation at the building site. Precipitation includes both rain and the equivalent water content of snow."
    }
}
```
