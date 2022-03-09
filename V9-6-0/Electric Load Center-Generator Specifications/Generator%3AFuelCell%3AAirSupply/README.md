```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "air_inlet_node_name": {
                    "type": "string"
                },
                "blower_power_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "blower_heat_loss_factor": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "air_supply_rate_calculation_mode": {
                    "type": "string",
                    "enum": [
                        "AirRatiobyStoics",
                        "QuadraticFunctionofElectricPower",
                        "QuadraticFunctionofFuelRate"
                    ]
                },
                "stoichiometric_ratio": {
                    "type": "number",
                    "note": "This is the excess air \"stoics\" the value entered is incremented by 1 in the model."
                },
                "air_rate_function_of_electric_power_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "air_rate_air_temperature_coefficient": {
                    "type": "number"
                },
                "air_rate_function_of_fuel_rate_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "air_intake_heat_recovery_mode": {
                    "type": "string",
                    "enum": [
                        "NoRecovery",
                        "RecoverAuxiliaryBurner",
                        "RecoverBurnerInverterStorage",
                        "RecoverElectricalStorage",
                        "RecoverInverter",
                        "RecoverInverterandStorage"
                    ]
                },
                "air_supply_constituent_mode": {
                    "type": "string",
                    "enum": [
                        "AmbientAir",
                        "UserDefinedConstituents"
                    ]
                },
                "number_of_userdefined_constituents": {
                    "type": "number",
                    "maximum": 5.0
                },
                "constituent_fractions": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "constituent_name": {
                                "type": "string",
                                "enum": [
                                    "Argon",
                                    "CarbonDioxide",
                                    "Nitrogen",
                                    "Oxygen",
                                    "Water"
                                ]
                            },
                            "molar_fraction": {
                                "type": "number",
                                "minimum": 0.0,
                                "maximum": 1.0
                            }
                        },
                        "type": "object"
                    }
                }
            },
            "required": [
                "air_supply_rate_calculation_mode",
                "air_intake_heat_recovery_mode",
                "air_supply_constituent_mode"
            ]
        }
    },
    "group": "Electric Load Center-Generator Specifications",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "FCAirSupNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "air_inlet_node_name": {
                "field_name": "Air Inlet Node Name",
                "field_type": "a"
            },
            "blower_power_curve_name": {
                "field_name": "Blower Power Curve Name",
                "field_type": "a"
            },
            "blower_heat_loss_factor": {
                "field_name": "Blower Heat Loss Factor",
                "field_type": "n"
            },
            "air_supply_rate_calculation_mode": {
                "field_name": "Air Supply Rate Calculation Mode",
                "field_type": "a"
            },
            "stoichiometric_ratio": {
                "field_name": "Stoichiometric Ratio",
                "field_type": "n"
            },
            "air_rate_function_of_electric_power_curve_name": {
                "field_name": "Air Rate Function of Electric Power Curve Name",
                "field_type": "a"
            },
            "air_rate_air_temperature_coefficient": {
                "field_name": "Air Rate Air Temperature Coefficient",
                "field_type": "n"
            },
            "air_rate_function_of_fuel_rate_curve_name": {
                "field_name": "Air Rate Function of Fuel Rate Curve Name",
                "field_type": "a"
            },
            "air_intake_heat_recovery_mode": {
                "field_name": "Air Intake Heat Recovery Mode",
                "field_type": "a"
            },
            "air_supply_constituent_mode": {
                "field_name": "Air Supply Constituent Mode",
                "field_type": "a"
            },
            "number_of_userdefined_constituents": {
                "field_name": "Number of UserDefined Constituents",
                "field_type": "n"
            },
            "constituent_name": {
                "field_name": "Constituent Name",
                "field_type": "a"
            },
            "molar_fraction": {
                "field_name": "Molar Fraction",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "air_inlet_node_name",
            "blower_power_curve_name",
            "blower_heat_loss_factor",
            "air_supply_rate_calculation_mode",
            "stoichiometric_ratio",
            "air_rate_function_of_electric_power_curve_name",
            "air_rate_air_temperature_coefficient",
            "air_rate_function_of_fuel_rate_curve_name",
            "air_intake_heat_recovery_mode",
            "air_supply_constituent_mode",
            "number_of_userdefined_constituents"
        ],
        "alphas": {
            "fields": [
                "name",
                "air_inlet_node_name",
                "blower_power_curve_name",
                "air_supply_rate_calculation_mode",
                "air_rate_function_of_electric_power_curve_name",
                "air_rate_function_of_fuel_rate_curve_name",
                "air_intake_heat_recovery_mode",
                "air_supply_constituent_mode"
            ],
            "extensions": [
                "constituent_name"
            ]
        },
        "numerics": {
            "fields": [
                "blower_heat_loss_factor",
                "stoichiometric_ratio",
                "air_rate_air_temperature_coefficient",
                "number_of_userdefined_constituents"
            ],
            "extensions": [
                "molar_fraction"
            ]
        },
        "extensibles": [
            "constituent_name",
            "molar_fraction"
        ],
        "extension": "constituent_fractions"
    },
    "type": "object",
    "memo": "Used to define details of the air supply subsystem for a fuel cell power generator.",
    "extensible_size": 2.0
}
```
