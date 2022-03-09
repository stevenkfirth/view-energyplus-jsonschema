```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "cooling_stage_on_supply_air_setpoint_temperature": {
                    "type": "number",
                    "note": "This is the setpoint value applied when cooling device is to cycle ON",
                    "units": "C",
                    "default": -99.0
                },
                "cooling_stage_off_supply_air_setpoint_temperature": {
                    "type": "number",
                    "note": "This is the setpoint value applied when cooling device is to cycle OFF",
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
                "setpoint_node_or_nodelist_name": {
                    "type": "string",
                    "note": "Node(s) at which the temperature will be set"
                }
            },
            "required": [
                "control_zone_name",
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
            "cooling_stage_on_supply_air_setpoint_temperature": {
                "field_name": "Cooling Stage On Supply Air Setpoint Temperature",
                "field_type": "n"
            },
            "cooling_stage_off_supply_air_setpoint_temperature": {
                "field_name": "Cooling Stage Off Supply Air Setpoint Temperature",
                "field_type": "n"
            },
            "control_zone_name": {
                "field_name": "Control Zone Name",
                "field_type": "a"
            },
            "setpoint_node_or_nodelist_name": {
                "field_name": "Setpoint Node or NodeList Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "cooling_stage_on_supply_air_setpoint_temperature",
            "cooling_stage_off_supply_air_setpoint_temperature",
            "control_zone_name",
            "setpoint_node_or_nodelist_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "control_zone_name",
                "setpoint_node_or_nodelist_name"
            ]
        },
        "numerics": {
            "fields": [
                "cooling_stage_on_supply_air_setpoint_temperature",
                "cooling_stage_off_supply_air_setpoint_temperature"
            ]
        }
    },
    "type": "object",
    "memo": "This object can be used with CoilSystem:Cooling:DX to model on/off cycling control of single stage air systems. Setpoints are modulated to run coil full on or full off depending on zone conditions. Intended for use with ZoneControl:Thermostat:StagedDualSetpoint",
    "min_fields": 5.0
}
```
