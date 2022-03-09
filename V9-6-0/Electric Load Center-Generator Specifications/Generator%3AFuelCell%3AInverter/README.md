```
{
    "Generator:FuelCell:Inverter": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "inverter_efficiency_calculation_mode": {
                        "type": "string",
                        "enum": [
                            "Constant",
                            "Quadratic"
                        ]
                    },
                    "inverter_efficiency": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "efficiency_function_of_dc_power_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ]
                    }
                }
            }
        },
        "group": "Electric Load Center-Generator Specifications",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "FCInverterNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "inverter_efficiency_calculation_mode": {
                    "field_name": "Inverter Efficiency Calculation Mode",
                    "field_type": "a"
                },
                "inverter_efficiency": {
                    "field_name": "Inverter Efficiency",
                    "field_type": "n"
                },
                "efficiency_function_of_dc_power_curve_name": {
                    "field_name": "Efficiency Function of DC Power Curve Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "inverter_efficiency_calculation_mode",
                "inverter_efficiency",
                "efficiency_function_of_dc_power_curve_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "inverter_efficiency_calculation_mode",
                    "efficiency_function_of_dc_power_curve_name"
                ]
            },
            "numerics": {
                "fields": [
                    "inverter_efficiency"
                ]
            }
        },
        "type": "object",
        "memo": "Used to describe the power condition unit subsystem of a fuel cell power generator. This object models an inverter system contained within a fuel cell system that converts from direct current (DC) to alternating current (AC)."
    }
}
```
