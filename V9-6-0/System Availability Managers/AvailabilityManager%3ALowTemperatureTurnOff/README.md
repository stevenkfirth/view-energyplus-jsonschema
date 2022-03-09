```
{
    "AvailabilityManager:LowTemperatureTurnOff": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "sensor_node_name": {
                        "type": "string"
                    },
                    "temperature": {
                        "type": "number",
                        "units": "C"
                    },
                    "applicability_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "If blank, defaults to always active"
                    }
                },
                "required": [
                    "sensor_node_name",
                    "temperature"
                ]
            }
        },
        "group": "System Availability Managers",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "SystemAvailabilityManagers"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "sensor_node_name": {
                    "field_name": "Sensor Node Name",
                    "field_type": "a"
                },
                "temperature": {
                    "field_name": "Temperature",
                    "field_type": "n"
                },
                "applicability_schedule_name": {
                    "field_name": "Applicability Schedule Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "sensor_node_name",
                "temperature",
                "applicability_schedule_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "sensor_node_name",
                    "applicability_schedule_name"
                ]
            },
            "numerics": {
                "fields": [
                    "temperature"
                ]
            }
        },
        "type": "object",
        "memo": "Overrides fan/pump schedules depending on temperature at sensor node."
    }
}
```
