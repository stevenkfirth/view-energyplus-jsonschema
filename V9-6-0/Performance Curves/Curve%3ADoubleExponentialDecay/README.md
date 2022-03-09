```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "coefficient1_c1": {
                    "type": "number"
                },
                "coefficient2_c2": {
                    "type": "number"
                },
                "coefficient3_c3": {
                    "type": "number"
                },
                "coefficient4_c4": {
                    "type": "number"
                },
                "coefficient5_c5": {
                    "type": "number"
                },
                "minimum_value_of_x": {
                    "type": "number",
                    "unitsBasedOnField": "input_unit_type_for_x"
                },
                "maximum_value_of_x": {
                    "type": "number",
                    "unitsBasedOnField": "input_unit_type_for_x"
                },
                "minimum_curve_output": {
                    "type": "number",
                    "unitsBasedOnField": "output_unit_type",
                    "note": "Specify the minimum value calculated by this curve object"
                },
                "maximum_curve_output": {
                    "type": "number",
                    "unitsBasedOnField": "output_unit_type",
                    "note": "Specify the maximum value calculated by this curve object"
                },
                "input_unit_type_for_x": {
                    "type": "string",
                    "enum": [
                        "",
                        "Dimensionless"
                    ],
                    "default": "Dimensionless"
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
                }
            },
            "required": [
                "coefficient1_c1",
                "coefficient2_c2",
                "coefficient3_c3",
                "coefficient4_c4",
                "coefficient5_c5",
                "minimum_value_of_x",
                "maximum_value_of_x"
            ]
        }
    },
    "group": "Performance Curves",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
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
            "coefficient1_c1": {
                "field_name": "Coefficient1 C1",
                "field_type": "n"
            },
            "coefficient2_c2": {
                "field_name": "Coefficient2 C2",
                "field_type": "n"
            },
            "coefficient3_c3": {
                "field_name": "Coefficient3 C3",
                "field_type": "n"
            },
            "coefficient4_c4": {
                "field_name": "Coefficient4 C4",
                "field_type": "n"
            },
            "coefficient5_c5": {
                "field_name": "Coefficient5 C5",
                "field_type": "n"
            },
            "minimum_value_of_x": {
                "field_name": "Minimum Value of x",
                "field_type": "n"
            },
            "maximum_value_of_x": {
                "field_name": "Maximum Value of x",
                "field_type": "n"
            },
            "minimum_curve_output": {
                "field_name": "Minimum Curve Output",
                "field_type": "n"
            },
            "maximum_curve_output": {
                "field_name": "Maximum Curve Output",
                "field_type": "n"
            },
            "input_unit_type_for_x": {
                "field_name": "Input Unit Type for x",
                "field_type": "a"
            },
            "output_unit_type": {
                "field_name": "Output Unit Type",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "coefficient1_c1",
            "coefficient2_c2",
            "coefficient3_c3",
            "coefficient4_c4",
            "coefficient5_c5",
            "minimum_value_of_x",
            "maximum_value_of_x",
            "minimum_curve_output",
            "maximum_curve_output",
            "input_unit_type_for_x",
            "output_unit_type"
        ],
        "alphas": {
            "fields": [
                "name",
                "input_unit_type_for_x",
                "output_unit_type"
            ]
        },
        "numerics": {
            "fields": [
                "coefficient1_c1",
                "coefficient2_c2",
                "coefficient3_c3",
                "coefficient4_c4",
                "coefficient5_c5",
                "minimum_value_of_x",
                "maximum_value_of_x",
                "minimum_curve_output",
                "maximum_curve_output"
            ]
        }
    },
    "type": "object",
    "memo": "Double exponential decay curve with one independent variable. Input consists of the curve name, the five coefficients, and the maximum and minimum valid independent variable values. Optional inputs for the curve minimum and maximum may be used to limit the output of the performance curve. curve = C1+C2*exp(C3*x)+C4*exp(C5*x)"
}
```
