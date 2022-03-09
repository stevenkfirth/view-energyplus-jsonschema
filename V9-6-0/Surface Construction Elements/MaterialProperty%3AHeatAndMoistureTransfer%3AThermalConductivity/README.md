```
{
    "MaterialProperty:HeatAndMoistureTransfer:ThermalConductivity": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "material_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "MaterialName"
                        ],
                        "note": "Moisture Material Name that the Thermal Conductivity will be added to."
                    },
                    "number_of_thermal_coordinates": {
                        "type": "number",
                        "note": "number of data coordinates",
                        "minimum": 1.0,
                        "maximum": 25.0
                    },
                    "moisture_content_1": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "thermal_conductivity_1": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "W/m-K"
                    },
                    "moisture_content_2": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "thermal_conductivity_2": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "W/m-K"
                    },
                    "moisture_content_3": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "thermal_conductivity_3": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "W/m-K"
                    },
                    "moisture_content_4": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "thermal_conductivity_4": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "W/m-K"
                    },
                    "moisture_content_5": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "thermal_conductivity_5": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "W/m-K"
                    },
                    "moisture_content_6": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "thermal_conductivity_6": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "W/m-K"
                    },
                    "moisture_content_7": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "thermal_conductivity_7": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "W/m-K"
                    },
                    "moisture_content_8": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "thermal_conductivity_8": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "W/m-K"
                    },
                    "moisture_content_9": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "thermal_conductivity_9": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "W/m-K"
                    },
                    "moisture_content_10": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "thermal_conductivity_10": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "W/m-K"
                    },
                    "moisture_content_11": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "thermal_conductivity_11": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "W/m-K"
                    },
                    "moisture_content_12": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "thermal_conductivity_12": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "W/m-K"
                    },
                    "moisture_content_13": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "thermal_conductivity_13": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "W/m-K"
                    },
                    "moisture_content_14": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "thermal_conductivity_14": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "W/m-K"
                    },
                    "moisture_content_15": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "thermal_conductivity_15": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "W/m-K"
                    },
                    "moisture_content_16": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "thermal_conductivity_16": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "W/m-K"
                    },
                    "moisture_content_17": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "thermal_conductivity_17": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "W/m-K"
                    },
                    "moisture_content_18": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "thermal_conductivity_18": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "W/m-K"
                    },
                    "moisture_content_19": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "thermal_conductivity_19": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "W/m-K"
                    },
                    "moisture_content_20": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "thermal_conductivity_20": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "W/m-K"
                    },
                    "moisture_content_21": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "thermal_conductivity_21": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "W/m-K"
                    },
                    "moisture_content_22": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "thermal_conductivity_22": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "W/m-K"
                    },
                    "moisture_content_23": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "thermal_conductivity_23": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "W/m-K"
                    },
                    "moisture_content_24": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "thermal_conductivity_24": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "W/m-K"
                    },
                    "moisture_content_25": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "thermal_conductivity_25": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "W/m-K"
                    }
                },
                "required": [
                    "material_name",
                    "number_of_thermal_coordinates",
                    "moisture_content_1",
                    "thermal_conductivity_1"
                ]
            }
        },
        "group": "Surface Construction Elements",
        "legacy_idd": {
            "field_info": {
                "material_name": {
                    "field_name": "Material Name",
                    "field_type": "a"
                },
                "number_of_thermal_coordinates": {
                    "field_name": "Number of Thermal Coordinates",
                    "field_type": "n"
                },
                "moisture_content_1": {
                    "field_name": "Moisture Content 1",
                    "field_type": "n"
                },
                "thermal_conductivity_1": {
                    "field_name": "Thermal Conductivity 1",
                    "field_type": "n"
                },
                "moisture_content_2": {
                    "field_name": "Moisture Content 2",
                    "field_type": "n"
                },
                "thermal_conductivity_2": {
                    "field_name": "Thermal Conductivity 2",
                    "field_type": "n"
                },
                "moisture_content_3": {
                    "field_name": "Moisture Content 3",
                    "field_type": "n"
                },
                "thermal_conductivity_3": {
                    "field_name": "Thermal Conductivity 3",
                    "field_type": "n"
                },
                "moisture_content_4": {
                    "field_name": "Moisture Content 4",
                    "field_type": "n"
                },
                "thermal_conductivity_4": {
                    "field_name": "Thermal Conductivity 4",
                    "field_type": "n"
                },
                "moisture_content_5": {
                    "field_name": "Moisture Content 5",
                    "field_type": "n"
                },
                "thermal_conductivity_5": {
                    "field_name": "Thermal Conductivity 5",
                    "field_type": "n"
                },
                "moisture_content_6": {
                    "field_name": "Moisture Content 6",
                    "field_type": "n"
                },
                "thermal_conductivity_6": {
                    "field_name": "Thermal Conductivity 6",
                    "field_type": "n"
                },
                "moisture_content_7": {
                    "field_name": "Moisture Content 7",
                    "field_type": "n"
                },
                "thermal_conductivity_7": {
                    "field_name": "Thermal Conductivity 7",
                    "field_type": "n"
                },
                "moisture_content_8": {
                    "field_name": "Moisture Content 8",
                    "field_type": "n"
                },
                "thermal_conductivity_8": {
                    "field_name": "Thermal Conductivity 8",
                    "field_type": "n"
                },
                "moisture_content_9": {
                    "field_name": "Moisture Content 9",
                    "field_type": "n"
                },
                "thermal_conductivity_9": {
                    "field_name": "Thermal Conductivity 9",
                    "field_type": "n"
                },
                "moisture_content_10": {
                    "field_name": "Moisture Content 10",
                    "field_type": "n"
                },
                "thermal_conductivity_10": {
                    "field_name": "Thermal Conductivity 10",
                    "field_type": "n"
                },
                "moisture_content_11": {
                    "field_name": "Moisture Content 11",
                    "field_type": "n"
                },
                "thermal_conductivity_11": {
                    "field_name": "Thermal Conductivity 11",
                    "field_type": "n"
                },
                "moisture_content_12": {
                    "field_name": "Moisture Content 12",
                    "field_type": "n"
                },
                "thermal_conductivity_12": {
                    "field_name": "Thermal Conductivity 12",
                    "field_type": "n"
                },
                "moisture_content_13": {
                    "field_name": "Moisture Content 13",
                    "field_type": "n"
                },
                "thermal_conductivity_13": {
                    "field_name": "Thermal Conductivity 13",
                    "field_type": "n"
                },
                "moisture_content_14": {
                    "field_name": "Moisture Content 14",
                    "field_type": "n"
                },
                "thermal_conductivity_14": {
                    "field_name": "Thermal Conductivity 14",
                    "field_type": "n"
                },
                "moisture_content_15": {
                    "field_name": "Moisture Content 15",
                    "field_type": "n"
                },
                "thermal_conductivity_15": {
                    "field_name": "Thermal Conductivity 15",
                    "field_type": "n"
                },
                "moisture_content_16": {
                    "field_name": "Moisture Content 16",
                    "field_type": "n"
                },
                "thermal_conductivity_16": {
                    "field_name": "Thermal Conductivity 16",
                    "field_type": "n"
                },
                "moisture_content_17": {
                    "field_name": "Moisture Content 17",
                    "field_type": "n"
                },
                "thermal_conductivity_17": {
                    "field_name": "Thermal Conductivity 17",
                    "field_type": "n"
                },
                "moisture_content_18": {
                    "field_name": "Moisture Content 18",
                    "field_type": "n"
                },
                "thermal_conductivity_18": {
                    "field_name": "Thermal Conductivity 18",
                    "field_type": "n"
                },
                "moisture_content_19": {
                    "field_name": "Moisture Content 19",
                    "field_type": "n"
                },
                "thermal_conductivity_19": {
                    "field_name": "Thermal Conductivity 19",
                    "field_type": "n"
                },
                "moisture_content_20": {
                    "field_name": "Moisture Content 20",
                    "field_type": "n"
                },
                "thermal_conductivity_20": {
                    "field_name": "Thermal Conductivity 20",
                    "field_type": "n"
                },
                "moisture_content_21": {
                    "field_name": "Moisture Content 21",
                    "field_type": "n"
                },
                "thermal_conductivity_21": {
                    "field_name": "Thermal Conductivity 21",
                    "field_type": "n"
                },
                "moisture_content_22": {
                    "field_name": "Moisture Content 22",
                    "field_type": "n"
                },
                "thermal_conductivity_22": {
                    "field_name": "Thermal Conductivity 22",
                    "field_type": "n"
                },
                "moisture_content_23": {
                    "field_name": "Moisture Content 23",
                    "field_type": "n"
                },
                "thermal_conductivity_23": {
                    "field_name": "Thermal Conductivity 23",
                    "field_type": "n"
                },
                "moisture_content_24": {
                    "field_name": "Moisture Content 24",
                    "field_type": "n"
                },
                "thermal_conductivity_24": {
                    "field_name": "Thermal Conductivity 24",
                    "field_type": "n"
                },
                "moisture_content_25": {
                    "field_name": "Moisture Content 25",
                    "field_type": "n"
                },
                "thermal_conductivity_25": {
                    "field_name": "Thermal Conductivity 25",
                    "field_type": "n"
                }
            },
            "fields": [
                "material_name",
                "number_of_thermal_coordinates",
                "moisture_content_1",
                "thermal_conductivity_1",
                "moisture_content_2",
                "thermal_conductivity_2",
                "moisture_content_3",
                "thermal_conductivity_3",
                "moisture_content_4",
                "thermal_conductivity_4",
                "moisture_content_5",
                "thermal_conductivity_5",
                "moisture_content_6",
                "thermal_conductivity_6",
                "moisture_content_7",
                "thermal_conductivity_7",
                "moisture_content_8",
                "thermal_conductivity_8",
                "moisture_content_9",
                "thermal_conductivity_9",
                "moisture_content_10",
                "thermal_conductivity_10",
                "moisture_content_11",
                "thermal_conductivity_11",
                "moisture_content_12",
                "thermal_conductivity_12",
                "moisture_content_13",
                "thermal_conductivity_13",
                "moisture_content_14",
                "thermal_conductivity_14",
                "moisture_content_15",
                "thermal_conductivity_15",
                "moisture_content_16",
                "thermal_conductivity_16",
                "moisture_content_17",
                "thermal_conductivity_17",
                "moisture_content_18",
                "thermal_conductivity_18",
                "moisture_content_19",
                "thermal_conductivity_19",
                "moisture_content_20",
                "thermal_conductivity_20",
                "moisture_content_21",
                "thermal_conductivity_21",
                "moisture_content_22",
                "thermal_conductivity_22",
                "moisture_content_23",
                "thermal_conductivity_23",
                "moisture_content_24",
                "thermal_conductivity_24",
                "moisture_content_25",
                "thermal_conductivity_25"
            ],
            "alphas": {
                "fields": [
                    "material_name"
                ]
            },
            "numerics": {
                "fields": [
                    "number_of_thermal_coordinates",
                    "moisture_content_1",
                    "thermal_conductivity_1",
                    "moisture_content_2",
                    "thermal_conductivity_2",
                    "moisture_content_3",
                    "thermal_conductivity_3",
                    "moisture_content_4",
                    "thermal_conductivity_4",
                    "moisture_content_5",
                    "thermal_conductivity_5",
                    "moisture_content_6",
                    "thermal_conductivity_6",
                    "moisture_content_7",
                    "thermal_conductivity_7",
                    "moisture_content_8",
                    "thermal_conductivity_8",
                    "moisture_content_9",
                    "thermal_conductivity_9",
                    "moisture_content_10",
                    "thermal_conductivity_10",
                    "moisture_content_11",
                    "thermal_conductivity_11",
                    "moisture_content_12",
                    "thermal_conductivity_12",
                    "moisture_content_13",
                    "thermal_conductivity_13",
                    "moisture_content_14",
                    "thermal_conductivity_14",
                    "moisture_content_15",
                    "thermal_conductivity_15",
                    "moisture_content_16",
                    "thermal_conductivity_16",
                    "moisture_content_17",
                    "thermal_conductivity_17",
                    "moisture_content_18",
                    "thermal_conductivity_18",
                    "moisture_content_19",
                    "thermal_conductivity_19",
                    "moisture_content_20",
                    "thermal_conductivity_20",
                    "moisture_content_21",
                    "thermal_conductivity_21",
                    "moisture_content_22",
                    "thermal_conductivity_22",
                    "moisture_content_23",
                    "thermal_conductivity_23",
                    "moisture_content_24",
                    "thermal_conductivity_24",
                    "moisture_content_25",
                    "thermal_conductivity_25"
                ]
            }
        },
        "type": "object",
        "memo": "HeatBalanceAlgorithm = CombinedHeatAndMoistureFiniteElement solution algorithm only. Relationship between thermal conductivity and moisture content Has no effect with other HeatBalanceAlgorithm solution algorithms"
    }
}
```
