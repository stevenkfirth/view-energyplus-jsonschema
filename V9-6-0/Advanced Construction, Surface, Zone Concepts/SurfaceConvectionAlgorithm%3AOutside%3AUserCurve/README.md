```
{
    "SurfaceConvectionAlgorithm:Outside:UserCurve": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "wind_speed_type_for_curve": {
                        "type": "string",
                        "enum": [
                            "",
                            "HeightAdjust",
                            "ParallelComponent",
                            "ParallelComponentHeightAdjust",
                            "WeatherFile"
                        ],
                        "default": "HeightAdjust"
                    },
                    "hf_function_of_wind_speed_curve_name": {
                        "type": "string",
                        "note": "Curve's \"x\" is wind speed of the type determined in the previous field (m/s)",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ]
                    },
                    "hn_function_of_temperature_difference_curve_name": {
                        "type": "string",
                        "note": "Curve's \"x\" is absolute value of delta-T (Surface temperature minus air temperature, (C))",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ]
                    },
                    "hn_function_of_temperature_difference_divided_by_height_curve_name": {
                        "type": "string",
                        "note": "Curve's \"x\" is absolute value of delta-T/Height (Surface temp minus Air temp)/(vertical length scale), (C/m) when used for an outside face the vertical length scale is the exterior facade's overall height",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ]
                    }
                }
            }
        },
        "group": "Advanced Construction, Surface, Zone Concepts",
        "name": {
            "type": "string",
            "reference": [
                "UserConvectionModels",
                "UserConvectionOutsideModels"
            ]
        },
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "wind_speed_type_for_curve": {
                    "field_name": "Wind Speed Type for Curve",
                    "field_type": "a"
                },
                "hf_function_of_wind_speed_curve_name": {
                    "field_name": "Hf Function of Wind Speed Curve Name",
                    "field_type": "a"
                },
                "hn_function_of_temperature_difference_curve_name": {
                    "field_name": "Hn Function of Temperature Difference Curve Name",
                    "field_type": "a"
                },
                "hn_function_of_temperature_difference_divided_by_height_curve_name": {
                    "field_name": "Hn Function of Temperature Difference Divided by Height Curve Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "wind_speed_type_for_curve",
                "hf_function_of_wind_speed_curve_name",
                "hn_function_of_temperature_difference_curve_name",
                "hn_function_of_temperature_difference_divided_by_height_curve_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "wind_speed_type_for_curve",
                    "hf_function_of_wind_speed_curve_name",
                    "hn_function_of_temperature_difference_curve_name",
                    "hn_function_of_temperature_difference_divided_by_height_curve_name"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "memo": "Used to describe a custom model equation for surface convection heat transfer coefficient If more than one curve is referenced they are all used and added together."
    }
}
```
