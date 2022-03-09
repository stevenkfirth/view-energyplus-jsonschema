```
{
    "CoolingTowerPerformance:CoolTools": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "minimum_inlet_air_wet_bulb_temperature": {
                        "type": "number",
                        "units": "C",
                        "note": "Minimum valid inlet air wet-bulb temperature for this approach temperature correlation."
                    },
                    "maximum_inlet_air_wet_bulb_temperature": {
                        "type": "number",
                        "units": "C",
                        "note": "Maximum valid inlet air wet-bulb temperature for this approach temperature correlation."
                    },
                    "minimum_range_temperature": {
                        "type": "number",
                        "units": "deltaC",
                        "note": "Minimum valid range temperature for this approach temperature correlation."
                    },
                    "maximum_range_temperature": {
                        "type": "number",
                        "units": "deltaC",
                        "note": "Maximum valid range temperature for this approach temperature correlation."
                    },
                    "minimum_approach_temperature": {
                        "type": "number",
                        "units": "deltaC",
                        "note": "Minimum valid approach temperature for this correlation."
                    },
                    "maximum_approach_temperature": {
                        "type": "number",
                        "units": "deltaC",
                        "note": "Maximum valid approach temperature for this correlation."
                    },
                    "minimum_water_flow_rate_ratio": {
                        "type": "number",
                        "note": "Minimum valid water flow rate ratio for this approach temperature correlation."
                    },
                    "maximum_water_flow_rate_ratio": {
                        "type": "number",
                        "note": "Maximum valid water flow rate ratio for this approach temperature correlation."
                    },
                    "coefficient_1": {
                        "type": "number"
                    },
                    "coefficient_2": {
                        "type": "number"
                    },
                    "coefficient_3": {
                        "type": "number"
                    },
                    "coefficient_4": {
                        "type": "number"
                    },
                    "coefficient_5": {
                        "type": "number"
                    },
                    "coefficient_6": {
                        "type": "number"
                    },
                    "coefficient_7": {
                        "type": "number"
                    },
                    "coefficient_8": {
                        "type": "number"
                    },
                    "coefficient_9": {
                        "type": "number"
                    },
                    "coefficient_10": {
                        "type": "number"
                    },
                    "coefficient_11": {
                        "type": "number"
                    },
                    "coefficient_12": {
                        "type": "number"
                    },
                    "coefficient_13": {
                        "type": "number"
                    },
                    "coefficient_14": {
                        "type": "number"
                    },
                    "coefficient_15": {
                        "type": "number"
                    },
                    "coefficient_16": {
                        "type": "number"
                    },
                    "coefficient_17": {
                        "type": "number"
                    },
                    "coefficient_18": {
                        "type": "number"
                    },
                    "coefficient_19": {
                        "type": "number"
                    },
                    "coefficient_20": {
                        "type": "number"
                    },
                    "coefficient_21": {
                        "type": "number"
                    },
                    "coefficient_22": {
                        "type": "number"
                    },
                    "coefficient_23": {
                        "type": "number"
                    },
                    "coefficient_24": {
                        "type": "number"
                    },
                    "coefficient_25": {
                        "type": "number"
                    },
                    "coefficient_26": {
                        "type": "number"
                    },
                    "coefficient_27": {
                        "type": "number"
                    },
                    "coefficient_28": {
                        "type": "number"
                    },
                    "coefficient_29": {
                        "type": "number"
                    },
                    "coefficient_30": {
                        "type": "number"
                    },
                    "coefficient_31": {
                        "type": "number"
                    },
                    "coefficient_32": {
                        "type": "number"
                    },
                    "coefficient_33": {
                        "type": "number"
                    },
                    "coefficient_34": {
                        "type": "number"
                    },
                    "coefficient_35": {
                        "type": "number"
                    }
                },
                "required": [
                    "minimum_inlet_air_wet_bulb_temperature",
                    "maximum_inlet_air_wet_bulb_temperature",
                    "minimum_range_temperature",
                    "maximum_range_temperature",
                    "minimum_approach_temperature",
                    "maximum_approach_temperature",
                    "minimum_water_flow_rate_ratio",
                    "maximum_water_flow_rate_ratio",
                    "coefficient_1",
                    "coefficient_2",
                    "coefficient_3",
                    "coefficient_4",
                    "coefficient_5",
                    "coefficient_6",
                    "coefficient_7",
                    "coefficient_8",
                    "coefficient_9",
                    "coefficient_10",
                    "coefficient_11",
                    "coefficient_12",
                    "coefficient_13",
                    "coefficient_14",
                    "coefficient_15",
                    "coefficient_16",
                    "coefficient_17",
                    "coefficient_18",
                    "coefficient_19",
                    "coefficient_20",
                    "coefficient_21",
                    "coefficient_22",
                    "coefficient_23",
                    "coefficient_24",
                    "coefficient_25",
                    "coefficient_26",
                    "coefficient_27",
                    "coefficient_28",
                    "coefficient_29",
                    "coefficient_30",
                    "coefficient_31",
                    "coefficient_32",
                    "coefficient_33",
                    "coefficient_34",
                    "coefficient_35"
                ]
            }
        },
        "group": "Condenser Equipment and Heat Exchangers",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "VariableSpeedTowerCoefficient"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "minimum_inlet_air_wet_bulb_temperature": {
                    "field_name": "Minimum Inlet Air Wet-Bulb Temperature",
                    "field_type": "n"
                },
                "maximum_inlet_air_wet_bulb_temperature": {
                    "field_name": "Maximum Inlet Air Wet-Bulb Temperature",
                    "field_type": "n"
                },
                "minimum_range_temperature": {
                    "field_name": "Minimum Range Temperature",
                    "field_type": "n"
                },
                "maximum_range_temperature": {
                    "field_name": "Maximum Range Temperature",
                    "field_type": "n"
                },
                "minimum_approach_temperature": {
                    "field_name": "Minimum Approach Temperature",
                    "field_type": "n"
                },
                "maximum_approach_temperature": {
                    "field_name": "Maximum Approach Temperature",
                    "field_type": "n"
                },
                "minimum_water_flow_rate_ratio": {
                    "field_name": "Minimum Water Flow Rate Ratio",
                    "field_type": "n"
                },
                "maximum_water_flow_rate_ratio": {
                    "field_name": "Maximum Water Flow Rate Ratio",
                    "field_type": "n"
                },
                "coefficient_1": {
                    "field_name": "Coefficient 1",
                    "field_type": "n"
                },
                "coefficient_2": {
                    "field_name": "Coefficient 2",
                    "field_type": "n"
                },
                "coefficient_3": {
                    "field_name": "Coefficient 3",
                    "field_type": "n"
                },
                "coefficient_4": {
                    "field_name": "Coefficient 4",
                    "field_type": "n"
                },
                "coefficient_5": {
                    "field_name": "Coefficient 5",
                    "field_type": "n"
                },
                "coefficient_6": {
                    "field_name": "Coefficient 6",
                    "field_type": "n"
                },
                "coefficient_7": {
                    "field_name": "Coefficient 7",
                    "field_type": "n"
                },
                "coefficient_8": {
                    "field_name": "Coefficient 8",
                    "field_type": "n"
                },
                "coefficient_9": {
                    "field_name": "Coefficient 9",
                    "field_type": "n"
                },
                "coefficient_10": {
                    "field_name": "Coefficient 10",
                    "field_type": "n"
                },
                "coefficient_11": {
                    "field_name": "Coefficient 11",
                    "field_type": "n"
                },
                "coefficient_12": {
                    "field_name": "Coefficient 12",
                    "field_type": "n"
                },
                "coefficient_13": {
                    "field_name": "Coefficient 13",
                    "field_type": "n"
                },
                "coefficient_14": {
                    "field_name": "Coefficient 14",
                    "field_type": "n"
                },
                "coefficient_15": {
                    "field_name": "Coefficient 15",
                    "field_type": "n"
                },
                "coefficient_16": {
                    "field_name": "Coefficient 16",
                    "field_type": "n"
                },
                "coefficient_17": {
                    "field_name": "Coefficient 17",
                    "field_type": "n"
                },
                "coefficient_18": {
                    "field_name": "Coefficient 18",
                    "field_type": "n"
                },
                "coefficient_19": {
                    "field_name": "Coefficient 19",
                    "field_type": "n"
                },
                "coefficient_20": {
                    "field_name": "Coefficient 20",
                    "field_type": "n"
                },
                "coefficient_21": {
                    "field_name": "Coefficient 21",
                    "field_type": "n"
                },
                "coefficient_22": {
                    "field_name": "Coefficient 22",
                    "field_type": "n"
                },
                "coefficient_23": {
                    "field_name": "Coefficient 23",
                    "field_type": "n"
                },
                "coefficient_24": {
                    "field_name": "Coefficient 24",
                    "field_type": "n"
                },
                "coefficient_25": {
                    "field_name": "Coefficient 25",
                    "field_type": "n"
                },
                "coefficient_26": {
                    "field_name": "Coefficient 26",
                    "field_type": "n"
                },
                "coefficient_27": {
                    "field_name": "Coefficient 27",
                    "field_type": "n"
                },
                "coefficient_28": {
                    "field_name": "Coefficient 28",
                    "field_type": "n"
                },
                "coefficient_29": {
                    "field_name": "Coefficient 29",
                    "field_type": "n"
                },
                "coefficient_30": {
                    "field_name": "Coefficient 30",
                    "field_type": "n"
                },
                "coefficient_31": {
                    "field_name": "Coefficient 31",
                    "field_type": "n"
                },
                "coefficient_32": {
                    "field_name": "Coefficient 32",
                    "field_type": "n"
                },
                "coefficient_33": {
                    "field_name": "Coefficient 33",
                    "field_type": "n"
                },
                "coefficient_34": {
                    "field_name": "Coefficient 34",
                    "field_type": "n"
                },
                "coefficient_35": {
                    "field_name": "Coefficient 35",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "minimum_inlet_air_wet_bulb_temperature",
                "maximum_inlet_air_wet_bulb_temperature",
                "minimum_range_temperature",
                "maximum_range_temperature",
                "minimum_approach_temperature",
                "maximum_approach_temperature",
                "minimum_water_flow_rate_ratio",
                "maximum_water_flow_rate_ratio",
                "coefficient_1",
                "coefficient_2",
                "coefficient_3",
                "coefficient_4",
                "coefficient_5",
                "coefficient_6",
                "coefficient_7",
                "coefficient_8",
                "coefficient_9",
                "coefficient_10",
                "coefficient_11",
                "coefficient_12",
                "coefficient_13",
                "coefficient_14",
                "coefficient_15",
                "coefficient_16",
                "coefficient_17",
                "coefficient_18",
                "coefficient_19",
                "coefficient_20",
                "coefficient_21",
                "coefficient_22",
                "coefficient_23",
                "coefficient_24",
                "coefficient_25",
                "coefficient_26",
                "coefficient_27",
                "coefficient_28",
                "coefficient_29",
                "coefficient_30",
                "coefficient_31",
                "coefficient_32",
                "coefficient_33",
                "coefficient_34",
                "coefficient_35"
            ],
            "alphas": {
                "fields": [
                    "name"
                ]
            },
            "numerics": {
                "fields": [
                    "minimum_inlet_air_wet_bulb_temperature",
                    "maximum_inlet_air_wet_bulb_temperature",
                    "minimum_range_temperature",
                    "maximum_range_temperature",
                    "minimum_approach_temperature",
                    "maximum_approach_temperature",
                    "minimum_water_flow_rate_ratio",
                    "maximum_water_flow_rate_ratio",
                    "coefficient_1",
                    "coefficient_2",
                    "coefficient_3",
                    "coefficient_4",
                    "coefficient_5",
                    "coefficient_6",
                    "coefficient_7",
                    "coefficient_8",
                    "coefficient_9",
                    "coefficient_10",
                    "coefficient_11",
                    "coefficient_12",
                    "coefficient_13",
                    "coefficient_14",
                    "coefficient_15",
                    "coefficient_16",
                    "coefficient_17",
                    "coefficient_18",
                    "coefficient_19",
                    "coefficient_20",
                    "coefficient_21",
                    "coefficient_22",
                    "coefficient_23",
                    "coefficient_24",
                    "coefficient_25",
                    "coefficient_26",
                    "coefficient_27",
                    "coefficient_28",
                    "coefficient_29",
                    "coefficient_30",
                    "coefficient_31",
                    "coefficient_32",
                    "coefficient_33",
                    "coefficient_34",
                    "coefficient_35"
                ]
            }
        },
        "type": "object",
        "memo": "This object is used to define coefficients for the approach temperature correlation for a variable speed cooling tower when tower Model Type is specified as CoolToolsUserDefined in the object CoolingTower:VariableSpeed.",
        "min_fields": 44.0
    }
}
```
