```
{
    "SetpointManager:OutdoorAirPretreat": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "control_variable": {
                        "type": "string",
                        "enum": [
                            "HumidityRatio",
                            "MaximumHumidityRatio",
                            "MinimumHumidityRatio",
                            "Temperature"
                        ]
                    },
                    "minimum_setpoint_temperature": {
                        "type": "number",
                        "units": "C",
                        "default": -99.0,
                        "note": "Applicable only if Control variable is Temperature"
                    },
                    "maximum_setpoint_temperature": {
                        "type": "number",
                        "units": "C",
                        "default": 99.0,
                        "note": "Applicable only if Control variable is Temperature"
                    },
                    "minimum_setpoint_humidity_ratio": {
                        "type": "number",
                        "units": "kgWater/kgDryAir",
                        "maximum": 1.0,
                        "default": 1e-05,
                        "note": "Applicable only if Control variable is MaximumHumidityRatio, MinimumHumidityRatio, or HumidityRatio - then minimum is 0.00001"
                    },
                    "maximum_setpoint_humidity_ratio": {
                        "type": "number",
                        "units": "kgWater/kgDryAir",
                        "maximum": 1.0,
                        "default": 1.0,
                        "note": "Applicable only if Control variable is MaximumHumidityRatio, MinimumHumidityRatio, or HumidityRatio - then minimum is 0.00001"
                    },
                    "reference_setpoint_node_name": {
                        "type": "string",
                        "note": "The current setpoint at this node is the desired condition for the Mixed Air Node This node must have a valid setpoint which has been set by another setpoint manager"
                    },
                    "mixed_air_stream_node_name": {
                        "type": "string",
                        "note": "Name of Mixed Air Node"
                    },
                    "outdoor_air_stream_node_name": {
                        "type": "string",
                        "note": "Name of Outdoor Air Stream Node"
                    },
                    "return_air_stream_node_name": {
                        "type": "string",
                        "note": "Name of Return Air Stream Node"
                    },
                    "setpoint_node_or_nodelist_name": {
                        "type": "string",
                        "note": "Node(s) at which the temperature or humidity ratio will be set"
                    }
                },
                "required": [
                    "mixed_air_stream_node_name",
                    "outdoor_air_stream_node_name",
                    "return_air_stream_node_name",
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
                "minimum_setpoint_temperature": {
                    "field_name": "Minimum Setpoint Temperature",
                    "field_type": "n"
                },
                "maximum_setpoint_temperature": {
                    "field_name": "Maximum Setpoint Temperature",
                    "field_type": "n"
                },
                "minimum_setpoint_humidity_ratio": {
                    "field_name": "Minimum Setpoint Humidity Ratio",
                    "field_type": "n"
                },
                "maximum_setpoint_humidity_ratio": {
                    "field_name": "Maximum Setpoint Humidity Ratio",
                    "field_type": "n"
                },
                "reference_setpoint_node_name": {
                    "field_name": "Reference Setpoint Node Name",
                    "field_type": "a"
                },
                "mixed_air_stream_node_name": {
                    "field_name": "Mixed Air Stream Node Name",
                    "field_type": "a"
                },
                "outdoor_air_stream_node_name": {
                    "field_name": "Outdoor Air Stream Node Name",
                    "field_type": "a"
                },
                "return_air_stream_node_name": {
                    "field_name": "Return Air Stream Node Name",
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
                "minimum_setpoint_temperature",
                "maximum_setpoint_temperature",
                "minimum_setpoint_humidity_ratio",
                "maximum_setpoint_humidity_ratio",
                "reference_setpoint_node_name",
                "mixed_air_stream_node_name",
                "outdoor_air_stream_node_name",
                "return_air_stream_node_name",
                "setpoint_node_or_nodelist_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "control_variable",
                    "reference_setpoint_node_name",
                    "mixed_air_stream_node_name",
                    "outdoor_air_stream_node_name",
                    "return_air_stream_node_name",
                    "setpoint_node_or_nodelist_name"
                ]
            },
            "numerics": {
                "fields": [
                    "minimum_setpoint_temperature",
                    "maximum_setpoint_temperature",
                    "minimum_setpoint_humidity_ratio",
                    "maximum_setpoint_humidity_ratio"
                ]
            }
        },
        "type": "object",
        "memo": "This setpoint manager determines the required conditions at the outdoor air stream node which will produce the reference setpoint condition at the mixed air node when mixed with the return air stream",
        "min_fields": 11.0
    }
}
```
