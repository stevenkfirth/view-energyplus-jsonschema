```
{
    "SetpointManager:MultiZone:Humidity:Minimum": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "hvac_air_loop_name": {
                        "type": "string",
                        "note": "Enter the name of an AirLoopHVAC object",
                        "data_type": "object_list",
                        "object_list": [
                            "AirPrimaryLoops"
                        ]
                    },
                    "minimum_setpoint_humidity_ratio": {
                        "type": "number",
                        "units": "kgWater/kgDryAir",
                        "exclusiveMinimum": 0.0,
                        "default": 0.005
                    },
                    "maximum_setpoint_humidity_ratio": {
                        "type": "number",
                        "units": "kgWater/kgDryAir",
                        "exclusiveMinimum": 0.0,
                        "default": 0.012
                    },
                    "setpoint_node_or_nodelist_name": {
                        "type": "string",
                        "note": "Node(s) at which the humidity ratio will be set"
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
                "hvac_air_loop_name": {
                    "field_name": "HVAC Air Loop Name",
                    "field_type": "a"
                },
                "minimum_setpoint_humidity_ratio": {
                    "field_name": "Minimum Setpoint Humidity Ratio",
                    "field_type": "n"
                },
                "maximum_setpoint_humidity_ratio": {
                    "field_name": "Maximum Setpoint Humidity Ratio",
                    "field_type": "n"
                },
                "setpoint_node_or_nodelist_name": {
                    "field_name": "Setpoint Node or NodeList Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "hvac_air_loop_name",
                "minimum_setpoint_humidity_ratio",
                "maximum_setpoint_humidity_ratio",
                "setpoint_node_or_nodelist_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "hvac_air_loop_name",
                    "setpoint_node_or_nodelist_name"
                ]
            },
            "numerics": {
                "fields": [
                    "minimum_setpoint_humidity_ratio",
                    "maximum_setpoint_humidity_ratio"
                ]
            }
        },
        "type": "object",
        "memo": "This setpoint manager sets the minimum supply air humidity ratio based on humidification requirements of a controlled zone with critical humidity ratio setpoint (i.e., a zone with the highest humidity ratio setpoint) in an air loop served by a central air-conditioner.",
        "min_fields": 5.0
    }
}
```
