```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "number_of_speeds_for_heating": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 10.0,
                    "note": "Used only for Multi speed coils Enter the number of the following sets of data for air flow rates."
                },
                "number_of_speeds_for_cooling": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 10.0,
                    "note": "Used only for Multi speed coils Enter the number of the following sets of data for air flow rates."
                },
                "single_mode_operation": {
                    "type": "string",
                    "enum": [
                        "",
                        "No",
                        "Yes"
                    ],
                    "default": "No",
                    "note": "Controls coil operation during each HVAC timestep. This choice does not apply to speed 1 operation. Yes = operate at the highest speed possible without exceeding the current load. No = allow operation at the average of two adjacent speeds to match the current load."
                },
                "no_load_supply_air_flow_rate_ratio": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 1.0,
                    "note": "Used to define the no load operating air flow rate when the system fan is specified to operate continuously."
                },
                "flow_ratios": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "heating_speed_supply_air_flow_ratio": {
                                "note": "Used only for Multi speed coils Enter the lowest operating supply air flow ratio during heating operation or specify autosize. This value is the ratio of air flow at this speed to the maximum air flow rate.",
                                "anyOf": [
                                    {
                                        "type": "number",
                                        "exclusiveMinimum": 0.0
                                    },
                                    {
                                        "type": "string",
                                        "enum": [
                                            "Autosize"
                                        ]
                                    }
                                ]
                            },
                            "cooling_speed_supply_air_flow_ratio": {
                                "note": "Used only for Multi speed coils Enter the lowest operating supply air flow ratio during cooling operation or specify autosize. This value is the ratio of air flow at this speed to the maximum air flow rate.",
                                "anyOf": [
                                    {
                                        "type": "number",
                                        "exclusiveMinimum": 0.0
                                    },
                                    {
                                        "type": "string",
                                        "enum": [
                                            "Autosize"
                                        ]
                                    }
                                ]
                            }
                        },
                        "type": "object",
                        "required": [
                            "cooling_speed_supply_air_flow_ratio",
                            "heating_speed_supply_air_flow_ratio"
                        ]
                    }
                }
            },
            "required": [
                "number_of_speeds_for_heating",
                "number_of_speeds_for_cooling"
            ]
        }
    },
    "group": "Unitary Equipment",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "UnitarySystemPerformaceNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "number_of_speeds_for_heating": {
                "field_name": "Number of Speeds for Heating",
                "field_type": "n"
            },
            "number_of_speeds_for_cooling": {
                "field_name": "Number of Speeds for Cooling",
                "field_type": "n"
            },
            "single_mode_operation": {
                "field_name": "Single Mode Operation",
                "field_type": "a"
            },
            "no_load_supply_air_flow_rate_ratio": {
                "field_name": "No Load Supply Air Flow Rate Ratio",
                "field_type": "n"
            },
            "heating_speed_supply_air_flow_ratio": {
                "field_name": "Heating Speed Supply Air Flow Ratio",
                "field_type": "n"
            },
            "cooling_speed_supply_air_flow_ratio": {
                "field_name": "Cooling Speed Supply Air Flow Ratio",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "number_of_speeds_for_heating",
            "number_of_speeds_for_cooling",
            "single_mode_operation",
            "no_load_supply_air_flow_rate_ratio"
        ],
        "alphas": {
            "fields": [
                "name",
                "single_mode_operation"
            ]
        },
        "numerics": {
            "fields": [
                "number_of_speeds_for_heating",
                "number_of_speeds_for_cooling",
                "no_load_supply_air_flow_rate_ratio"
            ],
            "extensions": [
                "heating_speed_supply_air_flow_ratio",
                "cooling_speed_supply_air_flow_ratio"
            ]
        },
        "extensibles": [
            "heating_speed_supply_air_flow_ratio",
            "cooling_speed_supply_air_flow_ratio"
        ],
        "extension": "flow_ratios"
    },
    "type": "object",
    "memo": "The UnitarySystemPerformance object is used to specify the air flow ratio at each operating speed. This object is primarily used for multispeed DX and water coils to allow operation at alternate flow rates different from those specified in the coil object.",
    "extensible_size": 2.0
}
```
