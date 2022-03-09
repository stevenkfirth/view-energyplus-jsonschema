```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "reference_cooling_mode_evaporator_capacity": {
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
                "reference_cooling_mode_cop": {
                    "type": "number",
                    "note": "Efficiency of the chiller compressor (cooling output/compressor energy input).",
                    "units": "W/W",
                    "exclusiveMinimum": 0.0
                },
                "reference_cooling_mode_leaving_chilled_water_temperature": {
                    "type": "number",
                    "default": 6.67,
                    "units": "C"
                },
                "reference_cooling_mode_entering_condenser_fluid_temperature": {
                    "type": "number",
                    "default": 29.44,
                    "units": "C"
                },
                "reference_cooling_mode_leaving_condenser_water_temperature": {
                    "type": "number",
                    "default": 35.0,
                    "units": "C"
                },
                "reference_heating_mode_cooling_capacity_ratio": {
                    "type": "number",
                    "note": "During simultaneous cooling-heating mode, this ratio is relative to the Reference Cooling Mode Cooling Capacity (Evaporator capacity at simul clg-htg mode ref condition)/ (Evaporator capacity at cooling mode ref condition)",
                    "default": 0.75
                },
                "reference_heating_mode_cooling_power_input_ratio": {
                    "type": "number",
                    "note": "During simultaneous cooling-heating mode, this ratio is relative to the Reference Cooling Mode COP (Power at simultaneous clg-htg mode reference condition)/ (Power at cooling mode reference condition)",
                    "default": 1.38,
                    "exclusiveMinimum": 0.0
                },
                "reference_heating_mode_leaving_chilled_water_temperature": {
                    "type": "number",
                    "note": "During simultaneous cooling-heating mode",
                    "default": 6.67,
                    "units": "C"
                },
                "reference_heating_mode_leaving_condenser_water_temperature": {
                    "type": "number",
                    "note": "During simultaneous cooling-heating mode",
                    "default": 49.0,
                    "units": "C"
                },
                "reference_heating_mode_entering_condenser_fluid_temperature": {
                    "type": "number",
                    "default": 29.44,
                    "units": "C"
                },
                "heating_mode_entering_chilled_water_temperature_low_limit": {
                    "type": "number",
                    "note": "During simultaneous cooling-heating mode",
                    "default": 12.22,
                    "units": "C"
                },
                "chilled_water_flow_mode_type": {
                    "type": "string",
                    "note": "Sets chilled water flow rate to either constant or variable.",
                    "enum": [
                        "",
                        "ConstantFlow",
                        "VariableFlow"
                    ],
                    "default": "ConstantFlow"
                },
                "design_chilled_water_flow_rate": {
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
                "design_condenser_water_flow_rate": {
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
                "design_hot_water_flow_rate": {
                    "type": "number",
                    "units": "m3/s",
                    "minimum": 0.0,
                    "default": 0.0,
                    "ip-units": "gal/min"
                },
                "compressor_motor_efficiency": {
                    "type": "number",
                    "note": "Fraction of compressor electrical energy that must be rejected by the condenser. Enter 1.0 or leave this field blank for a hermetic compressor.",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 1.0
                },
                "condenser_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "AirCooled",
                        "WaterCooled"
                    ],
                    "default": "WaterCooled"
                },
                "cooling_mode_temperature_curve_condenser_water_independent_variable": {
                    "type": "string",
                    "enum": [
                        "",
                        "EnteringCondenser",
                        "LeavingCondenser"
                    ],
                    "default": "EnteringCondenser",
                    "note": "Sets the second independent variable in the three temperature dependent performance curves to either the leaving or entering condenser water temperature. Manufacturers express the performance of their chillers using either the leaving condenser water temperature (to the tower) or the entering condenser water temperature (from the tower). Cooling mode is generally a stronger function of Entering Condenser Fluid Temperature"
                },
                "cooling_mode_cooling_capacity_function_of_temperature_curve_name": {
                    "type": "string",
                    "note": "Cooling capacity as a function of leaving chilled water temperature and either entering or leaving condenser fluid temperature curve = a + b*CWS + c*CWS**2 + d*TCond + e*TCond**2 + f*CWS*TCond If ClgModeCondWaterCurveInputVariable = EnteringCondenser, TCond = ECT If ClgModeCondWaterCurveInputVariable = LeavingCondenser, TCond = LCT CWS = supply (leaving) chilled water temperature(C) LCT = leaving condenser fluid temperature(C) ECT = entering condenser fluid temperature(C)",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ]
                },
                "cooling_mode_electric_input_to_cooling_output_ratio_function_of_temperature_curve_name": {
                    "type": "string",
                    "note": "Electric Input Ratio (EIR) as a function of supply (leaving) chilled water temperature and leaving condenser fluid temperature. EIR = 1/COP. curve = a + b*CWS + c*CWS**2 + d*TCond + e*TCond**2 + f*CWS*TCond If ClgModeCondWaterCurveInputVariable = EnteringCondenser, TCond = ECT If ClgModeCondWaterCurveInputVariable = LeavingCondenser, TCond = LCT CWS = supply (leaving) chilled water temperature(C) LCT = leaving condenser fluid temperature(C) ECT = entering condenser fluid temperature(C)",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ]
                },
                "cooling_mode_electric_input_to_cooling_output_ratio_function_of_part_load_ratio_curve_name": {
                    "type": "string",
                    "note": "Electric Input Ratio (EIR) as a function of Part Load Ratio (PLR) EIR = 1/COP Bicubic = a + b*TCond + c*TCond**2 + d*PLR + e*PLR**2 + f*TCond*PLR +g*0 + h*PLR**3+i*0+j*0 If ClgModeCondWaterCurveInputVariable = EnteringCondenser, TCond = ECT If ClgModeCondWaterCurveInputVariable = LeavingCondenser, TCond = LCT Normally, a bicubic curve here should be in terms of LCT rather than ECT Also, a bicubic curve is more applicable for variable-speed compressor motor drives or Quadratic = a + b*PLR + c*PLR**2 PLR = part load ratio (cooling load/steady-state capacity) LCT = leaving condenser fluid temperature(C) ECT = entering condenser fluid temperature(C)",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions",
                        "UnivariateFunctions"
                    ]
                },
                "cooling_mode_cooling_capacity_optimum_part_load_ratio": {
                    "type": "number",
                    "note": "Optimum part load ratio where the chiller is most efficient. Must be greater than or equal to the Minimum Part Load Ratio and less than or equal to the Maximum Part Load Ratio. The Min/Max PLR are taken from their associated EIR-FPLR curve references.",
                    "exclusiveMinimum": 0.0,
                    "default": 1.0
                },
                "heating_mode_temperature_curve_condenser_water_independent_variable": {
                    "type": "string",
                    "enum": [
                        "",
                        "EnteringCondenser",
                        "LeavingCondenser"
                    ],
                    "default": "LeavingCondenser",
                    "note": "Sets the second independent variable in the three temperature dependent performance curves to either the leaving or entering condenser water temperature. Manufacturers express the performance of their chillers using either the leaving condenser water temperature (to the tower) or the entering condenser water temperature (from the tower). Heating mode (or Simul Clg/Htg Load) should be a function of Leaving Condenser Fluid Temperature Only use EnteringCondenser as a last resort in case no performance data exists for LeavingCondenser"
                },
                "heating_mode_cooling_capacity_function_of_temperature_curve_name": {
                    "type": "string",
                    "note": "Evaporator (cooling) capacity as a function of leaving chilled water temperature and leaving condenser fluid temperature when in heating or simultaneous cool/heat mode curve = a + b*CWS + c*CWS**2 + d*TCond + e*TCond**2 + f*CWS*TCond If independent variable = EnteringCondenser, TCond = ECT If independent variable = LeavingCondenser, TCond = LCT CWS = supply (leaving) chilled water temperature(C) LCT = leaving condenser fluid temperature(C) ECT = entering condenser fluid temperature(C)",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ]
                },
                "heating_mode_electric_input_to_cooling_output_ratio_function_of_temperature_curve_name": {
                    "type": "string",
                    "note": "Electric Input Ratio (EIR) as a function of leaving chilled water temperature when in heating or simultaneous cool/heat mode and leaving condenser fluid temperature. EIR = 1/COP. curve = a + b*CWS + c*CWS**2 + d*TCond + e*TCond**2 + f*CWS*TCond If independent variable = EnteringCondenser, TCond = ECT If independent variable = LeavingCondenser, TCond = LCT CWS = leaving chilled water temperature(C) LCT = leaving condenser fluid temperature(C) ECT = entering condenser fluid temperature(C)",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ]
                },
                "heating_mode_electric_input_to_cooling_output_ratio_function_of_part_load_ratio_curve_name": {
                    "type": "string",
                    "note": "Electric Input Ratio (EIR) as a function of Part Load Ratio (PLR) when in heating or simultaneous cool/heat mode EIR = 1/COP Bicubic = a + b*LCT + c*LCT**2 + d*PLR + e*PLR**2 + f*LCT*PLR + g*0 + h*PLR**3 + i*0 + j*0 Normally, a bicubic curve here should be in terms of LCT rather than ECT Also, a bicubic curve is more applicable for variable-speed compressor motor drives or Quadratic = a + b*PLR + c*PLR**2 PLR = part load ratio (cooling load/steady-state capacity) LCT = leaving condenser fluid temperature(C) ECT = entering condenser fluid temperature(C)",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions",
                        "UnivariateFunctions"
                    ]
                },
                "heating_mode_cooling_capacity_optimum_part_load_ratio": {
                    "type": "number",
                    "note": "Optimum part load ratio where the chiller is most efficient when in heating or simultaneous cool/heat mode. Must be greater than or equal to the Minimum Part Load Ratio and less than or equal to the Maximum Part Load Ratio. The Min/Max PLR are taken from their associated EIR-FPLR curve references.",
                    "exclusiveMinimum": 0.0,
                    "default": 1.0
                },
                "sizing_factor": {
                    "type": "number",
                    "note": "Multiplies the autosized capacity and flow rates",
                    "exclusiveMinimum": 0.0,
                    "default": 1.0
                }
            },
            "required": [
                "reference_cooling_mode_evaporator_capacity",
                "reference_cooling_mode_cop",
                "cooling_mode_cooling_capacity_function_of_temperature_curve_name",
                "cooling_mode_electric_input_to_cooling_output_ratio_function_of_temperature_curve_name",
                "cooling_mode_electric_input_to_cooling_output_ratio_function_of_part_load_ratio_curve_name",
                "heating_mode_cooling_capacity_function_of_temperature_curve_name",
                "heating_mode_electric_input_to_cooling_output_ratio_function_of_temperature_curve_name",
                "heating_mode_electric_input_to_cooling_output_ratio_function_of_part_load_ratio_curve_name"
            ]
        }
    },
    "group": "Plant Heating and Cooling Equipment",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "ChillerHeaterEIRNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "reference_cooling_mode_evaporator_capacity": {
                "field_name": "Reference Cooling Mode Evaporator Capacity",
                "field_type": "n"
            },
            "reference_cooling_mode_cop": {
                "field_name": "Reference Cooling Mode COP",
                "field_type": "n"
            },
            "reference_cooling_mode_leaving_chilled_water_temperature": {
                "field_name": "Reference Cooling Mode Leaving Chilled Water Temperature",
                "field_type": "n"
            },
            "reference_cooling_mode_entering_condenser_fluid_temperature": {
                "field_name": "Reference Cooling Mode Entering Condenser Fluid Temperature",
                "field_type": "n"
            },
            "reference_cooling_mode_leaving_condenser_water_temperature": {
                "field_name": "Reference Cooling Mode Leaving Condenser Water Temperature",
                "field_type": "n"
            },
            "reference_heating_mode_cooling_capacity_ratio": {
                "field_name": "Reference Heating Mode Cooling Capacity Ratio",
                "field_type": "n"
            },
            "reference_heating_mode_cooling_power_input_ratio": {
                "field_name": "Reference Heating Mode Cooling Power Input Ratio",
                "field_type": "n"
            },
            "reference_heating_mode_leaving_chilled_water_temperature": {
                "field_name": "Reference Heating Mode Leaving Chilled Water Temperature",
                "field_type": "n"
            },
            "reference_heating_mode_leaving_condenser_water_temperature": {
                "field_name": "Reference Heating Mode Leaving Condenser Water Temperature",
                "field_type": "n"
            },
            "reference_heating_mode_entering_condenser_fluid_temperature": {
                "field_name": "Reference Heating Mode Entering Condenser Fluid Temperature",
                "field_type": "n"
            },
            "heating_mode_entering_chilled_water_temperature_low_limit": {
                "field_name": "Heating Mode Entering Chilled Water Temperature Low Limit",
                "field_type": "n"
            },
            "chilled_water_flow_mode_type": {
                "field_name": "Chilled Water Flow Mode Type",
                "field_type": "a"
            },
            "design_chilled_water_flow_rate": {
                "field_name": "Design Chilled Water Flow Rate",
                "field_type": "n"
            },
            "design_condenser_water_flow_rate": {
                "field_name": "Design Condenser Water Flow Rate",
                "field_type": "n"
            },
            "design_hot_water_flow_rate": {
                "field_name": "Design Hot Water Flow Rate",
                "field_type": "n"
            },
            "compressor_motor_efficiency": {
                "field_name": "Compressor Motor Efficiency",
                "field_type": "n"
            },
            "condenser_type": {
                "field_name": "Condenser Type",
                "field_type": "a"
            },
            "cooling_mode_temperature_curve_condenser_water_independent_variable": {
                "field_name": "Cooling Mode Temperature Curve Condenser Water Independent Variable",
                "field_type": "a"
            },
            "cooling_mode_cooling_capacity_function_of_temperature_curve_name": {
                "field_name": "Cooling Mode Cooling Capacity Function of Temperature Curve Name",
                "field_type": "a"
            },
            "cooling_mode_electric_input_to_cooling_output_ratio_function_of_temperature_curve_name": {
                "field_name": "Cooling Mode Electric Input to Cooling Output Ratio Function of Temperature Curve Name",
                "field_type": "a"
            },
            "cooling_mode_electric_input_to_cooling_output_ratio_function_of_part_load_ratio_curve_name": {
                "field_name": "Cooling Mode Electric Input to Cooling Output Ratio Function of Part Load Ratio Curve Name",
                "field_type": "a"
            },
            "cooling_mode_cooling_capacity_optimum_part_load_ratio": {
                "field_name": "Cooling Mode Cooling Capacity Optimum Part Load Ratio",
                "field_type": "n"
            },
            "heating_mode_temperature_curve_condenser_water_independent_variable": {
                "field_name": "Heating Mode Temperature Curve Condenser Water Independent Variable",
                "field_type": "a"
            },
            "heating_mode_cooling_capacity_function_of_temperature_curve_name": {
                "field_name": "Heating Mode Cooling Capacity Function of Temperature Curve Name",
                "field_type": "a"
            },
            "heating_mode_electric_input_to_cooling_output_ratio_function_of_temperature_curve_name": {
                "field_name": "Heating Mode Electric Input to Cooling Output Ratio Function of Temperature Curve Name",
                "field_type": "a"
            },
            "heating_mode_electric_input_to_cooling_output_ratio_function_of_part_load_ratio_curve_name": {
                "field_name": "Heating Mode Electric Input to Cooling Output Ratio Function of Part Load Ratio Curve Name",
                "field_type": "a"
            },
            "heating_mode_cooling_capacity_optimum_part_load_ratio": {
                "field_name": "Heating Mode Cooling Capacity Optimum Part Load Ratio",
                "field_type": "n"
            },
            "sizing_factor": {
                "field_name": "Sizing Factor",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "reference_cooling_mode_evaporator_capacity",
            "reference_cooling_mode_cop",
            "reference_cooling_mode_leaving_chilled_water_temperature",
            "reference_cooling_mode_entering_condenser_fluid_temperature",
            "reference_cooling_mode_leaving_condenser_water_temperature",
            "reference_heating_mode_cooling_capacity_ratio",
            "reference_heating_mode_cooling_power_input_ratio",
            "reference_heating_mode_leaving_chilled_water_temperature",
            "reference_heating_mode_leaving_condenser_water_temperature",
            "reference_heating_mode_entering_condenser_fluid_temperature",
            "heating_mode_entering_chilled_water_temperature_low_limit",
            "chilled_water_flow_mode_type",
            "design_chilled_water_flow_rate",
            "design_condenser_water_flow_rate",
            "design_hot_water_flow_rate",
            "compressor_motor_efficiency",
            "condenser_type",
            "cooling_mode_temperature_curve_condenser_water_independent_variable",
            "cooling_mode_cooling_capacity_function_of_temperature_curve_name",
            "cooling_mode_electric_input_to_cooling_output_ratio_function_of_temperature_curve_name",
            "cooling_mode_electric_input_to_cooling_output_ratio_function_of_part_load_ratio_curve_name",
            "cooling_mode_cooling_capacity_optimum_part_load_ratio",
            "heating_mode_temperature_curve_condenser_water_independent_variable",
            "heating_mode_cooling_capacity_function_of_temperature_curve_name",
            "heating_mode_electric_input_to_cooling_output_ratio_function_of_temperature_curve_name",
            "heating_mode_electric_input_to_cooling_output_ratio_function_of_part_load_ratio_curve_name",
            "heating_mode_cooling_capacity_optimum_part_load_ratio",
            "sizing_factor"
        ],
        "alphas": {
            "fields": [
                "name",
                "chilled_water_flow_mode_type",
                "condenser_type",
                "cooling_mode_temperature_curve_condenser_water_independent_variable",
                "cooling_mode_cooling_capacity_function_of_temperature_curve_name",
                "cooling_mode_electric_input_to_cooling_output_ratio_function_of_temperature_curve_name",
                "cooling_mode_electric_input_to_cooling_output_ratio_function_of_part_load_ratio_curve_name",
                "heating_mode_temperature_curve_condenser_water_independent_variable",
                "heating_mode_cooling_capacity_function_of_temperature_curve_name",
                "heating_mode_electric_input_to_cooling_output_ratio_function_of_temperature_curve_name",
                "heating_mode_electric_input_to_cooling_output_ratio_function_of_part_load_ratio_curve_name"
            ]
        },
        "numerics": {
            "fields": [
                "reference_cooling_mode_evaporator_capacity",
                "reference_cooling_mode_cop",
                "reference_cooling_mode_leaving_chilled_water_temperature",
                "reference_cooling_mode_entering_condenser_fluid_temperature",
                "reference_cooling_mode_leaving_condenser_water_temperature",
                "reference_heating_mode_cooling_capacity_ratio",
                "reference_heating_mode_cooling_power_input_ratio",
                "reference_heating_mode_leaving_chilled_water_temperature",
                "reference_heating_mode_leaving_condenser_water_temperature",
                "reference_heating_mode_entering_condenser_fluid_temperature",
                "heating_mode_entering_chilled_water_temperature_low_limit",
                "design_chilled_water_flow_rate",
                "design_condenser_water_flow_rate",
                "design_hot_water_flow_rate",
                "compressor_motor_efficiency",
                "cooling_mode_cooling_capacity_optimum_part_load_ratio",
                "heating_mode_cooling_capacity_optimum_part_load_ratio",
                "sizing_factor"
            ]
        }
    },
    "type": "object",
    "memo": "This chiller model is a generic chiller-heater where the cooling mode performance is a function of condenser entering or leaving fluid temperature and the heating mode performance is typically a function of condenser leaving fluid temperature. Performance at off-reference conditions is modeled using three polynomial equations per mode. Six curve objects are required.",
    "min_fields": 29.0
}
```
