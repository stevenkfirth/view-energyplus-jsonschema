```
{
    "HeatPump:PlantLoop:EIR:Heating": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "load_side_inlet_node_name": {
                        "type": "string"
                    },
                    "load_side_outlet_node_name": {
                        "type": "string"
                    },
                    "condenser_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "AirSource",
                            "WaterSource"
                        ],
                        "default": "WaterSource"
                    },
                    "source_side_inlet_node_name": {
                        "type": "string"
                    },
                    "source_side_outlet_node_name": {
                        "type": "string"
                    },
                    "companion_heat_pump_name": {
                        "type": "string",
                        "note": "This field allows the user to specify a companion cooling object for this heating object. The companion is used in sizing the heat pump as well as to allow checks for unexpected simultaneous operation of the two objects.",
                        "data_type": "object_list",
                        "object_list": [
                            "PLHPCoolingNames"
                        ]
                    },
                    "load_side_reference_flow_rate": {
                        "note": "This component is currently a constant-flow device, meaning it will always try to request the full design flow from the central plant manager.",
                        "units": "m3/s",
                        "ip-units": "gal/min",
                        "default": "Autosize",
                        "anyOf": [
                            {
                                "type": "number",
                                "exclusiveMinimum": 0.0
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
                    "source_side_reference_flow_rate": {
                        "units": "m3/s",
                        "ip-units": "gal/min",
                        "default": "Autosize",
                        "anyOf": [
                            {
                                "type": "number",
                                "exclusiveMinimum": 0.0
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
                    "reference_capacity": {
                        "units": "W",
                        "default": "Autosize",
                        "anyOf": [
                            {
                                "type": "number",
                                "exclusiveMinimum": 0.0
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
                    "reference_coefficient_of_performance": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "default": 7.5,
                        "units": "W/W"
                    },
                    "sizing_factor": {
                        "type": "number",
                        "note": "Multiplies the autosized capacity and flow rates",
                        "exclusiveMinimum": 0.0,
                        "default": 1.0
                    },
                    "capacity_modifier_function_of_temperature_curve_name": {
                        "type": "string",
                        "note": "Heating capacity modifier as a function of CW supply temp and entering condenser temp curve = a + b*CWS + c*CWS**2 + d*ECT + e*ECT**2 + f*CWS*ECT CWS = supply (leaving) hot water temperature(C) ECT = entering condenser fluid temperature(C)",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ]
                    },
                    "electric_input_to_output_ratio_modifier_function_of_temperature_curve_name": {
                        "type": "string",
                        "note": "Electric Input Ratio (EIR) modifier as a function of temperature EIR = 1/COP curve = a + b*CWS + c*CWS**2 + d*ECT + e*ECT**2 + f*CWS*ECT CWS = supply (leaving) hot water temperature(C) ECT = entering condenser fluid temperature(C)",
                        "data_type": "object_list",
                        "object_list": [
                            "BiVariateFunctions"
                        ]
                    },
                    "electric_input_to_output_ratio_modifier_function_of_part_load_ratio_curve_name": {
                        "type": "string",
                        "note": "Electric Input Ratio (EIR) modifier as a function of Part Load Ratio (PLR) EIR = 1/COP quadratic curve = a + b*PLR + c*PLR**2 is typical, other univariate curves may be used PLR = part load ratio (hot load/steady state capacity)",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ]
                    }
                },
                "required": [
                    "load_side_inlet_node_name",
                    "load_side_outlet_node_name",
                    "source_side_inlet_node_name",
                    "source_side_outlet_node_name",
                    "capacity_modifier_function_of_temperature_curve_name",
                    "electric_input_to_output_ratio_modifier_function_of_temperature_curve_name",
                    "electric_input_to_output_ratio_modifier_function_of_part_load_ratio_curve_name"
                ]
            }
        },
        "group": "Plant Heating and Cooling Equipment",
        "name": {
            "type": "string",
            "reference": [
                "PLHPHeatingNames",
                "validBranchEquipmentNames",
                "validPlantEquipmentNames"
            ],
            "is_required": true,
            "reference-class-name": [
                "validBranchEquipmentTypes",
                "validPlantEquipmentTypes"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "load_side_inlet_node_name": {
                    "field_name": "Load Side Inlet Node Name",
                    "field_type": "a"
                },
                "load_side_outlet_node_name": {
                    "field_name": "Load Side Outlet Node Name",
                    "field_type": "a"
                },
                "condenser_type": {
                    "field_name": "Condenser Type",
                    "field_type": "a"
                },
                "source_side_inlet_node_name": {
                    "field_name": "Source Side Inlet Node Name",
                    "field_type": "a"
                },
                "source_side_outlet_node_name": {
                    "field_name": "Source Side Outlet Node Name",
                    "field_type": "a"
                },
                "companion_heat_pump_name": {
                    "field_name": "Companion Heat Pump Name",
                    "field_type": "a"
                },
                "load_side_reference_flow_rate": {
                    "field_name": "Load Side Reference Flow Rate",
                    "field_type": "n"
                },
                "source_side_reference_flow_rate": {
                    "field_name": "Source Side Reference Flow Rate",
                    "field_type": "n"
                },
                "reference_capacity": {
                    "field_name": "Reference Capacity",
                    "field_type": "n"
                },
                "reference_coefficient_of_performance": {
                    "field_name": "Reference Coefficient of Performance",
                    "field_type": "n"
                },
                "sizing_factor": {
                    "field_name": "Sizing Factor",
                    "field_type": "n"
                },
                "capacity_modifier_function_of_temperature_curve_name": {
                    "field_name": "Capacity Modifier Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "electric_input_to_output_ratio_modifier_function_of_temperature_curve_name": {
                    "field_name": "Electric Input to Output Ratio Modifier Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "electric_input_to_output_ratio_modifier_function_of_part_load_ratio_curve_name": {
                    "field_name": "Electric Input to Output Ratio Modifier Function of Part Load Ratio Curve Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "load_side_inlet_node_name",
                "load_side_outlet_node_name",
                "condenser_type",
                "source_side_inlet_node_name",
                "source_side_outlet_node_name",
                "companion_heat_pump_name",
                "load_side_reference_flow_rate",
                "source_side_reference_flow_rate",
                "reference_capacity",
                "reference_coefficient_of_performance",
                "sizing_factor",
                "capacity_modifier_function_of_temperature_curve_name",
                "electric_input_to_output_ratio_modifier_function_of_temperature_curve_name",
                "electric_input_to_output_ratio_modifier_function_of_part_load_ratio_curve_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "load_side_inlet_node_name",
                    "load_side_outlet_node_name",
                    "condenser_type",
                    "source_side_inlet_node_name",
                    "source_side_outlet_node_name",
                    "companion_heat_pump_name",
                    "capacity_modifier_function_of_temperature_curve_name",
                    "electric_input_to_output_ratio_modifier_function_of_temperature_curve_name",
                    "electric_input_to_output_ratio_modifier_function_of_part_load_ratio_curve_name"
                ]
            },
            "numerics": {
                "fields": [
                    "load_side_reference_flow_rate",
                    "source_side_reference_flow_rate",
                    "reference_capacity",
                    "reference_coefficient_of_performance",
                    "sizing_factor"
                ]
            }
        },
        "type": "object",
        "memo": "An EIR formulated water to water heat pump model, heating operation",
        "min_fields": 14.0
    }
}
```
