```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "schedule_type_limits_names": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleTypeLimitsNames"
                    ]
                },
                "fmu_file_name": {
                    "type": "string",
                    "retaincase": true,
                    "data_type": "object_list",
                    "object_list": [
                        "FMUFileName"
                    ]
                },
                "fmu_instance_name": {
                    "type": "string",
                    "retaincase": true
                },
                "fmu_variable_name": {
                    "type": "string",
                    "retaincase": true
                },
                "initial_value": {
                    "type": "number",
                    "note": "Used during the first call of EnergyPlus."
                }
            },
            "required": [
                "fmu_file_name",
                "fmu_instance_name",
                "fmu_variable_name",
                "initial_value"
            ]
        }
    },
    "group": "External Interface",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "ScheduleNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "schedule_type_limits_names": {
                "field_name": "Schedule Type Limits Names",
                "field_type": "a"
            },
            "fmu_file_name": {
                "field_name": "FMU File Name",
                "field_type": "a"
            },
            "fmu_instance_name": {
                "field_name": "FMU Instance Name",
                "field_type": "a"
            },
            "fmu_variable_name": {
                "field_name": "FMU Variable Name",
                "field_type": "a"
            },
            "initial_value": {
                "field_name": "Initial Value",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "schedule_type_limits_names",
            "fmu_file_name",
            "fmu_instance_name",
            "fmu_variable_name",
            "initial_value"
        ],
        "alphas": {
            "fields": [
                "name",
                "schedule_type_limits_names",
                "fmu_file_name",
                "fmu_instance_name",
                "fmu_variable_name"
            ]
        },
        "numerics": {
            "fields": [
                "initial_value"
            ]
        }
    },
    "type": "object",
    "memo": "This objects contains only one value, which is used during the first call of EnergyPlus",
    "min_fields": 6.0
}
```
