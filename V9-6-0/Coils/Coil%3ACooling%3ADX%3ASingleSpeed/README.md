```
{
    "Coil:Cooling:DX:SingleSpeed": {
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
                        "note": "Flow rate corresponding to rated total cooling capacity, Rated SHR and Rated COP should be between 0.00004027 m3/s and .00006041 m3/s per watt of rated total cooling capacity",
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
                    "rated_evaporator_fan_power_per_volume_flow_rate": {
                        "type": "number",
                        "note": "Enter the evaporator fan power per air volume flow rate at the rated test conditions. The test conditions vary external static pressure based on total cooling capacity. This value is only used to calculate Seasonal Energy Efficiency Ratio (SEER), Energy Efficiency Ratio (EER), Integrated Energy Efficiency Ratio (IEER), and the Standard Rating (Net) Cooling Capacity which will be outputs in the EnergyPlus eio file. This value is not used for modeling the evaporator fan during simulations.",
                        "units": "W/(m3/s)",
                        "minimum": 0.0,
                        "maximum": 1250.0,
                        "default": 773.3
                    },
                    "air_inlet_node_name": {
                        "type": "string"
                    },
                    "air_outlet_node_name": {
                        "type": "string"
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
                        "note": "quadratic curve = a + b*ff + c*ff**2 cubic curve = a + b*ff + c*ff**2 + d*ff**3 ff = Fraction of the full load flow"
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
                        "note": "quadratic curve = a + b*ff + c*ff**2 cubic curve = a + b*ff + c*ff**2 + d*ff**3 ff = Fraction of the full load flow"
                    },
                    "part_load_fraction_correlation_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "quadratic curve = a + b*PLR + c*PLR**2 cubic curve = a + b*PLR + c*PLR**2 + d*PLR**3 PLR = part load ratio (cooling load/steady state capacity)"
                    },
                    "minimum_outdoor_dry_bulb_temperature_for_compressor_operation": {
                        "type": "number",
                        "default": -25.0,
                        "units": "C"
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
                        "note": "The maximum on-off cycling Rate for the compressor, which occurs at 50% run time fraction. Suggested value is 3; zero value means latent degradation model is disabled."
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
                    },
                    "report_ashrae_standard_127_performance_ratings": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "No",
                        "note": "when this input field is specified as Yes then the program calculates the net cooling capacity and total electric power input of DX cooling coils per ANSI/ASHRAE 127."
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
                    "gross_rated_total_cooling_capacity",
                    "gross_rated_sensible_heat_ratio",
                    "rated_air_flow_rate",
                    "air_inlet_node_name",
                    "air_outlet_node_name",
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
                "AFNCoilNames",
                "CoolingCoilsDX",
                "CoolingCoilsDXMultiModeOrSingleSpeed",
                "CoolingCoilsDXSingleSpeed",
                "DesuperHeatingCoilSources"
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
                "rated_evaporator_fan_power_per_volume_flow_rate": {
                    "field_name": "Rated Evaporator Fan Power Per Volume Flow Rate",
                    "field_type": "n"
                },
                "air_inlet_node_name": {
                    "field_name": "Air Inlet Node Name",
                    "field_type": "a"
                },
                "air_outlet_node_name": {
                    "field_name": "Air Outlet Node Name",
                    "field_type": "a"
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
                "minimum_outdoor_dry_bulb_temperature_for_compressor_operation": {
                    "field_name": "Minimum Outdoor Dry-Bulb Temperature for Compressor Operation",
                    "field_type": "n"
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
                "crankcase_heater_capacity": {
                    "field_name": "Crankcase Heater Capacity",
                    "field_type": "n"
                },
                "maximum_outdoor_dry_bulb_temperature_for_crankcase_heater_operation": {
                    "field_name": "Maximum Outdoor Dry-Bulb Temperature for Crankcase Heater Operation",
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
                "sensible_heat_ratio_function_of_temperature_curve_name": {
                    "field_name": "Sensible Heat Ratio Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "sensible_heat_ratio_function_of_flow_fraction_curve_name": {
                    "field_name": "Sensible Heat Ratio Function of Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "report_ashrae_standard_127_performance_ratings": {
                    "field_name": "Report ASHRAE Standard 127 Performance Ratings",
                    "field_type": "a"
                },
                "zone_name_for_condenser_placement": {
                    "field_name": "Zone Name for Condenser Placement",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "availability_schedule_name",
                "gross_rated_total_cooling_capacity",
                "gross_rated_sensible_heat_ratio",
                "gross_rated_cooling_cop",
                "rated_air_flow_rate",
                "rated_evaporator_fan_power_per_volume_flow_rate",
                "air_inlet_node_name",
                "air_outlet_node_name",
                "total_cooling_capacity_function_of_temperature_curve_name",
                "total_cooling_capacity_function_of_flow_fraction_curve_name",
                "energy_input_ratio_function_of_temperature_curve_name",
                "energy_input_ratio_function_of_flow_fraction_curve_name",
                "part_load_fraction_correlation_curve_name",
                "minimum_outdoor_dry_bulb_temperature_for_compressor_operation",
                "nominal_time_for_condensate_removal_to_begin",
                "ratio_of_initial_moisture_evaporation_rate_and_steady_state_latent_capacity",
                "maximum_cycling_rate",
                "latent_capacity_time_constant",
                "condenser_air_inlet_node_name",
                "condenser_type",
                "evaporative_condenser_effectiveness",
                "evaporative_condenser_air_flow_rate",
                "evaporative_condenser_pump_rated_power_consumption",
                "crankcase_heater_capacity",
                "maximum_outdoor_dry_bulb_temperature_for_crankcase_heater_operation",
                "supply_water_storage_tank_name",
                "condensate_collection_water_storage_tank_name",
                "basin_heater_capacity",
                "basin_heater_setpoint_temperature",
                "basin_heater_operating_schedule_name",
                "sensible_heat_ratio_function_of_temperature_curve_name",
                "sensible_heat_ratio_function_of_flow_fraction_curve_name",
                "report_ashrae_standard_127_performance_ratings",
                "zone_name_for_condenser_placement"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "air_inlet_node_name",
                    "air_outlet_node_name",
                    "total_cooling_capacity_function_of_temperature_curve_name",
                    "total_cooling_capacity_function_of_flow_fraction_curve_name",
                    "energy_input_ratio_function_of_temperature_curve_name",
                    "energy_input_ratio_function_of_flow_fraction_curve_name",
                    "part_load_fraction_correlation_curve_name",
                    "condenser_air_inlet_node_name",
                    "condenser_type",
                    "supply_water_storage_tank_name",
                    "condensate_collection_water_storage_tank_name",
                    "basin_heater_operating_schedule_name",
                    "sensible_heat_ratio_function_of_temperature_curve_name",
                    "sensible_heat_ratio_function_of_flow_fraction_curve_name",
                    "report_ashrae_standard_127_performance_ratings",
                    "zone_name_for_condenser_placement"
                ]
            },
            "numerics": {
                "fields": [
                    "gross_rated_total_cooling_capacity",
                    "gross_rated_sensible_heat_ratio",
                    "gross_rated_cooling_cop",
                    "rated_air_flow_rate",
                    "rated_evaporator_fan_power_per_volume_flow_rate",
                    "minimum_outdoor_dry_bulb_temperature_for_compressor_operation",
                    "nominal_time_for_condensate_removal_to_begin",
                    "ratio_of_initial_moisture_evaporation_rate_and_steady_state_latent_capacity",
                    "maximum_cycling_rate",
                    "latent_capacity_time_constant",
                    "evaporative_condenser_effectiveness",
                    "evaporative_condenser_air_flow_rate",
                    "evaporative_condenser_pump_rated_power_consumption",
                    "crankcase_heater_capacity",
                    "maximum_outdoor_dry_bulb_temperature_for_crankcase_heater_operation",
                    "basin_heater_capacity",
                    "basin_heater_setpoint_temperature"
                ]
            }
        },
        "type": "object",
        "memo": "Direct expansion (DX) cooling coil and condensing unit (includes electric compressor and condenser fan), single-speed. Optional inputs for moisture evaporation from wet coil when compressor cycles off with continuous fan operation.",
        "min_fields": 14.0
    }
}
```
