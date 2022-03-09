```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "wind_speed_profile_exponent": {
                    "type": "number",
                    "note": "Set to zero for no wind speed dependence on height.",
                    "default": 0.22,
                    "minimum": 0.0
                },
                "wind_speed_profile_boundary_layer_thickness": {
                    "type": "number",
                    "units": "m",
                    "default": 370.0,
                    "exclusiveMinimum": 0.0
                },
                "air_temperature_gradient_coefficient": {
                    "type": "number",
                    "note": "Set to zero for no air temperature dependence on height.",
                    "units": "K/m",
                    "default": 0.0065,
                    "minimum": 0.0
                }
            }
        }
    },
    "group": "Location and Climate",
    "legacy_idd": {
        "field_info": {
            "wind_speed_profile_exponent": {
                "field_name": "Wind Speed Profile Exponent",
                "field_type": "n"
            },
            "wind_speed_profile_boundary_layer_thickness": {
                "field_name": "Wind Speed Profile Boundary Layer Thickness",
                "field_type": "n"
            },
            "air_temperature_gradient_coefficient": {
                "field_name": "Air Temperature Gradient Coefficient",
                "field_type": "n"
            }
        },
        "fields": [
            "wind_speed_profile_exponent",
            "wind_speed_profile_boundary_layer_thickness",
            "air_temperature_gradient_coefficient"
        ],
        "alphas": {
            "fields": []
        },
        "numerics": {
            "fields": [
                "wind_speed_profile_exponent",
                "wind_speed_profile_boundary_layer_thickness",
                "air_temperature_gradient_coefficient"
            ]
        }
    },
    "type": "object",
    "maxProperties": 1,
    "memo": "This object is used if the user requires advanced control over height-dependent variations in wind speed and temperature. When this object is not present, the default model for temperature dependence on height is used, and the wind speed is modeled according to the Terrain field of the BUILDING object."
}
```
