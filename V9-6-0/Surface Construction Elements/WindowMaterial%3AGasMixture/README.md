```
{
    "WindowMaterial:GasMixture": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "thickness": {
                        "type": "number",
                        "units": "m",
                        "exclusiveMinimum": 0.0
                    },
                    "number_of_gases_in_mixture": {
                        "type": "number",
                        "minimum": 1.0,
                        "maximum": 4.0
                    },
                    "gas_1_type": {
                        "type": "string",
                        "enum": [
                            "Air",
                            "Argon",
                            "Krypton",
                            "Xenon"
                        ]
                    },
                    "gas_1_fraction": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "maximum": 1.0
                    },
                    "gas_2_type": {
                        "type": "string",
                        "enum": [
                            "Air",
                            "Argon",
                            "Krypton",
                            "Xenon"
                        ]
                    },
                    "gas_2_fraction": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "maximum": 1.0
                    },
                    "gas_3_type": {
                        "type": "string",
                        "enum": [
                            "Air",
                            "Argon",
                            "Krypton",
                            "Xenon"
                        ]
                    },
                    "gas_3_fraction": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "maximum": 1.0
                    },
                    "gas_4_type": {
                        "type": "string",
                        "enum": [
                            "Air",
                            "Argon",
                            "Krypton",
                            "Xenon"
                        ]
                    },
                    "gas_4_fraction": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "maximum": 1.0
                    }
                },
                "required": [
                    "thickness",
                    "number_of_gases_in_mixture",
                    "gas_1_type",
                    "gas_1_fraction",
                    "gas_2_type",
                    "gas_2_fraction"
                ]
            }
        },
        "group": "Surface Construction Elements",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "MaterialName",
                "WindowGasAndGasMixtures"
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
                "number_of_gases_in_mixture": {
                    "field_name": "Number of Gases in Mixture",
                    "field_type": "n"
                },
                "gas_1_type": {
                    "field_name": "Gas 1 Type",
                    "field_type": "a"
                },
                "gas_1_fraction": {
                    "field_name": "Gas 1 Fraction",
                    "field_type": "n"
                },
                "gas_2_type": {
                    "field_name": "Gas 2 Type",
                    "field_type": "a"
                },
                "gas_2_fraction": {
                    "field_name": "Gas 2 Fraction",
                    "field_type": "n"
                },
                "gas_3_type": {
                    "field_name": "Gas 3 Type",
                    "field_type": "a"
                },
                "gas_3_fraction": {
                    "field_name": "Gas 3 Fraction",
                    "field_type": "n"
                },
                "gas_4_type": {
                    "field_name": "Gas 4 Type",
                    "field_type": "a"
                },
                "gas_4_fraction": {
                    "field_name": "Gas 4 Fraction",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "thickness",
                "number_of_gases_in_mixture",
                "gas_1_type",
                "gas_1_fraction",
                "gas_2_type",
                "gas_2_fraction",
                "gas_3_type",
                "gas_3_fraction",
                "gas_4_type",
                "gas_4_fraction"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "gas_1_type",
                    "gas_2_type",
                    "gas_3_type",
                    "gas_4_type"
                ]
            },
            "numerics": {
                "fields": [
                    "thickness",
                    "number_of_gases_in_mixture",
                    "gas_1_fraction",
                    "gas_2_fraction",
                    "gas_3_fraction",
                    "gas_4_fraction"
                ]
            }
        },
        "type": "object",
        "memo": "Gas mixtures that are used in Windows or Glass Doors",
        "min_fields": 7.0
    }
}
```
