```
{
    "PlantEquipmentOperation:UserDefined": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "main_model_program_calling_manager_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ProgramNames"
                        ]
                    },
                    "initialization_program_calling_manager_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ProgramNames"
                        ]
                    },
                    "equipment_1_object_type": {
                        "type": "string"
                    },
                    "equipment_1_name": {
                        "type": "string"
                    },
                    "equipment_2_object_type": {
                        "type": "string"
                    },
                    "equipment_2_name": {
                        "type": "string"
                    },
                    "equipment_3_object_type": {
                        "type": "string"
                    },
                    "equipment_3_name": {
                        "type": "string"
                    },
                    "equipment_4_object_type": {
                        "type": "string"
                    },
                    "equipment_4_name": {
                        "type": "string"
                    },
                    "equipment_5_object_type": {
                        "type": "string"
                    },
                    "equipment_5_name": {
                        "type": "string"
                    },
                    "equipment_6_object_type": {
                        "type": "string"
                    },
                    "equipment_6_name": {
                        "type": "string"
                    },
                    "equipment_7_object_type": {
                        "type": "string"
                    },
                    "equipment_7_name": {
                        "type": "string"
                    },
                    "equipment_8_object_type": {
                        "type": "string"
                    },
                    "equipment_8_name": {
                        "type": "string"
                    },
                    "equipment_9_object_type": {
                        "type": "string"
                    },
                    "equipment_9_name": {
                        "type": "string"
                    },
                    "equipment_10_object_type": {
                        "type": "string"
                    },
                    "equipment_10_name": {
                        "type": "string"
                    }
                },
                "required": [
                    "main_model_program_calling_manager_name"
                ]
            }
        },
        "group": "User Defined HVAC and Plant Component Models",
        "name": {
            "type": "string",
            "is_required": true,
            "note": "This is the name of the plant operation scheme"
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "main_model_program_calling_manager_name": {
                    "field_name": "Main Model Program Calling Manager Name",
                    "field_type": "a"
                },
                "initialization_program_calling_manager_name": {
                    "field_name": "Initialization Program Calling Manager Name",
                    "field_type": "a"
                },
                "equipment_1_object_type": {
                    "field_name": "Equipment 1 Object Type",
                    "field_type": "a"
                },
                "equipment_1_name": {
                    "field_name": "Equipment 1 Name",
                    "field_type": "a"
                },
                "equipment_2_object_type": {
                    "field_name": "Equipment 2 Object Type",
                    "field_type": "a"
                },
                "equipment_2_name": {
                    "field_name": "Equipment 2 Name",
                    "field_type": "a"
                },
                "equipment_3_object_type": {
                    "field_name": "Equipment 3 Object Type",
                    "field_type": "a"
                },
                "equipment_3_name": {
                    "field_name": "Equipment 3 Name",
                    "field_type": "a"
                },
                "equipment_4_object_type": {
                    "field_name": "Equipment 4 Object Type",
                    "field_type": "a"
                },
                "equipment_4_name": {
                    "field_name": "Equipment 4 Name",
                    "field_type": "a"
                },
                "equipment_5_object_type": {
                    "field_name": "Equipment 5 Object Type",
                    "field_type": "a"
                },
                "equipment_5_name": {
                    "field_name": "Equipment 5 Name",
                    "field_type": "a"
                },
                "equipment_6_object_type": {
                    "field_name": "Equipment 6 Object Type",
                    "field_type": "a"
                },
                "equipment_6_name": {
                    "field_name": "Equipment 6 Name",
                    "field_type": "a"
                },
                "equipment_7_object_type": {
                    "field_name": "Equipment 7 Object Type",
                    "field_type": "a"
                },
                "equipment_7_name": {
                    "field_name": "Equipment 7 Name",
                    "field_type": "a"
                },
                "equipment_8_object_type": {
                    "field_name": "Equipment 8 Object Type",
                    "field_type": "a"
                },
                "equipment_8_name": {
                    "field_name": "Equipment 8 Name",
                    "field_type": "a"
                },
                "equipment_9_object_type": {
                    "field_name": "Equipment 9 Object Type",
                    "field_type": "a"
                },
                "equipment_9_name": {
                    "field_name": "Equipment 9 Name",
                    "field_type": "a"
                },
                "equipment_10_object_type": {
                    "field_name": "Equipment 10 Object Type",
                    "field_type": "a"
                },
                "equipment_10_name": {
                    "field_name": "Equipment 10 Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "main_model_program_calling_manager_name",
                "initialization_program_calling_manager_name",
                "equipment_1_object_type",
                "equipment_1_name",
                "equipment_2_object_type",
                "equipment_2_name",
                "equipment_3_object_type",
                "equipment_3_name",
                "equipment_4_object_type",
                "equipment_4_name",
                "equipment_5_object_type",
                "equipment_5_name",
                "equipment_6_object_type",
                "equipment_6_name",
                "equipment_7_object_type",
                "equipment_7_name",
                "equipment_8_object_type",
                "equipment_8_name",
                "equipment_9_object_type",
                "equipment_9_name",
                "equipment_10_object_type",
                "equipment_10_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "main_model_program_calling_manager_name",
                    "initialization_program_calling_manager_name",
                    "equipment_1_object_type",
                    "equipment_1_name",
                    "equipment_2_object_type",
                    "equipment_2_name",
                    "equipment_3_object_type",
                    "equipment_3_name",
                    "equipment_4_object_type",
                    "equipment_4_name",
                    "equipment_5_object_type",
                    "equipment_5_name",
                    "equipment_6_object_type",
                    "equipment_6_name",
                    "equipment_7_object_type",
                    "equipment_7_name",
                    "equipment_8_object_type",
                    "equipment_8_name",
                    "equipment_9_object_type",
                    "equipment_9_name",
                    "equipment_10_object_type",
                    "equipment_10_name"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "memo": "Defines a generic plant operation scheme for custom supervisory control using Energy Management System or External Interface to dispatch loads",
        "min_fields": 5.0
    }
}
```
