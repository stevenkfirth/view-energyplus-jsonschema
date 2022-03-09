```
{
    "Parametric:FileNameSuffix": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "suffixes": {
                        "type": "array",
                        "items": {
                            "properties": {
                                "suffix_for_file_name_in_run": {
                                    "type": "string"
                                }
                            },
                            "type": "object"
                        }
                    }
                }
            }
        },
        "group": "Parametrics",
        "name": {
            "type": "string"
        },
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "suffix_for_file_name_in_run": {
                    "field_name": "Suffix for File Name in Run",
                    "field_type": "a"
                }
            },
            "fields": [
                "name"
            ],
            "alphas": {
                "fields": [
                    "name"
                ],
                "extensions": [
                    "suffix_for_file_name_in_run"
                ]
            },
            "numerics": {
                "fields": []
            },
            "extensibles": [
                "suffix_for_file_name_in_run"
            ],
            "extension": "suffixes"
        },
        "type": "object",
        "maxProperties": 1,
        "memo": "Defines the suffixes to be appended to the idf and output file names for each parametric run. If this object is omitted, the suffix will default to the run number.",
        "min_fields": 2.0,
        "extensible_size": 1.0
    }
}
```
