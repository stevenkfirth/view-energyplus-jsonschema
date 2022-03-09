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
                        "MaximumTemperature",
                        "MinimumTemperature",
                        "Temperature"
                    ],
                    "default": "Temperature"
                },
                "reference_ground_temperature_object_type": {
                    "type": "string",
                    "enum": [
                        "Site:GroundTemperature:BuildingSurface",
                        "Site:GroundTemperature:Deep",
                        "Site:GroundTemperature:FCfactorMethod",
                        "Site:GroundTemperature:Shallow"
                    ]
                },
                "offset_temperature_difference": {
                    "type": "number",
                    "units": "deltaC"
                },
                "maximum_setpoint_temperature": {
                    "type": "number",
                    "units": "C"
                },
                "minimum_setpoint_temperature": {
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
            "reference_ground_temperature_object_type": {
                "field_name": "Reference Ground Temperature Object Type",
                "field_type": "a"
            },
            "offset_temperature_difference": {
                "field_name": "Offset Temperature Difference",
                "field_type": "n"
            },
            "maximum_setpoint_temperature": {
                "field_name": "Maximum Setpoint Temperature",
                "field_type": "n"
            },
            "minimum_setpoint_temperature": {
                "field_name": "Minimum Setpoint Temperature",
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
            "reference_ground_temperature_object_type",
            "offset_temperature_difference",
            "maximum_setpoint_temperature",
            "minimum_setpoint_temperature",
            "setpoint_node_or_nodelist_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "control_variable",
                "reference_ground_temperature_object_type",
                "setpoint_node_or_nodelist_name"
            ]
        },
        "numerics": {
            "fields": [
                "offset_temperature_difference",
                "maximum_setpoint_temperature",
                "minimum_setpoint_temperature"
            ]
        }
    },
    "type": "object",
    "memo": "This setpoint manager is used to place a temperature setpoint on a system node that is derived from a current ground temperature. The ground temperatures are specified in different Site:GroundTemperature:* objects and used during the simulation. This setpoint manager is primarily intended for condenser or plant loops using some type of ground heat exchanger."
}
```
