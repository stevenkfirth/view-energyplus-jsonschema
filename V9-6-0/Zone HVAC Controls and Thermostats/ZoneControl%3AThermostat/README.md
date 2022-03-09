```
{
    "ZoneControl:Thermostat": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "zone_or_zonelist_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneAndZoneListNames"
                        ]
                    },
                    "control_type_schedule_name": {
                        "type": "string",
                        "note": "This schedule contains appropriate control types for thermostat. Control types are integers: 0 - Uncontrolled (floating, no thermostat), 1 = ThermostatSetpoint:SingleHeating, 2 = ThermostatSetpoint:SingleCooling, 3 = ThermostatSetpoint:SingleHeatingOrCooling, 4 = ThermostatSetpoint:DualSetpoint",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "control_1_object_type": {
                        "type": "string",
                        "enum": [
                            "ThermostatSetpoint:DualSetpoint",
                            "ThermostatSetpoint:SingleCooling",
                            "ThermostatSetpoint:SingleHeating",
                            "ThermostatSetpoint:SingleHeatingOrCooling"
                        ]
                    },
                    "control_1_name": {
                        "type": "string",
                        "note": "Control names are names of individual control objects (e.g. ThermostatSetpoint:SingleHeating) Schedule values in these objects list actual setpoint temperatures for the control types",
                        "data_type": "object_list",
                        "object_list": [
                            "ControlTypeNames"
                        ]
                    },
                    "control_2_object_type": {
                        "type": "string",
                        "enum": [
                            "ThermostatSetpoint:DualSetpoint",
                            "ThermostatSetpoint:SingleCooling",
                            "ThermostatSetpoint:SingleHeating",
                            "ThermostatSetpoint:SingleHeatingOrCooling"
                        ]
                    },
                    "control_2_name": {
                        "type": "string",
                        "note": "Control names are names of individual control objects (e.g. ThermostatSetpoint:SingleHeating) Schedule values in these objects list actual setpoint temperatures for the control types",
                        "data_type": "object_list",
                        "object_list": [
                            "ControlTypeNames"
                        ]
                    },
                    "control_3_object_type": {
                        "type": "string",
                        "enum": [
                            "ThermostatSetpoint:DualSetpoint",
                            "ThermostatSetpoint:SingleCooling",
                            "ThermostatSetpoint:SingleHeating",
                            "ThermostatSetpoint:SingleHeatingOrCooling"
                        ]
                    },
                    "control_3_name": {
                        "type": "string",
                        "note": "Control names are names of individual control objects (e.g. ThermostatSetpoint:SingleHeating) Schedule values in these objects list actual setpoint temperatures for the control types",
                        "data_type": "object_list",
                        "object_list": [
                            "ControlTypeNames"
                        ]
                    },
                    "control_4_object_type": {
                        "type": "string",
                        "enum": [
                            "ThermostatSetpoint:DualSetpoint",
                            "ThermostatSetpoint:SingleCooling",
                            "ThermostatSetpoint:SingleHeating",
                            "ThermostatSetpoint:SingleHeatingOrCooling"
                        ]
                    },
                    "control_4_name": {
                        "type": "string",
                        "note": "Control names are names of individual control objects (e.g. ThermostatSetpoint:SingleHeating) Schedule values in these objects list actual setpoint temperatures for the control types",
                        "data_type": "object_list",
                        "object_list": [
                            "ControlTypeNames"
                        ]
                    },
                    "temperature_difference_between_cutout_and_setpoint": {
                        "type": "number",
                        "note": "This optional choice field provides a temperature difference between cut-out temperature and setpoint. The difference is used to adjust to heating or cooling setpoint based on control types.",
                        "units": "deltaC",
                        "minimum": 0.0,
                        "default": 0.0
                    }
                },
                "required": [
                    "zone_or_zonelist_name",
                    "control_type_schedule_name",
                    "control_1_object_type",
                    "control_1_name"
                ]
            }
        },
        "group": "Zone HVAC Controls and Thermostats",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "ZoneControlThermostaticNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "zone_or_zonelist_name": {
                    "field_name": "Zone or ZoneList Name",
                    "field_type": "a"
                },
                "control_type_schedule_name": {
                    "field_name": "Control Type Schedule Name",
                    "field_type": "a"
                },
                "control_1_object_type": {
                    "field_name": "Control 1 Object Type",
                    "field_type": "a"
                },
                "control_1_name": {
                    "field_name": "Control 1 Name",
                    "field_type": "a"
                },
                "control_2_object_type": {
                    "field_name": "Control 2 Object Type",
                    "field_type": "a"
                },
                "control_2_name": {
                    "field_name": "Control 2 Name",
                    "field_type": "a"
                },
                "control_3_object_type": {
                    "field_name": "Control 3 Object Type",
                    "field_type": "a"
                },
                "control_3_name": {
                    "field_name": "Control 3 Name",
                    "field_type": "a"
                },
                "control_4_object_type": {
                    "field_name": "Control 4 Object Type",
                    "field_type": "a"
                },
                "control_4_name": {
                    "field_name": "Control 4 Name",
                    "field_type": "a"
                },
                "temperature_difference_between_cutout_and_setpoint": {
                    "field_name": "Temperature Difference Between Cutout And Setpoint",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "zone_or_zonelist_name",
                "control_type_schedule_name",
                "control_1_object_type",
                "control_1_name",
                "control_2_object_type",
                "control_2_name",
                "control_3_object_type",
                "control_3_name",
                "control_4_object_type",
                "control_4_name",
                "temperature_difference_between_cutout_and_setpoint"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "zone_or_zonelist_name",
                    "control_type_schedule_name",
                    "control_1_object_type",
                    "control_1_name",
                    "control_2_object_type",
                    "control_2_name",
                    "control_3_object_type",
                    "control_3_name",
                    "control_4_object_type",
                    "control_4_name"
                ]
            },
            "numerics": {
                "fields": [
                    "temperature_difference_between_cutout_and_setpoint"
                ]
            }
        },
        "type": "object",
        "memo": "Define the Thermostat settings for a zone or list of zones. If you use a ZoneList in the Zone or ZoneList name field then this definition applies to all the zones in the ZoneList."
    }
}
```
