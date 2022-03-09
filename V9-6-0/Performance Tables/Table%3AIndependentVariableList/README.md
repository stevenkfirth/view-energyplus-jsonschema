```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "independent_variables": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "independent_variable_name": {
                                "type": "string",
                                "data_type": "object_list",
                                "object_list": [
                                    "IndependentVariableName"
                                ]
                            }
                        },
                        "type": "object",
                        "required": [
                            "independent_variable_name"
                        ]
                    }
                }
            }
        }
    },
    "group": "Performance Tables",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "IndependentVariableListName"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "independent_variable_name": {
                "field_name": "Independent Variable Name",
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
                "independent_variable_name"
            ]
        },
        "numerics": {
            "fields": []
        },
        "extensibles": [
            "independent_variable_name"
        ],
        "extension": "independent_variables"
    },
    "type": "object",
    "memo": "A sorted list of independent variables used by one or more Table:Lookup objects.",
    "extensible_size": 1.0
}
```
