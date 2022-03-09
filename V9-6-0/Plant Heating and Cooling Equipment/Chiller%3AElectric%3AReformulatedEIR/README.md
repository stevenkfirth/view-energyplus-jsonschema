```
{
    "Chiller:Electric:ReformulatedEIR": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "reference_capacity": {
                        "units": "W",
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
                    "reference_cop": {
                        "type": "number",
                        "note": "Efficiency of the chiller compressor (cooling output/compressor energy input). Condenser fan power should not be included here.",
                        "units": "W/W",
                        "exclusiveMinimum": 0.0
                    },
                    "reference_leaving_chilled_water_temperature": {
                        "type": "number",
                        "default": 6.67,
                        "units": "C"
                    },
                    "reference_leaving_condenser_water_temperature": {
                        "type": "number",
                        "default": 35.0,
                        "units": "C"
                    },
                    "reference_chilled_water_flow_rate": {
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
                    "reference_condenser_water_flow_rate": {
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
                    "cooling_capacity_function_of_temperature_curve_name": {
                        "type": "string",
                        "note": "Cooling capacity as a function of supply (leaving) chilled water temperature and leaving condenser fluid temperature curve = a + b*CWS + c*CWS**2 + d*LCT + e*LCT**2 + f*CWS*LCT CWS = supply (leaving) chilled water temperature(C) LCT = leaving condenser fluid temperature(C)",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ]
                    },
                    "electric_input_to_cooling_output_ratio_function_of_temperature_curve_name": {
                        "type": "string",
                        "note": "Electric Input Ratio (EIR) as a function of supply (leaving) chilled water temperature and leaving condenser fluid temperature. EIR = 1/COP. curve = a + b*CWS + c*CWS**2 + d*LCT + e*LCT**2 + f*CWS*LCT CWS = supply (leaving) chilled water temperature(C) LCT = leaving condenser fluid temperature(C)",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ]
                    },
                    "electric_input_to_cooling_output_ratio_function_of_part_load_ratio_curve_type": {
                        "type": "string",
                        "note": "Two curve types are available: Type LeavingCondenserWaterTemperature: based on the leaving condenser water temperature. Type Lift: based on the normalized lift, which is the temperature difference between the leaving condenser water temperature and the leaving evaporator water temperature.",
                        "enum": [
                            "",
                            "LeavingCondenserWaterTemperature",
                            "Lift"
                        ],
                        "default": "LeavingCondenserWaterTemperature"
                    },
                    "electric_input_to_cooling_output_ratio_function_of_part_load_ratio_curve_name": {
                        "type": "string",
                        "note": "Electric Input Ratio (EIR) as a function of Part Load Ratio (PLR) EIR = 1/COP The form of this curve is based on the input for Electric Input to Cooling Output RatioFunction of Part Load Ratio Curve Type Type=LeavingCondenserWaterTemperature: Calculated based on LCT and PLR Curve object type should be Curve:Bicubic or Table:Lookup Bicubic curve = a + b*LCT + c*LCT**2 + d*PLR + e*PLR**2 + f*LCT*PLR + g*0 + h*PLR**3 + i*0 + j*0 PLR = part load ratio (cooling load/steady state capacity) LCT = leaving condenser fluid temperature(C) Type=Lift: Calculated based on dT*, Tdev* and PLR Curve object type should be Curve:ChillerPartLoadWithLiftCurves or Table:Lookup ChillerPartLoadWithLiftCurves curve = a + b*(dT*) + c*(dT*)**2 + d*PLR + e*PLR**2 + f*(dT*)*PLR + g*(dT*)**3 + h*PLR**3 + i*(dT*)**2*PLR + j*(dT*)*PLR**2 + k*(dT*)**2*PLR**2 + l*(Tdev*)*PLR**3 x = dT* = normalized fractional Lift = dT / dTref y = PLR = part load ratio (cooling load/steady state capacity) z = Tdev* = normalized Tdev = Tdev / dTref Where: dT = Lift = Leaving Condenser Water Temperature - Leaving Chilled Water Temperature dTref = dT at the reference condition Tdev = Leaving Chilled Water Temperature - Reference Chilled Water Temperature",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions",
                            "TrivariateFunctions"
                        ]
                    },
                    "minimum_part_load_ratio": {
                        "type": "number",
                        "note": "Part load ratio below which the chiller starts cycling on/off to meet the load. Must be less than or equal to Maximum Part Load Ratio.",
                        "minimum": 0.0,
                        "default": 0.1
                    },
                    "maximum_part_load_ratio": {
                        "type": "number",
                        "note": "Maximum allowable part load ratio. Must be greater than or equal to Minimum Part Load Ratio.",
                        "exclusiveMinimum": 0.0,
                        "default": 1.0
                    },
                    "optimum_part_load_ratio": {
                        "type": "number",
                        "note": "Optimum part load ratio where the chiller is most efficient. Must be greater than or equal to the Minimum Part Load Ratio and less than or equal to the Maximum Part Load Ratio.",
                        "exclusiveMinimum": 0.0,
                        "default": 1.0
                    },
                    "minimum_unloading_ratio": {
                        "type": "number",
                        "note": "Part load ratio where the chiller can no longer unload and false loading begins. Minimum unloading ratio must be greater than or equal to the Minimum Part Load Ratio and less than or equal to the Maximum Part Load Ratio.",
                        "minimum": 0.0,
                        "default": 0.2
                    },
                    "chilled_water_inlet_node_name": {
                        "type": "string"
                    },
                    "chilled_water_outlet_node_name": {
                        "type": "string"
                    },
                    "condenser_inlet_node_name": {
                        "type": "string"
                    },
                    "condenser_outlet_node_name": {
                        "type": "string"
                    },
                    "fraction_of_compressor_electric_consumption_rejected_by_condenser": {
                        "type": "number",
                        "note": "Fraction of compressor electrical energy that must be rejected by the condenser. Enter a value of 1.0 when modeling hermetic chillers. For open chillers, enter the compressor motor efficiency. This value should be greater than 0.6 for practical applications.",
                        "exclusiveMinimum": 0.0,
                        "maximum": 1.0,
                        "default": 1.0
                    },
                    "leaving_chilled_water_lower_temperature_limit": {
                        "type": "number",
                        "default": 2.0,
                        "units": "C"
                    },
                    "chiller_flow_mode_type": {
                        "type": "string",
                        "note": "Select operating mode for fluid flow through the chiller. \"NotModulated\" is for either variable or constant pumping with flow controlled by the external plant system. \"ConstantFlow\" is for constant pumping with flow controlled by chiller to operate at full design flow rate. \"LeavingSetpointModulated\" is for variable pumping with flow controlled by chiller to vary flow to target a leaving temperature setpoint.",
                        "enum": [
                            "",
                            "ConstantFlow",
                            "LeavingSetpointModulated",
                            "NotModulated"
                        ],
                        "default": "NotModulated"
                    },
                    "design_heat_recovery_water_flow_rate": {
                        "note": "If non-zero, then the heat recovery inlet and outlet node names must be entered.",
                        "units": "m3/s",
                        "default": 0.0,
                        "ip-units": "gal/min",
                        "anyOf": [
                            {
                                "type": "number",
                                "minimum": 0.0
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
                    "heat_recovery_inlet_node_name": {
                        "type": "string"
                    },
                    "heat_recovery_outlet_node_name": {
                        "type": "string"
                    },
                    "sizing_factor": {
                        "type": "number",
                        "note": "Multiplies the autosized capacity and flow rates",
                        "exclusiveMinimum": 0.0,
                        "default": 1.0
                    },
                    "condenser_heat_recovery_relative_capacity_fraction": {
                        "type": "number",
                        "note": "This optional field is the fraction of total rejected heat that can be recovered at full load",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "heat_recovery_inlet_high_temperature_limit_schedule_name": {
                        "type": "string",
                        "note": "This optional schedule of temperatures will turn off heat recovery if inlet exceeds the value",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "heat_recovery_leaving_temperature_setpoint_node_name": {
                        "type": "string",
                        "note": "This optional field provides control over the heat recovery Using this triggers a model more suited to series bundle and chillers with higher temperature heat recovery If this field is not used, the bundles are modeled as being in parallel"
                    },
                    "end_use_subcategory": {
                        "type": "string",
                        "note": "Any text may be used here to categorize the end-uses in the ABUPS End Uses by Subcategory table.",
                        "retaincase": true,
                        "default": "General"
                    }
                },
                "required": [
                    "reference_capacity",
                    "reference_cop",
                    "cooling_capacity_function_of_temperature_curve_name",
                    "electric_input_to_cooling_output_ratio_function_of_temperature_curve_name",
                    "electric_input_to_cooling_output_ratio_function_of_part_load_ratio_curve_name",
                    "chilled_water_inlet_node_name",
                    "chilled_water_outlet_node_name",
                    "condenser_inlet_node_name",
                    "condenser_outlet_node_name"
                ]
            }
        },
        "group": "Plant Heating and Cooling Equipment",
        "name": {
            "type": "string",
            "reference": [
                "Chillers",
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
                "reference_capacity": {
                    "field_name": "Reference Capacity",
                    "field_type": "n"
                },
                "reference_cop": {
                    "field_name": "Reference COP",
                    "field_type": "n"
                },
                "reference_leaving_chilled_water_temperature": {
                    "field_name": "Reference Leaving Chilled Water Temperature",
                    "field_type": "n"
                },
                "reference_leaving_condenser_water_temperature": {
                    "field_name": "Reference Leaving Condenser Water Temperature",
                    "field_type": "n"
                },
                "reference_chilled_water_flow_rate": {
                    "field_name": "Reference Chilled Water Flow Rate",
                    "field_type": "n"
                },
                "reference_condenser_water_flow_rate": {
                    "field_name": "Reference Condenser Water Flow Rate",
                    "field_type": "n"
                },
                "cooling_capacity_function_of_temperature_curve_name": {
                    "field_name": "Cooling Capacity Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "electric_input_to_cooling_output_ratio_function_of_temperature_curve_name": {
                    "field_name": "Electric Input to Cooling Output Ratio Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "electric_input_to_cooling_output_ratio_function_of_part_load_ratio_curve_type": {
                    "field_name": "Electric Input to Cooling Output Ratio Function of Part Load Ratio Curve Type",
                    "field_type": "a"
                },
                "electric_input_to_cooling_output_ratio_function_of_part_load_ratio_curve_name": {
                    "field_name": "Electric Input to Cooling Output Ratio Function of Part Load Ratio Curve Name",
                    "field_type": "a"
                },
                "minimum_part_load_ratio": {
                    "field_name": "Minimum Part Load Ratio",
                    "field_type": "n"
                },
                "maximum_part_load_ratio": {
                    "field_name": "Maximum Part Load Ratio",
                    "field_type": "n"
                },
                "optimum_part_load_ratio": {
                    "field_name": "Optimum Part Load Ratio",
                    "field_type": "n"
                },
                "minimum_unloading_ratio": {
                    "field_name": "Minimum Unloading Ratio",
                    "field_type": "n"
                },
                "chilled_water_inlet_node_name": {
                    "field_name": "Chilled Water Inlet Node Name",
                    "field_type": "a"
                },
                "chilled_water_outlet_node_name": {
                    "field_name": "Chilled Water Outlet Node Name",
                    "field_type": "a"
                },
                "condenser_inlet_node_name": {
                    "field_name": "Condenser Inlet Node Name",
                    "field_type": "a"
                },
                "condenser_outlet_node_name": {
                    "field_name": "Condenser Outlet Node Name",
                    "field_type": "a"
                },
                "fraction_of_compressor_electric_consumption_rejected_by_condenser": {
                    "field_name": "Fraction of Compressor Electric Consumption Rejected by Condenser",
                    "field_type": "n"
                },
                "leaving_chilled_water_lower_temperature_limit": {
                    "field_name": "Leaving Chilled Water Lower Temperature Limit",
                    "field_type": "n"
                },
                "chiller_flow_mode_type": {
                    "field_name": "Chiller Flow Mode Type",
                    "field_type": "a"
                },
                "design_heat_recovery_water_flow_rate": {
                    "field_name": "Design Heat Recovery Water Flow Rate",
                    "field_type": "n"
                },
                "heat_recovery_inlet_node_name": {
                    "field_name": "Heat Recovery Inlet Node Name",
                    "field_type": "a"
                },
                "heat_recovery_outlet_node_name": {
                    "field_name": "Heat Recovery Outlet Node Name",
                    "field_type": "a"
                },
                "sizing_factor": {
                    "field_name": "Sizing Factor",
                    "field_type": "n"
                },
                "condenser_heat_recovery_relative_capacity_fraction": {
                    "field_name": "Condenser Heat Recovery Relative Capacity Fraction",
                    "field_type": "n"
                },
                "heat_recovery_inlet_high_temperature_limit_schedule_name": {
                    "field_name": "Heat Recovery Inlet High Temperature Limit Schedule Name",
                    "field_type": "a"
                },
                "heat_recovery_leaving_temperature_setpoint_node_name": {
                    "field_name": "Heat Recovery Leaving Temperature Setpoint Node Name",
                    "field_type": "a"
                },
                "end_use_subcategory": {
                    "field_name": "End-Use Subcategory",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "reference_capacity",
                "reference_cop",
                "reference_leaving_chilled_water_temperature",
                "reference_leaving_condenser_water_temperature",
                "reference_chilled_water_flow_rate",
                "reference_condenser_water_flow_rate",
                "cooling_capacity_function_of_temperature_curve_name",
                "electric_input_to_cooling_output_ratio_function_of_temperature_curve_name",
                "electric_input_to_cooling_output_ratio_function_of_part_load_ratio_curve_type",
                "electric_input_to_cooling_output_ratio_function_of_part_load_ratio_curve_name",
                "minimum_part_load_ratio",
                "maximum_part_load_ratio",
                "optimum_part_load_ratio",
                "minimum_unloading_ratio",
                "chilled_water_inlet_node_name",
                "chilled_water_outlet_node_name",
                "condenser_inlet_node_name",
                "condenser_outlet_node_name",
                "fraction_of_compressor_electric_consumption_rejected_by_condenser",
                "leaving_chilled_water_lower_temperature_limit",
                "chiller_flow_mode_type",
                "design_heat_recovery_water_flow_rate",
                "heat_recovery_inlet_node_name",
                "heat_recovery_outlet_node_name",
                "sizing_factor",
                "condenser_heat_recovery_relative_capacity_fraction",
                "heat_recovery_inlet_high_temperature_limit_schedule_name",
                "heat_recovery_leaving_temperature_setpoint_node_name",
                "end_use_subcategory"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "cooling_capacity_function_of_temperature_curve_name",
                    "electric_input_to_cooling_output_ratio_function_of_temperature_curve_name",
                    "electric_input_to_cooling_output_ratio_function_of_part_load_ratio_curve_type",
                    "electric_input_to_cooling_output_ratio_function_of_part_load_ratio_curve_name",
                    "chilled_water_inlet_node_name",
                    "chilled_water_outlet_node_name",
                    "condenser_inlet_node_name",
                    "condenser_outlet_node_name",
                    "chiller_flow_mode_type",
                    "heat_recovery_inlet_node_name",
                    "heat_recovery_outlet_node_name",
                    "heat_recovery_inlet_high_temperature_limit_schedule_name",
                    "heat_recovery_leaving_temperature_setpoint_node_name",
                    "end_use_subcategory"
                ]
            },
            "numerics": {
                "fields": [
                    "reference_capacity",
                    "reference_cop",
                    "reference_leaving_chilled_water_temperature",
                    "reference_leaving_condenser_water_temperature",
                    "reference_chilled_water_flow_rate",
                    "reference_condenser_water_flow_rate",
                    "minimum_part_load_ratio",
                    "maximum_part_load_ratio",
                    "optimum_part_load_ratio",
                    "minimum_unloading_ratio",
                    "fraction_of_compressor_electric_consumption_rejected_by_condenser",
                    "leaving_chilled_water_lower_temperature_limit",
                    "design_heat_recovery_water_flow_rate",
                    "sizing_factor",
                    "condenser_heat_recovery_relative_capacity_fraction"
                ]
            }
        },
        "type": "object",
        "memo": "This chiller model is an empirical model, a reformulated version of Chiller:Electric:EIR where the performance is a function of condenser leaving fluid Temperature instead of condenser entering fluid Temperature. Chiller performance at off-reference conditions is modeled using three polynomial equations. Three curve objects are required.",
        "min_fields": 22.0
    }
}
```
