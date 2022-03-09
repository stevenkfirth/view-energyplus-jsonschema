```
{
    "SetpointManager:OutdoorAirReset": {
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
                    "setpoint_at_outdoor_low_temperature": {
                        "type": "number",
                        "units": "C"
                    },
                    "outdoor_low_temperature": {
                        "type": "number",
                        "units": "C"
                    },
                    "setpoint_at_outdoor_high_temperature": {
                        "type": "number",
                        "units": "C"
                    },
                    "outdoor_high_temperature": {
                        "type": "number",
                        "units": "C"
                    },
                    "setpoint_node_or_nodelist_name": {
                        "type": "string",
                        "note": "Node(s) at which temperature will be set"
                    },
                    "schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "Optional input. Schedule allows scheduling of the outdoor air reset rule - a schedule value of 1 means use the first rule; a value of 2 means use the second rule."
                    },
                    "setpoint_at_outdoor_low_temperature_2": {
                        "type": "number",
                        "note": "2nd outdoor air temperature reset rule",
                        "units": "C"
                    },
                    "outdoor_low_temperature_2": {
                        "type": "number",
                        "note": "2nd outdoor air temperature reset rule",
                        "units": "C"
                    },
                    "setpoint_at_outdoor_high_temperature_2": {
                        "type": "number",
                        "note": "2nd outdoor air temperature reset rule",
                        "units": "C"
                    },
                    "outdoor_high_temperature_2": {
                        "type": "number",
                        "note": "2nd outdoor air temperature reset rule",
                        "units": "C"
                    }
                },
                "required": [
                    "setpoint_at_outdoor_low_temperature",
                    "outdoor_low_temperature",
                    "setpoint_at_outdoor_high_temperature",
                    "outdoor_high_temperature",
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
                "setpoint_at_outdoor_low_temperature": {
                    "field_name": "Setpoint at Outdoor Low Temperature",
                    "field_type": "n"
                },
                "outdoor_low_temperature": {
                    "field_name": "Outdoor Low Temperature",
                    "field_type": "n"
                },
                "setpoint_at_outdoor_high_temperature": {
                    "field_name": "Setpoint at Outdoor High Temperature",
                    "field_type": "n"
                },
                "outdoor_high_temperature": {
                    "field_name": "Outdoor High Temperature",
                    "field_type": "n"
                },
                "setpoint_node_or_nodelist_name": {
                    "field_name": "Setpoint Node or NodeList Name",
                    "field_type": "a"
                },
                "schedule_name": {
                    "field_name": "Schedule Name",
                    "field_type": "a"
                },
                "setpoint_at_outdoor_low_temperature_2": {
                    "field_name": "Setpoint at Outdoor Low Temperature 2",
                    "field_type": "n"
                },
                "outdoor_low_temperature_2": {
                    "field_name": "Outdoor Low Temperature 2",
                    "field_type": "n"
                },
                "setpoint_at_outdoor_high_temperature_2": {
                    "field_name": "Setpoint at Outdoor High Temperature 2",
                    "field_type": "n"
                },
                "outdoor_high_temperature_2": {
                    "field_name": "Outdoor High Temperature 2",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "control_variable",
                "setpoint_at_outdoor_low_temperature",
                "outdoor_low_temperature",
                "setpoint_at_outdoor_high_temperature",
                "outdoor_high_temperature",
                "setpoint_node_or_nodelist_name",
                "schedule_name",
                "setpoint_at_outdoor_low_temperature_2",
                "outdoor_low_temperature_2",
                "setpoint_at_outdoor_high_temperature_2",
                "outdoor_high_temperature_2"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "control_variable",
                    "setpoint_node_or_nodelist_name",
                    "schedule_name"
                ]
            },
            "numerics": {
                "fields": [
                    "setpoint_at_outdoor_low_temperature",
                    "outdoor_low_temperature",
                    "setpoint_at_outdoor_high_temperature",
                    "outdoor_high_temperature",
                    "setpoint_at_outdoor_low_temperature_2",
                    "outdoor_low_temperature_2",
                    "setpoint_at_outdoor_high_temperature_2",
                    "outdoor_high_temperature_2"
                ]
            }
        },
        "type": "object",
        "memo": "This Setpoint Manager is used to place a setpoint temperature on system node according to the outdoor air temperature using a reset rule. The outdoor air temperature is obtained from the weather information during the simulation."
    }
}
```
