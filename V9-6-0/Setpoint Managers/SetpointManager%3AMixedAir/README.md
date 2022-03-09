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
                "reference_setpoint_node_name": {
                    "type": "string"
                },
                "fan_inlet_node_name": {
                    "type": "string"
                },
                "fan_outlet_node_name": {
                    "type": "string"
                },
                "setpoint_node_or_nodelist_name": {
                    "type": "string",
                    "note": "Node(s) at which the temperature will be set"
                },
                "cooling_coil_inlet_node_name": {
                    "type": "string",
                    "note": "Optional field used to limit economizer operation to prevent freezing of DX cooling coil."
                },
                "cooling_coil_outlet_node_name": {
                    "type": "string",
                    "note": "Optional field used to limit economizer operation to prevent freezing of DX cooling coil."
                },
                "minimum_temperature_at_cooling_coil_outlet_node": {
                    "type": "number",
                    "units": "C",
                    "exclusiveMinimum": 0.0,
                    "default": 7.2,
                    "note": "Optional field used to limit economizer operation to prevent freezing of DX cooling coil."
                }
            },
            "required": [
                "reference_setpoint_node_name",
                "fan_inlet_node_name",
                "fan_outlet_node_name",
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
            "reference_setpoint_node_name": {
                "field_name": "Reference Setpoint Node Name",
                "field_type": "a"
            },
            "fan_inlet_node_name": {
                "field_name": "Fan Inlet Node Name",
                "field_type": "a"
            },
            "fan_outlet_node_name": {
                "field_name": "Fan Outlet Node Name",
                "field_type": "a"
            },
            "setpoint_node_or_nodelist_name": {
                "field_name": "Setpoint Node or NodeList Name",
                "field_type": "a"
            },
            "cooling_coil_inlet_node_name": {
                "field_name": "Cooling Coil Inlet Node Name",
                "field_type": "a"
            },
            "cooling_coil_outlet_node_name": {
                "field_name": "Cooling coil Outlet Node Name",
                "field_type": "a"
            },
            "minimum_temperature_at_cooling_coil_outlet_node": {
                "field_name": "Minimum Temperature at Cooling Coil Outlet Node",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "control_variable",
            "reference_setpoint_node_name",
            "fan_inlet_node_name",
            "fan_outlet_node_name",
            "setpoint_node_or_nodelist_name",
            "cooling_coil_inlet_node_name",
            "cooling_coil_outlet_node_name",
            "minimum_temperature_at_cooling_coil_outlet_node"
        ],
        "alphas": {
            "fields": [
                "name",
                "control_variable",
                "reference_setpoint_node_name",
                "fan_inlet_node_name",
                "fan_outlet_node_name",
                "setpoint_node_or_nodelist_name",
                "cooling_coil_inlet_node_name",
                "cooling_coil_outlet_node_name"
            ]
        },
        "numerics": {
            "fields": [
                "minimum_temperature_at_cooling_coil_outlet_node"
            ]
        }
    },
    "type": "object",
    "memo": "The Mixed Air Setpoint Manager is meant to be used in conjunction with a Controller:OutdoorAir object. This setpoint manager is used to establish a temperature setpoint at the mixed air node."
}
```
