```
{
    "Coil:Cooling:DX:CurveFit:Speed": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "gross_total_cooling_capacity_fraction": {
                        "type": "number",
                        "note": "Ratio of capacity at this speed to the operating mode Rated Gross Total Cooling Capacity",
                        "exclusiveMinimum": 0.0
                    },
                    "evaporator_air_flow_rate_fraction": {
                        "type": "number",
                        "note": "Ratio of capacity at this speed to the operating mode Rated Evaporator Air Flow Rate",
                        "exclusiveMinimum": 0.0
                    },
                    "condenser_air_flow_rate_fraction": {
                        "type": "number",
                        "note": "Ratio of condenser air flow at this speed to the operating mode Rated Condenser Air Flow Rate",
                        "exclusiveMinimum": 0.0
                    },
                    "gross_sensible_heat_ratio": {
                        "note": "Rated sensible heat ratio (gross sensible capacity/gross total capacity) sensible and total capacities do not include supply fan heat",
                        "default": "Autosize",
                        "anyOf": [
                            {
                                "type": "number",
                                "minimum": 0.1,
                                "maximum": 1.0
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
                    "gross_cooling_cop": {
                        "type": "number",
                        "note": "Gross cooling capacity divided by power input to the compressor and condenser fan. Does not include supply fan heat or supply fan electrical energy input.",
                        "units": "W/W",
                        "exclusiveMinimum": 0.0,
                        "default": 3.0
                    },
                    "active_fraction_of_coil_face_area": {
                        "type": "number",
                        "note": "The fraction of the cooling coil face which is actively cooled at this speed. For non-split-face coils, this should be 1.0.",
                        "exclusiveMinimum": 0.0,
                        "maximum": 1.0,
                        "default": 1.0
                    },
                    "rated_evaporator_fan_power_per_volume_flow_rate": {
                        "type": "number",
                        "note": "Enter the evaporator fan power per air volume flow rate at the rated test conditions. The test conditions vary external static pressure based on total cooling capacity. This value is only used to calculate Seasonal Energy Efficiency Ratio (SEER), and the Standard Rating (Net) Cooling Capacity which will be outputs in the EnergyPlus eio file. This value is not used for modeling the evaporator fan during simulations.",
                        "units": "W/(m3/s)",
                        "minimum": 0.0,
                        "maximum": 1250.0,
                        "default": 773.3
                    },
                    "evaporative_condenser_pump_power_fraction": {
                        "type": "number",
                        "note": "Ratio of evaporative condenser pump power at this speed to the operating mode Nominal Evaporative Condenser Pump Power",
                        "exclusiveMinimum": 0.0,
                        "default": 1.0
                    },
                    "evaporative_condenser_effectiveness": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.9
                    },
                    "total_cooling_capacity_modifier_function_of_temperature_curve_name": {
                        "type": "string",
                        "note": "biquadratic curve = a + b*wb + c*wb**2 + d*edb + e*edb**2 + f*wb*edb quadratic curve = a + b*edb + c*edb**2 wb = entering wet-bulb temperature (C) edb = dry-bulb temperature seen by the condenser (C)",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions",
                            "UnivariateFunctions"
                        ]
                    },
                    "total_cooling_capacity_modifier_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "note": "quadratic curve = a + b*ff + c*ff**2 cubic curve = a + b*ff + c*ff**2 + d*ff**3 ff = Fraction of the full load flow",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ]
                    },
                    "energy_input_ratio_modifier_function_of_temperature_curve_name": {
                        "type": "string",
                        "note": "curve = a + b*wb + c*wb**2 + d*edb + e*edb**2 + f*wb*edb wb = entering wet-bulb temperature (C) edb = dry-bulb temperature seen by the condenser (C)",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions",
                            "UnivariateFunctions"
                        ]
                    },
                    "energy_input_ratio_modifier_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "note": "quadratic curve = a + b*ff + c*ff**2 cubic curve = a + b*ff + c*ff**2 + d*ff**3 ff = Fraction of the full load flow",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ]
                    },
                    "part_load_fraction_correlation_curve_name": {
                        "type": "string",
                        "note": "quadratic curve = a + b*PLR + c*PLR**2 cubic curve = a + b*PLR + c*PLR**2 + d*PLR**3 PLR = part load ratio (cooling load/steady state capacity)",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ]
                    },
                    "rated_waste_heat_fraction_of_power_input": {
                        "type": "number",
                        "note": "Recoverable waste heat at full load and rated conditions",
                        "units": "dimensionless",
                        "exclusiveMinimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.2
                    },
                    "waste_heat_modifier_function_of_temperature_curve_name": {
                        "type": "string",
                        "note": "curve = a + b*cdb + c*cdb**2 + d*edb + e*edb**2 + f*cdb*edb cdb = entering condenser dry-bulb temperature (C) edb = entering coil dry-bulb temperature (C)",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ]
                    },
                    "sensible_heat_ratio_modifier_function_of_temperature_curve_name": {
                        "type": "string",
                        "note": "curve = a + b*wb + c*wb**2 + d*db + e*db**2 + f*wb*db wb = entering wet-bulb temperature seen by the DX cooling coil (C) db = entering dry-bulb temperature seen by the DX cooling coil (C) entering temperature can be outside air or pretreated air. If this curve is used and the Sensible Heat Ratio Modifier Function of Flow Fraction (SHRFFF) Curve Name is blank, the SHRFFF is assumed to be a constant value of 1.0.",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ]
                    },
                    "sensible_heat_ratio_modifier_function_of_flow_fraction_curve_name": {
                        "type": "string",
                        "note": "quadratic curve = a + b*ff + c*ff**2 cubic curve = a + b*ff + c*ff**2 + d*ff**3 ff = fraction of the full load flow If this curve is used and the Sensible Heat Ratio Modifier Function of Temperature Curve Name (SHRFT) Curve Name is blank, the SHRFT is assumed to be a constant value of 1.0.",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ]
                    }
                },
                "required": [
                    "gross_total_cooling_capacity_fraction",
                    "evaporator_air_flow_rate_fraction"
                ]
            }
        },
        "group": "Coils",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "DXCoolingSpeedNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "gross_total_cooling_capacity_fraction": {
                    "field_name": "Gross Total Cooling Capacity Fraction",
                    "field_type": "n"
                },
                "evaporator_air_flow_rate_fraction": {
                    "field_name": "Evaporator Air Flow Rate Fraction",
                    "field_type": "n"
                },
                "condenser_air_flow_rate_fraction": {
                    "field_name": "Condenser Air Flow Rate Fraction",
                    "field_type": "n"
                },
                "gross_sensible_heat_ratio": {
                    "field_name": "Gross Sensible Heat Ratio",
                    "field_type": "n"
                },
                "gross_cooling_cop": {
                    "field_name": "Gross Cooling COP",
                    "field_type": "n"
                },
                "active_fraction_of_coil_face_area": {
                    "field_name": "Active Fraction of Coil Face Area",
                    "field_type": "n"
                },
                "rated_evaporator_fan_power_per_volume_flow_rate": {
                    "field_name": "Rated Evaporator Fan Power Per Volume Flow Rate",
                    "field_type": "n"
                },
                "evaporative_condenser_pump_power_fraction": {
                    "field_name": "Evaporative Condenser Pump Power Fraction",
                    "field_type": "n"
                },
                "evaporative_condenser_effectiveness": {
                    "field_name": "Evaporative Condenser Effectiveness",
                    "field_type": "n"
                },
                "total_cooling_capacity_modifier_function_of_temperature_curve_name": {
                    "field_name": "Total Cooling Capacity Modifier Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "total_cooling_capacity_modifier_function_of_air_flow_fraction_curve_name": {
                    "field_name": "Total Cooling Capacity Modifier Function of Air Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "energy_input_ratio_modifier_function_of_temperature_curve_name": {
                    "field_name": "Energy Input Ratio Modifier Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "energy_input_ratio_modifier_function_of_air_flow_fraction_curve_name": {
                    "field_name": "Energy Input Ratio Modifier Function of Air Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "part_load_fraction_correlation_curve_name": {
                    "field_name": "Part Load Fraction Correlation Curve Name",
                    "field_type": "a"
                },
                "rated_waste_heat_fraction_of_power_input": {
                    "field_name": "Rated Waste Heat Fraction of Power Input",
                    "field_type": "n"
                },
                "waste_heat_modifier_function_of_temperature_curve_name": {
                    "field_name": "Waste Heat Modifier Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "sensible_heat_ratio_modifier_function_of_temperature_curve_name": {
                    "field_name": "Sensible Heat Ratio Modifier Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "sensible_heat_ratio_modifier_function_of_flow_fraction_curve_name": {
                    "field_name": "Sensible Heat Ratio Modifier Function of Flow Fraction Curve Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "gross_total_cooling_capacity_fraction",
                "evaporator_air_flow_rate_fraction",
                "condenser_air_flow_rate_fraction",
                "gross_sensible_heat_ratio",
                "gross_cooling_cop",
                "active_fraction_of_coil_face_area",
                "rated_evaporator_fan_power_per_volume_flow_rate",
                "evaporative_condenser_pump_power_fraction",
                "evaporative_condenser_effectiveness",
                "total_cooling_capacity_modifier_function_of_temperature_curve_name",
                "total_cooling_capacity_modifier_function_of_air_flow_fraction_curve_name",
                "energy_input_ratio_modifier_function_of_temperature_curve_name",
                "energy_input_ratio_modifier_function_of_air_flow_fraction_curve_name",
                "part_load_fraction_correlation_curve_name",
                "rated_waste_heat_fraction_of_power_input",
                "waste_heat_modifier_function_of_temperature_curve_name",
                "sensible_heat_ratio_modifier_function_of_temperature_curve_name",
                "sensible_heat_ratio_modifier_function_of_flow_fraction_curve_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "total_cooling_capacity_modifier_function_of_temperature_curve_name",
                    "total_cooling_capacity_modifier_function_of_air_flow_fraction_curve_name",
                    "energy_input_ratio_modifier_function_of_temperature_curve_name",
                    "energy_input_ratio_modifier_function_of_air_flow_fraction_curve_name",
                    "part_load_fraction_correlation_curve_name",
                    "waste_heat_modifier_function_of_temperature_curve_name",
                    "sensible_heat_ratio_modifier_function_of_temperature_curve_name",
                    "sensible_heat_ratio_modifier_function_of_flow_fraction_curve_name"
                ]
            },
            "numerics": {
                "fields": [
                    "gross_total_cooling_capacity_fraction",
                    "evaporator_air_flow_rate_fraction",
                    "condenser_air_flow_rate_fraction",
                    "gross_sensible_heat_ratio",
                    "gross_cooling_cop",
                    "active_fraction_of_coil_face_area",
                    "rated_evaporator_fan_power_per_volume_flow_rate",
                    "evaporative_condenser_pump_power_fraction",
                    "evaporative_condenser_effectiveness",
                    "rated_waste_heat_fraction_of_power_input"
                ]
            }
        },
        "type": "object",
        "memo": "DX cooling coil performance for a single speed within a single operating mode.",
        "min_fields": 15.0
    }
}
```
