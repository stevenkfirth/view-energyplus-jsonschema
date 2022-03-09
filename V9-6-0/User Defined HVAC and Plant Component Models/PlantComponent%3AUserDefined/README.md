```
{
    "PlantComponent:UserDefined": {
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
                    "number_of_plant_loop_connections": {
                        "type": "number",
                        "minimum": 1.0,
                        "maximum": 4.0
                    },
                    "plant_connection_1_inlet_node_name": {
                        "type": "string"
                    },
                    "plant_connection_1_outlet_node_name": {
                        "type": "string"
                    },
                    "plant_connection_1_loading_mode": {
                        "type": "string",
                        "enum": [
                            "DemandsLoad",
                            "MeetsLoadWithNominalCapacity",
                            "MeetsLoadWithNominalCapacityHiOutLimit",
                            "MeetsLoadWithNominalCapacityLowOutLimit",
                            "MeetsLoadWithPassiveCapacity"
                        ]
                    },
                    "plant_connection_1_loop_flow_request_mode": {
                        "type": "string",
                        "enum": [
                            "NeedsFlowAndTurnsLoopOn",
                            "NeedsFlowIfLoopOn",
                            "ReceivesWhateverFlowAvailable"
                        ]
                    },
                    "plant_connection_1_initialization_program_calling_manager_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ProgramNames"
                        ]
                    },
                    "plant_connection_1_simulation_program_calling_manager_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ProgramNames"
                        ]
                    },
                    "plant_connection_2_inlet_node_name": {
                        "type": "string"
                    },
                    "plant_connection_2_outlet_node_name": {
                        "type": "string"
                    },
                    "plant_connection_2_loading_mode": {
                        "type": "string",
                        "enum": [
                            "DemandsLoad",
                            "MeetLoadWithNominalCapacity",
                            "MeetLoadWithNominalCapacityHiOutLimit",
                            "MeetLoadWithNominalCapacityLowOutLimit",
                            "MeetLoadWithPassiveCapacity"
                        ]
                    },
                    "plant_connection_2_loop_flow_request_mode": {
                        "type": "string",
                        "enum": [
                            "NeedsFlowAndTurnsLoopOn",
                            "NeedsFlowIfLoopOn",
                            "ReceivesWhateverFlowAvailable"
                        ]
                    },
                    "plant_connection_2_initialization_program_calling_manager_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ProgramNames"
                        ]
                    },
                    "plant_connection_2_simulation_program_calling_manager_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ProgramNames"
                        ]
                    },
                    "plant_connection_3_inlet_node_name": {
                        "type": "string"
                    },
                    "plant_connection_3_outlet_node_name": {
                        "type": "string"
                    },
                    "plant_connection_3_loading_mode": {
                        "type": "string",
                        "enum": [
                            "DemandsLoad",
                            "MeetLoadWithNominalCapacity",
                            "MeetLoadWithNominalCapacityHiOutLimit",
                            "MeetLoadWithNominalCapacityLowOutLimit",
                            "MeetLoadWithPassiveCapacity"
                        ]
                    },
                    "plant_connection_3_loop_flow_request_mode": {
                        "type": "string",
                        "enum": [
                            "NeedsFlowAndTurnsLoopOn",
                            "NeedsFlowIfLoopOn",
                            "ReceivesWhateverFlowAvailable"
                        ]
                    },
                    "plant_connection_3_initialization_program_calling_manager_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ProgramNames"
                        ]
                    },
                    "plant_connection_3_simulation_program_calling_manager_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ProgramNames"
                        ]
                    },
                    "plant_connection_4_inlet_node_name": {
                        "type": "string"
                    },
                    "plant_connection_4_outlet_node_name": {
                        "type": "string"
                    },
                    "plant_connection_4_loading_mode": {
                        "type": "string",
                        "enum": [
                            "DemandsLoad",
                            "MeetLoadWithNominalCapacity",
                            "MeetLoadWithNominalCapacityHiOutLimit",
                            "MeetLoadWithNominalCapacityLowOutLimit",
                            "MeetLoadWithPassiveCapacity"
                        ]
                    },
                    "plant_connection_4_loop_flow_request_mode": {
                        "type": "string",
                        "enum": [
                            "NeedsFlowAndTurnsLoopOn",
                            "NeedsFlowIfLoopOn",
                            "ReceivesWhateverFlowAvailable"
                        ]
                    },
                    "plant_connection_4_initialization_program_calling_manager_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ProgramNames"
                        ]
                    },
                    "plant_connection_4_simulation_program_calling_manager_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ProgramNames"
                        ]
                    },
                    "air_connection_inlet_node_name": {
                        "type": "string",
                        "note": "Inlet air used for heat rejection or air source"
                    },
                    "air_connection_outlet_node_name": {
                        "type": "string",
                        "note": "Outlet air used for heat rejection or air source"
                    },
                    "supply_inlet_water_storage_tank_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "WaterStorageTankNames"
                        ],
                        "note": "Water use storage tank for alternate source of water consumed by device"
                    },
                    "collection_outlet_water_storage_tank_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "WaterStorageTankNames"
                        ],
                        "note": "Water use storage tank for collection of condensate by device"
                    },
                    "ambient_zone_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ],
                        "note": "Used for modeling device losses to surrounding zone"
                    }
                },
                "required": [
                    "number_of_plant_loop_connections",
                    "plant_connection_1_inlet_node_name",
                    "plant_connection_1_outlet_node_name",
                    "plant_connection_1_loading_mode",
                    "plant_connection_1_loop_flow_request_mode"
                ]
            }
        },
        "group": "User Defined HVAC and Plant Component Models",
        "name": {
            "type": "string",
            "is_required": true,
            "note": "This is the name of the plant component",
            "reference-class-name": [
                "validBranchEquipmentTypes",
                "validCondenserEquipmentTypes",
                "validPlantEquipmentTypes"
            ],
            "reference": [
                "validBranchEquipmentNames",
                "validCondenserEquipmentNames",
                "validPlantEquipmentNames"
            ]
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
                "number_of_plant_loop_connections": {
                    "field_name": "Number of Plant Loop Connections",
                    "field_type": "n"
                },
                "plant_connection_1_inlet_node_name": {
                    "field_name": "Plant Connection 1 Inlet Node Name",
                    "field_type": "a"
                },
                "plant_connection_1_outlet_node_name": {
                    "field_name": "Plant Connection 1 Outlet Node Name",
                    "field_type": "a"
                },
                "plant_connection_1_loading_mode": {
                    "field_name": "Plant Connection 1 Loading Mode",
                    "field_type": "a"
                },
                "plant_connection_1_loop_flow_request_mode": {
                    "field_name": "Plant Connection 1 Loop Flow Request Mode",
                    "field_type": "a"
                },
                "plant_connection_1_initialization_program_calling_manager_name": {
                    "field_name": "Plant Connection 1 Initialization Program Calling Manager Name",
                    "field_type": "a"
                },
                "plant_connection_1_simulation_program_calling_manager_name": {
                    "field_name": "Plant Connection 1 Simulation Program Calling Manager Name",
                    "field_type": "a"
                },
                "plant_connection_2_inlet_node_name": {
                    "field_name": "Plant Connection 2 Inlet Node Name",
                    "field_type": "a"
                },
                "plant_connection_2_outlet_node_name": {
                    "field_name": "Plant Connection 2 Outlet Node Name",
                    "field_type": "a"
                },
                "plant_connection_2_loading_mode": {
                    "field_name": "Plant Connection 2 Loading Mode",
                    "field_type": "a"
                },
                "plant_connection_2_loop_flow_request_mode": {
                    "field_name": "Plant Connection 2 Loop Flow Request Mode",
                    "field_type": "a"
                },
                "plant_connection_2_initialization_program_calling_manager_name": {
                    "field_name": "Plant Connection 2 Initialization Program Calling Manager Name",
                    "field_type": "a"
                },
                "plant_connection_2_simulation_program_calling_manager_name": {
                    "field_name": "Plant Connection 2 Simulation Program Calling Manager Name",
                    "field_type": "a"
                },
                "plant_connection_3_inlet_node_name": {
                    "field_name": "Plant Connection 3 Inlet Node Name",
                    "field_type": "a"
                },
                "plant_connection_3_outlet_node_name": {
                    "field_name": "Plant Connection 3 Outlet Node Name",
                    "field_type": "a"
                },
                "plant_connection_3_loading_mode": {
                    "field_name": "Plant Connection 3 Loading Mode",
                    "field_type": "a"
                },
                "plant_connection_3_loop_flow_request_mode": {
                    "field_name": "Plant Connection 3 Loop Flow Request Mode",
                    "field_type": "a"
                },
                "plant_connection_3_initialization_program_calling_manager_name": {
                    "field_name": "Plant Connection 3 Initialization Program Calling Manager Name",
                    "field_type": "a"
                },
                "plant_connection_3_simulation_program_calling_manager_name": {
                    "field_name": "Plant Connection 3 Simulation Program Calling Manager Name",
                    "field_type": "a"
                },
                "plant_connection_4_inlet_node_name": {
                    "field_name": "Plant Connection 4 Inlet Node Name",
                    "field_type": "a"
                },
                "plant_connection_4_outlet_node_name": {
                    "field_name": "Plant Connection 4 Outlet Node Name",
                    "field_type": "a"
                },
                "plant_connection_4_loading_mode": {
                    "field_name": "Plant Connection 4 Loading Mode",
                    "field_type": "a"
                },
                "plant_connection_4_loop_flow_request_mode": {
                    "field_name": "Plant Connection 4 Loop Flow Request Mode",
                    "field_type": "a"
                },
                "plant_connection_4_initialization_program_calling_manager_name": {
                    "field_name": "Plant Connection 4 Initialization Program Calling Manager Name",
                    "field_type": "a"
                },
                "plant_connection_4_simulation_program_calling_manager_name": {
                    "field_name": "Plant Connection 4 Simulation Program Calling Manager Name",
                    "field_type": "a"
                },
                "air_connection_inlet_node_name": {
                    "field_name": "Air Connection Inlet Node Name",
                    "field_type": "a"
                },
                "air_connection_outlet_node_name": {
                    "field_name": "Air Connection Outlet Node Name",
                    "field_type": "a"
                },
                "supply_inlet_water_storage_tank_name": {
                    "field_name": "Supply Inlet Water Storage Tank Name",
                    "field_type": "a"
                },
                "collection_outlet_water_storage_tank_name": {
                    "field_name": "Collection Outlet Water Storage Tank Name",
                    "field_type": "a"
                },
                "ambient_zone_name": {
                    "field_name": "Ambient Zone Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "main_model_program_calling_manager_name",
                "number_of_plant_loop_connections",
                "plant_connection_1_inlet_node_name",
                "plant_connection_1_outlet_node_name",
                "plant_connection_1_loading_mode",
                "plant_connection_1_loop_flow_request_mode",
                "plant_connection_1_initialization_program_calling_manager_name",
                "plant_connection_1_simulation_program_calling_manager_name",
                "plant_connection_2_inlet_node_name",
                "plant_connection_2_outlet_node_name",
                "plant_connection_2_loading_mode",
                "plant_connection_2_loop_flow_request_mode",
                "plant_connection_2_initialization_program_calling_manager_name",
                "plant_connection_2_simulation_program_calling_manager_name",
                "plant_connection_3_inlet_node_name",
                "plant_connection_3_outlet_node_name",
                "plant_connection_3_loading_mode",
                "plant_connection_3_loop_flow_request_mode",
                "plant_connection_3_initialization_program_calling_manager_name",
                "plant_connection_3_simulation_program_calling_manager_name",
                "plant_connection_4_inlet_node_name",
                "plant_connection_4_outlet_node_name",
                "plant_connection_4_loading_mode",
                "plant_connection_4_loop_flow_request_mode",
                "plant_connection_4_initialization_program_calling_manager_name",
                "plant_connection_4_simulation_program_calling_manager_name",
                "air_connection_inlet_node_name",
                "air_connection_outlet_node_name",
                "supply_inlet_water_storage_tank_name",
                "collection_outlet_water_storage_tank_name",
                "ambient_zone_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "main_model_program_calling_manager_name",
                    "plant_connection_1_inlet_node_name",
                    "plant_connection_1_outlet_node_name",
                    "plant_connection_1_loading_mode",
                    "plant_connection_1_loop_flow_request_mode",
                    "plant_connection_1_initialization_program_calling_manager_name",
                    "plant_connection_1_simulation_program_calling_manager_name",
                    "plant_connection_2_inlet_node_name",
                    "plant_connection_2_outlet_node_name",
                    "plant_connection_2_loading_mode",
                    "plant_connection_2_loop_flow_request_mode",
                    "plant_connection_2_initialization_program_calling_manager_name",
                    "plant_connection_2_simulation_program_calling_manager_name",
                    "plant_connection_3_inlet_node_name",
                    "plant_connection_3_outlet_node_name",
                    "plant_connection_3_loading_mode",
                    "plant_connection_3_loop_flow_request_mode",
                    "plant_connection_3_initialization_program_calling_manager_name",
                    "plant_connection_3_simulation_program_calling_manager_name",
                    "plant_connection_4_inlet_node_name",
                    "plant_connection_4_outlet_node_name",
                    "plant_connection_4_loading_mode",
                    "plant_connection_4_loop_flow_request_mode",
                    "plant_connection_4_initialization_program_calling_manager_name",
                    "plant_connection_4_simulation_program_calling_manager_name",
                    "air_connection_inlet_node_name",
                    "air_connection_outlet_node_name",
                    "supply_inlet_water_storage_tank_name",
                    "collection_outlet_water_storage_tank_name",
                    "ambient_zone_name"
                ]
            },
            "numerics": {
                "fields": [
                    "number_of_plant_loop_connections"
                ]
            }
        },
        "type": "object",
        "memo": "Defines a generic plant component for custom modeling using Energy Management System or External Interface",
        "min_fields": 9.0
    }
}
```
