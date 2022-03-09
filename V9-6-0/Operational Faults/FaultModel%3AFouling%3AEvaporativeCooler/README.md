```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "availability_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "severity_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "evaporative_cooler_object_type": {
                    "type": "string",
                    "note": "Enter the type of a Evaporative Cooler object The fault applies to the wetted coil evaporative cooler The fault does not apply to direct evaporative coolers or the dry coil indirect evaporative coolers",
                    "enum": [
                        "EvaporativeCooler:Indirect:WetCoil"
                    ]
                },
                "evaporative_cooler_object_name": {
                    "type": "string",
                    "note": "Enter the name of aN Evaporative Cooler object",
                    "data_type": "object_list",
                    "object_list": [
                        "Chillers"
                    ]
                },
                "fouling_factor": {
                    "type": "number",
                    "note": "The factor indicates the decrease of the indirect stage efficiency It is the ratio between the indirect stage efficiency at fouling case and that at fault free case",
                    "exclusiveMinimum": 0.0,
                    "maximum": 1.0,
                    "default": 1.0,
                    "units": "dimensionless"
                }
            },
            "required": [
                "evaporative_cooler_object_type",
                "evaporative_cooler_object_name"
            ]
        }
    },
    "group": "Operational Faults",
    "name": {
        "type": "string",
        "note": "Enter the name of the fault",
        "is_required": true
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "availability_schedule_name": {
                "field_name": "Availability Schedule Name",
                "field_type": "a"
            },
            "severity_schedule_name": {
                "field_name": "Severity Schedule Name",
                "field_type": "a"
            },
            "evaporative_cooler_object_type": {
                "field_name": "Evaporative Cooler Object Type",
                "field_type": "a"
            },
            "evaporative_cooler_object_name": {
                "field_name": "Evaporative Cooler Object Name",
                "field_type": "a"
            },
            "fouling_factor": {
                "field_name": "Fouling Factor",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "availability_schedule_name",
            "severity_schedule_name",
            "evaporative_cooler_object_type",
            "evaporative_cooler_object_name",
            "fouling_factor"
        ],
        "alphas": {
            "fields": [
                "name",
                "availability_schedule_name",
                "severity_schedule_name",
                "evaporative_cooler_object_type",
                "evaporative_cooler_object_name"
            ]
        },
        "numerics": {
            "fields": [
                "fouling_factor"
            ]
        }
    },
    "type": "object",
    "memo": "This object describes the fouling fault of the wetted coil evaporative cooler",
    "min_fields": 6.0
}
```
