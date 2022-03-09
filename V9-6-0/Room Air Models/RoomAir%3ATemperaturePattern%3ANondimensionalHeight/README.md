```
{
    "RoomAir:TemperaturePattern:NondimensionalHeight": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "control_integer_for_pattern_control_schedule_name": {
                        "type": "number",
                        "note": "this value should appear in as a schedule value"
                    },
                    "thermostat_offset": {
                        "type": "number",
                        "note": "= (Temp at thermostat- Mean Air Temp)",
                        "units": "deltaC"
                    },
                    "return_air_offset": {
                        "type": "number",
                        "note": "= (Temp leaving - Mean Air Temp ) deg C",
                        "units": "deltaC"
                    },
                    "exhaust_air_offset": {
                        "type": "number",
                        "note": "= (Temp exhaust - Mean Air Temp) deg C the remaining fields have pairs that describe the relative temperature pattern in the vertical direction of a zone Zeta is the nondimensional height (in z-direction). on [0..1] DeltaTai =  (Tai - MAT) in units of deg. C relative deg C on [-10.0 .. 20.0 ]",
                        "units": "deltaC"
                    },
                    "pairs": {
                        "type": "array",
                        "items": {
                            "properties": {
                                "pair_zeta_nondimensional_height": {
                                    "type": "number"
                                },
                                "pair_delta_adjacent_air_temperature": {
                                    "type": "number",
                                    "units": "deltaC",
                                    "minimum": -10.0,
                                    "maximum": 20.0
                                }
                            },
                            "type": "object",
                            "required": [
                                "pair_delta_adjacent_air_temperature",
                                "pair_zeta_nondimensional_height"
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
                "pair_zeta_nondimensional_height": {
                    "field_name": "Pair Zeta Nondimensional Height",
                    "field_type": "n"
                },
                "pair_delta_adjacent_air_temperature": {
                    "field_name": "Pair Delta Adjacent Air Temperature",
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
                    "pair_zeta_nondimensional_height",
                    "pair_delta_adjacent_air_temperature"
                ]
            },
            "extensibles": [
                "pair_zeta_nondimensional_height",
                "pair_delta_adjacent_air_temperature"
            ],
            "extension": "pairs"
        },
        "type": "object",
        "memo": "Defines a distribution pattern for air temperatures relative to the current mean air temperature as a function of height. The height, referred to as Zeta, is nondimensional by normalizing with the zone ceiling height. Used in combination with RoomAir:TemperaturePattern:UserDefined.",
        "extensible_size": 2.0
    }
}
```
