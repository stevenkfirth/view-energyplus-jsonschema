```
{
    "SetpointManager:FollowSystemNodeTemperature": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "control_variable": {
                        "type": "string",
                        "enum": [
                            "",
                            "MaximumTemperature",
                            "MinimumTemperature",
                            "Temperature"
                        ],
                        "default": "Temperature"
                    },
                    "reference_node_name": {
                        "type": "string"
                    },
                    "reference_temperature_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "NodeDryBulb",
                            "NodeWetBulb"
                        ],
                        "default": "NodeDryBulb"
                    },
                    "offset_temperature_difference": {
                        "type": "number",
                        "units": "deltaC"
                    },
                    "maximum_limit_setpoint_temperature": {
                        "type": "number",
                        "units": "C"
                    },
                    "minimum_limit_setpoint_temperature": {
                        "type": "number",
                        "units": "C"
                    },
                    "setpoint_node_or_nodelist_name": {
                        "type": "string",
                        "note": "Node(s) at which control variable will be set"
                    }
                },
                "required": [
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
                "reference_node_name": {
                    "field_name": "Reference Node Name",
                    "field_type": "a"
                },
                "reference_temperature_type": {
                    "field_name": "Reference Temperature Type",
                    "field_type": "a"
                },
                "offset_temperature_difference": {
                    "field_name": "Offset Temperature Difference",
                    "field_type": "n"
                },
                "maximum_limit_setpoint_temperature": {
                    "field_name": "Maximum Limit Setpoint Temperature",
                    "field_type": "n"
                },
                "minimum_limit_setpoint_temperature": {
                    "field_name": "Minimum Limit Setpoint Temperature",
                    "field_type": "n"
                },
                "setpoint_node_or_nodelist_name": {
                    "field_name": "Setpoint Node or NodeList Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "control_variable",
                "reference_node_name",
                "reference_temperature_type",
                "offset_temperature_difference",
                "maximum_limit_setpoint_temperature",
                "minimum_limit_setpoint_temperature",
                "setpoint_node_or_nodelist_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "control_variable",
                    "reference_node_name",
                    "reference_temperature_type",
                    "setpoint_node_or_nodelist_name"
                ]
            },
            "numerics": {
                "fields": [
                    "offset_temperature_difference",
                    "maximum_limit_setpoint_temperature",
                    "minimum_limit_setpoint_temperature"
                ]
            }
        },
        "type": "object",
        "memo": "This setpoint manager is used to place a temperature setpoint on a system node that is derived from the current temperatures at a separate system node. The current value of the temperature at a reference node is obtained and used to generate setpoint on a second system node. If the reference node is also designated to be an outdoor air (intake) node, then this setpoint manager can be used to follow outdoor air conditions that are adjusted for altitude."
    }
}
```
