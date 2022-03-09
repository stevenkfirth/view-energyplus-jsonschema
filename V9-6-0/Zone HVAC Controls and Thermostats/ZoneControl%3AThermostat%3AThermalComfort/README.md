```
{
    "ZoneControl:Thermostat:ThermalComfort": {
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
                    "averaging_method": {
                        "type": "string",
                        "note": "The method used to calculate thermal comfort dry-bulb temperature setpoint for multiple people objects in a zone",
                        "enum": [
                            "",
                            "ObjectAverage",
                            "PeopleAverage",
                            "SpecificObject"
                        ],
                        "default": "PeopleAverage"
                    },
                    "specific_people_name": {
                        "type": "string",
                        "note": "Used only when Averaging Method = SpecificObject in the previous field.",
                        "data_type": "object_list",
                        "object_list": [
                            "PeopleNames"
                        ]
                    },
                    "minimum_dry_bulb_temperature_setpoint": {
                        "type": "number",
                        "units": "C",
                        "minimum": 0.0,
                        "maximum": 50.0,
                        "default": 0.0
                    },
                    "maximum_dry_bulb_temperature_setpoint": {
                        "type": "number",
                        "units": "C",
                        "minimum": 0.0,
                        "maximum": 50.0,
                        "default": 50.0
                    },
                    "thermal_comfort_control_type_schedule_name": {
                        "type": "string",
                        "note": "The Thermal Comfort Control Type Schedule contains values that are appropriate control types. Thermal Comfort Control types are integers: 0 - Uncontrolled (floating), 1 = ThermostatSetpoint:ThermalComfort:Fanger:SingleHeating 2 = ThermostatSetpoint:ThermalComfort:Fanger:SingleCooling 3 = ThermostatSetpoint:ThermalComfort:Fanger:SingleHeatingOrCooling 4 = ThermostatSetpoint:ThermalComfort:Fanger:DualSetpoint",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "thermal_comfort_control_1_object_type": {
                        "type": "string",
                        "enum": [
                            "ThermostatSetpoint:ThermalComfort:Fanger:DualSetpoint",
                            "ThermostatSetpoint:ThermalComfort:Fanger:SingleCooling",
                            "ThermostatSetpoint:ThermalComfort:Fanger:SingleHeating",
                            "ThermostatSetpoint:ThermalComfort:Fanger:SingleHeatingOrCooling"
                        ]
                    },
                    "thermal_comfort_control_1_name": {
                        "type": "string",
                        "note": "Control type names are names for individual control type objects. Schedule values in these objects list actual setpoint temperatures for the control types",
                        "data_type": "object_list",
                        "object_list": [
                            "ThermalComfortControlTypeNames"
                        ]
                    },
                    "thermal_comfort_control_2_object_type": {
                        "type": "string",
                        "enum": [
                            "ThermostatSetpoint:ThermalComfort:Fanger:DualSetpoint",
                            "ThermostatSetpoint:ThermalComfort:Fanger:SingleCooling",
                            "ThermostatSetpoint:ThermalComfort:Fanger:SingleHeating",
                            "ThermostatSetpoint:ThermalComfort:Fanger:SingleHeatingOrCooling"
                        ]
                    },
                    "thermal_comfort_control_2_name": {
                        "type": "string",
                        "note": "Control Type names are names for individual control type objects. Schedule values in these objects list actual setpoint temperatures for the control types",
                        "data_type": "object_list",
                        "object_list": [
                            "ThermalComfortControlTypeNames"
                        ]
                    },
                    "thermal_comfort_control_3_object_type": {
                        "type": "string",
                        "enum": [
                            "ThermostatSetpoint:ThermalComfort:Fanger:DualSetpoint",
                            "ThermostatSetpoint:ThermalComfort:Fanger:SingleCooling",
                            "ThermostatSetpoint:ThermalComfort:Fanger:SingleHeating",
                            "ThermostatSetpoint:ThermalComfort:Fanger:SingleHeatingOrCooling"
                        ]
                    },
                    "thermal_comfort_control_3_name": {
                        "type": "string",
                        "note": "Control type names are names for individual control type objects. Schedule values in these objects list actual setpoint temperatures for the control types",
                        "data_type": "object_list",
                        "object_list": [
                            "ThermalComfortControlTypeNames"
                        ]
                    },
                    "thermal_comfort_control_4_object_type": {
                        "type": "string",
                        "enum": [
                            "ThermostatSetpoint:ThermalComfort:Fanger:DualSetpoint",
                            "ThermostatSetpoint:ThermalComfort:Fanger:SingleCooling",
                            "ThermostatSetpoint:ThermalComfort:Fanger:SingleHeating",
                            "ThermostatSetpoint:ThermalComfort:Fanger:SingleHeatingOrCooling"
                        ]
                    },
                    "thermal_comfort_control_4_name": {
                        "type": "string",
                        "note": "Control type names are names for individual control type objects. Schedule values in these objects list actual setpoint temperatures for the control types",
                        "data_type": "object_list",
                        "object_list": [
                            "ThermalComfortControlTypeNames"
                        ]
                    }
                },
                "required": [
                    "zone_or_zonelist_name",
                    "thermal_comfort_control_type_schedule_name",
                    "thermal_comfort_control_1_object_type",
                    "thermal_comfort_control_1_name"
                ]
            }
        },
        "group": "Zone HVAC Controls and Thermostats",
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
                "zone_or_zonelist_name": {
                    "field_name": "Zone or ZoneList Name",
                    "field_type": "a"
                },
                "averaging_method": {
                    "field_name": "Averaging Method",
                    "field_type": "a"
                },
                "specific_people_name": {
                    "field_name": "Specific People Name",
                    "field_type": "a"
                },
                "minimum_dry_bulb_temperature_setpoint": {
                    "field_name": "Minimum Dry-Bulb Temperature Setpoint",
                    "field_type": "n"
                },
                "maximum_dry_bulb_temperature_setpoint": {
                    "field_name": "Maximum Dry-Bulb Temperature Setpoint",
                    "field_type": "n"
                },
                "thermal_comfort_control_type_schedule_name": {
                    "field_name": "Thermal Comfort Control Type Schedule Name",
                    "field_type": "a"
                },
                "thermal_comfort_control_1_object_type": {
                    "field_name": "Thermal Comfort Control 1 Object Type",
                    "field_type": "a"
                },
                "thermal_comfort_control_1_name": {
                    "field_name": "Thermal Comfort Control 1 Name",
                    "field_type": "a"
                },
                "thermal_comfort_control_2_object_type": {
                    "field_name": "Thermal Comfort Control 2 Object Type",
                    "field_type": "a"
                },
                "thermal_comfort_control_2_name": {
                    "field_name": "Thermal Comfort Control 2 Name",
                    "field_type": "a"
                },
                "thermal_comfort_control_3_object_type": {
                    "field_name": "Thermal Comfort Control 3 Object Type",
                    "field_type": "a"
                },
                "thermal_comfort_control_3_name": {
                    "field_name": "Thermal Comfort Control 3 Name",
                    "field_type": "a"
                },
                "thermal_comfort_control_4_object_type": {
                    "field_name": "Thermal Comfort Control 4 Object Type",
                    "field_type": "a"
                },
                "thermal_comfort_control_4_name": {
                    "field_name": "Thermal Comfort Control 4 Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "zone_or_zonelist_name",
                "averaging_method",
                "specific_people_name",
                "minimum_dry_bulb_temperature_setpoint",
                "maximum_dry_bulb_temperature_setpoint",
                "thermal_comfort_control_type_schedule_name",
                "thermal_comfort_control_1_object_type",
                "thermal_comfort_control_1_name",
                "thermal_comfort_control_2_object_type",
                "thermal_comfort_control_2_name",
                "thermal_comfort_control_3_object_type",
                "thermal_comfort_control_3_name",
                "thermal_comfort_control_4_object_type",
                "thermal_comfort_control_4_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "zone_or_zonelist_name",
                    "averaging_method",
                    "specific_people_name",
                    "thermal_comfort_control_type_schedule_name",
                    "thermal_comfort_control_1_object_type",
                    "thermal_comfort_control_1_name",
                    "thermal_comfort_control_2_object_type",
                    "thermal_comfort_control_2_name",
                    "thermal_comfort_control_3_object_type",
                    "thermal_comfort_control_3_name",
                    "thermal_comfort_control_4_object_type",
                    "thermal_comfort_control_4_name"
                ]
            },
            "numerics": {
                "fields": [
                    "minimum_dry_bulb_temperature_setpoint",
                    "maximum_dry_bulb_temperature_setpoint"
                ]
            }
        },
        "type": "object",
        "memo": "If you use a ZoneList in the Zone or ZoneList name field then this definition applies to all the zones in the ZoneList.",
        "min_fields": 9.0
    }
}
```
