```
{
    "ZoneHVAC:ForcedAir:UserDefined": {
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
                    "primary_air_inlet_node_name": {
                        "type": "string",
                        "note": "Air inlet node for the unit must be a zone air exhaust Node."
                    },
                    "primary_air_outlet_node_name": {
                        "type": "string",
                        "note": "Air outlet node for the unit must be a zone air inlet node."
                    },
                    "secondary_air_inlet_node_name": {
                        "type": "string",
                        "note": "Inlet air used for heat rejection or air source"
                    },
                    "secondary_air_outlet_node_name": {
                        "type": "string",
                        "note": "Outlet air used for heat rejection or air source"
                    },
                    "number_of_plant_loop_connections": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 3.0
                    },
                    "plant_connection_1_inlet_node_name": {
                        "type": "string"
                    },
                    "plant_connection_1_outlet_node_name": {
                        "type": "string"
                    },
                    "plant_connection_2_inlet_node_name": {
                        "type": "string"
                    },
                    "plant_connection_2_outlet_node_name": {
                        "type": "string"
                    },
                    "plant_connection_3_inlet_node_name": {
                        "type": "string"
                    },
                    "plant_connection_3_outlet_node_name": {
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
                    "primary_air_inlet_node_name",
                    "primary_air_outlet_node_name",
                    "number_of_plant_loop_connections"
                ]
            }
        },
        "group": "User Defined HVAC and Plant Component Models",
        "name": {
            "type": "string",
            "is_required": true,
            "reference-class-name": [
                "validBranchEquipmentTypes"
            ],
            "reference": [
                "ZoneEquipmentNames",
                "validBranchEquipmentNames"
            ],
            "note": "This is the name of the zone unit"
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
                "primary_air_inlet_node_name": {
                    "field_name": "Primary Air Inlet Node Name",
                    "field_type": "a"
                },
                "primary_air_outlet_node_name": {
                    "field_name": "Primary Air Outlet Node Name",
                    "field_type": "a"
                },
                "secondary_air_inlet_node_name": {
                    "field_name": "Secondary Air Inlet Node Name",
                    "field_type": "a"
                },
                "secondary_air_outlet_node_name": {
                    "field_name": "Secondary Air Outlet Node Name",
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
                "plant_connection_2_inlet_node_name": {
                    "field_name": "Plant Connection 2 Inlet Node Name",
                    "field_type": "a"
                },
                "plant_connection_2_outlet_node_name": {
                    "field_name": "Plant Connection 2 Outlet Node Name",
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
                "primary_air_inlet_node_name",
                "primary_air_outlet_node_name",
                "secondary_air_inlet_node_name",
                "secondary_air_outlet_node_name",
                "number_of_plant_loop_connections",
                "plant_connection_1_inlet_node_name",
                "plant_connection_1_outlet_node_name",
                "plant_connection_2_inlet_node_name",
                "plant_connection_2_outlet_node_name",
                "plant_connection_3_inlet_node_name",
                "plant_connection_3_outlet_node_name",
                "supply_inlet_water_storage_tank_name",
                "collection_outlet_water_storage_tank_name",
                "ambient_zone_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "overall_model_simulation_program_calling_manager_name",
                    "model_setup_and_sizing_program_calling_manager_name",
                    "primary_air_inlet_node_name",
                    "primary_air_outlet_node_name",
                    "secondary_air_inlet_node_name",
                    "secondary_air_outlet_node_name",
                    "plant_connection_1_inlet_node_name",
                    "plant_connection_1_outlet_node_name",
                    "plant_connection_2_inlet_node_name",
                    "plant_connection_2_outlet_node_name",
                    "plant_connection_3_inlet_node_name",
                    "plant_connection_3_outlet_node_name",
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
        "memo": "Defines a generic zone air unit for custom modeling using Energy Management System or External Interface",
        "min_fields": 8.0
    }
}
```
