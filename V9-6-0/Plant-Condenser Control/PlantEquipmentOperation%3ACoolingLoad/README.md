```
{
    "PlantEquipmentOperation:CoolingLoad": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "load_range_1_lower_limit": {
                        "type": "number",
                        "units": "W",
                        "minimum": 0.0
                    },
                    "load_range_1_upper_limit": {
                        "type": "number",
                        "units": "W",
                        "minimum": 0.0
                    },
                    "range_1_equipment_list_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "PlantAndCondenserEquipmentLists"
                        ]
                    },
                    "load_range_2_lower_limit": {
                        "type": "number",
                        "units": "W",
                        "minimum": 0.0
                    },
                    "load_range_2_upper_limit": {
                        "type": "number",
                        "units": "W"
                    },
                    "range_2_equipment_list_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "PlantAndCondenserEquipmentLists"
                        ]
                    },
                    "load_range_3_lower_limit": {
                        "type": "number",
                        "units": "W",
                        "minimum": 0.0
                    },
                    "load_range_3_upper_limit": {
                        "type": "number",
                        "units": "W",
                        "minimum": 0.0
                    },
                    "range_3_equipment_list_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "PlantAndCondenserEquipmentLists"
                        ]
                    },
                    "load_range_4_lower_limit": {
                        "type": "number",
                        "units": "W",
                        "minimum": 0.0
                    },
                    "load_range_4_upper_limit": {
                        "type": "number",
                        "units": "W",
                        "minimum": 0.0
                    },
                    "range_4_equipment_list_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "PlantAndCondenserEquipmentLists"
                        ]
                    },
                    "load_range_5_lower_limit": {
                        "type": "number",
                        "units": "W",
                        "minimum": 0.0
                    },
                    "load_range_5_upper_limit": {
                        "type": "number",
                        "units": "W",
                        "minimum": 0.0
                    },
                    "range_5_equipment_list_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "PlantAndCondenserEquipmentLists"
                        ]
                    },
                    "load_range_6_lower_limit": {
                        "type": "number",
                        "units": "W",
                        "minimum": 0.0
                    },
                    "load_range_6_upper_limit": {
                        "type": "number",
                        "units": "W",
                        "minimum": 0.0
                    },
                    "range_6_equipment_list_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "PlantAndCondenserEquipmentLists"
                        ]
                    },
                    "load_range_7_lower_limit": {
                        "type": "number",
                        "units": "W",
                        "minimum": 0.0
                    },
                    "load_range_7_upper_limit": {
                        "type": "number",
                        "units": "W",
                        "minimum": 0.0
                    },
                    "range_7_equipment_list_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "PlantAndCondenserEquipmentLists"
                        ]
                    },
                    "load_range_8_lower_limit": {
                        "type": "number",
                        "units": "W",
                        "minimum": 0.0
                    },
                    "load_range_8_upper_limit": {
                        "type": "number",
                        "units": "W",
                        "minimum": 0.0
                    },
                    "range_8_equipment_list_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "PlantAndCondenserEquipmentLists"
                        ]
                    },
                    "load_range_9_lower_limit": {
                        "type": "number",
                        "units": "W",
                        "minimum": 0.0
                    },
                    "load_range_9_upper_limit": {
                        "type": "number",
                        "units": "W",
                        "minimum": 0.0
                    },
                    "range_9_equipment_list_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "PlantAndCondenserEquipmentLists"
                        ]
                    },
                    "load_range_10_lower_limit": {
                        "type": "number",
                        "units": "W",
                        "minimum": 0.0
                    },
                    "load_range_10_upper_limit": {
                        "type": "number",
                        "units": "W",
                        "minimum": 0.0
                    },
                    "range_10_equipment_list_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "PlantAndCondenserEquipmentLists"
                        ]
                    }
                },
                "required": [
                    "load_range_1_lower_limit",
                    "load_range_1_upper_limit"
                ]
            }
        },
        "group": "Plant-Condenser Control",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "ControlSchemeList"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "load_range_1_lower_limit": {
                    "field_name": "Load Range 1 Lower Limit",
                    "field_type": "n"
                },
                "load_range_1_upper_limit": {
                    "field_name": "Load Range 1 Upper Limit",
                    "field_type": "n"
                },
                "range_1_equipment_list_name": {
                    "field_name": "Range 1 Equipment List Name",
                    "field_type": "a"
                },
                "load_range_2_lower_limit": {
                    "field_name": "Load Range 2 Lower Limit",
                    "field_type": "n"
                },
                "load_range_2_upper_limit": {
                    "field_name": "Load Range 2 Upper Limit",
                    "field_type": "n"
                },
                "range_2_equipment_list_name": {
                    "field_name": "Range 2 Equipment List Name",
                    "field_type": "a"
                },
                "load_range_3_lower_limit": {
                    "field_name": "Load Range 3 Lower Limit",
                    "field_type": "n"
                },
                "load_range_3_upper_limit": {
                    "field_name": "Load Range 3 Upper Limit",
                    "field_type": "n"
                },
                "range_3_equipment_list_name": {
                    "field_name": "Range 3 Equipment List Name",
                    "field_type": "a"
                },
                "load_range_4_lower_limit": {
                    "field_name": "Load Range 4 Lower Limit",
                    "field_type": "n"
                },
                "load_range_4_upper_limit": {
                    "field_name": "Load Range 4 Upper Limit",
                    "field_type": "n"
                },
                "range_4_equipment_list_name": {
                    "field_name": "Range 4 Equipment List Name",
                    "field_type": "a"
                },
                "load_range_5_lower_limit": {
                    "field_name": "Load Range 5 Lower Limit",
                    "field_type": "n"
                },
                "load_range_5_upper_limit": {
                    "field_name": "Load Range 5 Upper Limit",
                    "field_type": "n"
                },
                "range_5_equipment_list_name": {
                    "field_name": "Range 5 Equipment List Name",
                    "field_type": "a"
                },
                "load_range_6_lower_limit": {
                    "field_name": "Load Range 6 Lower Limit",
                    "field_type": "n"
                },
                "load_range_6_upper_limit": {
                    "field_name": "Load Range 6 Upper Limit",
                    "field_type": "n"
                },
                "range_6_equipment_list_name": {
                    "field_name": "Range 6 Equipment List Name",
                    "field_type": "a"
                },
                "load_range_7_lower_limit": {
                    "field_name": "Load Range 7 Lower Limit",
                    "field_type": "n"
                },
                "load_range_7_upper_limit": {
                    "field_name": "Load Range 7 Upper Limit",
                    "field_type": "n"
                },
                "range_7_equipment_list_name": {
                    "field_name": "Range 7 Equipment List Name",
                    "field_type": "a"
                },
                "load_range_8_lower_limit": {
                    "field_name": "Load Range 8 Lower Limit",
                    "field_type": "n"
                },
                "load_range_8_upper_limit": {
                    "field_name": "Load Range 8 Upper Limit",
                    "field_type": "n"
                },
                "range_8_equipment_list_name": {
                    "field_name": "Range 8 Equipment List Name",
                    "field_type": "a"
                },
                "load_range_9_lower_limit": {
                    "field_name": "Load Range 9 Lower Limit",
                    "field_type": "n"
                },
                "load_range_9_upper_limit": {
                    "field_name": "Load Range 9 Upper Limit",
                    "field_type": "n"
                },
                "range_9_equipment_list_name": {
                    "field_name": "Range 9 Equipment List Name",
                    "field_type": "a"
                },
                "load_range_10_lower_limit": {
                    "field_name": "Load Range 10 Lower Limit",
                    "field_type": "n"
                },
                "load_range_10_upper_limit": {
                    "field_name": "Load Range 10 Upper Limit",
                    "field_type": "n"
                },
                "range_10_equipment_list_name": {
                    "field_name": "Range 10 Equipment List Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "load_range_1_lower_limit",
                "load_range_1_upper_limit",
                "range_1_equipment_list_name",
                "load_range_2_lower_limit",
                "load_range_2_upper_limit",
                "range_2_equipment_list_name",
                "load_range_3_lower_limit",
                "load_range_3_upper_limit",
                "range_3_equipment_list_name",
                "load_range_4_lower_limit",
                "load_range_4_upper_limit",
                "range_4_equipment_list_name",
                "load_range_5_lower_limit",
                "load_range_5_upper_limit",
                "range_5_equipment_list_name",
                "load_range_6_lower_limit",
                "load_range_6_upper_limit",
                "range_6_equipment_list_name",
                "load_range_7_lower_limit",
                "load_range_7_upper_limit",
                "range_7_equipment_list_name",
                "load_range_8_lower_limit",
                "load_range_8_upper_limit",
                "range_8_equipment_list_name",
                "load_range_9_lower_limit",
                "load_range_9_upper_limit",
                "range_9_equipment_list_name",
                "load_range_10_lower_limit",
                "load_range_10_upper_limit",
                "range_10_equipment_list_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "range_1_equipment_list_name",
                    "range_2_equipment_list_name",
                    "range_3_equipment_list_name",
                    "range_4_equipment_list_name",
                    "range_5_equipment_list_name",
                    "range_6_equipment_list_name",
                    "range_7_equipment_list_name",
                    "range_8_equipment_list_name",
                    "range_9_equipment_list_name",
                    "range_10_equipment_list_name"
                ]
            },
            "numerics": {
                "fields": [
                    "load_range_1_lower_limit",
                    "load_range_1_upper_limit",
                    "load_range_2_lower_limit",
                    "load_range_2_upper_limit",
                    "load_range_3_lower_limit",
                    "load_range_3_upper_limit",
                    "load_range_4_lower_limit",
                    "load_range_4_upper_limit",
                    "load_range_5_lower_limit",
                    "load_range_5_upper_limit",
                    "load_range_6_lower_limit",
                    "load_range_6_upper_limit",
                    "load_range_7_lower_limit",
                    "load_range_7_upper_limit",
                    "load_range_8_lower_limit",
                    "load_range_8_upper_limit",
                    "load_range_9_lower_limit",
                    "load_range_9_upper_limit",
                    "load_range_10_lower_limit",
                    "load_range_10_upper_limit"
                ]
            }
        },
        "type": "object",
        "memo": "Plant equipment operation scheme for cooling load range operation. Specifies one or more groups of equipment which are available to operate for successive cooling load ranges.",
        "min_fields": 4.0
    }
}
```
