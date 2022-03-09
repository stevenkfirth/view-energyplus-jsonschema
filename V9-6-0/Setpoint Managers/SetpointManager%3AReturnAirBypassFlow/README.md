```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "control_variable": {
                    "type": "string",
                    "enum": [
                        "",
                        "Flow"
                    ],
                    "default": "Flow"
                },
                "hvac_air_loop_name": {
                    "type": "string",
                    "note": "Enter the name of an AirLoopHVAC object.",
                    "data_type": "object_list",
                    "object_list": [
                        "AirPrimaryLoops"
                    ]
                },
                "temperature_setpoint_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                }
            },
            "required": [
                "hvac_air_loop_name"
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
            "hvac_air_loop_name": {
                "field_name": "HVAC Air Loop Name",
                "field_type": "a"
            },
            "temperature_setpoint_schedule_name": {
                "field_name": "Temperature Setpoint Schedule Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "control_variable",
            "hvac_air_loop_name",
            "temperature_setpoint_schedule_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "control_variable",
                "hvac_air_loop_name",
                "temperature_setpoint_schedule_name"
            ]
        },
        "numerics": {
            "fields": []
        }
    },
    "type": "object",
    "memo": "This setpoint manager determines the required mass flow rate through a return air bypass duct to meet the specified temperature setpoint",
    "min_fields": 4.0
}
```
