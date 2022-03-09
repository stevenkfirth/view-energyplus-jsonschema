```
{
    "PythonPlugin:Variables": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "global_py_vars": {
                        "type": "array",
                        "items": {
                            "properties": {
                                "variable_name": {
                                    "type": "string",
                                    "note": "This variable is used to identify and create a shared variable in EnergyPlus. This variable can then be used by all running Python Plugin instances."
                                }
                            },
                            "type": "object"
                        }
                    }
                }
            }
        },
        "group": "Python Plugin System",
        "name": {
            "type": "string",
            "is_required": true,
            "note": "This object name is purely for reporting and diagnostics"
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "variable_name": {
                    "field_name": "Variable Name",
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
                    "variable_name"
                ]
            },
            "numerics": {
                "fields": []
            },
            "extensibles": [
                "variable_name"
            ],
            "extension": "global_py_vars"
        },
        "type": "object",
        "maxProperties": 1,
        "memo": "This object defines name identifiers for custom Python Plugin variable data that should be shared among all running Python Plugins.",
        "min_fields": 2.0,
        "extensible_size": 1.0
    }
}
```
