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
                "cooling_tower_object_type": {
                    "type": "string",
                    "note": "Enter the type of the cooling tower affected",
                    "enum": [
                        "CoolingTower:SingleSpeed",
                        "CoolingTower:TwoSpeed",
                        "CoolingTower:VariableSpeed:MERKEL"
                    ]
                },
                "cooling_tower_object_name": {
                    "type": "string",
                    "note": "Enter the name of the cooling tower affected",
                    "data_type": "object_list",
                    "object_list": [
                        "CoolingTowersWithUA"
                    ]
                },
                "reference_ua_reduction_factor": {
                    "type": "number",
                    "note": "Factor describing the tower UA reduction due to fouling It is the ratio between the UA value at fouling case and that at fault free case It is applicable to both the Design UA and Free Convection UA of the tower",
                    "units": "dimensionless",
                    "exclusiveMinimum": 0.0
                }
            },
            "required": [
                "cooling_tower_object_type",
                "cooling_tower_object_name"
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
            "cooling_tower_object_type": {
                "field_name": "Cooling Tower Object Type",
                "field_type": "a"
            },
            "cooling_tower_object_name": {
                "field_name": "Cooling Tower Object Name",
                "field_type": "a"
            },
            "reference_ua_reduction_factor": {
                "field_name": "Reference UA Reduction Factor",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "availability_schedule_name",
            "severity_schedule_name",
            "cooling_tower_object_type",
            "cooling_tower_object_name",
            "reference_ua_reduction_factor"
        ],
        "alphas": {
            "fields": [
                "name",
                "availability_schedule_name",
                "severity_schedule_name",
                "cooling_tower_object_type",
                "cooling_tower_object_name"
            ]
        },
        "numerics": {
            "fields": [
                "reference_ua_reduction_factor"
            ]
        }
    },
    "type": "object",
    "memo": "This object describes the fault of fouling cooling towers",
    "min_fields": 6.0
}
```
