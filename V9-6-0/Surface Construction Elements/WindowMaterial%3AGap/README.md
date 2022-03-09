```
{
    "WindowMaterial:Gap": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "thickness": {
                        "type": "number",
                        "units": "m",
                        "exclusiveMinimum": 0.0
                    },
                    "gas_or_gas_mixture_": {
                        "type": "string",
                        "note": "This field should reference only WindowMaterial:Gas or WindowMaterial:GasMixture objects",
                        "data_type": "object_list",
                        "object_list": [
                            "WindowGasAndGasMixtures"
                        ]
                    },
                    "pressure": {
                        "type": "number",
                        "units": "Pa",
                        "default": 101325.0
                    },
                    "deflection_state": {
                        "type": "string",
                        "note": "If left blank, it will be considered that gap is not deflected",
                        "data_type": "object_list",
                        "object_list": [
                            "WindowGapDeflectionStates"
                        ]
                    },
                    "support_pillar": {
                        "type": "string",
                        "note": "If left blank, it will be considered that gap does not have support pillars",
                        "data_type": "object_list",
                        "object_list": [
                            "WindowGapSupportPillars"
                        ]
                    }
                },
                "required": [
                    "thickness",
                    "gas_or_gas_mixture_"
                ]
            }
        },
        "group": "Surface Construction Elements",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "CFSGap"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "thickness": {
                    "field_name": "Thickness",
                    "field_type": "n"
                },
                "gas_or_gas_mixture_": {
                    "field_name": "Gas (or Gas Mixture)",
                    "field_type": "a"
                },
                "pressure": {
                    "field_name": "Pressure",
                    "field_type": "n"
                },
                "deflection_state": {
                    "field_name": "Deflection State",
                    "field_type": "a"
                },
                "support_pillar": {
                    "field_name": "Support Pillar",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "thickness",
                "gas_or_gas_mixture_",
                "pressure",
                "deflection_state",
                "support_pillar"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "gas_or_gas_mixture_",
                    "deflection_state",
                    "support_pillar"
                ]
            },
            "numerics": {
                "fields": [
                    "thickness",
                    "pressure"
                ]
            }
        },
        "type": "object",
        "memo": "Used to define the gap between two layers in a complex fenestration system, where the Construction:ComplexFenestrationState object is used. It is referenced as a layer in the Construction:ComplexFenestrationState object. It cannot be referenced as a layer from the Construction object."
    }
}
```
