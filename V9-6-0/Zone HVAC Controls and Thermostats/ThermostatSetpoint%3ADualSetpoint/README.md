```
{
    "ThermostatSetpoint:DualSetpoint": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "heating_setpoint_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "cooling_setpoint_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    }
                }
            }
        },
        "group": "Zone HVAC Controls and Thermostats",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "ControlTypeNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "heating_setpoint_temperature_schedule_name": {
                    "field_name": "Heating Setpoint Temperature Schedule Name",
                    "field_type": "a"
                },
                "cooling_setpoint_temperature_schedule_name": {
                    "field_name": "Cooling Setpoint Temperature Schedule Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "heating_setpoint_temperature_schedule_name",
                "cooling_setpoint_temperature_schedule_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "heating_setpoint_temperature_schedule_name",
                    "cooling_setpoint_temperature_schedule_name"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "memo": "Used for a heating and cooling thermostat with dual setpoints. The setpoints can be scheduled and varied throughout the simulation for both heating and cooling."
    }
}
```
