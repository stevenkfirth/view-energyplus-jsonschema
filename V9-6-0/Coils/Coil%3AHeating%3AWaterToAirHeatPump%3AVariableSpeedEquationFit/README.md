```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "water_to_refrigerant_hx_water_inlet_node_name": {
                    "type": "string"
                },
                "water_to_refrigerant_hx_water_outlet_node_name": {
                    "type": "string"
                },
                "indoor_air_inlet_node_name": {
                    "type": "string"
                },
                "indoor_air_outlet_node_name": {
                    "type": "string"
                },
                "number_of_speeds": {
                    "type": "number",
                    "units": "dimensionless",
                    "minimum": 1.0,
                    "maximum": 10.0,
                    "default": 2.0
                },
                "nominal_speed_level": {
                    "type": "number",
                    "units": "dimensionless",
                    "default": 2.0,
                    "note": "must be lower than or equal to the highest speed number"
                },
                "rated_heating_capacity_at_selected_nominal_speed_level": {
                    "units": "W",
                    "default": "Autosize",
                    "anyOf": [
                        {
                            "type": "number"
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
                "rated_air_flow_rate_at_selected_nominal_speed_level": {
                    "units": "m3/s",
                    "default": "Autosize",
                    "anyOf": [
                        {
                            "type": "number"
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
                "rated_water_flow_rate_at_selected_nominal_speed_level": {
                    "units": "m3/s",
                    "ip-units": "gal/min",
                    "default": "Autosize",
                    "anyOf": [
                        {
                            "type": "number"
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
                "energy_part_load_fraction_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "quadratic curve = a + b*PLR + c*PLR**2 cubic curve = a + b*PLR + c*PLR**2 + d*PLR**3 PLR = part load ratio (heating load/steady state capacity)"
                },
                "speed_1_reference_unit_gross_rated_heating_capacity": {
                    "type": "number",
                    "note": "Heating capacity not accounting for the effect of supply air fan heat",
                    "units": "W",
                    "minimum": 0.0
                },
                "speed_1_reference_unit_gross_rated_heating_cop": {
                    "type": "number",
                    "units": "W/W",
                    "exclusiveMinimum": 0.0
                },
                "speed_1_reference_unit_rated_air_flow": {
                    "type": "number",
                    "units": "m3/s",
                    "minimum": 0.0
                },
                "speed_1_reference_unit_rated_water_flow_rate": {
                    "type": "number",
                    "units": "m3/s",
                    "ip-units": "gal/min",
                    "minimum": 0.0
                },
                "speed_1_heating_capacity_function_of_temperature_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ],
                    "note": "curve = a + b*db + c*db**2 + d*ewt + e*ewt**2 + f*db*ewt db = entering air dry-bulb temperature (C) ewt = water entering temperature seen by the evaporator (C)"
                },
                "speed_1_total_heating_capacity_function_of_air_flow_fraction_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
                },
                "speed_1_heating_capacity_function_of_water_flow_fraction_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "quadratic curve = a + b*ffw + c*ffw**2 cubic curve = a + b*ffw + c*ffw**2 + d*ffw**3 ffw = Fraction of the full load Water Flow"
                },
                "speed_1_energy_input_ratio_function_of_temperature_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ],
                    "note": "curve = a + b*db + c*db**2 + d*ewt + e*ewt**2 + f*db*ewt db = entering air dry-bulb temperature (C) ewt = water entering temperature seen by the evaporator (C)"
                },
                "speed_1_energy_input_ratio_function_of_air_flow_fraction_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
                },
                "speed_1_energy_input_ratio_function_of_water_flow_fraction_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "quadratic curve = a + b*ffw + c*ffw**2 cubic curve = a + b*ffw + c*ffw**2 + d*ffw**3 ffw = Fraction of the full load Water Flow"
                },
                "speed_1_reference_unit_waste_heat_fraction_of_input_power_at_rated_conditions": {
                    "type": "number",
                    "units": "dimensionless",
                    "minimum": 0.0
                },
                "speed_1_waste_heat_function_of_temperature_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ],
                    "note": "curve = a + b*db + c*db**2 + d*ewt + e*ewt**2 + f*db*ewt db = entering air dry-bulb temperature (C) ewt = water entering temperature seen by the evaporator (C)"
                },
                "speed_2_reference_unit_gross_rated_heating_capacity": {
                    "type": "number",
                    "note": "Heating capacity not accounting for the effect of supply air fan heat",
                    "units": "W",
                    "minimum": 0.0
                },
                "speed_2_reference_unit_gross_rated_heating_cop": {
                    "type": "number",
                    "units": "W/W",
                    "exclusiveMinimum": 0.0
                },
                "speed_2_reference_unit_rated_air_flow_rate": {
                    "type": "number",
                    "units": "m3/s",
                    "minimum": 0.0
                },
                "speed_2_reference_unit_rated_water_flow_rate": {
                    "type": "number",
                    "units": "m3/s",
                    "ip-units": "gal/min",
                    "minimum": 0.0
                },
                "speed_2_heating_capacity_function_of_temperature_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ],
                    "note": "curve = a + b*db + c*db**2 + d*ewt + e*ewt**2 + f*db*ewt db = entering air dry-bulb temperature (C) ewt = water entering temperature seen by the evaporator (C)"
                },
                "speed_2_total_heating_capacity_function_of_air_flow_fraction_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
                },
                "speed_2_heating_capacity_function_of_water_flow_fraction_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "quadratic curve = a + b*ffw + c*ffw**2 cubic curve = a + b*ffw + c*ffw**2 + d*ffw**3 ffw = Fraction of the full load Water Flow"
                },
                "speed_2_energy_input_ratio_function_of_temperature_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ],
                    "note": "curve = a + b*db + c*db**2 + d*ewt + e*ewt**2 + f*db*ewt db = entering air dry-bulb temperature (C) ewt = water entering temperature seen by the evaporator (C)"
                },
                "speed_2_energy_input_ratio_function_of_air_flow_fraction_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
                },
                "speed_2_energy_input_ratio_function_of_water_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "optional quadratic curve = a + b*ffw + c*ffw**2 cubic curve = a + b*ffw + c*ffw**2 + d*ffw**3 ffw = Fraction of the full load Water Flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "speed_2_reference_unit_waste_heat_fraction_of_input_power_at_rated_conditions": {
                    "type": "number",
                    "units": "dimensionless",
                    "minimum": 0.0
                },
                "speed_2_waste_heat_function_of_temperature_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ],
                    "note": "curve = a + b*db + c*db**2 + d*ewt + e*ewt**2 + f*db*ewt db = entering air dry-bulb temperature (C) ewt = water entering temperature seen by the evaporator (C)"
                },
                "speed_3_reference_unit_gross_rated_heating_capacity": {
                    "type": "number",
                    "note": "Heating capacity not accounting for the effect of supply air fan heat",
                    "units": "W",
                    "minimum": 0.0
                },
                "speed_3_reference_unit_gross_rated_heating_cop": {
                    "type": "number",
                    "units": "W/W",
                    "exclusiveMinimum": 0.0
                },
                "speed_3_reference_unit_rated_air_flow_rate": {
                    "type": "number",
                    "units": "m3/s",
                    "minimum": 0.0
                },
                "speed_3_reference_unit_rated_water_flow_rate": {
                    "type": "number",
                    "units": "m3/s",
                    "ip-units": "gal/min",
                    "minimum": 0.0
                },
                "speed_3_heating_capacity_function_of_temperature_curve_name": {
                    "type": "string",
                    "note": "optional curve = a + b*db + c*db**2 + d*ewt + e*ewt**2 + f*db*ewt db = entering air dry-bulb temperature (C) ewt = water entering temperature seen by the evaporator (C)",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ]
                },
                "speed_3_total_heating_capacity_function_of_air_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "optional quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "speed_3_heating_capacity_function_of_water_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "optional quadratic curve = a + b*ffw + c*ffw**2 cubic curve = a + b*ffw + c*ffw**2 + d*ffw**3 ffw = Fraction of the full load Water Flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "speed_3_energy_input_ratio_function_of_temperature_curve_name": {
                    "type": "string",
                    "note": "optional curve = a + b*db + c*db**2 + d*ewt + e*ewt**2 + f*db*ewt db = entering air dry-bulb temperature (C) ewt = water entering temperature seen by the evaporator (C)",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ]
                },
                "speed_3_energy_input_ratio_function_of_air_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "optional quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "speed_3_energy_input_ratio_function_of_water_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "optional quadratic curve = a + b*ffw + c*ffw**2 cubic curve = a + b*ffw + c*ffw**2 + d*ffw**3 ffw = Fraction of the full load Water Flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "speed_3_reference_unit_waste_heat_fraction_of_input_power_at_rated_conditions": {
                    "type": "number",
                    "units": "dimensionless",
                    "minimum": 0.0
                },
                "speed_3_waste_heat_function_of_temperature_curve_name": {
                    "type": "string",
                    "note": "optional curve = a + b*db + c*db**2 + d*ewt + e*ewt**2 + f*db*ewt db = entering air dry-bulb temperature (C) ewt = water entering temperature seen by the evaporator (C)",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ]
                },
                "speed_4_reference_unit_gross_rated_heating_capacity": {
                    "type": "number",
                    "note": "Heating capacity not accounting for the effect of supply air fan heat",
                    "units": "W",
                    "minimum": 0.0
                },
                "speed_4_reference_unit_gross_rated_heating_cop": {
                    "type": "number",
                    "units": "W/W",
                    "exclusiveMinimum": 0.0
                },
                "speed_4_reference_unit_rated_air_flow_rate": {
                    "type": "number",
                    "units": "m3/s",
                    "minimum": 0.0
                },
                "speed_4_reference_unit_rated_water_flow_rate": {
                    "type": "number",
                    "units": "m3/s",
                    "ip-units": "gal/min",
                    "minimum": 0.0
                },
                "speed_4_heating_capacity_function_of_temperature_curve_name": {
                    "type": "string",
                    "note": "optional curve = a + b*db + c*db**2 + d*ewt + e*ewt**2 + f*db*ewt db = entering air dry-bulb temperature (C) ewt = water entering temperature seen by the evaporator (C)",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ]
                },
                "speed_4_total_heating_capacity_function_of_air_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "optional quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "speed_4_heating_capacity_function_of_water_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "optional quadratic curve = a + b*ffw + c*ffw**2 cubic curve = a + b*ffw + c*ffw**2 + d*ffw**3 ffw = Fraction of the full load Water Flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "speed_4_energy_input_ratio_function_of_temperature_curve_name": {
                    "type": "string",
                    "note": "optional curve = a + b*db + c*db**2 + d*ewt + e*ewt**2 + f*db*ewt db = entering air dry-bulb temperature (C) ewt = water entering temperature seen by the evaporator (C)",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ]
                },
                "speed_4_energy_input_ratio_function_of_air_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "optional quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "speed_4_energy_input_ratio_function_of_water_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "optional quadratic curve = a + b*ffw + c*ffw**2 cubic curve = a + b*ffw + c*ffw**2 + d*ffw**3 ffw = Fraction of the full load Water Flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "speed_4_reference_unit_waste_heat_fraction_of_input_power_at_rated_conditions": {
                    "type": "number",
                    "units": "dimensionless",
                    "minimum": 0.0
                },
                "speed_4_waste_heat_function_of_temperature_curve_name": {
                    "type": "string",
                    "note": "optional curve = a + b*db + c*db**2 + d*ewt + e*ewt**2 + f*db*ewt db = entering air dry-bulb temperature (C) ewt = water entering temperature seen by the evaporator (C)",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ]
                },
                "speed_5_reference_unit_gross_rated_heating_capacity": {
                    "type": "number",
                    "note": "Heating capacity not accounting for the effect of supply air fan heat",
                    "units": "W",
                    "minimum": 0.0
                },
                "speed_5_reference_unit_gross_rated_heating_cop": {
                    "type": "number",
                    "units": "W/W",
                    "exclusiveMinimum": 0.0
                },
                "speed_5_reference_unit_rated_air_flow_rate": {
                    "type": "number",
                    "units": "m3/s",
                    "minimum": 0.0
                },
                "speed_5_reference_unit_rated_water_flow_rate": {
                    "type": "number",
                    "units": "m3/s",
                    "ip-units": "gal/min",
                    "minimum": 0.0
                },
                "speed_5_heating_capacity_function_of_temperature_curve_name": {
                    "type": "string",
                    "note": "optional curve = a + b*db + c*db**2 + d*ewt + e*ewt**2 + f*db*ewt db = entering air dry-bulb temperature (C) ewt = water entering temperature seen by the evaporator (C)",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ]
                },
                "speed_5_total_heating_capacity_function_of_air_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "optional quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "speed_5_heating_capacity_function_of_water_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "optional quadratic curve = a + b*ffw + c*ffw**2 cubic curve = a + b*ffw + c*ffw**2 + d*ffw**3 ffw = Fraction of the full load Water Flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "speed_5_energy_input_ratio_function_of_temperature_curve_name": {
                    "type": "string",
                    "note": "optional curve = a + b*db + c*db**2 + d*ewt + e*ewt**2 + f*db*ewt db = entering air dry-bulb temperature (C) ewt = water entering temperature seen by the evaporator (C)",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ]
                },
                "speed_5_energy_input_ratio_function_of_air_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "optional quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "speed_5_energy_input_ratio_function_of_water_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "optional quadratic curve = a + b*ffw + c*ffw**2 cubic curve = a + b*ffw + c*ffw**2 + d*ffw**3 ffw = Fraction of the full load Water Flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "speed_5_reference_unit_waste_heat_fraction_of_input_power_at_rated_conditions": {
                    "type": "number",
                    "units": "dimensionless",
                    "minimum": 0.0
                },
                "speed_5_waste_heat_function_of_temperature_curve_name": {
                    "type": "string",
                    "note": "optional curve = a + b*db + c*db**2 + d*ewt + e*ewt**2 + f*db*ewt db = entering air dry-bulb temperature (C) ewt = water entering temperature seen by the evaporator (C)",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ]
                },
                "speed_6_reference_unit_gross_rated_heating_capacity": {
                    "type": "number",
                    "note": "Heating capacity not accounting for the effect of supply air fan heat",
                    "units": "W",
                    "minimum": 0.0
                },
                "speed_6_reference_unit_gross_rated_heating_cop": {
                    "type": "number",
                    "units": "W/W",
                    "exclusiveMinimum": 0.0
                },
                "speed_6_reference_unit_rated_air_flow_rate": {
                    "type": "number",
                    "units": "m3/s",
                    "minimum": 0.0
                },
                "speed_6_reference_unit_rated_water_flow_rate": {
                    "type": "number",
                    "units": "m3/s",
                    "ip-units": "gal/min",
                    "minimum": 0.0
                },
                "speed_6_heating_capacity_function_of_temperature_curve_name": {
                    "type": "string",
                    "note": "optional curve = a + b*db + c*db**2 + d*ewt + e*ewt**2 + f*db*ewt db = entering air dry-bulb temperature (C) ewt = water entering temperature seen by the evaporator (C)",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ]
                },
                "speed_6_total_heating_capacity_function_of_air_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "optional quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "speed_6_heating_capacity_function_of_water_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "optional quadratic curve = a + b*ffw + c*ffw**2 cubic curve = a + b*ffw + c*ffw**2 + d*ffw**3 ffw = Fraction of the full load Water Flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "speed_6_energy_input_ratio_function_of_temperature_curve_name": {
                    "type": "string",
                    "note": "optional curve = a + b*db + c*db**2 + d*ewt + e*ewt**2 + f*db*ewt db = entering air dry-bulb temperature (C) ewt = water entering temperature seen by the evaporator (C)",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ]
                },
                "speed_6_energy_input_ratio_function_of_air_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "optional quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "speed_6_energy_input_ratio_function_of_water_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "optional quadratic curve = a + b*ffw + c*ffw**2 cubic curve = a + b*ffw + c*ffw**2 + d*ffw**3 ffw = Fraction of the full load Water Flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "speed_6_reference_unit_waste_heat_fraction_of_input_power_at_rated_conditions": {
                    "type": "number",
                    "units": "dimensionless",
                    "minimum": 0.0
                },
                "speed_6_waste_heat_function_of_temperature_curve_name": {
                    "type": "string",
                    "note": "optional curve = a + b*db + c*db**2 + d*ewt + e*ewt**2 + f*db*ewt db = entering air dry-bulb temperature (C) ewt = water entering temperature seen by the evaporator (C)",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ]
                },
                "speed_7_reference_unit_gross_rated_heating_capacity": {
                    "type": "number",
                    "note": "Heating capacity not accounting for the effect of supply air fan heat",
                    "units": "W",
                    "minimum": 0.0
                },
                "speed_7_reference_unit_gross_rated_heating_cop": {
                    "type": "number",
                    "units": "W/W",
                    "exclusiveMinimum": 0.0
                },
                "speed_7_reference_unit_rated_air_flow_rate": {
                    "type": "number",
                    "units": "m3/s",
                    "minimum": 0.0
                },
                "speed_7_reference_unit_rated_water_flow_rate": {
                    "type": "number",
                    "units": "m3/s",
                    "ip-units": "gal/min",
                    "minimum": 0.0
                },
                "speed_7_heating_capacity_function_of_temperature_curve_name": {
                    "type": "string",
                    "note": "optional curve = a + b*db + c*db**2 + d*ewt + e*ewt**2 + f*db*ewt db = entering air dry-bulb temperature (C) ewt = water entering temperature seen by the evaporator (C)",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ]
                },
                "speed_7_total_heating_capacity_function_of_air_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "optional quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "speed_7_heating_capacity_function_of_water_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "optional quadratic curve = a + b*ffw + c*ffw**2 cubic curve = a + b*ffw + c*ffw**2 + d*ffw**3 ffw = Fraction of the full load Water Flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "speed_7_energy_input_ratio_function_of_temperature_curve_name": {
                    "type": "string",
                    "note": "optional curve = a + b*db + c*db**2 + d*ewt + e*ewt**2 + f*db*ewt db = entering air dry-bulb temperature (C) ewt = water entering temperature seen by the evaporator (C)",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ]
                },
                "speed_7_energy_input_ratio_function_of_air_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "optional quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "speed_7_energy_input_ratio_function_of_water_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "optional quadratic curve = a + b*ffw + c*ffw**2 cubic curve = a + b*ffw + c*ffw**2 + d*ffw**3 ffw = Fraction of the full load Water Flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "speed_7_reference_unit_waste_heat_fraction_of_input_power_at_rated_conditions": {
                    "type": "number",
                    "units": "dimensionless",
                    "minimum": 0.0
                },
                "speed_7_waste_heat_function_of_temperature_curve_name": {
                    "type": "string",
                    "note": "optional curve = a + b*db + c*db**2 + d*ewt + e*ewt**2 + f*db*ewt db = entering air dry-bulb temperature (C) ewt = water entering temperature seen by the evaporator (C)",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ]
                },
                "speed_8_reference_unit_gross_rated_heating_capacity": {
                    "type": "number",
                    "note": "Heating capacity not accounting for the effect of supply air fan heat",
                    "units": "W",
                    "minimum": 0.0
                },
                "speed_8_reference_unit_gross_rated_heating_cop": {
                    "type": "number",
                    "units": "W/W",
                    "exclusiveMinimum": 0.0
                },
                "speed_8_reference_unit_rated_air_flow_rate": {
                    "type": "number",
                    "units": "m3/s",
                    "minimum": 0.0
                },
                "speed_8_reference_unit_rated_water_flow_rate": {
                    "type": "number",
                    "units": "m3/s",
                    "ip-units": "gal/min",
                    "minimum": 0.0
                },
                "speed_8_heating_capacity_function_of_temperature_curve_name": {
                    "type": "string",
                    "note": "optional curve = a + b*db + c*db**2 + d*ewt + e*ewt**2 + f*db*ewt db = entering air dry-bulb temperature (C) ewt = water entering temperature seen by the evaporator (C)",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ]
                },
                "speed_8_total_heating_capacity_function_of_air_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "optional quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "speed_8_heating_capacity_function_of_water_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "optional quadratic curve = a + b*ffw + c*ffw**2 cubic curve = a + b*ffw + c*ffw**2 + d*ffw**3 ffw = Fraction of the full load Water Flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "speed_8_energy_input_ratio_function_of_temperature_curve_name": {
                    "type": "string",
                    "note": "optional curve = a + b*db + c*db**2 + d*ewt + e*ewt**2 + f*db*ewt db = entering air dry-bulb temperature (C) ewt = water entering temperature seen by the evaporator (C)",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ]
                },
                "speed_8_energy_input_ratio_function_of_air_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "optional quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "speed_8_energy_input_ratio_function_of_water_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "optional quadratic curve = a + b*ffw + c*ffw**2 cubic curve = a + b*ffw + c*ffw**2 + d*ffw**3 ffw = Fraction of the full load Water Flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "speed_8_reference_unit_waste_heat_fraction_of_input_power_at_rated_conditions": {
                    "type": "number",
                    "units": "dimensionless",
                    "minimum": 0.0
                },
                "speed_8_waste_heat_function_of_temperature_curve_name": {
                    "type": "string",
                    "note": "optional curve = a + b*db + c*db**2 + d*ewt + e*ewt**2 + f*db*ewt db = entering air dry-bulb temperature (C) ewt = water entering temperature seen by the evaporator (C)",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ]
                },
                "speed_9_reference_unit_gross_rated_heating_capacity": {
                    "type": "number",
                    "note": "Heating capacity not accounting for the effect of supply air fan heat",
                    "units": "W",
                    "minimum": 0.0
                },
                "speed_9_reference_unit_gross_rated_heating_cop": {
                    "type": "number",
                    "units": "W/W",
                    "exclusiveMinimum": 0.0
                },
                "speed_9_reference_unit_rated_air_flow_rate": {
                    "type": "number",
                    "units": "m3/s",
                    "minimum": 0.0
                },
                "speed_9_reference_unit_rated_water_flow_rate": {
                    "type": "number",
                    "units": "m3/s",
                    "ip-units": "gal/min",
                    "minimum": 0.0
                },
                "speed_9_heating_capacity_function_of_temperature_curve_name": {
                    "type": "string",
                    "note": "optional curve = a + b*db + c*db**2 + d*ewt + e*ewt**2 + f*db*ewt db = entering air dry-bulb temperature (C) ewt = water entering temperature seen by the evaporator (C)",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ]
                },
                "speed_9_total_heating_capacity_function_of_air_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "optional quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "speed_9_heating_capacity_function_of_water_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "optional quadratic curve = a + b*ffw + c*ffw**2 cubic curve = a + b*ffw + c*ffw**2 + d*ffw**3 ffw = Fraction of the full load Water Flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "speed_9_energy_input_ratio_function_of_temperature_curve_name": {
                    "type": "string",
                    "note": "optional curve = a + b*db + c*db**2 + d*ewt + e*ewt**2 + f*db*ewt db = entering air dry-bulb temperature (C) ewt = water entering temperature seen by the evaporator (C)",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ]
                },
                "speed_9_energy_input_ratio_function_of_air_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "optional quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "speed_9_energy_input_ratio_function_of_water_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "optional quadratic curve = a + b*ffw + c*ffw**2 cubic curve = a + b*ffw + c*ffw**2 + d*ffw**3 ffw = Fraction of the full load Water Flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "speed_9_reference_unit_waste_heat_fraction_of_input_power_at_rated_conditions": {
                    "type": "number",
                    "units": "dimensionless",
                    "minimum": 0.0
                },
                "speed_9_waste_heat_function_of_temperature_curve_name": {
                    "type": "string",
                    "note": "optional curve = a + b*db + c*db**2 + d*ewt + e*ewt**2 + f*db*ewt db = entering air dry-bulb temperature (C) ewt = water entering temperature seen by the evaporator (C)",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ]
                },
                "speed_10_reference_unit_gross_rated_heating_capacity": {
                    "type": "number",
                    "note": "Heating capacity not accounting for the effect of supply air fan heat",
                    "units": "W",
                    "minimum": 0.0
                },
                "speed_10_reference_unit_gross_rated_heating_cop": {
                    "type": "number",
                    "units": "W/W",
                    "exclusiveMinimum": 0.0
                },
                "speed_10_reference_unit_rated_air_flow_rate": {
                    "type": "number",
                    "units": "m3/s",
                    "minimum": 0.0
                },
                "speed_10_reference_unit_rated_water_flow_rate": {
                    "type": "number",
                    "units": "m3/s",
                    "ip-units": "gal/min",
                    "minimum": 0.0
                },
                "speed_10_heating_capacity_function_of_temperature_curve_name": {
                    "type": "string",
                    "note": "optional curve = a + b*db + c*db**2 + d*ewt + e*ewt**2 + f*db*ewt db = entering air dry-bulb temperature (C) ewt = water entering temperature seen by the evaporator (C)",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ]
                },
                "speed_10_total_heating_capacity_function_of_air_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "optional quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "speed_10_heating_capacity_function_of_water_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "optional quadratic curve = a + b*ffw + c*ffw**2 cubic curve = a + b*ffw + c*ffw**2 + d*ffw**3 ffw = Fraction of the full load Water Flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "speed_10_energy_input_ratio_function_of_temperature_curve_name": {
                    "type": "string",
                    "note": "optional curve = a + b*db + c*db**2 + d*ewt + e*ewt**2 + f*db*ewt db = entering air dry-bulb temperature (C) ewt = water entering temperature seen by the evaporator (C)",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ]
                },
                "speed_10_energy_input_ratio_function_of_air_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "optional quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "speed_10_energy_input_ratio_function_of_water_flow_fraction_curve_name": {
                    "type": "string",
                    "note": "optional quadratic curve = a + b*ffw + c*ffw**2 cubic curve = a + b*ffw + c*ffw**2 + d*ffw**3 ffw = Fraction of the full load Water Flow",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "speed_10_reference_unit_waste_heat_fraction_of_input_power_at_rated_conditions": {
                    "type": "number",
                    "units": "dimensionless",
                    "minimum": 0.0
                },
                "speed_10_waste_heat_function_of_temperature_curve_name": {
                    "type": "string",
                    "note": "optional curve = a + b*db + c*db**2 + d*ewt + e*ewt**2 + f*db*ewt db = entering air dry-bulb temperature (C) ewt = water entering temperature seen by the evaporator (C)",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ]
                }
            },
            "required": [
                "water_to_refrigerant_hx_water_inlet_node_name",
                "water_to_refrigerant_hx_water_outlet_node_name",
                "indoor_air_inlet_node_name",
                "indoor_air_outlet_node_name",
                "energy_part_load_fraction_curve_name",
                "speed_1_reference_unit_gross_rated_heating_capacity",
                "speed_1_reference_unit_gross_rated_heating_cop",
                "speed_1_reference_unit_rated_air_flow",
                "speed_1_reference_unit_rated_water_flow_rate",
                "speed_1_heating_capacity_function_of_temperature_curve_name",
                "speed_1_total_heating_capacity_function_of_air_flow_fraction_curve_name",
                "speed_1_heating_capacity_function_of_water_flow_fraction_curve_name",
                "speed_1_energy_input_ratio_function_of_temperature_curve_name",
                "speed_1_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                "speed_1_energy_input_ratio_function_of_water_flow_fraction_curve_name",
                "speed_1_reference_unit_waste_heat_fraction_of_input_power_at_rated_conditions",
                "speed_1_waste_heat_function_of_temperature_curve_name"
            ]
        }
    },
    "group": "Coils",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "HeatingCoilsWaterToAirVSHP",
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
            "water_to_refrigerant_hx_water_inlet_node_name": {
                "field_name": "Water-to-Refrigerant HX Water Inlet Node Name",
                "field_type": "a"
            },
            "water_to_refrigerant_hx_water_outlet_node_name": {
                "field_name": "Water-to-Refrigerant HX Water Outlet Node Name",
                "field_type": "a"
            },
            "indoor_air_inlet_node_name": {
                "field_name": "Indoor Air Inlet Node Name",
                "field_type": "a"
            },
            "indoor_air_outlet_node_name": {
                "field_name": "Indoor Air Outlet Node Name",
                "field_type": "a"
            },
            "number_of_speeds": {
                "field_name": "Number of Speeds",
                "field_type": "n"
            },
            "nominal_speed_level": {
                "field_name": "Nominal Speed Level",
                "field_type": "n"
            },
            "rated_heating_capacity_at_selected_nominal_speed_level": {
                "field_name": "Rated Heating Capacity At Selected Nominal Speed Level",
                "field_type": "n"
            },
            "rated_air_flow_rate_at_selected_nominal_speed_level": {
                "field_name": "Rated Air Flow Rate At Selected Nominal Speed Level",
                "field_type": "n"
            },
            "rated_water_flow_rate_at_selected_nominal_speed_level": {
                "field_name": "Rated Water Flow Rate At Selected Nominal Speed Level",
                "field_type": "n"
            },
            "energy_part_load_fraction_curve_name": {
                "field_name": "Energy Part Load Fraction Curve Name",
                "field_type": "a"
            },
            "speed_1_reference_unit_gross_rated_heating_capacity": {
                "field_name": "Speed 1 Reference Unit Gross Rated Heating Capacity",
                "field_type": "n"
            },
            "speed_1_reference_unit_gross_rated_heating_cop": {
                "field_name": "Speed 1 Reference Unit Gross Rated Heating COP",
                "field_type": "n"
            },
            "speed_1_reference_unit_rated_air_flow": {
                "field_name": "Speed 1 Reference Unit Rated Air Flow",
                "field_type": "n"
            },
            "speed_1_reference_unit_rated_water_flow_rate": {
                "field_name": "Speed 1 Reference Unit Rated Water Flow Rate",
                "field_type": "n"
            },
            "speed_1_heating_capacity_function_of_temperature_curve_name": {
                "field_name": "Speed 1 Heating Capacity Function of Temperature Curve Name",
                "field_type": "a"
            },
            "speed_1_total_heating_capacity_function_of_air_flow_fraction_curve_name": {
                "field_name": "Speed 1 Total  Heating Capacity Function of Air Flow Fraction Curve Name",
                "field_type": "a"
            },
            "speed_1_heating_capacity_function_of_water_flow_fraction_curve_name": {
                "field_name": "Speed 1 Heating Capacity Function of Water Flow Fraction Curve Name",
                "field_type": "a"
            },
            "speed_1_energy_input_ratio_function_of_temperature_curve_name": {
                "field_name": "Speed 1 Energy Input Ratio Function of Temperature Curve Name",
                "field_type": "a"
            },
            "speed_1_energy_input_ratio_function_of_air_flow_fraction_curve_name": {
                "field_name": "Speed 1 Energy Input Ratio Function of Air Flow Fraction Curve Name",
                "field_type": "a"
            },
            "speed_1_energy_input_ratio_function_of_water_flow_fraction_curve_name": {
                "field_name": "Speed 1 Energy Input Ratio Function of Water Flow Fraction Curve Name",
                "field_type": "a"
            },
            "speed_1_reference_unit_waste_heat_fraction_of_input_power_at_rated_conditions": {
                "field_name": "Speed 1 Reference Unit Waste Heat Fraction of Input Power At Rated Conditions",
                "field_type": "n"
            },
            "speed_1_waste_heat_function_of_temperature_curve_name": {
                "field_name": "Speed 1 Waste Heat Function of Temperature Curve Name",
                "field_type": "a"
            },
            "speed_2_reference_unit_gross_rated_heating_capacity": {
                "field_name": "Speed 2 Reference Unit Gross Rated Heating Capacity",
                "field_type": "n"
            },
            "speed_2_reference_unit_gross_rated_heating_cop": {
                "field_name": "Speed 2 Reference Unit Gross Rated Heating COP",
                "field_type": "n"
            },
            "speed_2_reference_unit_rated_air_flow_rate": {
                "field_name": "Speed 2 Reference Unit Rated Air Flow Rate",
                "field_type": "n"
            },
            "speed_2_reference_unit_rated_water_flow_rate": {
                "field_name": "Speed 2 Reference Unit Rated Water Flow Rate",
                "field_type": "n"
            },
            "speed_2_heating_capacity_function_of_temperature_curve_name": {
                "field_name": "Speed 2 Heating Capacity Function of Temperature Curve Name",
                "field_type": "a"
            },
            "speed_2_total_heating_capacity_function_of_air_flow_fraction_curve_name": {
                "field_name": "Speed 2 Total  Heating Capacity Function of Air Flow Fraction Curve Name",
                "field_type": "a"
            },
            "speed_2_heating_capacity_function_of_water_flow_fraction_curve_name": {
                "field_name": "Speed 2 Heating Capacity Function of Water Flow Fraction Curve Name",
                "field_type": "a"
            },
            "speed_2_energy_input_ratio_function_of_temperature_curve_name": {
                "field_name": "Speed 2 Energy Input Ratio Function of Temperature Curve Name",
                "field_type": "a"
            },
            "speed_2_energy_input_ratio_function_of_air_flow_fraction_curve_name": {
                "field_name": "Speed 2 Energy Input Ratio Function of Air Flow Fraction Curve Name",
                "field_type": "a"
            },
            "speed_2_energy_input_ratio_function_of_water_flow_fraction_curve_name": {
                "field_name": "Speed 2 Energy Input Ratio Function of Water Flow Fraction Curve Name",
                "field_type": "a"
            },
            "speed_2_reference_unit_waste_heat_fraction_of_input_power_at_rated_conditions": {
                "field_name": "Speed 2 Reference Unit Waste Heat Fraction of Input Power At Rated Conditions",
                "field_type": "n"
            },
            "speed_2_waste_heat_function_of_temperature_curve_name": {
                "field_name": "Speed 2 Waste Heat Function of Temperature Curve Name",
                "field_type": "a"
            },
            "speed_3_reference_unit_gross_rated_heating_capacity": {
                "field_name": "Speed 3 Reference Unit Gross Rated Heating Capacity",
                "field_type": "n"
            },
            "speed_3_reference_unit_gross_rated_heating_cop": {
                "field_name": "Speed 3 Reference Unit Gross Rated Heating COP",
                "field_type": "n"
            },
            "speed_3_reference_unit_rated_air_flow_rate": {
                "field_name": "Speed 3 Reference Unit Rated Air Flow Rate",
                "field_type": "n"
            },
            "speed_3_reference_unit_rated_water_flow_rate": {
                "field_name": "Speed 3 Reference Unit Rated Water Flow Rate",
                "field_type": "n"
            },
            "speed_3_heating_capacity_function_of_temperature_curve_name": {
                "field_name": "Speed 3 Heating Capacity Function of Temperature Curve Name",
                "field_type": "a"
            },
            "speed_3_total_heating_capacity_function_of_air_flow_fraction_curve_name": {
                "field_name": "Speed 3 Total  Heating Capacity Function of Air Flow Fraction Curve Name",
                "field_type": "a"
            },
            "speed_3_heating_capacity_function_of_water_flow_fraction_curve_name": {
                "field_name": "Speed 3 Heating Capacity Function of Water Flow Fraction Curve Name",
                "field_type": "a"
            },
            "speed_3_energy_input_ratio_function_of_temperature_curve_name": {
                "field_name": "Speed 3 Energy Input Ratio Function of Temperature Curve Name",
                "field_type": "a"
            },
            "speed_3_energy_input_ratio_function_of_air_flow_fraction_curve_name": {
                "field_name": "Speed 3 Energy Input Ratio Function of Air Flow Fraction Curve Name",
                "field_type": "a"
            },
            "speed_3_energy_input_ratio_function_of_water_flow_fraction_curve_name": {
                "field_name": "Speed 3 Energy Input Ratio Function of Water Flow Fraction Curve Name",
                "field_type": "a"
            },
            "speed_3_reference_unit_waste_heat_fraction_of_input_power_at_rated_conditions": {
                "field_name": "Speed 3 Reference Unit Waste Heat Fraction of Input Power At Rated Conditions",
                "field_type": "n"
            },
            "speed_3_waste_heat_function_of_temperature_curve_name": {
                "field_name": "Speed 3 Waste Heat Function of Temperature Curve Name",
                "field_type": "a"
            },
            "speed_4_reference_unit_gross_rated_heating_capacity": {
                "field_name": "Speed 4 Reference Unit Gross Rated Heating Capacity",
                "field_type": "n"
            },
            "speed_4_reference_unit_gross_rated_heating_cop": {
                "field_name": "Speed 4 Reference Unit Gross Rated Heating COP",
                "field_type": "n"
            },
            "speed_4_reference_unit_rated_air_flow_rate": {
                "field_name": "Speed 4 Reference Unit Rated Air Flow Rate",
                "field_type": "n"
            },
            "speed_4_reference_unit_rated_water_flow_rate": {
                "field_name": "Speed 4 Reference Unit Rated Water Flow Rate",
                "field_type": "n"
            },
            "speed_4_heating_capacity_function_of_temperature_curve_name": {
                "field_name": "Speed 4 Heating Capacity Function of Temperature Curve Name",
                "field_type": "a"
            },
            "speed_4_total_heating_capacity_function_of_air_flow_fraction_curve_name": {
                "field_name": "Speed 4 Total  Heating Capacity Function of Air Flow Fraction Curve Name",
                "field_type": "a"
            },
            "speed_4_heating_capacity_function_of_water_flow_fraction_curve_name": {
                "field_name": "Speed 4 Heating Capacity Function of Water Flow Fraction Curve Name",
                "field_type": "a"
            },
            "speed_4_energy_input_ratio_function_of_temperature_curve_name": {
                "field_name": "Speed 4 Energy Input Ratio Function of Temperature Curve Name",
                "field_type": "a"
            },
            "speed_4_energy_input_ratio_function_of_air_flow_fraction_curve_name": {
                "field_name": "Speed 4 Energy Input Ratio Function of Air Flow Fraction Curve Name",
                "field_type": "a"
            },
            "speed_4_energy_input_ratio_function_of_water_flow_fraction_curve_name": {
                "field_name": "Speed 4 Energy Input Ratio Function of Water Flow Fraction Curve Name",
                "field_type": "a"
            },
            "speed_4_reference_unit_waste_heat_fraction_of_input_power_at_rated_conditions": {
                "field_name": "Speed 4 Reference Unit Waste Heat Fraction of Input Power At Rated Conditions",
                "field_type": "n"
            },
            "speed_4_waste_heat_function_of_temperature_curve_name": {
                "field_name": "Speed 4 Waste Heat Function of Temperature Curve Name",
                "field_type": "a"
            },
            "speed_5_reference_unit_gross_rated_heating_capacity": {
                "field_name": "Speed 5 Reference Unit Gross Rated Heating Capacity",
                "field_type": "n"
            },
            "speed_5_reference_unit_gross_rated_heating_cop": {
                "field_name": "Speed 5 Reference Unit Gross Rated Heating COP",
                "field_type": "n"
            },
            "speed_5_reference_unit_rated_air_flow_rate": {
                "field_name": "Speed 5 Reference Unit Rated Air Flow Rate",
                "field_type": "n"
            },
            "speed_5_reference_unit_rated_water_flow_rate": {
                "field_name": "Speed 5 Reference Unit Rated Water Flow Rate",
                "field_type": "n"
            },
            "speed_5_heating_capacity_function_of_temperature_curve_name": {
                "field_name": "Speed 5 Heating Capacity Function of Temperature Curve Name",
                "field_type": "a"
            },
            "speed_5_total_heating_capacity_function_of_air_flow_fraction_curve_name": {
                "field_name": "Speed 5 Total  Heating Capacity Function of Air Flow Fraction Curve Name",
                "field_type": "a"
            },
            "speed_5_heating_capacity_function_of_water_flow_fraction_curve_name": {
                "field_name": "Speed 5 Heating Capacity Function of Water Flow Fraction Curve Name",
                "field_type": "a"
            },
            "speed_5_energy_input_ratio_function_of_temperature_curve_name": {
                "field_name": "Speed 5 Energy Input Ratio Function of Temperature Curve Name",
                "field_type": "a"
            },
            "speed_5_energy_input_ratio_function_of_air_flow_fraction_curve_name": {
                "field_name": "Speed 5 Energy Input Ratio Function of Air Flow Fraction Curve Name",
                "field_type": "a"
            },
            "speed_5_energy_input_ratio_function_of_water_flow_fraction_curve_name": {
                "field_name": "Speed 5 Energy Input Ratio Function of Water Flow Fraction Curve Name",
                "field_type": "a"
            },
            "speed_5_reference_unit_waste_heat_fraction_of_input_power_at_rated_conditions": {
                "field_name": "Speed 5 Reference Unit Waste Heat Fraction of Input Power At Rated Conditions",
                "field_type": "n"
            },
            "speed_5_waste_heat_function_of_temperature_curve_name": {
                "field_name": "Speed 5 Waste Heat Function of Temperature Curve Name",
                "field_type": "a"
            },
            "speed_6_reference_unit_gross_rated_heating_capacity": {
                "field_name": "Speed 6 Reference Unit Gross Rated Heating Capacity",
                "field_type": "n"
            },
            "speed_6_reference_unit_gross_rated_heating_cop": {
                "field_name": "Speed 6 Reference Unit Gross Rated Heating COP",
                "field_type": "n"
            },
            "speed_6_reference_unit_rated_air_flow_rate": {
                "field_name": "Speed 6 Reference Unit Rated Air Flow Rate",
                "field_type": "n"
            },
            "speed_6_reference_unit_rated_water_flow_rate": {
                "field_name": "Speed 6 Reference Unit Rated Water Flow Rate",
                "field_type": "n"
            },
            "speed_6_heating_capacity_function_of_temperature_curve_name": {
                "field_name": "Speed 6 Heating Capacity Function of Temperature Curve Name",
                "field_type": "a"
            },
            "speed_6_total_heating_capacity_function_of_air_flow_fraction_curve_name": {
                "field_name": "Speed 6 Total  Heating Capacity Function of Air Flow Fraction Curve Name",
                "field_type": "a"
            },
            "speed_6_heating_capacity_function_of_water_flow_fraction_curve_name": {
                "field_name": "Speed 6 Heating Capacity Function of Water Flow Fraction Curve Name",
                "field_type": "a"
            },
            "speed_6_energy_input_ratio_function_of_temperature_curve_name": {
                "field_name": "Speed 6 Energy Input Ratio Function of Temperature Curve Name",
                "field_type": "a"
            },
            "speed_6_energy_input_ratio_function_of_air_flow_fraction_curve_name": {
                "field_name": "Speed 6 Energy Input Ratio Function of Air Flow Fraction Curve Name",
                "field_type": "a"
            },
            "speed_6_energy_input_ratio_function_of_water_flow_fraction_curve_name": {
                "field_name": "Speed 6 Energy Input Ratio Function of Water Flow Fraction Curve Name",
                "field_type": "a"
            },
            "speed_6_reference_unit_waste_heat_fraction_of_input_power_at_rated_conditions": {
                "field_name": "Speed 6 Reference Unit Waste Heat Fraction of Input Power At Rated Conditions",
                "field_type": "n"
            },
            "speed_6_waste_heat_function_of_temperature_curve_name": {
                "field_name": "Speed 6 Waste Heat Function of Temperature Curve Name",
                "field_type": "a"
            },
            "speed_7_reference_unit_gross_rated_heating_capacity": {
                "field_name": "Speed 7 Reference Unit Gross Rated Heating Capacity",
                "field_type": "n"
            },
            "speed_7_reference_unit_gross_rated_heating_cop": {
                "field_name": "Speed 7 Reference Unit Gross Rated Heating COP",
                "field_type": "n"
            },
            "speed_7_reference_unit_rated_air_flow_rate": {
                "field_name": "Speed 7 Reference Unit Rated Air Flow Rate",
                "field_type": "n"
            },
            "speed_7_reference_unit_rated_water_flow_rate": {
                "field_name": "Speed 7 Reference Unit Rated Water Flow Rate",
                "field_type": "n"
            },
            "speed_7_heating_capacity_function_of_temperature_curve_name": {
                "field_name": "Speed 7 Heating Capacity Function of Temperature Curve Name",
                "field_type": "a"
            },
            "speed_7_total_heating_capacity_function_of_air_flow_fraction_curve_name": {
                "field_name": "Speed 7 Total  Heating Capacity Function of Air Flow Fraction Curve Name",
                "field_type": "a"
            },
            "speed_7_heating_capacity_function_of_water_flow_fraction_curve_name": {
                "field_name": "Speed 7 Heating Capacity Function of Water Flow Fraction Curve Name",
                "field_type": "a"
            },
            "speed_7_energy_input_ratio_function_of_temperature_curve_name": {
                "field_name": "Speed 7 Energy Input Ratio Function of Temperature Curve Name",
                "field_type": "a"
            },
            "speed_7_energy_input_ratio_function_of_air_flow_fraction_curve_name": {
                "field_name": "Speed 7 Energy Input Ratio Function of Air Flow Fraction Curve Name",
                "field_type": "a"
            },
            "speed_7_energy_input_ratio_function_of_water_flow_fraction_curve_name": {
                "field_name": "Speed 7 Energy Input Ratio Function of Water Flow Fraction Curve Name",
                "field_type": "a"
            },
            "speed_7_reference_unit_waste_heat_fraction_of_input_power_at_rated_conditions": {
                "field_name": "Speed 7 Reference Unit Waste Heat Fraction of Input Power At Rated Conditions",
                "field_type": "n"
            },
            "speed_7_waste_heat_function_of_temperature_curve_name": {
                "field_name": "Speed 7 Waste Heat Function of Temperature Curve Name",
                "field_type": "a"
            },
            "speed_8_reference_unit_gross_rated_heating_capacity": {
                "field_name": "Speed 8 Reference Unit Gross Rated Heating Capacity",
                "field_type": "n"
            },
            "speed_8_reference_unit_gross_rated_heating_cop": {
                "field_name": "Speed 8 Reference Unit Gross Rated Heating COP",
                "field_type": "n"
            },
            "speed_8_reference_unit_rated_air_flow_rate": {
                "field_name": "Speed 8 Reference Unit Rated Air Flow Rate",
                "field_type": "n"
            },
            "speed_8_reference_unit_rated_water_flow_rate": {
                "field_name": "Speed 8 Reference Unit Rated Water Flow Rate",
                "field_type": "n"
            },
            "speed_8_heating_capacity_function_of_temperature_curve_name": {
                "field_name": "Speed 8 Heating Capacity Function of Temperature Curve Name",
                "field_type": "a"
            },
            "speed_8_total_heating_capacity_function_of_air_flow_fraction_curve_name": {
                "field_name": "Speed 8 Total  Heating Capacity Function of Air Flow Fraction Curve Name",
                "field_type": "a"
            },
            "speed_8_heating_capacity_function_of_water_flow_fraction_curve_name": {
                "field_name": "Speed 8 Heating Capacity Function of Water Flow Fraction Curve Name",
                "field_type": "a"
            },
            "speed_8_energy_input_ratio_function_of_temperature_curve_name": {
                "field_name": "Speed 8 Energy Input Ratio Function of Temperature Curve Name",
                "field_type": "a"
            },
            "speed_8_energy_input_ratio_function_of_air_flow_fraction_curve_name": {
                "field_name": "Speed 8 Energy Input Ratio Function of Air Flow Fraction Curve Name",
                "field_type": "a"
            },
            "speed_8_energy_input_ratio_function_of_water_flow_fraction_curve_name": {
                "field_name": "Speed 8 Energy Input Ratio Function of Water Flow Fraction Curve Name",
                "field_type": "a"
            },
            "speed_8_reference_unit_waste_heat_fraction_of_input_power_at_rated_conditions": {
                "field_name": "Speed 8 Reference Unit Waste Heat Fraction of Input Power At Rated Conditions",
                "field_type": "n"
            },
            "speed_8_waste_heat_function_of_temperature_curve_name": {
                "field_name": "Speed 8 Waste Heat Function of Temperature Curve Name",
                "field_type": "a"
            },
            "speed_9_reference_unit_gross_rated_heating_capacity": {
                "field_name": "Speed 9 Reference Unit Gross Rated Heating Capacity",
                "field_type": "n"
            },
            "speed_9_reference_unit_gross_rated_heating_cop": {
                "field_name": "Speed 9 Reference Unit Gross Rated Heating COP",
                "field_type": "n"
            },
            "speed_9_reference_unit_rated_air_flow_rate": {
                "field_name": "Speed 9 Reference Unit Rated Air Flow Rate",
                "field_type": "n"
            },
            "speed_9_reference_unit_rated_water_flow_rate": {
                "field_name": "Speed 9 Reference Unit Rated Water Flow Rate",
                "field_type": "n"
            },
            "speed_9_heating_capacity_function_of_temperature_curve_name": {
                "field_name": "Speed 9 Heating Capacity Function of Temperature Curve Name",
                "field_type": "a"
            },
            "speed_9_total_heating_capacity_function_of_air_flow_fraction_curve_name": {
                "field_name": "Speed 9 Total  Heating Capacity Function of Air Flow Fraction Curve Name",
                "field_type": "a"
            },
            "speed_9_heating_capacity_function_of_water_flow_fraction_curve_name": {
                "field_name": "Speed 9 Heating Capacity Function of Water Flow Fraction Curve Name",
                "field_type": "a"
            },
            "speed_9_energy_input_ratio_function_of_temperature_curve_name": {
                "field_name": "Speed 9 Energy Input Ratio Function of Temperature Curve Name",
                "field_type": "a"
            },
            "speed_9_energy_input_ratio_function_of_air_flow_fraction_curve_name": {
                "field_name": "Speed 9 Energy Input Ratio Function of Air Flow Fraction Curve Name",
                "field_type": "a"
            },
            "speed_9_energy_input_ratio_function_of_water_flow_fraction_curve_name": {
                "field_name": "Speed 9 Energy Input Ratio Function of Water Flow Fraction Curve Name",
                "field_type": "a"
            },
            "speed_9_reference_unit_waste_heat_fraction_of_input_power_at_rated_conditions": {
                "field_name": "Speed 9 Reference Unit Waste Heat Fraction of Input Power At Rated Conditions",
                "field_type": "n"
            },
            "speed_9_waste_heat_function_of_temperature_curve_name": {
                "field_name": "Speed 9 Waste Heat Function of Temperature Curve Name",
                "field_type": "a"
            },
            "speed_10_reference_unit_gross_rated_heating_capacity": {
                "field_name": "Speed 10 Reference Unit Gross Rated Heating Capacity",
                "field_type": "n"
            },
            "speed_10_reference_unit_gross_rated_heating_cop": {
                "field_name": "Speed 10 Reference Unit Gross Rated Heating COP",
                "field_type": "n"
            },
            "speed_10_reference_unit_rated_air_flow_rate": {
                "field_name": "Speed 10 Reference Unit Rated Air Flow Rate",
                "field_type": "n"
            },
            "speed_10_reference_unit_rated_water_flow_rate": {
                "field_name": "Speed 10 Reference Unit Rated Water Flow Rate",
                "field_type": "n"
            },
            "speed_10_heating_capacity_function_of_temperature_curve_name": {
                "field_name": "Speed 10 Heating Capacity Function of Temperature Curve Name",
                "field_type": "a"
            },
            "speed_10_total_heating_capacity_function_of_air_flow_fraction_curve_name": {
                "field_name": "Speed 10 Total  Heating Capacity Function of Air Flow Fraction Curve Name",
                "field_type": "a"
            },
            "speed_10_heating_capacity_function_of_water_flow_fraction_curve_name": {
                "field_name": "Speed 10 Heating Capacity Function of Water Flow Fraction Curve Name",
                "field_type": "a"
            },
            "speed_10_energy_input_ratio_function_of_temperature_curve_name": {
                "field_name": "Speed 10 Energy Input Ratio Function of Temperature Curve Name",
                "field_type": "a"
            },
            "speed_10_energy_input_ratio_function_of_air_flow_fraction_curve_name": {
                "field_name": "Speed 10 Energy Input Ratio Function of Air Flow Fraction Curve Name",
                "field_type": "a"
            },
            "speed_10_energy_input_ratio_function_of_water_flow_fraction_curve_name": {
                "field_name": "Speed 10 Energy Input Ratio Function of Water Flow Fraction Curve Name",
                "field_type": "a"
            },
            "speed_10_reference_unit_waste_heat_fraction_of_input_power_at_rated_conditions": {
                "field_name": "Speed 10 Reference Unit Waste Heat Fraction of Input Power At Rated Conditions",
                "field_type": "n"
            },
            "speed_10_waste_heat_function_of_temperature_curve_name": {
                "field_name": "Speed 10 Waste Heat Function of Temperature Curve Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "water_to_refrigerant_hx_water_inlet_node_name",
            "water_to_refrigerant_hx_water_outlet_node_name",
            "indoor_air_inlet_node_name",
            "indoor_air_outlet_node_name",
            "number_of_speeds",
            "nominal_speed_level",
            "rated_heating_capacity_at_selected_nominal_speed_level",
            "rated_air_flow_rate_at_selected_nominal_speed_level",
            "rated_water_flow_rate_at_selected_nominal_speed_level",
            "energy_part_load_fraction_curve_name",
            "speed_1_reference_unit_gross_rated_heating_capacity",
            "speed_1_reference_unit_gross_rated_heating_cop",
            "speed_1_reference_unit_rated_air_flow",
            "speed_1_reference_unit_rated_water_flow_rate",
            "speed_1_heating_capacity_function_of_temperature_curve_name",
            "speed_1_total_heating_capacity_function_of_air_flow_fraction_curve_name",
            "speed_1_heating_capacity_function_of_water_flow_fraction_curve_name",
            "speed_1_energy_input_ratio_function_of_temperature_curve_name",
            "speed_1_energy_input_ratio_function_of_air_flow_fraction_curve_name",
            "speed_1_energy_input_ratio_function_of_water_flow_fraction_curve_name",
            "speed_1_reference_unit_waste_heat_fraction_of_input_power_at_rated_conditions",
            "speed_1_waste_heat_function_of_temperature_curve_name",
            "speed_2_reference_unit_gross_rated_heating_capacity",
            "speed_2_reference_unit_gross_rated_heating_cop",
            "speed_2_reference_unit_rated_air_flow_rate",
            "speed_2_reference_unit_rated_water_flow_rate",
            "speed_2_heating_capacity_function_of_temperature_curve_name",
            "speed_2_total_heating_capacity_function_of_air_flow_fraction_curve_name",
            "speed_2_heating_capacity_function_of_water_flow_fraction_curve_name",
            "speed_2_energy_input_ratio_function_of_temperature_curve_name",
            "speed_2_energy_input_ratio_function_of_air_flow_fraction_curve_name",
            "speed_2_energy_input_ratio_function_of_water_flow_fraction_curve_name",
            "speed_2_reference_unit_waste_heat_fraction_of_input_power_at_rated_conditions",
            "speed_2_waste_heat_function_of_temperature_curve_name",
            "speed_3_reference_unit_gross_rated_heating_capacity",
            "speed_3_reference_unit_gross_rated_heating_cop",
            "speed_3_reference_unit_rated_air_flow_rate",
            "speed_3_reference_unit_rated_water_flow_rate",
            "speed_3_heating_capacity_function_of_temperature_curve_name",
            "speed_3_total_heating_capacity_function_of_air_flow_fraction_curve_name",
            "speed_3_heating_capacity_function_of_water_flow_fraction_curve_name",
            "speed_3_energy_input_ratio_function_of_temperature_curve_name",
            "speed_3_energy_input_ratio_function_of_air_flow_fraction_curve_name",
            "speed_3_energy_input_ratio_function_of_water_flow_fraction_curve_name",
            "speed_3_reference_unit_waste_heat_fraction_of_input_power_at_rated_conditions",
            "speed_3_waste_heat_function_of_temperature_curve_name",
            "speed_4_reference_unit_gross_rated_heating_capacity",
            "speed_4_reference_unit_gross_rated_heating_cop",
            "speed_4_reference_unit_rated_air_flow_rate",
            "speed_4_reference_unit_rated_water_flow_rate",
            "speed_4_heating_capacity_function_of_temperature_curve_name",
            "speed_4_total_heating_capacity_function_of_air_flow_fraction_curve_name",
            "speed_4_heating_capacity_function_of_water_flow_fraction_curve_name",
            "speed_4_energy_input_ratio_function_of_temperature_curve_name",
            "speed_4_energy_input_ratio_function_of_air_flow_fraction_curve_name",
            "speed_4_energy_input_ratio_function_of_water_flow_fraction_curve_name",
            "speed_4_reference_unit_waste_heat_fraction_of_input_power_at_rated_conditions",
            "speed_4_waste_heat_function_of_temperature_curve_name",
            "speed_5_reference_unit_gross_rated_heating_capacity",
            "speed_5_reference_unit_gross_rated_heating_cop",
            "speed_5_reference_unit_rated_air_flow_rate",
            "speed_5_reference_unit_rated_water_flow_rate",
            "speed_5_heating_capacity_function_of_temperature_curve_name",
            "speed_5_total_heating_capacity_function_of_air_flow_fraction_curve_name",
            "speed_5_heating_capacity_function_of_water_flow_fraction_curve_name",
            "speed_5_energy_input_ratio_function_of_temperature_curve_name",
            "speed_5_energy_input_ratio_function_of_air_flow_fraction_curve_name",
            "speed_5_energy_input_ratio_function_of_water_flow_fraction_curve_name",
            "speed_5_reference_unit_waste_heat_fraction_of_input_power_at_rated_conditions",
            "speed_5_waste_heat_function_of_temperature_curve_name",
            "speed_6_reference_unit_gross_rated_heating_capacity",
            "speed_6_reference_unit_gross_rated_heating_cop",
            "speed_6_reference_unit_rated_air_flow_rate",
            "speed_6_reference_unit_rated_water_flow_rate",
            "speed_6_heating_capacity_function_of_temperature_curve_name",
            "speed_6_total_heating_capacity_function_of_air_flow_fraction_curve_name",
            "speed_6_heating_capacity_function_of_water_flow_fraction_curve_name",
            "speed_6_energy_input_ratio_function_of_temperature_curve_name",
            "speed_6_energy_input_ratio_function_of_air_flow_fraction_curve_name",
            "speed_6_energy_input_ratio_function_of_water_flow_fraction_curve_name",
            "speed_6_reference_unit_waste_heat_fraction_of_input_power_at_rated_conditions",
            "speed_6_waste_heat_function_of_temperature_curve_name",
            "speed_7_reference_unit_gross_rated_heating_capacity",
            "speed_7_reference_unit_gross_rated_heating_cop",
            "speed_7_reference_unit_rated_air_flow_rate",
            "speed_7_reference_unit_rated_water_flow_rate",
            "speed_7_heating_capacity_function_of_temperature_curve_name",
            "speed_7_total_heating_capacity_function_of_air_flow_fraction_curve_name",
            "speed_7_heating_capacity_function_of_water_flow_fraction_curve_name",
            "speed_7_energy_input_ratio_function_of_temperature_curve_name",
            "speed_7_energy_input_ratio_function_of_air_flow_fraction_curve_name",
            "speed_7_energy_input_ratio_function_of_water_flow_fraction_curve_name",
            "speed_7_reference_unit_waste_heat_fraction_of_input_power_at_rated_conditions",
            "speed_7_waste_heat_function_of_temperature_curve_name",
            "speed_8_reference_unit_gross_rated_heating_capacity",
            "speed_8_reference_unit_gross_rated_heating_cop",
            "speed_8_reference_unit_rated_air_flow_rate",
            "speed_8_reference_unit_rated_water_flow_rate",
            "speed_8_heating_capacity_function_of_temperature_curve_name",
            "speed_8_total_heating_capacity_function_of_air_flow_fraction_curve_name",
            "speed_8_heating_capacity_function_of_water_flow_fraction_curve_name",
            "speed_8_energy_input_ratio_function_of_temperature_curve_name",
            "speed_8_energy_input_ratio_function_of_air_flow_fraction_curve_name",
            "speed_8_energy_input_ratio_function_of_water_flow_fraction_curve_name",
            "speed_8_reference_unit_waste_heat_fraction_of_input_power_at_rated_conditions",
            "speed_8_waste_heat_function_of_temperature_curve_name",
            "speed_9_reference_unit_gross_rated_heating_capacity",
            "speed_9_reference_unit_gross_rated_heating_cop",
            "speed_9_reference_unit_rated_air_flow_rate",
            "speed_9_reference_unit_rated_water_flow_rate",
            "speed_9_heating_capacity_function_of_temperature_curve_name",
            "speed_9_total_heating_capacity_function_of_air_flow_fraction_curve_name",
            "speed_9_heating_capacity_function_of_water_flow_fraction_curve_name",
            "speed_9_energy_input_ratio_function_of_temperature_curve_name",
            "speed_9_energy_input_ratio_function_of_air_flow_fraction_curve_name",
            "speed_9_energy_input_ratio_function_of_water_flow_fraction_curve_name",
            "speed_9_reference_unit_waste_heat_fraction_of_input_power_at_rated_conditions",
            "speed_9_waste_heat_function_of_temperature_curve_name",
            "speed_10_reference_unit_gross_rated_heating_capacity",
            "speed_10_reference_unit_gross_rated_heating_cop",
            "speed_10_reference_unit_rated_air_flow_rate",
            "speed_10_reference_unit_rated_water_flow_rate",
            "speed_10_heating_capacity_function_of_temperature_curve_name",
            "speed_10_total_heating_capacity_function_of_air_flow_fraction_curve_name",
            "speed_10_heating_capacity_function_of_water_flow_fraction_curve_name",
            "speed_10_energy_input_ratio_function_of_temperature_curve_name",
            "speed_10_energy_input_ratio_function_of_air_flow_fraction_curve_name",
            "speed_10_energy_input_ratio_function_of_water_flow_fraction_curve_name",
            "speed_10_reference_unit_waste_heat_fraction_of_input_power_at_rated_conditions",
            "speed_10_waste_heat_function_of_temperature_curve_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "water_to_refrigerant_hx_water_inlet_node_name",
                "water_to_refrigerant_hx_water_outlet_node_name",
                "indoor_air_inlet_node_name",
                "indoor_air_outlet_node_name",
                "energy_part_load_fraction_curve_name",
                "speed_1_heating_capacity_function_of_temperature_curve_name",
                "speed_1_total_heating_capacity_function_of_air_flow_fraction_curve_name",
                "speed_1_heating_capacity_function_of_water_flow_fraction_curve_name",
                "speed_1_energy_input_ratio_function_of_temperature_curve_name",
                "speed_1_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                "speed_1_energy_input_ratio_function_of_water_flow_fraction_curve_name",
                "speed_1_waste_heat_function_of_temperature_curve_name",
                "speed_2_heating_capacity_function_of_temperature_curve_name",
                "speed_2_total_heating_capacity_function_of_air_flow_fraction_curve_name",
                "speed_2_heating_capacity_function_of_water_flow_fraction_curve_name",
                "speed_2_energy_input_ratio_function_of_temperature_curve_name",
                "speed_2_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                "speed_2_energy_input_ratio_function_of_water_flow_fraction_curve_name",
                "speed_2_waste_heat_function_of_temperature_curve_name",
                "speed_3_heating_capacity_function_of_temperature_curve_name",
                "speed_3_total_heating_capacity_function_of_air_flow_fraction_curve_name",
                "speed_3_heating_capacity_function_of_water_flow_fraction_curve_name",
                "speed_3_energy_input_ratio_function_of_temperature_curve_name",
                "speed_3_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                "speed_3_energy_input_ratio_function_of_water_flow_fraction_curve_name",
                "speed_3_waste_heat_function_of_temperature_curve_name",
                "speed_4_heating_capacity_function_of_temperature_curve_name",
                "speed_4_total_heating_capacity_function_of_air_flow_fraction_curve_name",
                "speed_4_heating_capacity_function_of_water_flow_fraction_curve_name",
                "speed_4_energy_input_ratio_function_of_temperature_curve_name",
                "speed_4_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                "speed_4_energy_input_ratio_function_of_water_flow_fraction_curve_name",
                "speed_4_waste_heat_function_of_temperature_curve_name",
                "speed_5_heating_capacity_function_of_temperature_curve_name",
                "speed_5_total_heating_capacity_function_of_air_flow_fraction_curve_name",
                "speed_5_heating_capacity_function_of_water_flow_fraction_curve_name",
                "speed_5_energy_input_ratio_function_of_temperature_curve_name",
                "speed_5_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                "speed_5_energy_input_ratio_function_of_water_flow_fraction_curve_name",
                "speed_5_waste_heat_function_of_temperature_curve_name",
                "speed_6_heating_capacity_function_of_temperature_curve_name",
                "speed_6_total_heating_capacity_function_of_air_flow_fraction_curve_name",
                "speed_6_heating_capacity_function_of_water_flow_fraction_curve_name",
                "speed_6_energy_input_ratio_function_of_temperature_curve_name",
                "speed_6_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                "speed_6_energy_input_ratio_function_of_water_flow_fraction_curve_name",
                "speed_6_waste_heat_function_of_temperature_curve_name",
                "speed_7_heating_capacity_function_of_temperature_curve_name",
                "speed_7_total_heating_capacity_function_of_air_flow_fraction_curve_name",
                "speed_7_heating_capacity_function_of_water_flow_fraction_curve_name",
                "speed_7_energy_input_ratio_function_of_temperature_curve_name",
                "speed_7_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                "speed_7_energy_input_ratio_function_of_water_flow_fraction_curve_name",
                "speed_7_waste_heat_function_of_temperature_curve_name",
                "speed_8_heating_capacity_function_of_temperature_curve_name",
                "speed_8_total_heating_capacity_function_of_air_flow_fraction_curve_name",
                "speed_8_heating_capacity_function_of_water_flow_fraction_curve_name",
                "speed_8_energy_input_ratio_function_of_temperature_curve_name",
                "speed_8_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                "speed_8_energy_input_ratio_function_of_water_flow_fraction_curve_name",
                "speed_8_waste_heat_function_of_temperature_curve_name",
                "speed_9_heating_capacity_function_of_temperature_curve_name",
                "speed_9_total_heating_capacity_function_of_air_flow_fraction_curve_name",
                "speed_9_heating_capacity_function_of_water_flow_fraction_curve_name",
                "speed_9_energy_input_ratio_function_of_temperature_curve_name",
                "speed_9_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                "speed_9_energy_input_ratio_function_of_water_flow_fraction_curve_name",
                "speed_9_waste_heat_function_of_temperature_curve_name",
                "speed_10_heating_capacity_function_of_temperature_curve_name",
                "speed_10_total_heating_capacity_function_of_air_flow_fraction_curve_name",
                "speed_10_heating_capacity_function_of_water_flow_fraction_curve_name",
                "speed_10_energy_input_ratio_function_of_temperature_curve_name",
                "speed_10_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                "speed_10_energy_input_ratio_function_of_water_flow_fraction_curve_name",
                "speed_10_waste_heat_function_of_temperature_curve_name"
            ]
        },
        "numerics": {
            "fields": [
                "number_of_speeds",
                "nominal_speed_level",
                "rated_heating_capacity_at_selected_nominal_speed_level",
                "rated_air_flow_rate_at_selected_nominal_speed_level",
                "rated_water_flow_rate_at_selected_nominal_speed_level",
                "speed_1_reference_unit_gross_rated_heating_capacity",
                "speed_1_reference_unit_gross_rated_heating_cop",
                "speed_1_reference_unit_rated_air_flow",
                "speed_1_reference_unit_rated_water_flow_rate",
                "speed_1_reference_unit_waste_heat_fraction_of_input_power_at_rated_conditions",
                "speed_2_reference_unit_gross_rated_heating_capacity",
                "speed_2_reference_unit_gross_rated_heating_cop",
                "speed_2_reference_unit_rated_air_flow_rate",
                "speed_2_reference_unit_rated_water_flow_rate",
                "speed_2_reference_unit_waste_heat_fraction_of_input_power_at_rated_conditions",
                "speed_3_reference_unit_gross_rated_heating_capacity",
                "speed_3_reference_unit_gross_rated_heating_cop",
                "speed_3_reference_unit_rated_air_flow_rate",
                "speed_3_reference_unit_rated_water_flow_rate",
                "speed_3_reference_unit_waste_heat_fraction_of_input_power_at_rated_conditions",
                "speed_4_reference_unit_gross_rated_heating_capacity",
                "speed_4_reference_unit_gross_rated_heating_cop",
                "speed_4_reference_unit_rated_air_flow_rate",
                "speed_4_reference_unit_rated_water_flow_rate",
                "speed_4_reference_unit_waste_heat_fraction_of_input_power_at_rated_conditions",
                "speed_5_reference_unit_gross_rated_heating_capacity",
                "speed_5_reference_unit_gross_rated_heating_cop",
                "speed_5_reference_unit_rated_air_flow_rate",
                "speed_5_reference_unit_rated_water_flow_rate",
                "speed_5_reference_unit_waste_heat_fraction_of_input_power_at_rated_conditions",
                "speed_6_reference_unit_gross_rated_heating_capacity",
                "speed_6_reference_unit_gross_rated_heating_cop",
                "speed_6_reference_unit_rated_air_flow_rate",
                "speed_6_reference_unit_rated_water_flow_rate",
                "speed_6_reference_unit_waste_heat_fraction_of_input_power_at_rated_conditions",
                "speed_7_reference_unit_gross_rated_heating_capacity",
                "speed_7_reference_unit_gross_rated_heating_cop",
                "speed_7_reference_unit_rated_air_flow_rate",
                "speed_7_reference_unit_rated_water_flow_rate",
                "speed_7_reference_unit_waste_heat_fraction_of_input_power_at_rated_conditions",
                "speed_8_reference_unit_gross_rated_heating_capacity",
                "speed_8_reference_unit_gross_rated_heating_cop",
                "speed_8_reference_unit_rated_air_flow_rate",
                "speed_8_reference_unit_rated_water_flow_rate",
                "speed_8_reference_unit_waste_heat_fraction_of_input_power_at_rated_conditions",
                "speed_9_reference_unit_gross_rated_heating_capacity",
                "speed_9_reference_unit_gross_rated_heating_cop",
                "speed_9_reference_unit_rated_air_flow_rate",
                "speed_9_reference_unit_rated_water_flow_rate",
                "speed_9_reference_unit_waste_heat_fraction_of_input_power_at_rated_conditions",
                "speed_10_reference_unit_gross_rated_heating_capacity",
                "speed_10_reference_unit_gross_rated_heating_cop",
                "speed_10_reference_unit_rated_air_flow_rate",
                "speed_10_reference_unit_rated_water_flow_rate",
                "speed_10_reference_unit_waste_heat_fraction_of_input_power_at_rated_conditions"
            ]
        }
    },
    "type": "object",
    "memo": "Direct expansion (DX) heating coil for water-to-air heat pump (includes electric compressor), variable-speed, equation-fit model. Equation-fit model uses normalized curves to describe the heat pump performance. Requires two to ten sets of performance data and will interpolate between speeds.",
    "min_fields": 23.0
}
```
