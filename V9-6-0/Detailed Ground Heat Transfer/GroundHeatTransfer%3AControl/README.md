```
{
    "GroundHeatTransfer:Control": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "run_basement_preprocessor": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "No"
                    },
                    "run_slab_preprocessor": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "No"
                    }
                }
            }
        },
        "group": "Detailed Ground Heat Transfer",
        "name": {
            "type": "string",
            "note": "This field is included for consistency.11"
        },
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "run_basement_preprocessor": {
                    "field_name": "Run Basement Preprocessor",
                    "field_type": "a"
                },
                "run_slab_preprocessor": {
                    "field_name": "Run Slab Preprocessor",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "run_basement_preprocessor",
                "run_slab_preprocessor"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "run_basement_preprocessor",
                    "run_slab_preprocessor"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "memo": "Object determines if the Slab and Basement preprocessors are going to be executed."
    }
}
```
