```
{
    "ZoneVentilation:WindandStackOpenArea": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "zone_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ]
                    },
                    "opening_area": {
                        "type": "number",
                        "note": "This is the opening area used to calculate stack effect and wind driven ventilation.",
                        "units": "m2",
                        "minimum": 0.0,
                        "default": 0.0
                    },
                    "opening_area_fraction_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "This schedule contains the fraction values applied to the opening area given in the previous input field (0.0 - 1.0)."
                    },
                    "opening_effectiveness": {
                        "note": "This field is used to calculate wind driven ventilation. \"Cw\" in the wind-driven equation and the maximum value is 1.0. When the input is Autocalculate, the program calculates Cw based on an angle between wind direction and effective angle Cw = 0.55 at angle = 0, and Cw = 0.3 at angle=180 Linear interpolation is used to calculate Cw based on the above two values.",
                        "units": "dimensionless",
                        "default": "Autocalculate",
                        "anyOf": [
                            {
                                "type": "number",
                                "minimum": 0.0,
                                "maximum": 1.0
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "",
                                    "Autocalculate"
                                ]
                            }
                        ]
                    },
                    "effective_angle": {
                        "type": "number",
                        "note": "This field is defined as normal angle of the opening area and is used when input field Opening Effectiveness = Autocalculate.",
                        "units": "deg",
                        "minimum": 0.0,
                        "exclusiveMaximum": 360.0,
                        "default": 0.0
                    },
                    "height_difference": {
                        "type": "number",
                        "note": "This is the height difference between the midpoint of an opening and the neutral pressure level. \"DH\" in the stack equation.",
                        "units": "m",
                        "minimum": 0.0,
                        "default": 0.0
                    },
                    "discharge_coefficient_for_opening": {
                        "note": "This is the discharge coefficient used to calculate stack effect. \"Cd\" in the stack equation and the maximum value is 1.0. When the input is Autocalculate, the following equation is used to calculate the coefficient: Cd = 0.4 + 0.0045*|(Tzone-Todb)|",
                        "default": "Autocalculate",
                        "anyOf": [
                            {
                                "type": "number",
                                "minimum": 0.0,
                                "maximum": 1.0
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "",
                                    "Autocalculate"
                                ]
                            }
                        ]
                    },
                    "minimum_indoor_temperature": {
                        "type": "number",
                        "note": "This is the indoor temperature below which ventilation is shutoff.",
                        "units": "C",
                        "minimum": -100.0,
                        "maximum": 100.0,
                        "default": -100.0
                    },
                    "minimum_indoor_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "This schedule contains the indoor temperature versus time below which ventilation is shutoff."
                    },
                    "maximum_indoor_temperature": {
                        "type": "number",
                        "note": "This is the indoor temperature above which ventilation is shutoff.",
                        "units": "C",
                        "minimum": -100.0,
                        "maximum": 100.0,
                        "default": 100.0
                    },
                    "maximum_indoor_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "This schedule contains the indoor temperature versus time above which ventilation is shutoff."
                    },
                    "delta_temperature": {
                        "type": "number",
                        "note": "This is the temperature differential between indoor and outdoor below which ventilation is shutoff.",
                        "units": "deltaC",
                        "minimum": -100.0,
                        "default": -100.0
                    },
                    "delta_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "This schedule contains the temperature differential between indoor and outdoor versus time below which ventilation is shutoff."
                    },
                    "minimum_outdoor_temperature": {
                        "type": "number",
                        "note": "This is the outdoor temperature below which ventilation is shutoff.",
                        "units": "C",
                        "minimum": -100.0,
                        "maximum": 100.0,
                        "default": -100.0
                    },
                    "minimum_outdoor_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "This schedule contains the outdoor temperature versus time below which ventilation is shutoff."
                    },
                    "maximum_outdoor_temperature": {
                        "type": "number",
                        "note": "This is the outdoor temperature above which ventilation is shutoff.",
                        "units": "C",
                        "minimum": -100.0,
                        "maximum": 100.0,
                        "default": 100.0
                    },
                    "maximum_outdoor_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "This schedule contains the outdoor temperature versus time above which ventilation is shutoff."
                    },
                    "maximum_wind_speed": {
                        "type": "number",
                        "note": "This is the outdoor wind speed above which ventilation is shutoff.",
                        "units": "m/s",
                        "minimum": 0.0,
                        "maximum": 40.0,
                        "default": 40.0
                    }
                },
                "required": [
                    "zone_name"
                ]
            }
        },
        "group": "Zone Airflow",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "VentilationNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "zone_name": {
                    "field_name": "Zone Name",
                    "field_type": "a"
                },
                "opening_area": {
                    "field_name": "Opening Area",
                    "field_type": "n"
                },
                "opening_area_fraction_schedule_name": {
                    "field_name": "Opening Area Fraction Schedule Name",
                    "field_type": "a"
                },
                "opening_effectiveness": {
                    "field_name": "Opening Effectiveness",
                    "field_type": "n"
                },
                "effective_angle": {
                    "field_name": "Effective Angle",
                    "field_type": "n"
                },
                "height_difference": {
                    "field_name": "Height Difference",
                    "field_type": "n"
                },
                "discharge_coefficient_for_opening": {
                    "field_name": "Discharge Coefficient for Opening",
                    "field_type": "n"
                },
                "minimum_indoor_temperature": {
                    "field_name": "Minimum Indoor Temperature",
                    "field_type": "n"
                },
                "minimum_indoor_temperature_schedule_name": {
                    "field_name": "Minimum Indoor Temperature Schedule Name",
                    "field_type": "a"
                },
                "maximum_indoor_temperature": {
                    "field_name": "Maximum Indoor Temperature",
                    "field_type": "n"
                },
                "maximum_indoor_temperature_schedule_name": {
                    "field_name": "Maximum Indoor Temperature Schedule Name",
                    "field_type": "a"
                },
                "delta_temperature": {
                    "field_name": "Delta Temperature",
                    "field_type": "n"
                },
                "delta_temperature_schedule_name": {
                    "field_name": "Delta Temperature Schedule Name",
                    "field_type": "a"
                },
                "minimum_outdoor_temperature": {
                    "field_name": "Minimum Outdoor Temperature",
                    "field_type": "n"
                },
                "minimum_outdoor_temperature_schedule_name": {
                    "field_name": "Minimum Outdoor Temperature Schedule Name",
                    "field_type": "a"
                },
                "maximum_outdoor_temperature": {
                    "field_name": "Maximum Outdoor Temperature",
                    "field_type": "n"
                },
                "maximum_outdoor_temperature_schedule_name": {
                    "field_name": "Maximum Outdoor Temperature Schedule Name",
                    "field_type": "a"
                },
                "maximum_wind_speed": {
                    "field_name": "Maximum Wind Speed",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "zone_name",
                "opening_area",
                "opening_area_fraction_schedule_name",
                "opening_effectiveness",
                "effective_angle",
                "height_difference",
                "discharge_coefficient_for_opening",
                "minimum_indoor_temperature",
                "minimum_indoor_temperature_schedule_name",
                "maximum_indoor_temperature",
                "maximum_indoor_temperature_schedule_name",
                "delta_temperature",
                "delta_temperature_schedule_name",
                "minimum_outdoor_temperature",
                "minimum_outdoor_temperature_schedule_name",
                "maximum_outdoor_temperature",
                "maximum_outdoor_temperature_schedule_name",
                "maximum_wind_speed"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "zone_name",
                    "opening_area_fraction_schedule_name",
                    "minimum_indoor_temperature_schedule_name",
                    "maximum_indoor_temperature_schedule_name",
                    "delta_temperature_schedule_name",
                    "minimum_outdoor_temperature_schedule_name",
                    "maximum_outdoor_temperature_schedule_name"
                ]
            },
            "numerics": {
                "fields": [
                    "opening_area",
                    "opening_effectiveness",
                    "effective_angle",
                    "height_difference",
                    "discharge_coefficient_for_opening",
                    "minimum_indoor_temperature",
                    "maximum_indoor_temperature",
                    "delta_temperature",
                    "minimum_outdoor_temperature",
                    "maximum_outdoor_temperature",
                    "maximum_wind_speed"
                ]
            }
        },
        "type": "object",
        "memo": "This object is specified as natural ventilation driven by wind and stack effect only: Ventilation Wind = Cw * Opening Area * Schedule * WindSpd Ventilation Stack = Cd * Opening Area * Schedule * SQRT(2*g*DH*(|(Tzone-Todb)|/Tzone)) Total Ventilation = SQRT((Ventilation Wind)^2 + (Ventilation Stack)^2)",
        "min_fields": 8.0
    }
}
```
