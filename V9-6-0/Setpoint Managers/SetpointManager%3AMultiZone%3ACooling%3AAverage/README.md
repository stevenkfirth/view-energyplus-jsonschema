```
{
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
            "setpoint_node_or_nodelist_name": {
                "field_name": "Setpoint Node or NodeList Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "hvac_air_loop_name",
            "minimum_setpoint_temperature",
            "maximum_setpoint_temperature",
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
                "minimum_setpoint_temperature",
                "maximum_setpoint_temperature"
            ]
        }
    },
    "type": "object",
    "memo": "This setpoint manager sets the average supply air temperature based on the cooling load requirements of all controlled zones in an air loop served by a central air-conditioner.",
    "min_fields": 5.0
}
```
