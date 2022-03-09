```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "fuel_temperature_modeling_mode": {
                    "type": "string",
                    "enum": [
                        "Scheduled",
                        "TemperatureFromAirNode"
                    ]
                },
                "fuel_temperature_reference_node_name": {
                    "type": "string"
                },
                "fuel_temperature_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "compressor_power_multiplier_function_of_fuel_rate_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "compressor_heat_loss_factor": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "fuel_type": {
                    "type": "string",
                    "enum": [
                        "GaseousConstituents",
                        "LiquidGeneric"
                    ]
                },
                "liquid_generic_fuel_lower_heating_value": {
                    "type": "number",
                    "units": "kJ/kg"
                },
                "liquid_generic_fuel_higher_heating_value": {
                    "type": "number",
                    "units": "kJ/kg"
                },
                "liquid_generic_fuel_molecular_weight": {
                    "type": "number",
                    "units": "g/mol"
                },
                "liquid_generic_fuel_co2_emission_factor": {
                    "type": "number"
                },
                "number_of_constituents_in_gaseous_constituent_fuel_supply": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 12.0
                },
                "constituent_1_name": {
                    "type": "string",
                    "enum": [
                        "Argon",
                        "Butane",
                        "CarbonDioxide",
                        "Ethane",
                        "Ethanol",
                        "Hexane",
                        "Hydrogen",
                        "Methane",
                        "Methanol",
                        "Nitrogen",
                        "Oxygen",
                        "Pentane",
                        "Propane",
                        "Water"
                    ]
                },
                "constituent_1_molar_fraction": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "constituent_2_name": {
                    "type": "string",
                    "enum": [
                        "Argon",
                        "Butane",
                        "CarbonDioxide",
                        "Ethane",
                        "Ethanol",
                        "Hexane",
                        "Hydrogen",
                        "Methane",
                        "Methanol",
                        "Nitrogen",
                        "Oxygen",
                        "Pentane",
                        "Propane",
                        "Water"
                    ]
                },
                "constituent_2_molar_fraction": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "constituent_3_name": {
                    "type": "string",
                    "enum": [
                        "Argon",
                        "Butane",
                        "CarbonDioxide",
                        "Ethane",
                        "Ethanol",
                        "Hexane",
                        "Hydrogen",
                        "Methane",
                        "Methanol",
                        "Nitrogen",
                        "Oxygen",
                        "Pentane",
                        "Propane",
                        "Water"
                    ]
                },
                "constituent_3_molar_fraction": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "constituent_4_name": {
                    "type": "string",
                    "enum": [
                        "Argon",
                        "Butane",
                        "CarbonDioxide",
                        "Ethane",
                        "Ethanol",
                        "Hexane",
                        "Hydrogen",
                        "Methane",
                        "Methanol",
                        "Nitrogen",
                        "Oxygen",
                        "Pentane",
                        "Propane",
                        "Water"
                    ]
                },
                "constituent_4_molar_fraction": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "constituent_5_name": {
                    "type": "string",
                    "enum": [
                        "Argon",
                        "Butane",
                        "CarbonDioxide",
                        "Ethane",
                        "Ethanol",
                        "Hexane",
                        "Hydrogen",
                        "Methane",
                        "Methanol",
                        "Nitrogen",
                        "Oxygen",
                        "Pentane",
                        "Propane",
                        "Water"
                    ]
                },
                "constituent_5_molar_fraction": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "constituent_6_name": {
                    "type": "string",
                    "enum": [
                        "Argon",
                        "Butane",
                        "CarbonDioxide",
                        "Ethane",
                        "Ethanol",
                        "Hexane",
                        "Hydrogen",
                        "Methane",
                        "Methanol",
                        "Nitrogen",
                        "Oxygen",
                        "Pentane",
                        "Propane",
                        "Water"
                    ]
                },
                "constituent_6_molar_fraction": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "constituent_7_name": {
                    "type": "string",
                    "enum": [
                        "Butane",
                        "Ethane",
                        "Ethanol",
                        "Hexane",
                        "Hydrogen",
                        "Methane",
                        "Methanol",
                        "Pentane",
                        "Propane"
                    ]
                },
                "constituent_7_molar_fraction": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "constituent_8_name": {
                    "type": "string",
                    "enum": [
                        "Argon",
                        "Butane",
                        "CarbonDioxide",
                        "Ethane",
                        "Ethanol",
                        "Hexane",
                        "Hydrogen",
                        "Methane",
                        "Methanol",
                        "Nitrogen",
                        "Oxygen",
                        "Pentane",
                        "Propane",
                        "Water"
                    ]
                },
                "constituent_8_molar_fraction": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "constituent_9_name": {
                    "type": "string",
                    "enum": [
                        "Argon",
                        "Butane",
                        "CarbonDioxide",
                        "Ethane",
                        "Ethanol",
                        "Hexane",
                        "Hydrogen",
                        "Methane",
                        "Methanol",
                        "Nitrogen",
                        "Oxygen",
                        "Pentane",
                        "Propane",
                        "Water"
                    ]
                },
                "constituent_9_molar_fraction": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "constituent_10_name": {
                    "type": "string",
                    "enum": [
                        "Argon",
                        "Butane",
                        "CarbonDioxide",
                        "Ethane",
                        "Ethanol",
                        "Hexane",
                        "Hydrogen",
                        "Methane",
                        "Methanol",
                        "Nitrogen",
                        "Oxygen",
                        "Pentane",
                        "Propane",
                        "Water"
                    ]
                },
                "constituent_10_molar_fraction": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "constituent_11_name": {
                    "type": "string",
                    "enum": [
                        "Argon",
                        "Butane",
                        "CarbonDioxide",
                        "Ethane",
                        "Ethanol",
                        "Hexane",
                        "Hydrogen",
                        "Methane",
                        "Methanol",
                        "Nitrogen",
                        "Oxygen",
                        "Pentane",
                        "Propane",
                        "Water"
                    ]
                },
                "constituent_11_molar_fraction": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "constituent_12_name": {
                    "type": "string",
                    "enum": [
                        "Argon",
                        "Butane",
                        "CarbonDioxide",
                        "Ethane",
                        "Ethanol",
                        "Hexane",
                        "Hydrogen",
                        "Methane",
                        "Methanol",
                        "Nitrogen",
                        "Oxygen",
                        "Pentane",
                        "Propane",
                        "Water"
                    ]
                },
                "constituent_12_molar_fraction": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0
                }
            }
        }
    },
    "group": "Electric Load Center-Generator Specifications",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "GenFuelSupNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "fuel_temperature_modeling_mode": {
                "field_name": "Fuel Temperature Modeling Mode",
                "field_type": "a"
            },
            "fuel_temperature_reference_node_name": {
                "field_name": "Fuel Temperature Reference Node Name",
                "field_type": "a"
            },
            "fuel_temperature_schedule_name": {
                "field_name": "Fuel Temperature Schedule Name",
                "field_type": "a"
            },
            "compressor_power_multiplier_function_of_fuel_rate_curve_name": {
                "field_name": "Compressor Power Multiplier Function of Fuel Rate Curve Name",
                "field_type": "a"
            },
            "compressor_heat_loss_factor": {
                "field_name": "Compressor Heat Loss Factor",
                "field_type": "n"
            },
            "fuel_type": {
                "field_name": "Fuel Type",
                "field_type": "a"
            },
            "liquid_generic_fuel_lower_heating_value": {
                "field_name": "Liquid Generic Fuel Lower Heating Value",
                "field_type": "n"
            },
            "liquid_generic_fuel_higher_heating_value": {
                "field_name": "Liquid Generic Fuel Higher Heating Value",
                "field_type": "n"
            },
            "liquid_generic_fuel_molecular_weight": {
                "field_name": "Liquid Generic Fuel Molecular Weight",
                "field_type": "n"
            },
            "liquid_generic_fuel_co2_emission_factor": {
                "field_name": "Liquid Generic Fuel CO2 Emission Factor",
                "field_type": "n"
            },
            "number_of_constituents_in_gaseous_constituent_fuel_supply": {
                "field_name": "Number of Constituents in Gaseous Constituent Fuel Supply",
                "field_type": "n"
            },
            "constituent_1_name": {
                "field_name": "Constituent 1 Name",
                "field_type": "a"
            },
            "constituent_1_molar_fraction": {
                "field_name": "Constituent 1 Molar Fraction",
                "field_type": "n"
            },
            "constituent_2_name": {
                "field_name": "Constituent 2 Name",
                "field_type": "a"
            },
            "constituent_2_molar_fraction": {
                "field_name": "Constituent 2 Molar Fraction",
                "field_type": "n"
            },
            "constituent_3_name": {
                "field_name": "Constituent 3 Name",
                "field_type": "a"
            },
            "constituent_3_molar_fraction": {
                "field_name": "Constituent 3 Molar Fraction",
                "field_type": "n"
            },
            "constituent_4_name": {
                "field_name": "Constituent 4 Name",
                "field_type": "a"
            },
            "constituent_4_molar_fraction": {
                "field_name": "Constituent 4 Molar Fraction",
                "field_type": "n"
            },
            "constituent_5_name": {
                "field_name": "Constituent 5 Name",
                "field_type": "a"
            },
            "constituent_5_molar_fraction": {
                "field_name": "Constituent 5 Molar Fraction",
                "field_type": "n"
            },
            "constituent_6_name": {
                "field_name": "Constituent 6 Name",
                "field_type": "a"
            },
            "constituent_6_molar_fraction": {
                "field_name": "Constituent 6 Molar Fraction",
                "field_type": "n"
            },
            "constituent_7_name": {
                "field_name": "Constituent 7 Name",
                "field_type": "a"
            },
            "constituent_7_molar_fraction": {
                "field_name": "Constituent 7 Molar Fraction",
                "field_type": "n"
            },
            "constituent_8_name": {
                "field_name": "Constituent 8 Name",
                "field_type": "a"
            },
            "constituent_8_molar_fraction": {
                "field_name": "Constituent 8 Molar Fraction",
                "field_type": "n"
            },
            "constituent_9_name": {
                "field_name": "Constituent 9 Name",
                "field_type": "a"
            },
            "constituent_9_molar_fraction": {
                "field_name": "Constituent 9 Molar Fraction",
                "field_type": "n"
            },
            "constituent_10_name": {
                "field_name": "Constituent 10 Name",
                "field_type": "a"
            },
            "constituent_10_molar_fraction": {
                "field_name": "Constituent 10 Molar Fraction",
                "field_type": "n"
            },
            "constituent_11_name": {
                "field_name": "Constituent 11 Name",
                "field_type": "a"
            },
            "constituent_11_molar_fraction": {
                "field_name": "Constituent 11 Molar Fraction",
                "field_type": "n"
            },
            "constituent_12_name": {
                "field_name": "Constituent 12 Name",
                "field_type": "a"
            },
            "constituent_12_molar_fraction": {
                "field_name": "Constituent 12 Molar Fraction",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "fuel_temperature_modeling_mode",
            "fuel_temperature_reference_node_name",
            "fuel_temperature_schedule_name",
            "compressor_power_multiplier_function_of_fuel_rate_curve_name",
            "compressor_heat_loss_factor",
            "fuel_type",
            "liquid_generic_fuel_lower_heating_value",
            "liquid_generic_fuel_higher_heating_value",
            "liquid_generic_fuel_molecular_weight",
            "liquid_generic_fuel_co2_emission_factor",
            "number_of_constituents_in_gaseous_constituent_fuel_supply",
            "constituent_1_name",
            "constituent_1_molar_fraction",
            "constituent_2_name",
            "constituent_2_molar_fraction",
            "constituent_3_name",
            "constituent_3_molar_fraction",
            "constituent_4_name",
            "constituent_4_molar_fraction",
            "constituent_5_name",
            "constituent_5_molar_fraction",
            "constituent_6_name",
            "constituent_6_molar_fraction",
            "constituent_7_name",
            "constituent_7_molar_fraction",
            "constituent_8_name",
            "constituent_8_molar_fraction",
            "constituent_9_name",
            "constituent_9_molar_fraction",
            "constituent_10_name",
            "constituent_10_molar_fraction",
            "constituent_11_name",
            "constituent_11_molar_fraction",
            "constituent_12_name",
            "constituent_12_molar_fraction"
        ],
        "alphas": {
            "fields": [
                "name",
                "fuel_temperature_modeling_mode",
                "fuel_temperature_reference_node_name",
                "fuel_temperature_schedule_name",
                "compressor_power_multiplier_function_of_fuel_rate_curve_name",
                "fuel_type",
                "constituent_1_name",
                "constituent_2_name",
                "constituent_3_name",
                "constituent_4_name",
                "constituent_5_name",
                "constituent_6_name",
                "constituent_7_name",
                "constituent_8_name",
                "constituent_9_name",
                "constituent_10_name",
                "constituent_11_name",
                "constituent_12_name"
            ]
        },
        "numerics": {
            "fields": [
                "compressor_heat_loss_factor",
                "liquid_generic_fuel_lower_heating_value",
                "liquid_generic_fuel_higher_heating_value",
                "liquid_generic_fuel_molecular_weight",
                "liquid_generic_fuel_co2_emission_factor",
                "number_of_constituents_in_gaseous_constituent_fuel_supply",
                "constituent_1_molar_fraction",
                "constituent_2_molar_fraction",
                "constituent_3_molar_fraction",
                "constituent_4_molar_fraction",
                "constituent_5_molar_fraction",
                "constituent_6_molar_fraction",
                "constituent_7_molar_fraction",
                "constituent_8_molar_fraction",
                "constituent_9_molar_fraction",
                "constituent_10_molar_fraction",
                "constituent_11_molar_fraction",
                "constituent_12_molar_fraction"
            ]
        }
    },
    "type": "object",
    "memo": "Used only with Generator:FuelCell and Generator:MicroCHP"
}
```
