```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "fluid_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "Steam",
                        "UserDefinedFluidType",
                        "Water"
                    ],
                    "default": "Water"
                },
                "user_defined_fluid_type": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "FluidAndGlycolNames"
                    ],
                    "note": "This field is only required when Fluid Type is UserDefinedFluidType"
                },
                "plant_equipment_operation_scheme_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "PlantOperationSchemes"
                    ]
                },
                "loop_temperature_setpoint_node_name": {
                    "type": "string"
                },
                "maximum_loop_temperature": {
                    "type": "number",
                    "units": "C"
                },
                "minimum_loop_temperature": {
                    "type": "number",
                    "units": "C"
                },
                "maximum_loop_flow_rate": {
                    "units": "m3/s",
                    "ip-units": "gal/min",
                    "anyOf": [
                        {
                            "type": "number",
                            "minimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "Autosize"
                            ]
                        }
                    ]
                },
                "minimum_loop_flow_rate": {
                    "type": "number",
                    "units": "m3/s",
                    "default": 0.0,
                    "ip-units": "gal/min"
                },
                "plant_loop_volume": {
                    "units": "m3",
                    "default": "Autocalculate",
                    "ip-units": "gal",
                    "anyOf": [
                        {
                            "type": "number",
                            "minimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "",
                                "Autocalculate"
                            ]
                        }
                    ]
                },
                "plant_side_inlet_node_name": {
                    "type": "string"
                },
                "plant_side_outlet_node_name": {
                    "type": "string"
                },
                "plant_side_branch_list_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "BranchLists"
                    ]
                },
                "plant_side_connector_list_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ConnectorLists"
                    ]
                },
                "demand_side_inlet_node_name": {
                    "type": "string"
                },
                "demand_side_outlet_node_name": {
                    "type": "string"
                },
                "demand_side_branch_list_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "BranchLists"
                    ]
                },
                "demand_side_connector_list_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ConnectorLists"
                    ]
                },
                "load_distribution_scheme": {
                    "type": "string",
                    "enum": [
                        "",
                        "Optimal",
                        "SequentialLoad",
                        "SequentialUniformPLR",
                        "UniformLoad",
                        "UniformPLR"
                    ],
                    "default": "SequentialLoad"
                },
                "availability_manager_list_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "SystemAvailabilityManagerLists"
                    ]
                },
                "plant_loop_demand_calculation_scheme": {
                    "type": "string",
                    "enum": [
                        "",
                        "DualSetpointDeadband",
                        "SingleSetpoint"
                    ],
                    "default": "SingleSetpoint"
                },
                "common_pipe_simulation": {
                    "type": "string",
                    "note": "Specifies a primary-secondary loop configuration. The plant side is the primary loop, and the demand side is the secondary loop. A secondary supply pump is required on the demand side. None = Primary-only, no secondary simulation CommonPipe = Primary-secondary with no temperature control at primary-secondary interface TwoWayCommonPipe = Primary-secondary with control of secondary supply temperature or primary return temperature (requires a setpoint be placed on the plant side or demand side inlet node).",
                    "enum": [
                        "",
                        "CommonPipe",
                        "None",
                        "TwoWayCommonPipe"
                    ],
                    "default": "None"
                },
                "pressure_simulation_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "LoopFlowCorrection",
                        "None",
                        "PumpPowerCorrection"
                    ],
                    "default": "None"
                },
                "loop_circulation_time": {
                    "type": "number",
                    "note": "This field is only used to autocalulate the Plant Loop Volume. Loop Volume = Loop Circulation Time * Maximum Loop Flow Rate",
                    "units": "minutes",
                    "minimum": 0.0,
                    "default": 2.0
                }
            },
            "required": [
                "plant_equipment_operation_scheme_name",
                "loop_temperature_setpoint_node_name",
                "maximum_loop_temperature",
                "minimum_loop_temperature",
                "maximum_loop_flow_rate",
                "plant_side_inlet_node_name",
                "plant_side_outlet_node_name",
                "plant_side_branch_list_name",
                "demand_side_inlet_node_name",
                "demand_side_outlet_node_name",
                "demand_side_branch_list_name"
            ]
        }
    },
    "group": "Plant-Condenser Loops",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "PlantLoops"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "fluid_type": {
                "field_name": "Fluid Type",
                "field_type": "a"
            },
            "user_defined_fluid_type": {
                "field_name": "User Defined Fluid Type",
                "field_type": "a"
            },
            "plant_equipment_operation_scheme_name": {
                "field_name": "Plant Equipment Operation Scheme Name",
                "field_type": "a"
            },
            "loop_temperature_setpoint_node_name": {
                "field_name": "Loop Temperature Setpoint Node Name",
                "field_type": "a"
            },
            "maximum_loop_temperature": {
                "field_name": "Maximum Loop Temperature",
                "field_type": "n"
            },
            "minimum_loop_temperature": {
                "field_name": "Minimum Loop Temperature",
                "field_type": "n"
            },
            "maximum_loop_flow_rate": {
                "field_name": "Maximum Loop Flow Rate",
                "field_type": "n"
            },
            "minimum_loop_flow_rate": {
                "field_name": "Minimum Loop Flow Rate",
                "field_type": "n"
            },
            "plant_loop_volume": {
                "field_name": "Plant Loop Volume",
                "field_type": "n"
            },
            "plant_side_inlet_node_name": {
                "field_name": "Plant Side Inlet Node Name",
                "field_type": "a"
            },
            "plant_side_outlet_node_name": {
                "field_name": "Plant Side Outlet Node Name",
                "field_type": "a"
            },
            "plant_side_branch_list_name": {
                "field_name": "Plant Side Branch List Name",
                "field_type": "a"
            },
            "plant_side_connector_list_name": {
                "field_name": "Plant Side Connector List Name",
                "field_type": "a"
            },
            "demand_side_inlet_node_name": {
                "field_name": "Demand Side Inlet Node Name",
                "field_type": "a"
            },
            "demand_side_outlet_node_name": {
                "field_name": "Demand Side Outlet Node Name",
                "field_type": "a"
            },
            "demand_side_branch_list_name": {
                "field_name": "Demand Side Branch List Name",
                "field_type": "a"
            },
            "demand_side_connector_list_name": {
                "field_name": "Demand Side Connector List Name",
                "field_type": "a"
            },
            "load_distribution_scheme": {
                "field_name": "Load Distribution Scheme",
                "field_type": "a"
            },
            "availability_manager_list_name": {
                "field_name": "Availability Manager List Name",
                "field_type": "a"
            },
            "plant_loop_demand_calculation_scheme": {
                "field_name": "Plant Loop Demand Calculation Scheme",
                "field_type": "a"
            },
            "common_pipe_simulation": {
                "field_name": "Common Pipe Simulation",
                "field_type": "a"
            },
            "pressure_simulation_type": {
                "field_name": "Pressure Simulation Type",
                "field_type": "a"
            },
            "loop_circulation_time": {
                "field_name": "Loop Circulation Time",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "fluid_type",
            "user_defined_fluid_type",
            "plant_equipment_operation_scheme_name",
            "loop_temperature_setpoint_node_name",
            "maximum_loop_temperature",
            "minimum_loop_temperature",
            "maximum_loop_flow_rate",
            "minimum_loop_flow_rate",
            "plant_loop_volume",
            "plant_side_inlet_node_name",
            "plant_side_outlet_node_name",
            "plant_side_branch_list_name",
            "plant_side_connector_list_name",
            "demand_side_inlet_node_name",
            "demand_side_outlet_node_name",
            "demand_side_branch_list_name",
            "demand_side_connector_list_name",
            "load_distribution_scheme",
            "availability_manager_list_name",
            "plant_loop_demand_calculation_scheme",
            "common_pipe_simulation",
            "pressure_simulation_type",
            "loop_circulation_time"
        ],
        "alphas": {
            "fields": [
                "name",
                "fluid_type",
                "user_defined_fluid_type",
                "plant_equipment_operation_scheme_name",
                "loop_temperature_setpoint_node_name",
                "plant_side_inlet_node_name",
                "plant_side_outlet_node_name",
                "plant_side_branch_list_name",
                "plant_side_connector_list_name",
                "demand_side_inlet_node_name",
                "demand_side_outlet_node_name",
                "demand_side_branch_list_name",
                "demand_side_connector_list_name",
                "load_distribution_scheme",
                "availability_manager_list_name",
                "plant_loop_demand_calculation_scheme",
                "common_pipe_simulation",
                "pressure_simulation_type"
            ]
        },
        "numerics": {
            "fields": [
                "maximum_loop_temperature",
                "minimum_loop_temperature",
                "maximum_loop_flow_rate",
                "minimum_loop_flow_rate",
                "plant_loop_volume",
                "loop_circulation_time"
            ]
        }
    },
    "type": "object",
    "memo": "Defines a central plant loop.",
    "min_fields": 18.0
}
```
