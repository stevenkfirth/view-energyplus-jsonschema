```
{
    "Curve:QuadLinear": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "coefficient1_constant": {
                        "type": "number"
                    },
                    "coefficient2_w": {
                        "type": "number"
                    },
                    "coefficient3_x": {
                        "type": "number"
                    },
                    "coefficient4_y": {
                        "type": "number"
                    },
                    "coefficient5_z": {
                        "type": "number"
                    },
                    "minimum_value_of_w": {
                        "type": "number",
                        "unitsBasedOnField": "input_unit_type_for_w"
                    },
                    "maximum_value_of_w": {
                        "type": "number",
                        "unitsBasedOnField": "input_unit_type_for_w"
                    },
                    "minimum_value_of_x": {
                        "type": "number",
                        "unitsBasedOnField": "input_unit_type_for_x"
                    },
                    "maximum_value_of_x": {
                        "type": "number",
                        "unitsBasedOnField": "input_unit_type_for_x"
                    },
                    "minimum_value_of_y": {
                        "type": "number",
                        "unitsBasedOnField": "input_unit_type_for_y"
                    },
                    "maximum_value_of_y": {
                        "type": "number",
                        "unitsBasedOnField": "input_unit_type_for_y"
                    },
                    "minimum_value_of_z": {
                        "type": "number",
                        "unitsBasedOnField": "input_unit_type_for_z"
                    },
                    "maximum_value_of_z": {
                        "type": "number",
                        "unitsBasedOnField": "input_unit_type_for_z"
                    },
                    "minimum_curve_output": {
                        "type": "number",
                        "note": "Specify the minimum value calculated by this curve object",
                        "unitsBasedOnField": "input_unit_type_for_y"
                    },
                    "maximum_curve_output": {
                        "type": "number",
                        "note": "Specify the maximum value calculated by this curve object",
                        "unitsBasedOnField": "input_unit_type_for_y"
                    },
                    "input_unit_type_for_w": {
                        "type": "string",
                        "enum": [
                            "",
                            "Dimensionless",
                            "Distance",
                            "MassFlow",
                            "Power",
                            "Temperature",
                            "VolumetricFlow",
                            "VolumetricFlowPerPower"
                        ],
                        "default": "Dimensionless"
                    },
                    "input_unit_type_for_x": {
                        "type": "string",
                        "enum": [
                            "",
                            "Dimensionless",
                            "Distance",
                            "MassFlow",
                            "Power",
                            "Temperature",
                            "VolumetricFlow",
                            "VolumetricFlowPerPower"
                        ],
                        "default": "Dimensionless"
                    },
                    "input_unit_type_for_y": {
                        "type": "string",
                        "enum": [
                            "",
                            "Dimensionless",
                            "Distance",
                            "MassFlow",
                            "Power",
                            "Temperature",
                            "VolumetricFlow",
                            "VolumetricFlowPerPower"
                        ],
                        "default": "Dimensionless"
                    },
                    "input_unit_type_for_z": {
                        "type": "string",
                        "enum": [
                            "",
                            "Dimensionless",
                            "Distance",
                            "MassFlow",
                            "Power",
                            "Temperature",
                            "VolumetricFlow",
                            "VolumetricFlowPerPower"
                        ],
                        "default": "Dimensionless"
                    }
                },
                "required": [
                    "coefficient1_constant",
                    "coefficient2_w",
                    "coefficient3_x",
                    "coefficient4_y",
                    "coefficient5_z",
                    "minimum_value_of_w",
                    "maximum_value_of_w",
                    "minimum_value_of_x",
                    "maximum_value_of_x",
                    "minimum_value_of_y",
                    "maximum_value_of_y",
                    "minimum_value_of_z",
                    "maximum_value_of_z"
                ]
            }
        },
        "group": "Performance Curves",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "QuadvariateFunctions"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "coefficient1_constant": {
                    "field_name": "Coefficient1 Constant",
                    "field_type": "n"
                },
                "coefficient2_w": {
                    "field_name": "Coefficient2 w",
                    "field_type": "n"
                },
                "coefficient3_x": {
                    "field_name": "Coefficient3 x",
                    "field_type": "n"
                },
                "coefficient4_y": {
                    "field_name": "Coefficient4 y",
                    "field_type": "n"
                },
                "coefficient5_z": {
                    "field_name": "Coefficient5 z",
                    "field_type": "n"
                },
                "minimum_value_of_w": {
                    "field_name": "Minimum Value of w",
                    "field_type": "n"
                },
                "maximum_value_of_w": {
                    "field_name": "Maximum Value of w",
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
                "minimum_value_of_y": {
                    "field_name": "Minimum Value of y",
                    "field_type": "n"
                },
                "maximum_value_of_y": {
                    "field_name": "Maximum Value of y",
                    "field_type": "n"
                },
                "minimum_value_of_z": {
                    "field_name": "Minimum Value of z",
                    "field_type": "n"
                },
                "maximum_value_of_z": {
                    "field_name": "Maximum Value of z",
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
                "input_unit_type_for_w": {
                    "field_name": "Input Unit Type for w",
                    "field_type": "a"
                },
                "input_unit_type_for_x": {
                    "field_name": "Input Unit Type for x",
                    "field_type": "a"
                },
                "input_unit_type_for_y": {
                    "field_name": "Input Unit Type for y",
                    "field_type": "a"
                },
                "input_unit_type_for_z": {
                    "field_name": "Input Unit Type for z",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "coefficient1_constant",
                "coefficient2_w",
                "coefficient3_x",
                "coefficient4_y",
                "coefficient5_z",
                "minimum_value_of_w",
                "maximum_value_of_w",
                "minimum_value_of_x",
                "maximum_value_of_x",
                "minimum_value_of_y",
                "maximum_value_of_y",
                "minimum_value_of_z",
                "maximum_value_of_z",
                "minimum_curve_output",
                "maximum_curve_output",
                "input_unit_type_for_w",
                "input_unit_type_for_x",
                "input_unit_type_for_y",
                "input_unit_type_for_z"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "input_unit_type_for_w",
                    "input_unit_type_for_x",
                    "input_unit_type_for_y",
                    "input_unit_type_for_z"
                ]
            },
            "numerics": {
                "fields": [
                    "coefficient1_constant",
                    "coefficient2_w",
                    "coefficient3_x",
                    "coefficient4_y",
                    "coefficient5_z",
                    "minimum_value_of_w",
                    "maximum_value_of_w",
                    "minimum_value_of_x",
                    "maximum_value_of_x",
                    "minimum_value_of_y",
                    "maximum_value_of_y",
                    "minimum_value_of_z",
                    "maximum_value_of_z",
                    "minimum_curve_output",
                    "maximum_curve_output"
                ]
            }
        },
        "type": "object",
        "memo": "Linear curve with four independent variables. Input for the linear curve consists of a curve name, the two coefficients, and the maximum and minimum valid independent variable values. Optional inputs for curve minimum and maximum may be used to limit the output of the performance curve. curve = C1 + C2*w + C3*x + C4*y + C5*z"
    }
}
```
