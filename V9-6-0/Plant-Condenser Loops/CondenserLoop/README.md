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
                "condenser_equipment_operation_scheme_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "CondenserOperationSchemes"
                    ]
                },
                "condenser_loop_temperature_setpoint_node_name": {
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
                            "exclusiveMinimum": 0.0
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
                "condenser_loop_volume": {
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
                "condenser_side_inlet_node_name": {
                    "type": "string"
                },
                "condenser_side_outlet_node_name": {
                    "type": "string"
                },
                "condenser_side_branch_list_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "BranchLists"
                    ]
                },
                "condenser_side_connector_list_name": {
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
                "condenser_demand_side_branch_list_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "BranchLists"
                    ]
                },
                "condenser_demand_side_connector_list_name": {
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
                    "note": "This field is only used to autocalulate the Condenser Loop Volume. Loop Volume = Loop Circulation Time * Maximum Loop Flow Rate",
                    "units": "minutes",
                    "minimum": 0.0,
                    "default": 2.0
                }
            },
            "required": [
                "condenser_equipment_operation_scheme_name",
                "condenser_loop_temperature_setpoint_node_name",
                "maximum_loop_temperature",
                "minimum_loop_temperature",
                "maximum_loop_flow_rate",
                "condenser_side_inlet_node_name",
                "condenser_side_outlet_node_name",
                "condenser_side_branch_list_name",
                "condenser_side_connector_list_name",
                "demand_side_inlet_node_name",
                "demand_side_outlet_node_name",
                "condenser_demand_side_branch_list_name",
                "condenser_demand_side_connector_list_name"
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
            "condenser_equipment_operation_scheme_name": {
                "field_name": "Condenser Equipment Operation Scheme Name",
                "field_type": "a"
            },
            "condenser_loop_temperature_setpoint_node_name": {
                "field_name": "Condenser Loop Temperature Setpoint Node Name",
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
            "condenser_loop_volume": {
                "field_name": "Condenser Loop Volume",
                "field_type": "n"
            },
            "condenser_side_inlet_node_name": {
                "field_name": "Condenser Side Inlet Node Name",
                "field_type": "a"
            },
            "condenser_side_outlet_node_name": {
                "field_name": "Condenser Side Outlet Node Name",
                "field_type": "a"
            },
            "condenser_side_branch_list_name": {
                "field_name": "Condenser Side Branch List Name",
                "field_type": "a"
            },
            "condenser_side_connector_list_name": {
                "field_name": "Condenser Side Connector List Name",
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
            "condenser_demand_side_branch_list_name": {
                "field_name": "Condenser Demand Side Branch List Name",
                "field_type": "a"
            },
            "condenser_demand_side_connector_list_name": {
                "field_name": "Condenser Demand Side Connector List Name",
                "field_type": "a"
            },
            "load_distribution_scheme": {
                "field_name": "Load Distribution Scheme",
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
            "condenser_equipment_operation_scheme_name",
            "condenser_loop_temperature_setpoint_node_name",
            "maximum_loop_temperature",
            "minimum_loop_temperature",
            "maximum_loop_flow_rate",
            "minimum_loop_flow_rate",
            "condenser_loop_volume",
            "condenser_side_inlet_node_name",
            "condenser_side_outlet_node_name",
            "condenser_side_branch_list_name",
            "condenser_side_connector_list_name",
            "demand_side_inlet_node_name",
            "demand_side_outlet_node_name",
            "condenser_demand_side_branch_list_name",
            "condenser_demand_side_connector_list_name",
            "load_distribution_scheme",
            "pressure_simulation_type",
            "loop_circulation_time"
        ],
        "alphas": {
            "fields": [
                "name",
                "fluid_type",
                "user_defined_fluid_type",
                "condenser_equipment_operation_scheme_name",
                "condenser_loop_temperature_setpoint_node_name",
                "condenser_side_inlet_node_name",
                "condenser_side_outlet_node_name",
                "condenser_side_branch_list_name",
                "condenser_side_connector_list_name",
                "demand_side_inlet_node_name",
                "demand_side_outlet_node_name",
                "condenser_demand_side_branch_list_name",
                "condenser_demand_side_connector_list_name",
                "load_distribution_scheme",
                "pressure_simulation_type"
            ]
        },
        "numerics": {
            "fields": [
                "maximum_loop_temperature",
                "minimum_loop_temperature",
                "maximum_loop_flow_rate",
                "minimum_loop_flow_rate",
                "condenser_loop_volume",
                "loop_circulation_time"
            ]
        }
    },
    "type": "object",
    "memo": "Defines a central plant condenser loop. CondenserLoop and PlantLoop are nearly identical except some components and operation schemes are applicable to only one loop type or the other.",
    "min_fields": 18.0
}
```
