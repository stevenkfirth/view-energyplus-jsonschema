```
{
    "Coil:UserDefined": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "overall_model_simulation_program_calling_manager_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ProgramNames"
                        ]
                    },
                    "model_setup_and_sizing_program_calling_manager_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ProgramNames"
                        ]
                    },
                    "number_of_air_connections": {
                        "type": "number",
                        "minimum": 1.0,
                        "maximum": 2.0
                    },
                    "air_connection_1_inlet_node_name": {
                        "type": "string",
                        "note": "Inlet air for primary air stream"
                    },
                    "air_connection_1_outlet_node_name": {
                        "type": "string",
                        "note": "Outlet air for primary air stream"
                    },
                    "air_connection_2_inlet_node_name": {
                        "type": "string",
                        "note": "Inlet air for secondary air stream"
                    },
                    "air_connection_2_outlet_node_name": {
                        "type": "string",
                        "note": "Outlet air for secondary air stream"
                    },
                    "plant_connection_is_used": {
                        "type": "string",
                        "enum": [
                            "No",
                            "Yes"
                        ]
                    },
                    "plant_connection_inlet_node_name": {
                        "type": "string"
                    },
                    "plant_connection_outlet_node_name": {
                        "type": "string"
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
                    "model_setup_and_sizing_program_calling_manager_name",
                    "number_of_air_connections",
                    "air_connection_1_inlet_node_name",
                    "air_connection_1_outlet_node_name"
                ]
            }
        },
        "group": "User Defined HVAC and Plant Component Models",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "UserDefinedCoil",
                "validBranchEquipmentNames",
                "validOASysEquipmentNames"
            ],
            "note": "This is the name of the coil",
            "reference-class-name": [
                "validBranchEquipmentTypes",
                "validOASysEquipmentTypes"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "overall_model_simulation_program_calling_manager_name": {
                    "field_name": "Overall Model Simulation Program Calling Manager Name",
                    "field_type": "a"
                },
                "model_setup_and_sizing_program_calling_manager_name": {
                    "field_name": "Model Setup and Sizing Program Calling Manager Name",
                    "field_type": "a"
                },
                "number_of_air_connections": {
                    "field_name": "Number of Air Connections",
                    "field_type": "n"
                },
                "air_connection_1_inlet_node_name": {
                    "field_name": "Air Connection 1 Inlet Node Name",
                    "field_type": "a"
                },
                "air_connection_1_outlet_node_name": {
                    "field_name": "Air Connection 1 Outlet Node Name",
                    "field_type": "a"
                },
                "air_connection_2_inlet_node_name": {
                    "field_name": "Air Connection 2 Inlet Node Name",
                    "field_type": "a"
                },
                "air_connection_2_outlet_node_name": {
                    "field_name": "Air Connection 2 Outlet Node Name",
                    "field_type": "a"
                },
                "plant_connection_is_used": {
                    "field_name": "Plant Connection is Used",
                    "field_type": "a"
                },
                "plant_connection_inlet_node_name": {
                    "field_name": "Plant Connection Inlet Node Name",
                    "field_type": "a"
                },
                "plant_connection_outlet_node_name": {
                    "field_name": "Plant Connection Outlet Node Name",
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
                "overall_model_simulation_program_calling_manager_name",
                "model_setup_and_sizing_program_calling_manager_name",
                "number_of_air_connections",
                "air_connection_1_inlet_node_name",
                "air_connection_1_outlet_node_name",
                "air_connection_2_inlet_node_name",
                "air_connection_2_outlet_node_name",
                "plant_connection_is_used",
                "plant_connection_inlet_node_name",
                "plant_connection_outlet_node_name",
                "supply_inlet_water_storage_tank_name",
                "collection_outlet_water_storage_tank_name",
                "ambient_zone_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "overall_model_simulation_program_calling_manager_name",
                    "model_setup_and_sizing_program_calling_manager_name",
                    "air_connection_1_inlet_node_name",
                    "air_connection_1_outlet_node_name",
                    "air_connection_2_inlet_node_name",
                    "air_connection_2_outlet_node_name",
                    "plant_connection_is_used",
                    "plant_connection_inlet_node_name",
                    "plant_connection_outlet_node_name",
                    "supply_inlet_water_storage_tank_name",
                    "collection_outlet_water_storage_tank_name",
                    "ambient_zone_name"
                ]
            },
            "numerics": {
                "fields": [
                    "number_of_air_connections"
                ]
            }
        },
        "type": "object",
        "memo": "Defines a generic air system component for custom modeling using Energy Management System or External Interface",
        "min_fields": 9.0
    }
}
```
