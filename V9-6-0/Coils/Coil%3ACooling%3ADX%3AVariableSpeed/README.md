```
{
    "Coil:Cooling:DX:VariableSpeed": {
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
                    "gross_rated_total_cooling_capacity_at_selected_nominal_speed_level": {
                        "note": "Total cooling capacity not accounting for the effect of supply air fan heat",
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
                    "nominal_time_for_condensate_to_begin_leaving_the_coil": {
                        "type": "number",
                        "units": "s",
                        "minimum": 0.0,
                        "default": 0.0
                    },
                    "initial_moisture_evaporation_rate_divided_by_steady_state_ac_latent_capacity": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "default": 0.0
                    },
                    "energy_part_load_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "quadratic curve = a + b*PLR + c*PLR**2 cubic curve = a + b*PLR + c*PLR**2 + d*PLR**3 PLR = part load ratio (cooling load/steady state capacity)"
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
                    "speed_1_reference_unit_gross_rated_total_cooling_capacity": {
                        "type": "number",
                        "note": "Total cooling capacity not accounting for the effect of supply air fan heat",
                        "units": "W",
                        "minimum": 0.0
                    },
                    "speed_1_reference_unit_gross_rated_sensible_heat_ratio": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "speed_1_reference_unit_gross_rated_cooling_cop": {
                        "type": "number",
                        "units": "W/W",
                        "exclusiveMinimum": 0.0
                    },
                    "speed_1_reference_unit_rated_air_flow_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "minimum": 0.0
                    },
                    "speed_1_reference_unit_rated_condenser_air_flow_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "minimum": 0.0,
                        "note": "This field is only used for Condenser Type = EvaporativelyCooled"
                    },
                    "speed_1_reference_unit_rated_pad_effectiveness_of_evap_precooling": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "note": "This field is only used for Condenser Type = EvaporativelyCooled"
                    },
                    "speed_1_total_cooling_capacity_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "curve = a + b*wb + c*wb**2 + d*odb + e*odb**2 + f*wb*odb wb = entering wet-bulb temperature (C) odb = air entering temperature seen by the condenser (C)"
                    },
                    "speed_1_total_cooling_capacity_function_of_air_flow_fraction_curve_name": {
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
                        "note": "curve = a + b*wb + c*wb**2 + d*odb + e*odb**2 + f*wb*odb wb = entering wet-bulb temperature (C) odb = air entering temperature seen by the condenser (C)"
                    },
                    "speed_1_energy_input_ratio_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
                    },
                    "speed_2_reference_unit_gross_rated_total_cooling_capacity": {
                        "type": "number",
                        "note": "Total cooling capacity not accounting for the effect of supply air fan heat",
                        "units": "W",
                        "minimum": 0.0
                    },
                    "speed_2_reference_unit_gross_rated_sensible_heat_ratio": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "speed_2_reference_unit_gross_rated_cooling_cop": {
                        "type": "number",
                        "units": "W/W",
                        "exclusiveMinimum": 0.0
                    },
                    "speed_2_reference_unit_rated_air_flow_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "minimum": 0.0
                    },
                    "speed_2_reference_unit_rated_condenser_air_flow_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "minimum": 0.0
                    },
                    "speed_2_reference_unit_rated_pad_effectiveness_of_evap_precooling": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "speed_2_total_cooling_capacity_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "curve = a + b*wb + c*wb**2 + d*odb + e*odb**2 + f*wb*odb wb = entering wet-bulb temperature (C) odb = air entering temperature seen by the condenser (C)"
                    },
                    "speed_2_total_cooling_capacity_function_of_air_flow_fraction_curve_name": {
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
                        "note": "curve = a + b*wb + c*wb**2 + d*odb + e*odb**2 + f*wb*odb wb = entering wet-bulb temperature (C) odb = air entering temperature seen by the condenser (C)"
                    },
                    "speed_2_energy_input_ratio_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
                    },
                    "speed_3_reference_unit_gross_rated_total_cooling_capacity": {
                        "type": "number",
                        "note": "Total cooling capacity not accounting for the effect of supply air fan heat",
                        "units": "W",
                        "minimum": 0.0
                    },
                    "speed_3_reference_unit_gross_rated_sensible_heat_ratio": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "speed_3_reference_unit_gross_rated_cooling_cop": {
                        "type": "number",
                        "units": "W/W",
                        "exclusiveMinimum": 0.0
                    },
                    "speed_3_reference_unit_rated_air_flow_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "minimum": 0.0
                    },
                    "speed_3_reference_unit_rated_condenser_air_flow_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "minimum": 0.0
                    },
                    "speed_3_reference_unit_rated_pad_effectiveness_of_evap_precooling": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "speed_3_total_cooling_capacity_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "curve = a + b*wb + c*wb**2 + d*odb + e*odb**2 + f*wb*odb wb = entering wet-bulb temperature (C) odb = air entering temperature seen by the condenser (C)"
                    },
                    "speed_3_total_cooling_capacity_function_of_air_flow_fraction_curve_name": {
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
                        "note": "curve = a + b*wb + c*wb**2 + d*odb + e*odb**2 + f*wb*odb wb = entering wet-bulb temperature (C) odb = air entering temperature seen by the condenser (C)"
                    },
                    "speed_3_energy_input_ratio_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
                    },
                    "speed_4_reference_unit_gross_rated_total_cooling_capacity": {
                        "type": "number",
                        "note": "Total cooling capacity not accounting for the effect of supply air fan heat",
                        "units": "W",
                        "minimum": 0.0
                    },
                    "speed_4_reference_unit_gross_rated_sensible_heat_ratio": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "speed_4_reference_unit_gross_rated_cooling_cop": {
                        "type": "number",
                        "units": "W/W",
                        "exclusiveMinimum": 0.0
                    },
                    "speed_4_reference_unit_rated_air_flow_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "minimum": 0.0
                    },
                    "speed_4_reference_unit_rated_condenser_air_flow_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "minimum": 0.0
                    },
                    "speed_4_reference_unit_rated_pad_effectiveness_of_evap_precooling": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "speed_4_total_cooling_capacity_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "curve = a + b*wb + c*wb**2 + d*odb + e*odb**2 + f*wb*odb wb = entering wet-bulb temperature (C) odb = air entering temperature seen by the condenser (C)"
                    },
                    "speed_4_total_cooling_capacity_function_of_air_flow_fraction_curve_name": {
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
                        "note": "curve = a + b*wb + c*wb**2 + d*odb + e*odb**2 + f*wb*odb wb = entering wet-bulb temperature (C) odb = air entering temperature seen by the condenser (C)"
                    },
                    "speed_4_energy_input_ratio_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
                    },
                    "speed_5_reference_unit_gross_rated_total_cooling_capacity": {
                        "type": "number",
                        "note": "Total cooling capacity not accounting for the effect of supply air fan heat",
                        "units": "W",
                        "minimum": 0.0
                    },
                    "speed_5_reference_unit_gross_rated_sensible_heat_ratio": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "speed_5_reference_unit_gross_rated_cooling_cop": {
                        "type": "number",
                        "units": "W/W",
                        "exclusiveMinimum": 0.0
                    },
                    "speed_5_reference_unit_rated_air_flow_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "minimum": 0.0
                    },
                    "speed_5_reference_unit_rated_condenser_air_flow_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "minimum": 0.0
                    },
                    "speed_5_reference_unit_rated_pad_effectiveness_of_evap_precooling": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "speed_5_total_cooling_capacity_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "curve = a + b*wb + c*wb**2 + d*odb + e*odb**2 + f*wb*odb wb = entering wet-bulb temperature (C) odb = air entering temperature seen by the condenser (C)"
                    },
                    "speed_5_total_cooling_capacity_function_of_air_flow_fraction_curve_name": {
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
                        "note": "curve = a + b*wb + c*wb**2 + d*odb + e*odb**2 + f*wb*odb wb = entering wet-bulb temperature (C) odb = air entering temperature seen by the condenser (C)"
                    },
                    "speed_5_energy_input_ratio_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
                    },
                    "speed_6_reference_unit_gross_rated_total_cooling_capacity": {
                        "type": "number",
                        "note": "Total cooling capacity not accounting for the effect of supply air fan heat",
                        "units": "W",
                        "minimum": 0.0
                    },
                    "speed_6_reference_unit_gross_rated_sensible_heat_ratio": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "speed_6_reference_unit_gross_rated_cooling_cop": {
                        "type": "number",
                        "units": "W/W",
                        "exclusiveMinimum": 0.0
                    },
                    "speed_6_reference_unit_rated_air_flow_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "minimum": 0.0
                    },
                    "speed_6_reference_unit_condenser_air_flow_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "minimum": 0.0
                    },
                    "speed_6_reference_unit_rated_pad_effectiveness_of_evap_precooling": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "speed_6_total_cooling_capacity_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "curve = a + b*wb + c*wb**2 + d*odb + e*odb**2 + f*wb*odb wb = entering wet-bulb temperature (C) odb = air entering temperature seen by the condenser (C)"
                    },
                    "speed_6_total_cooling_capacity_function_of_air_flow_fraction_curve_name": {
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
                        "note": "curve = a + b*wb + c*wb**2 + d*odb + e*odb**2 + f*wb*odb wb = entering wet-bulb temperature (C) odb = air entering temperature seen by the condenser (C)"
                    },
                    "speed_6_energy_input_ratio_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
                    },
                    "speed_7_reference_unit_gross_rated_total_cooling_capacity": {
                        "type": "number",
                        "note": "Total cooling capacity not accounting for the effect of supply air fan heat",
                        "units": "W",
                        "minimum": 0.0
                    },
                    "speed_7_reference_unit_gross_rated_sensible_heat_ratio": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "speed_7_reference_unit_gross_rated_cooling_cop": {
                        "type": "number",
                        "units": "W/W",
                        "exclusiveMinimum": 0.0
                    },
                    "speed_7_reference_unit_rated_air_flow_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "minimum": 0.0
                    },
                    "speed_7_reference_unit_condenser_flow_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "minimum": 0.0
                    },
                    "speed_7_reference_unit_rated_pad_effectiveness_of_evap_precooling": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "speed_7_total_cooling_capacity_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "curve = a + b*wb + c*wb**2 + d*odb + e*odb**2 + f*wb*odb wb = entering wet-bulb temperature (C) odb = air entering temperature seen by the condenser (C)"
                    },
                    "speed_7_total_cooling_capacity_function_of_air_flow_fraction_curve_name": {
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
                        "note": "curve = a + b*wb + c*wb**2 + d*odb + e*odb**2 + f*wb*odb wb = entering wet-bulb temperature (C) odb = air entering temperature seen by the condenser (C)"
                    },
                    "speed_7_energy_input_ratio_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
                    },
                    "speed_8_reference_unit_gross_rated_total_cooling_capacity": {
                        "type": "number",
                        "note": "Total cooling capacity not accounting for the effect of supply air fan heat",
                        "units": "W",
                        "minimum": 0.0
                    },
                    "speed_8_reference_unit_gross_rated_sensible_heat_ratio": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "speed_8_reference_unit_gross_rated_cooling_cop": {
                        "type": "number",
                        "units": "W/W",
                        "exclusiveMinimum": 0.0
                    },
                    "speed_8_reference_unit_rated_air_flow_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "minimum": 0.0
                    },
                    "speed_8_reference_unit_condenser_air_flow_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "minimum": 0.0
                    },
                    "speed_8_reference_unit_rated_pad_effectiveness_of_evap_precooling": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "speed_8_total_cooling_capacity_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "curve = a + b*wb + c*wb**2 + d*odb + e*odb**2 + f*wb*odb wb = entering wet-bulb temperature (C) odb = air entering temperature seen by the condenser (C)"
                    },
                    "speed_8_total_cooling_capacity_function_of_air_flow_fraction_curve_name": {
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
                        "note": "curve = a + b*wb + c*wb**2 + d*odb + e*odb**2 + f*wb*odb wb = entering wet-bulb temperature (C) odb = air entering temperature seen by the condenser (C)"
                    },
                    "speed_8_energy_input_ratio_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
                    },
                    "speed_9_reference_unit_gross_rated_total_cooling_capacity": {
                        "type": "number",
                        "note": "Total cooling capacity not accounting for the effect of supply air fan heat",
                        "units": "W",
                        "minimum": 0.0
                    },
                    "speed_9_reference_unit_gross_rated_sensible_heat_ratio": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "speed_9_reference_unit_gross_rated_cooling_cop": {
                        "type": "number",
                        "units": "W/W",
                        "exclusiveMinimum": 0.0
                    },
                    "speed_9_reference_unit_rated_air_flow_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "minimum": 0.0
                    },
                    "speed_9_reference_unit_condenser_air_flow_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "minimum": 0.0,
                        "note": "optional"
                    },
                    "speed_9_reference_unit_rated_pad_effectiveness_of_evap_precooling": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "note": "optional"
                    },
                    "speed_9_total_cooling_capacity_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "curve = a + b*wb + c*wb**2 + d*odb + e*odb**2 + f*wb*odb wb = entering wet-bulb temperature (C) odb = air entering temperature seen by the condenser (C)"
                    },
                    "speed_9_total_cooling_capacity_function_of_air_flow_fraction_curve_name": {
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
                        "note": "curve = a + b*wb + c*wb**2 + d*odb + e*odb**2 + f*wb*odb wb = entering wet-bulb temperature (C) odb = air entering temperature seen by the condenser (C)"
                    },
                    "speed_9_energy_input_ratio_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
                    },
                    "speed_10_reference_unit_gross_rated_total_cooling_capacity": {
                        "type": "number",
                        "note": "Total cooling capacity not accounting for the effect of supply air fan heat",
                        "units": "W",
                        "minimum": 0.0
                    },
                    "speed_10_reference_unit_gross_rated_sensible_heat_ratio": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "speed_10_reference_unit_gross_rated_cooling_cop": {
                        "type": "number",
                        "units": "W/W",
                        "exclusiveMinimum": 0.0
                    },
                    "speed_10_reference_unit_rated_air_flow_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "minimum": 0.0
                    },
                    "speed_10_reference_unit_condenser_air_flow_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "minimum": 0.0,
                        "note": "optional"
                    },
                    "speed_10_reference_unit_rated_pad_effectiveness_of_evap_precooling": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "note": "optional"
                    },
                    "speed_10_total_cooling_capacity_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "curve = a + b*wb + c*wb**2 + d*odb + e*odb**2 + f*wb*odb wb = entering wet-bulb temperature (C) odb = air entering temperature seen by the condenser (C)"
                    },
                    "speed_10_total_cooling_capacity_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "note": "optional quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ]
                    },
                    "speed_10_energy_input_ratio_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "curve = a + b*wb + c*wb**2 + d*odb + e*odb**2 + f*wb*odb wb = entering wet-bulb temperature (C) odb = air entering temperature seen by the condenser (C)"
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
                    "speed_1_reference_unit_gross_rated_total_cooling_capacity",
                    "speed_1_reference_unit_gross_rated_sensible_heat_ratio",
                    "speed_1_reference_unit_gross_rated_cooling_cop",
                    "speed_1_reference_unit_rated_air_flow_rate",
                    "speed_1_total_cooling_capacity_function_of_temperature_curve_name",
                    "speed_1_total_cooling_capacity_function_of_air_flow_fraction_curve_name",
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
                "CoolingCoilsDXVariableSpeed",
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
                "gross_rated_total_cooling_capacity_at_selected_nominal_speed_level": {
                    "field_name": "Gross Rated Total Cooling Capacity At Selected Nominal Speed Level",
                    "field_type": "n"
                },
                "rated_air_flow_rate_at_selected_nominal_speed_level": {
                    "field_name": "Rated Air Flow Rate At Selected Nominal Speed Level",
                    "field_type": "n"
                },
                "nominal_time_for_condensate_to_begin_leaving_the_coil": {
                    "field_name": "Nominal Time for Condensate to Begin Leaving the Coil",
                    "field_type": "n"
                },
                "initial_moisture_evaporation_rate_divided_by_steady_state_ac_latent_capacity": {
                    "field_name": "Initial Moisture Evaporation Rate Divided by Steady-State AC Latent Capacity",
                    "field_type": "n"
                },
                "energy_part_load_fraction_curve_name": {
                    "field_name": "Energy Part Load Fraction Curve Name",
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
                "speed_1_reference_unit_gross_rated_total_cooling_capacity": {
                    "field_name": "Speed 1 Reference Unit Gross Rated Total Cooling Capacity",
                    "field_type": "n"
                },
                "speed_1_reference_unit_gross_rated_sensible_heat_ratio": {
                    "field_name": "Speed 1 Reference Unit Gross Rated Sensible Heat Ratio",
                    "field_type": "n"
                },
                "speed_1_reference_unit_gross_rated_cooling_cop": {
                    "field_name": "Speed 1 Reference Unit Gross Rated Cooling COP",
                    "field_type": "n"
                },
                "speed_1_reference_unit_rated_air_flow_rate": {
                    "field_name": "Speed 1 Reference Unit Rated Air Flow Rate",
                    "field_type": "n"
                },
                "speed_1_reference_unit_rated_condenser_air_flow_rate": {
                    "field_name": "Speed 1 Reference Unit Rated Condenser Air Flow Rate",
                    "field_type": "n"
                },
                "speed_1_reference_unit_rated_pad_effectiveness_of_evap_precooling": {
                    "field_name": "Speed 1 Reference Unit Rated Pad Effectiveness of Evap Precooling",
                    "field_type": "n"
                },
                "speed_1_total_cooling_capacity_function_of_temperature_curve_name": {
                    "field_name": "Speed 1 Total Cooling Capacity Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_1_total_cooling_capacity_function_of_air_flow_fraction_curve_name": {
                    "field_name": "Speed 1 Total Cooling Capacity Function of Air Flow Fraction Curve Name",
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
                "speed_2_reference_unit_gross_rated_total_cooling_capacity": {
                    "field_name": "Speed 2 Reference Unit Gross Rated Total Cooling Capacity",
                    "field_type": "n"
                },
                "speed_2_reference_unit_gross_rated_sensible_heat_ratio": {
                    "field_name": "Speed 2 Reference Unit Gross Rated Sensible Heat Ratio",
                    "field_type": "n"
                },
                "speed_2_reference_unit_gross_rated_cooling_cop": {
                    "field_name": "Speed 2 Reference Unit Gross Rated Cooling COP",
                    "field_type": "n"
                },
                "speed_2_reference_unit_rated_air_flow_rate": {
                    "field_name": "Speed 2 Reference Unit Rated Air Flow Rate",
                    "field_type": "n"
                },
                "speed_2_reference_unit_rated_condenser_air_flow_rate": {
                    "field_name": "Speed 2 Reference Unit Rated Condenser Air Flow Rate",
                    "field_type": "n"
                },
                "speed_2_reference_unit_rated_pad_effectiveness_of_evap_precooling": {
                    "field_name": "Speed 2 Reference Unit Rated Pad Effectiveness of Evap Precooling",
                    "field_type": "n"
                },
                "speed_2_total_cooling_capacity_function_of_temperature_curve_name": {
                    "field_name": "Speed 2 Total Cooling Capacity Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_2_total_cooling_capacity_function_of_air_flow_fraction_curve_name": {
                    "field_name": "Speed 2 Total Cooling Capacity Function of Air Flow Fraction Curve Name",
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
                "speed_3_reference_unit_gross_rated_total_cooling_capacity": {
                    "field_name": "Speed 3 Reference Unit Gross Rated Total Cooling Capacity",
                    "field_type": "n"
                },
                "speed_3_reference_unit_gross_rated_sensible_heat_ratio": {
                    "field_name": "Speed 3 Reference Unit Gross Rated Sensible Heat Ratio",
                    "field_type": "n"
                },
                "speed_3_reference_unit_gross_rated_cooling_cop": {
                    "field_name": "Speed 3 Reference Unit Gross Rated Cooling COP",
                    "field_type": "n"
                },
                "speed_3_reference_unit_rated_air_flow_rate": {
                    "field_name": "Speed 3 Reference Unit Rated Air Flow Rate",
                    "field_type": "n"
                },
                "speed_3_reference_unit_rated_condenser_air_flow_rate": {
                    "field_name": "Speed 3 Reference Unit Rated Condenser Air Flow Rate",
                    "field_type": "n"
                },
                "speed_3_reference_unit_rated_pad_effectiveness_of_evap_precooling": {
                    "field_name": "Speed 3 Reference Unit Rated Pad Effectiveness of Evap Precooling",
                    "field_type": "n"
                },
                "speed_3_total_cooling_capacity_function_of_temperature_curve_name": {
                    "field_name": "Speed 3 Total Cooling Capacity Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_3_total_cooling_capacity_function_of_air_flow_fraction_curve_name": {
                    "field_name": "Speed 3 Total Cooling Capacity Function of Air Flow Fraction Curve Name",
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
                "speed_4_reference_unit_gross_rated_total_cooling_capacity": {
                    "field_name": "Speed 4 Reference Unit Gross Rated Total Cooling Capacity",
                    "field_type": "n"
                },
                "speed_4_reference_unit_gross_rated_sensible_heat_ratio": {
                    "field_name": "Speed 4 Reference Unit Gross Rated Sensible Heat Ratio",
                    "field_type": "n"
                },
                "speed_4_reference_unit_gross_rated_cooling_cop": {
                    "field_name": "Speed 4 Reference Unit Gross Rated Cooling COP",
                    "field_type": "n"
                },
                "speed_4_reference_unit_rated_air_flow_rate": {
                    "field_name": "Speed 4 Reference Unit Rated Air Flow Rate",
                    "field_type": "n"
                },
                "speed_4_reference_unit_rated_condenser_air_flow_rate": {
                    "field_name": "Speed 4 Reference Unit Rated Condenser Air Flow Rate",
                    "field_type": "n"
                },
                "speed_4_reference_unit_rated_pad_effectiveness_of_evap_precooling": {
                    "field_name": "Speed 4 Reference Unit Rated Pad Effectiveness of Evap Precooling",
                    "field_type": "n"
                },
                "speed_4_total_cooling_capacity_function_of_temperature_curve_name": {
                    "field_name": "Speed 4 Total Cooling Capacity Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_4_total_cooling_capacity_function_of_air_flow_fraction_curve_name": {
                    "field_name": "Speed 4 Total Cooling Capacity Function of Air Flow Fraction Curve Name",
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
                "speed_5_reference_unit_gross_rated_total_cooling_capacity": {
                    "field_name": "Speed 5 Reference Unit Gross Rated Total Cooling Capacity",
                    "field_type": "n"
                },
                "speed_5_reference_unit_gross_rated_sensible_heat_ratio": {
                    "field_name": "Speed 5 Reference Unit Gross Rated Sensible Heat Ratio",
                    "field_type": "n"
                },
                "speed_5_reference_unit_gross_rated_cooling_cop": {
                    "field_name": "Speed 5 Reference Unit Gross Rated Cooling COP",
                    "field_type": "n"
                },
                "speed_5_reference_unit_rated_air_flow_rate": {
                    "field_name": "Speed 5 Reference Unit Rated Air Flow Rate",
                    "field_type": "n"
                },
                "speed_5_reference_unit_rated_condenser_air_flow_rate": {
                    "field_name": "Speed 5 Reference Unit Rated Condenser Air Flow Rate",
                    "field_type": "n"
                },
                "speed_5_reference_unit_rated_pad_effectiveness_of_evap_precooling": {
                    "field_name": "Speed 5 Reference Unit Rated Pad Effectiveness of Evap Precooling",
                    "field_type": "n"
                },
                "speed_5_total_cooling_capacity_function_of_temperature_curve_name": {
                    "field_name": "Speed 5 Total Cooling Capacity Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_5_total_cooling_capacity_function_of_air_flow_fraction_curve_name": {
                    "field_name": "Speed 5 Total Cooling Capacity Function of Air Flow Fraction Curve Name",
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
                "speed_6_reference_unit_gross_rated_total_cooling_capacity": {
                    "field_name": "Speed 6 Reference Unit Gross Rated Total Cooling Capacity",
                    "field_type": "n"
                },
                "speed_6_reference_unit_gross_rated_sensible_heat_ratio": {
                    "field_name": "Speed 6 Reference Unit Gross Rated Sensible Heat Ratio",
                    "field_type": "n"
                },
                "speed_6_reference_unit_gross_rated_cooling_cop": {
                    "field_name": "Speed 6 Reference Unit Gross Rated Cooling COP",
                    "field_type": "n"
                },
                "speed_6_reference_unit_rated_air_flow_rate": {
                    "field_name": "Speed 6 Reference Unit Rated Air Flow Rate",
                    "field_type": "n"
                },
                "speed_6_reference_unit_condenser_air_flow_rate": {
                    "field_name": "Speed 6 Reference Unit Condenser Air Flow Rate",
                    "field_type": "n"
                },
                "speed_6_reference_unit_rated_pad_effectiveness_of_evap_precooling": {
                    "field_name": "Speed 6 Reference Unit Rated Pad Effectiveness of Evap Precooling",
                    "field_type": "n"
                },
                "speed_6_total_cooling_capacity_function_of_temperature_curve_name": {
                    "field_name": "Speed 6 Total Cooling Capacity Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_6_total_cooling_capacity_function_of_air_flow_fraction_curve_name": {
                    "field_name": "Speed 6 Total Cooling Capacity Function of Air Flow Fraction Curve Name",
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
                "speed_7_reference_unit_gross_rated_total_cooling_capacity": {
                    "field_name": "Speed 7 Reference Unit Gross Rated Total Cooling Capacity",
                    "field_type": "n"
                },
                "speed_7_reference_unit_gross_rated_sensible_heat_ratio": {
                    "field_name": "Speed 7 Reference Unit Gross Rated Sensible Heat Ratio",
                    "field_type": "n"
                },
                "speed_7_reference_unit_gross_rated_cooling_cop": {
                    "field_name": "Speed 7 Reference Unit Gross Rated Cooling COP",
                    "field_type": "n"
                },
                "speed_7_reference_unit_rated_air_flow_rate": {
                    "field_name": "Speed 7 Reference Unit Rated Air Flow Rate",
                    "field_type": "n"
                },
                "speed_7_reference_unit_condenser_flow_rate": {
                    "field_name": "Speed 7 Reference Unit Condenser Flow Rate",
                    "field_type": "n"
                },
                "speed_7_reference_unit_rated_pad_effectiveness_of_evap_precooling": {
                    "field_name": "Speed 7 Reference Unit Rated Pad Effectiveness of Evap Precooling",
                    "field_type": "n"
                },
                "speed_7_total_cooling_capacity_function_of_temperature_curve_name": {
                    "field_name": "Speed 7 Total Cooling Capacity Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_7_total_cooling_capacity_function_of_air_flow_fraction_curve_name": {
                    "field_name": "Speed 7 Total Cooling Capacity Function of Air Flow Fraction Curve Name",
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
                "speed_8_reference_unit_gross_rated_total_cooling_capacity": {
                    "field_name": "Speed 8 Reference Unit Gross Rated Total Cooling Capacity",
                    "field_type": "n"
                },
                "speed_8_reference_unit_gross_rated_sensible_heat_ratio": {
                    "field_name": "Speed 8 Reference Unit Gross Rated Sensible Heat Ratio",
                    "field_type": "n"
                },
                "speed_8_reference_unit_gross_rated_cooling_cop": {
                    "field_name": "Speed 8 Reference Unit Gross Rated Cooling COP",
                    "field_type": "n"
                },
                "speed_8_reference_unit_rated_air_flow_rate": {
                    "field_name": "Speed 8 Reference Unit Rated Air Flow Rate",
                    "field_type": "n"
                },
                "speed_8_reference_unit_condenser_air_flow_rate": {
                    "field_name": "Speed 8 Reference Unit Condenser Air Flow Rate",
                    "field_type": "n"
                },
                "speed_8_reference_unit_rated_pad_effectiveness_of_evap_precooling": {
                    "field_name": "Speed 8 Reference Unit Rated Pad Effectiveness of Evap Precooling",
                    "field_type": "n"
                },
                "speed_8_total_cooling_capacity_function_of_temperature_curve_name": {
                    "field_name": "Speed 8 Total Cooling Capacity Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_8_total_cooling_capacity_function_of_air_flow_fraction_curve_name": {
                    "field_name": "Speed 8 Total Cooling Capacity Function of Air Flow Fraction Curve Name",
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
                "speed_9_reference_unit_gross_rated_total_cooling_capacity": {
                    "field_name": "Speed 9 Reference Unit Gross Rated Total Cooling Capacity",
                    "field_type": "n"
                },
                "speed_9_reference_unit_gross_rated_sensible_heat_ratio": {
                    "field_name": "Speed 9 Reference Unit Gross Rated Sensible Heat Ratio",
                    "field_type": "n"
                },
                "speed_9_reference_unit_gross_rated_cooling_cop": {
                    "field_name": "Speed 9 Reference Unit Gross Rated Cooling COP",
                    "field_type": "n"
                },
                "speed_9_reference_unit_rated_air_flow_rate": {
                    "field_name": "Speed 9 Reference Unit Rated Air Flow Rate",
                    "field_type": "n"
                },
                "speed_9_reference_unit_condenser_air_flow_rate": {
                    "field_name": "Speed 9 Reference Unit Condenser Air Flow Rate",
                    "field_type": "n"
                },
                "speed_9_reference_unit_rated_pad_effectiveness_of_evap_precooling": {
                    "field_name": "Speed 9 Reference Unit Rated Pad Effectiveness of Evap Precooling",
                    "field_type": "n"
                },
                "speed_9_total_cooling_capacity_function_of_temperature_curve_name": {
                    "field_name": "Speed 9 Total Cooling Capacity Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_9_total_cooling_capacity_function_of_air_flow_fraction_curve_name": {
                    "field_name": "Speed 9 Total Cooling Capacity Function of Air Flow Fraction Curve Name",
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
                "speed_10_reference_unit_gross_rated_total_cooling_capacity": {
                    "field_name": "Speed 10 Reference Unit Gross Rated Total Cooling Capacity",
                    "field_type": "n"
                },
                "speed_10_reference_unit_gross_rated_sensible_heat_ratio": {
                    "field_name": "Speed 10 Reference Unit Gross Rated Sensible Heat Ratio",
                    "field_type": "n"
                },
                "speed_10_reference_unit_gross_rated_cooling_cop": {
                    "field_name": "Speed 10 Reference Unit Gross Rated Cooling COP",
                    "field_type": "n"
                },
                "speed_10_reference_unit_rated_air_flow_rate": {
                    "field_name": "Speed 10 Reference Unit Rated Air Flow Rate",
                    "field_type": "n"
                },
                "speed_10_reference_unit_condenser_air_flow_rate": {
                    "field_name": "Speed 10 Reference Unit Condenser Air Flow Rate",
                    "field_type": "n"
                },
                "speed_10_reference_unit_rated_pad_effectiveness_of_evap_precooling": {
                    "field_name": "Speed 10 Reference Unit Rated Pad Effectiveness of Evap Precooling",
                    "field_type": "n"
                },
                "speed_10_total_cooling_capacity_function_of_temperature_curve_name": {
                    "field_name": "Speed 10 Total Cooling Capacity Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_10_total_cooling_capacity_function_of_air_flow_fraction_curve_name": {
                    "field_name": "Speed 10 Total Cooling Capacity Function of Air Flow Fraction Curve Name",
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
                "gross_rated_total_cooling_capacity_at_selected_nominal_speed_level",
                "rated_air_flow_rate_at_selected_nominal_speed_level",
                "nominal_time_for_condensate_to_begin_leaving_the_coil",
                "initial_moisture_evaporation_rate_divided_by_steady_state_ac_latent_capacity",
                "energy_part_load_fraction_curve_name",
                "condenser_air_inlet_node_name",
                "condenser_type",
                "evaporative_condenser_pump_rated_power_consumption",
                "crankcase_heater_capacity",
                "maximum_outdoor_dry_bulb_temperature_for_crankcase_heater_operation",
                "minimum_outdoor_dry_bulb_temperature_for_compressor_operation",
                "supply_water_storage_tank_name",
                "condensate_collection_water_storage_tank_name",
                "basin_heater_capacity",
                "basin_heater_setpoint_temperature",
                "basin_heater_operating_schedule_name",
                "speed_1_reference_unit_gross_rated_total_cooling_capacity",
                "speed_1_reference_unit_gross_rated_sensible_heat_ratio",
                "speed_1_reference_unit_gross_rated_cooling_cop",
                "speed_1_reference_unit_rated_air_flow_rate",
                "speed_1_reference_unit_rated_condenser_air_flow_rate",
                "speed_1_reference_unit_rated_pad_effectiveness_of_evap_precooling",
                "speed_1_total_cooling_capacity_function_of_temperature_curve_name",
                "speed_1_total_cooling_capacity_function_of_air_flow_fraction_curve_name",
                "speed_1_energy_input_ratio_function_of_temperature_curve_name",
                "speed_1_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                "speed_2_reference_unit_gross_rated_total_cooling_capacity",
                "speed_2_reference_unit_gross_rated_sensible_heat_ratio",
                "speed_2_reference_unit_gross_rated_cooling_cop",
                "speed_2_reference_unit_rated_air_flow_rate",
                "speed_2_reference_unit_rated_condenser_air_flow_rate",
                "speed_2_reference_unit_rated_pad_effectiveness_of_evap_precooling",
                "speed_2_total_cooling_capacity_function_of_temperature_curve_name",
                "speed_2_total_cooling_capacity_function_of_air_flow_fraction_curve_name",
                "speed_2_energy_input_ratio_function_of_temperature_curve_name",
                "speed_2_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                "speed_3_reference_unit_gross_rated_total_cooling_capacity",
                "speed_3_reference_unit_gross_rated_sensible_heat_ratio",
                "speed_3_reference_unit_gross_rated_cooling_cop",
                "speed_3_reference_unit_rated_air_flow_rate",
                "speed_3_reference_unit_rated_condenser_air_flow_rate",
                "speed_3_reference_unit_rated_pad_effectiveness_of_evap_precooling",
                "speed_3_total_cooling_capacity_function_of_temperature_curve_name",
                "speed_3_total_cooling_capacity_function_of_air_flow_fraction_curve_name",
                "speed_3_energy_input_ratio_function_of_temperature_curve_name",
                "speed_3_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                "speed_4_reference_unit_gross_rated_total_cooling_capacity",
                "speed_4_reference_unit_gross_rated_sensible_heat_ratio",
                "speed_4_reference_unit_gross_rated_cooling_cop",
                "speed_4_reference_unit_rated_air_flow_rate",
                "speed_4_reference_unit_rated_condenser_air_flow_rate",
                "speed_4_reference_unit_rated_pad_effectiveness_of_evap_precooling",
                "speed_4_total_cooling_capacity_function_of_temperature_curve_name",
                "speed_4_total_cooling_capacity_function_of_air_flow_fraction_curve_name",
                "speed_4_energy_input_ratio_function_of_temperature_curve_name",
                "speed_4_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                "speed_5_reference_unit_gross_rated_total_cooling_capacity",
                "speed_5_reference_unit_gross_rated_sensible_heat_ratio",
                "speed_5_reference_unit_gross_rated_cooling_cop",
                "speed_5_reference_unit_rated_air_flow_rate",
                "speed_5_reference_unit_rated_condenser_air_flow_rate",
                "speed_5_reference_unit_rated_pad_effectiveness_of_evap_precooling",
                "speed_5_total_cooling_capacity_function_of_temperature_curve_name",
                "speed_5_total_cooling_capacity_function_of_air_flow_fraction_curve_name",
                "speed_5_energy_input_ratio_function_of_temperature_curve_name",
                "speed_5_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                "speed_6_reference_unit_gross_rated_total_cooling_capacity",
                "speed_6_reference_unit_gross_rated_sensible_heat_ratio",
                "speed_6_reference_unit_gross_rated_cooling_cop",
                "speed_6_reference_unit_rated_air_flow_rate",
                "speed_6_reference_unit_condenser_air_flow_rate",
                "speed_6_reference_unit_rated_pad_effectiveness_of_evap_precooling",
                "speed_6_total_cooling_capacity_function_of_temperature_curve_name",
                "speed_6_total_cooling_capacity_function_of_air_flow_fraction_curve_name",
                "speed_6_energy_input_ratio_function_of_temperature_curve_name",
                "speed_6_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                "speed_7_reference_unit_gross_rated_total_cooling_capacity",
                "speed_7_reference_unit_gross_rated_sensible_heat_ratio",
                "speed_7_reference_unit_gross_rated_cooling_cop",
                "speed_7_reference_unit_rated_air_flow_rate",
                "speed_7_reference_unit_condenser_flow_rate",
                "speed_7_reference_unit_rated_pad_effectiveness_of_evap_precooling",
                "speed_7_total_cooling_capacity_function_of_temperature_curve_name",
                "speed_7_total_cooling_capacity_function_of_air_flow_fraction_curve_name",
                "speed_7_energy_input_ratio_function_of_temperature_curve_name",
                "speed_7_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                "speed_8_reference_unit_gross_rated_total_cooling_capacity",
                "speed_8_reference_unit_gross_rated_sensible_heat_ratio",
                "speed_8_reference_unit_gross_rated_cooling_cop",
                "speed_8_reference_unit_rated_air_flow_rate",
                "speed_8_reference_unit_condenser_air_flow_rate",
                "speed_8_reference_unit_rated_pad_effectiveness_of_evap_precooling",
                "speed_8_total_cooling_capacity_function_of_temperature_curve_name",
                "speed_8_total_cooling_capacity_function_of_air_flow_fraction_curve_name",
                "speed_8_energy_input_ratio_function_of_temperature_curve_name",
                "speed_8_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                "speed_9_reference_unit_gross_rated_total_cooling_capacity",
                "speed_9_reference_unit_gross_rated_sensible_heat_ratio",
                "speed_9_reference_unit_gross_rated_cooling_cop",
                "speed_9_reference_unit_rated_air_flow_rate",
                "speed_9_reference_unit_condenser_air_flow_rate",
                "speed_9_reference_unit_rated_pad_effectiveness_of_evap_precooling",
                "speed_9_total_cooling_capacity_function_of_temperature_curve_name",
                "speed_9_total_cooling_capacity_function_of_air_flow_fraction_curve_name",
                "speed_9_energy_input_ratio_function_of_temperature_curve_name",
                "speed_9_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                "speed_10_reference_unit_gross_rated_total_cooling_capacity",
                "speed_10_reference_unit_gross_rated_sensible_heat_ratio",
                "speed_10_reference_unit_gross_rated_cooling_cop",
                "speed_10_reference_unit_rated_air_flow_rate",
                "speed_10_reference_unit_condenser_air_flow_rate",
                "speed_10_reference_unit_rated_pad_effectiveness_of_evap_precooling",
                "speed_10_total_cooling_capacity_function_of_temperature_curve_name",
                "speed_10_total_cooling_capacity_function_of_air_flow_fraction_curve_name",
                "speed_10_energy_input_ratio_function_of_temperature_curve_name",
                "speed_10_energy_input_ratio_function_of_air_flow_fraction_curve_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "indoor_air_inlet_node_name",
                    "indoor_air_outlet_node_name",
                    "energy_part_load_fraction_curve_name",
                    "condenser_air_inlet_node_name",
                    "condenser_type",
                    "supply_water_storage_tank_name",
                    "condensate_collection_water_storage_tank_name",
                    "basin_heater_operating_schedule_name",
                    "speed_1_total_cooling_capacity_function_of_temperature_curve_name",
                    "speed_1_total_cooling_capacity_function_of_air_flow_fraction_curve_name",
                    "speed_1_energy_input_ratio_function_of_temperature_curve_name",
                    "speed_1_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                    "speed_2_total_cooling_capacity_function_of_temperature_curve_name",
                    "speed_2_total_cooling_capacity_function_of_air_flow_fraction_curve_name",
                    "speed_2_energy_input_ratio_function_of_temperature_curve_name",
                    "speed_2_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                    "speed_3_total_cooling_capacity_function_of_temperature_curve_name",
                    "speed_3_total_cooling_capacity_function_of_air_flow_fraction_curve_name",
                    "speed_3_energy_input_ratio_function_of_temperature_curve_name",
                    "speed_3_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                    "speed_4_total_cooling_capacity_function_of_temperature_curve_name",
                    "speed_4_total_cooling_capacity_function_of_air_flow_fraction_curve_name",
                    "speed_4_energy_input_ratio_function_of_temperature_curve_name",
                    "speed_4_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                    "speed_5_total_cooling_capacity_function_of_temperature_curve_name",
                    "speed_5_total_cooling_capacity_function_of_air_flow_fraction_curve_name",
                    "speed_5_energy_input_ratio_function_of_temperature_curve_name",
                    "speed_5_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                    "speed_6_total_cooling_capacity_function_of_temperature_curve_name",
                    "speed_6_total_cooling_capacity_function_of_air_flow_fraction_curve_name",
                    "speed_6_energy_input_ratio_function_of_temperature_curve_name",
                    "speed_6_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                    "speed_7_total_cooling_capacity_function_of_temperature_curve_name",
                    "speed_7_total_cooling_capacity_function_of_air_flow_fraction_curve_name",
                    "speed_7_energy_input_ratio_function_of_temperature_curve_name",
                    "speed_7_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                    "speed_8_total_cooling_capacity_function_of_temperature_curve_name",
                    "speed_8_total_cooling_capacity_function_of_air_flow_fraction_curve_name",
                    "speed_8_energy_input_ratio_function_of_temperature_curve_name",
                    "speed_8_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                    "speed_9_total_cooling_capacity_function_of_temperature_curve_name",
                    "speed_9_total_cooling_capacity_function_of_air_flow_fraction_curve_name",
                    "speed_9_energy_input_ratio_function_of_temperature_curve_name",
                    "speed_9_energy_input_ratio_function_of_air_flow_fraction_curve_name",
                    "speed_10_total_cooling_capacity_function_of_temperature_curve_name",
                    "speed_10_total_cooling_capacity_function_of_air_flow_fraction_curve_name",
                    "speed_10_energy_input_ratio_function_of_temperature_curve_name",
                    "speed_10_energy_input_ratio_function_of_air_flow_fraction_curve_name"
                ]
            },
            "numerics": {
                "fields": [
                    "number_of_speeds",
                    "nominal_speed_level",
                    "gross_rated_total_cooling_capacity_at_selected_nominal_speed_level",
                    "rated_air_flow_rate_at_selected_nominal_speed_level",
                    "nominal_time_for_condensate_to_begin_leaving_the_coil",
                    "initial_moisture_evaporation_rate_divided_by_steady_state_ac_latent_capacity",
                    "evaporative_condenser_pump_rated_power_consumption",
                    "crankcase_heater_capacity",
                    "maximum_outdoor_dry_bulb_temperature_for_crankcase_heater_operation",
                    "minimum_outdoor_dry_bulb_temperature_for_compressor_operation",
                    "basin_heater_capacity",
                    "basin_heater_setpoint_temperature",
                    "speed_1_reference_unit_gross_rated_total_cooling_capacity",
                    "speed_1_reference_unit_gross_rated_sensible_heat_ratio",
                    "speed_1_reference_unit_gross_rated_cooling_cop",
                    "speed_1_reference_unit_rated_air_flow_rate",
                    "speed_1_reference_unit_rated_condenser_air_flow_rate",
                    "speed_1_reference_unit_rated_pad_effectiveness_of_evap_precooling",
                    "speed_2_reference_unit_gross_rated_total_cooling_capacity",
                    "speed_2_reference_unit_gross_rated_sensible_heat_ratio",
                    "speed_2_reference_unit_gross_rated_cooling_cop",
                    "speed_2_reference_unit_rated_air_flow_rate",
                    "speed_2_reference_unit_rated_condenser_air_flow_rate",
                    "speed_2_reference_unit_rated_pad_effectiveness_of_evap_precooling",
                    "speed_3_reference_unit_gross_rated_total_cooling_capacity",
                    "speed_3_reference_unit_gross_rated_sensible_heat_ratio",
                    "speed_3_reference_unit_gross_rated_cooling_cop",
                    "speed_3_reference_unit_rated_air_flow_rate",
                    "speed_3_reference_unit_rated_condenser_air_flow_rate",
                    "speed_3_reference_unit_rated_pad_effectiveness_of_evap_precooling",
                    "speed_4_reference_unit_gross_rated_total_cooling_capacity",
                    "speed_4_reference_unit_gross_rated_sensible_heat_ratio",
                    "speed_4_reference_unit_gross_rated_cooling_cop",
                    "speed_4_reference_unit_rated_air_flow_rate",
                    "speed_4_reference_unit_rated_condenser_air_flow_rate",
                    "speed_4_reference_unit_rated_pad_effectiveness_of_evap_precooling",
                    "speed_5_reference_unit_gross_rated_total_cooling_capacity",
                    "speed_5_reference_unit_gross_rated_sensible_heat_ratio",
                    "speed_5_reference_unit_gross_rated_cooling_cop",
                    "speed_5_reference_unit_rated_air_flow_rate",
                    "speed_5_reference_unit_rated_condenser_air_flow_rate",
                    "speed_5_reference_unit_rated_pad_effectiveness_of_evap_precooling",
                    "speed_6_reference_unit_gross_rated_total_cooling_capacity",
                    "speed_6_reference_unit_gross_rated_sensible_heat_ratio",
                    "speed_6_reference_unit_gross_rated_cooling_cop",
                    "speed_6_reference_unit_rated_air_flow_rate",
                    "speed_6_reference_unit_condenser_air_flow_rate",
                    "speed_6_reference_unit_rated_pad_effectiveness_of_evap_precooling",
                    "speed_7_reference_unit_gross_rated_total_cooling_capacity",
                    "speed_7_reference_unit_gross_rated_sensible_heat_ratio",
                    "speed_7_reference_unit_gross_rated_cooling_cop",
                    "speed_7_reference_unit_rated_air_flow_rate",
                    "speed_7_reference_unit_condenser_flow_rate",
                    "speed_7_reference_unit_rated_pad_effectiveness_of_evap_precooling",
                    "speed_8_reference_unit_gross_rated_total_cooling_capacity",
                    "speed_8_reference_unit_gross_rated_sensible_heat_ratio",
                    "speed_8_reference_unit_gross_rated_cooling_cop",
                    "speed_8_reference_unit_rated_air_flow_rate",
                    "speed_8_reference_unit_condenser_air_flow_rate",
                    "speed_8_reference_unit_rated_pad_effectiveness_of_evap_precooling",
                    "speed_9_reference_unit_gross_rated_total_cooling_capacity",
                    "speed_9_reference_unit_gross_rated_sensible_heat_ratio",
                    "speed_9_reference_unit_gross_rated_cooling_cop",
                    "speed_9_reference_unit_rated_air_flow_rate",
                    "speed_9_reference_unit_condenser_air_flow_rate",
                    "speed_9_reference_unit_rated_pad_effectiveness_of_evap_precooling",
                    "speed_10_reference_unit_gross_rated_total_cooling_capacity",
                    "speed_10_reference_unit_gross_rated_sensible_heat_ratio",
                    "speed_10_reference_unit_gross_rated_cooling_cop",
                    "speed_10_reference_unit_rated_air_flow_rate",
                    "speed_10_reference_unit_condenser_air_flow_rate",
                    "speed_10_reference_unit_rated_pad_effectiveness_of_evap_precooling"
                ]
            }
        },
        "type": "object",
        "memo": "Direct expansion (DX) cooling coil and condensing unit (includes electric compressor and condenser fan), variable-speed. Optional inputs for moisture evaporation from wet coil when compressor cycles off with continuous fan operation. Requires two to ten sets of performance data and will interpolate between speeds. Modeled as a single coil with variable-speed compressor.",
        "min_fields": 31.0
    }
}
```
