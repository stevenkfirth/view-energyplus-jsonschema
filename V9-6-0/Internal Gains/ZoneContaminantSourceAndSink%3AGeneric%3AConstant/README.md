```
{
    "ZoneContaminantSourceAndSink:Generic:Constant": {
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
                        "minimum": 0.0,
                        "note": "The values represent source."
                    },
                    "generation_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "Value in this schedule should be a fraction (generally 0.0 - 1.0) applied to the Design Generation Rate"
                    },
                    "design_removal_coefficient": {
                        "type": "number",
                        "units": "m3/s",
                        "minimum": 0.0,
                        "note": "The value represent sink."
                    },
                    "removal_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "Value in this schedule should be a fraction (generally 0.0 - 1.0) applied to the Design removal Coefficient"
                    }
                },
                "required": [
                    "zone_name",
                    "generation_schedule_name",
                    "removal_schedule_name"
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
                "generation_schedule_name": {
                    "field_name": "Generation Schedule Name",
                    "field_type": "a"
                },
                "design_removal_coefficient": {
                    "field_name": "Design Removal Coefficient",
                    "field_type": "n"
                },
                "removal_schedule_name": {
                    "field_name": "Removal Schedule Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "zone_name",
                "design_generation_rate",
                "generation_schedule_name",
                "design_removal_coefficient",
                "removal_schedule_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "zone_name",
                    "generation_schedule_name",
                    "removal_schedule_name"
                ]
            },
            "numerics": {
                "fields": [
                    "design_generation_rate",
                    "design_removal_coefficient"
                ]
            }
        },
        "type": "object",
        "memo": "Sets internal generic contaminant gains and sinks in a zone with constant values."
    }
}
```
