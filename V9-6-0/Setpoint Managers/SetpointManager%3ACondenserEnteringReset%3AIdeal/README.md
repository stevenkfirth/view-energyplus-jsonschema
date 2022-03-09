```
{
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
                "minimum_lift": {
                    "type": "number",
                    "units": "deltaC",
                    "default": 11.1
                },
                "maximum_condenser_entering_water_temperature": {
                    "type": "number",
                    "units": "C",
                    "default": 32.0
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
            "minimum_lift": {
                "field_name": "Minimum Lift",
                "field_type": "n"
            },
            "maximum_condenser_entering_water_temperature": {
                "field_name": "Maximum Condenser Entering Water Temperature",
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
            "minimum_lift",
            "maximum_condenser_entering_water_temperature",
            "setpoint_node_or_nodelist_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "control_variable",
                "setpoint_node_or_nodelist_name"
            ]
        },
        "numerics": {
            "fields": [
                "minimum_lift",
                "maximum_condenser_entering_water_temperature"
            ]
        }
    },
    "type": "object",
    "memo": "This setpoint manager determine the ideal optimum condenser entering water temperature setpoint for a given timestep.",
    "min_fields": 5.0
}
```
