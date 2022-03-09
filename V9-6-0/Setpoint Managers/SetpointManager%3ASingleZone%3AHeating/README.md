```
{
    "SetpointManager:SingleZone:Heating": {
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
                    "minimum_supply_air_temperature": {
                        "type": "number",
                        "units": "C",
                        "default": -99.0
                    },
                    "maximum_supply_air_temperature": {
                        "type": "number",
                        "units": "C",
                        "default": 99.0
                    },
                    "control_zone_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ]
                    },
                    "zone_node_name": {
                        "type": "string"
                    },
                    "zone_inlet_node_name": {
                        "type": "string"
                    },
                    "setpoint_node_or_nodelist_name": {
                        "type": "string",
                        "note": "Node(s) at which the temperature will be set"
                    }
                },
                "required": [
                    "control_zone_name",
                    "zone_node_name",
                    "zone_inlet_node_name",
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
                "minimum_supply_air_temperature": {
                    "field_name": "Minimum Supply Air Temperature",
                    "field_type": "n"
                },
                "maximum_supply_air_temperature": {
                    "field_name": "Maximum Supply Air Temperature",
                    "field_type": "n"
                },
                "control_zone_name": {
                    "field_name": "Control Zone Name",
                    "field_type": "a"
                },
                "zone_node_name": {
                    "field_name": "Zone Node Name",
                    "field_type": "a"
                },
                "zone_inlet_node_name": {
                    "field_name": "Zone Inlet Node Name",
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
                "minimum_supply_air_temperature",
                "maximum_supply_air_temperature",
                "control_zone_name",
                "zone_node_name",
                "zone_inlet_node_name",
                "setpoint_node_or_nodelist_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "control_variable",
                    "control_zone_name",
                    "zone_node_name",
                    "zone_inlet_node_name",
                    "setpoint_node_or_nodelist_name"
                ]
            },
            "numerics": {
                "fields": [
                    "minimum_supply_air_temperature",
                    "maximum_supply_air_temperature"
                ]
            }
        },
        "type": "object",
        "memo": "This setpoint manager detects the control zone load to meet the current heating setpoint, zone inlet node flow rate, and zone node temperature, and calculates a setpoint temperature for the supply air that will satisfy the zone heating load for the control zone.",
        "min_fields": 8.0
    }
}
```
