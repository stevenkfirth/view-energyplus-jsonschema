```
{
    "Table:Lookup": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "independent_variable_list_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "IndependentVariableListName"
                        ]
                    },
                    "normalization_method": {
                        "type": "string",
                        "enum": [
                            "",
                            "AutomaticWithDivisor",
                            "DivisorOnly",
                            "None"
                        ],
                        "default": "None"
                    },
                    "normalization_divisor": {
                        "type": "number",
                        "default": 1.0
                    },
                    "minimum_output": {
                        "type": "number",
                        "unitsBasedOnField": "output_unit_type"
                    },
                    "maximum_output": {
                        "type": "number",
                        "unitsBasedOnField": "output_unit_type"
                    },
                    "output_unit_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "Capacity",
                            "Dimensionless",
                            "Power",
                            "Pressure",
                            "Temperature"
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
                                "output_value": {
                                    "type": "number",
                                    "unitsBasedOnField": "A4"
                                }
                            },
                            "type": "object"
                        }
                    }
                },
                "required": [
                    "independent_variable_list_name"
                ]
            }
        },
        "group": "Performance Tables",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "BivariateFunctions",
                "MultivariateFunctions",
                "QuadvariateFunctions",
                "QuintvariateFunctions",
                "TrivariateFunctions",
                "UnivariateFunctions"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "independent_variable_list_name": {
                    "field_name": "Independent Variable List Name",
                    "field_type": "a"
                },
                "normalization_method": {
                    "field_name": "Normalization Method",
                    "field_type": "a"
                },
                "normalization_divisor": {
                    "field_name": "Normalization Divisor",
                    "field_type": "n"
                },
                "minimum_output": {
                    "field_name": "Minimum Output",
                    "field_type": "n"
                },
                "maximum_output": {
                    "field_name": "Maximum Output",
                    "field_type": "n"
                },
                "output_unit_type": {
                    "field_name": "Output Unit Type",
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
                "output_value": {
                    "field_name": "Output Value",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "independent_variable_list_name",
                "normalization_method",
                "normalization_divisor",
                "minimum_output",
                "maximum_output",
                "output_unit_type",
                "external_file_name",
                "external_file_column_number",
                "external_file_starting_row_number"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "independent_variable_list_name",
                    "normalization_method",
                    "output_unit_type",
                    "external_file_name"
                ]
            },
            "numerics": {
                "fields": [
                    "normalization_divisor",
                    "minimum_output",
                    "maximum_output",
                    "external_file_column_number",
                    "external_file_starting_row_number"
                ],
                "extensions": [
                    "output_value"
                ]
            },
            "extensibles": [
                "output_value"
            ],
            "extension": "values"
        },
        "type": "object",
        "memo": "Lookup tables are used in place of curves and can represent any number of independent variables (defined as Table:IndependentVariable objects in a Table:IndependentVariableList). Output values are interpolated within the bounds defined by each independent variable and extrapolated beyond the bounds according to the interpolation/extrapolation methods defined by each independent variable.",
        "extensible_size": 1.0
    }
}
```
