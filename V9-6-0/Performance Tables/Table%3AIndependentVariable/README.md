```
{
    "Table:IndependentVariable": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "interpolation_method": {
                        "type": "string",
                        "enum": [
                            "",
                            "Cubic",
                            "Linear"
                        ],
                        "default": "Linear"
                    },
                    "extrapolation_method": {
                        "type": "string",
                        "enum": [
                            "",
                            "Constant",
                            "Linear"
                        ],
                        "default": "Constant"
                    },
                    "minimum_value": {
                        "type": "number",
                        "unitsBasedOnField": "unit_type"
                    },
                    "maximum_value": {
                        "type": "number",
                        "unitsBasedOnField": "unit_type"
                    },
                    "normalization_reference_value": {
                        "type": "number",
                        "unitsBasedOnField": "unit_type"
                    },
                    "unit_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "Angle",
                            "Dimensionless",
                            "Distance",
                            "MassFlow",
                            "Power",
                            "Temperature",
                            "VolumetricFlow"
                        ],
                        "default": "Dimensionless"
                    },
                    "external_file_name": {
                        "type": "string",
                        "retaincase": true
                    },
                    "external_file_column_number": {
                        "type": "number",
                        "minimum": 1.0
                    },
                    "external_file_starting_row_number": {
                        "type": "number",
                        "minimum": 1.0
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
                }
            }
        },
        "group": "Performance Tables",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "IndependentVariableName"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "interpolation_method": {
                    "field_name": "Interpolation Method",
                    "field_type": "a"
                },
                "extrapolation_method": {
                    "field_name": "Extrapolation Method",
                    "field_type": "a"
                },
                "minimum_value": {
                    "field_name": "Minimum Value",
                    "field_type": "n"
                },
                "maximum_value": {
                    "field_name": "Maximum Value",
                    "field_type": "n"
                },
                "normalization_reference_value": {
                    "field_name": "Normalization Reference Value",
                    "field_type": "n"
                },
                "unit_type": {
                    "field_name": "Unit Type",
                    "field_type": "a"
                },
                "external_file_name": {
                    "field_name": "External File Name",
                    "field_type": "a"
                },
                "external_file_column_number": {
                    "field_name": "External File Column Number",
                    "field_type": "n"
                },
                "external_file_starting_row_number": {
                    "field_name": "External File Starting Row Number",
                    "field_type": "n"
                },
                "value": {
                    "field_name": "Value",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "interpolation_method",
                "extrapolation_method",
                "minimum_value",
                "maximum_value",
                "normalization_reference_value",
                "unit_type",
                "external_file_name",
                "external_file_column_number",
                "external_file_starting_row_number"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "interpolation_method",
                    "extrapolation_method",
                    "unit_type",
                    "external_file_name"
                ]
            },
            "numerics": {
                "fields": [
                    "minimum_value",
                    "maximum_value",
                    "normalization_reference_value",
                    "external_file_column_number",
                    "external_file_starting_row_number"
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
        "memo": "An independent variable representing a single dimension of a Table:Lookup object.",
        "extensible_size": 1.0
    }
}
```
