```
{
    "Curve:Bicubic": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "coefficient1_constant": {
                        "type": "number"
                    },
                    "coefficient2_x": {
                        "type": "number"
                    },
                    "coefficient3_x_2": {
                        "type": "number"
                    },
                    "coefficient4_y": {
                        "type": "number"
                    },
                    "coefficient5_y_2": {
                        "type": "number"
                    },
                    "coefficient6_x_y": {
                        "type": "number"
                    },
                    "coefficient7_x_3": {
                        "type": "number"
                    },
                    "coefficient8_y_3": {
                        "type": "number"
                    },
                    "coefficient9_x_2_y": {
                        "type": "number"
                    },
                    "coefficient10_x_y_2": {
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
                    "minimum_value_of_y": {
                        "type": "number",
                        "unitsBasedOnField": "input_unit_type_for_y"
                    },
                    "maximum_value_of_y": {
                        "type": "number",
                        "unitsBasedOnField": "input_unit_type_for_y"
                    },
                    "minimum_curve_output": {
                        "type": "number",
                        "note": "Specify the minimum value calculated by this curve object",
                        "unitsBasedOnField": "output_unit_type"
                    },
                    "maximum_curve_output": {
                        "type": "number",
                        "note": "Specify the maximum value calculated by this curve object",
                        "unitsBasedOnField": "output_unit_type"
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
                            "VolumetricFlow"
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
                            "VolumetricFlow"
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
                    "coefficient1_constant",
                    "coefficient2_x",
                    "coefficient3_x_2",
                    "coefficient4_y",
                    "coefficient5_y_2",
                    "coefficient6_x_y",
                    "coefficient7_x_3",
                    "coefficient8_y_3",
                    "coefficient9_x_2_y",
                    "coefficient10_x_y_2",
                    "minimum_value_of_x",
                    "maximum_value_of_x",
                    "minimum_value_of_y",
                    "maximum_value_of_y"
                ]
            }
        },
        "group": "Performance Curves",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "BivariateFunctions"
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
                "coefficient2_x": {
                    "field_name": "Coefficient2 x",
                    "field_type": "n"
                },
                "coefficient3_x_2": {
                    "field_name": "Coefficient3 x**2",
                    "field_type": "n"
                },
                "coefficient4_y": {
                    "field_name": "Coefficient4 y",
                    "field_type": "n"
                },
                "coefficient5_y_2": {
                    "field_name": "Coefficient5 y**2",
                    "field_type": "n"
                },
                "coefficient6_x_y": {
                    "field_name": "Coefficient6 x*y",
                    "field_type": "n"
                },
                "coefficient7_x_3": {
                    "field_name": "Coefficient7 x**3",
                    "field_type": "n"
                },
                "coefficient8_y_3": {
                    "field_name": "Coefficient8 y**3",
                    "field_type": "n"
                },
                "coefficient9_x_2_y": {
                    "field_name": "Coefficient9 x**2*y",
                    "field_type": "n"
                },
                "coefficient10_x_y_2": {
                    "field_name": "Coefficient10 x*y**2",
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
                "minimum_curve_output": {
                    "field_name": "Minimum Curve Output",
                    "field_type": "n"
                },
                "maximum_curve_output": {
                    "field_name": "Maximum Curve Output",
                    "field_type": "n"
                },
                "input_unit_type_for_x": {
                    "field_name": "Input Unit Type for X",
                    "field_type": "a"
                },
                "input_unit_type_for_y": {
                    "field_name": "Input Unit Type for Y",
                    "field_type": "a"
                },
                "output_unit_type": {
                    "field_name": "Output Unit Type",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "coefficient1_constant",
                "coefficient2_x",
                "coefficient3_x_2",
                "coefficient4_y",
                "coefficient5_y_2",
                "coefficient6_x_y",
                "coefficient7_x_3",
                "coefficient8_y_3",
                "coefficient9_x_2_y",
                "coefficient10_x_y_2",
                "minimum_value_of_x",
                "maximum_value_of_x",
                "minimum_value_of_y",
                "maximum_value_of_y",
                "minimum_curve_output",
                "maximum_curve_output",
                "input_unit_type_for_x",
                "input_unit_type_for_y",
                "output_unit_type"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "input_unit_type_for_x",
                    "input_unit_type_for_y",
                    "output_unit_type"
                ]
            },
            "numerics": {
                "fields": [
                    "coefficient1_constant",
                    "coefficient2_x",
                    "coefficient3_x_2",
                    "coefficient4_y",
                    "coefficient5_y_2",
                    "coefficient6_x_y",
                    "coefficient7_x_3",
                    "coefficient8_y_3",
                    "coefficient9_x_2_y",
                    "coefficient10_x_y_2",
                    "minimum_value_of_x",
                    "maximum_value_of_x",
                    "minimum_value_of_y",
                    "maximum_value_of_y",
                    "minimum_curve_output",
                    "maximum_curve_output"
                ]
            }
        },
        "type": "object",
        "memo": "Cubic curve with two independent variables. Input consists of the curve name, the ten coefficients, and the minimum and maximum values for each of the independent variables. Optional inputs for curve minimum and maximum may be used to limit the output of the performance curve. curve = C1 + C2*x + C3*x**2 + C4*y + C5*y**2 + C6*x*y + C7*x**3 + C8*y**3 + C9*x**2*y + C10*x*y**2"
    }
}
```
