```
{
    "WindowMaterial:Gap:EquivalentLayer": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "gas_type": {
                        "type": "string",
                        "enum": [
                            "AIR",
                            "ARGON",
                            "CUSTOM",
                            "KRYPTON",
                            "XENON"
                        ]
                    },
                    "thickness": {
                        "type": "number",
                        "units": "m",
                        "exclusiveMinimum": 0.0,
                        "ip-units": "in"
                    },
                    "gap_vent_type": {
                        "type": "string",
                        "enum": [
                            "Sealed",
                            "VentedIndoor",
                            "VentedOutdoor"
                        ],
                        "note": "Sealed means the gap is enclosed and gas tight, i.e., no venting to indoor or outdoor environment. VentedIndoor means the gap is vented to indoor environment, and VentedOutdoor means the gap is vented to the outdoor environment. The gap types VentedIndoor and VentedOutdoor are used with gas type \"Air\" only."
                    },
                    "conductivity_coefficient_a": {
                        "type": "number",
                        "units": "W/m-K",
                        "note": "Used only if Gas Type = Custom"
                    },
                    "conductivity_coefficient_b": {
                        "type": "number",
                        "units": "W/m-K2",
                        "note": "Used only if Gas Type = Custom"
                    },
                    "conductivity_coefficient_c": {
                        "type": "number",
                        "units": "W/m-K3",
                        "note": "Used only if Gas Type = Custom"
                    },
                    "viscosity_coefficient_a": {
                        "type": "number",
                        "units": "kg/m-s",
                        "note": "Used only if Gas Type = Custom",
                        "exclusiveMinimum": 0.0
                    },
                    "viscosity_coefficient_b": {
                        "type": "number",
                        "units": "kg/m-s-K",
                        "note": "Used only if Gas Type = Custom"
                    },
                    "viscosity_coefficient_c": {
                        "type": "number",
                        "units": "kg/m-s-K2",
                        "note": "Used only if Gas Type = Custom"
                    },
                    "specific_heat_coefficient_a": {
                        "type": "number",
                        "units": "J/kg-K",
                        "note": "Used only if Gas Type = Custom",
                        "exclusiveMinimum": 0.0
                    },
                    "specific_heat_coefficient_b": {
                        "type": "number",
                        "units": "J/kg-K2",
                        "note": "Used only if Gas Type = Custom"
                    },
                    "specific_heat_coefficient_c": {
                        "type": "number",
                        "units": "J/kg-K3",
                        "note": "Used only if Gas Type = Custom"
                    },
                    "molecular_weight": {
                        "type": "number",
                        "note": "Used only if Gas Type = Custom",
                        "units": "g/mol",
                        "minimum": 20.0,
                        "maximum": 200.0
                    },
                    "specific_heat_ratio": {
                        "type": "number",
                        "note": "Used only if Gas Type = Custom",
                        "exclusiveMinimum": 1.0
                    }
                },
                "required": [
                    "gas_type",
                    "thickness",
                    "gap_vent_type"
                ]
            }
        },
        "group": "Surface Construction Elements",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "WindowEquivalentLayerMaterialNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "gas_type": {
                    "field_name": "Gas Type",
                    "field_type": "a"
                },
                "thickness": {
                    "field_name": "Thickness",
                    "field_type": "n"
                },
                "gap_vent_type": {
                    "field_name": "Gap Vent Type",
                    "field_type": "a"
                },
                "conductivity_coefficient_a": {
                    "field_name": "Conductivity Coefficient A",
                    "field_type": "n"
                },
                "conductivity_coefficient_b": {
                    "field_name": "Conductivity Coefficient B",
                    "field_type": "n"
                },
                "conductivity_coefficient_c": {
                    "field_name": "Conductivity Coefficient C",
                    "field_type": "n"
                },
                "viscosity_coefficient_a": {
                    "field_name": "Viscosity Coefficient A",
                    "field_type": "n"
                },
                "viscosity_coefficient_b": {
                    "field_name": "Viscosity Coefficient B",
                    "field_type": "n"
                },
                "viscosity_coefficient_c": {
                    "field_name": "Viscosity Coefficient C",
                    "field_type": "n"
                },
                "specific_heat_coefficient_a": {
                    "field_name": "Specific Heat Coefficient A",
                    "field_type": "n"
                },
                "specific_heat_coefficient_b": {
                    "field_name": "Specific Heat Coefficient B",
                    "field_type": "n"
                },
                "specific_heat_coefficient_c": {
                    "field_name": "Specific Heat Coefficient C",
                    "field_type": "n"
                },
                "molecular_weight": {
                    "field_name": "Molecular Weight",
                    "field_type": "n"
                },
                "specific_heat_ratio": {
                    "field_name": "Specific Heat Ratio",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "gas_type",
                "thickness",
                "gap_vent_type",
                "conductivity_coefficient_a",
                "conductivity_coefficient_b",
                "conductivity_coefficient_c",
                "viscosity_coefficient_a",
                "viscosity_coefficient_b",
                "viscosity_coefficient_c",
                "specific_heat_coefficient_a",
                "specific_heat_coefficient_b",
                "specific_heat_coefficient_c",
                "molecular_weight",
                "specific_heat_ratio"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "gas_type",
                    "gap_vent_type"
                ]
            },
            "numerics": {
                "fields": [
                    "thickness",
                    "conductivity_coefficient_a",
                    "conductivity_coefficient_b",
                    "conductivity_coefficient_c",
                    "viscosity_coefficient_a",
                    "viscosity_coefficient_b",
                    "viscosity_coefficient_c",
                    "specific_heat_coefficient_a",
                    "specific_heat_coefficient_b",
                    "specific_heat_coefficient_c",
                    "molecular_weight",
                    "specific_heat_ratio"
                ]
            }
        },
        "type": "object",
        "memo": "Gas material properties that are used in Windows Equivalent Layer References only WindowMaterial:Gas properties",
        "min_fields": 3.0
    }
}
```
