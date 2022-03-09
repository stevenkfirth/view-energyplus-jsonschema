```
{
    "Output:VariableDictionary": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "key_field": {
                        "type": "string",
                        "enum": [
                            "",
                            "IDF",
                            "regular"
                        ],
                        "default": "regular"
                    },
                    "sort_option": {
                        "type": "string",
                        "enum": [
                            "Name",
                            "Unsorted"
                        ]
                    }
                }
            }
        },
        "group": "Output Reporting",
        "legacy_idd": {
            "field_info": {
                "key_field": {
                    "field_name": "Key Field",
                    "field_type": "a"
                },
                "sort_option": {
                    "field_name": "Sort Option",
                    "field_type": "a"
                }
            },
            "fields": [
                "key_field",
                "sort_option"
            ],
            "alphas": {
                "fields": [
                    "key_field",
                    "sort_option"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "memo": "Produces a list summarizing the output variables and meters that are available for reporting for the model being simulated (rdd output file). The list varies depending on the types of objects present in the idf file. For example, variables related to lights will only appear if a Lights object is present. The IDF option generates complete Output:Variable objects to simplify adding the desired output to the idf file.",
        "min_fields": 1.0,
        "format": "singleLine"
    }
}
```
