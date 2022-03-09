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
                "coefficient6_c6": {
                    "type": "number"
                },
                "coefficient7_c7": {
                    "type": "number"
                },
                "coefficient8_c8": {
                    "type": "number"
                },
                "coefficient9_c9": {
                    "type": "number"
                },
                "coefficient10_c10": {
                    "type": "number"
                },
                "coefficient11_c11": {
                    "type": "number"
                },
                "coefficient12_c12": {
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
                "input_unit_type_for_y": {
                    "type": "string",
                    "enum": [
                        "",
                        "Dimensionless"
                    ],
                    "default": "Dimensionless"
                },
                "input_unit_type_for_z": {
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
                "coefficient6_c6",
                "coefficient7_c7",
                "coefficient8_c8",
                "coefficient9_c9",
                "coefficient10_c10",
                "coefficient11_c11",
                "coefficient12_c12",
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
            "coefficient6_c6": {
                "field_name": "Coefficient6 C6",
                "field_type": "n"
            },
            "coefficient7_c7": {
                "field_name": "Coefficient7 C7",
                "field_type": "n"
            },
            "coefficient8_c8": {
                "field_name": "Coefficient8 C8",
                "field_type": "n"
            },
            "coefficient9_c9": {
                "field_name": "Coefficient9 C9",
                "field_type": "n"
            },
            "coefficient10_c10": {
                "field_name": "Coefficient10 C10",
                "field_type": "n"
            },
            "coefficient11_c11": {
                "field_name": "Coefficient11 C11",
                "field_type": "n"
            },
            "coefficient12_c12": {
                "field_name": "Coefficient12 C12",
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
            "coefficient6_c6",
            "coefficient7_c7",
            "coefficient8_c8",
            "coefficient9_c9",
            "coefficient10_c10",
            "coefficient11_c11",
            "coefficient12_c12",
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
                "coefficient1_c1",
                "coefficient2_c2",
                "coefficient3_c3",
                "coefficient4_c4",
                "coefficient5_c5",
                "coefficient6_c6",
                "coefficient7_c7",
                "coefficient8_c8",
                "coefficient9_c9",
                "coefficient10_c10",
                "coefficient11_c11",
                "coefficient12_c12",
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
    "memo": "This chiller part-load performance curve has three independent variables. Input consists of the curve name, the twelve coefficients, and the maximum and minimum valid independent variable values. Optional inputs for the curve minimum and maximum may be used to limit the output of the performance curve. curve = C1 + C2*x + C3*x**2 + C4*y + C5*y**2 + C6*x*y + C7*x**3 + C8*y**3 + C9*x**2*y + C10*x*y**2 + C11*x**2*y**2 + C12*z*y**3 x = dT* = normalized fractional Lift = dT / dTref y = PLR = part load ratio (cooling load/steady state capacity) z = Tdev* = normalized Tdev = Tdev / dTref Where: dT = Lift = Leaving Condenser Water Temperature - Leaving Chilled Water Temperature dTref = dT at the reference condition Tdev = Leaving Chilled Water Temperature - Reference Chilled Water Temperature"
}
```
