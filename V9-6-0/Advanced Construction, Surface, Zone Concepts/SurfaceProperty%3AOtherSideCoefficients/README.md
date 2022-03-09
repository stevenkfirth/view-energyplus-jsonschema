```
{
    "SurfaceProperty:OtherSideCoefficients": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "combined_convective_radiative_film_coefficient": {
                        "type": "number",
                        "units": "W/m2-K",
                        "note": "if>0, this field becomes the exterior convective/radiative film coefficient and the other fields are used to calculate the outdoor air temperature then exterior surface temperature based on outdoor air and specified coefficient if<=0, then remaining fields calculate the outside surface temperature The following fields are used in the equation: OtherSideTemp=N2*N3 + N4*OutdoorDry-bulb + N5*GroundTemp + N6*WindSpeed*OutdoorDry-bulb + N7*TempZone + N9*TempPrev"
                    },
                    "constant_temperature": {
                        "type": "number",
                        "units": "C",
                        "default": 0.0,
                        "note": "This parameter will be overwritten by the values from the Constant Temperature Schedule Name (below) if one is present"
                    },
                    "constant_temperature_coefficient": {
                        "type": "number",
                        "note": "This coefficient is used even with a Schedule. It should normally be 1.0 in that case. This field is ignored if Sinusoidal Variation of Constant Temperature Coefficient = Yes.",
                        "default": 1.0
                    },
                    "external_dry_bulb_temperature_coefficient": {
                        "type": "number",
                        "default": 0.0
                    },
                    "ground_temperature_coefficient": {
                        "type": "number",
                        "default": 0.0
                    },
                    "wind_speed_coefficient": {
                        "type": "number",
                        "default": 0.0
                    },
                    "zone_air_temperature_coefficient": {
                        "type": "number",
                        "default": 0.0
                    },
                    "constant_temperature_schedule_name": {
                        "type": "string",
                        "note": "Name of schedule for values of constant temperature. Schedule values replace any value specified in the field Constant Temperature.",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "sinusoidal_variation_of_constant_temperature_coefficient": {
                        "type": "string",
                        "note": "Optionally used to vary Constant Temperature Coefficient with unitary sine wave",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "No"
                    },
                    "period_of_sinusoidal_variation": {
                        "type": "number",
                        "note": "Use with sinusoidal variation to define the time period",
                        "units": "hr",
                        "default": 24.0,
                        "exclusiveMinimum": 0.0
                    },
                    "previous_other_side_temperature_coefficient": {
                        "type": "number",
                        "note": "This coefficient multiplies the other side temperature result from the previous zone timestep",
                        "default": 0.0
                    },
                    "minimum_other_side_temperature_limit": {
                        "type": "number",
                        "note": "This field specifies a lower limit for the other side temperature result. Blank indicates no limit",
                        "units": "C"
                    },
                    "maximum_other_side_temperature_limit": {
                        "type": "number",
                        "note": "This field specifies an upper limit for the other side temperature result. Blank indicates no limit",
                        "units": "C"
                    }
                },
                "required": [
                    "combined_convective_radiative_film_coefficient"
                ]
            }
        },
        "group": "Advanced Construction, Surface, Zone Concepts",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "OutFaceEnvNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "combined_convective_radiative_film_coefficient": {
                    "field_name": "Combined Convective/Radiative Film Coefficient",
                    "field_type": "n"
                },
                "constant_temperature": {
                    "field_name": "Constant Temperature",
                    "field_type": "n"
                },
                "constant_temperature_coefficient": {
                    "field_name": "Constant Temperature Coefficient",
                    "field_type": "n"
                },
                "external_dry_bulb_temperature_coefficient": {
                    "field_name": "External Dry-Bulb Temperature Coefficient",
                    "field_type": "n"
                },
                "ground_temperature_coefficient": {
                    "field_name": "Ground Temperature Coefficient",
                    "field_type": "n"
                },
                "wind_speed_coefficient": {
                    "field_name": "Wind Speed Coefficient",
                    "field_type": "n"
                },
                "zone_air_temperature_coefficient": {
                    "field_name": "Zone Air Temperature Coefficient",
                    "field_type": "n"
                },
                "constant_temperature_schedule_name": {
                    "field_name": "Constant Temperature Schedule Name",
                    "field_type": "a"
                },
                "sinusoidal_variation_of_constant_temperature_coefficient": {
                    "field_name": "Sinusoidal Variation of Constant Temperature Coefficient",
                    "field_type": "a"
                },
                "period_of_sinusoidal_variation": {
                    "field_name": "Period of Sinusoidal Variation",
                    "field_type": "n"
                },
                "previous_other_side_temperature_coefficient": {
                    "field_name": "Previous Other Side Temperature Coefficient",
                    "field_type": "n"
                },
                "minimum_other_side_temperature_limit": {
                    "field_name": "Minimum Other Side Temperature Limit",
                    "field_type": "n"
                },
                "maximum_other_side_temperature_limit": {
                    "field_name": "Maximum Other Side Temperature Limit",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "combined_convective_radiative_film_coefficient",
                "constant_temperature",
                "constant_temperature_coefficient",
                "external_dry_bulb_temperature_coefficient",
                "ground_temperature_coefficient",
                "wind_speed_coefficient",
                "zone_air_temperature_coefficient",
                "constant_temperature_schedule_name",
                "sinusoidal_variation_of_constant_temperature_coefficient",
                "period_of_sinusoidal_variation",
                "previous_other_side_temperature_coefficient",
                "minimum_other_side_temperature_limit",
                "maximum_other_side_temperature_limit"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "constant_temperature_schedule_name",
                    "sinusoidal_variation_of_constant_temperature_coefficient"
                ]
            },
            "numerics": {
                "fields": [
                    "combined_convective_radiative_film_coefficient",
                    "constant_temperature",
                    "constant_temperature_coefficient",
                    "external_dry_bulb_temperature_coefficient",
                    "ground_temperature_coefficient",
                    "wind_speed_coefficient",
                    "zone_air_temperature_coefficient",
                    "period_of_sinusoidal_variation",
                    "previous_other_side_temperature_coefficient",
                    "minimum_other_side_temperature_limit",
                    "maximum_other_side_temperature_limit"
                ]
            }
        },
        "type": "object",
        "memo": "This object sets the other side conditions for a surface in a variety of ways.",
        "min_fields": 8.0
    }
}
```
