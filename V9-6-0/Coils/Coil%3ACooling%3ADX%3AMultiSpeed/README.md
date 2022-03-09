```
{
    "Coil:Cooling:DX:MultiSpeed": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "availability_schedule_name": {
                        "type": "string",
                        "note": "Availability schedule name for this system. Schedule value > 0 means the system is available. If this field is blank, the system is always available.",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "air_inlet_node_name": {
                        "type": "string"
                    },
                    "air_outlet_node_name": {
                        "type": "string"
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
                    "minimum_outdoor_dry_bulb_temperature_for_compressor_operation": {
                        "type": "number",
                        "default": -25.0,
                        "units": "C"
                    },
                    "supply_water_storage_tank_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "WaterStorageTankNames"
                        ]
                    },
                    "condensate_collection_water_storage_tank_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "WaterStorageTankNames"
                        ]
                    },
                    "apply_part_load_fraction_to_speeds_greater_than_1": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "No"
                    },
                    "apply_latent_degradation_to_speeds_greater_than_1": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "No"
                    },
                    "crankcase_heater_capacity": {
                        "type": "number",
                        "minimum": 0.0,
                        "default": 0.0,
                        "units": "W",
                        "ip-units": "W"
                    },
                    "maximum_outdoor_dry_bulb_temperature_for_crankcase_heater_operation": {
                        "type": "number",
                        "minimum": 0.0,
                        "default": 10.0,
                        "units": "C"
                    },
                    "basin_heater_capacity": {
                        "type": "number",
                        "units": "W/K",
                        "minimum": 0.0,
                        "default": 0.0,
                        "note": "This field is only used for Condenser Type = EvaporativelyCooled and for periods when the basin heater is available (field Basin Heater Operating Schedule Name). For this situation, the heater maintains the basin water temperature at the basin heater setpoint temperature when the outdoor air temperature falls below the setpoint temperature. The basin heater only operates when the DX coil is off."
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
                    "fuel_type": {
                        "type": "string",
                        "enum": [
                            "Diesel",
                            "Electricity",
                            "FuelOilNo1",
                            "FuelOilNo2",
                            "Gasoline",
                            "NaturalGas",
                            "OtherFuel1",
                            "OtherFuel2",
                            "Propane"
                        ]
                    },
                    "number_of_speeds": {
                        "type": "number",
                        "minimum": 2.0,
                        "maximum": 4.0,
                        "note": "Enter the number of the following sets of data for coil capacity, SHR, COP, flow rate, and associated curves."
                    },
                    "speed_1_gross_rated_total_cooling_capacity": {
                        "note": "Total cooling capacity not accounting for the effect of supply air fan heat Gross capacity excluding supply air fan heat Rating point: air entering the cooling coil at 26.7 C dry-bulb/19.4 C wet-bulb, and air entering the outdoor condenser coil at 35 C dry-bulb/23.9 C wet-bulb Speed 1 is defined as low speed",
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
                    "speed_1_gross_rated_sensible_heat_ratio": {
                        "note": "Gross Rated Sensible Heat Ratio (gross sensible capacity/gross total capacity) Sensible and total capacities do not include supply fan heat",
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
                    "speed_1_gross_rated_cooling_cop": {
                        "type": "number",
                        "note": "Gross cooling capacity divided by power input to the compressor and outdoor fan, does not include supply fan heat or supply fan electrical energy input",
                        "units": "W/W",
                        "exclusiveMinimum": 0.0,
                        "default": 3.0
                    },
                    "speed_1_rated_air_flow_rate": {
                        "units": "m3/s",
                        "note": "Flow rate corresponding to rated total cooling capacity, rated SHR and rated COP should be between 0.00004027 m3/s and .00006041 m3/s per watt of rated total cooling capacity",
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
                    "speed_1_rated_evaporator_fan_power_per_volume_flow_rate": {
                        "type": "number",
                        "note": "Enter the evaporator fan power per air volume flow rate at the rated test conditions. The test conditions vary external static pressure based on total cooling capacity. This value is only used to calculate Seasonal Energy Efficiency Ratio (SEER), and the Standard Rating (Net) Cooling Capacity which will be outputs in the EnergyPlus eio file. This value is not used for modeling the evaporator fan during simulations.",
                        "units": "W/(m3/s)",
                        "minimum": 0.0,
                        "maximum": 1250.0,
                        "default": 773.3
                    },
                    "speed_1_total_cooling_capacity_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "curve = a + b*wb + c*wb**2 + d*edb + e*edb**2 + f*wb*edb wb = entering wet-bulb temperature (C) edb = dry-bulb temperature seen by the condenser (C)"
                    },
                    "speed_1_total_cooling_capacity_function_of_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "quadratic curve = a + b*ff + c*ff**2 cubic curve = a + b*ff + c*ff**2 + d*ff**3 ff = Fraction of the full load Flow"
                    },
                    "speed_1_energy_input_ratio_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "curve = a + b*wb + c*wb**2 + d*edb + e*edb**2 + f*wb*edb wb = entering wet-bulb temperature (C) edb = dry-bulb temperature seen by the condenser (C)"
                    },
                    "speed_1_energy_input_ratio_function_of_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "quadratic curve = a + b*ff + c*ff**2 cubic curve = a + b*ff + c*ff**2 + d*ff**3 ff = fraction of the full load flow"
                    },
                    "speed_1_part_load_fraction_correlation_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "quadratic curve = a + b*PLR + c*PLR**2 cubic curve = a + b*PLR + c*PLR**2 + d*PLR**3 PLR = part load ratio (cooling load/steady state capacity)"
                    },
                    "speed_1_nominal_time_for_condensate_removal_to_begin": {
                        "type": "number",
                        "units": "s",
                        "minimum": 0.0,
                        "maximum": 3000.0,
                        "default": 0.0,
                        "note": "The nominal time for condensate to begin leaving the coil's condensate drain line at the coil's rated air flow rate and temperature conditions. Nominal time is equal to the ratio of the energy of the coil's maximum condensate holding capacity (J) to the coil's steady state latent capacity (W). Suggested value is 1000; zero value means latent degradation model is disabled."
                    },
                    "speed_1_ratio_of_initial_moisture_evaporation_rate_and_steady_state_latent_capacity": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 5.0,
                        "default": 0.0,
                        "note": "Ratio of the initial moisture evaporation Rate from the Cooling Coil (when the compressor first turns off) and the Coil's steady state latent capacity at rated air flow rate and temperature conditions. Suggested value is 1.5; zero value means latent degradation model is disabled."
                    },
                    "speed_1_maximum_cycling_rate": {
                        "type": "number",
                        "units": "cycles/hr",
                        "minimum": 0.0,
                        "maximum": 5.0,
                        "default": 0.0,
                        "note": "The maximum on-off cycling rate for the compressor, which occurs at 50% run time fraction. Suggested value is 3; zero value means latent degradation model is disabled."
                    },
                    "speed_1_latent_capacity_time_constant": {
                        "type": "number",
                        "units": "s",
                        "minimum": 0.0,
                        "maximum": 500.0,
                        "default": 0.0,
                        "note": "Time constant for the cooling coil's latent capacity to reach steady state after startup. Suggested value is 45; zero value means latent degradation model is disabled."
                    },
                    "speed_1_rated_waste_heat_fraction_of_power_input": {
                        "type": "number",
                        "units": "dimensionless",
                        "exclusiveMinimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.2,
                        "note": "Recoverable waste heat at full load and rated conditions"
                    },
                    "speed_1_waste_heat_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "curve = a + b*odb + c*odb**2 + d*db + e*db**2 + f*odb*db odb = Outdoor air dry-bulb temperature (C) db = entering coil dry-bulb temperature (C)"
                    },
                    "speed_1_evaporative_condenser_effectiveness": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.9
                    },
                    "speed_1_evaporative_condenser_air_flow_rate": {
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
                    "speed_1_rated_evaporative_condenser_pump_power_consumption": {
                        "units": "W",
                        "note": "Rated power consumed by the evaporative condenser's water pump at high speed",
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
                    "speed_2_gross_rated_total_cooling_capacity": {
                        "note": "Total cooling capacity not accounting for the effect of supply air fan heat Gross capacity excluding supply air fan heat Rating point: air entering the cooling coil at 26.7 C dry-bulb/19.4 C wet-bulb, and air entering the outdoor condenser coil at 35 C dry-bulb/23.9 C wet-bulb",
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
                    "speed_2_gross_rated_sensible_heat_ratio": {
                        "note": "Gross Rated Sensible Heat Ratio (gross sensible capacity/gross total capacity) Sensible and total capacities do not include supply fan heat",
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
                    "speed_2_gross_rated_cooling_cop": {
                        "type": "number",
                        "note": "Gross cooling capacity divided by power input to the compressor and outdoor fan, does not include supply fan heat or supply fan electrical energy input",
                        "units": "W/W",
                        "exclusiveMinimum": 0.0,
                        "default": 3.0
                    },
                    "speed_2_rated_air_flow_rate": {
                        "units": "m3/s",
                        "note": "Flow rate corresponding to rated total cooling capacity, rated SHR and rated COP should be between 0.00004027 m3/s and .00006041 m3/s per watt of rated total cooling capacity for Speed 2.",
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
                    "speed_2_rated_evaporator_fan_power_per_volume_flow_rate": {
                        "type": "number",
                        "note": "Enter the evaporator fan power per air volume flow rate at the rated test conditions. The test conditions vary external static pressure based on total cooling capacity. This value is only used to calculate Seasonal Energy Efficiency Ratio (SEER), and the Standard Rating (Net) Cooling Capacity which will be outputs in the EnergyPlus eio file. This value is not used for modeling the evaporator fan during simulations.",
                        "units": "W/(m3/s)",
                        "minimum": 0.0,
                        "maximum": 1250.0,
                        "default": 773.3
                    },
                    "speed_2_total_cooling_capacity_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "curve = a + b*wb + c*wb**2 + d*edb + e*edb**2 + f*wb*edb wb = entering wet-bulb temperature (C) edb = dry-bulb temperature seen by the condenser (C)"
                    },
                    "speed_2_total_cooling_capacity_function_of_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "quadratic curve = a + b*ff + c*ff**2 cubic curve = a + b*ff + c*ff**2 + d*ff**3 ff = fraction of the full load flow"
                    },
                    "speed_2_energy_input_ratio_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "curve = a + b*wb + c*wb**2 + d*edb + e*edb**2 + f*wb*edb wb = entering wet-bulb temperature (C) edb = dry-bulb temperature seen by the condenser (C)"
                    },
                    "speed_2_energy_input_ratio_function_of_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "quadratic curve = a + b*ff + c*ff**2 cubic curve = a + b*ff + c*ff**2 + d*ff**3 ff = Fraction of the full load Flow"
                    },
                    "speed_2_part_load_fraction_correlation_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "quadratic curve = a + b*PLR + c*PLR**2 cubic curve = a + b*PLR + c*PLR**2 + d*PLR**3 PLR = part load ratio (Cooling load/steady state capacity)"
                    },
                    "speed_2_nominal_time_for_condensate_removal_to_begin": {
                        "type": "number",
                        "units": "s",
                        "minimum": 0.0,
                        "maximum": 3000.0,
                        "default": 0.0,
                        "note": "The nominal time for condensate to begin leaving the coil's condensate drain line at the coil's rated air flow rate and temperature conditions. Nominal time is equal to the ratio of the energy of the coil's maximum condensate holding capacity (J) to the coil's steady state latent capacity (W). Suggested value is 1000; zero value means latent degradation model is disabled."
                    },
                    "speed_2_ratio_of_initial_moisture_evaporation_rate_and_steady_state_latent_capacity": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 5.0,
                        "default": 0.0,
                        "note": "Ratio of the initial moisture evaporation rate from the cooling coil (when the compressor first turns off) and the coil's steady state latent capacity at rated air flow rate and temperature conditions. Suggested value is 1.5; zero value means latent degradation model is disabled."
                    },
                    "speed_2_maximum_cycling_rate": {
                        "type": "number",
                        "units": "cycles/hr",
                        "minimum": 0.0,
                        "maximum": 5.0,
                        "default": 0.0,
                        "note": "The maximum on-off cycling rate for the compressor, which occurs at 50% run time fraction. Suggested value is 3; zero value means latent degradation model is disabled."
                    },
                    "speed_2_latent_capacity_time_constant": {
                        "type": "number",
                        "units": "s",
                        "minimum": 0.0,
                        "maximum": 500.0,
                        "default": 0.0,
                        "note": "Time constant for the cooling coil's latent capacity to reach steady state after startup. Suggested value is 45; zero value means latent degradation model is disabled."
                    },
                    "speed_2_rated_waste_heat_fraction_of_power_input": {
                        "type": "number",
                        "units": "dimensionless",
                        "exclusiveMinimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.2,
                        "note": "Recoverable waste heat at full load and rated conditions"
                    },
                    "speed_2_waste_heat_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "curve = a + b*odb + c*odb**2 + d*db + e*db**2 + f*odb*db odb = Outdoor air dry-bulb temperature (C) db = entering coil dry-bulb temperature (C)"
                    },
                    "speed_2_evaporative_condenser_effectiveness": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.9
                    },
                    "speed_2_evaporative_condenser_air_flow_rate": {
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
                    "speed_2_rated_evaporative_condenser_pump_power_consumption": {
                        "units": "W",
                        "note": "Rated power consumed by the evaporative condenser's water pump at low speed",
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
                    "speed_3_gross_rated_total_cooling_capacity": {
                        "note": "Total cooling capacity not accounting for the effect of supply air fan heat Gross capacity excluding supply air fan heat Rating point: air entering the cooling coil at 26.7 C dry-bulb/19.4 C wet-bulb, and air entering the outdoor condenser coil at 35 C dry-bulb/23.9 C wet-bulb",
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
                    "speed_3_gross_rated_sensible_heat_ratio": {
                        "note": "Gross Rated Sensible Heat Ratio (gross sensible capacity/gross total capacity) Sensible and total capacities do not include supply fan heat",
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
                    "speed_3_gross_rated_cooling_cop": {
                        "type": "number",
                        "note": "Gross cooling capacity divided by power input to the compressor and outdoor fan, does not include supply fan heat or supply fan electrical energy input",
                        "units": "W/W",
                        "exclusiveMinimum": 0.0,
                        "default": 3.0
                    },
                    "speed_3_rated_air_flow_rate": {
                        "units": "m3/s",
                        "note": "Flow rate corresponding to rated total cooling capacity, rated SHR and rated COP should be between 0.00004027 m3/s and .00006041 m3/s per watt of rated total cooling capacity for Speed 3.",
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
                    "speed_3_rated_evaporator_fan_power_per_volume_flow_rate": {
                        "type": "number",
                        "note": "Enter the evaporator fan power per air volume flow rate at the rated test conditions. The test conditions vary external static pressure based on total cooling capacity. This value is only used to calculate Seasonal Energy Efficiency Ratio (SEER), and the Standard Rating (Net) Cooling Capacity which will be outputs in the EnergyPlus eio file. This value is not used for modeling the evaporator fan during simulations.",
                        "units": "W/(m3/s)",
                        "minimum": 0.0,
                        "maximum": 1250.0,
                        "default": 773.3
                    },
                    "speed_3_total_cooling_capacity_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "curve = a + b*wb + c*wb**2 + d*edb + e*edb**2 + f*wb*edb wb = entering wet-bulb temperature (C) edb = dry-bulb temperature seen by the condenser (C)"
                    },
                    "speed_3_total_cooling_capacity_function_of_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "quadratic curve = a + b*ff + c*ff**2 cubic curve = a + b*ff + c*ff**2 + d*ff**3 ff = fraction of the full load flow"
                    },
                    "speed_3_energy_input_ratio_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "curve = a + b*wb + c*wb**2 + d*edb + e*edb**2 + f*wb*edb wb = entering wet-bulb temperature (C) edb = dry-bulb temperature seen by the condenser (C)"
                    },
                    "speed_3_energy_input_ratio_function_of_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "quadratic curve = a + b*ff + c*ff**2 cubic curve = a + b*ff + c*ff**2 + d*ff**3 ff = fraction of the full load flow"
                    },
                    "speed_3_part_load_fraction_correlation_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "quadratic curve = a + b*PLR + c*PLR**2 cubic curve = a + b*PLR + c*PLR**2 + d*PLR**3 PLR = part load ratio (Cooling load/steady state capacity)"
                    },
                    "speed_3_nominal_time_for_condensate_removal_to_begin": {
                        "type": "number",
                        "units": "s",
                        "minimum": 0.0,
                        "maximum": 3000.0,
                        "default": 0.0,
                        "note": "The nominal time for condensate to begin leaving the coil's condensate drain line at the coil's rated air flow rate and temperature conditions. Nominal time is equal to the ratio of the energy of the coil's maximum condensate holding capacity (J) to the coil's steady state latent capacity (W). Suggested value is 1000; zero value means latent degradation model is disabled."
                    },
                    "speed_3_ratio_of_initial_moisture_evaporation_rate_and_steady_state_latent_capacity": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 5.0,
                        "default": 0.0,
                        "note": "Ratio of the initial moisture evaporation rate from the cooling coil (when the compressor first turns off) and the coil's steady state latent capacity at rated air flow and temperature conditions. Suggested value is 1.5; zero value means latent degradation model is disabled."
                    },
                    "speed_3_maximum_cycling_rate": {
                        "type": "number",
                        "units": "cycles/hr",
                        "minimum": 0.0,
                        "maximum": 5.0,
                        "default": 0.0,
                        "note": "The maximum on-off cycling rate for the compressor, which occurs at 50% run time fraction. Suggested value is 3; zero value means latent degradation model is disabled."
                    },
                    "speed_3_latent_capacity_time_constant": {
                        "type": "number",
                        "units": "s",
                        "minimum": 0.0,
                        "maximum": 500.0,
                        "default": 0.0,
                        "note": "Time constant for the cooling coil's latent capacity to reach steady state after startup. Suggested value is 45; zero value means latent degradation model is disabled."
                    },
                    "speed_3_rated_waste_heat_fraction_of_power_input": {
                        "type": "number",
                        "units": "dimensionless",
                        "exclusiveMinimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.2,
                        "note": "Recoverable waste heat at full load and rated conditions"
                    },
                    "speed_3_waste_heat_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "curve = a + b*odb + c*odb**2 + d*db + e*db**2 + f*odb*db odb = Outdoor air dry-bulb temperature (C) db = entering coil dry-bulb temperature (C)"
                    },
                    "speed_3_evaporative_condenser_effectiveness": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.9
                    },
                    "speed_3_evaporative_condenser_air_flow_rate": {
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
                    "speed_3_rated_evaporative_condenser_pump_power_consumption": {
                        "units": "W",
                        "note": "Rated power consumed by the evaporative condenser's water pump at Low speed",
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
                    "speed_4_gross_rated_total_cooling_capacity": {
                        "note": "Total cooling capacity not accounting for the effect of supply air fan heat Gross capacity excluding supply air fan heat Rating point: air entering the cooling coil at 26.7 C dry-bulb/19.4 C wet-bulb, and air entering the outdoor condenser coil at 35 C dry-bulb/23.9 C wet-bulb",
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
                    "speed_4_gross_rated_sensible_heat_ratio": {
                        "note": "Gross Rated Sensible Heat Ratio (gross sensible capacity/gross total capacity) Sensible and total capacities do not include supply fan heat",
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
                    "speed_4_gross_rated_cooling_cop": {
                        "type": "number",
                        "note": "Gross cooling capacity divided by power input to the compressor and outdoor fan, does not include supply fan heat or supply fan electrical energy input",
                        "units": "W/W",
                        "exclusiveMinimum": 0.0,
                        "default": 3.0
                    },
                    "speed_4_rated_air_flow_rate": {
                        "units": "m3/s",
                        "note": "Flow rate corresponding to rated total cooling capacity, rated SHR and rated COP should be between 0.00004027 m3/s and .00006041 m3/s per watt of rated total cooling capacity for Speed 4",
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
                    "speed_4_rated_evaporator_fan_power_per_volume_flow_rate": {
                        "type": "number",
                        "note": "Enter the evaporator fan power per air volume flow rate at the rated test conditions. The test conditions vary external static pressure based on total cooling capacity. This value is only used to calculate Seasonal Energy Efficiency Ratio (SEER), and the Standard Rating (Net) Cooling Capacity which will be outputs in the EnergyPlus eio file. This value is not used for modeling the evaporator fan during simulations.",
                        "units": "W/(m3/s)",
                        "minimum": 0.0,
                        "maximum": 1250.0,
                        "default": 773.3
                    },
                    "speed_4_total_cooling_capacity_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "curve = a + b*wb + c*wb**2 + d*edb + e*edb**2 + f*wb*edb wb = entering wet-bulb temperature (C) edb = dry-bulb temperature seen by the condenser (C)"
                    },
                    "speed_4_total_cooling_capacity_function_of_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "quadratic curve = a + b*ff + c*ff**2 cubic curve = a + b*ff + c*ff**2 + d*ff**3 ff = fraction of the full load flow"
                    },
                    "speed_4_energy_input_ratio_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "curve = a + b*wb + c*wb**2 + d*edb + e*edb**2 + f*wb*edb wb = entering wet-bulb temperature (C) edb = dry-bulb temperature seen by the condenser (C)"
                    },
                    "speed_4_energy_input_ratio_function_of_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "quadratic curve = a + b*ff + c*ff**2 cubic curve = a + b*ff + c*ff**2 + d*ff**3 ff = fraction of the full load flow"
                    },
                    "speed_4_part_load_fraction_correlation_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "quadratic curve = a + b*PLR + c*PLR**2 cubic curve = a + b*PLR + c*PLR**2 + d*PLR**3 PLR = part load ratio (cooling load/steady state capacity)"
                    },
                    "speed_4_nominal_time_for_condensate_removal_to_begin": {
                        "type": "number",
                        "units": "s",
                        "minimum": 0.0,
                        "maximum": 3000.0,
                        "default": 0.0,
                        "note": "The nominal time for condensate to begin leaving the coil's condensate drain line at the coil's rated air flow rate and temperature conditions. Nominal time is equal to the ratio of the energy of the coil's maximum condensate holding capacity (J) to the coil's steady state latent capacity (W). Suggested value is 1000; zero value means latent degradation model is disabled."
                    },
                    "speed_4_ratio_of_initial_moisture_evaporation_rate_and_steady_state_latent_capacity": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 5.0,
                        "default": 0.0,
                        "note": "Ratio of the initial moisture evaporation rate from the cooling coil (when the compressor first turns off) and the coil's steady state latent capacity at rated air flow rate and temperature conditions. Suggested value is 1.5; zero value means latent degradation model is disabled."
                    },
                    "speed_4_maximum_cycling_rate": {
                        "type": "number",
                        "units": "cycles/hr",
                        "minimum": 0.0,
                        "maximum": 5.0,
                        "default": 0.0,
                        "note": "The maximum on-off cycling rate for the compressor, which occurs at 50% run time fraction. Suggested value is 3; zero value means latent degradation model is disabled."
                    },
                    "speed_4_latent_capacity_time_constant": {
                        "type": "number",
                        "units": "s",
                        "minimum": 0.0,
                        "maximum": 500.0,
                        "default": 0.0,
                        "note": "Time constant for the cooling coil's latent capacity to reach steady state after startup. Suggested value is 45; zero value means latent degradation model is disabled."
                    },
                    "speed_4_rated_waste_heat_fraction_of_power_input": {
                        "type": "number",
                        "units": "dimensionless",
                        "exclusiveMinimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.2,
                        "note": "Recoverable waste heat at full load and rated conditions"
                    },
                    "speed_4_waste_heat_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "curve = a + b*odb + c*odb**2 + d*db + e*db**2 + f*odb*db odb = Outdoor air dry-bulb temperature (C) db = entering coil dry-bulb temperature (C)"
                    },
                    "speed_4_evaporative_condenser_effectiveness": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.9
                    },
                    "speed_4_evaporative_condenser_air_flow_rate": {
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
                    "speed_4_rated_evaporative_condenser_pump_power_consumption": {
                        "units": "W",
                        "note": "Rated power consumed by the evaporative condenser's water pump at Speed 4",
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
                    "zone_name_for_condenser_placement": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ],
                        "note": "This input field is name of a conditioned or unconditioned zone where the secondary coil (condenser) of DX system or a heat pump is to be placed. This is an optional input field specified only when user desires to reject the condenser heat into a zone. The heat rejected is modelled as internal sensible heat gain of the zone."
                    }
                },
                "required": [
                    "air_inlet_node_name",
                    "air_outlet_node_name",
                    "fuel_type",
                    "number_of_speeds",
                    "speed_1_gross_rated_total_cooling_capacity",
                    "speed_1_gross_rated_sensible_heat_ratio",
                    "speed_1_rated_air_flow_rate",
                    "speed_1_total_cooling_capacity_function_of_temperature_curve_name",
                    "speed_1_total_cooling_capacity_function_of_flow_fraction_curve_name",
                    "speed_1_energy_input_ratio_function_of_temperature_curve_name",
                    "speed_1_energy_input_ratio_function_of_flow_fraction_curve_name",
                    "speed_1_part_load_fraction_correlation_curve_name",
                    "speed_2_gross_rated_total_cooling_capacity",
                    "speed_2_gross_rated_sensible_heat_ratio",
                    "speed_2_rated_air_flow_rate",
                    "speed_2_total_cooling_capacity_function_of_temperature_curve_name",
                    "speed_2_total_cooling_capacity_function_of_flow_fraction_curve_name",
                    "speed_2_energy_input_ratio_function_of_temperature_curve_name",
                    "speed_2_energy_input_ratio_function_of_flow_fraction_curve_name",
                    "speed_2_part_load_fraction_correlation_curve_name"
                ]
            }
        },
        "group": "Coils",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "AFNCoilNames",
                "CoolingCoilsDXMultiSpeed",
                "DesuperHeatingWaterOnlySources"
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
                "air_inlet_node_name": {
                    "field_name": "Air Inlet Node Name",
                    "field_type": "a"
                },
                "air_outlet_node_name": {
                    "field_name": "Air Outlet Node Name",
                    "field_type": "a"
                },
                "condenser_air_inlet_node_name": {
                    "field_name": "Condenser Air Inlet Node Name",
                    "field_type": "a"
                },
                "condenser_type": {
                    "field_name": "Condenser Type",
                    "field_type": "a"
                },
                "minimum_outdoor_dry_bulb_temperature_for_compressor_operation": {
                    "field_name": "Minimum Outdoor Dry-Bulb Temperature for Compressor Operation",
                    "field_type": "n"
                },
                "supply_water_storage_tank_name": {
                    "field_name": "Supply Water Storage Tank Name",
                    "field_type": "a"
                },
                "condensate_collection_water_storage_tank_name": {
                    "field_name": "Condensate Collection Water Storage Tank Name",
                    "field_type": "a"
                },
                "apply_part_load_fraction_to_speeds_greater_than_1": {
                    "field_name": "Apply Part Load Fraction to Speeds Greater than 1",
                    "field_type": "a"
                },
                "apply_latent_degradation_to_speeds_greater_than_1": {
                    "field_name": "Apply Latent Degradation to Speeds Greater than 1",
                    "field_type": "a"
                },
                "crankcase_heater_capacity": {
                    "field_name": "Crankcase Heater Capacity",
                    "field_type": "n"
                },
                "maximum_outdoor_dry_bulb_temperature_for_crankcase_heater_operation": {
                    "field_name": "Maximum Outdoor Dry-Bulb Temperature for Crankcase Heater Operation",
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
                "fuel_type": {
                    "field_name": "Fuel Type",
                    "field_type": "a"
                },
                "number_of_speeds": {
                    "field_name": "Number of Speeds",
                    "field_type": "n"
                },
                "speed_1_gross_rated_total_cooling_capacity": {
                    "field_name": "Speed 1 Gross Rated Total Cooling Capacity",
                    "field_type": "n"
                },
                "speed_1_gross_rated_sensible_heat_ratio": {
                    "field_name": "Speed 1 Gross Rated Sensible Heat Ratio",
                    "field_type": "n"
                },
                "speed_1_gross_rated_cooling_cop": {
                    "field_name": "Speed 1 Gross Rated Cooling COP",
                    "field_type": "n"
                },
                "speed_1_rated_air_flow_rate": {
                    "field_name": "Speed 1 Rated Air Flow Rate",
                    "field_type": "n"
                },
                "speed_1_rated_evaporator_fan_power_per_volume_flow_rate": {
                    "field_name": "Speed 1 Rated Evaporator Fan Power Per Volume Flow Rate",
                    "field_type": "n"
                },
                "speed_1_total_cooling_capacity_function_of_temperature_curve_name": {
                    "field_name": "Speed 1 Total Cooling Capacity Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_1_total_cooling_capacity_function_of_flow_fraction_curve_name": {
                    "field_name": "Speed 1 Total Cooling Capacity Function of Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "speed_1_energy_input_ratio_function_of_temperature_curve_name": {
                    "field_name": "Speed 1 Energy Input Ratio Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_1_energy_input_ratio_function_of_flow_fraction_curve_name": {
                    "field_name": "Speed 1 Energy Input Ratio Function of Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "speed_1_part_load_fraction_correlation_curve_name": {
                    "field_name": "Speed 1 Part Load Fraction Correlation Curve Name",
                    "field_type": "a"
                },
                "speed_1_nominal_time_for_condensate_removal_to_begin": {
                    "field_name": "Speed 1 Nominal Time for Condensate Removal to Begin",
                    "field_type": "n"
                },
                "speed_1_ratio_of_initial_moisture_evaporation_rate_and_steady_state_latent_capacity": {
                    "field_name": "Speed 1 Ratio of Initial Moisture Evaporation Rate and Steady State Latent Capacity",
                    "field_type": "n"
                },
                "speed_1_maximum_cycling_rate": {
                    "field_name": "Speed 1 Maximum Cycling Rate",
                    "field_type": "n"
                },
                "speed_1_latent_capacity_time_constant": {
                    "field_name": "Speed 1 Latent Capacity Time Constant",
                    "field_type": "n"
                },
                "speed_1_rated_waste_heat_fraction_of_power_input": {
                    "field_name": "Speed 1 Rated Waste Heat Fraction of Power Input",
                    "field_type": "n"
                },
                "speed_1_waste_heat_function_of_temperature_curve_name": {
                    "field_name": "Speed 1 Waste Heat Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_1_evaporative_condenser_effectiveness": {
                    "field_name": "Speed 1 Evaporative Condenser Effectiveness",
                    "field_type": "n"
                },
                "speed_1_evaporative_condenser_air_flow_rate": {
                    "field_name": "Speed 1 Evaporative Condenser Air Flow Rate",
                    "field_type": "n"
                },
                "speed_1_rated_evaporative_condenser_pump_power_consumption": {
                    "field_name": "Speed 1 Rated Evaporative Condenser Pump Power Consumption",
                    "field_type": "n"
                },
                "speed_2_gross_rated_total_cooling_capacity": {
                    "field_name": "Speed 2 Gross Rated Total Cooling Capacity",
                    "field_type": "n"
                },
                "speed_2_gross_rated_sensible_heat_ratio": {
                    "field_name": "Speed 2 Gross Rated Sensible Heat Ratio",
                    "field_type": "n"
                },
                "speed_2_gross_rated_cooling_cop": {
                    "field_name": "Speed 2 Gross Rated Cooling COP",
                    "field_type": "n"
                },
                "speed_2_rated_air_flow_rate": {
                    "field_name": "Speed 2 Rated Air Flow Rate",
                    "field_type": "n"
                },
                "speed_2_rated_evaporator_fan_power_per_volume_flow_rate": {
                    "field_name": "Speed 2 Rated Evaporator Fan Power Per Volume Flow Rate",
                    "field_type": "n"
                },
                "speed_2_total_cooling_capacity_function_of_temperature_curve_name": {
                    "field_name": "Speed 2 Total Cooling Capacity Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_2_total_cooling_capacity_function_of_flow_fraction_curve_name": {
                    "field_name": "Speed 2 Total Cooling Capacity Function of Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "speed_2_energy_input_ratio_function_of_temperature_curve_name": {
                    "field_name": "Speed 2 Energy Input Ratio Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_2_energy_input_ratio_function_of_flow_fraction_curve_name": {
                    "field_name": "Speed 2 Energy Input Ratio Function of Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "speed_2_part_load_fraction_correlation_curve_name": {
                    "field_name": "Speed 2 Part Load Fraction Correlation Curve Name",
                    "field_type": "a"
                },
                "speed_2_nominal_time_for_condensate_removal_to_begin": {
                    "field_name": "Speed 2 Nominal Time for Condensate Removal to Begin",
                    "field_type": "n"
                },
                "speed_2_ratio_of_initial_moisture_evaporation_rate_and_steady_state_latent_capacity": {
                    "field_name": "Speed 2 Ratio of Initial Moisture Evaporation Rate and steady state Latent Capacity",
                    "field_type": "n"
                },
                "speed_2_maximum_cycling_rate": {
                    "field_name": "Speed 2 Maximum Cycling Rate",
                    "field_type": "n"
                },
                "speed_2_latent_capacity_time_constant": {
                    "field_name": "Speed 2 Latent Capacity Time Constant",
                    "field_type": "n"
                },
                "speed_2_rated_waste_heat_fraction_of_power_input": {
                    "field_name": "Speed 2 Rated Waste Heat Fraction of Power Input",
                    "field_type": "n"
                },
                "speed_2_waste_heat_function_of_temperature_curve_name": {
                    "field_name": "Speed 2 Waste Heat Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_2_evaporative_condenser_effectiveness": {
                    "field_name": "Speed 2 Evaporative Condenser Effectiveness",
                    "field_type": "n"
                },
                "speed_2_evaporative_condenser_air_flow_rate": {
                    "field_name": "Speed 2 Evaporative Condenser Air Flow Rate",
                    "field_type": "n"
                },
                "speed_2_rated_evaporative_condenser_pump_power_consumption": {
                    "field_name": "Speed 2 Rated Evaporative Condenser Pump Power Consumption",
                    "field_type": "n"
                },
                "speed_3_gross_rated_total_cooling_capacity": {
                    "field_name": "Speed 3 Gross Rated Total Cooling Capacity",
                    "field_type": "n"
                },
                "speed_3_gross_rated_sensible_heat_ratio": {
                    "field_name": "Speed 3 Gross Rated Sensible Heat Ratio",
                    "field_type": "n"
                },
                "speed_3_gross_rated_cooling_cop": {
                    "field_name": "Speed 3 Gross Rated Cooling COP",
                    "field_type": "n"
                },
                "speed_3_rated_air_flow_rate": {
                    "field_name": "Speed 3 Rated Air Flow Rate",
                    "field_type": "n"
                },
                "speed_3_rated_evaporator_fan_power_per_volume_flow_rate": {
                    "field_name": "Speed 3 Rated Evaporator Fan Power Per Volume Flow Rate",
                    "field_type": "n"
                },
                "speed_3_total_cooling_capacity_function_of_temperature_curve_name": {
                    "field_name": "Speed 3 Total Cooling Capacity Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_3_total_cooling_capacity_function_of_flow_fraction_curve_name": {
                    "field_name": "Speed 3 Total Cooling Capacity Function of Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "speed_3_energy_input_ratio_function_of_temperature_curve_name": {
                    "field_name": "Speed 3 Energy Input Ratio Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_3_energy_input_ratio_function_of_flow_fraction_curve_name": {
                    "field_name": "Speed 3 Energy Input Ratio Function of Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "speed_3_part_load_fraction_correlation_curve_name": {
                    "field_name": "Speed 3 Part Load Fraction Correlation Curve Name",
                    "field_type": "a"
                },
                "speed_3_nominal_time_for_condensate_removal_to_begin": {
                    "field_name": "Speed 3 Nominal Time for Condensate Removal to Begin",
                    "field_type": "n"
                },
                "speed_3_ratio_of_initial_moisture_evaporation_rate_and_steady_state_latent_capacity": {
                    "field_name": "Speed 3 Ratio of Initial Moisture Evaporation Rate and steady state Latent Capacity",
                    "field_type": "n"
                },
                "speed_3_maximum_cycling_rate": {
                    "field_name": "Speed 3 Maximum Cycling Rate",
                    "field_type": "n"
                },
                "speed_3_latent_capacity_time_constant": {
                    "field_name": "Speed 3 Latent Capacity Time Constant",
                    "field_type": "n"
                },
                "speed_3_rated_waste_heat_fraction_of_power_input": {
                    "field_name": "Speed 3 Rated Waste Heat Fraction of Power Input",
                    "field_type": "n"
                },
                "speed_3_waste_heat_function_of_temperature_curve_name": {
                    "field_name": "Speed 3 Waste Heat Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_3_evaporative_condenser_effectiveness": {
                    "field_name": "Speed 3 Evaporative Condenser Effectiveness",
                    "field_type": "n"
                },
                "speed_3_evaporative_condenser_air_flow_rate": {
                    "field_name": "Speed 3 Evaporative Condenser Air Flow Rate",
                    "field_type": "n"
                },
                "speed_3_rated_evaporative_condenser_pump_power_consumption": {
                    "field_name": "Speed 3 Rated Evaporative Condenser Pump Power Consumption",
                    "field_type": "n"
                },
                "speed_4_gross_rated_total_cooling_capacity": {
                    "field_name": "Speed 4 Gross Rated Total Cooling Capacity",
                    "field_type": "n"
                },
                "speed_4_gross_rated_sensible_heat_ratio": {
                    "field_name": "Speed 4 Gross Rated Sensible Heat Ratio",
                    "field_type": "n"
                },
                "speed_4_gross_rated_cooling_cop": {
                    "field_name": "Speed 4 Gross Rated Cooling COP",
                    "field_type": "n"
                },
                "speed_4_rated_air_flow_rate": {
                    "field_name": "Speed 4 Rated Air Flow Rate",
                    "field_type": "n"
                },
                "speed_4_rated_evaporator_fan_power_per_volume_flow_rate": {
                    "field_name": "Speed 4 Rated Evaporator Fan Power Per Volume Flow Rate",
                    "field_type": "n"
                },
                "speed_4_total_cooling_capacity_function_of_temperature_curve_name": {
                    "field_name": "Speed 4 Total Cooling Capacity Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_4_total_cooling_capacity_function_of_flow_fraction_curve_name": {
                    "field_name": "Speed 4 Total Cooling Capacity Function of Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "speed_4_energy_input_ratio_function_of_temperature_curve_name": {
                    "field_name": "Speed 4 Energy Input Ratio Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_4_energy_input_ratio_function_of_flow_fraction_curve_name": {
                    "field_name": "Speed 4 Energy Input Ratio Function of Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "speed_4_part_load_fraction_correlation_curve_name": {
                    "field_name": "Speed 4 Part Load Fraction Correlation Curve Name",
                    "field_type": "a"
                },
                "speed_4_nominal_time_for_condensate_removal_to_begin": {
                    "field_name": "Speed 4 Nominal Time for Condensate Removal to Begin",
                    "field_type": "n"
                },
                "speed_4_ratio_of_initial_moisture_evaporation_rate_and_steady_state_latent_capacity": {
                    "field_name": "Speed 4 Ratio of Initial Moisture Evaporation Rate and steady state Latent Capacity",
                    "field_type": "n"
                },
                "speed_4_maximum_cycling_rate": {
                    "field_name": "Speed 4 Maximum Cycling Rate",
                    "field_type": "n"
                },
                "speed_4_latent_capacity_time_constant": {
                    "field_name": "Speed 4 Latent Capacity Time Constant",
                    "field_type": "n"
                },
                "speed_4_rated_waste_heat_fraction_of_power_input": {
                    "field_name": "Speed 4 Rated Waste Heat Fraction of Power Input",
                    "field_type": "n"
                },
                "speed_4_waste_heat_function_of_temperature_curve_name": {
                    "field_name": "Speed 4 Waste Heat Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_4_evaporative_condenser_effectiveness": {
                    "field_name": "Speed 4 Evaporative Condenser Effectiveness",
                    "field_type": "n"
                },
                "speed_4_evaporative_condenser_air_flow_rate": {
                    "field_name": "Speed 4 Evaporative Condenser Air Flow Rate",
                    "field_type": "n"
                },
                "speed_4_rated_evaporative_condenser_pump_power_consumption": {
                    "field_name": "Speed 4 Rated Evaporative Condenser Pump Power Consumption",
                    "field_type": "n"
                },
                "zone_name_for_condenser_placement": {
                    "field_name": "Zone Name for Condenser Placement",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "availability_schedule_name",
                "air_inlet_node_name",
                "air_outlet_node_name",
                "condenser_air_inlet_node_name",
                "condenser_type",
                "minimum_outdoor_dry_bulb_temperature_for_compressor_operation",
                "supply_water_storage_tank_name",
                "condensate_collection_water_storage_tank_name",
                "apply_part_load_fraction_to_speeds_greater_than_1",
                "apply_latent_degradation_to_speeds_greater_than_1",
                "crankcase_heater_capacity",
                "maximum_outdoor_dry_bulb_temperature_for_crankcase_heater_operation",
                "basin_heater_capacity",
                "basin_heater_setpoint_temperature",
                "basin_heater_operating_schedule_name",
                "fuel_type",
                "number_of_speeds",
                "speed_1_gross_rated_total_cooling_capacity",
                "speed_1_gross_rated_sensible_heat_ratio",
                "speed_1_gross_rated_cooling_cop",
                "speed_1_rated_air_flow_rate",
                "speed_1_rated_evaporator_fan_power_per_volume_flow_rate",
                "speed_1_total_cooling_capacity_function_of_temperature_curve_name",
                "speed_1_total_cooling_capacity_function_of_flow_fraction_curve_name",
                "speed_1_energy_input_ratio_function_of_temperature_curve_name",
                "speed_1_energy_input_ratio_function_of_flow_fraction_curve_name",
                "speed_1_part_load_fraction_correlation_curve_name",
                "speed_1_nominal_time_for_condensate_removal_to_begin",
                "speed_1_ratio_of_initial_moisture_evaporation_rate_and_steady_state_latent_capacity",
                "speed_1_maximum_cycling_rate",
                "speed_1_latent_capacity_time_constant",
                "speed_1_rated_waste_heat_fraction_of_power_input",
                "speed_1_waste_heat_function_of_temperature_curve_name",
                "speed_1_evaporative_condenser_effectiveness",
                "speed_1_evaporative_condenser_air_flow_rate",
                "speed_1_rated_evaporative_condenser_pump_power_consumption",
                "speed_2_gross_rated_total_cooling_capacity",
                "speed_2_gross_rated_sensible_heat_ratio",
                "speed_2_gross_rated_cooling_cop",
                "speed_2_rated_air_flow_rate",
                "speed_2_rated_evaporator_fan_power_per_volume_flow_rate",
                "speed_2_total_cooling_capacity_function_of_temperature_curve_name",
                "speed_2_total_cooling_capacity_function_of_flow_fraction_curve_name",
                "speed_2_energy_input_ratio_function_of_temperature_curve_name",
                "speed_2_energy_input_ratio_function_of_flow_fraction_curve_name",
                "speed_2_part_load_fraction_correlation_curve_name",
                "speed_2_nominal_time_for_condensate_removal_to_begin",
                "speed_2_ratio_of_initial_moisture_evaporation_rate_and_steady_state_latent_capacity",
                "speed_2_maximum_cycling_rate",
                "speed_2_latent_capacity_time_constant",
                "speed_2_rated_waste_heat_fraction_of_power_input",
                "speed_2_waste_heat_function_of_temperature_curve_name",
                "speed_2_evaporative_condenser_effectiveness",
                "speed_2_evaporative_condenser_air_flow_rate",
                "speed_2_rated_evaporative_condenser_pump_power_consumption",
                "speed_3_gross_rated_total_cooling_capacity",
                "speed_3_gross_rated_sensible_heat_ratio",
                "speed_3_gross_rated_cooling_cop",
                "speed_3_rated_air_flow_rate",
                "speed_3_rated_evaporator_fan_power_per_volume_flow_rate",
                "speed_3_total_cooling_capacity_function_of_temperature_curve_name",
                "speed_3_total_cooling_capacity_function_of_flow_fraction_curve_name",
                "speed_3_energy_input_ratio_function_of_temperature_curve_name",
                "speed_3_energy_input_ratio_function_of_flow_fraction_curve_name",
                "speed_3_part_load_fraction_correlation_curve_name",
                "speed_3_nominal_time_for_condensate_removal_to_begin",
                "speed_3_ratio_of_initial_moisture_evaporation_rate_and_steady_state_latent_capacity",
                "speed_3_maximum_cycling_rate",
                "speed_3_latent_capacity_time_constant",
                "speed_3_rated_waste_heat_fraction_of_power_input",
                "speed_3_waste_heat_function_of_temperature_curve_name",
                "speed_3_evaporative_condenser_effectiveness",
                "speed_3_evaporative_condenser_air_flow_rate",
                "speed_3_rated_evaporative_condenser_pump_power_consumption",
                "speed_4_gross_rated_total_cooling_capacity",
                "speed_4_gross_rated_sensible_heat_ratio",
                "speed_4_gross_rated_cooling_cop",
                "speed_4_rated_air_flow_rate",
                "speed_4_rated_evaporator_fan_power_per_volume_flow_rate",
                "speed_4_total_cooling_capacity_function_of_temperature_curve_name",
                "speed_4_total_cooling_capacity_function_of_flow_fraction_curve_name",
                "speed_4_energy_input_ratio_function_of_temperature_curve_name",
                "speed_4_energy_input_ratio_function_of_flow_fraction_curve_name",
                "speed_4_part_load_fraction_correlation_curve_name",
                "speed_4_nominal_time_for_condensate_removal_to_begin",
                "speed_4_ratio_of_initial_moisture_evaporation_rate_and_steady_state_latent_capacity",
                "speed_4_maximum_cycling_rate",
                "speed_4_latent_capacity_time_constant",
                "speed_4_rated_waste_heat_fraction_of_power_input",
                "speed_4_waste_heat_function_of_temperature_curve_name",
                "speed_4_evaporative_condenser_effectiveness",
                "speed_4_evaporative_condenser_air_flow_rate",
                "speed_4_rated_evaporative_condenser_pump_power_consumption",
                "zone_name_for_condenser_placement"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "air_inlet_node_name",
                    "air_outlet_node_name",
                    "condenser_air_inlet_node_name",
                    "condenser_type",
                    "supply_water_storage_tank_name",
                    "condensate_collection_water_storage_tank_name",
                    "apply_part_load_fraction_to_speeds_greater_than_1",
                    "apply_latent_degradation_to_speeds_greater_than_1",
                    "basin_heater_operating_schedule_name",
                    "fuel_type",
                    "speed_1_total_cooling_capacity_function_of_temperature_curve_name",
                    "speed_1_total_cooling_capacity_function_of_flow_fraction_curve_name",
                    "speed_1_energy_input_ratio_function_of_temperature_curve_name",
                    "speed_1_energy_input_ratio_function_of_flow_fraction_curve_name",
                    "speed_1_part_load_fraction_correlation_curve_name",
                    "speed_1_waste_heat_function_of_temperature_curve_name",
                    "speed_2_total_cooling_capacity_function_of_temperature_curve_name",
                    "speed_2_total_cooling_capacity_function_of_flow_fraction_curve_name",
                    "speed_2_energy_input_ratio_function_of_temperature_curve_name",
                    "speed_2_energy_input_ratio_function_of_flow_fraction_curve_name",
                    "speed_2_part_load_fraction_correlation_curve_name",
                    "speed_2_waste_heat_function_of_temperature_curve_name",
                    "speed_3_total_cooling_capacity_function_of_temperature_curve_name",
                    "speed_3_total_cooling_capacity_function_of_flow_fraction_curve_name",
                    "speed_3_energy_input_ratio_function_of_temperature_curve_name",
                    "speed_3_energy_input_ratio_function_of_flow_fraction_curve_name",
                    "speed_3_part_load_fraction_correlation_curve_name",
                    "speed_3_waste_heat_function_of_temperature_curve_name",
                    "speed_4_total_cooling_capacity_function_of_temperature_curve_name",
                    "speed_4_total_cooling_capacity_function_of_flow_fraction_curve_name",
                    "speed_4_energy_input_ratio_function_of_temperature_curve_name",
                    "speed_4_energy_input_ratio_function_of_flow_fraction_curve_name",
                    "speed_4_part_load_fraction_correlation_curve_name",
                    "speed_4_waste_heat_function_of_temperature_curve_name",
                    "zone_name_for_condenser_placement"
                ]
            },
            "numerics": {
                "fields": [
                    "minimum_outdoor_dry_bulb_temperature_for_compressor_operation",
                    "crankcase_heater_capacity",
                    "maximum_outdoor_dry_bulb_temperature_for_crankcase_heater_operation",
                    "basin_heater_capacity",
                    "basin_heater_setpoint_temperature",
                    "number_of_speeds",
                    "speed_1_gross_rated_total_cooling_capacity",
                    "speed_1_gross_rated_sensible_heat_ratio",
                    "speed_1_gross_rated_cooling_cop",
                    "speed_1_rated_air_flow_rate",
                    "speed_1_rated_evaporator_fan_power_per_volume_flow_rate",
                    "speed_1_nominal_time_for_condensate_removal_to_begin",
                    "speed_1_ratio_of_initial_moisture_evaporation_rate_and_steady_state_latent_capacity",
                    "speed_1_maximum_cycling_rate",
                    "speed_1_latent_capacity_time_constant",
                    "speed_1_rated_waste_heat_fraction_of_power_input",
                    "speed_1_evaporative_condenser_effectiveness",
                    "speed_1_evaporative_condenser_air_flow_rate",
                    "speed_1_rated_evaporative_condenser_pump_power_consumption",
                    "speed_2_gross_rated_total_cooling_capacity",
                    "speed_2_gross_rated_sensible_heat_ratio",
                    "speed_2_gross_rated_cooling_cop",
                    "speed_2_rated_air_flow_rate",
                    "speed_2_rated_evaporator_fan_power_per_volume_flow_rate",
                    "speed_2_nominal_time_for_condensate_removal_to_begin",
                    "speed_2_ratio_of_initial_moisture_evaporation_rate_and_steady_state_latent_capacity",
                    "speed_2_maximum_cycling_rate",
                    "speed_2_latent_capacity_time_constant",
                    "speed_2_rated_waste_heat_fraction_of_power_input",
                    "speed_2_evaporative_condenser_effectiveness",
                    "speed_2_evaporative_condenser_air_flow_rate",
                    "speed_2_rated_evaporative_condenser_pump_power_consumption",
                    "speed_3_gross_rated_total_cooling_capacity",
                    "speed_3_gross_rated_sensible_heat_ratio",
                    "speed_3_gross_rated_cooling_cop",
                    "speed_3_rated_air_flow_rate",
                    "speed_3_rated_evaporator_fan_power_per_volume_flow_rate",
                    "speed_3_nominal_time_for_condensate_removal_to_begin",
                    "speed_3_ratio_of_initial_moisture_evaporation_rate_and_steady_state_latent_capacity",
                    "speed_3_maximum_cycling_rate",
                    "speed_3_latent_capacity_time_constant",
                    "speed_3_rated_waste_heat_fraction_of_power_input",
                    "speed_3_evaporative_condenser_effectiveness",
                    "speed_3_evaporative_condenser_air_flow_rate",
                    "speed_3_rated_evaporative_condenser_pump_power_consumption",
                    "speed_4_gross_rated_total_cooling_capacity",
                    "speed_4_gross_rated_sensible_heat_ratio",
                    "speed_4_gross_rated_cooling_cop",
                    "speed_4_rated_air_flow_rate",
                    "speed_4_rated_evaporator_fan_power_per_volume_flow_rate",
                    "speed_4_nominal_time_for_condensate_removal_to_begin",
                    "speed_4_ratio_of_initial_moisture_evaporation_rate_and_steady_state_latent_capacity",
                    "speed_4_maximum_cycling_rate",
                    "speed_4_latent_capacity_time_constant",
                    "speed_4_rated_waste_heat_fraction_of_power_input",
                    "speed_4_evaporative_condenser_effectiveness",
                    "speed_4_evaporative_condenser_air_flow_rate",
                    "speed_4_rated_evaporative_condenser_pump_power_consumption"
                ]
            }
        },
        "type": "object",
        "memo": "Direct expansion (DX) cooling coil and condensing unit (includes electric or engine-driven compressor and condenser fan), multi-speed (or variable-speed). Optional moisture evaporation from wet coil when compressor cycles off with continuous fan operation. Requires two to four sets of performance data and will interpolate between speeds. Modeled as a single coil (multi-speed compressor or multiple compressors with row split or intertwined coil).",
        "min_fields": 56.0
    }
}
```
