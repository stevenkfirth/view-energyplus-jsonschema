```
{
    "PlantEquipmentOperation:ThermalEnergyStorage": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "on_peak_schedule": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "charging_availability_schedule": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "non_charging_chilled_water_temperature": {
                        "type": "number",
                        "note": "Single temperature for chiller outlet when not in cooling season or during on-peak cooling (discharge)",
                        "units": "C"
                    },
                    "charging_chilled_water_temperature": {
                        "type": "number",
                        "note": "Single temperature for chiller outlet when off-peak during cooling season (charging)",
                        "units": "C"
                    },
                    "component_1_object_type": {
                        "type": "string",
                        "note": "This field is the type of object and should either be a chiller or some ice storage equipment.",
                        "enum": [
                            "Chiller:Absorption",
                            "Chiller:Absorption:Indirect",
                            "Chiller:CombustionTurbine",
                            "Chiller:ConstantCOP",
                            "Chiller:Electric",
                            "Chiller:Electric:EIR",
                            "Chiller:Electric:ReformulatedEIR",
                            "Chiller:EngineDriven",
                            "ThermalStorage:Ice:Detailed",
                            "ThermalStorage:Ice:Simple"
                        ]
                    },
                    "component_1_name": {
                        "type": "string",
                        "note": "This field is the name of either the chiller or ice storage equipment on the loop.",
                        "data_type": "object_list",
                        "object_list": [
                            "Chillers",
                            "IceThermalStorageEquipment"
                        ]
                    },
                    "component_1_demand_calculation_node_name": {
                        "type": "string",
                        "note": "This field is the name of the inlet node for the component defined in the two previous input fields."
                    },
                    "component_1_setpoint_node_name": {
                        "type": "string",
                        "note": "This field is the name of the outlet node for the component listed above."
                    },
                    "component_1_flow_rate": {
                        "note": "This field is the flow rate for the component listed above.",
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
                    "component_1_operation_type": {
                        "type": "string",
                        "note": "This field is the operation type for the component listed above. For this plant equipment operation scheme, \"Cooling\" should be selected for chiller equipment while ice storage equipment should be defined as \"Dual\".",
                        "enum": [
                            "Cooling",
                            "Dual",
                            "Heating"
                        ]
                    },
                    "component_2_object_type": {
                        "type": "string",
                        "enum": [
                            "Chiller:Absorption",
                            "Chiller:Absorption:Indirect",
                            "Chiller:CombustionTurbine",
                            "Chiller:ConstantCOP",
                            "Chiller:Electric",
                            "Chiller:Electric:EIR",
                            "Chiller:Electric:ReformulatedEIR",
                            "Chiller:EngineDriven",
                            "ThermalStorage:Ice:Detailed",
                            "ThermalStorage:Ice:Simple"
                        ]
                    },
                    "component_2_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "Chillers",
                            "IceThermalStorageEquipment"
                        ]
                    },
                    "component_2_demand_calculation_node_name": {
                        "type": "string"
                    },
                    "component_2_setpoint_node_name": {
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
                    "component_2_operation_type": {
                        "type": "string",
                        "enum": [
                            "Cooling",
                            "Dual",
                            "Heating"
                        ]
                    },
                    "component_3_object_type": {
                        "type": "string",
                        "enum": [
                            "Chiller:Absorption",
                            "Chiller:Absorption:Indirect",
                            "Chiller:CombustionTurbine",
                            "Chiller:ConstantCOP",
                            "Chiller:Electric",
                            "Chiller:Electric:EIR",
                            "Chiller:Electric:ReformulatedEIR",
                            "Chiller:EngineDriven",
                            "ThermalStorage:Ice:Detailed",
                            "ThermalStorage:Ice:Simple"
                        ]
                    },
                    "component_3_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "Chillers",
                            "IceThermalStorageEquipment"
                        ]
                    },
                    "component_3_demand_calculation_node_name": {
                        "type": "string"
                    },
                    "component_3_setpoint_node_name": {
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
                    "component_3_operation_type": {
                        "type": "string",
                        "enum": [
                            "Cooling",
                            "Dual",
                            "Heating"
                        ]
                    },
                    "component_4_object_type": {
                        "type": "string",
                        "enum": [
                            "Chiller:Absorption",
                            "Chiller:Absorption:Indirect",
                            "Chiller:CombustionTurbine",
                            "Chiller:ConstantCOP",
                            "Chiller:Electric",
                            "Chiller:Electric:EIR",
                            "Chiller:Electric:ReformulatedEIR",
                            "Chiller:EngineDriven",
                            "ThermalStorage:Ice:Detailed",
                            "ThermalStorage:Ice:Simple"
                        ]
                    },
                    "component_4_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "Chillers",
                            "IceThermalStorageEquipment"
                        ]
                    },
                    "component_4_demand_calculation_node_name": {
                        "type": "string"
                    },
                    "component_4_setpoint_node_name": {
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
                    "component_4_operation_type": {
                        "type": "string",
                        "enum": [
                            "Cooling",
                            "Dual",
                            "Heating"
                        ]
                    },
                    "component_5_object_type": {
                        "type": "string",
                        "enum": [
                            "Chiller:Absorption",
                            "Chiller:Absorption:Indirect",
                            "Chiller:CombustionTurbine",
                            "Chiller:ConstantCOP",
                            "Chiller:Electric",
                            "Chiller:Electric:EIR",
                            "Chiller:Electric:ReformulatedEIR",
                            "Chiller:EngineDriven",
                            "ThermalStorage:Ice:Detailed",
                            "ThermalStorage:Ice:Simple"
                        ]
                    },
                    "component_5_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "Chillers",
                            "IceThermalStorageEquipment"
                        ]
                    },
                    "component_5_demand_calculation_node_name": {
                        "type": "string"
                    },
                    "component_5_setpoint_node_name": {
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
                    "component_5_operation_type": {
                        "type": "string",
                        "enum": [
                            "Cooling",
                            "Dual",
                            "Heating"
                        ]
                    },
                    "component_6_object_type": {
                        "type": "string",
                        "enum": [
                            "Chiller:Absorption",
                            "Chiller:Absorption:Indirect",
                            "Chiller:CombustionTurbine",
                            "Chiller:ConstantCOP",
                            "Chiller:Electric",
                            "Chiller:Electric:EIR",
                            "Chiller:Electric:ReformulatedEIR",
                            "Chiller:EngineDriven",
                            "ThermalStorage:Ice:Detailed",
                            "ThermalStorage:Ice:Simple"
                        ]
                    },
                    "component_6_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "Chillers",
                            "IceThermalStorageEquipment"
                        ]
                    },
                    "component_6_demand_calculation_node_name": {
                        "type": "string"
                    },
                    "component_6_setpoint_node_name": {
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
                    "component_6_operation_type": {
                        "type": "string",
                        "enum": [
                            "Cooling",
                            "Dual",
                            "Heating"
                        ]
                    },
                    "component_7_object_type": {
                        "type": "string",
                        "enum": [
                            "Chiller:Absorption",
                            "Chiller:Absorption:Indirect",
                            "Chiller:CombustionTurbine",
                            "Chiller:ConstantCOP",
                            "Chiller:Electric",
                            "Chiller:Electric:EIR",
                            "Chiller:Electric:ReformulatedEIR",
                            "Chiller:EngineDriven",
                            "ThermalStorage:Ice:Detailed",
                            "ThermalStorage:Ice:Simple"
                        ]
                    },
                    "component_7_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "Chillers",
                            "IceThermalStorageEquipment"
                        ]
                    },
                    "component_7_demand_calculation_node_name": {
                        "type": "string"
                    },
                    "component_7_setpoint_node_name": {
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
                    "component_7_operation_type": {
                        "type": "string",
                        "enum": [
                            "Cooling",
                            "Dual",
                            "Heating"
                        ]
                    },
                    "component_8_object_type": {
                        "type": "string",
                        "enum": [
                            "Chiller:Absorption",
                            "Chiller:Absorption:Indirect",
                            "Chiller:CombustionTurbine",
                            "Chiller:ConstantCOP",
                            "Chiller:Electric",
                            "Chiller:Electric:EIR",
                            "Chiller:Electric:ReformulatedEIR",
                            "Chiller:EngineDriven",
                            "ThermalStorage:Ice:Detailed",
                            "ThermalStorage:Ice:Simple"
                        ]
                    },
                    "component_8_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "Chillers",
                            "IceThermalStorageEquipment"
                        ]
                    },
                    "component_8_demand_calculation_node_name": {
                        "type": "string"
                    },
                    "component_8_setpoint_node_name": {
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
                    "component_8_operation_type": {
                        "type": "string",
                        "enum": [
                            "Cooling",
                            "Dual",
                            "Heating"
                        ]
                    },
                    "component_9_object_type": {
                        "type": "string",
                        "enum": [
                            "Chiller:Absorption",
                            "Chiller:Absorption:Indirect",
                            "Chiller:CombustionTurbine",
                            "Chiller:ConstantCOP",
                            "Chiller:Electric",
                            "Chiller:Electric:EIR",
                            "Chiller:Electric:ReformulatedEIR",
                            "Chiller:EngineDriven",
                            "ThermalStorage:Ice:Detailed",
                            "ThermalStorage:Ice:Simple"
                        ]
                    },
                    "component_9_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "Chillers",
                            "IceThermalStorageEquipment"
                        ]
                    },
                    "component_9_demand_calculation_node_name": {
                        "type": "string"
                    },
                    "component_9_setpoint_node_name": {
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
                    "component_9_operation_type": {
                        "type": "string",
                        "enum": [
                            "Cooling",
                            "Dual",
                            "Heating"
                        ]
                    },
                    "component_10_object_type": {
                        "type": "string",
                        "enum": [
                            "Chiller:Absorption",
                            "Chiller:Absorption:Indirect",
                            "Chiller:CombustionTurbine",
                            "Chiller:ConstantCOP",
                            "Chiller:Electric",
                            "Chiller:Electric:EIR",
                            "Chiller:Electric:ReformulatedEIR",
                            "Chiller:EngineDriven",
                            "ThermalStorage:Ice:Detailed",
                            "ThermalStorage:Ice:Simple"
                        ]
                    },
                    "component_10_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "Chillers",
                            "IceThermalStorageEquipment"
                        ]
                    },
                    "component_10_demand_calculation_node_name": {
                        "type": "string"
                    },
                    "component_10_setpoint_node_name": {
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
                    "component_10_operation_type": {
                        "type": "string",
                        "enum": [
                            "Cooling",
                            "Dual",
                            "Heating"
                        ]
                    }
                },
                "required": [
                    "on_peak_schedule",
                    "charging_availability_schedule",
                    "non_charging_chilled_water_temperature",
                    "charging_chilled_water_temperature",
                    "component_1_object_type",
                    "component_1_name",
                    "component_1_demand_calculation_node_name",
                    "component_1_setpoint_node_name",
                    "component_1_flow_rate",
                    "component_1_operation_type"
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
                "on_peak_schedule": {
                    "field_name": "On-Peak Schedule",
                    "field_type": "a"
                },
                "charging_availability_schedule": {
                    "field_name": "Charging Availability Schedule",
                    "field_type": "a"
                },
                "non_charging_chilled_water_temperature": {
                    "field_name": "Non-Charging Chilled Water Temperature",
                    "field_type": "n"
                },
                "charging_chilled_water_temperature": {
                    "field_name": "Charging Chilled Water Temperature",
                    "field_type": "n"
                },
                "component_1_object_type": {
                    "field_name": "Component 1 Object Type",
                    "field_type": "a"
                },
                "component_1_name": {
                    "field_name": "Component 1 Name",
                    "field_type": "a"
                },
                "component_1_demand_calculation_node_name": {
                    "field_name": "Component 1 Demand Calculation Node Name",
                    "field_type": "a"
                },
                "component_1_setpoint_node_name": {
                    "field_name": "Component 1 Setpoint Node Name",
                    "field_type": "a"
                },
                "component_1_flow_rate": {
                    "field_name": "Component 1 Flow Rate",
                    "field_type": "n"
                },
                "component_1_operation_type": {
                    "field_name": "Component 1 Operation Type",
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
                "component_2_demand_calculation_node_name": {
                    "field_name": "Component 2 Demand Calculation Node Name",
                    "field_type": "a"
                },
                "component_2_setpoint_node_name": {
                    "field_name": "Component 2 Setpoint Node Name",
                    "field_type": "a"
                },
                "component_2_flow_rate": {
                    "field_name": "Component 2 Flow Rate",
                    "field_type": "n"
                },
                "component_2_operation_type": {
                    "field_name": "Component 2 Operation Type",
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
                "component_3_demand_calculation_node_name": {
                    "field_name": "Component 3 Demand Calculation Node Name",
                    "field_type": "a"
                },
                "component_3_setpoint_node_name": {
                    "field_name": "Component 3 Setpoint Node Name",
                    "field_type": "a"
                },
                "component_3_flow_rate": {
                    "field_name": "Component 3 Flow Rate",
                    "field_type": "n"
                },
                "component_3_operation_type": {
                    "field_name": "Component 3 Operation Type",
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
                "component_4_demand_calculation_node_name": {
                    "field_name": "Component 4 Demand Calculation Node Name",
                    "field_type": "a"
                },
                "component_4_setpoint_node_name": {
                    "field_name": "Component 4 Setpoint Node Name",
                    "field_type": "a"
                },
                "component_4_flow_rate": {
                    "field_name": "Component 4 Flow Rate",
                    "field_type": "n"
                },
                "component_4_operation_type": {
                    "field_name": "Component 4 Operation Type",
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
                "component_5_demand_calculation_node_name": {
                    "field_name": "Component 5 Demand Calculation Node Name",
                    "field_type": "a"
                },
                "component_5_setpoint_node_name": {
                    "field_name": "Component 5 Setpoint Node Name",
                    "field_type": "a"
                },
                "component_5_flow_rate": {
                    "field_name": "Component 5 Flow Rate",
                    "field_type": "n"
                },
                "component_5_operation_type": {
                    "field_name": "Component 5 Operation Type",
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
                "component_6_demand_calculation_node_name": {
                    "field_name": "Component 6 Demand Calculation Node Name",
                    "field_type": "a"
                },
                "component_6_setpoint_node_name": {
                    "field_name": "Component 6 Setpoint Node Name",
                    "field_type": "a"
                },
                "component_6_flow_rate": {
                    "field_name": "Component 6 Flow Rate",
                    "field_type": "n"
                },
                "component_6_operation_type": {
                    "field_name": "Component 6 Operation Type",
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
                "component_7_demand_calculation_node_name": {
                    "field_name": "Component 7 Demand Calculation Node Name",
                    "field_type": "a"
                },
                "component_7_setpoint_node_name": {
                    "field_name": "Component 7 Setpoint Node Name",
                    "field_type": "a"
                },
                "component_7_flow_rate": {
                    "field_name": "Component 7 Flow Rate",
                    "field_type": "n"
                },
                "component_7_operation_type": {
                    "field_name": "Component 7 Operation Type",
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
                "component_8_demand_calculation_node_name": {
                    "field_name": "Component 8 Demand Calculation Node Name",
                    "field_type": "a"
                },
                "component_8_setpoint_node_name": {
                    "field_name": "Component 8 Setpoint Node Name",
                    "field_type": "a"
                },
                "component_8_flow_rate": {
                    "field_name": "Component 8 Flow Rate",
                    "field_type": "n"
                },
                "component_8_operation_type": {
                    "field_name": "Component 8 Operation Type",
                    "field_type": "a"
                },
                "component_9_object_type": {
                    "field_name": "Component 9 Object Type",
                    "field_type": "a"
                },
                "component_9_name": {
                    "field_name": "Component 9 Name",
                    "field_type": "a"
                },
                "component_9_demand_calculation_node_name": {
                    "field_name": "Component 9 Demand Calculation Node Name",
                    "field_type": "a"
                },
                "component_9_setpoint_node_name": {
                    "field_name": "Component 9 Setpoint Node Name",
                    "field_type": "a"
                },
                "component_9_flow_rate": {
                    "field_name": "Component 9 Flow Rate",
                    "field_type": "n"
                },
                "component_9_operation_type": {
                    "field_name": "Component 9 Operation Type",
                    "field_type": "a"
                },
                "component_10_object_type": {
                    "field_name": "Component 10 Object Type",
                    "field_type": "a"
                },
                "component_10_name": {
                    "field_name": "Component 10 Name",
                    "field_type": "a"
                },
                "component_10_demand_calculation_node_name": {
                    "field_name": "Component 10 Demand Calculation Node Name",
                    "field_type": "a"
                },
                "component_10_setpoint_node_name": {
                    "field_name": "Component 10 Setpoint Node Name",
                    "field_type": "a"
                },
                "component_10_flow_rate": {
                    "field_name": "Component 10 Flow Rate",
                    "field_type": "n"
                },
                "component_10_operation_type": {
                    "field_name": "Component 10 Operation Type",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "on_peak_schedule",
                "charging_availability_schedule",
                "non_charging_chilled_water_temperature",
                "charging_chilled_water_temperature",
                "component_1_object_type",
                "component_1_name",
                "component_1_demand_calculation_node_name",
                "component_1_setpoint_node_name",
                "component_1_flow_rate",
                "component_1_operation_type",
                "component_2_object_type",
                "component_2_name",
                "component_2_demand_calculation_node_name",
                "component_2_setpoint_node_name",
                "component_2_flow_rate",
                "component_2_operation_type",
                "component_3_object_type",
                "component_3_name",
                "component_3_demand_calculation_node_name",
                "component_3_setpoint_node_name",
                "component_3_flow_rate",
                "component_3_operation_type",
                "component_4_object_type",
                "component_4_name",
                "component_4_demand_calculation_node_name",
                "component_4_setpoint_node_name",
                "component_4_flow_rate",
                "component_4_operation_type",
                "component_5_object_type",
                "component_5_name",
                "component_5_demand_calculation_node_name",
                "component_5_setpoint_node_name",
                "component_5_flow_rate",
                "component_5_operation_type",
                "component_6_object_type",
                "component_6_name",
                "component_6_demand_calculation_node_name",
                "component_6_setpoint_node_name",
                "component_6_flow_rate",
                "component_6_operation_type",
                "component_7_object_type",
                "component_7_name",
                "component_7_demand_calculation_node_name",
                "component_7_setpoint_node_name",
                "component_7_flow_rate",
                "component_7_operation_type",
                "component_8_object_type",
                "component_8_name",
                "component_8_demand_calculation_node_name",
                "component_8_setpoint_node_name",
                "component_8_flow_rate",
                "component_8_operation_type",
                "component_9_object_type",
                "component_9_name",
                "component_9_demand_calculation_node_name",
                "component_9_setpoint_node_name",
                "component_9_flow_rate",
                "component_9_operation_type",
                "component_10_object_type",
                "component_10_name",
                "component_10_demand_calculation_node_name",
                "component_10_setpoint_node_name",
                "component_10_flow_rate",
                "component_10_operation_type"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "on_peak_schedule",
                    "charging_availability_schedule",
                    "component_1_object_type",
                    "component_1_name",
                    "component_1_demand_calculation_node_name",
                    "component_1_setpoint_node_name",
                    "component_1_operation_type",
                    "component_2_object_type",
                    "component_2_name",
                    "component_2_demand_calculation_node_name",
                    "component_2_setpoint_node_name",
                    "component_2_operation_type",
                    "component_3_object_type",
                    "component_3_name",
                    "component_3_demand_calculation_node_name",
                    "component_3_setpoint_node_name",
                    "component_3_operation_type",
                    "component_4_object_type",
                    "component_4_name",
                    "component_4_demand_calculation_node_name",
                    "component_4_setpoint_node_name",
                    "component_4_operation_type",
                    "component_5_object_type",
                    "component_5_name",
                    "component_5_demand_calculation_node_name",
                    "component_5_setpoint_node_name",
                    "component_5_operation_type",
                    "component_6_object_type",
                    "component_6_name",
                    "component_6_demand_calculation_node_name",
                    "component_6_setpoint_node_name",
                    "component_6_operation_type",
                    "component_7_object_type",
                    "component_7_name",
                    "component_7_demand_calculation_node_name",
                    "component_7_setpoint_node_name",
                    "component_7_operation_type",
                    "component_8_object_type",
                    "component_8_name",
                    "component_8_demand_calculation_node_name",
                    "component_8_setpoint_node_name",
                    "component_8_operation_type",
                    "component_9_object_type",
                    "component_9_name",
                    "component_9_demand_calculation_node_name",
                    "component_9_setpoint_node_name",
                    "component_9_operation_type",
                    "component_10_object_type",
                    "component_10_name",
                    "component_10_demand_calculation_node_name",
                    "component_10_setpoint_node_name",
                    "component_10_operation_type"
                ]
            },
            "numerics": {
                "fields": [
                    "non_charging_chilled_water_temperature",
                    "charging_chilled_water_temperature",
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
        "memo": "Plant equipment operation scheme for simpler input to control thermal (ice) energy storage systems. It replaces a host of setpoint managers with simple, single input values. For more complex controls, use the ComponentSetpoint scheme.",
        "min_fields": 7.0
    }
}
```
