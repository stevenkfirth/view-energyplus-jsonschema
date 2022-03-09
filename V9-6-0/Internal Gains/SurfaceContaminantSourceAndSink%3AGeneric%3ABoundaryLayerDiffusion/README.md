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
                        "SurfaceNames"
                    ]
                },
                "mass_transfer_coefficient": {
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
                },
                "henry_adsorption_constant_or_partition_coefficient": {
                    "type": "number",
                    "units": "dimensionless",
                    "exclusiveMinimum": 0.0
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
            "mass_transfer_coefficient": {
                "field_name": "Mass Transfer Coefficient",
                "field_type": "n"
            },
            "schedule_name": {
                "field_name": "Schedule Name",
                "field_type": "a"
            },
            "henry_adsorption_constant_or_partition_coefficient": {
                "field_name": "Henry Adsorption Constant or Partition Coefficient",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "surface_name",
            "mass_transfer_coefficient",
            "schedule_name",
            "henry_adsorption_constant_or_partition_coefficient"
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
                "mass_transfer_coefficient",
                "henry_adsorption_constant_or_partition_coefficient"
            ]
        }
    },
    "type": "object",
    "memo": "Simulate generic contaminant source driven by the boundary layer diffusion controlled model."
}
```
