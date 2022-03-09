```
{
    "SurfaceContaminantSourceAndSink:Generic:DepositionVelocitySink": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "surface_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "SurfaceNames"
                        ]
                    },
                    "deposition_velocity": {
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
                    "surface_name",
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
                "surface_name": {
                    "field_name": "Surface Name",
                    "field_type": "a"
                },
                "deposition_velocity": {
                    "field_name": "Deposition Velocity",
                    "field_type": "n"
                },
                "schedule_name": {
                    "field_name": "Schedule Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "surface_name",
                "deposition_velocity",
                "schedule_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "surface_name",
                    "schedule_name"
                ]
            },
            "numerics": {
                "fields": [
                    "deposition_velocity"
                ]
            }
        },
        "type": "object",
        "memo": "Simulate generic contaminant source driven by the boundary layer diffusion controlled model."
    }
}
```
