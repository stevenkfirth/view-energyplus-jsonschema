```
{
    "ZoneContaminantSourceAndSink:Generic:DepositionRateSink": {
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
                    "deposition_rate": {
                        "type": "number",
                        "units": "m/s",
                        "minimum": 0.0
                    },
                    "schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "Value in this schedule should be a fraction (generally 0.0 - 1.0) applied to the Initial Emission Rate. When the value is equal to 1.0, the time will be reset to zero."
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
                "deposition_rate": {
                    "field_name": "Deposition Rate",
                    "field_type": "n"
                },
                "schedule_name": {
                    "field_name": "Schedule Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "zone_name",
                "deposition_rate",
                "schedule_name"
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
                    "deposition_rate"
                ]
            }
        },
        "type": "object",
        "memo": "Simulate generic contaminant source driven by the boundary layer diffusion controlled model."
    }
}
```
