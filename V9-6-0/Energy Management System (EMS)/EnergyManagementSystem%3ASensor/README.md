```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "output_variable_or_output_meter_index_key_name": {
                    "type": "string"
                },
                "output_variable_or_output_meter_name": {
                    "type": "string",
                    "data_type": "external_list",
                    "external_list": [
                        "autoRDDvariableMeter"
                    ]
                }
            },
            "required": [
                "output_variable_or_output_meter_name"
            ]
        }
    },
    "group": "Energy Management System (EMS)",
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
            "output_variable_or_output_meter_index_key_name": {
                "field_name": "Output:Variable or Output:Meter Index Key Name",
                "field_type": "a"
            },
            "output_variable_or_output_meter_name": {
                "field_name": "Output:Variable or Output:Meter Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "output_variable_or_output_meter_index_key_name",
            "output_variable_or_output_meter_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "output_variable_or_output_meter_index_key_name",
                "output_variable_or_output_meter_name"
            ]
        },
        "numerics": {
            "fields": []
        }
    },
    "type": "object",
    "memo": "Declares EMS variable as a sensor a list of output variables and meters that can be reported are available after a run on the report (.rdd) or meter dictionary file (.mdd) if the Output:VariableDictionary has been requested.",
    "min_fields": 3.0
}
```
