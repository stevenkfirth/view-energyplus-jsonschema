```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "values": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "value_for_run": {
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
        "type": "string",
        "note": "Parameter Name Must begin with the dollar sign character. The second character must be a letter. Remaining characters may only be letters or numbers. No spaces allowed.",
        "is_required": true
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "value_for_run": {
                "field_name": "Value for Run",
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
                "value_for_run"
            ]
        },
        "numerics": {
            "fields": []
        },
        "extensibles": [
            "value_for_run"
        ],
        "extension": "values"
    },
    "type": "object",
    "memo": "Parametric objects allow a set of multiple simulations to be defined in a single idf file. The parametric preprocessor scans the idf for Parametric:* objects then creates and runs multiple idf files, one for each defined simulation. The core parametric object is Parametric:SetValueForRun which defines the name of a parameter and sets the parameter to different values depending on which run is being simulated.",
    "min_fields": 2.0,
    "extensible_size": 1.0
}
```
