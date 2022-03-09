```
{
    "HeatExchanger:FluidToFluid": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "availability_schedule_name": {
                        "type": "string",
                        "note": "Availability schedule name for this system. Schedule value > 0 means the system is available. If this field is blank, the system is always available. default is that heat exchanger is on",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "loop_demand_side_inlet_node_name": {
                        "type": "string",
                        "note": "This connection is to the demand side of a loop and is the inlet to the heat exchanger"
                    },
                    "loop_demand_side_outlet_node_name": {
                        "type": "string",
                        "note": "This connection is to the demand side of a loop"
                    },
                    "loop_demand_side_design_flow_rate": {
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
                    "loop_supply_side_inlet_node_name": {
                        "type": "string"
                    },
                    "loop_supply_side_outlet_node_name": {
                        "type": "string"
                    },
                    "loop_supply_side_design_flow_rate": {
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
                    "heat_exchange_model_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "CounterFlow",
                            "CrossFlowBothMixed",
                            "CrossFlowBothUnMixed",
                            "CrossFlowSupplyMixedDemandUnMixed",
                            "CrossFlowSupplyUnMixedDemandMixed",
                            "Ideal",
                            "ParallelFlow"
                        ],
                        "default": "Ideal"
                    },
                    "heat_exchanger_u_factor_times_area_value": {
                        "units": "W/K",
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
                    "control_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "CoolingDifferentialOnOff",
                            "CoolingSetpointModulated",
                            "CoolingSetpointOnOff",
                            "CoolingSetpointOnOffWithComponentOverride",
                            "DualDeadbandSetpointModulated",
                            "DualDeadbandSetpointOnOff",
                            "HeatingSetpointModulated",
                            "HeatingSetpointOnOff",
                            "OperationSchemeModulated",
                            "OperationSchemeOnOff",
                            "UncontrolledOn"
                        ],
                        "default": "UncontrolledOn"
                    },
                    "heat_exchanger_setpoint_node_name": {
                        "type": "string",
                        "note": "Setpoint node is needed with any Control Type that is \"*Setpoint*\""
                    },
                    "minimum_temperature_difference_to_activate_heat_exchanger": {
                        "type": "number",
                        "note": "Tolerance between control temperatures used to determine if heat exchanger should run.",
                        "minimum": 0.0,
                        "maximum": 50.0,
                        "default": 0.01,
                        "units": "deltaC"
                    },
                    "heat_transfer_metering_end_use_type": {
                        "type": "string",
                        "note": "This field controls end use reporting for heat transfer meters",
                        "enum": [
                            "",
                            "FreeCooling",
                            "HeatRecovery",
                            "HeatRecoveryForCooling",
                            "HeatRecoveryForHeating",
                            "HeatRejection",
                            "LoopToLoop"
                        ],
                        "default": "LoopToLoop"
                    },
                    "component_override_loop_supply_side_inlet_node_name": {
                        "type": "string",
                        "note": "This field is only used if Control Type is set to CoolingSetpointOnOffWithComponentOverride"
                    },
                    "component_override_loop_demand_side_inlet_node_name": {
                        "type": "string",
                        "note": "This field is only used if Control Type is set to CoolingSetpointOnOffWithComponentOverride"
                    },
                    "component_override_cooling_control_temperature_mode": {
                        "type": "string",
                        "enum": [
                            "",
                            "DryBulbTemperature",
                            "Loop",
                            "WetBulbTemperature"
                        ],
                        "default": "Loop",
                        "note": "This field is only used if Control Type is set to CoolingSetpointOnOffWithComponentOverride"
                    },
                    "sizing_factor": {
                        "type": "number",
                        "note": "Multiplies the autosized flow rates for this device",
                        "exclusiveMinimum": 0.0,
                        "default": 1.0
                    },
                    "operation_minimum_temperature_limit": {
                        "type": "number",
                        "note": "Lower limit on inlet temperatures, heat exchanger will not operate if either inlet is below this limit",
                        "units": "C"
                    },
                    "operation_maximum_temperature_limit": {
                        "type": "number",
                        "note": "Upper limit on inlet temperatures, heat exchanger will not operate if either inlet is above this limit",
                        "units": "C"
                    }
                },
                "required": [
                    "loop_demand_side_inlet_node_name",
                    "loop_demand_side_outlet_node_name",
                    "loop_demand_side_design_flow_rate",
                    "loop_supply_side_inlet_node_name",
                    "loop_supply_side_outlet_node_name",
                    "loop_supply_side_design_flow_rate",
                    "heat_exchanger_u_factor_times_area_value"
                ]
            }
        },
        "group": "Condenser Equipment and Heat Exchangers",
        "name": {
            "type": "string",
            "is_required": true,
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
                "availability_schedule_name": {
                    "field_name": "Availability Schedule Name",
                    "field_type": "a"
                },
                "loop_demand_side_inlet_node_name": {
                    "field_name": "Loop Demand Side Inlet Node Name",
                    "field_type": "a"
                },
                "loop_demand_side_outlet_node_name": {
                    "field_name": "Loop Demand Side Outlet Node Name",
                    "field_type": "a"
                },
                "loop_demand_side_design_flow_rate": {
                    "field_name": "Loop Demand Side Design Flow Rate",
                    "field_type": "n"
                },
                "loop_supply_side_inlet_node_name": {
                    "field_name": "Loop Supply Side Inlet Node Name",
                    "field_type": "a"
                },
                "loop_supply_side_outlet_node_name": {
                    "field_name": "Loop Supply Side Outlet Node Name",
                    "field_type": "a"
                },
                "loop_supply_side_design_flow_rate": {
                    "field_name": "Loop Supply Side Design Flow Rate",
                    "field_type": "n"
                },
                "heat_exchange_model_type": {
                    "field_name": "Heat Exchange Model Type",
                    "field_type": "a"
                },
                "heat_exchanger_u_factor_times_area_value": {
                    "field_name": "Heat Exchanger U-Factor Times Area Value",
                    "field_type": "n"
                },
                "control_type": {
                    "field_name": "Control Type",
                    "field_type": "a"
                },
                "heat_exchanger_setpoint_node_name": {
                    "field_name": "Heat Exchanger Setpoint Node Name",
                    "field_type": "a"
                },
                "minimum_temperature_difference_to_activate_heat_exchanger": {
                    "field_name": "Minimum Temperature Difference to Activate Heat Exchanger",
                    "field_type": "n"
                },
                "heat_transfer_metering_end_use_type": {
                    "field_name": "Heat Transfer Metering End Use Type",
                    "field_type": "a"
                },
                "component_override_loop_supply_side_inlet_node_name": {
                    "field_name": "Component Override Loop Supply Side Inlet Node Name",
                    "field_type": "a"
                },
                "component_override_loop_demand_side_inlet_node_name": {
                    "field_name": "Component Override Loop Demand Side Inlet Node Name",
                    "field_type": "a"
                },
                "component_override_cooling_control_temperature_mode": {
                    "field_name": "Component Override Cooling Control Temperature Mode",
                    "field_type": "a"
                },
                "sizing_factor": {
                    "field_name": "Sizing Factor",
                    "field_type": "n"
                },
                "operation_minimum_temperature_limit": {
                    "field_name": "Operation Minimum Temperature Limit",
                    "field_type": "n"
                },
                "operation_maximum_temperature_limit": {
                    "field_name": "Operation Maximum Temperature Limit",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "availability_schedule_name",
                "loop_demand_side_inlet_node_name",
                "loop_demand_side_outlet_node_name",
                "loop_demand_side_design_flow_rate",
                "loop_supply_side_inlet_node_name",
                "loop_supply_side_outlet_node_name",
                "loop_supply_side_design_flow_rate",
                "heat_exchange_model_type",
                "heat_exchanger_u_factor_times_area_value",
                "control_type",
                "heat_exchanger_setpoint_node_name",
                "minimum_temperature_difference_to_activate_heat_exchanger",
                "heat_transfer_metering_end_use_type",
                "component_override_loop_supply_side_inlet_node_name",
                "component_override_loop_demand_side_inlet_node_name",
                "component_override_cooling_control_temperature_mode",
                "sizing_factor",
                "operation_minimum_temperature_limit",
                "operation_maximum_temperature_limit"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "loop_demand_side_inlet_node_name",
                    "loop_demand_side_outlet_node_name",
                    "loop_supply_side_inlet_node_name",
                    "loop_supply_side_outlet_node_name",
                    "heat_exchange_model_type",
                    "control_type",
                    "heat_exchanger_setpoint_node_name",
                    "heat_transfer_metering_end_use_type",
                    "component_override_loop_supply_side_inlet_node_name",
                    "component_override_loop_demand_side_inlet_node_name",
                    "component_override_cooling_control_temperature_mode"
                ]
            },
            "numerics": {
                "fields": [
                    "loop_demand_side_design_flow_rate",
                    "loop_supply_side_design_flow_rate",
                    "heat_exchanger_u_factor_times_area_value",
                    "minimum_temperature_difference_to_activate_heat_exchanger",
                    "sizing_factor",
                    "operation_minimum_temperature_limit",
                    "operation_maximum_temperature_limit"
                ]
            }
        },
        "type": "object",
        "memo": "A fluid/fluid heat exchanger designed to couple the supply side of one loop to the demand side of another loop Loops can be either plant or condenser loops but no air side connections are allowed",
        "min_fields": 14.0
    }
}
```
