```
{
    "AirLoopHVAC:ControllerList": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "controller_1_object_type": {
                        "type": "string",
                        "enum": [
                            "Controller:OutdoorAir",
                            "Controller:WaterCoil"
                        ]
                    },
                    "controller_1_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "AirLoopControllers"
                        ]
                    },
                    "controller_2_object_type": {
                        "type": "string",
                        "enum": [
                            "Controller:OutdoorAir",
                            "Controller:WaterCoil"
                        ]
                    },
                    "controller_2_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "AirLoopControllers"
                        ]
                    },
                    "controller_3_object_type": {
                        "type": "string",
                        "enum": [
                            "Controller:OutdoorAir",
                            "Controller:WaterCoil"
                        ]
                    },
                    "controller_3_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "AirLoopControllers"
                        ]
                    },
                    "controller_4_object_type": {
                        "type": "string",
                        "enum": [
                            "Controller:OutdoorAir",
                            "Controller:WaterCoil"
                        ]
                    },
                    "controller_4_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "AirLoopControllers"
                        ]
                    },
                    "controller_5_object_type": {
                        "type": "string",
                        "enum": [
                            "Controller:OutdoorAir",
                            "Controller:WaterCoil"
                        ]
                    },
                    "controller_5_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "AirLoopControllers"
                        ]
                    },
                    "controller_6_object_type": {
                        "type": "string",
                        "enum": [
                            "Controller:OutdoorAir",
                            "Controller:WaterCoil"
                        ]
                    },
                    "controller_6_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "AirLoopControllers"
                        ]
                    },
                    "controller_7_object_type": {
                        "type": "string",
                        "enum": [
                            "Controller:OutdoorAir",
                            "Controller:WaterCoil"
                        ]
                    },
                    "controller_7_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "AirLoopControllers"
                        ]
                    },
                    "controller_8_object_type": {
                        "type": "string",
                        "enum": [
                            "Controller:OutdoorAir",
                            "Controller:WaterCoil"
                        ]
                    },
                    "controller_8_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "AirLoopControllers"
                        ]
                    }
                },
                "required": [
                    "controller_1_object_type",
                    "controller_1_name"
                ]
            }
        },
        "group": "Controllers",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "ControllerLists"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "controller_1_object_type": {
                    "field_name": "Controller 1 Object Type",
                    "field_type": "a"
                },
                "controller_1_name": {
                    "field_name": "Controller 1 Name",
                    "field_type": "a"
                },
                "controller_2_object_type": {
                    "field_name": "Controller 2 Object Type",
                    "field_type": "a"
                },
                "controller_2_name": {
                    "field_name": "Controller 2 Name",
                    "field_type": "a"
                },
                "controller_3_object_type": {
                    "field_name": "Controller 3 Object Type",
                    "field_type": "a"
                },
                "controller_3_name": {
                    "field_name": "Controller 3 Name",
                    "field_type": "a"
                },
                "controller_4_object_type": {
                    "field_name": "Controller 4 Object Type",
                    "field_type": "a"
                },
                "controller_4_name": {
                    "field_name": "Controller 4 Name",
                    "field_type": "a"
                },
                "controller_5_object_type": {
                    "field_name": "Controller 5 Object Type",
                    "field_type": "a"
                },
                "controller_5_name": {
                    "field_name": "Controller 5 Name",
                    "field_type": "a"
                },
                "controller_6_object_type": {
                    "field_name": "Controller 6 Object Type",
                    "field_type": "a"
                },
                "controller_6_name": {
                    "field_name": "Controller 6 Name",
                    "field_type": "a"
                },
                "controller_7_object_type": {
                    "field_name": "Controller 7 Object Type",
                    "field_type": "a"
                },
                "controller_7_name": {
                    "field_name": "Controller 7 Name",
                    "field_type": "a"
                },
                "controller_8_object_type": {
                    "field_name": "Controller 8 Object Type",
                    "field_type": "a"
                },
                "controller_8_name": {
                    "field_name": "Controller 8 Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "controller_1_object_type",
                "controller_1_name",
                "controller_2_object_type",
                "controller_2_name",
                "controller_3_object_type",
                "controller_3_name",
                "controller_4_object_type",
                "controller_4_name",
                "controller_5_object_type",
                "controller_5_name",
                "controller_6_object_type",
                "controller_6_name",
                "controller_7_object_type",
                "controller_7_name",
                "controller_8_object_type",
                "controller_8_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "controller_1_object_type",
                    "controller_1_name",
                    "controller_2_object_type",
                    "controller_2_name",
                    "controller_3_object_type",
                    "controller_3_name",
                    "controller_4_object_type",
                    "controller_4_name",
                    "controller_5_object_type",
                    "controller_5_name",
                    "controller_6_object_type",
                    "controller_6_name",
                    "controller_7_object_type",
                    "controller_7_name",
                    "controller_8_object_type",
                    "controller_8_name"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "memo": "List controllers in order of control sequence"
    }
}
```
