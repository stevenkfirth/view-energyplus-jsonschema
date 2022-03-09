```
{
    "Parametric:Logic": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "lines": {
                        "type": "array",
                        "items": {
                            "properties": {
                                "parametric_logic_line": {
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
            "is_required": true
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "parametric_logic_line": {
                    "field_name": "Parametric Logic Line",
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
                    "parametric_logic_line"
                ]
            },
            "numerics": {
                "fields": []
            },
            "extensibles": [
                "parametric_logic_line"
            ],
            "extension": "lines"
        },
        "type": "object",
        "maxProperties": 1,
        "memo": "This object allows some types of objects to be included for some parametric cases and not for others. For example, you might want an overhang on a window in some parametric runs and not others. A single Parametric:Logic object is allowed per file. Consult the Input Output Reference for available commands and syntax.",
        "min_fields": 2.0,
        "extensible_size": 1.0
    }
}
```
