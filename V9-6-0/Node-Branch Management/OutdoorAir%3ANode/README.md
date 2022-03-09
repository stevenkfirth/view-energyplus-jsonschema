```
{
    "OutdoorAir:Node": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "height_above_ground": {
                        "type": "number",
                        "note": "A value less than zero indicates that the height will be ignored and the weather file conditions will be used.",
                        "units": "m",
                        "default": -1.0
                    },
                    "drybulb_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "Schedule values are real numbers, -100.0 to 100.0, units C"
                    },
                    "wetbulb_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "Schedule values are real numbers, -100.0 to 100.0, units C"
                    },
                    "wind_speed_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "Schedule values are real numbers, 0.0 to 40.0, units m/s"
                    },
                    "wind_direction_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "Schedule values are real numbers, 0.0 to 360.0, units degree"
                    },
                    "wind_pressure_coefficient_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions",
                            "WPCValueNames"
                        ],
                        "note": "The name of the AirflowNetwork:MultiZone:WindPressureCoefficientValues, curve, or table object specifying the wind pressure coefficient."
                    },
                    "symmetric_wind_pressure_coefficient_curve": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "No",
                        "note": "Specify whether the pressure curve is symmetric or not. Specify Yes for curves that should be evaluated from 0 to 180 degrees Specify No for curves that should be evaluated from 0 to 360 degrees"
                    },
                    "wind_angle_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "Absolute",
                            "Relative"
                        ],
                        "default": "Absolute",
                        "note": "Specify whether the angle used to compute the wind pressure coefficient is absolute or relative Specify Relative to compute the angle between the wind direction and the surface azimuth Specify Absolute to use the wind direction angle directly"
                    }
                }
            }
        },
        "group": "Node-Branch Management",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "OutdoorAirNodeNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "height_above_ground": {
                    "field_name": "Height Above Ground",
                    "field_type": "n"
                },
                "drybulb_temperature_schedule_name": {
                    "field_name": "Drybulb Temperature Schedule Name",
                    "field_type": "a"
                },
                "wetbulb_temperature_schedule_name": {
                    "field_name": "Wetbulb Temperature Schedule Name",
                    "field_type": "a"
                },
                "wind_speed_schedule_name": {
                    "field_name": "Wind Speed Schedule Name",
                    "field_type": "a"
                },
                "wind_direction_schedule_name": {
                    "field_name": "Wind Direction Schedule Name",
                    "field_type": "a"
                },
                "wind_pressure_coefficient_curve_name": {
                    "field_name": "Wind Pressure Coefficient Curve Name",
                    "field_type": "a"
                },
                "symmetric_wind_pressure_coefficient_curve": {
                    "field_name": "Symmetric Wind Pressure Coefficient Curve",
                    "field_type": "a"
                },
                "wind_angle_type": {
                    "field_name": "Wind Angle Type",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "height_above_ground",
                "drybulb_temperature_schedule_name",
                "wetbulb_temperature_schedule_name",
                "wind_speed_schedule_name",
                "wind_direction_schedule_name",
                "wind_pressure_coefficient_curve_name",
                "symmetric_wind_pressure_coefficient_curve",
                "wind_angle_type"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "drybulb_temperature_schedule_name",
                    "wetbulb_temperature_schedule_name",
                    "wind_speed_schedule_name",
                    "wind_direction_schedule_name",
                    "wind_pressure_coefficient_curve_name",
                    "symmetric_wind_pressure_coefficient_curve",
                    "wind_angle_type"
                ]
            },
            "numerics": {
                "fields": [
                    "height_above_ground"
                ]
            }
        },
        "type": "object",
        "memo": "This object sets the temperature and humidity conditions for an outdoor air node. It allows the height above ground to be specified. This object may be used more than once. The same node name may not appear in both an OutdoorAir:Node object and an OutdoorAir:NodeList object. This object defines local outdoor air environmental conditions."
    }
}
```
