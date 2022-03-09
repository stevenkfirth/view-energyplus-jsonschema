```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "room_air_temperature_pattern_two_gradient_name": {
                    "type": "string"
                },
                "control_integer_for_pattern_control_schedule_name": {
                    "type": "number",
                    "note": "reference this entry in Schedule Name"
                },
                "thermostat_height": {
                    "type": "number",
                    "note": "= Distance from floor of zone",
                    "units": "m"
                },
                "return_air_height": {
                    "type": "number",
                    "note": "= Distance from floor of zone",
                    "units": "m"
                },
                "exhaust_air_height": {
                    "type": "number",
                    "note": "= Distance from floor of zone",
                    "units": "m"
                },
                "temperature_gradient_lower_bound": {
                    "type": "number",
                    "note": "Slope of temperature change in vertical direction",
                    "units": "K/m"
                },
                "temperature_gradient_upper_bound": {
                    "type": "number",
                    "note": "Slope of temperature change in vertical direction",
                    "units": "K/m"
                },
                "gradient_interpolation_mode": {
                    "type": "string",
                    "enum": [
                        "OutdoorDryBulbTemperature",
                        "SensibleCoolingLoad",
                        "SensibleHeatingLoad",
                        "ZoneAndOutdoorTemperatureDifference",
                        "ZoneDryBulbTemperature"
                    ]
                },
                "upper_temperature_bound": {
                    "type": "number",
                    "units": "C"
                },
                "lower_temperature_bound": {
                    "type": "number",
                    "units": "C"
                },
                "upper_heat_rate_bound": {
                    "type": "number",
                    "units": "W"
                },
                "lower_heat_rate_bound": {
                    "type": "number",
                    "units": "W"
                }
            },
            "required": [
                "room_air_temperature_pattern_two_gradient_name",
                "control_integer_for_pattern_control_schedule_name"
            ]
        }
    },
    "group": "Room Air Models",
    "legacy_idd": {
        "field_info": {
            "room_air_temperature_pattern_two_gradient_name": {
                "field_name": "Room Air Temperature Pattern Two Gradient Name",
                "field_type": "a"
            },
            "control_integer_for_pattern_control_schedule_name": {
                "field_name": "Control Integer for Pattern Control Schedule Name",
                "field_type": "n"
            },
            "thermostat_height": {
                "field_name": "Thermostat Height",
                "field_type": "n"
            },
            "return_air_height": {
                "field_name": "Return Air Height",
                "field_type": "n"
            },
            "exhaust_air_height": {
                "field_name": "Exhaust Air Height",
                "field_type": "n"
            },
            "temperature_gradient_lower_bound": {
                "field_name": "Temperature Gradient Lower Bound",
                "field_type": "n"
            },
            "temperature_gradient_upper_bound": {
                "field_name": "Temperature Gradient Upper  Bound",
                "field_type": "n"
            },
            "gradient_interpolation_mode": {
                "field_name": "Gradient Interpolation Mode",
                "field_type": "a"
            },
            "upper_temperature_bound": {
                "field_name": "Upper Temperature Bound",
                "field_type": "n"
            },
            "lower_temperature_bound": {
                "field_name": "Lower Temperature Bound",
                "field_type": "n"
            },
            "upper_heat_rate_bound": {
                "field_name": "Upper Heat Rate Bound",
                "field_type": "n"
            },
            "lower_heat_rate_bound": {
                "field_name": "Lower Heat Rate Bound",
                "field_type": "n"
            }
        },
        "fields": [
            "room_air_temperature_pattern_two_gradient_name",
            "control_integer_for_pattern_control_schedule_name",
            "thermostat_height",
            "return_air_height",
            "exhaust_air_height",
            "temperature_gradient_lower_bound",
            "temperature_gradient_upper_bound",
            "gradient_interpolation_mode",
            "upper_temperature_bound",
            "lower_temperature_bound",
            "upper_heat_rate_bound",
            "lower_heat_rate_bound"
        ],
        "alphas": {
            "fields": [
                "room_air_temperature_pattern_two_gradient_name",
                "gradient_interpolation_mode"
            ]
        },
        "numerics": {
            "fields": [
                "control_integer_for_pattern_control_schedule_name",
                "thermostat_height",
                "return_air_height",
                "exhaust_air_height",
                "temperature_gradient_lower_bound",
                "temperature_gradient_upper_bound",
                "upper_temperature_bound",
                "lower_temperature_bound",
                "upper_heat_rate_bound",
                "lower_heat_rate_bound"
            ]
        }
    },
    "type": "object",
    "memo": "Used to model room air with two temperature gradients in the vertical direction. Used in combination with RoomAir:TemperaturePattern:UserDefined."
}
```
