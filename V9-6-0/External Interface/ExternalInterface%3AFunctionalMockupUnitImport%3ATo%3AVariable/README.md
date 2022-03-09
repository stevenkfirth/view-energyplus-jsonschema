```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
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
        "note": "This name becomes a variable for use in Erl programs no spaces allowed in name"
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
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
            "fmu_file_name",
            "fmu_instance_name",
            "fmu_variable_name",
            "initial_value"
        ],
        "alphas": {
            "fields": [
                "name",
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
    "memo": "Declares Erl variable as having global scope No spaces allowed in names used for Erl variables",
    "min_fields": 5.0
}
```
