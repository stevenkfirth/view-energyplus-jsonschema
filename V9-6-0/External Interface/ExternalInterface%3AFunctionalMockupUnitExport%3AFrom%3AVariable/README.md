```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "output_variable_index_key_name": {
                    "type": "string"
                },
                "output_variable_name": {
                    "type": "string",
                    "data_type": "external_list",
                    "external_list": [
                        "autoRDDvariable"
                    ]
                },
                "fmu_variable_name": {
                    "type": "string",
                    "retaincase": true
                }
            },
            "required": [
                "output_variable_index_key_name",
                "output_variable_name",
                "fmu_variable_name"
            ]
        }
    },
    "group": "External Interface",
    "legacy_idd": {
        "field_info": {
            "output_variable_index_key_name": {
                "field_name": "Output:Variable Index Key Name",
                "field_type": "a"
            },
            "output_variable_name": {
                "field_name": "Output:Variable Name",
                "field_type": "a"
            },
            "fmu_variable_name": {
                "field_name": "FMU Variable Name",
                "field_type": "a"
            }
        },
        "fields": [
            "output_variable_index_key_name",
            "output_variable_name",
            "fmu_variable_name"
        ],
        "alphas": {
            "fields": [
                "output_variable_index_key_name",
                "output_variable_name",
                "fmu_variable_name"
            ]
        },
        "numerics": {
            "fields": []
        }
    },
    "type": "object",
    "memo": "This object declares an FMU input variable",
    "min_fields": 3.0
}
```
