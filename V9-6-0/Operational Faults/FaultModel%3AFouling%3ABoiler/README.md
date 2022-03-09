```
{
    "FaultModel:Fouling:Boiler": {
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
                    "boiler_object_type": {
                        "type": "string",
                        "note": "Enter the type of a boiler object The fault applies to the hot-water boilers",
                        "enum": [
                            "Boiler:HotWater"
                        ]
                    },
                    "boiler_object_name": {
                        "type": "string",
                        "note": "Enter the name of a Boiler object",
                        "data_type": "object_list",
                        "object_list": [
                            "Boilers"
                        ]
                    },
                    "fouling_factor": {
                        "type": "number",
                        "note": "The factor indicates the decrease of the nominal capacity of the boiler It is the ratio between the nominal capacity at fouling case and that at fault free case",
                        "exclusiveMinimum": 0.0,
                        "maximum": 1.0,
                        "default": 1.0,
                        "units": "dimensionless"
                    }
                },
                "required": [
                    "boiler_object_type",
                    "boiler_object_name"
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
                "boiler_object_type": {
                    "field_name": "Boiler Object Type",
                    "field_type": "a"
                },
                "boiler_object_name": {
                    "field_name": "Boiler Object Name",
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
                "boiler_object_type",
                "boiler_object_name",
                "fouling_factor"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "severity_schedule_name",
                    "boiler_object_type",
                    "boiler_object_name"
                ]
            },
            "numerics": {
                "fields": [
                    "fouling_factor"
                ]
            }
        },
        "type": "object",
        "memo": "This object describes the fouling fault of boilers with water-based heat exchangers",
        "min_fields": 6.0
    }
}
```
