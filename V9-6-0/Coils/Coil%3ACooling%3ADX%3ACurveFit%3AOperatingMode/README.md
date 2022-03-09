```
{
    "Coil:Cooling:DX:CurveFit:OperatingMode": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "rated_gross_total_cooling_capacity": {
                        "note": "Total (sensible+latent) cooling capacity not accounting for the effect of supply air fan heat. Rating point: air entering the evaporator coil at 26.7 C dry-bulb/19.4 C wet-bulb, and air entering the condenser coil at 35 C dry-bulb/23.9 C wet-bulb. gross capacity excluding supply air fan heat",
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
                    "rated_evaporator_air_flow_rate": {
                        "note": "Flow rate corresponding to rated total cooling capacity, Rated SHR and Rated COP. Should be between 0.00004027 m3/s and 0.00006041 m3/s per watt of rated total cooling capacity.",
                        "units": "m3/s",
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
                    "rated_condenser_air_flow_rate": {
                        "note": "Used to calculate evaporative condenser water use.",
                        "units": "m3/s",
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
                    "maximum_cycling_rate": {
                        "type": "number",
                        "note": "The maximum on-off cycling Rate for the compressor, which occurs at 50% run time fraction. Suggested value is 3; zero value means latent degradation model is disabled.",
                        "units": "cycles/hr",
                        "minimum": 0.0,
                        "maximum": 5.0,
                        "default": 0.0
                    },
                    "ratio_of_initial_moisture_evaporation_rate_and_steady_state_latent_capacity": {
                        "type": "number",
                        "note": "Ratio of the initial moisture evaporation rate from the cooling coil (when the compressor first turns off) and the coil's steady state latent capacity at rated air flow rate and temperature conditions. Suggested value is 1.5; zero value means latent degradation model is disabled.",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 5.0,
                        "default": 0.0
                    },
                    "latent_capacity_time_constant": {
                        "type": "number",
                        "note": "Time constant for the cooling coil's latent capacity to reach steady state after startup. Suggested value is 45; zero value means latent degradation model is disabled.",
                        "units": "s",
                        "minimum": 0.0,
                        "maximum": 500.0,
                        "default": 0.0
                    },
                    "nominal_time_for_condensate_removal_to_begin": {
                        "type": "number",
                        "note": "The nominal time for condensate to begin leaving the coil's condensate drain line at the coil's rated air flow rate and temperature conditions. Nominal time is equal to the ratio of the energy of the coil's maximum condensate holding capacity (J) to the coil's steady state latent capacity (W). Suggested value is 1000; zero value means latent degradation model is disabled.",
                        "units": "s",
                        "minimum": 0.0,
                        "maximum": 3000.0,
                        "default": 0.0
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
                    "condenser_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "AirCooled",
                            "EvaporativelyCooled"
                        ],
                        "default": "AirCooled"
                    },
                    "nominal_evaporative_condenser_pump_power": {
                        "note": "Rated power consumed by the evaporative condenser's water pump",
                        "units": "W",
                        "default": 0.0,
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
                    "nominal_speed_number": {
                        "type": "number",
                        "note": "Must be lower than or equal to the highest speed number. If blank, defaults to the highest speed number used."
                    },
                    "speed_1_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "DXCoolingSpeedNames"
                        ]
                    },
                    "speed_2_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "DXCoolingSpeedNames"
                        ]
                    },
                    "speed_3_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "DXCoolingSpeedNames"
                        ]
                    },
                    "speed_4_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "DXCoolingSpeedNames"
                        ]
                    },
                    "speed_5_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "DXCoolingSpeedNames"
                        ]
                    },
                    "speed_6_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "DXCoolingSpeedNames"
                        ]
                    },
                    "speed_7_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "DXCoolingSpeedNames"
                        ]
                    },
                    "speed_8_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "DXCoolingSpeedNames"
                        ]
                    },
                    "speed_9_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "DXCoolingSpeedNames"
                        ]
                    },
                    "speed_10_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "DXCoolingSpeedNames"
                        ]
                    }
                },
                "required": [
                    "speed_1_name"
                ]
            }
        },
        "group": "Coils",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "DXCoolingOperatingModeNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "rated_gross_total_cooling_capacity": {
                    "field_name": "Rated Gross Total Cooling Capacity",
                    "field_type": "n"
                },
                "rated_evaporator_air_flow_rate": {
                    "field_name": "Rated Evaporator Air Flow Rate",
                    "field_type": "n"
                },
                "rated_condenser_air_flow_rate": {
                    "field_name": "Rated Condenser Air Flow Rate",
                    "field_type": "n"
                },
                "maximum_cycling_rate": {
                    "field_name": "Maximum Cycling Rate",
                    "field_type": "n"
                },
                "ratio_of_initial_moisture_evaporation_rate_and_steady_state_latent_capacity": {
                    "field_name": "Ratio of Initial Moisture Evaporation Rate and Steady State Latent Capacity",
                    "field_type": "n"
                },
                "latent_capacity_time_constant": {
                    "field_name": "Latent Capacity Time Constant",
                    "field_type": "n"
                },
                "nominal_time_for_condensate_removal_to_begin": {
                    "field_name": "Nominal Time for Condensate Removal to Begin",
                    "field_type": "n"
                },
                "apply_latent_degradation_to_speeds_greater_than_1": {
                    "field_name": "Apply Latent Degradation to Speeds Greater than 1",
                    "field_type": "a"
                },
                "condenser_type": {
                    "field_name": "Condenser Type",
                    "field_type": "a"
                },
                "nominal_evaporative_condenser_pump_power": {
                    "field_name": "Nominal Evaporative Condenser Pump Power",
                    "field_type": "n"
                },
                "nominal_speed_number": {
                    "field_name": "Nominal Speed Number",
                    "field_type": "n"
                },
                "speed_1_name": {
                    "field_name": "Speed 1 Name",
                    "field_type": "a"
                },
                "speed_2_name": {
                    "field_name": "Speed 2 Name",
                    "field_type": "a"
                },
                "speed_3_name": {
                    "field_name": "Speed 3 Name",
                    "field_type": "a"
                },
                "speed_4_name": {
                    "field_name": "Speed 4 Name",
                    "field_type": "a"
                },
                "speed_5_name": {
                    "field_name": "Speed 5 Name",
                    "field_type": "a"
                },
                "speed_6_name": {
                    "field_name": "Speed 6 Name",
                    "field_type": "a"
                },
                "speed_7_name": {
                    "field_name": "Speed 7 Name",
                    "field_type": "a"
                },
                "speed_8_name": {
                    "field_name": "Speed 8 Name",
                    "field_type": "a"
                },
                "speed_9_name": {
                    "field_name": "Speed 9 Name",
                    "field_type": "a"
                },
                "speed_10_name": {
                    "field_name": "Speed 10 Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "rated_gross_total_cooling_capacity",
                "rated_evaporator_air_flow_rate",
                "rated_condenser_air_flow_rate",
                "maximum_cycling_rate",
                "ratio_of_initial_moisture_evaporation_rate_and_steady_state_latent_capacity",
                "latent_capacity_time_constant",
                "nominal_time_for_condensate_removal_to_begin",
                "apply_latent_degradation_to_speeds_greater_than_1",
                "condenser_type",
                "nominal_evaporative_condenser_pump_power",
                "nominal_speed_number",
                "speed_1_name",
                "speed_2_name",
                "speed_3_name",
                "speed_4_name",
                "speed_5_name",
                "speed_6_name",
                "speed_7_name",
                "speed_8_name",
                "speed_9_name",
                "speed_10_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "apply_latent_degradation_to_speeds_greater_than_1",
                    "condenser_type",
                    "speed_1_name",
                    "speed_2_name",
                    "speed_3_name",
                    "speed_4_name",
                    "speed_5_name",
                    "speed_6_name",
                    "speed_7_name",
                    "speed_8_name",
                    "speed_9_name",
                    "speed_10_name"
                ]
            },
            "numerics": {
                "fields": [
                    "rated_gross_total_cooling_capacity",
                    "rated_evaporator_air_flow_rate",
                    "rated_condenser_air_flow_rate",
                    "maximum_cycling_rate",
                    "ratio_of_initial_moisture_evaporation_rate_and_steady_state_latent_capacity",
                    "latent_capacity_time_constant",
                    "nominal_time_for_condensate_removal_to_begin",
                    "nominal_evaporative_condenser_pump_power",
                    "nominal_speed_number"
                ]
            }
        },
        "type": "object",
        "memo": "DX cooling coil performance for a single operating mode which may have one or more speeds.",
        "min_fields": 13.0
    }
}
```
