```
{
    "AirLoopHVAC:OutdoorAirSystem:EquipmentList": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "component_1_object_type": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "validOASysEquipmentTypes"
                        ]
                    },
                    "component_1_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "validOASysEquipmentNames"
                        ]
                    },
                    "component_2_object_type": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "validOASysEquipmentTypes"
                        ]
                    },
                    "component_2_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "validOASysEquipmentNames"
                        ]
                    },
                    "component_3_object_type": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "validOASysEquipmentTypes"
                        ]
                    },
                    "component_3_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "validOASysEquipmentNames"
                        ]
                    },
                    "component_4_object_type": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "validOASysEquipmentTypes"
                        ]
                    },
                    "component_4_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "validOASysEquipmentNames"
                        ]
                    },
                    "component_5_object_type": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "validOASysEquipmentTypes"
                        ]
                    },
                    "component_5_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "validOASysEquipmentNames"
                        ]
                    },
                    "component_6_object_type": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "validOASysEquipmentTypes"
                        ]
                    },
                    "component_6_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "validOASysEquipmentNames"
                        ]
                    },
                    "component_7_object_type": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "validOASysEquipmentTypes"
                        ]
                    },
                    "component_7_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "validOASysEquipmentNames"
                        ]
                    },
                    "component_8_object_type": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "validOASysEquipmentTypes"
                        ]
                    },
                    "component_8_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "validOASysEquipmentNames"
                        ]
                    },
                    "component_9_object_type": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "validOASysEquipmentTypes"
                        ]
                    },
                    "component_9_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "validOASysEquipmentNames"
                        ]
                    }
                },
                "required": [
                    "component_1_object_type",
                    "component_1_name"
                ]
            }
        },
        "group": "Air Distribution",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "AirLoopOAEquipmentLists"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "component_1_object_type": {
                    "field_name": "Component 1 Object Type",
                    "field_type": "a"
                },
                "component_1_name": {
                    "field_name": "Component 1 Name",
                    "field_type": "a"
                },
                "component_2_object_type": {
                    "field_name": "Component 2 Object Type",
                    "field_type": "a"
                },
                "component_2_name": {
                    "field_name": "Component 2 Name",
                    "field_type": "a"
                },
                "component_3_object_type": {
                    "field_name": "Component 3 Object Type",
                    "field_type": "a"
                },
                "component_3_name": {
                    "field_name": "Component 3 Name",
                    "field_type": "a"
                },
                "component_4_object_type": {
                    "field_name": "Component 4 Object Type",
                    "field_type": "a"
                },
                "component_4_name": {
                    "field_name": "Component 4 Name",
                    "field_type": "a"
                },
                "component_5_object_type": {
                    "field_name": "Component 5 Object Type",
                    "field_type": "a"
                },
                "component_5_name": {
                    "field_name": "Component 5 Name",
                    "field_type": "a"
                },
                "component_6_object_type": {
                    "field_name": "Component 6 Object Type",
                    "field_type": "a"
                },
                "component_6_name": {
                    "field_name": "Component 6 Name",
                    "field_type": "a"
                },
                "component_7_object_type": {
                    "field_name": "Component 7 Object Type",
                    "field_type": "a"
                },
                "component_7_name": {
                    "field_name": "Component 7 Name",
                    "field_type": "a"
                },
                "component_8_object_type": {
                    "field_name": "Component 8 Object Type",
                    "field_type": "a"
                },
                "component_8_name": {
                    "field_name": "Component 8 Name",
                    "field_type": "a"
                },
                "component_9_object_type": {
                    "field_name": "Component 9 Object Type",
                    "field_type": "a"
                },
                "component_9_name": {
                    "field_name": "Component 9 Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "component_1_object_type",
                "component_1_name",
                "component_2_object_type",
                "component_2_name",
                "component_3_object_type",
                "component_3_name",
                "component_4_object_type",
                "component_4_name",
                "component_5_object_type",
                "component_5_name",
                "component_6_object_type",
                "component_6_name",
                "component_7_object_type",
                "component_7_name",
                "component_8_object_type",
                "component_8_name",
                "component_9_object_type",
                "component_9_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "component_1_object_type",
                    "component_1_name",
                    "component_2_object_type",
                    "component_2_name",
                    "component_3_object_type",
                    "component_3_name",
                    "component_4_object_type",
                    "component_4_name",
                    "component_5_object_type",
                    "component_5_name",
                    "component_6_object_type",
                    "component_6_name",
                    "component_7_object_type",
                    "component_7_name",
                    "component_8_object_type",
                    "component_8_name",
                    "component_9_object_type",
                    "component_9_name"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "memo": "List equipment in simulation order"
    }
}
```
