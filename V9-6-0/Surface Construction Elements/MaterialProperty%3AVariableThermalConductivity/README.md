```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "temperature_1": {
                    "type": "number",
                    "note": "for Temperature-Thermal Conductivity function",
                    "units": "C"
                },
                "thermal_conductivity_1": {
                    "type": "number",
                    "note": "for Temperature-Thermal Conductivity function corresponding to temperature 1",
                    "units": "W/m-K"
                },
                "temperature_2": {
                    "type": "number",
                    "note": "for Temperature-Thermal Conductivity function",
                    "units": "C"
                },
                "thermal_conductivity_2": {
                    "type": "number",
                    "note": "for Temperature-Thermal Conductivity function corresponding to temperature 2",
                    "units": "W/m-K"
                },
                "temperature_3": {
                    "type": "number",
                    "note": "for Temperature-Thermal Conductivity function",
                    "units": "C"
                },
                "thermal_conductivity_3": {
                    "type": "number",
                    "note": "for Temperature-Thermal Conductivity function corresponding to temperature 3",
                    "units": "W/m-K"
                },
                "temperature_4": {
                    "type": "number",
                    "note": "for Temperature-Thermal Conductivity function",
                    "units": "C"
                },
                "thermal_conductivity_4": {
                    "type": "number",
                    "note": "for Temperature-Thermal Conductivity function corresponding to temperature 4",
                    "units": "W/m-K"
                },
                "temperature_5": {
                    "type": "number",
                    "note": "for Temperature-Thermal Conductivity function",
                    "units": "C"
                },
                "thermal_conductivity_5": {
                    "type": "number",
                    "note": "for Temperature-Thermal Conductivity function corresponding to temperature 5",
                    "units": "W/m-K"
                },
                "temperature_6": {
                    "type": "number",
                    "note": "for Temperature-Thermal Conductivity function",
                    "units": "C"
                },
                "thermal_conductivity_6": {
                    "type": "number",
                    "note": "for Temperature-Thermal Conductivity function corresponding to temperature 6",
                    "units": "W/m-K"
                },
                "temperature_7": {
                    "type": "number",
                    "note": "for Temperature-Thermal Conductivity function",
                    "units": "C"
                },
                "thermal_conductivity_7": {
                    "type": "number",
                    "note": "for Temperature-Thermal Conductivity function corresponding to temperature 7",
                    "units": "W/m-K"
                },
                "temperature_8": {
                    "type": "number",
                    "note": "for Temperature-Thermal Conductivity function",
                    "units": "C"
                },
                "thermal_conductivity_8": {
                    "type": "number",
                    "note": "for Temperature-Thermal Conductivity function corresponding to temperature 8",
                    "units": "W/m-K"
                },
                "temperature_9": {
                    "type": "number",
                    "note": "for Temperature-Thermal Conductivity function",
                    "units": "C"
                },
                "thermal_conductivity_9": {
                    "type": "number",
                    "note": "for Temperature-Thermal Conductivity function corresponding to temperature 9",
                    "units": "W/m-K"
                },
                "temperature_10": {
                    "type": "number",
                    "note": "for Temperature-Thermal Conductivity function",
                    "units": "C"
                },
                "thermal_conductivity_10": {
                    "type": "number",
                    "note": "for Temperature-Thermal Conductivity function corresponding to temperature 10",
                    "units": "W/m-K"
                }
            },
            "required": [
                "temperature_1",
                "thermal_conductivity_1",
                "temperature_2",
                "thermal_conductivity_2",
                "temperature_3",
                "thermal_conductivity_3"
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
            "temperature_1": {
                "field_name": "Temperature 1",
                "field_type": "n"
            },
            "thermal_conductivity_1": {
                "field_name": "Thermal Conductivity 1",
                "field_type": "n"
            },
            "temperature_2": {
                "field_name": "Temperature 2",
                "field_type": "n"
            },
            "thermal_conductivity_2": {
                "field_name": "Thermal Conductivity 2",
                "field_type": "n"
            },
            "temperature_3": {
                "field_name": "Temperature 3",
                "field_type": "n"
            },
            "thermal_conductivity_3": {
                "field_name": "Thermal Conductivity 3",
                "field_type": "n"
            },
            "temperature_4": {
                "field_name": "Temperature 4",
                "field_type": "n"
            },
            "thermal_conductivity_4": {
                "field_name": "Thermal Conductivity 4",
                "field_type": "n"
            },
            "temperature_5": {
                "field_name": "Temperature 5",
                "field_type": "n"
            },
            "thermal_conductivity_5": {
                "field_name": "Thermal Conductivity 5",
                "field_type": "n"
            },
            "temperature_6": {
                "field_name": "Temperature 6",
                "field_type": "n"
            },
            "thermal_conductivity_6": {
                "field_name": "Thermal Conductivity 6",
                "field_type": "n"
            },
            "temperature_7": {
                "field_name": "Temperature 7",
                "field_type": "n"
            },
            "thermal_conductivity_7": {
                "field_name": "Thermal Conductivity 7",
                "field_type": "n"
            },
            "temperature_8": {
                "field_name": "Temperature 8",
                "field_type": "n"
            },
            "thermal_conductivity_8": {
                "field_name": "Thermal Conductivity 8",
                "field_type": "n"
            },
            "temperature_9": {
                "field_name": "Temperature 9",
                "field_type": "n"
            },
            "thermal_conductivity_9": {
                "field_name": "Thermal Conductivity 9",
                "field_type": "n"
            },
            "temperature_10": {
                "field_name": "Temperature 10",
                "field_type": "n"
            },
            "thermal_conductivity_10": {
                "field_name": "Thermal Conductivity 10",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "temperature_1",
            "thermal_conductivity_1",
            "temperature_2",
            "thermal_conductivity_2",
            "temperature_3",
            "thermal_conductivity_3",
            "temperature_4",
            "thermal_conductivity_4",
            "temperature_5",
            "thermal_conductivity_5",
            "temperature_6",
            "thermal_conductivity_6",
            "temperature_7",
            "thermal_conductivity_7",
            "temperature_8",
            "thermal_conductivity_8",
            "temperature_9",
            "thermal_conductivity_9",
            "temperature_10",
            "thermal_conductivity_10"
        ],
        "alphas": {
            "fields": [
                "name"
            ]
        },
        "numerics": {
            "fields": [
                "temperature_1",
                "thermal_conductivity_1",
                "temperature_2",
                "thermal_conductivity_2",
                "temperature_3",
                "thermal_conductivity_3",
                "temperature_4",
                "thermal_conductivity_4",
                "temperature_5",
                "thermal_conductivity_5",
                "temperature_6",
                "thermal_conductivity_6",
                "temperature_7",
                "thermal_conductivity_7",
                "temperature_8",
                "thermal_conductivity_8",
                "temperature_9",
                "thermal_conductivity_9",
                "temperature_10",
                "thermal_conductivity_10"
            ]
        }
    },
    "type": "object",
    "memo": "Additional properties for temperature dependent thermal conductivity using piecewise linear temperature-conductivity function. HeatBalanceAlgorithm = CondFD(ConductionFiniteDifference) solution algorithm only. Has no effect with other HeatBalanceAlgorithm solution algorithms"
}
```
