```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "surface_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "SurfAndSubSurfNames"
                    ]
                },
                "design_generation_rate_coefficient": {
                    "type": "number",
                    "units": "m3/s",
                    "minimum": 0.0
                },
                "generation_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "Value in this schedule should be a fraction (generally 0.0 - 1.0) applied to the Design Generation Rate Coefficient"
                },
                "generation_exponent": {
                    "type": "number",
                    "units": "dimensionless",
                    "exclusiveMinimum": 0.0,
                    "maximum": 1.0
                }
            },
            "required": [
                "surface_name",
                "generation_schedule_name"
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
            "surface_name": {
                "field_name": "Surface Name",
                "field_type": "a"
            },
            "design_generation_rate_coefficient": {
                "field_name": "Design Generation Rate Coefficient",
                "field_type": "n"
            },
            "generation_schedule_name": {
                "field_name": "Generation Schedule Name",
                "field_type": "a"
            },
            "generation_exponent": {
                "field_name": "Generation Exponent",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "surface_name",
            "design_generation_rate_coefficient",
            "generation_schedule_name",
            "generation_exponent"
        ],
        "alphas": {
            "fields": [
                "name",
                "surface_name",
                "generation_schedule_name"
            ]
        },
        "numerics": {
            "fields": [
                "design_generation_rate_coefficient",
                "generation_exponent"
            ]
        }
    },
    "type": "object",
    "memo": "Simulate generic contaminant source driven by the pressure difference across a surface."
}
```
