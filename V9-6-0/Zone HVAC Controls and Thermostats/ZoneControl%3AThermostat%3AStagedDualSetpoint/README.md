```
{
    "ZoneControl:Thermostat:StagedDualSetpoint": {
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
                    "number_of_heating_stages": {
                        "type": "number",
                        "minimum": 1.0,
                        "maximum": 4.0,
                        "note": "Enter the number of the following sets of data for heating temperature offset"
                    },
                    "heating_temperature_setpoint_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "heating_throttling_temperature_range": {
                        "type": "number",
                        "units": "deltaC",
                        "minimum": 0.0,
                        "default": 1.1
                    },
                    "stage_1_heating_temperature_offset": {
                        "type": "number",
                        "units": "deltaC",
                        "maximum": 0.0,
                        "note": "The heating temperature offset is used to determine heating stage number for multi stage equipment. When the temperature difference of the heating setpoint and the controlled zone temperature at previous time step is less than Stage 1 value and greater than Stage 2 value, the stage number is 1."
                    },
                    "stage_2_heating_temperature_offset": {
                        "type": "number",
                        "units": "deltaC",
                        "maximum": 0.0,
                        "note": "The heating temperature offset is used to determine heating stage number for multi stage equipment. When the temperature difference of the heating setpoint and the controlled zone temperature at previous time step is less than Stage 2 value and greater than Stage 3 value, the stage number is 2. The value of this field has to be less the value at the previous field."
                    },
                    "stage_3_heating_temperature_offset": {
                        "type": "number",
                        "units": "deltaC",
                        "maximum": 0.0,
                        "note": "The heating temperature offset is used to determine heating stage number for multi stage equipment. When the temperature difference of the heating setpoint and the controlled zone temperature at previous time step is less than Stage 3 value and greater than Stage 4 value, the stage number is 3. The value of this field has to be less the value at the previous field."
                    },
                    "stage_4_heating_temperature_offset": {
                        "type": "number",
                        "units": "deltaC",
                        "maximum": 0.0,
                        "note": "The heating temperature offset is used to determine heating stage number for multi stage equipment. When the temperature difference of the heating setpoint and the controlled zone temperature at previous time step is less than Stage 4 value, the stage number is 4. The value of this field has to be less the value at the previous field."
                    },
                    "number_of_cooling_stages": {
                        "type": "number",
                        "minimum": 1.0,
                        "maximum": 4.0,
                        "note": "Enter the number of the following sets of data for cooling temperature offset"
                    },
                    "cooling_temperature_setpoint_base_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "cooling_throttling_temperature_range": {
                        "type": "number",
                        "units": "deltaC",
                        "minimum": 0.0,
                        "default": 1.1
                    },
                    "stage_1_cooling_temperature_offset": {
                        "type": "number",
                        "units": "deltaC",
                        "minimum": 0.0,
                        "note": "The cooling temperature offset is used to determine cooling stage number for multi stage equipment. When the temperature difference of the cooling setpoint and the controlled zone temperature at previous time step is greater than Stage 1 value and less than Stage 2 value, the stage number is 1."
                    },
                    "stage_2_cooling_temperature_offset": {
                        "type": "number",
                        "units": "deltaC",
                        "minimum": 0.0,
                        "note": "The cooling temperature offset is used to determine cooling stage number for multi stage equipment. When the temperature difference of the cooling setpoint and the controlled zone temperature at previous time step is greater than Stage 2 value and less than Stage 3 value, the stage number is 2. The value of this field has to be greater than the value at the previous field."
                    },
                    "stage_3_cooling_temperature_offset": {
                        "type": "number",
                        "units": "deltaC",
                        "minimum": 0.0,
                        "note": "The cooling temperature offset is used to determine cooling stage number for multi stage equipment. When the temperature difference of the cooling setpoint and the controlled zone temperature at previous time step is greater than Stage 3 value and less than Stage 4 value, the stage number is 3. The value of this field has to be greater than the value at the previous field."
                    },
                    "stage_4_cooling_temperature_offset": {
                        "type": "number",
                        "units": "deltaC",
                        "minimum": 0.0,
                        "note": "The cooling temperature offset is used to determine cooling stage number for multi stage equipment. When the temperature difference of the cooling setpoint and the controlled zone temperature at previous time step is greater than Stage 4 value, the stage number is 4. The value of this field has to be greater than the value at the previous field."
                    }
                },
                "required": [
                    "zone_or_zonelist_name",
                    "number_of_heating_stages",
                    "stage_1_heating_temperature_offset",
                    "number_of_cooling_stages",
                    "stage_1_cooling_temperature_offset"
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
                "number_of_heating_stages": {
                    "field_name": "Number of Heating Stages",
                    "field_type": "n"
                },
                "heating_temperature_setpoint_schedule_name": {
                    "field_name": "Heating Temperature Setpoint Schedule Name",
                    "field_type": "a"
                },
                "heating_throttling_temperature_range": {
                    "field_name": "Heating Throttling Temperature Range",
                    "field_type": "n"
                },
                "stage_1_heating_temperature_offset": {
                    "field_name": "Stage 1 Heating Temperature Offset",
                    "field_type": "n"
                },
                "stage_2_heating_temperature_offset": {
                    "field_name": "Stage 2 Heating Temperature Offset",
                    "field_type": "n"
                },
                "stage_3_heating_temperature_offset": {
                    "field_name": "Stage 3 Heating Temperature Offset",
                    "field_type": "n"
                },
                "stage_4_heating_temperature_offset": {
                    "field_name": "Stage 4 Heating Temperature Offset",
                    "field_type": "n"
                },
                "number_of_cooling_stages": {
                    "field_name": "Number of Cooling Stages",
                    "field_type": "n"
                },
                "cooling_temperature_setpoint_base_schedule_name": {
                    "field_name": "Cooling Temperature Setpoint Base Schedule Name",
                    "field_type": "a"
                },
                "cooling_throttling_temperature_range": {
                    "field_name": "Cooling Throttling Temperature Range",
                    "field_type": "n"
                },
                "stage_1_cooling_temperature_offset": {
                    "field_name": "Stage 1 Cooling Temperature Offset",
                    "field_type": "n"
                },
                "stage_2_cooling_temperature_offset": {
                    "field_name": "Stage 2 Cooling Temperature Offset",
                    "field_type": "n"
                },
                "stage_3_cooling_temperature_offset": {
                    "field_name": "Stage 3 Cooling Temperature Offset",
                    "field_type": "n"
                },
                "stage_4_cooling_temperature_offset": {
                    "field_name": "Stage 4 Cooling Temperature Offset",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "zone_or_zonelist_name",
                "number_of_heating_stages",
                "heating_temperature_setpoint_schedule_name",
                "heating_throttling_temperature_range",
                "stage_1_heating_temperature_offset",
                "stage_2_heating_temperature_offset",
                "stage_3_heating_temperature_offset",
                "stage_4_heating_temperature_offset",
                "number_of_cooling_stages",
                "cooling_temperature_setpoint_base_schedule_name",
                "cooling_throttling_temperature_range",
                "stage_1_cooling_temperature_offset",
                "stage_2_cooling_temperature_offset",
                "stage_3_cooling_temperature_offset",
                "stage_4_cooling_temperature_offset"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "zone_or_zonelist_name",
                    "heating_temperature_setpoint_schedule_name",
                    "cooling_temperature_setpoint_base_schedule_name"
                ]
            },
            "numerics": {
                "fields": [
                    "number_of_heating_stages",
                    "heating_throttling_temperature_range",
                    "stage_1_heating_temperature_offset",
                    "stage_2_heating_temperature_offset",
                    "stage_3_heating_temperature_offset",
                    "stage_4_heating_temperature_offset",
                    "number_of_cooling_stages",
                    "cooling_throttling_temperature_range",
                    "stage_1_cooling_temperature_offset",
                    "stage_2_cooling_temperature_offset",
                    "stage_3_cooling_temperature_offset",
                    "stage_4_cooling_temperature_offset"
                ]
            }
        },
        "type": "object",
        "memo": "Define the Thermostat StagedDualSetpoint settings for a zone or list of zones. If you use a ZoneList in the Zone or ZoneList name field then this definition applies to all the zones in the ZoneList."
    }
}
```
