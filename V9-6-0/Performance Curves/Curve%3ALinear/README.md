```
{
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
                        "Pressure",
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
            "coefficient1_constant": {
                "field_name": "Coefficient1 Constant",
                "field_type": "n"
            },
            "coefficient2_x": {
                "field_name": "Coefficient2 x",
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
                "field_name": "Input Unit Type for X",
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
                "coefficient1_constant",
                "coefficient2_x",
                "minimum_value_of_x",
                "maximum_value_of_x",
                "minimum_curve_output",
                "maximum_curve_output"
            ]
        }
    },
    "type": "object",
    "memo": "Linear curve with one independent variable. Input for the linear curve consists of a curve name, the two coefficients, and the maximum and minimum valid independent variable values. Optional inputs for curve minimum and maximum may be used to limit the output of the performance curve. curve = C1 + C2*x"
}
```
