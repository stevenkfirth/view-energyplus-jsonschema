```
{
    "HVACTemplate:Thermostat": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "heating_setpoint_schedule_name": {
                        "type": "string",
                        "note": "Leave blank if constant setpoint specified below, must enter schedule or constant setpoint",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "constant_heating_setpoint": {
                        "type": "number",
                        "note": "Ignored if schedule specified above, must enter schedule or constant setpoint",
                        "units": "C"
                    },
                    "cooling_setpoint_schedule_name": {
                        "type": "string",
                        "note": "Leave blank if constant setpoint specified below, must enter schedule or constant setpoint",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "constant_cooling_setpoint": {
                        "type": "number",
                        "note": "Ignored if schedule specified above, must enter schedule or constant setpoint",
                        "units": "C"
                    }
                }
            }
        },
        "group": "HVAC Templates",
        "name": {
            "type": "string",
            "is_required": true,
            "note": "This name is referenced by HVACTemplate:Zone:* objects",
            "reference": [
                "CompactHVACThermostats"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "heating_setpoint_schedule_name": {
                    "field_name": "Heating Setpoint Schedule Name",
                    "field_type": "a"
                },
                "constant_heating_setpoint": {
                    "field_name": "Constant Heating Setpoint",
                    "field_type": "n"
                },
                "cooling_setpoint_schedule_name": {
                    "field_name": "Cooling Setpoint Schedule Name",
                    "field_type": "a"
                },
                "constant_cooling_setpoint": {
                    "field_name": "Constant Cooling Setpoint",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "heating_setpoint_schedule_name",
                "constant_heating_setpoint",
                "cooling_setpoint_schedule_name",
                "constant_cooling_setpoint"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "heating_setpoint_schedule_name",
                    "cooling_setpoint_schedule_name"
                ]
            },
            "numerics": {
                "fields": [
                    "constant_heating_setpoint",
                    "constant_cooling_setpoint"
                ]
            }
        },
        "type": "object",
        "memo": "Zone thermostat control. Referenced schedules must be defined elsewhere in the idf. Thermostat control type is dual setpoint with deadband. It is not necessary to create a thermostat object for every zone, only for each unique set of setpoint schedules. For example, an office building may have two thermostat objects, one for \"Office\" and one for \"Storage\".",
        "min_fields": 5.0
    }
}
```
