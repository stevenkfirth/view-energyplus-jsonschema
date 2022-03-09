```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "water_inlet_node_name": {
                    "type": "string"
                },
                "water_outlet_node_name": {
                    "type": "string"
                },
                "air_inlet_node_name": {
                    "type": "string"
                },
                "air_outlet_node_name": {
                    "type": "string"
                },
                "rated_air_flow_rate": {
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
                "rated_water_flow_rate": {
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
                "gross_rated_total_cooling_capacity": {
                    "note": "Total cooling capacity not accounting for the effect of supply air fan heat",
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
                "gross_rated_sensible_cooling_capacity": {
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
                "gross_rated_cooling_cop": {
                    "type": "number",
                    "units": "W/W",
                    "exclusiveMinimum": 0.0
                },
                "total_cooling_capacity_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "QuadvariateFunctions"
                    ]
                },
                "sensible_cooling_capacity_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "QuintvariateFunctions"
                    ]
                },
                "cooling_power_consumption_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "QuadvariateFunctions"
                    ]
                },
                "nominal_time_for_condensate_removal_to_begin": {
                    "type": "number",
                    "units": "s",
                    "minimum": 0.0,
                    "maximum": 3000.0,
                    "default": 0.0,
                    "note": "The nominal time for condensate to begin leaving the coil's condensate drain line at the coil's rated air flow and temperature conditions. Nominal time is equal to the ratio of the energy of the coil's maximum condensate holding capacity (J) to the coil's steady state latent capacity (W). Suggested value is 1000; zero value means latent degradation model is disabled."
                },
                "ratio_of_initial_moisture_evaporation_rate_and_steady_state_latent_capacity": {
                    "type": "number",
                    "units": "dimensionless",
                    "minimum": 0.0,
                    "maximum": 5.0,
                    "default": 0.0,
                    "note": "Ratio of the initial moisture evaporation rate from the cooling coil (when the compressor first turns off) and the coil's steady state latent capacity at rated air flow rate and temperature conditions. Suggested value is 1.5; zero value means latent degradation model is disabled."
                }
            },
            "required": [
                "water_inlet_node_name",
                "water_outlet_node_name",
                "air_inlet_node_name",
                "air_outlet_node_name",
                "rated_air_flow_rate",
                "rated_water_flow_rate",
                "gross_rated_total_cooling_capacity",
                "gross_rated_sensible_cooling_capacity",
                "gross_rated_cooling_cop",
                "total_cooling_capacity_curve_name",
                "sensible_cooling_capacity_curve_name",
                "cooling_power_consumption_curve_name"
            ]
        }
    },
    "group": "Coils",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "CoolingCoilsWaterToAirHP",
            "DesuperHeatingWaterOnlySources",
            "validBranchEquipmentNames"
        ],
        "reference-class-name": [
            "validBranchEquipmentTypes"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "water_inlet_node_name": {
                "field_name": "Water Inlet Node Name",
                "field_type": "a"
            },
            "water_outlet_node_name": {
                "field_name": "Water Outlet Node Name",
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
            "rated_air_flow_rate": {
                "field_name": "Rated Air Flow Rate",
                "field_type": "n"
            },
            "rated_water_flow_rate": {
                "field_name": "Rated Water Flow Rate",
                "field_type": "n"
            },
            "gross_rated_total_cooling_capacity": {
                "field_name": "Gross Rated Total Cooling Capacity",
                "field_type": "n"
            },
            "gross_rated_sensible_cooling_capacity": {
                "field_name": "Gross Rated Sensible Cooling Capacity",
                "field_type": "n"
            },
            "gross_rated_cooling_cop": {
                "field_name": "Gross Rated Cooling COP",
                "field_type": "n"
            },
            "total_cooling_capacity_curve_name": {
                "field_name": "Total Cooling Capacity Curve Name",
                "field_type": "a"
            },
            "sensible_cooling_capacity_curve_name": {
                "field_name": "Sensible Cooling Capacity Curve Name",
                "field_type": "a"
            },
            "cooling_power_consumption_curve_name": {
                "field_name": "Cooling Power Consumption Curve Name",
                "field_type": "a"
            },
            "nominal_time_for_condensate_removal_to_begin": {
                "field_name": "Nominal Time for Condensate Removal to Begin",
                "field_type": "n"
            },
            "ratio_of_initial_moisture_evaporation_rate_and_steady_state_latent_capacity": {
                "field_name": "Ratio of Initial Moisture Evaporation Rate and Steady State Latent Capacity",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "water_inlet_node_name",
            "water_outlet_node_name",
            "air_inlet_node_name",
            "air_outlet_node_name",
            "rated_air_flow_rate",
            "rated_water_flow_rate",
            "gross_rated_total_cooling_capacity",
            "gross_rated_sensible_cooling_capacity",
            "gross_rated_cooling_cop",
            "total_cooling_capacity_curve_name",
            "sensible_cooling_capacity_curve_name",
            "cooling_power_consumption_curve_name",
            "nominal_time_for_condensate_removal_to_begin",
            "ratio_of_initial_moisture_evaporation_rate_and_steady_state_latent_capacity"
        ],
        "alphas": {
            "fields": [
                "name",
                "water_inlet_node_name",
                "water_outlet_node_name",
                "air_inlet_node_name",
                "air_outlet_node_name",
                "total_cooling_capacity_curve_name",
                "sensible_cooling_capacity_curve_name",
                "cooling_power_consumption_curve_name"
            ]
        },
        "numerics": {
            "fields": [
                "rated_air_flow_rate",
                "rated_water_flow_rate",
                "gross_rated_total_cooling_capacity",
                "gross_rated_sensible_cooling_capacity",
                "gross_rated_cooling_cop",
                "nominal_time_for_condensate_removal_to_begin",
                "ratio_of_initial_moisture_evaporation_rate_and_steady_state_latent_capacity"
            ]
        }
    },
    "type": "object",
    "memo": "Direct expansion (DX) cooling coil for water-to-air heat pump (includes electric compressor), single-speed, equation-fit model. Optional inputs for moisture evaporation from wet coil when compressor cycles off with continuous fan operation. Equation-fit model uses normalized curves to describe the heat pump performance."
}
```
