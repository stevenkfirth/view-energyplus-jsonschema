```
{
    "SetpointManager:Warmest": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "control_variable": {
                        "type": "string",
                        "enum": [
                            "",
                            "Temperature"
                        ],
                        "default": "Temperature"
                    },
                    "hvac_air_loop_name": {
                        "type": "string",
                        "note": "Enter the name of an AirLoopHVAC object",
                        "data_type": "object_list",
                        "object_list": [
                            "AirPrimaryLoops"
                        ]
                    },
                    "minimum_setpoint_temperature": {
                        "type": "number",
                        "units": "C",
                        "exclusiveMinimum": 0.0,
                        "default": 12.0
                    },
                    "maximum_setpoint_temperature": {
                        "type": "number",
                        "units": "C",
                        "exclusiveMinimum": 0.0,
                        "default": 18.0
                    },
                    "strategy": {
                        "type": "string",
                        "enum": [
                            "",
                            "MaximumTemperature"
                        ],
                        "default": "MaximumTemperature"
                    },
                    "setpoint_node_or_nodelist_name": {
                        "type": "string",
                        "note": "Node(s) at which the temperature will be set"
                    }
                },
                "required": [
                    "hvac_air_loop_name",
                    "setpoint_node_or_nodelist_name"
                ]
            }
        },
        "group": "Setpoint Managers",
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
                "control_variable": {
                    "field_name": "Control Variable",
                    "field_type": "a"
                },
                "hvac_air_loop_name": {
                    "field_name": "HVAC Air Loop Name",
                    "field_type": "a"
                },
                "minimum_setpoint_temperature": {
                    "field_name": "Minimum Setpoint Temperature",
                    "field_type": "n"
                },
                "maximum_setpoint_temperature": {
                    "field_name": "Maximum Setpoint Temperature",
                    "field_type": "n"
                },
                "strategy": {
                    "field_name": "Strategy",
                    "field_type": "a"
                },
                "setpoint_node_or_nodelist_name": {
                    "field_name": "Setpoint Node or NodeList Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "control_variable",
                "hvac_air_loop_name",
                "minimum_setpoint_temperature",
                "maximum_setpoint_temperature",
                "strategy",
                "setpoint_node_or_nodelist_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "control_variable",
                    "hvac_air_loop_name",
                    "strategy",
                    "setpoint_node_or_nodelist_name"
                ]
            },
            "numerics": {
                "fields": [
                    "minimum_setpoint_temperature",
                    "maximum_setpoint_temperature"
                ]
            }
        },
        "type": "object",
        "memo": "This SetpointManager resets the cooling supply air temperature of a central forced air HVAC system according to the cooling demand of the warmest zone."
    }
}
```
