```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "calculation_method": {
                    "type": "string",
                    "enum": [
                        "",
                        "Correlation",
                        "CorrelationFromWeatherFile",
                        "Schedule"
                    ],
                    "default": "CorrelationFromWeatherFile",
                    "note": "If calculation method is CorrelationFromWeatherFile, the two numeric input fields are ignored. Instead, EnergyPlus calculates them from weather file."
                },
                "temperature_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "annual_average_outdoor_air_temperature": {
                    "type": "number",
                    "note": "If calculation method is CorrelationFromWeatherFile or Schedule, this input field is ignored.",
                    "units": "C"
                },
                "maximum_difference_in_monthly_average_outdoor_air_temperatures": {
                    "type": "number",
                    "note": "If calculation method is CorrelationFromWeatherFile or Schedule, this input field is ignored.",
                    "units": "deltaC",
                    "minimum": 0.0
                }
            }
        }
    },
    "group": "Location and Climate",
    "legacy_idd": {
        "field_info": {
            "calculation_method": {
                "field_name": "Calculation Method",
                "field_type": "a"
            },
            "temperature_schedule_name": {
                "field_name": "Temperature Schedule Name",
                "field_type": "a"
            },
            "annual_average_outdoor_air_temperature": {
                "field_name": "Annual Average Outdoor Air Temperature",
                "field_type": "n"
            },
            "maximum_difference_in_monthly_average_outdoor_air_temperatures": {
                "field_name": "Maximum Difference In Monthly Average Outdoor Air Temperatures",
                "field_type": "n"
            }
        },
        "fields": [
            "calculation_method",
            "temperature_schedule_name",
            "annual_average_outdoor_air_temperature",
            "maximum_difference_in_monthly_average_outdoor_air_temperatures"
        ],
        "alphas": {
            "fields": [
                "calculation_method",
                "temperature_schedule_name"
            ]
        },
        "numerics": {
            "fields": [
                "annual_average_outdoor_air_temperature",
                "maximum_difference_in_monthly_average_outdoor_air_temperatures"
            ]
        }
    },
    "type": "object",
    "memo": "Used to calculate water mains temperatures delivered by underground water main pipes. Water mains temperatures are a function of outdoor climate conditions and vary with time of year."
}
```
