```
{
    "HeatBalanceAlgorithm": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "algorithm": {
                        "type": "string",
                        "enum": [
                            "",
                            "CombinedHeatAndMoistureFiniteElement",
                            "ConductionFiniteDifference",
                            "ConductionTransferFunction",
                            "MoisturePenetrationDepthConductionTransferFunction"
                        ],
                        "default": "ConductionTransferFunction"
                    },
                    "surface_temperature_upper_limit": {
                        "type": "number",
                        "minimum": 200.0,
                        "default": 200.0,
                        "units": "C"
                    },
                    "minimum_surface_convection_heat_transfer_coefficient_value": {
                        "type": "number",
                        "units": "W/m2-K",
                        "default": 0.1,
                        "exclusiveMinimum": 0.0
                    },
                    "maximum_surface_convection_heat_transfer_coefficient_value": {
                        "type": "number",
                        "units": "W/m2-K",
                        "default": 1000.0,
                        "minimum": 1.0
                    }
                }
            }
        },
        "group": "Simulation Parameters",
        "legacy_idd": {
            "field_info": {
                "algorithm": {
                    "field_name": "Algorithm",
                    "field_type": "a"
                },
                "surface_temperature_upper_limit": {
                    "field_name": "Surface Temperature Upper Limit",
                    "field_type": "n"
                },
                "minimum_surface_convection_heat_transfer_coefficient_value": {
                    "field_name": "Minimum Surface Convection Heat Transfer Coefficient Value",
                    "field_type": "n"
                },
                "maximum_surface_convection_heat_transfer_coefficient_value": {
                    "field_name": "Maximum Surface Convection Heat Transfer Coefficient Value",
                    "field_type": "n"
                }
            },
            "fields": [
                "algorithm",
                "surface_temperature_upper_limit",
                "minimum_surface_convection_heat_transfer_coefficient_value",
                "maximum_surface_convection_heat_transfer_coefficient_value"
            ],
            "alphas": {
                "fields": [
                    "algorithm"
                ]
            },
            "numerics": {
                "fields": [
                    "surface_temperature_upper_limit",
                    "minimum_surface_convection_heat_transfer_coefficient_value",
                    "maximum_surface_convection_heat_transfer_coefficient_value"
                ]
            }
        },
        "type": "object",
        "maxProperties": 1,
        "memo": "Determines which Heat Balance Algorithm will be used ie. CTF (Conduction Transfer Functions), EMPD (Effective Moisture Penetration Depth with Conduction Transfer Functions). Advanced/Research Usage: CondFD (Conduction Finite Difference) Advanced/Research Usage: ConductionFiniteDifferenceSimplified Advanced/Research Usage: HAMT (Combined Heat And Moisture Finite Element)",
        "format": "singleLine"
    }
}
```
