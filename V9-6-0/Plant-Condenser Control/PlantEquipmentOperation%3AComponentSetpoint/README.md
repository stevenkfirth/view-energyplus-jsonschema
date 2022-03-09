```
{
    "PlantEquipmentOperation:ComponentSetpoint": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "equipment_1_object_type": {
                        "type": "string"
                    },
                    "equipment_1_name": {
                        "type": "string"
                    },
                    "demand_calculation_1_node_name": {
                        "type": "string"
                    },
                    "setpoint_1_node_name": {
                        "type": "string"
                    },
                    "component_1_flow_rate": {
                        "units": "m3/s",
                        "anyOf": [
                            {
                                "type": "number"
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "operation_1_type": {
                        "type": "string",
                        "enum": [
                            "Cooling",
                            "Dual",
                            "Heating"
                        ]
                    },
                    "equipment_2_object_type": {
                        "type": "string"
                    },
                    "equipment_2_name": {
                        "type": "string"
                    },
                    "demand_calculation_2_node_name": {
                        "type": "string"
                    },
                    "setpoint_2_node_name": {
                        "type": "string"
                    },
                    "component_2_flow_rate": {
                        "units": "m3/s",
                        "anyOf": [
                            {
                                "type": "number"
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "operation_2_type": {
                        "type": "string",
                        "enum": [
                            "Cooling",
                            "Dual",
                            "Heating"
                        ]
                    },
                    "equipment_3_object_type": {
                        "type": "string"
                    },
                    "equipment_3_name": {
                        "type": "string"
                    },
                    "demand_calculation_3_node_name": {
                        "type": "string"
                    },
                    "setpoint_3_node_name": {
                        "type": "string"
                    },
                    "component_3_flow_rate": {
                        "units": "m3/s",
                        "anyOf": [
                            {
                                "type": "number"
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "operation_3_type": {
                        "type": "string",
                        "enum": [
                            "Cooling",
                            "Dual",
                            "Heating"
                        ]
                    },
                    "equipment_4_object_type": {
                        "type": "string"
                    },
                    "equipment_4_name": {
                        "type": "string"
                    },
                    "demand_calculation_4_node_name": {
                        "type": "string"
                    },
                    "setpoint_4_node_name": {
                        "type": "string"
                    },
                    "component_4_flow_rate": {
                        "units": "m3/s",
                        "anyOf": [
                            {
                                "type": "number"
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "operation_4_type": {
                        "type": "string",
                        "enum": [
                            "Cooling",
                            "Dual",
                            "Heating"
                        ]
                    },
                    "equipment_5_object_type": {
                        "type": "string"
                    },
                    "equipment_5_name": {
                        "type": "string"
                    },
                    "demand_calculation_5_node_name": {
                        "type": "string"
                    },
                    "setpoint_5_node_name": {
                        "type": "string"
                    },
                    "component_5_flow_rate": {
                        "units": "m3/s",
                        "anyOf": [
                            {
                                "type": "number"
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "operation_5_type": {
                        "type": "string",
                        "enum": [
                            "Cooling",
                            "Dual",
                            "Heating"
                        ]
                    },
                    "equipment_6_object_type": {
                        "type": "string"
                    },
                    "equipment_6_name": {
                        "type": "string"
                    },
                    "demand_calculation_6_node_name": {
                        "type": "string"
                    },
                    "setpoint_6_node_name": {
                        "type": "string"
                    },
                    "component_6_flow_rate": {
                        "units": "m3/s",
                        "anyOf": [
                            {
                                "type": "number"
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "operation_6_type": {
                        "type": "string",
                        "enum": [
                            "Cooling",
                            "Dual",
                            "Heating"
                        ]
                    },
                    "equipment_7_object_type": {
                        "type": "string"
                    },
                    "equipment_7_name": {
                        "type": "string"
                    },
                    "demand_calculation_7_node_name": {
                        "type": "string"
                    },
                    "setpoint_7_node_name": {
                        "type": "string"
                    },
                    "component_7_flow_rate": {
                        "units": "m3/s",
                        "anyOf": [
                            {
                                "type": "number"
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "operation_7_type": {
                        "type": "string",
                        "enum": [
                            "Cooling",
                            "Dual",
                            "Heating"
                        ]
                    },
                    "equipment_8_object_type": {
                        "type": "string"
                    },
                    "equipment_8_name": {
                        "type": "string"
                    },
                    "demand_calculation_8_node_name": {
                        "type": "string"
                    },
                    "setpoint_8_node_name": {
                        "type": "string"
                    },
                    "component_8_flow_rate": {
                        "units": "m3/s",
                        "anyOf": [
                            {
                                "type": "number"
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "operation_8_type": {
                        "type": "string",
                        "enum": [
                            "Cooling",
                            "Dual",
                            "Heating"
                        ]
                    },
                    "equipment_9_object_type": {
                        "type": "string"
                    },
                    "equipment_9_name": {
                        "type": "string"
                    },
                    "demand_calculation_9_node_name": {
                        "type": "string"
                    },
                    "setpoint_9_node_name": {
                        "type": "string"
                    },
                    "component_9_flow_rate": {
                        "units": "m3/s",
                        "anyOf": [
                            {
                                "type": "number"
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "operation_9_type": {
                        "type": "string",
                        "enum": [
                            "Cooling",
                            "Dual",
                            "Heating"
                        ]
                    },
                    "equipment_10_object_type": {
                        "type": "string"
                    },
                    "equipment_10_name": {
                        "type": "string"
                    },
                    "demand_calculation_10_node_name": {
                        "type": "string"
                    },
                    "setpoint_10_node_name": {
                        "type": "string"
                    },
                    "component_10_flow_rate": {
                        "units": "m3/s",
                        "anyOf": [
                            {
                                "type": "number"
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "operation_10_type": {
                        "type": "string",
                        "enum": [
                            "Cooling",
                            "Dual",
                            "Heating"
                        ]
                    }
                },
                "required": [
                    "equipment_1_object_type",
                    "equipment_1_name",
                    "demand_calculation_1_node_name",
                    "setpoint_1_node_name",
                    "component_1_flow_rate",
                    "operation_1_type"
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
                "equipment_1_object_type": {
                    "field_name": "Equipment 1 Object Type",
                    "field_type": "a"
                },
                "equipment_1_name": {
                    "field_name": "Equipment 1 Name",
                    "field_type": "a"
                },
                "demand_calculation_1_node_name": {
                    "field_name": "Demand Calculation 1 Node Name",
                    "field_type": "a"
                },
                "setpoint_1_node_name": {
                    "field_name": "Setpoint 1 Node Name",
                    "field_type": "a"
                },
                "component_1_flow_rate": {
                    "field_name": "Component 1 Flow Rate",
                    "field_type": "n"
                },
                "operation_1_type": {
                    "field_name": "Operation 1 Type",
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
                "demand_calculation_2_node_name": {
                    "field_name": "Demand Calculation 2 Node Name",
                    "field_type": "a"
                },
                "setpoint_2_node_name": {
                    "field_name": "Setpoint 2 Node Name",
                    "field_type": "a"
                },
                "component_2_flow_rate": {
                    "field_name": "Component 2 Flow Rate",
                    "field_type": "n"
                },
                "operation_2_type": {
                    "field_name": "Operation 2 Type",
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
                "demand_calculation_3_node_name": {
                    "field_name": "Demand Calculation 3 Node Name",
                    "field_type": "a"
                },
                "setpoint_3_node_name": {
                    "field_name": "Setpoint 3 Node Name",
                    "field_type": "a"
                },
                "component_3_flow_rate": {
                    "field_name": "Component 3 Flow Rate",
                    "field_type": "n"
                },
                "operation_3_type": {
                    "field_name": "Operation 3 Type",
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
                "demand_calculation_4_node_name": {
                    "field_name": "Demand Calculation 4 Node Name",
                    "field_type": "a"
                },
                "setpoint_4_node_name": {
                    "field_name": "Setpoint 4 Node Name",
                    "field_type": "a"
                },
                "component_4_flow_rate": {
                    "field_name": "Component 4 Flow Rate",
                    "field_type": "n"
                },
                "operation_4_type": {
                    "field_name": "Operation 4 Type",
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
                "demand_calculation_5_node_name": {
                    "field_name": "Demand Calculation 5 Node Name",
                    "field_type": "a"
                },
                "setpoint_5_node_name": {
                    "field_name": "Setpoint 5 Node Name",
                    "field_type": "a"
                },
                "component_5_flow_rate": {
                    "field_name": "Component 5 Flow Rate",
                    "field_type": "n"
                },
                "operation_5_type": {
                    "field_name": "Operation 5 Type",
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
                "demand_calculation_6_node_name": {
                    "field_name": "Demand Calculation 6 Node Name",
                    "field_type": "a"
                },
                "setpoint_6_node_name": {
                    "field_name": "Setpoint 6 Node Name",
                    "field_type": "a"
                },
                "component_6_flow_rate": {
                    "field_name": "Component 6 Flow Rate",
                    "field_type": "n"
                },
                "operation_6_type": {
                    "field_name": "Operation 6 Type",
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
                "demand_calculation_7_node_name": {
                    "field_name": "Demand Calculation 7 Node Name",
                    "field_type": "a"
                },
                "setpoint_7_node_name": {
                    "field_name": "Setpoint 7 Node Name",
                    "field_type": "a"
                },
                "component_7_flow_rate": {
                    "field_name": "Component 7 Flow Rate",
                    "field_type": "n"
                },
                "operation_7_type": {
                    "field_name": "Operation 7 Type",
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
                "demand_calculation_8_node_name": {
                    "field_name": "Demand Calculation 8 Node Name",
                    "field_type": "a"
                },
                "setpoint_8_node_name": {
                    "field_name": "Setpoint 8 Node Name",
                    "field_type": "a"
                },
                "component_8_flow_rate": {
                    "field_name": "Component 8 Flow Rate",
                    "field_type": "n"
                },
                "operation_8_type": {
                    "field_name": "Operation 8 Type",
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
                "demand_calculation_9_node_name": {
                    "field_name": "Demand Calculation 9 Node Name",
                    "field_type": "a"
                },
                "setpoint_9_node_name": {
                    "field_name": "Setpoint 9 Node Name",
                    "field_type": "a"
                },
                "component_9_flow_rate": {
                    "field_name": "Component 9 Flow Rate",
                    "field_type": "n"
                },
                "operation_9_type": {
                    "field_name": "Operation 9 Type",
                    "field_type": "a"
                },
                "equipment_10_object_type": {
                    "field_name": "Equipment 10 Object Type",
                    "field_type": "a"
                },
                "equipment_10_name": {
                    "field_name": "Equipment 10 Name",
                    "field_type": "a"
                },
                "demand_calculation_10_node_name": {
                    "field_name": "Demand Calculation 10 Node Name",
                    "field_type": "a"
                },
                "setpoint_10_node_name": {
                    "field_name": "Setpoint 10 Node Name",
                    "field_type": "a"
                },
                "component_10_flow_rate": {
                    "field_name": "Component 10 Flow Rate",
                    "field_type": "n"
                },
                "operation_10_type": {
                    "field_name": "Operation 10 Type",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "equipment_1_object_type",
                "equipment_1_name",
                "demand_calculation_1_node_name",
                "setpoint_1_node_name",
                "component_1_flow_rate",
                "operation_1_type",
                "equipment_2_object_type",
                "equipment_2_name",
                "demand_calculation_2_node_name",
                "setpoint_2_node_name",
                "component_2_flow_rate",
                "operation_2_type",
                "equipment_3_object_type",
                "equipment_3_name",
                "demand_calculation_3_node_name",
                "setpoint_3_node_name",
                "component_3_flow_rate",
                "operation_3_type",
                "equipment_4_object_type",
                "equipment_4_name",
                "demand_calculation_4_node_name",
                "setpoint_4_node_name",
                "component_4_flow_rate",
                "operation_4_type",
                "equipment_5_object_type",
                "equipment_5_name",
                "demand_calculation_5_node_name",
                "setpoint_5_node_name",
                "component_5_flow_rate",
                "operation_5_type",
                "equipment_6_object_type",
                "equipment_6_name",
                "demand_calculation_6_node_name",
                "setpoint_6_node_name",
                "component_6_flow_rate",
                "operation_6_type",
                "equipment_7_object_type",
                "equipment_7_name",
                "demand_calculation_7_node_name",
                "setpoint_7_node_name",
                "component_7_flow_rate",
                "operation_7_type",
                "equipment_8_object_type",
                "equipment_8_name",
                "demand_calculation_8_node_name",
                "setpoint_8_node_name",
                "component_8_flow_rate",
                "operation_8_type",
                "equipment_9_object_type",
                "equipment_9_name",
                "demand_calculation_9_node_name",
                "setpoint_9_node_name",
                "component_9_flow_rate",
                "operation_9_type",
                "equipment_10_object_type",
                "equipment_10_name",
                "demand_calculation_10_node_name",
                "setpoint_10_node_name",
                "component_10_flow_rate",
                "operation_10_type"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "equipment_1_object_type",
                    "equipment_1_name",
                    "demand_calculation_1_node_name",
                    "setpoint_1_node_name",
                    "operation_1_type",
                    "equipment_2_object_type",
                    "equipment_2_name",
                    "demand_calculation_2_node_name",
                    "setpoint_2_node_name",
                    "operation_2_type",
                    "equipment_3_object_type",
                    "equipment_3_name",
                    "demand_calculation_3_node_name",
                    "setpoint_3_node_name",
                    "operation_3_type",
                    "equipment_4_object_type",
                    "equipment_4_name",
                    "demand_calculation_4_node_name",
                    "setpoint_4_node_name",
                    "operation_4_type",
                    "equipment_5_object_type",
                    "equipment_5_name",
                    "demand_calculation_5_node_name",
                    "setpoint_5_node_name",
                    "operation_5_type",
                    "equipment_6_object_type",
                    "equipment_6_name",
                    "demand_calculation_6_node_name",
                    "setpoint_6_node_name",
                    "operation_6_type",
                    "equipment_7_object_type",
                    "equipment_7_name",
                    "demand_calculation_7_node_name",
                    "setpoint_7_node_name",
                    "operation_7_type",
                    "equipment_8_object_type",
                    "equipment_8_name",
                    "demand_calculation_8_node_name",
                    "setpoint_8_node_name",
                    "operation_8_type",
                    "equipment_9_object_type",
                    "equipment_9_name",
                    "demand_calculation_9_node_name",
                    "setpoint_9_node_name",
                    "operation_9_type",
                    "equipment_10_object_type",
                    "equipment_10_name",
                    "demand_calculation_10_node_name",
                    "setpoint_10_node_name",
                    "operation_10_type"
                ]
            },
            "numerics": {
                "fields": [
                    "component_1_flow_rate",
                    "component_2_flow_rate",
                    "component_3_flow_rate",
                    "component_4_flow_rate",
                    "component_5_flow_rate",
                    "component_6_flow_rate",
                    "component_7_flow_rate",
                    "component_8_flow_rate",
                    "component_9_flow_rate",
                    "component_10_flow_rate"
                ]
            }
        },
        "type": "object",
        "memo": "Plant equipment operation scheme for component setpoint operation. Specifies one or pieces of equipment which are controlled to meet the temperature setpoint at the component outlet node.",
        "min_fields": 7.0
    }
}
```
