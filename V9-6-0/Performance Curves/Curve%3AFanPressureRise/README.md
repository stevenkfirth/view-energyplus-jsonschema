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
                "minimum_value_of_qfan": {
                    "type": "number",
                    "units": "m3/s"
                },
                "maximum_value_of_qfan": {
                    "type": "number",
                    "units": "m3/s"
                },
                "minimum_value_of_psm": {
                    "type": "number",
                    "units": "Pa",
                    "ip-units": "Pa"
                },
                "maximum_value_of_psm": {
                    "type": "number",
                    "units": "Pa",
                    "ip-units": "Pa"
                },
                "minimum_curve_output": {
                    "type": "number",
                    "units": "Pa",
                    "ip-units": "Pa",
                    "note": "Specify the minimum value calculated by this curve object"
                },
                "maximum_curve_output": {
                    "type": "number",
                    "units": "Pa",
                    "ip-units": "Pa",
                    "note": "Specify the maximum value calculated by this curve object"
                }
            },
            "required": [
                "coefficient1_c1",
                "coefficient2_c2",
                "coefficient3_c3",
                "coefficient4_c4",
                "minimum_value_of_qfan",
                "maximum_value_of_qfan",
                "minimum_value_of_psm",
                "maximum_value_of_psm"
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
            "minimum_value_of_qfan": {
                "field_name": "Minimum Value of Qfan",
                "field_type": "n"
            },
            "maximum_value_of_qfan": {
                "field_name": "Maximum Value of Qfan",
                "field_type": "n"
            },
            "minimum_value_of_psm": {
                "field_name": "Minimum Value of Psm",
                "field_type": "n"
            },
            "maximum_value_of_psm": {
                "field_name": "Maximum Value of Psm",
                "field_type": "n"
            },
            "minimum_curve_output": {
                "field_name": "Minimum Curve Output",
                "field_type": "n"
            },
            "maximum_curve_output": {
                "field_name": "Maximum Curve Output",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "coefficient1_c1",
            "coefficient2_c2",
            "coefficient3_c3",
            "coefficient4_c4",
            "minimum_value_of_qfan",
            "maximum_value_of_qfan",
            "minimum_value_of_psm",
            "maximum_value_of_psm",
            "minimum_curve_output",
            "maximum_curve_output"
        ],
        "alphas": {
            "fields": [
                "name"
            ]
        },
        "numerics": {
            "fields": [
                "coefficient1_c1",
                "coefficient2_c2",
                "coefficient3_c3",
                "coefficient4_c4",
                "minimum_value_of_qfan",
                "maximum_value_of_qfan",
                "minimum_value_of_psm",
                "maximum_value_of_psm",
                "minimum_curve_output",
                "maximum_curve_output"
            ]
        }
    },
    "type": "object",
    "memo": "Special curve type with two independent variables. Input for the fan total pressure rise curve consists of the curve name, the four coefficients, and the maximum and minimum valid independent variable values. Optional inputs for the curve minimum and maximum may be used to limit the output of the performance curve. curve = C1*Qfan**2+C2*Qfan+C3*Qfan*(Psm-Po)**0.5+C4*(Psm-Po) Po assumed to be zero See InputOut Reference for curve details"
}
```
