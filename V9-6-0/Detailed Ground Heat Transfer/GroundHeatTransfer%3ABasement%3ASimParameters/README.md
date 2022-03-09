```
{
    "GroundHeatTransfer:Basement:SimParameters": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "f_multiplier_for_the_adi_solution": {
                        "type": "number",
                        "note": "0<F<1.0, typically 0.1 (0.3 for high k soil - saturated sand is about 2.6 w/m-K)",
                        "exclusiveMinimum": 0.0,
                        "maximum": 1.0
                    },
                    "iyrs_maximum_number_of_yearly_iterations_": {
                        "type": "number",
                        "note": "typically 15-30]",
                        "minimum": 0.0,
                        "default": 15.0
                    }
                }
            }
        },
        "group": "Detailed Ground Heat Transfer",
        "legacy_idd": {
            "field_info": {
                "f_multiplier_for_the_adi_solution": {
                    "field_name": "F: Multiplier for the ADI solution",
                    "field_type": "n"
                },
                "iyrs_maximum_number_of_yearly_iterations_": {
                    "field_name": "IYRS: Maximum number of yearly iterations:",
                    "field_type": "n"
                }
            },
            "fields": [
                "f_multiplier_for_the_adi_solution",
                "iyrs_maximum_number_of_yearly_iterations_"
            ],
            "alphas": {
                "fields": []
            },
            "numerics": {
                "fields": [
                    "f_multiplier_for_the_adi_solution",
                    "iyrs_maximum_number_of_yearly_iterations_"
                ]
            }
        },
        "type": "object",
        "memo": "Specifies certain parameters that control the Basement preprocessor ground heat transfer simulation."
    }
}
```
