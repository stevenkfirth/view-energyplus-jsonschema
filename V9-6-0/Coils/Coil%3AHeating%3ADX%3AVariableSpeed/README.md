```
{
    "Coil:Heating:DX:VariableSpeed": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
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
                    "energy_part_load_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "quadratic curve = a + b*PLR + c*PLR**2 cubic curve = a + b*PLR + c*PLR**2 + d*PLR**3 PLR = part load ratio (heating load/steady state capacity)"
                    },
                    "defrost_energy_input_ratio_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "biquadratic curve = a + b*wb + c*wb**2 + d*oat + e*oat**2 + f*wb*oat wb = wet-bulb temperature (C) of air entering the indoor coil oat = outdoor air dry-bulb temperature (C) only required if ReverseCycle defrost strategy is specified"
                    },
                    "minimum_outdoor_dry_bulb_temperature_for_compressor_operation": {
                        "type": "number",
                        "default": -8.0,
                        "units": "C"
                    },
                    "outdoor_dry_bulb_temperature_to_turn_on_compressor": {
                        "type": "number",
                        "units": "C",
                        "note": "The outdoor temperature when the compressor is automatically turned back on following an automatic shut off because of low outdoor dry-bulb temperature. This field is only used for the calculation of HSPF. If this field is not provided, then outdoor bin temperature used in the HSPF calculation is always considered to be greater than this temperature and 'Minimum Outdoor Dry-Bulb Temperature for Compressor Operation' field described above. This assumption is based on AHRI standard 210/240 (2008) and can introduce significant error in the final value of HSPF."
                    },
                    "maximum_outdoor_dry_bulb_temperature_for_defrost_operation": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 7.22,
                        "default": 5.0,
                        "units": "C"
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
                    "defrost_strategy": {
                        "type": "string",
                        "enum": [
                            "",
                            "Resistive",
                            "ReverseCycle"
                        ],
                        "default": "ReverseCycle"
                    },
                    "defrost_control": {
                        "type": "string",
                        "enum": [
                            "",
                            "OnDemand",
                            "Timed"
                        ],
                        "default": "Timed"
                    },
                    "defrost_time_period_fraction": {
                        "type": "number",
                        "minimum": 0.0,
                        "default": 0.058333,
                        "note": "Fraction of time in defrost mode only applicable if timed defrost control is specified"
                    },
                    "resistive_defrost_heater_capacity": {
                        "default": 0.0,
                        "units": "W",
                        "note": "only applicable if resistive defrost strategy is specified",
                        "ip-units": "W",
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
                    "speed_1_reference_unit_rated_air_flow_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "minimum": 0.0
                    },
                    "speed_1_heating_capacity_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "curve = a + b*db + c*db**2 + d*oat + e*oat**2 + f*db*oat db = entering air dry-bulb temperature (C) oat = air entering temperature seen by the evaporator (C)"
                    },
                    "speed_1_total_heating_capacity_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
                    },
                    "speed_1_energy_input_ratio_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "curve = a + b*db + c*db**2 + d*oat + e*oat**2 + f*db*oat db = entering air dry-bulb temperature (C) oat = air entering temperature seen by the evaporator (C)"
                    },
                    "speed_1_energy_input_ratio_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
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
                    "speed_2_heating_capacity_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "curve = a + b*db + c*db**2 + d*oat + e*oat**2 + f*db*oat db = entering air dry-bulb temperature (C) oat = air entering temperature seen by the evaporator (C)"
                    },
                    "speed_2_total_heating_capacity_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
                    },
                    "speed_2_energy_input_ratio_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "curve = a + b*db + c*db**2 + d*oat + e*oat**2 + f*db*oat db = entering air dry-bulb temperature (C) oat = air entering temperature seen by the evaporator (C)"
                    },
                    "speed_2_energy_input_ratio_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
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
                    "speed_3_heating_capacity_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions",
                            "UnivariateFunctions"
                        ],
                        "note": "curve = a + b*db + c*db**2 + d*oat + e*oat**2 + f*db*oat db = entering air dry-bulb temperature (C) oat = air entering temperature seen by the evaporator (C)"
                    },
                    "speed_3_total_heating_capacity_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
                    },
                    "speed_3_energy_input_ratio_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "curve = a + b*db + c*db**2 + d*oat + e*oat**2 + f*db*oat db = entering air dry-bulb temperature (C) oat = air entering temperature seen by the evaporator (C)"
                    },
                    "speed_3_energy_input_ratio_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
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
                    "speed_4_heating_capacity_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "curve = a + b*db + c*db**2 + d*oat + e*oat**2 + f*db*oat db = entering air dry-bulb temperature (C) oat = air entering temperature seen by the evaporator (C)"
                    },
                    "speed_4_heating_capacity_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
                    },
                    "speed_4_energy_input_ratio_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "curve = a + b*db + c*db**2 + d*oat + e*oat**2 + f*db*oat db = entering air dry-bulb temperature (C) oat = air entering temperature seen by the evaporator (C)"
                    },
                    "speed_4_energy_input_ratio_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
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
                    "speed_5_heating_capacity_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "curve = a + b*db + c*db**2 + d*oat + e*oat**2 + f*db*oat db = entering air dry-bulb temperature (C) oat = air entering temperature seen by the evaporator (C)"
                    },
                    "speed_5_heating_capacity_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
                    },
                    "speed_5_energy_input_ratio_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "curve = a + b*db + c*db**2 + d*oat + e*oat**2 + f*db*oat db = entering air dry-bulb temperature (C) oat = air entering temperature seen by the evaporator (C)"
                    },
                    "speed_5_energy_input_ratio_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
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
                    "speed_6_heating_capacity_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "curve = a + b*db + c*db**2 + d*oat + e*oat**2 + f*db*oat db = entering air dry-bulb temperature (C) oat = air entering temperature seen by the evaporator (C)"
                    },
                    "speed_6_heating_capacity_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
                    },
                    "speed_6_energy_input_ratio_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "curve = a + b*db + c*db**2 + d*oat + e*oat**2 + f*db*oat db = entering air dry-bulb temperature (C) oat = air entering temperature seen by the evaporator (C)"
                    },
                    "speed_6_energy_input_ratio_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
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
                    "speed_7_heating_capacity_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "curve = a + b*db + c*db**2 + d*oat + e*oat**2 + f*db*oat db = entering air dry-bulb temperature (C) oat = air entering temperature seen by the evaporator (C)"
                    },
                    "speed_7_heating_capacity_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
                    },
                    "speed_7_energy_input_ratio_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "curve = a + b*db + c*db**2 + d*oat + e*oat**2 + f*db*oat db = entering air dry-bulb temperature (C) oat = air entering temperature seen by the evaporator (C)"
                    },
                    "speed_7_energy_input_ratio_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
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
                    "speed_8_heating_capacity_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "curve = a + b*db + c*db**2 + d*oat + e*oat**2 + f*db*oat db = entering air dry-bulb temperature (C) oat = air entering temperature seen by the evaporator (C)"
                    },
                    "speed_8_heating_capacity_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
                    },
                    "speed_8_energy_input_ratio_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "curve = a + b*db + c*db**2 + d*oat + e*oat**2 + f*db*oat db = entering air dry-bulb temperature (C) oat = air entering temperature seen by the evaporator (C)"
                    },
                    "speed_8_energy_input_ratio_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
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
                    "speed_9_heating_capacity_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "curve = a + b*db + c*db**2 + d*oat + e*oat**2 + f*db*oat db = entering air dry-bulb temperature (C) oat = air entering temperature seen by the evaporator (C)"
                    },
                    "speed_9_heating_capacity_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
                    },
                    "speed_9_energy_input_ratio_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "curve = a + b*db + c*db**2 + d*oat + e*oat**2 + f*db*oat db = entering air dry-bulb temperature (C) oat = air entering temperature seen by the evaporator (C)"
                    },
                    "speed_9_energy_input_ratio_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
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
                    "speed_10_heating_capacity_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "curve = a + b*db + c*db**2 + d*oat + e*oat**2 + f*db*oat db = entering air dry-bulb temperature (C) oat = air entering temperature seen by the evaporator (C)"
                    },
                    "speed_10_heating_capacity_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
                    },
                    "speed_10_energy_input_ratio_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "curve = a + b*db + c*db**2 + d*oat + e*oat**2 + f*db*oat db = entering air dry-bulb temperature (C) oat = air entering temperature seen by the evaporator (C)"
                    },
                    "speed_10_energy_input_ratio_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
                    }
                },
                "required": [
                    "indoor_air_inlet_node_name",
                    "indoor_air_outlet_node_name",
                    "energy_part_load_fraction_curve_name",
                    "speed_1_reference_unit_gross_rated_heating_capacity",
                    "speed_1_reference_unit_gross_rated_heating_cop",
                    "speed_1_reference_unit_rated_air_flow_rate",
                    "speed_1_heating_capacity_function_of_temperature_curve_name",
                    "speed_1_total_heating_capacity_function_of_air_flow_fraction_curve_name",
                    "speed_1_energy_input_ratio_function_of_temperature_curve_name",
                    "speed_1_energy_input_ratio_function_of_air_flow_fraction_curve_name"
                ]
            }
        },
        "group": "Coils",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "HeatingCoilsDXVariableSpeed"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
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
                "energy_part_load_fraction_curve_name": {
                    "field_name": "Energy Part Load Fraction Curve Name",
                    "field_type": "a"
                },
                "defrost_energy_input_ratio_function_of_temperature_curve_name": {
                    "field_name": "Defrost Energy Input Ratio Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "minimum_outdoor_dry_bulb_temperature_for_compressor_operation": {
                    "field_name": "Minimum Outdoor Dry-Bulb Temperature for Compressor Operation",
                    "field_type": "n"
                },
                "outdoor_dry_bulb_temperature_to_turn_on_compressor": {
                    "field_name": "Outdoor Dry-Bulb Temperature to Turn On Compressor",
                    "field_type": "n"
                },
                "maximum_outdoor_dry_bulb_temperature_for_defrost_operation": {
                    "field_name": "Maximum Outdoor Dry-Bulb Temperature for Defrost Operation",
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
                "defrost_strategy": {
                    "field_name": "Defrost Strategy",
                    "field_type": "a"
                },
                "defrost_control": {
                    "field_name": "Defrost Control",
                    "field_type": "a"
                },
                "defrost_time_period_fraction": {
                    "field_name": "Defrost Time Period Fraction",
                    "field_type": "n"
                },
                "resistive_defrost_heater_capacity": {
                    "field_name": "Resistive Defrost Heater Capacity",
                    "field_type": "n"
                },
                "speed_1_reference_unit_gross_rated_heating_capacity": {
                    "field_name": "Speed 1 Reference Unit Gross Rated Heating Capacity",
                    "field_type": "n"
                },
                "speed_1_reference_unit_gross_rated_heating_cop": {
                    "field_name": "Speed 1 Reference Unit Gross Rated Heating COP",
                    "field_type": "n"
                },
                "speed_1_reference_unit_rated_air_flow_rate": {
                    "field_name": "Speed 1 Reference Unit Rated Air Flow Rate",
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
                "speed_1_energy_input_ratio_function_of_temperature_curve_name": {
                    "field_name": "Speed 1 Energy Input Ratio Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_1_energy_input_ratio_function_of_air_flow_fraction_curve_name": {
                    "field_name": "Speed 1 Energy Input Ratio Function of Air Flow Fraction Curve Name",
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
                "speed_2_heating_capacity_function_of_temperature_curve_name": {
                    "field_name": "Speed 2 Heating Capacity Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_2_total_heating_capacity_function_of_air_flow_fraction_curve_name": {
                    "field_name": "Speed 2 Total  Heating Capacity Function of Air Flow Fraction Curve Name",
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
                "speed_3_heating_capacity_function_of_temperature_curve_name": {
                    "field_name": "Speed 3 Heating Capacity Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_3_total_heating_capacity_function_of_air_flow_fraction_curve_name": {
                    "field_name": "Speed 3 Total  Heating Capacity Function of Air Flow Fraction Curve Name",
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
                "speed_4_heating_capacity_function_of_temperature_curve_name": {
                    "field_name": "Speed 4 Heating Capacity Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_4_heating_capacity_function_of_air_flow_fraction_curve_name": {
                    "field_name": "Speed 4 Heating Capacity Function of Air Flow Fraction Curve Name",
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
                "speed_5_heating_capacity_function_of_temperature_curve_name": {
                    "field_name": "Speed 5 Heating Capacity Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_5_heating_capacity_function_of_air_flow_fraction_curve_name": {
                    "field_name": "Speed 5 Heating Capacity Function of Air Flow Fraction Curve Name",
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
                "speed_6_heating_capacity_function_of_temperature_curve_name": {
                    "field_name": "Speed 6 Heating Capacity Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_6_heating_capacity_function_of_air_flow_fraction_curve_name": {
                    "field_name": "Speed 6 Heating Capacity Function of Air Flow Fraction Curve Name",
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
                "speed_7_heating_capacity_function_of_temperature_curve_name": {
                    "field_name": "Speed 7 Heating Capacity Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_7_heating_capacity_function_of_air_flow_fraction_curve_name": {
                    "field_name": "Speed 7 Heating Capacity Function of Air Flow Fraction Curve Name",
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
                "speed_8_heating_capacity_function_of_temperature_curve_name": {
                    "field_name": "Speed 8 Heating Capacity Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_8_heating_capacity_function_of_air_flow_fraction_curve_name": {
                    "field_name": "Speed 8 Heating Capacity Function of Air Flow Fraction Curve Name",
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
                "speed_9_heating_capacity_function_of_temperature_curve_name": {
                    "field_name": "Speed 9 Heating Capacity Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_9_heating_capacity_function_of_air_flow_fraction_curve_name": {
                    "field_name": "Speed 9 Heating Capacity Function of Air Flow Fraction Curve Name",
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
                "speed_10_heating_capacity_function_of_temperature_curve_name": {
                    "field_name": "Speed 10 Heating Capacity Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_10_heating_capacity_function_of_air_flow_fraction_curve_name": {
                    "field_name": "Speed 10 Heating Capacity Function of Air Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "speed_10_energy_input_ratio_function_of_temperature_curve_name": {
                    "field_name": "Speed 10 Energy Input Ratio Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_10_energy_input_ratio_function_of_air_flow_fraction_curve_name": {
                    "field_name": "Speed 10 Energy Input Ratio Function of Air Flow Fraction Curve Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "indoor_air_inlet_node_name",
                "indoor_air_outlet_node_name",
                "number_of_speeds",
                "nominal_speed_level",
                "rated_heating_capacity_at_selected_nominal_speed_level",
                "rated_air_flow_rate_at_selected_nominal_speed_level",
                "energy_part_load_fraction_curve_name",
                "defrost_energy_input_ratio_function_of_temperature_curve_name",
                "minimum_outdoor_dry_bulb_temperature_for_compressor_operation",
                "outdoor_dry_bulb_temperature_to_turn_on_compressor",
                "maximum_outdoor_dry_bulb_temperature_for_defrost_operation",
                "crankcase_heater_capacity",
                "maximum_outdoor_dry_bulb_temperature_for_crankcase_heater_operation",
                "defrost_strategy",
                "defrost_control",
                "defrost_time_period_fraction",
                "resistive_defrost_heater_capacity",
                "speed_1_reference_unit_gross_rated_heating_capacity",
                "speed_1_reference_unit_gross_rated_heating_cop",
                "speed_1_reference_unit_rated_air_flow_rate",
                "speed_1_heating_capacity_function_of_temperature_curve_name",
                "speed_1_total_heating_capacity_function_of_air_flow_fraction_curve_name",
                "speed_1_energy_input_ratio_function_of_temperature_curve_name",
                "speed_1_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                "speed_2_reference_unit_gross_rated_heating_capacity",
                "speed_2_reference_unit_gross_rated_heating_cop",
                "speed_2_reference_unit_rated_air_flow_rate",
                "speed_2_heating_capacity_function_of_temperature_curve_name",
                "speed_2_total_heating_capacity_function_of_air_flow_fraction_curve_name",
                "speed_2_energy_input_ratio_function_of_temperature_curve_name",
                "speed_2_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                "speed_3_reference_unit_gross_rated_heating_capacity",
                "speed_3_reference_unit_gross_rated_heating_cop",
                "speed_3_reference_unit_rated_air_flow_rate",
                "speed_3_heating_capacity_function_of_temperature_curve_name",
                "speed_3_total_heating_capacity_function_of_air_flow_fraction_curve_name",
                "speed_3_energy_input_ratio_function_of_temperature_curve_name",
                "speed_3_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                "speed_4_reference_unit_gross_rated_heating_capacity",
                "speed_4_reference_unit_gross_rated_heating_cop",
                "speed_4_reference_unit_rated_air_flow_rate",
                "speed_4_heating_capacity_function_of_temperature_curve_name",
                "speed_4_heating_capacity_function_of_air_flow_fraction_curve_name",
                "speed_4_energy_input_ratio_function_of_temperature_curve_name",
                "speed_4_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                "speed_5_reference_unit_gross_rated_heating_capacity",
                "speed_5_reference_unit_gross_rated_heating_cop",
                "speed_5_reference_unit_rated_air_flow_rate",
                "speed_5_heating_capacity_function_of_temperature_curve_name",
                "speed_5_heating_capacity_function_of_air_flow_fraction_curve_name",
                "speed_5_energy_input_ratio_function_of_temperature_curve_name",
                "speed_5_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                "speed_6_reference_unit_gross_rated_heating_capacity",
                "speed_6_reference_unit_gross_rated_heating_cop",
                "speed_6_reference_unit_rated_air_flow_rate",
                "speed_6_heating_capacity_function_of_temperature_curve_name",
                "speed_6_heating_capacity_function_of_air_flow_fraction_curve_name",
                "speed_6_energy_input_ratio_function_of_temperature_curve_name",
                "speed_6_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                "speed_7_reference_unit_gross_rated_heating_capacity",
                "speed_7_reference_unit_gross_rated_heating_cop",
                "speed_7_reference_unit_rated_air_flow_rate",
                "speed_7_heating_capacity_function_of_temperature_curve_name",
                "speed_7_heating_capacity_function_of_air_flow_fraction_curve_name",
                "speed_7_energy_input_ratio_function_of_temperature_curve_name",
                "speed_7_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                "speed_8_reference_unit_gross_rated_heating_capacity",
                "speed_8_reference_unit_gross_rated_heating_cop",
                "speed_8_reference_unit_rated_air_flow_rate",
                "speed_8_heating_capacity_function_of_temperature_curve_name",
                "speed_8_heating_capacity_function_of_air_flow_fraction_curve_name",
                "speed_8_energy_input_ratio_function_of_temperature_curve_name",
                "speed_8_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                "speed_9_reference_unit_gross_rated_heating_capacity",
                "speed_9_reference_unit_gross_rated_heating_cop",
                "speed_9_reference_unit_rated_air_flow_rate",
                "speed_9_heating_capacity_function_of_temperature_curve_name",
                "speed_9_heating_capacity_function_of_air_flow_fraction_curve_name",
                "speed_9_energy_input_ratio_function_of_temperature_curve_name",
                "speed_9_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                "speed_10_reference_unit_gross_rated_heating_capacity",
                "speed_10_reference_unit_gross_rated_heating_cop",
                "speed_10_reference_unit_rated_air_flow_rate",
                "speed_10_heating_capacity_function_of_temperature_curve_name",
                "speed_10_heating_capacity_function_of_air_flow_fraction_curve_name",
                "speed_10_energy_input_ratio_function_of_temperature_curve_name",
                "speed_10_energy_input_ratio_function_of_air_flow_fraction_curve_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "indoor_air_inlet_node_name",
                    "indoor_air_outlet_node_name",
                    "energy_part_load_fraction_curve_name",
                    "defrost_energy_input_ratio_function_of_temperature_curve_name",
                    "defrost_strategy",
                    "defrost_control",
                    "speed_1_heating_capacity_function_of_temperature_curve_name",
                    "speed_1_total_heating_capacity_function_of_air_flow_fraction_curve_name",
                    "speed_1_energy_input_ratio_function_of_temperature_curve_name",
                    "speed_1_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                    "speed_2_heating_capacity_function_of_temperature_curve_name",
                    "speed_2_total_heating_capacity_function_of_air_flow_fraction_curve_name",
                    "speed_2_energy_input_ratio_function_of_temperature_curve_name",
                    "speed_2_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                    "speed_3_heating_capacity_function_of_temperature_curve_name",
                    "speed_3_total_heating_capacity_function_of_air_flow_fraction_curve_name",
                    "speed_3_energy_input_ratio_function_of_temperature_curve_name",
                    "speed_3_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                    "speed_4_heating_capacity_function_of_temperature_curve_name",
                    "speed_4_heating_capacity_function_of_air_flow_fraction_curve_name",
                    "speed_4_energy_input_ratio_function_of_temperature_curve_name",
                    "speed_4_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                    "speed_5_heating_capacity_function_of_temperature_curve_name",
                    "speed_5_heating_capacity_function_of_air_flow_fraction_curve_name",
                    "speed_5_energy_input_ratio_function_of_temperature_curve_name",
                    "speed_5_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                    "speed_6_heating_capacity_function_of_temperature_curve_name",
                    "speed_6_heating_capacity_function_of_air_flow_fraction_curve_name",
                    "speed_6_energy_input_ratio_function_of_temperature_curve_name",
                    "speed_6_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                    "speed_7_heating_capacity_function_of_temperature_curve_name",
                    "speed_7_heating_capacity_function_of_air_flow_fraction_curve_name",
                    "speed_7_energy_input_ratio_function_of_temperature_curve_name",
                    "speed_7_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                    "speed_8_heating_capacity_function_of_temperature_curve_name",
                    "speed_8_heating_capacity_function_of_air_flow_fraction_curve_name",
                    "speed_8_energy_input_ratio_function_of_temperature_curve_name",
                    "speed_8_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                    "speed_9_heating_capacity_function_of_temperature_curve_name",
                    "speed_9_heating_capacity_function_of_air_flow_fraction_curve_name",
                    "speed_9_energy_input_ratio_function_of_temperature_curve_name",
                    "speed_9_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                    "speed_10_heating_capacity_function_of_temperature_curve_name",
                    "speed_10_heating_capacity_function_of_air_flow_fraction_curve_name",
                    "speed_10_energy_input_ratio_function_of_temperature_curve_name",
                    "speed_10_energy_input_ratio_function_of_air_flow_fraction_curve_name"
                ]
            },
            "numerics": {
                "fields": [
                    "number_of_speeds",
                    "nominal_speed_level",
                    "rated_heating_capacity_at_selected_nominal_speed_level",
                    "rated_air_flow_rate_at_selected_nominal_speed_level",
                    "minimum_outdoor_dry_bulb_temperature_for_compressor_operation",
                    "outdoor_dry_bulb_temperature_to_turn_on_compressor",
                    "maximum_outdoor_dry_bulb_temperature_for_defrost_operation",
                    "crankcase_heater_capacity",
                    "maximum_outdoor_dry_bulb_temperature_for_crankcase_heater_operation",
                    "defrost_time_period_fraction",
                    "resistive_defrost_heater_capacity",
                    "speed_1_reference_unit_gross_rated_heating_capacity",
                    "speed_1_reference_unit_gross_rated_heating_cop",
                    "speed_1_reference_unit_rated_air_flow_rate",
                    "speed_2_reference_unit_gross_rated_heating_capacity",
                    "speed_2_reference_unit_gross_rated_heating_cop",
                    "speed_2_reference_unit_rated_air_flow_rate",
                    "speed_3_reference_unit_gross_rated_heating_capacity",
                    "speed_3_reference_unit_gross_rated_heating_cop",
                    "speed_3_reference_unit_rated_air_flow_rate",
                    "speed_4_reference_unit_gross_rated_heating_capacity",
                    "speed_4_reference_unit_gross_rated_heating_cop",
                    "speed_4_reference_unit_rated_air_flow_rate",
                    "speed_5_reference_unit_gross_rated_heating_capacity",
                    "speed_5_reference_unit_gross_rated_heating_cop",
                    "speed_5_reference_unit_rated_air_flow_rate",
                    "speed_6_reference_unit_gross_rated_heating_capacity",
                    "speed_6_reference_unit_gross_rated_heating_cop",
                    "speed_6_reference_unit_rated_air_flow_rate",
                    "speed_7_reference_unit_gross_rated_heating_capacity",
                    "speed_7_reference_unit_gross_rated_heating_cop",
                    "speed_7_reference_unit_rated_air_flow_rate",
                    "speed_8_reference_unit_gross_rated_heating_capacity",
                    "speed_8_reference_unit_gross_rated_heating_cop",
                    "speed_8_reference_unit_rated_air_flow_rate",
                    "speed_9_reference_unit_gross_rated_heating_capacity",
                    "speed_9_reference_unit_gross_rated_heating_cop",
                    "speed_9_reference_unit_rated_air_flow_rate",
                    "speed_10_reference_unit_gross_rated_heating_capacity",
                    "speed_10_reference_unit_gross_rated_heating_cop",
                    "speed_10_reference_unit_rated_air_flow_rate"
                ]
            }
        },
        "type": "object",
        "memo": "Direct expansion (DX) heating coil (air-to-air heat pump) and compressor unit (includes electric compressor and outdoor fan), variable-speed, with defrost controls. Requires two to ten sets of performance data and will interpolate between speeds.",
        "min_fields": 25.0
    }
}
```
