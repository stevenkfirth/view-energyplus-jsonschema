```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "schedule_name": {
                    "type": "string",
                    "reference": [
                        "ScheduleNames"
                    ]
                },
                "schedule_type_limits_names": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleTypeLimitsNames"
                    ]
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
                "schedule_name",
                "fmu_variable_name",
                "initial_value"
            ]
        }
    },
    "group": "External Interface",
    "legacy_idd": {
        "field_info": {
            "schedule_name": {
                "field_name": "Schedule Name",
                "field_type": "a"
            },
            "schedule_type_limits_names": {
                "field_name": "Schedule Type Limits Names",
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
            "schedule_name",
            "schedule_type_limits_names",
            "fmu_variable_name",
            "initial_value"
        ],
        "alphas": {
            "fields": [
                "schedule_name",
                "schedule_type_limits_names",
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
    "min_fields": 4.0
}
```
