```
{
    "AirflowNetwork:MultiZone:ExternalNode": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "external_node_height": {
                        "type": "number",
                        "units": "m",
                        "default": 0.0,
                        "note": "Designates the reference height used to calculate relative pressure."
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
                },
                "required": [
                    "wind_pressure_coefficient_curve_name"
                ]
            }
        },
        "group": "AirflowNetwork",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "ExternalNodeNames"
            ],
            "note": "Enter a unique name for this object. This node name will be referenced by a particular building facade."
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "external_node_height": {
                    "field_name": "External Node Height",
                    "field_type": "n"
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
                "external_node_height",
                "wind_pressure_coefficient_curve_name",
                "symmetric_wind_pressure_coefficient_curve",
                "wind_angle_type"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "wind_pressure_coefficient_curve_name",
                    "symmetric_wind_pressure_coefficient_curve",
                    "wind_angle_type"
                ]
            },
            "numerics": {
                "fields": [
                    "external_node_height"
                ]
            }
        },
        "type": "object",
        "memo": "This object defines outdoor environmental conditions outside of the building.",
        "min_fields": 3.0
    }
}
```
