```
{
    "ZoneContaminantSourceAndSink:Generic:CutoffModel": {
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
                    "design_generation_rate_coefficient": {
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
                        "note": "Value in this schedule should be a fraction (generally 0.0 - 1.0) applied to the Design Generation Rate Coefficient"
                    },
                    "cutoff_generic_contaminant_at_which_emission_ceases": {
                        "type": "number",
                        "units": "ppm",
                        "exclusiveMinimum": 0.0,
                        "note": "When the zone concentration level is greater than the cutoff level, emission stops, and the source level is zero."
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
                "design_generation_rate_coefficient": {
                    "field_name": "Design Generation Rate Coefficient",
                    "field_type": "n"
                },
                "schedule_name": {
                    "field_name": "Schedule Name",
                    "field_type": "a"
                },
                "cutoff_generic_contaminant_at_which_emission_ceases": {
                    "field_name": "Cutoff Generic Contaminant at which Emission Ceases",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "zone_name",
                "design_generation_rate_coefficient",
                "schedule_name",
                "cutoff_generic_contaminant_at_which_emission_ceases"
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
                    "design_generation_rate_coefficient",
                    "cutoff_generic_contaminant_at_which_emission_ceases"
                ]
            }
        },
        "type": "object",
        "memo": "Simulate generic contaminant source driven by the cutoff concentration model."
    }
}
```
