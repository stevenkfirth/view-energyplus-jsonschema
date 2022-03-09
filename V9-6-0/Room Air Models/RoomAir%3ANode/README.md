```
{
    "RoomAir:Node": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "node_type": {
                        "type": "string",
                        "enum": [
                            "Ceiling",
                            "Control",
                            "Floor",
                            "Inlet",
                            "MundtRoom",
                            "Return"
                        ]
                    },
                    "zone_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ]
                    },
                    "height_of_nodal_control_volume_center": {
                        "type": "number",
                        "units": "m"
                    },
                    "surface_1_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "AllHeatTranSurfNames"
                        ]
                    },
                    "surface_2_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "AllHeatTranSurfNames"
                        ]
                    },
                    "surface_3_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "AllHeatTranSurfNames"
                        ]
                    },
                    "surface_4_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "AllHeatTranSurfNames"
                        ]
                    },
                    "surface_5_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "AllHeatTranSurfNames"
                        ]
                    },
                    "surface_6_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "AllHeatTranSurfNames"
                        ]
                    },
                    "surface_7_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "AllHeatTranSurfNames"
                        ]
                    },
                    "surface_8_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "AllHeatTranSurfNames"
                        ]
                    },
                    "surface_9_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "AllHeatTranSurfNames"
                        ]
                    },
                    "surface_10_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "AllHeatTranSurfNames"
                        ]
                    },
                    "surface_11_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "AllHeatTranSurfNames"
                        ]
                    },
                    "surface_12_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "AllHeatTranSurfNames"
                        ]
                    },
                    "surface_13_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "AllHeatTranSurfNames"
                        ]
                    },
                    "surface_14_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "AllHeatTranSurfNames"
                        ]
                    },
                    "surface_15_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "AllHeatTranSurfNames"
                        ]
                    },
                    "surface_16_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "AllHeatTranSurfNames"
                        ]
                    },
                    "surface_17_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "AllHeatTranSurfNames"
                        ]
                    },
                    "surface_18_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "AllHeatTranSurfNames"
                        ]
                    },
                    "surface_19_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "AllHeatTranSurfNames"
                        ]
                    },
                    "surface_20_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "AllHeatTranSurfNames"
                        ]
                    },
                    "surface_21_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "AllHeatTranSurfNames"
                        ]
                    }
                },
                "required": [
                    "node_type",
                    "zone_name",
                    "height_of_nodal_control_volume_center"
                ]
            }
        },
        "group": "Room Air Models",
        "name": {
            "type": "string",
            "reference": [
                "RoomAirNodes"
            ]
        },
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "node_type": {
                    "field_name": "Node Type",
                    "field_type": "a"
                },
                "zone_name": {
                    "field_name": "Zone Name",
                    "field_type": "a"
                },
                "height_of_nodal_control_volume_center": {
                    "field_name": "Height of Nodal Control Volume Center",
                    "field_type": "n"
                },
                "surface_1_name": {
                    "field_name": "Surface 1 Name",
                    "field_type": "a"
                },
                "surface_2_name": {
                    "field_name": "Surface 2 Name",
                    "field_type": "a"
                },
                "surface_3_name": {
                    "field_name": "Surface 3 Name",
                    "field_type": "a"
                },
                "surface_4_name": {
                    "field_name": "Surface 4 Name",
                    "field_type": "a"
                },
                "surface_5_name": {
                    "field_name": "Surface 5 Name",
                    "field_type": "a"
                },
                "surface_6_name": {
                    "field_name": "Surface 6 Name",
                    "field_type": "a"
                },
                "surface_7_name": {
                    "field_name": "Surface 7 Name",
                    "field_type": "a"
                },
                "surface_8_name": {
                    "field_name": "Surface 8 Name",
                    "field_type": "a"
                },
                "surface_9_name": {
                    "field_name": "Surface 9 Name",
                    "field_type": "a"
                },
                "surface_10_name": {
                    "field_name": "Surface 10 Name",
                    "field_type": "a"
                },
                "surface_11_name": {
                    "field_name": "Surface 11 Name",
                    "field_type": "a"
                },
                "surface_12_name": {
                    "field_name": "Surface 12 Name",
                    "field_type": "a"
                },
                "surface_13_name": {
                    "field_name": "Surface 13 Name",
                    "field_type": "a"
                },
                "surface_14_name": {
                    "field_name": "Surface 14 Name",
                    "field_type": "a"
                },
                "surface_15_name": {
                    "field_name": "Surface 15 Name",
                    "field_type": "a"
                },
                "surface_16_name": {
                    "field_name": "Surface 16 Name",
                    "field_type": "a"
                },
                "surface_17_name": {
                    "field_name": "Surface 17 Name",
                    "field_type": "a"
                },
                "surface_18_name": {
                    "field_name": "Surface 18 Name",
                    "field_type": "a"
                },
                "surface_19_name": {
                    "field_name": "Surface 19 Name",
                    "field_type": "a"
                },
                "surface_20_name": {
                    "field_name": "Surface 20 Name",
                    "field_type": "a"
                },
                "surface_21_name": {
                    "field_name": "Surface 21 Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "node_type",
                "zone_name",
                "height_of_nodal_control_volume_center",
                "surface_1_name",
                "surface_2_name",
                "surface_3_name",
                "surface_4_name",
                "surface_5_name",
                "surface_6_name",
                "surface_7_name",
                "surface_8_name",
                "surface_9_name",
                "surface_10_name",
                "surface_11_name",
                "surface_12_name",
                "surface_13_name",
                "surface_14_name",
                "surface_15_name",
                "surface_16_name",
                "surface_17_name",
                "surface_18_name",
                "surface_19_name",
                "surface_20_name",
                "surface_21_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "node_type",
                    "zone_name",
                    "surface_1_name",
                    "surface_2_name",
                    "surface_3_name",
                    "surface_4_name",
                    "surface_5_name",
                    "surface_6_name",
                    "surface_7_name",
                    "surface_8_name",
                    "surface_9_name",
                    "surface_10_name",
                    "surface_11_name",
                    "surface_12_name",
                    "surface_13_name",
                    "surface_14_name",
                    "surface_15_name",
                    "surface_16_name",
                    "surface_17_name",
                    "surface_18_name",
                    "surface_19_name",
                    "surface_20_name",
                    "surface_21_name"
                ]
            },
            "numerics": {
                "fields": [
                    "height_of_nodal_control_volume_center"
                ]
            }
        },
        "type": "object",
        "memo": "Define an air node for some types of nodal room air models"
    }
}
```
