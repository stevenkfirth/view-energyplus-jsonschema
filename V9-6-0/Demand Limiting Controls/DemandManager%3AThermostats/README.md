```
{
    "DemandManager:Thermostats": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "availability_schedule_name": {
                        "type": "string",
                        "note": "Availability schedule name for this system. Schedule value > 0 means the system is available. If this field is blank, the system is always available.",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "reset_control": {
                        "type": "string",
                        "enum": [
                            "Fixed",
                            "Off"
                        ]
                    },
                    "minimum_reset_duration": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "minutes",
                        "note": "If blank, duration defaults to the timestep"
                    },
                    "maximum_heating_setpoint_reset": {
                        "type": "number",
                        "units": "C"
                    },
                    "maximum_cooling_setpoint_reset": {
                        "type": "number",
                        "units": "C"
                    },
                    "reset_step_change": {
                        "type": "number",
                        "note": "Not yet implemented"
                    },
                    "selection_control": {
                        "type": "string",
                        "enum": [
                            "All",
                            "RotateMany",
                            "RotateOne"
                        ]
                    },
                    "rotation_duration": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "minutes",
                        "note": "If blank, duration defaults to the timestep"
                    },
                    "thermostats": {
                        "type": "array",
                        "items": {
                            "properties": {
                                "thermostat_name": {
                                    "type": "string",
                                    "note": "Enter the name of a ZoneControl:Thermostat object. if ZoneList option is used on the ZoneControl:Thermostat object, a single thermostat object from that assignment can be selected by entering <Zone Name><space><Global Thermostat Object Name>.",
                                    "data_type": "object_list",
                                    "object_list": [
                                        "ZoneControlThermostaticNames"
                                    ]
                                }
                            },
                            "type": "object",
                            "required": [
                                "thermostat_name"
                            ]
                        }
                    }
                },
                "required": [
                    "reset_control",
                    "maximum_heating_setpoint_reset",
                    "maximum_cooling_setpoint_reset",
                    "selection_control"
                ]
            }
        },
        "group": "Demand Limiting Controls",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "DemandManagerNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "availability_schedule_name": {
                    "field_name": "Availability Schedule Name",
                    "field_type": "a"
                },
                "reset_control": {
                    "field_name": "Reset Control",
                    "field_type": "a"
                },
                "minimum_reset_duration": {
                    "field_name": "Minimum Reset Duration",
                    "field_type": "n"
                },
                "maximum_heating_setpoint_reset": {
                    "field_name": "Maximum Heating Setpoint Reset",
                    "field_type": "n"
                },
                "maximum_cooling_setpoint_reset": {
                    "field_name": "Maximum Cooling Setpoint Reset",
                    "field_type": "n"
                },
                "reset_step_change": {
                    "field_name": "Reset Step Change",
                    "field_type": "n"
                },
                "selection_control": {
                    "field_name": "Selection Control",
                    "field_type": "a"
                },
                "rotation_duration": {
                    "field_name": "Rotation Duration",
                    "field_type": "n"
                },
                "thermostat_name": {
                    "field_name": "Thermostat Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "availability_schedule_name",
                "reset_control",
                "minimum_reset_duration",
                "maximum_heating_setpoint_reset",
                "maximum_cooling_setpoint_reset",
                "reset_step_change",
                "selection_control",
                "rotation_duration"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "reset_control",
                    "selection_control"
                ],
                "extensions": [
                    "thermostat_name"
                ]
            },
            "numerics": {
                "fields": [
                    "minimum_reset_duration",
                    "maximum_heating_setpoint_reset",
                    "maximum_cooling_setpoint_reset",
                    "reset_step_change",
                    "rotation_duration"
                ]
            },
            "extensibles": [
                "thermostat_name"
            ],
            "extension": "thermostats"
        },
        "type": "object",
        "memo": "used for demand limiting ZoneControl:Thermostat objects.",
        "extensible_size": 1.0
    }
}
```
