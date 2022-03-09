```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "fanger_thermal_comfort_schedule_name": {
                    "type": "string",
                    "note": "Schedule values should be Predicted Mean Vote (PMV)",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                }
            },
            "required": [
                "fanger_thermal_comfort_schedule_name"
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
            "fanger_thermal_comfort_schedule_name": {
                "field_name": "Fanger Thermal Comfort Schedule Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "fanger_thermal_comfort_schedule_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "fanger_thermal_comfort_schedule_name"
            ]
        },
        "numerics": {
            "fields": []
        }
    },
    "type": "object",
    "memo": "Used for cooling only thermal comfort control. The PMV setpoint can be scheduled and varied throughout the simulation but only cooling is allowed with this control type.",
    "min_fields": 2.0
}
```
