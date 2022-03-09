```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "control_integer_for_pattern_control_schedule_name": {
                    "type": "number",
                    "note": "reference this entry in schedule"
                },
                "thermostat_offset": {
                    "type": "number",
                    "note": "= (Temp at thermostat- Mean Air Temp)",
                    "units": "deltaC"
                },
                "return_air_offset": {
                    "type": "number",
                    "note": "= (Tleaving - Mean Air Temp ) deg C",
                    "units": "deltaC"
                },
                "exhaust_air_offset": {
                    "type": "number",
                    "note": "= (Texhaust - Mean Air Temp) deg C",
                    "units": "deltaC"
                },
                "surface_deltas": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "surface_name_pair": {
                                "type": "string",
                                "data_type": "object_list",
                                "object_list": [
                                    "AllHeatTranSurfNames"
                                ]
                            },
                            "delta_adjacent_air_temperature_pair": {
                                "type": "number",
                                "units": "deltaC"
                            }
                        },
                        "type": "object",
                        "required": [
                            "delta_adjacent_air_temperature_pair",
                            "surface_name_pair"
                        ]
                    }
                }
            },
            "required": [
                "control_integer_for_pattern_control_schedule_name"
            ]
        }
    },
    "group": "Room Air Models",
    "name": {
        "type": "string",
        "is_required": true
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
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
            "surface_name_pair": {
                "field_name": "Surface Name Pair",
                "field_type": "a"
            },
            "delta_adjacent_air_temperature_pair": {
                "field_name": "Delta Adjacent Air Temperature Pair",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "control_integer_for_pattern_control_schedule_name",
            "thermostat_offset",
            "return_air_offset",
            "exhaust_air_offset"
        ],
        "alphas": {
            "fields": [
                "name"
            ],
            "extensions": [
                "surface_name_pair"
            ]
        },
        "numerics": {
            "fields": [
                "control_integer_for_pattern_control_schedule_name",
                "thermostat_offset",
                "return_air_offset",
                "exhaust_air_offset"
            ],
            "extensions": [
                "delta_adjacent_air_temperature_pair"
            ]
        },
        "extensibles": [
            "surface_name_pair",
            "delta_adjacent_air_temperature_pair"
        ],
        "extension": "surface_deltas"
    },
    "type": "object",
    "memo": "Defines a distribution pattern for the air temperatures adjacent to individual surfaces. This allows controlling the adjacent air temperature on a surface-by-surface basis rather than by height. This allows modeling different adjacent air temperatures on the opposite sides of the zone. Used in combination with RoomAir:TemperaturePattern:UserDefined.",
    "extensible_size": 2.0
}
```
