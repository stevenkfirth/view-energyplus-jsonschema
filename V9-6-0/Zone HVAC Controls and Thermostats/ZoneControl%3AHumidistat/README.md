```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "zone_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ]
                },
                "humidifying_relative_humidity_setpoint_schedule_name": {
                    "type": "string",
                    "note": "hourly schedule values should be in Relative Humidity (percent)",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "dehumidifying_relative_humidity_setpoint_schedule_name": {
                    "type": "string",
                    "note": "hourly schedule values should be in Relative Humidity (percent)",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                }
            },
            "required": [
                "zone_name",
                "humidifying_relative_humidity_setpoint_schedule_name"
            ]
        }
    },
    "group": "Zone HVAC Controls and Thermostats",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "ZoneControlHumidistatNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "zone_name": {
                "field_name": "Zone Name",
                "field_type": "a"
            },
            "humidifying_relative_humidity_setpoint_schedule_name": {
                "field_name": "Humidifying Relative Humidity Setpoint Schedule Name",
                "field_type": "a"
            },
            "dehumidifying_relative_humidity_setpoint_schedule_name": {
                "field_name": "Dehumidifying Relative Humidity Setpoint Schedule Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "zone_name",
            "humidifying_relative_humidity_setpoint_schedule_name",
            "dehumidifying_relative_humidity_setpoint_schedule_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "zone_name",
                "humidifying_relative_humidity_setpoint_schedule_name",
                "dehumidifying_relative_humidity_setpoint_schedule_name"
            ]
        },
        "numerics": {
            "fields": []
        }
    },
    "type": "object",
    "memo": "Specifies zone relative humidity setpoint schedules for humidifying and dehumidifying.",
    "min_fields": 3.0
}
```
