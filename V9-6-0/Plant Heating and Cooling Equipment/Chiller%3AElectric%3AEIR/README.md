```
{
    "Chiller:Electric:EIR": {
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
                    "reference_entering_condenser_fluid_temperature": {
                        "type": "number",
                        "default": 29.4,
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
                    "reference_condenser_fluid_flow_rate": {
                        "units": "m3/s",
                        "ip-units": "gal/min",
                        "note": "This field is only used for Condenser Type = AirCooled or EvaporativelyCooled when Heat Recovery is specified",
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
                    "cooling_capacity_function_of_temperature_curve_name": {
                        "type": "string",
                        "note": "Cooling capacity as a function of CW supply temp and entering condenser temp curve = a + b*CWS + c*CWS**2 + d*ECT + e*ECT**2 + f*CWS*ECT CWS = supply (leaving) chilled water temperature(C) ECT = entering condenser fluid temperature(C)",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ]
                    },
                    "electric_input_to_cooling_output_ratio_function_of_temperature_curve_name": {
                        "type": "string",
                        "note": "Electric Input Ratio (EIR) as a function of temperature EIR = 1/COP curve = a + b*CWS + c*CWS**2 + d*ECT + e*ECT**2 + f*CWS*ECT CWS = supply (leaving) chilled water temperature(C) ECT = entering condenser fluid temperature(C)",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ]
                    },
                    "electric_input_to_cooling_output_ratio_function_of_part_load_ratio_curve_name": {
                        "type": "string",
                        "note": "Electric Input Ratio (EIR) as a function of Part Load Ratio (PLR) EIR = 1/COP quadratic curve = a + b*PLR + c*PLR**2 is typical, other univariate curves may be used PLR = part load ratio (cooling load/steady state capacity)",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
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
                        "type": "string",
                        "note": "Not required if air-cooled or evaporatively-cooled"
                    },
                    "condenser_outlet_node_name": {
                        "type": "string",
                        "note": "Not required if air-cooled or evaporatively-cooled"
                    },
                    "condenser_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "AirCooled",
                            "EvaporativelyCooled",
                            "WaterCooled"
                        ],
                        "default": "WaterCooled"
                    },
                    "condenser_fan_power_ratio": {
                        "type": "number",
                        "units": "W/W",
                        "minimum": 0.0,
                        "default": 0.0,
                        "note": "Use for air-cooled or evaporatively-cooled condensers. Ratio of condenser fan power to reference chiller capacity"
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
                    "chiller_flow_mode": {
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
                        "note": "If non-zero, then the heat recovery inlet and outlet node names must be entered. Heat recovery is only available with Condenser Type = WaterCooled.",
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
                    "basin_heater_capacity": {
                        "type": "number",
                        "units": "W/K",
                        "minimum": 0.0,
                        "default": 0.0,
                        "note": "This field is only used for Condenser Type = EvaporativelyCooled and for periods when the basin heater is available (field Basin Heater Operating Schedule Name). For this situation, the heater maintains the basin water temperature at the basin heater setpoint temperature when the outdoor air temperature falls below the setpoint temperature. The basin heater only operates when the chiller is not operating."
                    },
                    "basin_heater_setpoint_temperature": {
                        "type": "number",
                        "units": "C",
                        "minimum": 2.0,
                        "default": 2.0,
                        "note": "This field is only used for Condenser Type = EvaporativelyCooled. Enter the outdoor dry-bulb temperature when the basin heater turns on."
                    },
                    "basin_heater_operating_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "This field is only used for Condenser Type = EvaporativelyCooled. Schedule values greater than 0 allow the basin heater to operate whenever the outdoor air dry-bulb temperature is below the basin heater setpoint temperature. If a schedule name is not entered, the basin heater is allowed to operate throughout the entire simulation."
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
                    "chilled_water_outlet_node_name"
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
                "reference_entering_condenser_fluid_temperature": {
                    "field_name": "Reference Entering Condenser Fluid Temperature",
                    "field_type": "n"
                },
                "reference_chilled_water_flow_rate": {
                    "field_name": "Reference Chilled Water Flow Rate",
                    "field_type": "n"
                },
                "reference_condenser_fluid_flow_rate": {
                    "field_name": "Reference Condenser Fluid Flow Rate",
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
                "condenser_type": {
                    "field_name": "Condenser Type",
                    "field_type": "a"
                },
                "condenser_fan_power_ratio": {
                    "field_name": "Condenser Fan Power Ratio",
                    "field_type": "n"
                },
                "fraction_of_compressor_electric_consumption_rejected_by_condenser": {
                    "field_name": "Fraction of Compressor Electric Consumption Rejected by Condenser",
                    "field_type": "n"
                },
                "leaving_chilled_water_lower_temperature_limit": {
                    "field_name": "Leaving Chilled Water Lower Temperature Limit",
                    "field_type": "n"
                },
                "chiller_flow_mode": {
                    "field_name": "Chiller Flow Mode",
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
                "basin_heater_capacity": {
                    "field_name": "Basin Heater Capacity",
                    "field_type": "n"
                },
                "basin_heater_setpoint_temperature": {
                    "field_name": "Basin Heater Setpoint Temperature",
                    "field_type": "n"
                },
                "basin_heater_operating_schedule_name": {
                    "field_name": "Basin Heater Operating Schedule Name",
                    "field_type": "a"
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
                "reference_entering_condenser_fluid_temperature",
                "reference_chilled_water_flow_rate",
                "reference_condenser_fluid_flow_rate",
                "cooling_capacity_function_of_temperature_curve_name",
                "electric_input_to_cooling_output_ratio_function_of_temperature_curve_name",
                "electric_input_to_cooling_output_ratio_function_of_part_load_ratio_curve_name",
                "minimum_part_load_ratio",
                "maximum_part_load_ratio",
                "optimum_part_load_ratio",
                "minimum_unloading_ratio",
                "chilled_water_inlet_node_name",
                "chilled_water_outlet_node_name",
                "condenser_inlet_node_name",
                "condenser_outlet_node_name",
                "condenser_type",
                "condenser_fan_power_ratio",
                "fraction_of_compressor_electric_consumption_rejected_by_condenser",
                "leaving_chilled_water_lower_temperature_limit",
                "chiller_flow_mode",
                "design_heat_recovery_water_flow_rate",
                "heat_recovery_inlet_node_name",
                "heat_recovery_outlet_node_name",
                "sizing_factor",
                "basin_heater_capacity",
                "basin_heater_setpoint_temperature",
                "basin_heater_operating_schedule_name",
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
                    "electric_input_to_cooling_output_ratio_function_of_part_load_ratio_curve_name",
                    "chilled_water_inlet_node_name",
                    "chilled_water_outlet_node_name",
                    "condenser_inlet_node_name",
                    "condenser_outlet_node_name",
                    "condenser_type",
                    "chiller_flow_mode",
                    "heat_recovery_inlet_node_name",
                    "heat_recovery_outlet_node_name",
                    "basin_heater_operating_schedule_name",
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
                    "reference_entering_condenser_fluid_temperature",
                    "reference_chilled_water_flow_rate",
                    "reference_condenser_fluid_flow_rate",
                    "minimum_part_load_ratio",
                    "maximum_part_load_ratio",
                    "optimum_part_load_ratio",
                    "minimum_unloading_ratio",
                    "condenser_fan_power_ratio",
                    "fraction_of_compressor_electric_consumption_rejected_by_condenser",
                    "leaving_chilled_water_lower_temperature_limit",
                    "design_heat_recovery_water_flow_rate",
                    "sizing_factor",
                    "basin_heater_capacity",
                    "basin_heater_setpoint_temperature",
                    "condenser_heat_recovery_relative_capacity_fraction"
                ]
            }
        },
        "type": "object",
        "memo": "This chiller model is the empirical model from the DOE-2 building Energy simulation program. Chiller performance at off-reference conditions is modeled using three polynomial equations. Three curves objects are required.",
        "min_fields": 23.0
    }
}
```
