```
{
    "MaterialProperty:HeatAndMoistureTransfer:Redistribution": {
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
                        "note": "Moisture Material Name that the moisture properties will be added to."
                    },
                    "number_of_redistribution_points": {
                        "type": "number",
                        "note": "number of data points",
                        "minimum": 1.0,
                        "maximum": 25.0
                    },
                    "moisture_content_1": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "liquid_transport_coefficient_1": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "m2/s"
                    },
                    "moisture_content_2": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "liquid_transport_coefficient_2": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "m2/s"
                    },
                    "moisture_content_3": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "liquid_transport_coefficient_3": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "m2/s"
                    },
                    "moisture_content_4": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "liquid_transport_coefficient_4": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "m2/s"
                    },
                    "moisture_content_5": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "liquid_transport_coefficient_5": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "m2/s"
                    },
                    "moisture_content_6": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "liquid_transport_coefficient_6": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "m2/s"
                    },
                    "moisture_content_7": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "liquid_transport_coefficient_7": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "m2/s"
                    },
                    "moisture_content_8": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "liquid_transport_coefficient_8": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "m2/s"
                    },
                    "moisture_content_9": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "liquid_transport_coefficient_9": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "m2/s"
                    },
                    "moisture_content_10": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "liquid_transport_coefficient_10": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "m2/s"
                    },
                    "moisture_content_11": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "liquid_transport_coefficient_11": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "m2/s"
                    },
                    "moisture_content_12": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "liquid_transport_coefficient_12": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "m2/s"
                    },
                    "moisture_content_13": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "liquid_transport_coefficient_13": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "m2/s"
                    },
                    "moisture_content_14": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "liquid_transport_coefficient_14": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "m2/s"
                    },
                    "moisture_content_15": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "liquid_transport_coefficient_15": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "m2/s"
                    },
                    "moisture_content_16": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "liquid_transport_coefficient_16": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "m2/s"
                    },
                    "moisture_content_17": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "liquid_transport_coefficient_17": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "m2/s"
                    },
                    "moisture_content_18": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "liquid_transport_coefficient_18": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "m2/s"
                    },
                    "moisture_content_19": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "liquid_transport_coefficient_19": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "m2/s"
                    },
                    "moisture_content_20": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "liquid_transport_coefficient_20": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "m2/s"
                    },
                    "moisture_content_21": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "liquid_transport_coefficient_21": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "m2/s"
                    },
                    "moisture_content_22": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "liquid_transport_coefficient_22": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "m2/s"
                    },
                    "moisture_content_23": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "liquid_transport_coefficient_23": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "m2/s"
                    },
                    "moisture_content_24": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "liquid_transport_coefficient_24": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "m2/s"
                    },
                    "moisture_content_25": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "kg/m3"
                    },
                    "liquid_transport_coefficient_25": {
                        "type": "number",
                        "minimum": 0.0,
                        "units": "m2/s"
                    }
                },
                "required": [
                    "material_name",
                    "number_of_redistribution_points",
                    "moisture_content_1",
                    "liquid_transport_coefficient_1"
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
                "number_of_redistribution_points": {
                    "field_name": "Number of Redistribution points",
                    "field_type": "n"
                },
                "moisture_content_1": {
                    "field_name": "Moisture Content 1",
                    "field_type": "n"
                },
                "liquid_transport_coefficient_1": {
                    "field_name": "Liquid Transport Coefficient 1",
                    "field_type": "n"
                },
                "moisture_content_2": {
                    "field_name": "Moisture Content 2",
                    "field_type": "n"
                },
                "liquid_transport_coefficient_2": {
                    "field_name": "Liquid Transport Coefficient 2",
                    "field_type": "n"
                },
                "moisture_content_3": {
                    "field_name": "Moisture Content 3",
                    "field_type": "n"
                },
                "liquid_transport_coefficient_3": {
                    "field_name": "Liquid Transport Coefficient 3",
                    "field_type": "n"
                },
                "moisture_content_4": {
                    "field_name": "Moisture Content 4",
                    "field_type": "n"
                },
                "liquid_transport_coefficient_4": {
                    "field_name": "Liquid Transport Coefficient 4",
                    "field_type": "n"
                },
                "moisture_content_5": {
                    "field_name": "Moisture Content 5",
                    "field_type": "n"
                },
                "liquid_transport_coefficient_5": {
                    "field_name": "Liquid Transport Coefficient 5",
                    "field_type": "n"
                },
                "moisture_content_6": {
                    "field_name": "Moisture Content 6",
                    "field_type": "n"
                },
                "liquid_transport_coefficient_6": {
                    "field_name": "Liquid Transport Coefficient 6",
                    "field_type": "n"
                },
                "moisture_content_7": {
                    "field_name": "Moisture Content 7",
                    "field_type": "n"
                },
                "liquid_transport_coefficient_7": {
                    "field_name": "Liquid Transport Coefficient 7",
                    "field_type": "n"
                },
                "moisture_content_8": {
                    "field_name": "Moisture Content 8",
                    "field_type": "n"
                },
                "liquid_transport_coefficient_8": {
                    "field_name": "Liquid Transport Coefficient 8",
                    "field_type": "n"
                },
                "moisture_content_9": {
                    "field_name": "Moisture Content 9",
                    "field_type": "n"
                },
                "liquid_transport_coefficient_9": {
                    "field_name": "Liquid Transport Coefficient 9",
                    "field_type": "n"
                },
                "moisture_content_10": {
                    "field_name": "Moisture Content 10",
                    "field_type": "n"
                },
                "liquid_transport_coefficient_10": {
                    "field_name": "Liquid Transport Coefficient 10",
                    "field_type": "n"
                },
                "moisture_content_11": {
                    "field_name": "Moisture Content 11",
                    "field_type": "n"
                },
                "liquid_transport_coefficient_11": {
                    "field_name": "Liquid Transport Coefficient 11",
                    "field_type": "n"
                },
                "moisture_content_12": {
                    "field_name": "Moisture Content 12",
                    "field_type": "n"
                },
                "liquid_transport_coefficient_12": {
                    "field_name": "Liquid Transport Coefficient 12",
                    "field_type": "n"
                },
                "moisture_content_13": {
                    "field_name": "Moisture Content 13",
                    "field_type": "n"
                },
                "liquid_transport_coefficient_13": {
                    "field_name": "Liquid Transport Coefficient 13",
                    "field_type": "n"
                },
                "moisture_content_14": {
                    "field_name": "Moisture Content 14",
                    "field_type": "n"
                },
                "liquid_transport_coefficient_14": {
                    "field_name": "Liquid Transport Coefficient 14",
                    "field_type": "n"
                },
                "moisture_content_15": {
                    "field_name": "Moisture Content 15",
                    "field_type": "n"
                },
                "liquid_transport_coefficient_15": {
                    "field_name": "Liquid Transport Coefficient 15",
                    "field_type": "n"
                },
                "moisture_content_16": {
                    "field_name": "Moisture Content 16",
                    "field_type": "n"
                },
                "liquid_transport_coefficient_16": {
                    "field_name": "Liquid Transport Coefficient 16",
                    "field_type": "n"
                },
                "moisture_content_17": {
                    "field_name": "Moisture Content 17",
                    "field_type": "n"
                },
                "liquid_transport_coefficient_17": {
                    "field_name": "Liquid Transport Coefficient 17",
                    "field_type": "n"
                },
                "moisture_content_18": {
                    "field_name": "Moisture Content 18",
                    "field_type": "n"
                },
                "liquid_transport_coefficient_18": {
                    "field_name": "Liquid Transport Coefficient 18",
                    "field_type": "n"
                },
                "moisture_content_19": {
                    "field_name": "Moisture Content 19",
                    "field_type": "n"
                },
                "liquid_transport_coefficient_19": {
                    "field_name": "Liquid Transport Coefficient 19",
                    "field_type": "n"
                },
                "moisture_content_20": {
                    "field_name": "Moisture Content 20",
                    "field_type": "n"
                },
                "liquid_transport_coefficient_20": {
                    "field_name": "Liquid Transport Coefficient 20",
                    "field_type": "n"
                },
                "moisture_content_21": {
                    "field_name": "Moisture Content 21",
                    "field_type": "n"
                },
                "liquid_transport_coefficient_21": {
                    "field_name": "Liquid Transport Coefficient 21",
                    "field_type": "n"
                },
                "moisture_content_22": {
                    "field_name": "Moisture Content 22",
                    "field_type": "n"
                },
                "liquid_transport_coefficient_22": {
                    "field_name": "Liquid Transport Coefficient 22",
                    "field_type": "n"
                },
                "moisture_content_23": {
                    "field_name": "Moisture Content 23",
                    "field_type": "n"
                },
                "liquid_transport_coefficient_23": {
                    "field_name": "Liquid Transport Coefficient 23",
                    "field_type": "n"
                },
                "moisture_content_24": {
                    "field_name": "Moisture Content 24",
                    "field_type": "n"
                },
                "liquid_transport_coefficient_24": {
                    "field_name": "Liquid Transport Coefficient 24",
                    "field_type": "n"
                },
                "moisture_content_25": {
                    "field_name": "Moisture Content 25",
                    "field_type": "n"
                },
                "liquid_transport_coefficient_25": {
                    "field_name": "Liquid Transport Coefficient 25",
                    "field_type": "n"
                }
            },
            "fields": [
                "material_name",
                "number_of_redistribution_points",
                "moisture_content_1",
                "liquid_transport_coefficient_1",
                "moisture_content_2",
                "liquid_transport_coefficient_2",
                "moisture_content_3",
                "liquid_transport_coefficient_3",
                "moisture_content_4",
                "liquid_transport_coefficient_4",
                "moisture_content_5",
                "liquid_transport_coefficient_5",
                "moisture_content_6",
                "liquid_transport_coefficient_6",
                "moisture_content_7",
                "liquid_transport_coefficient_7",
                "moisture_content_8",
                "liquid_transport_coefficient_8",
                "moisture_content_9",
                "liquid_transport_coefficient_9",
                "moisture_content_10",
                "liquid_transport_coefficient_10",
                "moisture_content_11",
                "liquid_transport_coefficient_11",
                "moisture_content_12",
                "liquid_transport_coefficient_12",
                "moisture_content_13",
                "liquid_transport_coefficient_13",
                "moisture_content_14",
                "liquid_transport_coefficient_14",
                "moisture_content_15",
                "liquid_transport_coefficient_15",
                "moisture_content_16",
                "liquid_transport_coefficient_16",
                "moisture_content_17",
                "liquid_transport_coefficient_17",
                "moisture_content_18",
                "liquid_transport_coefficient_18",
                "moisture_content_19",
                "liquid_transport_coefficient_19",
                "moisture_content_20",
                "liquid_transport_coefficient_20",
                "moisture_content_21",
                "liquid_transport_coefficient_21",
                "moisture_content_22",
                "liquid_transport_coefficient_22",
                "moisture_content_23",
                "liquid_transport_coefficient_23",
                "moisture_content_24",
                "liquid_transport_coefficient_24",
                "moisture_content_25",
                "liquid_transport_coefficient_25"
            ],
            "alphas": {
                "fields": [
                    "material_name"
                ]
            },
            "numerics": {
                "fields": [
                    "number_of_redistribution_points",
                    "moisture_content_1",
                    "liquid_transport_coefficient_1",
                    "moisture_content_2",
                    "liquid_transport_coefficient_2",
                    "moisture_content_3",
                    "liquid_transport_coefficient_3",
                    "moisture_content_4",
                    "liquid_transport_coefficient_4",
                    "moisture_content_5",
                    "liquid_transport_coefficient_5",
                    "moisture_content_6",
                    "liquid_transport_coefficient_6",
                    "moisture_content_7",
                    "liquid_transport_coefficient_7",
                    "moisture_content_8",
                    "liquid_transport_coefficient_8",
                    "moisture_content_9",
                    "liquid_transport_coefficient_9",
                    "moisture_content_10",
                    "liquid_transport_coefficient_10",
                    "moisture_content_11",
                    "liquid_transport_coefficient_11",
                    "moisture_content_12",
                    "liquid_transport_coefficient_12",
                    "moisture_content_13",
                    "liquid_transport_coefficient_13",
                    "moisture_content_14",
                    "liquid_transport_coefficient_14",
                    "moisture_content_15",
                    "liquid_transport_coefficient_15",
                    "moisture_content_16",
                    "liquid_transport_coefficient_16",
                    "moisture_content_17",
                    "liquid_transport_coefficient_17",
                    "moisture_content_18",
                    "liquid_transport_coefficient_18",
                    "moisture_content_19",
                    "liquid_transport_coefficient_19",
                    "moisture_content_20",
                    "liquid_transport_coefficient_20",
                    "moisture_content_21",
                    "liquid_transport_coefficient_21",
                    "moisture_content_22",
                    "liquid_transport_coefficient_22",
                    "moisture_content_23",
                    "liquid_transport_coefficient_23",
                    "moisture_content_24",
                    "liquid_transport_coefficient_24",
                    "moisture_content_25",
                    "liquid_transport_coefficient_25"
                ]
            }
        },
        "type": "object",
        "memo": "HeatBalanceAlgorithm = CombinedHeatAndMoistureFiniteElement solution algorithm only. Relationship between liquid transport coefficient and moisture content Has no effect with other HeatBalanceAlgorithm solution algorithms"
    }
}
```
