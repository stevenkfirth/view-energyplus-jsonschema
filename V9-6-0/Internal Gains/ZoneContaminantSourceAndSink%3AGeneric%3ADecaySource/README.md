```
{
    "ZoneContaminantSourceAndSink:Generic:DecaySource": {
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
                    "initial_emission_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "minimum": 0.0
                    },
                    "schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "Value in this schedule should be a fraction (generally 0.0 - 1.0) applied to the Initial Emission Rate. When the value is equal to 1.0, the time will be reset to zero."
                    },
                    "delay_time_constant": {
                        "type": "number",
                        "units": "s",
                        "exclusiveMinimum": 0.0
                    }
                },
                "required": [
                    "zone_name",
                    "schedule_name"
                ]
            }
        },
        "group": "Internal Gains",
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
                "zone_name": {
                    "field_name": "Zone Name",
                    "field_type": "a"
                },
                "initial_emission_rate": {
                    "field_name": "Initial Emission Rate",
                    "field_type": "n"
                },
                "schedule_name": {
                    "field_name": "Schedule Name",
                    "field_type": "a"
                },
                "delay_time_constant": {
                    "field_name": "Delay Time Constant",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "zone_name",
                "initial_emission_rate",
                "schedule_name",
                "delay_time_constant"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "zone_name",
                    "schedule_name"
                ]
            },
            "numerics": {
                "fields": [
                    "initial_emission_rate",
                    "delay_time_constant"
                ]
            }
        },
        "type": "object",
        "memo": "Simulate generic contaminant source driven by the cutoff concentration model."
    }
}
```
