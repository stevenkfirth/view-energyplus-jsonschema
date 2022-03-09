```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "setpoint_temperature_schedule_name": {
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
            "setpoint_temperature_schedule_name": {
                "field_name": "Setpoint Temperature Schedule Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "setpoint_temperature_schedule_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "setpoint_temperature_schedule_name"
            ]
        },
        "numerics": {
            "fields": []
        }
    },
    "type": "object",
    "memo": "Used for a cooling only thermostat. The setpoint can be scheduled and varied throughout the simulation but only cooling is allowed."
}
```
