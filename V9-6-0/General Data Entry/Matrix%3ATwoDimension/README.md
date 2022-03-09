```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "number_of_rows": {
                    "type": "number"
                },
                "number_of_columns": {
                    "type": "number"
                },
                "values": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "value": {
                                "type": "number"
                            }
                        },
                        "type": "object"
                    }
                }
            },
            "required": [
                "number_of_rows",
                "number_of_columns"
            ]
        }
    },
    "group": "General Data Entry",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "DataMatrices"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "number_of_rows": {
                "field_name": "Number of Rows",
                "field_type": "n"
            },
            "number_of_columns": {
                "field_name": "Number of Columns",
                "field_type": "n"
            },
            "value": {
                "field_name": "Value",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "number_of_rows",
            "number_of_columns"
        ],
        "alphas": {
            "fields": [
                "name"
            ]
        },
        "numerics": {
            "fields": [
                "number_of_rows",
                "number_of_columns"
            ],
            "extensions": [
                "value"
            ]
        },
        "extensibles": [
            "value"
        ],
        "extension": "values"
    },
    "type": "object",
    "memo": "matrix data in row-major order list each row keeping the columns in order number of values must equal N1 x N2",
    "extensible_size": 1.0
}
```
