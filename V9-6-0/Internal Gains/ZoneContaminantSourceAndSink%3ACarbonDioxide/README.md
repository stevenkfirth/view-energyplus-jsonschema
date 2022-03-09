```
{
    "ZoneContaminantSourceAndSink:CarbonDioxide": {
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
                    "design_generation_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "note": "Positive values represent sources and negative values represent sinks."
                    },
                    "schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "Value in this schedule should be a fraction (generally 0.0 - 1.0) applied to the Design Generation Rate"
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
                "design_generation_rate": {
                    "field_name": "Design Generation Rate",
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
                "design_generation_rate",
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
                    "design_generation_rate"
                ]
            }
        },
        "type": "object",
        "memo": "Represents internal CO2 gains and sinks in the zone."
    }
}
```
