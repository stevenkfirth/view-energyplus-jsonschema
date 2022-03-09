```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "wind_sensor_height_above_ground": {
                    "type": "number",
                    "units": "m",
                    "default": 10.0,
                    "exclusiveMinimum": 0.0
                },
                "wind_speed_profile_exponent": {
                    "type": "number",
                    "default": 0.14,
                    "minimum": 0.0
                },
                "wind_speed_profile_boundary_layer_thickness": {
                    "type": "number",
                    "units": "m",
                    "default": 270.0,
                    "minimum": 0.0
                },
                "air_temperature_sensor_height_above_ground": {
                    "type": "number",
                    "units": "m",
                    "default": 1.5,
                    "minimum": 0.0
                }
            }
        }
    },
    "group": "Location and Climate",
    "legacy_idd": {
        "field_info": {
            "wind_sensor_height_above_ground": {
                "field_name": "Wind Sensor Height Above Ground",
                "field_type": "n"
            },
            "wind_speed_profile_exponent": {
                "field_name": "Wind Speed Profile Exponent",
                "field_type": "n"
            },
            "wind_speed_profile_boundary_layer_thickness": {
                "field_name": "Wind Speed Profile Boundary Layer Thickness",
                "field_type": "n"
            },
            "air_temperature_sensor_height_above_ground": {
                "field_name": "Air Temperature Sensor Height Above Ground",
                "field_type": "n"
            }
        },
        "fields": [
            "wind_sensor_height_above_ground",
            "wind_speed_profile_exponent",
            "wind_speed_profile_boundary_layer_thickness",
            "air_temperature_sensor_height_above_ground"
        ],
        "alphas": {
            "fields": []
        },
        "numerics": {
            "fields": [
                "wind_sensor_height_above_ground",
                "wind_speed_profile_exponent",
                "wind_speed_profile_boundary_layer_thickness",
                "air_temperature_sensor_height_above_ground"
            ]
        }
    },
    "type": "object",
    "maxProperties": 1,
    "memo": "This object should only be used for non-standard weather data. Standard weather data such as TMY2, IWEC, and ASHRAE design day data are all measured at the default conditions and do not require this object."
}
```
