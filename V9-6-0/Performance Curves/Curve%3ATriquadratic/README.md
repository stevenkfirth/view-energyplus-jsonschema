```
{
    "Curve:Triquadratic": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "coefficient1_constant": {
                        "type": "number"
                    },
                    "coefficient2_x_2": {
                        "type": "number"
                    },
                    "coefficient3_x": {
                        "type": "number"
                    },
                    "coefficient4_y_2": {
                        "type": "number"
                    },
                    "coefficient5_y": {
                        "type": "number"
                    },
                    "coefficient6_z_2": {
                        "type": "number"
                    },
                    "coefficient7_z": {
                        "type": "number"
                    },
                    "coefficient8_x_2_y_2": {
                        "type": "number"
                    },
                    "coefficient9_x_y": {
                        "type": "number"
                    },
                    "coefficient10_x_y_2": {
                        "type": "number"
                    },
                    "coefficient11_x_2_y": {
                        "type": "number"
                    },
                    "coefficient12_x_2_z_2": {
                        "type": "number"
                    },
                    "coefficient13_x_z": {
                        "type": "number"
                    },
                    "coefficient14_x_z_2": {
                        "type": "number"
                    },
                    "coefficient15_x_2_z": {
                        "type": "number"
                    },
                    "coefficient16_y_2_z_2": {
                        "type": "number"
                    },
                    "coefficient17_y_z": {
                        "type": "number"
                    },
                    "coefficient18_y_z_2": {
                        "type": "number"
                    },
                    "coefficient19_y_2_z": {
                        "type": "number"
                    },
                    "coefficient20_x_2_y_2_z_2": {
                        "type": "number"
                    },
                    "coefficient21_x_2_y_2_z": {
                        "type": "number"
                    },
                    "coefficient22_x_2_y_z_2": {
                        "type": "number"
                    },
                    "coefficient23_x_y_2_z_2": {
                        "type": "number"
                    },
                    "coefficient24_x_2_y_z": {
                        "type": "number"
                    },
                    "coefficient25_x_y_2_z": {
                        "type": "number"
                    },
                    "coefficient26_x_y_z_2": {
                        "type": "number"
                    },
                    "coefficient27_x_y_z": {
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
                    "input_unit_type_for_z": {
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
                }
            }
        },
        "group": "Performance Curves",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "TrivariateFunctions"
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
                "coefficient2_x_2": {
                    "field_name": "Coefficient2 x**2",
                    "field_type": "n"
                },
                "coefficient3_x": {
                    "field_name": "Coefficient3 x",
                    "field_type": "n"
                },
                "coefficient4_y_2": {
                    "field_name": "Coefficient4 y**2",
                    "field_type": "n"
                },
                "coefficient5_y": {
                    "field_name": "Coefficient5 y",
                    "field_type": "n"
                },
                "coefficient6_z_2": {
                    "field_name": "Coefficient6 z**2",
                    "field_type": "n"
                },
                "coefficient7_z": {
                    "field_name": "Coefficient7 z",
                    "field_type": "n"
                },
                "coefficient8_x_2_y_2": {
                    "field_name": "Coefficient8 x**2*y**2",
                    "field_type": "n"
                },
                "coefficient9_x_y": {
                    "field_name": "Coefficient9 x*y",
                    "field_type": "n"
                },
                "coefficient10_x_y_2": {
                    "field_name": "Coefficient10 x*y**2",
                    "field_type": "n"
                },
                "coefficient11_x_2_y": {
                    "field_name": "Coefficient11 x**2*y",
                    "field_type": "n"
                },
                "coefficient12_x_2_z_2": {
                    "field_name": "Coefficient12 x**2*z**2",
                    "field_type": "n"
                },
                "coefficient13_x_z": {
                    "field_name": "Coefficient13 x*z",
                    "field_type": "n"
                },
                "coefficient14_x_z_2": {
                    "field_name": "Coefficient14 x*z**2",
                    "field_type": "n"
                },
                "coefficient15_x_2_z": {
                    "field_name": "Coefficient15 x**2*z",
                    "field_type": "n"
                },
                "coefficient16_y_2_z_2": {
                    "field_name": "Coefficient16 y**2*z**2",
                    "field_type": "n"
                },
                "coefficient17_y_z": {
                    "field_name": "Coefficient17 y*z",
                    "field_type": "n"
                },
                "coefficient18_y_z_2": {
                    "field_name": "Coefficient18 y*z**2",
                    "field_type": "n"
                },
                "coefficient19_y_2_z": {
                    "field_name": "Coefficient19 y**2*z",
                    "field_type": "n"
                },
                "coefficient20_x_2_y_2_z_2": {
                    "field_name": "Coefficient20 x**2*y**2*z**2",
                    "field_type": "n"
                },
                "coefficient21_x_2_y_2_z": {
                    "field_name": "Coefficient21 x**2*y**2*z",
                    "field_type": "n"
                },
                "coefficient22_x_2_y_z_2": {
                    "field_name": "Coefficient22 x**2*y*z**2",
                    "field_type": "n"
                },
                "coefficient23_x_y_2_z_2": {
                    "field_name": "Coefficient23 x*y**2*z**2",
                    "field_type": "n"
                },
                "coefficient24_x_2_y_z": {
                    "field_name": "Coefficient24 x**2*y*z",
                    "field_type": "n"
                },
                "coefficient25_x_y_2_z": {
                    "field_name": "Coefficient25 x*y**2*z",
                    "field_type": "n"
                },
                "coefficient26_x_y_z_2": {
                    "field_name": "Coefficient26 x*y*z**2",
                    "field_type": "n"
                },
                "coefficient27_x_y_z": {
                    "field_name": "Coefficient27 x*y*z",
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
                "input_unit_type_for_x": {
                    "field_name": "Input Unit Type for X",
                    "field_type": "a"
                },
                "input_unit_type_for_y": {
                    "field_name": "Input Unit Type for Y",
                    "field_type": "a"
                },
                "input_unit_type_for_z": {
                    "field_name": "Input Unit Type for Z",
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
                "coefficient2_x_2",
                "coefficient3_x",
                "coefficient4_y_2",
                "coefficient5_y",
                "coefficient6_z_2",
                "coefficient7_z",
                "coefficient8_x_2_y_2",
                "coefficient9_x_y",
                "coefficient10_x_y_2",
                "coefficient11_x_2_y",
                "coefficient12_x_2_z_2",
                "coefficient13_x_z",
                "coefficient14_x_z_2",
                "coefficient15_x_2_z",
                "coefficient16_y_2_z_2",
                "coefficient17_y_z",
                "coefficient18_y_z_2",
                "coefficient19_y_2_z",
                "coefficient20_x_2_y_2_z_2",
                "coefficient21_x_2_y_2_z",
                "coefficient22_x_2_y_z_2",
                "coefficient23_x_y_2_z_2",
                "coefficient24_x_2_y_z",
                "coefficient25_x_y_2_z",
                "coefficient26_x_y_z_2",
                "coefficient27_x_y_z",
                "minimum_value_of_x",
                "maximum_value_of_x",
                "minimum_value_of_y",
                "maximum_value_of_y",
                "minimum_value_of_z",
                "maximum_value_of_z",
                "minimum_curve_output",
                "maximum_curve_output",
                "input_unit_type_for_x",
                "input_unit_type_for_y",
                "input_unit_type_for_z",
                "output_unit_type"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "input_unit_type_for_x",
                    "input_unit_type_for_y",
                    "input_unit_type_for_z",
                    "output_unit_type"
                ]
            },
            "numerics": {
                "fields": [
                    "coefficient1_constant",
                    "coefficient2_x_2",
                    "coefficient3_x",
                    "coefficient4_y_2",
                    "coefficient5_y",
                    "coefficient6_z_2",
                    "coefficient7_z",
                    "coefficient8_x_2_y_2",
                    "coefficient9_x_y",
                    "coefficient10_x_y_2",
                    "coefficient11_x_2_y",
                    "coefficient12_x_2_z_2",
                    "coefficient13_x_z",
                    "coefficient14_x_z_2",
                    "coefficient15_x_2_z",
                    "coefficient16_y_2_z_2",
                    "coefficient17_y_z",
                    "coefficient18_y_z_2",
                    "coefficient19_y_2_z",
                    "coefficient20_x_2_y_2_z_2",
                    "coefficient21_x_2_y_2_z",
                    "coefficient22_x_2_y_z_2",
                    "coefficient23_x_y_2_z_2",
                    "coefficient24_x_2_y_z",
                    "coefficient25_x_y_2_z",
                    "coefficient26_x_y_z_2",
                    "coefficient27_x_y_z",
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
        "memo": "Quadratic curve with three independent variables. Input consists of the curve name, the twenty seven coefficients, and min and max values for each of the independent variables. Optional inputs for curve minimum and maximum may be used to limit the output of the performance curve. curve = a0 + a1*x**2 + a2*x + a3*y**2 + a4*y + a5*z**2 + a6*z + a7*x**2*y**2 + a8*x*y + a9*x*y**2 + a10*x**2*y + a11*x**2*z**2 + a12*x*z + a13*x*z**2 + a14*x**2*z + a15*y**2*z**2 + a16*y*z + a17*y*z**2 + a18*y**2*z + a19*x**2*y**2*z**2 + a20*x**2*y**2*z + a21*x**2*y*z**2 + a22*x*y**2*z**2 + a23*x**2*y*z + a24*x*y**2*z + a25*x*y*z**2 +a26*x*y*z"
    }
}
```
