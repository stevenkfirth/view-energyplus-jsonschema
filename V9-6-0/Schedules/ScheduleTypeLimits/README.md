```
{
    "ScheduleTypeLimits": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "lower_limit_value": {
                        "type": "number",
                        "note": "lower limit (real or integer) for the Schedule Type. e.g. if fraction, this is 0.0",
                        "unitsBasedOnField": "unit_type"
                    },
                    "upper_limit_value": {
                        "type": "number",
                        "note": "upper limit (real or integer) for the Schedule Type. e.g. if fraction, this is 1.0",
                        "unitsBasedOnField": "unit_type"
                    },
                    "numeric_type": {
                        "type": "string",
                        "note": "Numeric type is either Continuous (all numbers within the min and max are valid or Discrete (only integer numbers between min and max are valid. (Could also allow REAL and INTEGER to mean the same things)",
                        "enum": [
                            "Continuous",
                            "Discrete"
                        ]
                    },
                    "unit_type": {
                        "type": "string",
                        "note": "Temperature (C or F) DeltaTemperature (C or F) PrecipitationRate (m/hr or ft/hr) Angle (degrees) Convection Coefficient (W/m2-K or Btu/sqft-hr-F) Activity Level (W/person) Velocity (m/s or ft/min) Capacity (W or Btu/h) Power (W)",
                        "enum": [
                            "",
                            "ActivityLevel",
                            "Angle",
                            "Availability",
                            "Capacity",
                            "Control",
                            "ConvectionCoefficient",
                            "DeltaTemperature",
                            "Dimensionless",
                            "Mode",
                            "Percent",
                            "Power",
                            "PrecipitationRate",
                            "Temperature",
                            "Velocity"
                        ],
                        "default": "Dimensionless"
                    }
                }
            }
        },
        "group": "Schedules",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "ScheduleTypeLimitsNames"
            ],
            "note": "used to validate schedule types in various schedule objects"
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "lower_limit_value": {
                    "field_name": "Lower Limit Value",
                    "field_type": "n"
                },
                "upper_limit_value": {
                    "field_name": "Upper Limit Value",
                    "field_type": "n"
                },
                "numeric_type": {
                    "field_name": "Numeric Type",
                    "field_type": "a"
                },
                "unit_type": {
                    "field_name": "Unit Type",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "lower_limit_value",
                "upper_limit_value",
                "numeric_type",
                "unit_type"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "numeric_type",
                    "unit_type"
                ]
            },
            "numerics": {
                "fields": [
                    "lower_limit_value",
                    "upper_limit_value"
                ]
            }
        },
        "type": "object",
        "memo": "ScheduleTypeLimits specifies the data types and limits for the values contained in schedules"
    }
}
```
