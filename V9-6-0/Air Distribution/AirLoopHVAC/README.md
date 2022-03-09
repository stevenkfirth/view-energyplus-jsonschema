```
{
    "AirLoopHVAC": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "controller_list_name": {
                        "type": "string",
                        "note": "Enter the name of an AirLoopHVAC:ControllerList object.",
                        "data_type": "object_list",
                        "object_list": [
                            "ControllerLists"
                        ]
                    },
                    "availability_manager_list_name": {
                        "type": "string",
                        "note": "Enter the name of an AvailabilityManagerAssignmentList object.",
                        "data_type": "object_list",
                        "object_list": [
                            "SystemAvailabilityManagerLists"
                        ]
                    },
                    "design_supply_air_flow_rate": {
                        "default": 0.0,
                        "units": "m3/s",
                        "anyOf": [
                            {
                                "type": "number"
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "",
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "branch_list_name": {
                        "type": "string",
                        "note": "Name of a BranchList containing all the branches in this air loop",
                        "data_type": "object_list",
                        "object_list": [
                            "BranchLists"
                        ]
                    },
                    "connector_list_name": {
                        "type": "string",
                        "note": "Name of a ConnectorList containing all the splitters and mixers in the loop",
                        "data_type": "object_list",
                        "object_list": [
                            "ConnectorLists"
                        ]
                    },
                    "supply_side_inlet_node_name": {
                        "type": "string",
                        "note": "Name of inlet node where air enters the supply side of the air loop. If this air loop has a return path, then this node is where return air enters the supply side. If this air loop has no return path, then this node is where outdoor air or other air enters the supply side."
                    },
                    "demand_side_outlet_node_name": {
                        "type": "string",
                        "note": "Name of outlet node where return air leaves the demand side and enters the supply side. Required if this air loop has a return path. Leave this field blank if there is no return."
                    },
                    "demand_side_inlet_node_names": {
                        "type": "string",
                        "note": "Name of a Node or NodeList containing the inlet node(s) supplying air to zone equipment."
                    },
                    "supply_side_outlet_node_names": {
                        "type": "string",
                        "note": "Name of a Node or NodeList containing the outlet node(s) supplying air to the demand side."
                    },
                    "design_return_air_flow_fraction_of_supply_air_flow": {
                        "type": "number",
                        "note": "The design return air flow rate as a fraction of supply air flow rate with no exhaust. This can be used to model a pressurized system or set to zero to model a DOAS with no return flow. Use ZoneAirMassFlowConservation to balance zone infiltration and mixing flows.",
                        "minimum": 0.0,
                        "default": 1.0
                    }
                },
                "required": [
                    "branch_list_name",
                    "supply_side_inlet_node_name",
                    "demand_side_inlet_node_names",
                    "supply_side_outlet_node_names"
                ]
            }
        },
        "group": "Air Distribution",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "AirPrimaryLoops"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "controller_list_name": {
                    "field_name": "Controller List Name",
                    "field_type": "a"
                },
                "availability_manager_list_name": {
                    "field_name": "Availability Manager List Name",
                    "field_type": "a"
                },
                "design_supply_air_flow_rate": {
                    "field_name": "Design Supply Air Flow Rate",
                    "field_type": "n"
                },
                "branch_list_name": {
                    "field_name": "Branch List Name",
                    "field_type": "a"
                },
                "connector_list_name": {
                    "field_name": "Connector List Name",
                    "field_type": "a"
                },
                "supply_side_inlet_node_name": {
                    "field_name": "Supply Side Inlet Node Name",
                    "field_type": "a"
                },
                "demand_side_outlet_node_name": {
                    "field_name": "Demand Side Outlet Node Name",
                    "field_type": "a"
                },
                "demand_side_inlet_node_names": {
                    "field_name": "Demand Side Inlet Node Names",
                    "field_type": "a"
                },
                "supply_side_outlet_node_names": {
                    "field_name": "Supply Side Outlet Node Names",
                    "field_type": "a"
                },
                "design_return_air_flow_fraction_of_supply_air_flow": {
                    "field_name": "Design Return Air Flow Fraction of Supply Air Flow",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "controller_list_name",
                "availability_manager_list_name",
                "design_supply_air_flow_rate",
                "branch_list_name",
                "connector_list_name",
                "supply_side_inlet_node_name",
                "demand_side_outlet_node_name",
                "demand_side_inlet_node_names",
                "supply_side_outlet_node_names",
                "design_return_air_flow_fraction_of_supply_air_flow"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "controller_list_name",
                    "availability_manager_list_name",
                    "branch_list_name",
                    "connector_list_name",
                    "supply_side_inlet_node_name",
                    "demand_side_outlet_node_name",
                    "demand_side_inlet_node_names",
                    "supply_side_outlet_node_names"
                ]
            },
            "numerics": {
                "fields": [
                    "design_supply_air_flow_rate",
                    "design_return_air_flow_fraction_of_supply_air_flow"
                ]
            }
        },
        "type": "object",
        "memo": "Defines a central forced air system.",
        "min_fields": 10.0
    }
}
```
