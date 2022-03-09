```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "gross_rated_total_cooling_capacity": {
                    "note": "Total cooling capacity not accounting for the effect of supply air fan heat gross capacity excluding supply air fan heat rating point: air entering the cooling coil at 26.7 C dry-bulb/19.4 C wet-bulb, and air entering the outdoor condenser coil at 35 C dry-bulb/23.9 C wet-bulb",
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
                "gross_rated_sensible_heat_ratio": {
                    "note": "Rated sensible heat ratio (gross sensible capacity/gross total capacity) sensible and total capacities do not include supply fan heat",
                    "anyOf": [
                        {
                            "type": "number",
                            "minimum": 0.5,
                            "maximum": 1.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "Autosize"
                            ]
                        }
                    ]
                },
                "gross_rated_cooling_cop": {
                    "type": "number",
                    "note": "Gross cooling capacity divided by power input to the compressor and outdoor fan, does not include supply fan heat or supply fan electrical energy input",
                    "units": "W/W",
                    "exclusiveMinimum": 0.0,
                    "default": 3.0
                },
                "rated_air_flow_rate": {
                    "units": "m3/s",
                    "note": "Flow rate corresponding to Rated total Cooling capacity, Rated SHR and Rated COP",
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
                "fraction_of_air_flow_bypassed_around_coil": {
                    "type": "number",
                    "minimum": 0.0,
                    "exclusiveMaximum": 1.0,
                    "default": 0.0,
                    "note": "Fraction of Rated Air Flow Rate which bypasses the cooling coil in this performance mode. The remaining portion of the flow should be between 0.00004027 m3/s and .00006041 m3/s per watt of rated total cooling capacity. This is used to model face-split coils on multi-stage units or bypass dampers. If total flow rate varies during simulation, the same fraction is bypassed."
                },
                "total_cooling_capacity_function_of_temperature_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ],
                    "note": "curve = a + b*wb + c*wb**2 + d*edb + e*edb**2 + f*wb*edb wb = entering wet-bulb temperature (C) edb = dry-bulb temperature seen by the condenser (C)"
                },
                "total_cooling_capacity_function_of_flow_fraction_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "quadratic curve = a + b*ff + c*ff**2 cubic curve = a + b*ff + c*ff**2 + d*ff**3 ff = fraction of the full load flow"
                },
                "energy_input_ratio_function_of_temperature_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ],
                    "note": "curve = a + b*wb + c*wb**2 + d*edb + e*edb**2 + f*wb*edb wb = entering wet-bulb temperature (C) edb = dry-bulb temperature seen by the condenser (C)"
                },
                "energy_input_ratio_function_of_flow_fraction_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "quadratic curve = a + b*ff + c*ff**2 cubic curve = a + b*ff + c*ff**2 + d*ff**3 ff = fraction of the full load flow"
                },
                "part_load_fraction_correlation_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "quadratic curve = a + b*PLR + c*PLR**2 cubic curve = a + b*PLR + c*PLR**2 + d*PLR**3 PLR = part load ratio (cooling load/steady state capacity)"
                },
                "nominal_time_for_condensate_removal_to_begin": {
                    "type": "number",
                    "units": "s",
                    "minimum": 0.0,
                    "maximum": 3000.0,
                    "default": 0.0,
                    "note": "The nominal time for condensate to begin leaving the coil's condensate drain line at the coil's rated air flow rate and temperature conditions. Nominal time is equal to the ratio of the energy of the coil's maximum condensate holding capacity (J) to the coil's steady state latent capacity (W). Suggested value is 1000; zero value means latent degradation model is disabled."
                },
                "ratio_of_initial_moisture_evaporation_rate_and_steady_state_latent_capacity": {
                    "type": "number",
                    "units": "dimensionless",
                    "minimum": 0.0,
                    "maximum": 5.0,
                    "default": 0.0,
                    "note": "Ratio of the initial moisture evaporation rate from the cooling coil (when the compressor first turns off) and the coil's steady state latent capacity at rated air flow rate and temperature conditions. Suggested value is 1.5; zero value means latent degradation model is disabled."
                },
                "maximum_cycling_rate": {
                    "type": "number",
                    "units": "cycles/hr",
                    "minimum": 0.0,
                    "maximum": 5.0,
                    "default": 0.0,
                    "note": "The maximum on-off cycling rate for the compressor, which occurs at 50% run time fraction. Suggested value is 3; zero value means latent degradation model is disabled."
                },
                "latent_capacity_time_constant": {
                    "type": "number",
                    "units": "s",
                    "minimum": 0.0,
                    "maximum": 500.0,
                    "default": 0.0,
                    "note": "Time constant for the cooling coil's latent capacity to reach steady state after startup. Suggested value is 45; zero value means latent degradation model is disabled."
                },
                "condenser_air_inlet_node_name": {
                    "type": "string",
                    "note": "Enter the name of an outdoor air node. This node name is also specified in an OutdoorAir:Node or OutdoorAir:NodeList object."
                },
                "condenser_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "AirCooled",
                        "EvaporativelyCooled"
                    ],
                    "default": "AirCooled"
                },
                "evaporative_condenser_effectiveness": {
                    "type": "number",
                    "units": "dimensionless",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.9
                },
                "evaporative_condenser_air_flow_rate": {
                    "units": "m3/s",
                    "note": "Used to calculate evaporative condenser water use",
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
                "evaporative_condenser_pump_rated_power_consumption": {
                    "units": "W",
                    "default": 0.0,
                    "note": "Rated power consumed by the evaporative condenser's water pump",
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
                "sensible_heat_ratio_function_of_temperature_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ],
                    "note": "curve = a + b*wb + c*wb**2 + d*db + e*db**2 + f*wb*db wb = entering wet-bulb temperature seen by the DX cooling coil (C) db = entering dry-bulb temperature seen by the DX cooling coil (C) entering temperature can be outside air or pretreated air."
                },
                "sensible_heat_ratio_function_of_flow_fraction_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "quadratic curve = a + b*ff + c*ff**2 cubic curve = a + b*ff + c*ff**2 + d*ff**3 ff = fraction of the full load flow"
                }
            },
            "required": [
                "gross_rated_total_cooling_capacity",
                "gross_rated_sensible_heat_ratio",
                "rated_air_flow_rate",
                "total_cooling_capacity_function_of_temperature_curve_name",
                "total_cooling_capacity_function_of_flow_fraction_curve_name",
                "energy_input_ratio_function_of_temperature_curve_name",
                "energy_input_ratio_function_of_flow_fraction_curve_name",
                "part_load_fraction_correlation_curve_name"
            ]
        }
    },
    "group": "Coils",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "CoilPerformanceDX"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "gross_rated_total_cooling_capacity": {
                "field_name": "Gross Rated Total Cooling Capacity",
                "field_type": "n"
            },
            "gross_rated_sensible_heat_ratio": {
                "field_name": "Gross Rated Sensible Heat Ratio",
                "field_type": "n"
            },
            "gross_rated_cooling_cop": {
                "field_name": "Gross Rated Cooling COP",
                "field_type": "n"
            },
            "rated_air_flow_rate": {
                "field_name": "Rated Air Flow Rate",
                "field_type": "n"
            },
            "fraction_of_air_flow_bypassed_around_coil": {
                "field_name": "Fraction of Air Flow Bypassed Around Coil",
                "field_type": "n"
            },
            "total_cooling_capacity_function_of_temperature_curve_name": {
                "field_name": "Total Cooling Capacity Function of Temperature Curve Name",
                "field_type": "a"
            },
            "total_cooling_capacity_function_of_flow_fraction_curve_name": {
                "field_name": "Total Cooling Capacity Function of Flow Fraction Curve Name",
                "field_type": "a"
            },
            "energy_input_ratio_function_of_temperature_curve_name": {
                "field_name": "Energy Input Ratio Function of Temperature Curve Name",
                "field_type": "a"
            },
            "energy_input_ratio_function_of_flow_fraction_curve_name": {
                "field_name": "Energy Input Ratio Function of Flow Fraction Curve Name",
                "field_type": "a"
            },
            "part_load_fraction_correlation_curve_name": {
                "field_name": "Part Load Fraction Correlation Curve Name",
                "field_type": "a"
            },
            "nominal_time_for_condensate_removal_to_begin": {
                "field_name": "Nominal Time for Condensate Removal to Begin",
                "field_type": "n"
            },
            "ratio_of_initial_moisture_evaporation_rate_and_steady_state_latent_capacity": {
                "field_name": "Ratio of Initial Moisture Evaporation Rate and Steady State Latent Capacity",
                "field_type": "n"
            },
            "maximum_cycling_rate": {
                "field_name": "Maximum Cycling Rate",
                "field_type": "n"
            },
            "latent_capacity_time_constant": {
                "field_name": "Latent Capacity Time Constant",
                "field_type": "n"
            },
            "condenser_air_inlet_node_name": {
                "field_name": "Condenser Air Inlet Node Name",
                "field_type": "a"
            },
            "condenser_type": {
                "field_name": "Condenser Type",
                "field_type": "a"
            },
            "evaporative_condenser_effectiveness": {
                "field_name": "Evaporative Condenser Effectiveness",
                "field_type": "n"
            },
            "evaporative_condenser_air_flow_rate": {
                "field_name": "Evaporative Condenser Air Flow Rate",
                "field_type": "n"
            },
            "evaporative_condenser_pump_rated_power_consumption": {
                "field_name": "Evaporative Condenser Pump Rated Power Consumption",
                "field_type": "n"
            },
            "sensible_heat_ratio_function_of_temperature_curve_name": {
                "field_name": "Sensible Heat Ratio Function of Temperature Curve Name",
                "field_type": "a"
            },
            "sensible_heat_ratio_function_of_flow_fraction_curve_name": {
                "field_name": "Sensible Heat Ratio Function of Flow Fraction Curve Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "gross_rated_total_cooling_capacity",
            "gross_rated_sensible_heat_ratio",
            "gross_rated_cooling_cop",
            "rated_air_flow_rate",
            "fraction_of_air_flow_bypassed_around_coil",
            "total_cooling_capacity_function_of_temperature_curve_name",
            "total_cooling_capacity_function_of_flow_fraction_curve_name",
            "energy_input_ratio_function_of_temperature_curve_name",
            "energy_input_ratio_function_of_flow_fraction_curve_name",
            "part_load_fraction_correlation_curve_name",
            "nominal_time_for_condensate_removal_to_begin",
            "ratio_of_initial_moisture_evaporation_rate_and_steady_state_latent_capacity",
            "maximum_cycling_rate",
            "latent_capacity_time_constant",
            "condenser_air_inlet_node_name",
            "condenser_type",
            "evaporative_condenser_effectiveness",
            "evaporative_condenser_air_flow_rate",
            "evaporative_condenser_pump_rated_power_consumption",
            "sensible_heat_ratio_function_of_temperature_curve_name",
            "sensible_heat_ratio_function_of_flow_fraction_curve_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "total_cooling_capacity_function_of_temperature_curve_name",
                "total_cooling_capacity_function_of_flow_fraction_curve_name",
                "energy_input_ratio_function_of_temperature_curve_name",
                "energy_input_ratio_function_of_flow_fraction_curve_name",
                "part_load_fraction_correlation_curve_name",
                "condenser_air_inlet_node_name",
                "condenser_type",
                "sensible_heat_ratio_function_of_temperature_curve_name",
                "sensible_heat_ratio_function_of_flow_fraction_curve_name"
            ]
        },
        "numerics": {
            "fields": [
                "gross_rated_total_cooling_capacity",
                "gross_rated_sensible_heat_ratio",
                "gross_rated_cooling_cop",
                "rated_air_flow_rate",
                "fraction_of_air_flow_bypassed_around_coil",
                "nominal_time_for_condensate_removal_to_begin",
                "ratio_of_initial_moisture_evaporation_rate_and_steady_state_latent_capacity",
                "maximum_cycling_rate",
                "latent_capacity_time_constant",
                "evaporative_condenser_effectiveness",
                "evaporative_condenser_air_flow_rate",
                "evaporative_condenser_pump_rated_power_consumption"
            ]
        }
    },
    "type": "object",
    "memo": "Used to specify DX cooling coil performance for one mode of operation for a Coil:Cooling:DX:TwoStageWithHumidityControlMode object which may reference one to four CoilPerformance:DX:Cooling objects depending on the specified number of stages and dehumidification modes. In nearly all cases, the Rated Air Flow Rate will be the same for all performance objects associated with a given coil. If bypass is specified, the Rated Air Flow Rate includes both the bypassed flow and the flow through the active part of the coil.",
    "min_fields": 11.0
}
```
