```
{
    "ThermostatSetpoint:ThermalComfort:Fanger:DualSetpoint": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "fanger_thermal_comfort_heating_schedule_name": {
                        "type": "string",
                        "note": "Schedule values should be Predicted Mean Vote (PMV)",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "fanger_thermal_comfort_cooling_schedule_name": {
                        "type": "string",
                        "note": "Schedule values should be Predicted Mean Vote (PMV)",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    }
                },
                "required": [
                    "fanger_thermal_comfort_heating_schedule_name",
                    "fanger_thermal_comfort_cooling_schedule_name"
                ]
            }
        },
        "group": "Zone HVAC Controls and Thermostats",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "ThermalComfortControlTypeNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "fanger_thermal_comfort_heating_schedule_name": {
                    "field_name": "Fanger Thermal Comfort Heating Schedule Name",
                    "field_type": "a"
                },
                "fanger_thermal_comfort_cooling_schedule_name": {
                    "field_name": "Fanger Thermal Comfort Cooling Schedule Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "fanger_thermal_comfort_heating_schedule_name",
                "fanger_thermal_comfort_cooling_schedule_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "fanger_thermal_comfort_heating_schedule_name",
                    "fanger_thermal_comfort_cooling_schedule_name"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "memo": "Used for heating and cooling thermal comfort control with dual setpoints. The PMV setpoints can be scheduled and varied throughout the simulation for both heating and cooling.",
        "min_fields": 3.0
    }
}
```
