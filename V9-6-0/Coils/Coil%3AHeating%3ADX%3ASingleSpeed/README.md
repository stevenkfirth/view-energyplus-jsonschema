```
{
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
                "gross_rated_heating_capacity": {
                    "note": "Heating capacity not accounting for the effect of supply air fan heat capacity excluding supply air fan heat rating point outdoor dry-bulb temp 8.33 C, outdoor wet-bulb temp 6.11 C rating point heating coil entering air dry-bulb 21.11 C, coil entering wet-bulb 15.55 C",
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
                "gross_rated_heating_cop": {
                    "type": "number",
                    "note": "Rated heating capacity divided by power input to the compressor and outdoor fan, does not include supply air fan heat or supply air fan electrical energy does not include supply air fan heat or supply air fan electrical energy",
                    "units": "W/W",
                    "exclusiveMinimum": 0.0
                },
                "rated_air_flow_rate": {
                    "units": "m3/s",
                    "note": "Flow rate corresponding to rated total capacity should be between 0.00004027 m3/s and .00006041 m3/s per watt of rated heating capacity",
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
                "rated_supply_fan_power_per_volume_flow_rate": {
                    "type": "number",
                    "note": "Enter the supply fan power per air volume flow rate at the rated test conditions. The test conditions vary external static pressure based on heating capacity. This value is only used to calculate Heating Seasonal Performance Factor(HSPF). This value is not used for modeling the supply (condenser) fan during simulations.",
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
                "heating_capacity_function_of_temperature_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions",
                        "UnivariateFunctions"
                    ],
                    "note": "quadratic curve = a + b*oat + c*oat**2 cubic curve = a + b*oat + c*oat**2 + d*oat**3 biquadratic curve = a + b*iat + c*iat**2 + d*oat + e*oat**2 + f*iat*oat oat = outdoor air dry-bulb temperature (C) iat = indoor air dry-bulb temperature (C) Biquadratic curve is recommended if sufficient manufacturer data is available for the heating capacity to be sensitive to both iat and oat."
                },
                "heating_capacity_function_of_flow_fraction_curve_name": {
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
                        "BivariateFunctions",
                        "UnivariateFunctions"
                    ],
                    "note": "quadratic curve = a + b*oat + c*oat**2 cubic curve = a + b*oat + c*oat**2 + d*oat**3 biquadratic curve = a + b*iat + c*iat**2 + d*oat + e*oat**2 + f*iat*oat oat = outdoor air dry-bulb temperature (C) iat = indoor air dry-bulb temperature (C) biquadratic curve is recommended if sufficient manufacturer data is available for the energy input ratio to be sensitive to both iat and oat."
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
                    "note": "quadratic curve = a + b*PLR + c*PLR**2 cubic curve = a + b*PLR + c*PLR**2 + d*PLR**3 PLR = part load ratio (sensible heating load/steady state heating capacity)"
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
                "region_number_for_calculating_hspf": {
                    "type": "number",
                    "minimum": 1.0,
                    "maximum": 6.0,
                    "default": 4.0,
                    "note": "Standard Region number for which HSPF and other standard ratings are calculated"
                },
                "evaporator_air_inlet_node_name": {
                    "type": "string",
                    "note": "Enter the name of an outdoor air node. This node name is also specified in an OutdoorAir:Node or OutdoorAir:NodeList object."
                },
                "zone_name_for_evaporator_placement": {
                    "type": "string",
                    "note": "This input field is name of a conditioned or unconditioned zone where the secondary coil (evaporator) of a heat pump is to be placed. This is an optional input field specified only when user desires to extract heat from the zone. The heat extracted is modelled as internal gain of the zone. If the primary DX system is a heat pump, then the zone name should be the same as the zone name specified for placing the secondary cooling DX coil."
                },
                "secondary_coil_air_flow_rate": {
                    "units": "m3/s",
                    "note": "This input value is the secondary coil (evaporator) air flow rate when the heat pump is working in heating mode or the secondary DX coil (condenser) air flow rate when the heat pump is working in cooling mode.",
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
                "secondary_coil_fan_flow_scaling_factor": {
                    "type": "number",
                    "units": "m3/s",
                    "exclusiveMinimum": 0.0,
                    "default": 1.25,
                    "note": "This input field is scaling factor for autosizing the secondary DX coil fan flow rate. The secondary air flow rate is determined by multiplying the primary DX coil rated air flow rate by the fan flow scaling factor. Default value is 1.25. If the secondary coil fan flow rate is not autosized, then the secondary coil fan flow scaling factor is set to 1.0."
                },
                "nominal_sensible_heat_ratio_of_secondary_coil": {
                    "type": "number",
                    "units": "m3/s",
                    "exclusiveMinimum": 0.0,
                    "maximum": 1.0,
                    "note": "This input value is the nominal sensible heat ratio used to split the heat extracted by a secondary DX coil (evaporator) of a heat pump into sensible and latent components. This is an optional input field. If this input field is left blank, then pure sensible internal heat gain is assumed, i.e., sensible heat ratio of 1.0."
                },
                "sensible_heat_ratio_modifier_function_of_temperature_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ],
                    "note": "curve = a + b*wb + c*wb**2 + d*db + e*db**2 + f*wb*db wb = entering wet-bulb temperature seen by the secondary DX coil (C) db = entering dry-bulb temperature seen by the primary DX coil (C) This input field is name of sensible heat ratio modifier biquadratic curve. The value of this curve modifies the nominal sensible heat ratio for current time step depending on the secondary zone air node wet-bulb temperature and the heating DX coil entering air dry-bulb temperature. This is an optional input field. If this input field is left blank, then the nominal sensible heat ratio specified in the field above will be used."
                },
                "sensible_heat_ratio_modifier_function_of_flow_fraction_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "quadratic curve = a + b*ff + c*ff**2 cubic curve = a + b*ff + c*ff**2 + d*ff**3 ff = secondary air flow fraction of the full load flow This input field is name of sensible heat ratio modifier curve. The value of this curve modifies the nominal sensible heat ratio for current time step depending on the secondary coil air flow fraction. This is an optional input field. If this input field is left blank, then the nominal sensible heat ratio specified will be used."
                }
            },
            "required": [
                "gross_rated_heating_capacity",
                "gross_rated_heating_cop",
                "rated_air_flow_rate",
                "air_inlet_node_name",
                "air_outlet_node_name",
                "heating_capacity_function_of_temperature_curve_name",
                "heating_capacity_function_of_flow_fraction_curve_name",
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
            "HeatingCoilsDX",
            "HeatingCoilsDXSingleSpeed"
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
            "gross_rated_heating_capacity": {
                "field_name": "Gross Rated Heating Capacity",
                "field_type": "n"
            },
            "gross_rated_heating_cop": {
                "field_name": "Gross Rated Heating COP",
                "field_type": "n"
            },
            "rated_air_flow_rate": {
                "field_name": "Rated Air Flow Rate",
                "field_type": "n"
            },
            "rated_supply_fan_power_per_volume_flow_rate": {
                "field_name": "Rated Supply Fan Power Per Volume Flow Rate",
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
            "heating_capacity_function_of_temperature_curve_name": {
                "field_name": "Heating Capacity Function of Temperature Curve Name",
                "field_type": "a"
            },
            "heating_capacity_function_of_flow_fraction_curve_name": {
                "field_name": "Heating Capacity Function of Flow Fraction Curve Name",
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
            "region_number_for_calculating_hspf": {
                "field_name": "Region number for calculating HSPF",
                "field_type": "n"
            },
            "evaporator_air_inlet_node_name": {
                "field_name": "Evaporator Air Inlet Node Name",
                "field_type": "a"
            },
            "zone_name_for_evaporator_placement": {
                "field_name": "Zone Name for Evaporator Placement",
                "field_type": "a"
            },
            "secondary_coil_air_flow_rate": {
                "field_name": "Secondary Coil Air Flow Rate",
                "field_type": "n"
            },
            "secondary_coil_fan_flow_scaling_factor": {
                "field_name": "Secondary Coil Fan Flow Scaling Factor",
                "field_type": "n"
            },
            "nominal_sensible_heat_ratio_of_secondary_coil": {
                "field_name": "Nominal Sensible Heat Ratio of Secondary Coil",
                "field_type": "n"
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
            "availability_schedule_name",
            "gross_rated_heating_capacity",
            "gross_rated_heating_cop",
            "rated_air_flow_rate",
            "rated_supply_fan_power_per_volume_flow_rate",
            "air_inlet_node_name",
            "air_outlet_node_name",
            "heating_capacity_function_of_temperature_curve_name",
            "heating_capacity_function_of_flow_fraction_curve_name",
            "energy_input_ratio_function_of_temperature_curve_name",
            "energy_input_ratio_function_of_flow_fraction_curve_name",
            "part_load_fraction_correlation_curve_name",
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
            "region_number_for_calculating_hspf",
            "evaporator_air_inlet_node_name",
            "zone_name_for_evaporator_placement",
            "secondary_coil_air_flow_rate",
            "secondary_coil_fan_flow_scaling_factor",
            "nominal_sensible_heat_ratio_of_secondary_coil",
            "sensible_heat_ratio_modifier_function_of_temperature_curve_name",
            "sensible_heat_ratio_modifier_function_of_flow_fraction_curve_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "availability_schedule_name",
                "air_inlet_node_name",
                "air_outlet_node_name",
                "heating_capacity_function_of_temperature_curve_name",
                "heating_capacity_function_of_flow_fraction_curve_name",
                "energy_input_ratio_function_of_temperature_curve_name",
                "energy_input_ratio_function_of_flow_fraction_curve_name",
                "part_load_fraction_correlation_curve_name",
                "defrost_energy_input_ratio_function_of_temperature_curve_name",
                "defrost_strategy",
                "defrost_control",
                "evaporator_air_inlet_node_name",
                "zone_name_for_evaporator_placement",
                "sensible_heat_ratio_modifier_function_of_temperature_curve_name",
                "sensible_heat_ratio_modifier_function_of_flow_fraction_curve_name"
            ]
        },
        "numerics": {
            "fields": [
                "gross_rated_heating_capacity",
                "gross_rated_heating_cop",
                "rated_air_flow_rate",
                "rated_supply_fan_power_per_volume_flow_rate",
                "minimum_outdoor_dry_bulb_temperature_for_compressor_operation",
                "outdoor_dry_bulb_temperature_to_turn_on_compressor",
                "maximum_outdoor_dry_bulb_temperature_for_defrost_operation",
                "crankcase_heater_capacity",
                "maximum_outdoor_dry_bulb_temperature_for_crankcase_heater_operation",
                "defrost_time_period_fraction",
                "resistive_defrost_heater_capacity",
                "region_number_for_calculating_hspf",
                "secondary_coil_air_flow_rate",
                "secondary_coil_fan_flow_scaling_factor",
                "nominal_sensible_heat_ratio_of_secondary_coil"
            ]
        }
    },
    "type": "object",
    "memo": "Direct expansion (DX) heating coil (air-to-air heat pump) and compressor unit (includes electric compressor and outdoor fan), single-speed, with defrost controls.",
    "min_fields": 21.0
}
```
