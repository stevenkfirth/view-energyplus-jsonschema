```
{
    "Coil:Cooling:DX:TwoSpeed": {
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
                    "high_speed_gross_rated_total_cooling_capacity": {
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
                    "high_speed_rated_sensible_heat_ratio": {
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
                    "high_speed_gross_rated_cooling_cop": {
                        "type": "number",
                        "note": "Gross cooling capacity divided by power input to the compressor and outdoor fan, does not include supply fan heat or supply fan electrical energy input",
                        "units": "W/W",
                        "exclusiveMinimum": 0.0,
                        "default": 3.0
                    },
                    "high_speed_rated_air_flow_rate": {
                        "units": "m3/s",
                        "note": "Flow rate corresponding to rated total cooling capacity, Rated SHR and Rated COP. Should be between 0.00004027 m3/s and .00006041 m3/s per watt of rated total cooling capacity.",
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
                    "unit_internal_static_air_pressure": {
                        "type": "number",
                        "note": "Enter pressure drop for the unit containing the coil. This value is only used to calculate Energy Efficiency Ratio (EER), Integrated Energy Efficiency Ratio (IEER), and the Standard Rating (Net) Cooling Capacity. This value is not used for modeling the evaporator fan during simulations.",
                        "units": "Pa",
                        "exclusiveMinimum": 0.0
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
                    "low_speed_gross_rated_total_cooling_capacity": {
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
                    "low_speed_gross_rated_sensible_heat_ratio": {
                        "note": "Gross Rated Sensible Heat Ratio (gross sensible capacity/gross total capacity) sensible and total capacities do not include supply fan heat",
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
                    "low_speed_gross_rated_cooling_cop": {
                        "type": "number",
                        "note": "Gross cooling capacity divided by power input to the compressor and outdoor fan, does not include supply fan heat or supply fan electrical energy input",
                        "units": "W/W",
                        "exclusiveMinimum": 0.0,
                        "default": 3.0
                    },
                    "low_speed_rated_air_flow_rate": {
                        "units": "m3/s",
                        "note": "Flow rate corresponding to rated total cooling capacity, Rated SHR and Rated COP. Should be between 0.00004027 m3/s and .00006041 m3/s per watt of rated total cooling capacity.",
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
                    "low_speed_total_cooling_capacity_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "curve = a + b*wb + c*wb**2 + d*edb + e*edb**2 + f*wb*edb wb = entering wet-bulb temperature (C) edb = dry-bulb temperature seen by the condenser (C)"
                    },
                    "low_speed_energy_input_ratio_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "curve = a + b*wb + c*wb**2 + d*edb + e*edb**2 + f*wb*edb wb = entering wet-bulb temperature (C) edb = dry-bulb temperature seen by the condenser (C)"
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
                    "high_speed_evaporative_condenser_effectiveness": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.9
                    },
                    "high_speed_evaporative_condenser_air_flow_rate": {
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
                    "high_speed_evaporative_condenser_pump_rated_power_consumption": {
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
                    "low_speed_evaporative_condenser_effectiveness": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.9
                    },
                    "low_speed_evaporative_condenser_air_flow_rate": {
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
                    "low_speed_evaporative_condenser_pump_rated_power_consumption": {
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
                    "low_speed_sensible_heat_ratio_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "curve = a + b*wb + c*wb**2 + d*db + e*db**2 + f*wb*db wb = entering wet-bulb temperature seen by the DX cooling coil (C) db = entering dry-bulb temperature seen by the DX cooling coil (C) entering temperature can be outside air or pretreated air."
                    },
                    "low_speed_sensible_heat_ratio_function_of_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "quadratic curve = a + b*ff + c*ff**2 cubic curve = a + b*ff + c*ff**2 + d*ff**3 ff = fraction of the full load flow"
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
                    "high_speed_gross_rated_total_cooling_capacity",
                    "high_speed_rated_sensible_heat_ratio",
                    "high_speed_rated_air_flow_rate",
                    "air_inlet_node_name",
                    "air_outlet_node_name",
                    "total_cooling_capacity_function_of_temperature_curve_name",
                    "total_cooling_capacity_function_of_flow_fraction_curve_name",
                    "energy_input_ratio_function_of_temperature_curve_name",
                    "energy_input_ratio_function_of_flow_fraction_curve_name",
                    "part_load_fraction_correlation_curve_name",
                    "low_speed_gross_rated_total_cooling_capacity",
                    "low_speed_gross_rated_sensible_heat_ratio",
                    "low_speed_rated_air_flow_rate",
                    "low_speed_total_cooling_capacity_function_of_temperature_curve_name",
                    "low_speed_energy_input_ratio_function_of_temperature_curve_name"
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
                "high_speed_gross_rated_total_cooling_capacity": {
                    "field_name": "High Speed Gross Rated Total Cooling Capacity",
                    "field_type": "n"
                },
                "high_speed_rated_sensible_heat_ratio": {
                    "field_name": "High Speed Rated Sensible Heat Ratio",
                    "field_type": "n"
                },
                "high_speed_gross_rated_cooling_cop": {
                    "field_name": "High Speed Gross Rated Cooling COP",
                    "field_type": "n"
                },
                "high_speed_rated_air_flow_rate": {
                    "field_name": "High Speed Rated Air Flow Rate",
                    "field_type": "n"
                },
                "unit_internal_static_air_pressure": {
                    "field_name": "Unit Internal Static Air Pressure",
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
                "low_speed_gross_rated_total_cooling_capacity": {
                    "field_name": "Low Speed Gross Rated Total Cooling Capacity",
                    "field_type": "n"
                },
                "low_speed_gross_rated_sensible_heat_ratio": {
                    "field_name": "Low Speed Gross Rated Sensible Heat Ratio",
                    "field_type": "n"
                },
                "low_speed_gross_rated_cooling_cop": {
                    "field_name": "Low Speed Gross Rated Cooling COP",
                    "field_type": "n"
                },
                "low_speed_rated_air_flow_rate": {
                    "field_name": "Low Speed Rated Air Flow Rate",
                    "field_type": "n"
                },
                "low_speed_total_cooling_capacity_function_of_temperature_curve_name": {
                    "field_name": "Low Speed Total Cooling Capacity Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "low_speed_energy_input_ratio_function_of_temperature_curve_name": {
                    "field_name": "Low Speed Energy Input Ratio Function of Temperature Curve Name",
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
                "high_speed_evaporative_condenser_effectiveness": {
                    "field_name": "High Speed Evaporative Condenser Effectiveness",
                    "field_type": "n"
                },
                "high_speed_evaporative_condenser_air_flow_rate": {
                    "field_name": "High Speed Evaporative Condenser Air Flow Rate",
                    "field_type": "n"
                },
                "high_speed_evaporative_condenser_pump_rated_power_consumption": {
                    "field_name": "High Speed Evaporative Condenser Pump Rated Power Consumption",
                    "field_type": "n"
                },
                "low_speed_evaporative_condenser_effectiveness": {
                    "field_name": "Low Speed Evaporative Condenser Effectiveness",
                    "field_type": "n"
                },
                "low_speed_evaporative_condenser_air_flow_rate": {
                    "field_name": "Low Speed Evaporative Condenser Air Flow Rate",
                    "field_type": "n"
                },
                "low_speed_evaporative_condenser_pump_rated_power_consumption": {
                    "field_name": "Low Speed Evaporative Condenser Pump Rated Power Consumption",
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
                "low_speed_sensible_heat_ratio_function_of_temperature_curve_name": {
                    "field_name": "Low Speed Sensible Heat Ratio Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "low_speed_sensible_heat_ratio_function_of_flow_fraction_curve_name": {
                    "field_name": "Low Speed Sensible Heat Ratio Function of Flow Fraction Curve Name",
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
                "high_speed_gross_rated_total_cooling_capacity",
                "high_speed_rated_sensible_heat_ratio",
                "high_speed_gross_rated_cooling_cop",
                "high_speed_rated_air_flow_rate",
                "unit_internal_static_air_pressure",
                "air_inlet_node_name",
                "air_outlet_node_name",
                "total_cooling_capacity_function_of_temperature_curve_name",
                "total_cooling_capacity_function_of_flow_fraction_curve_name",
                "energy_input_ratio_function_of_temperature_curve_name",
                "energy_input_ratio_function_of_flow_fraction_curve_name",
                "part_load_fraction_correlation_curve_name",
                "low_speed_gross_rated_total_cooling_capacity",
                "low_speed_gross_rated_sensible_heat_ratio",
                "low_speed_gross_rated_cooling_cop",
                "low_speed_rated_air_flow_rate",
                "low_speed_total_cooling_capacity_function_of_temperature_curve_name",
                "low_speed_energy_input_ratio_function_of_temperature_curve_name",
                "condenser_air_inlet_node_name",
                "condenser_type",
                "minimum_outdoor_dry_bulb_temperature_for_compressor_operation",
                "high_speed_evaporative_condenser_effectiveness",
                "high_speed_evaporative_condenser_air_flow_rate",
                "high_speed_evaporative_condenser_pump_rated_power_consumption",
                "low_speed_evaporative_condenser_effectiveness",
                "low_speed_evaporative_condenser_air_flow_rate",
                "low_speed_evaporative_condenser_pump_rated_power_consumption",
                "supply_water_storage_tank_name",
                "condensate_collection_water_storage_tank_name",
                "basin_heater_capacity",
                "basin_heater_setpoint_temperature",
                "basin_heater_operating_schedule_name",
                "sensible_heat_ratio_function_of_temperature_curve_name",
                "sensible_heat_ratio_function_of_flow_fraction_curve_name",
                "low_speed_sensible_heat_ratio_function_of_temperature_curve_name",
                "low_speed_sensible_heat_ratio_function_of_flow_fraction_curve_name",
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
                    "low_speed_total_cooling_capacity_function_of_temperature_curve_name",
                    "low_speed_energy_input_ratio_function_of_temperature_curve_name",
                    "condenser_air_inlet_node_name",
                    "condenser_type",
                    "supply_water_storage_tank_name",
                    "condensate_collection_water_storage_tank_name",
                    "basin_heater_operating_schedule_name",
                    "sensible_heat_ratio_function_of_temperature_curve_name",
                    "sensible_heat_ratio_function_of_flow_fraction_curve_name",
                    "low_speed_sensible_heat_ratio_function_of_temperature_curve_name",
                    "low_speed_sensible_heat_ratio_function_of_flow_fraction_curve_name",
                    "zone_name_for_condenser_placement"
                ]
            },
            "numerics": {
                "fields": [
                    "high_speed_gross_rated_total_cooling_capacity",
                    "high_speed_rated_sensible_heat_ratio",
                    "high_speed_gross_rated_cooling_cop",
                    "high_speed_rated_air_flow_rate",
                    "unit_internal_static_air_pressure",
                    "low_speed_gross_rated_total_cooling_capacity",
                    "low_speed_gross_rated_sensible_heat_ratio",
                    "low_speed_gross_rated_cooling_cop",
                    "low_speed_rated_air_flow_rate",
                    "minimum_outdoor_dry_bulb_temperature_for_compressor_operation",
                    "high_speed_evaporative_condenser_effectiveness",
                    "high_speed_evaporative_condenser_air_flow_rate",
                    "high_speed_evaporative_condenser_pump_rated_power_consumption",
                    "low_speed_evaporative_condenser_effectiveness",
                    "low_speed_evaporative_condenser_air_flow_rate",
                    "low_speed_evaporative_condenser_pump_rated_power_consumption",
                    "basin_heater_capacity",
                    "basin_heater_setpoint_temperature"
                ]
            }
        },
        "type": "object",
        "memo": "Direct expansion (DX) cooling coil and condensing unit (includes electric compressor and condenser fan), two-speed (or variable-speed). Requires two sets of performance data and will interpolate between speeds. Modeled as a single coil (multi-speed compressor or multiple compressors with row split or intertwined coil).",
        "min_fields": 20.0
    }
}
```
