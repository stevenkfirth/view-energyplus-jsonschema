```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "runs": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "perform_run": {
                                "type": "string",
                                "enum": [
                                    "",
                                    "No",
                                    "Yes"
                                ],
                                "default": "Yes"
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
            "perform_run": {
                "field_name": "Perform Run",
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
                "perform_run"
            ]
        },
        "numerics": {
            "fields": []
        },
        "extensibles": [
            "perform_run"
        ],
        "extension": "runs"
    },
    "type": "object",
    "maxProperties": 1,
    "memo": "Controls which parametric runs are simulated. This object is optional. If it is not included, then all parametric runs are performed.",
    "min_fields": 2.0,
    "extensible_size": 1.0
}
```
