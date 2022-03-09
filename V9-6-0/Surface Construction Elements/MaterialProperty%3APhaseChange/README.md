```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "temperature_coefficient_for_thermal_conductivity": {
                    "type": "number",
                    "note": "The base temperature is 20C. This is the thermal conductivity change per degree excursion from 20C. This variable conductivity function is overridden by the VariableThermalConductivity object, if present.",
                    "units": "W/m-K2",
                    "default": 0.0
                },
                "temperature_1": {
                    "type": "number",
                    "note": "for Temperature-enthalpy function",
                    "units": "C"
                },
                "enthalpy_1": {
                    "type": "number",
                    "note": "for Temperature-enthalpy function corresponding to temperature 1",
                    "units": "J/kg"
                },
                "temperature_2": {
                    "type": "number",
                    "note": "for Temperature-enthalpy function",
                    "units": "C"
                },
                "enthalpy_2": {
                    "type": "number",
                    "note": "for Temperature-enthalpy function corresponding to temperature 2",
                    "units": "J/kg"
                },
                "temperature_3": {
                    "type": "number",
                    "note": "for Temperature-enthalpy function",
                    "units": "C"
                },
                "enthalpy_3": {
                    "type": "number",
                    "note": "for Temperature-enthalpy function corresponding to temperature 3",
                    "units": "J/kg"
                },
                "temperature_4": {
                    "type": "number",
                    "note": "for Temperature-enthalpy function",
                    "units": "C"
                },
                "enthalpy_4": {
                    "type": "number",
                    "note": "for Temperature-enthalpy function corresponding to temperature 4",
                    "units": "J/kg"
                },
                "temperature_5": {
                    "type": "number",
                    "note": "for Temperature-enthalpy function",
                    "units": "C"
                },
                "enthalpy_5": {
                    "type": "number",
                    "note": "for Temperature-enthalpy function corresponding to temperature 5",
                    "units": "J/kg"
                },
                "temperature_6": {
                    "type": "number",
                    "note": "for Temperature-enthalpy function",
                    "units": "C"
                },
                "enthalpy_6": {
                    "type": "number",
                    "note": "for Temperature-enthalpy function corresponding to temperature 6",
                    "units": "J/kg"
                },
                "temperature_7": {
                    "type": "number",
                    "note": "for Temperature-enthalpy function",
                    "units": "C"
                },
                "enthalpy_7": {
                    "type": "number",
                    "note": "for Temperature-enthalpy function corresponding to temperature 7",
                    "units": "J/kg"
                },
                "temperature_8": {
                    "type": "number",
                    "note": "for Temperature-enthalpy function",
                    "units": "C"
                },
                "enthalpy_8": {
                    "type": "number",
                    "note": "for Temperature-enthalpy function corresponding to temperature 8",
                    "units": "J/kg"
                },
                "temperature_9": {
                    "type": "number",
                    "note": "for Temperature-enthalpy function",
                    "units": "C"
                },
                "enthalpy_9": {
                    "type": "number",
                    "note": "for Temperature-enthalpy function corresponding to temperature 1",
                    "units": "J/kg"
                },
                "temperature_10": {
                    "type": "number",
                    "note": "for Temperature-enthalpy function",
                    "units": "C"
                },
                "enthalpy_10": {
                    "type": "number",
                    "note": "for Temperature-enthalpy function corresponding to temperature 2",
                    "units": "J/kg"
                },
                "temperature_11": {
                    "type": "number",
                    "note": "for Temperature-enthalpy function",
                    "units": "C"
                },
                "enthalpy_11": {
                    "type": "number",
                    "note": "for Temperature-enthalpy function corresponding to temperature 3",
                    "units": "J/kg"
                },
                "temperature_12": {
                    "type": "number",
                    "note": "for Temperature-enthalpy function",
                    "units": "C"
                },
                "enthalpy_12": {
                    "type": "number",
                    "note": "for Temperature-enthalpy function corresponding to temperature 14",
                    "units": "J/kg"
                },
                "temperature_13": {
                    "type": "number",
                    "note": "for Temperature-enthalpy function",
                    "units": "C"
                },
                "enthalpy_13": {
                    "type": "number",
                    "note": "for Temperature-enthalpy function corresponding to temperature 15",
                    "units": "J/kg"
                },
                "temperature_14": {
                    "type": "number",
                    "note": "for Temperature-enthalpy function",
                    "units": "C"
                },
                "enthalpy_14": {
                    "type": "number",
                    "note": "for Temperature-enthalpy function corresponding to temperature 16",
                    "units": "J/kg"
                },
                "temperature_15": {
                    "type": "number",
                    "note": "for Temperature-enthalpy function",
                    "units": "C"
                },
                "enthalpy_15": {
                    "type": "number",
                    "note": "for Temperature-enthalpy function corresponding to temperature 17",
                    "units": "J/kg"
                },
                "temperature_16": {
                    "type": "number",
                    "note": "for Temperature-enthalpy function",
                    "units": "C"
                },
                "enthalpy_16": {
                    "type": "number",
                    "note": "for Temperature-enthalpy function corresponding to temperature 16",
                    "units": "J/kg"
                }
            },
            "required": [
                "temperature_1",
                "enthalpy_1",
                "temperature_2",
                "enthalpy_2",
                "temperature_3",
                "enthalpy_3"
            ]
        }
    },
    "group": "Surface Construction Elements",
    "name": {
        "type": "string",
        "is_required": true,
        "data_type": "object_list",
        "object_list": [
            "MaterialName"
        ],
        "note": "Regular Material Name to which the additional properties will be added. this the material name for the basic material properties."
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "temperature_coefficient_for_thermal_conductivity": {
                "field_name": "Temperature Coefficient for Thermal Conductivity",
                "field_type": "n"
            },
            "temperature_1": {
                "field_name": "Temperature 1",
                "field_type": "n"
            },
            "enthalpy_1": {
                "field_name": "Enthalpy 1",
                "field_type": "n"
            },
            "temperature_2": {
                "field_name": "Temperature 2",
                "field_type": "n"
            },
            "enthalpy_2": {
                "field_name": "Enthalpy 2",
                "field_type": "n"
            },
            "temperature_3": {
                "field_name": "Temperature 3",
                "field_type": "n"
            },
            "enthalpy_3": {
                "field_name": "Enthalpy 3",
                "field_type": "n"
            },
            "temperature_4": {
                "field_name": "Temperature 4",
                "field_type": "n"
            },
            "enthalpy_4": {
                "field_name": "Enthalpy 4",
                "field_type": "n"
            },
            "temperature_5": {
                "field_name": "Temperature 5",
                "field_type": "n"
            },
            "enthalpy_5": {
                "field_name": "Enthalpy 5",
                "field_type": "n"
            },
            "temperature_6": {
                "field_name": "Temperature 6",
                "field_type": "n"
            },
            "enthalpy_6": {
                "field_name": "Enthalpy 6",
                "field_type": "n"
            },
            "temperature_7": {
                "field_name": "Temperature 7",
                "field_type": "n"
            },
            "enthalpy_7": {
                "field_name": "Enthalpy 7",
                "field_type": "n"
            },
            "temperature_8": {
                "field_name": "Temperature 8",
                "field_type": "n"
            },
            "enthalpy_8": {
                "field_name": "Enthalpy 8",
                "field_type": "n"
            },
            "temperature_9": {
                "field_name": "Temperature 9",
                "field_type": "n"
            },
            "enthalpy_9": {
                "field_name": "Enthalpy 9",
                "field_type": "n"
            },
            "temperature_10": {
                "field_name": "Temperature 10",
                "field_type": "n"
            },
            "enthalpy_10": {
                "field_name": "Enthalpy 10",
                "field_type": "n"
            },
            "temperature_11": {
                "field_name": "Temperature 11",
                "field_type": "n"
            },
            "enthalpy_11": {
                "field_name": "Enthalpy 11",
                "field_type": "n"
            },
            "temperature_12": {
                "field_name": "Temperature 12",
                "field_type": "n"
            },
            "enthalpy_12": {
                "field_name": "Enthalpy 12",
                "field_type": "n"
            },
            "temperature_13": {
                "field_name": "Temperature 13",
                "field_type": "n"
            },
            "enthalpy_13": {
                "field_name": "Enthalpy 13",
                "field_type": "n"
            },
            "temperature_14": {
                "field_name": "Temperature 14",
                "field_type": "n"
            },
            "enthalpy_14": {
                "field_name": "Enthalpy 14",
                "field_type": "n"
            },
            "temperature_15": {
                "field_name": "Temperature 15",
                "field_type": "n"
            },
            "enthalpy_15": {
                "field_name": "Enthalpy 15",
                "field_type": "n"
            },
            "temperature_16": {
                "field_name": "Temperature 16",
                "field_type": "n"
            },
            "enthalpy_16": {
                "field_name": "Enthalpy 16",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "temperature_coefficient_for_thermal_conductivity",
            "temperature_1",
            "enthalpy_1",
            "temperature_2",
            "enthalpy_2",
            "temperature_3",
            "enthalpy_3",
            "temperature_4",
            "enthalpy_4",
            "temperature_5",
            "enthalpy_5",
            "temperature_6",
            "enthalpy_6",
            "temperature_7",
            "enthalpy_7",
            "temperature_8",
            "enthalpy_8",
            "temperature_9",
            "enthalpy_9",
            "temperature_10",
            "enthalpy_10",
            "temperature_11",
            "enthalpy_11",
            "temperature_12",
            "enthalpy_12",
            "temperature_13",
            "enthalpy_13",
            "temperature_14",
            "enthalpy_14",
            "temperature_15",
            "enthalpy_15",
            "temperature_16",
            "enthalpy_16"
        ],
        "alphas": {
            "fields": [
                "name"
            ]
        },
        "numerics": {
            "fields": [
                "temperature_coefficient_for_thermal_conductivity",
                "temperature_1",
                "enthalpy_1",
                "temperature_2",
                "enthalpy_2",
                "temperature_3",
                "enthalpy_3",
                "temperature_4",
                "enthalpy_4",
                "temperature_5",
                "enthalpy_5",
                "temperature_6",
                "enthalpy_6",
                "temperature_7",
                "enthalpy_7",
                "temperature_8",
                "enthalpy_8",
                "temperature_9",
                "enthalpy_9",
                "temperature_10",
                "enthalpy_10",
                "temperature_11",
                "enthalpy_11",
                "temperature_12",
                "enthalpy_12",
                "temperature_13",
                "enthalpy_13",
                "temperature_14",
                "enthalpy_14",
                "temperature_15",
                "enthalpy_15",
                "temperature_16",
                "enthalpy_16"
            ]
        }
    },
    "type": "object",
    "memo": "Additional properties for temperature dependent thermal conductivity and enthalpy for Phase Change Materials (PCM) HeatBalanceAlgorithm = CondFD(ConductionFiniteDifference) solution algorithm only. Constructions with this should use the detailed CondFD process. Has no effect with other HeatBalanceAlgorithm solution algorithms"
}
```
