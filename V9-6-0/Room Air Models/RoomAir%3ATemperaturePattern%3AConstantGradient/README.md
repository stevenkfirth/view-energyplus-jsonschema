```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "room_air_temperature_pattern_constant_gradient_name": {
                    "type": "string"
                },
                "control_integer_for_pattern_control_schedule_name": {
                    "type": "number",
                    "note": "reference this entry in Schedule Name"
                },
                "thermostat_offset": {
                    "type": "number",
                    "note": "= (Temp at thermostat- Mean Air Temp)",
                    "units": "deltaC"
                },
                "return_air_offset": {
                    "type": "number",
                    "note": "= (Tleaving - Mean Air Temp )",
                    "units": "deltaC"
                },
                "exhaust_air_offset": {
                    "type": "number",
                    "note": "= (Texhaust - Mean Air Temp) deg C",
                    "units": "deltaC"
                },
                "temperature_gradient": {
                    "type": "number",
                    "note": "Slope of temperature change in vertical direction",
                    "units": "K/m"
                }
            },
            "required": [
                "room_air_temperature_pattern_constant_gradient_name",
                "control_integer_for_pattern_control_schedule_name"
            ]
        }
    },
    "group": "Room Air Models",
    "legacy_idd": {
        "field_info": {
            "room_air_temperature_pattern_constant_gradient_name": {
                "field_name": "Room Air Temperature Pattern Constant Gradient Name",
                "field_type": "a"
            },
            "control_integer_for_pattern_control_schedule_name": {
                "field_name": "Control Integer for Pattern Control Schedule Name",
                "field_type": "n"
            },
            "thermostat_offset": {
                "field_name": "Thermostat Offset",
                "field_type": "n"
            },
            "return_air_offset": {
                "field_name": "Return Air Offset",
                "field_type": "n"
            },
            "exhaust_air_offset": {
                "field_name": "Exhaust Air Offset",
                "field_type": "n"
            },
            "temperature_gradient": {
                "field_name": "Temperature Gradient",
                "field_type": "n"
            }
        },
        "fields": [
            "room_air_temperature_pattern_constant_gradient_name",
            "control_integer_for_pattern_control_schedule_name",
            "thermostat_offset",
            "return_air_offset",
            "exhaust_air_offset",
            "temperature_gradient"
        ],
        "alphas": {
            "fields": [
                "room_air_temperature_pattern_constant_gradient_name"
            ]
        },
        "numerics": {
            "fields": [
                "control_integer_for_pattern_control_schedule_name",
                "thermostat_offset",
                "return_air_offset",
                "exhaust_air_offset",
                "temperature_gradient"
            ]
        }
    },
    "type": "object",
    "memo": "Used to model room air with a fixed temperature gradient in the vertical direction. Used in combination with RoomAir:TemperaturePattern:UserDefined."
}
```
