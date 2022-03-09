```
{
    "Coil:WaterHeating:AirToWaterHeatPump:VariableSpeed": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "number_of_speeds": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 1.0,
                        "maximum": 10.0,
                        "default": 1.0
                    },
                    "nominal_speed_level": {
                        "type": "number",
                        "units": "dimensionless",
                        "default": 1.0,
                        "note": "must be lower than or equal to the highest speed number"
                    },
                    "rated_water_heating_capacity": {
                        "type": "number",
                        "units": "W",
                        "exclusiveMinimum": 0.0,
                        "note": "Water Heating capacity at the rated inlet air temperatures, rated condenser inlet water temperature, rated air flow rate, and rated water flow rate. Can optionally include condenser pump heat."
                    },
                    "rated_evaporator_inlet_air_dry_bulb_temperature": {
                        "type": "number",
                        "units": "C",
                        "exclusiveMinimum": 5.0,
                        "default": 19.7,
                        "note": "Evaporator inlet air dry-bulb temperature corresponding to rated coil performance (heating capacity, COP and SHR)."
                    },
                    "rated_evaporator_inlet_air_wet_bulb_temperature": {
                        "type": "number",
                        "units": "C",
                        "exclusiveMinimum": 5.0,
                        "default": 13.5,
                        "note": "Evaporator inlet air wet-bulb temperature corresponding to rated coil performance (heating capacity, COP and SHR)."
                    },
                    "rated_condenser_inlet_water_temperature": {
                        "type": "number",
                        "units": "C",
                        "exclusiveMinimum": 25.0,
                        "default": 57.5,
                        "note": "Condenser inlet water temperature corresponding to rated coil performance (heating capacity, COP and SHR)."
                    },
                    "rated_evaporator_air_flow_rate": {
                        "units": "m3/s",
                        "note": "Evaporator air flow rate corresponding to rated coil performance (heating capacity, COP and SHR). Default is 5.035E-5 m3/s/W (31.25 cfm/MBH) of rated heating capacity when autocalculated.",
                        "anyOf": [
                            {
                                "type": "number",
                                "exclusiveMinimum": 0.0
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "Autocalculate"
                                ]
                            }
                        ]
                    },
                    "rated_condenser_water_flow_rate": {
                        "units": "m3/s",
                        "ip-units": "gal/min",
                        "note": "Condenser water flow rate corresponding to rated coil performance (heating capacity, COP and SHR). Default is 4.487E-8 m3/s/W (0.208 gpm/MBH) of rated heating capacity when autocalculated. A warning message will be issued if the ratio of Rated Condenser Water Flow Rate to Heating Capacity is less than 1.79405E-8 m3/s/W (0.083 gpm/MBH) or greater than 8.97024E-8 m3/s/W (0.417 gpm/MBH), but the simulation will continue.",
                        "anyOf": [
                            {
                                "type": "number",
                                "exclusiveMinimum": 0.0
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "Autocalculate"
                                ]
                            }
                        ]
                    },
                    "evaporator_fan_power_included_in_rated_cop": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "Yes",
                        "note": "Select Yes if the evaporator fan power is included in the rated COP. This choice field impacts the calculation of compressor electric power."
                    },
                    "condenser_pump_power_included_in_rated_cop": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "No",
                        "note": "Select Yes if the condenser pump power is included in the rated COP. This choice field impacts the calculation of compressor electric power."
                    },
                    "condenser_pump_heat_included_in_rated_heating_capacity_and_rated_cop": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "No",
                        "note": "Select Yes if the condenser pump heat is included in the rated heating capacity and rated COP. This choice field impacts the calculation of water heating capacity."
                    },
                    "fraction_of_condenser_pump_heat_to_water": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.2,
                        "note": "Fraction of pump heat transferred to the condenser water. The pump is assumed to be located downstream of the condenser."
                    },
                    "evaporator_air_inlet_node_name": {
                        "type": "string",
                        "note": "The node from which the DX coil draws its inlet air."
                    },
                    "evaporator_air_outlet_node_name": {
                        "type": "string",
                        "note": "The node to which the DX coil sends its outlet air."
                    },
                    "condenser_water_inlet_node_name": {
                        "type": "string",
                        "note": "The node from which the DX coil condenser draws its inlet water. This name should match the source side outlet node name in the associated water heater tank object."
                    },
                    "condenser_water_outlet_node_name": {
                        "type": "string",
                        "note": "The node to which the DX coil condenser sends its outlet water. This name should match the source side inlet node name in the associated water heater tank object."
                    },
                    "crankcase_heater_capacity": {
                        "type": "number",
                        "minimum": 0.0,
                        "default": 0.0,
                        "units": "W",
                        "note": "The compressor crankcase heater only operates when the dry-bulb temperature of air surrounding the compressor is below the Maximum Ambient Temperature for Crankcase Heater Operation and the DX coil is off. The ambient temperature surrounding the compressor is set by the WaterHeater:HeatPump parent object (field Compressor Location)."
                    },
                    "maximum_ambient_temperature_for_crankcase_heater_operation": {
                        "type": "number",
                        "minimum": 0.0,
                        "default": 10.0,
                        "units": "C",
                        "note": "The compressor crankcase heater only operates when the dry-bulb temperature of air surrounding the compressor is below the Maximum Outdoor Temperature for Crankcase Heater Operation and the unit is off. The ambient temperature surrounding the compressor is set by the WaterHeater:HeatPump parent object (field Compressor Location)."
                    },
                    "evaporator_air_temperature_type_for_curve_objects": {
                        "type": "string",
                        "enum": [
                            "",
                            "DryBulbTemperature",
                            "WetBulbTemperature"
                        ],
                        "default": "WetBulbTemperature",
                        "note": "Determines temperature type for heating capacity curves and heating COP curves. This input determines whether the inlet air dry-bulb or wet-bulb temperature is used to evaluate these curves."
                    },
                    "part_load_fraction_correlation_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used Part Load Fraction Correlation (function of part load ratio) should be quadratic or cubic. Quadratic curve = a + b(PLR) + c(PLR)^2. Cubic curve = a + b(PLR) + c(PLR)^2 + d(PLR)^3. PLR = part load ratio (heating delivered/steady state heating capacity). Use curve coefficients of 1,0,0 or leave this field blank when neglecting performance impacts due to variations in part load ratio."
                    },
                    "rated_water_heating_capacity_at_speed_1": {
                        "type": "number",
                        "units": "W",
                        "exclusiveMinimum": 0.0,
                        "note": "Heating capacity at the rated inlet air temperatures, rated condenser inlet water temperature, rated air flow rate, and rated water flow rate. Can optionally include condenser pump heat."
                    },
                    "rated_water_heating_cop_at_speed_1": {
                        "type": "number",
                        "units": "W/W",
                        "exclusiveMinimum": 0.0,
                        "default": 3.2,
                        "note": "Heating coefficient of performance at the rated inlet air and water temperatures, rated condenser inlet water temperature, rated air flow rate, and rated water flow rate. Can optionally include condenser pump power and evaporator fan power (see fields below)."
                    },
                    "rated_sensible_heat_ratio_at_speed_1": {
                        "type": "number",
                        "minimum": 0.5,
                        "maximum": 1.0,
                        "default": 0.85,
                        "note": "Gross air-side sensible heat ratio at the rated inlet air temperatures, rated condenser inlet water temperature, rated air flow rate, and rated water flow rate. Sensible heat ratio equals gross sensible cooling capacity divided by gross total cooling capacity. Rated SHR (gross) should not include evaporator fan heat, only sensible cooling and dehumidification by the coil alone."
                    },
                    "speed_1_reference_unit_rated_air_flow_rate": {
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
                    "speed_1_reference_unit_water_pump_input_power_at_rated_conditions": {
                        "type": "number",
                        "units": "W",
                        "minimum": 0.0
                    },
                    "speed_1_total_wh_capacity_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used curve = a + b*wb + c*wb**2 + d*ewt + e*ewt**2 + f*wb*ewt wb = entering wet-bulb temperature or dry bulb temperature upon selection (C) ewt = water entering temperature seen by the condenser (C)"
                    },
                    "speed_1_total_wh_capacity_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
                    },
                    "speed_1_total_wh_capacity_function_of_water_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used quadratic curve = a + b*ffw + c*ffw**2 cubic curve = a + b*ffw + c*ffw**2 + d*ffw**3 ffw = Fraction of the full load Water Flow"
                    },
                    "speed_1_cop_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used curve = a + b*wb + c*wb**2 + d*ewt + e*ewt**2 + f*wb*ewt wb = entering wet-bulb temperature or dry bulb temperature upon selection (C) ewt = water entering temperature seen by the condenser (C)"
                    },
                    "speed_1_cop_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
                    },
                    "speed_1_cop_function_of_water_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used quadratic curve = a + b*ffw + c*ffw**2 cubic curve = a + b*ffw + c*ffw**2 + d*ffw**3 ffw = Fraction of the full load Water Flow"
                    },
                    "rated_water_heating_capacity_at_speed_2": {
                        "type": "number",
                        "units": "W",
                        "exclusiveMinimum": 0.0,
                        "note": "Heating capacity at the rated inlet air temperatures, rated condenser inlet water temperature, rated air flow rate, and rated water flow rate. Can optionally include condenser pump heat."
                    },
                    "rated_water_heating_cop_at_speed_2": {
                        "type": "number",
                        "units": "W/W",
                        "exclusiveMinimum": 0.0,
                        "default": 3.2,
                        "note": "Heating coefficient of performance at the rated inlet air and water temperatures, rated condenser inlet water temperature, rated air flow rate, and rated water flow rate. Can optionally include condenser pump power and evaporator fan power (see fields below)."
                    },
                    "rated_sensible_heat_ratio_at_speed_2": {
                        "type": "number",
                        "minimum": 0.5,
                        "maximum": 1.0,
                        "default": 0.85,
                        "note": "Gross air-side sensible heat ratio at the rated inlet air temperatures, rated condenser inlet water temperature, rated air flow rate, and rated water flow rate. Sensible heat ratio equals gross sensible cooling capacity divided by gross total cooling capacity. Rated SHR (gross) should not include evaporator fan heat, only sensible cooling and dehumidification by the coil alone."
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
                    "speed_2_reference_unit_water_pump_input_power_at_rated_conditions": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0
                    },
                    "speed_2_total_wh_capacity_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used curve = a + b*wb + c*wb**2 + d*ewt + e*ewt**2 + f*wb*ewt wb = entering wet-bulb temperature or dry bulb temperature upon selection (C) ewt = water entering temperature seen by the condenser (C)"
                    },
                    "speed_2_total_wh_capacity_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
                    },
                    "speed_2_total_wh_capacity_function_of_water_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used quadratic curve = a + b*ffw + c*ffw**2 cubic curve = a + b*ffw + c*ffw**2 + d*ffw**3 ffw = Fraction of the full load Water Flow"
                    },
                    "speed_2_cop_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used curve = a + b*wb + c*wb**2 + d*ewt + e*ewt**2 + f*wb*ewt wb = entering wet-bulb temperature or dry bulb temperature upon selection (C) ewt = water entering temperature seen by the condenser (C)"
                    },
                    "speed_2_cop_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
                    },
                    "speed_2_cop_function_of_water_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used quadratic curve = a + b*ffw + c*ffw**2 cubic curve = a + b*ffw + c*ffw**2 + d*ffw**3 ffw = Fraction of the full load Water Flow"
                    },
                    "rated_water_heating_capacity_at_speed_3": {
                        "type": "number",
                        "units": "W",
                        "exclusiveMinimum": 0.0,
                        "note": "Heating capacity at the rated inlet air temperatures, rated condenser inlet water temperature, rated air flow rate, and rated water flow rate. Can optionally include condenser pump heat."
                    },
                    "rated_water_heating_cop_at_speed_3": {
                        "type": "number",
                        "units": "W/W",
                        "exclusiveMinimum": 0.0,
                        "default": 3.2,
                        "note": "Heating coefficient of performance at the rated inlet air and water temperatures, rated condenser inlet water temperature, rated air flow rate, and rated water flow rate. Can optionally include condenser pump power and evaporator fan power (see fields below)."
                    },
                    "rated_sensible_heat_ratio_at_speed_3": {
                        "type": "number",
                        "minimum": 0.5,
                        "maximum": 1.0,
                        "default": 0.85,
                        "note": "Gross air-side sensible heat ratio at the rated inlet air temperatures, rated condenser inlet water temperature, rated air flow rate, and rated water flow rate. Sensible heat ratio equals gross sensible cooling capacity divided by gross total cooling capacity. Rated SHR (gross) should not include evaporator fan heat, only sensible cooling and dehumidification by the coil alone."
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
                    "speed_3_reference_unit_water_pump_input_power_at_rated_conditions": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0
                    },
                    "speed_3_total_wh_capacity_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used curve = a + b*wb + c*wb**2 + d*ewt + e*ewt**2 + f*wb*ewt wb = entering wet-bulb temperature or dry bulb temperature upon selection (C) ewt = water entering temperature seen by the condenser (C)"
                    },
                    "speed_3_total_wh_capacity_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
                    },
                    "speed_3_total_wh_capacity_function_of_water_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used quadratic curve = a + b*ffw + c*ffw**2 cubic curve = a + b*ffw + c*ffw**2 + d*ffw**3 ffw = Fraction of the full load Water Flow"
                    },
                    "speed_3_cop_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used curve = a + b*wb + c*wb**2 + d*ewt + e*ewt**2 + f*wb*ewt wb = entering wet-bulb temperature or dry bulb temperature upon selection (C) ewt = water entering temperature seen by the condenser (C)"
                    },
                    "speed_3_cop_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
                    },
                    "speed_3_cop_function_of_water_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used quadratic curve = a + b*ffw + c*ffw**2 cubic curve = a + b*ffw + c*ffw**2 + d*ffw**3 ffw = Fraction of the full load Water Flow"
                    },
                    "rated_water_heating_capacity_at_speed_4": {
                        "type": "number",
                        "units": "W",
                        "exclusiveMinimum": 0.0,
                        "note": "Heating capacity at the rated inlet air temperatures, rated condenser inlet water temperature, rated air flow rate, and rated water flow rate. Can optionally include condenser pump heat."
                    },
                    "rated_water_heating_cop_at_speed_4": {
                        "type": "number",
                        "units": "W/W",
                        "exclusiveMinimum": 0.0,
                        "default": 3.2,
                        "note": "Heating coefficient of performance at the rated inlet air and water temperatures, rated condenser inlet water temperature, rated air flow rate, and rated water flow rate. Can optionally include condenser pump power and evaporator fan power (see fields below)."
                    },
                    "rated_sensible_heat_ratio_at_speed_4": {
                        "type": "number",
                        "minimum": 0.5,
                        "maximum": 1.0,
                        "default": 0.85,
                        "note": "Gross air-side sensible heat ratio at the rated inlet air temperatures, rated condenser inlet water temperature, rated air flow rate, and rated water flow rate. Sensible heat ratio equals gross sensible cooling capacity divided by gross total cooling capacity. Rated SHR (gross) should not include evaporator fan heat, only sensible cooling and dehumidification by the coil alone."
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
                    "speed_4_reference_unit_water_pump_input_power_at_rated_conditions": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0
                    },
                    "speed_4_total_wh_capacity_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used curve = a + b*wb + c*wb**2 + d*ewt + e*ewt**2 + f*wb*ewt wb = entering wet-bulb temperature or dry bulb temperature upon selection (C) ewt = water entering temperature seen by the condenser (C)"
                    },
                    "speed_4_total_wh_capacity_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
                    },
                    "speed_4_total_wh_capacity_function_of_water_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used quadratic curve = a + b*ffw + c*ffw**2 cubic curve = a + b*ffw + c*ffw**2 + d*ffw**3 ffw = Fraction of the full load Water Flow"
                    },
                    "speed_4_cop_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used curve = a + b*wb + c*wb**2 + d*ewt + e*ewt**2 + f*wb*ewt wb = entering wet-bulb temperature or dry bulb temperature upon selection (C) ewt = water entering temperature seen by the condenser (C)"
                    },
                    "speed_4_cop_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
                    },
                    "speed_4_cop_function_of_water_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used quadratic curve = a + b*ffw + c*ffw**2 cubic curve = a + b*ffw + c*ffw**2 + d*ffw**3 ffw = Fraction of the full load Water Flow"
                    },
                    "rated_water_heating_capacity_at_speed_5": {
                        "type": "number",
                        "units": "W",
                        "exclusiveMinimum": 0.0,
                        "note": "Heating capacity at the rated inlet air temperatures, rated condenser inlet water temperature, rated air flow rate, and rated water flow rate. Can optionally include condenser pump heat."
                    },
                    "rated_water_heating_cop_at_speed_5": {
                        "type": "number",
                        "units": "W/W",
                        "exclusiveMinimum": 0.0,
                        "default": 3.2,
                        "note": "Heating coefficient of performance at the rated inlet air and water temperatures, rated condenser inlet water temperature, rated air flow rate, and rated water flow rate. Can optionally include condenser pump power and evaporator fan power (see fields below)."
                    },
                    "rated_sensible_heat_ratio_at_speed_5": {
                        "type": "number",
                        "minimum": 0.5,
                        "maximum": 1.0,
                        "default": 0.85,
                        "note": "Gross air-side sensible heat ratio at the rated inlet air temperatures, rated condenser inlet water temperature, rated air flow rate, and rated water flow rate. Sensible heat ratio equals gross sensible cooling capacity divided by gross total cooling capacity. Rated SHR (gross) should not include evaporator fan heat, only sensible cooling and dehumidification by the coil alone."
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
                    "speed_5_reference_unit_water_pump_input_power_at_rated_conditions": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0
                    },
                    "speed_5_total_wh_capacity_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used curve = a + b*wb + c*wb**2 + d*ewt + e*ewt**2 + f*wb*ewt wb = entering wet-bulb temperature or dry bulb temperature upon selection (C) ewt = water entering temperature seen by the condenser (C)"
                    },
                    "speed_5_total_wh_capacity_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
                    },
                    "speed_5_total_wh_capacity_function_of_water_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used quadratic curve = a + b*ffw + c*ffw**2 cubic curve = a + b*ffw + c*ffw**2 + d*ffw**3 ffw = Fraction of the full load Water Flow"
                    },
                    "speed_5_cop_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used curve = a + b*wb + c*wb**2 + d*ewt + e*ewt**2 + f*wb*ewt wb = entering wet-bulb temperature or dry bulb temperature upon selection (C) ewt = water entering temperature seen by the condenser (C)"
                    },
                    "speed_5_cop_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
                    },
                    "speed_5_cop_function_of_water_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used quadratic curve = a + b*ffw + c*ffw**2 cubic curve = a + b*ffw + c*ffw**2 + d*ffw**3 ffw = Fraction of the full load Water Flow"
                    },
                    "rated_water_heating_capacity_at_speed_6": {
                        "type": "number",
                        "units": "W",
                        "exclusiveMinimum": 0.0,
                        "note": "Heating capacity at the rated inlet air temperatures, rated condenser inlet water temperature, rated air flow rate, and rated water flow rate. Can optionally include condenser pump heat."
                    },
                    "rated_water_heating_cop_at_speed_6": {
                        "type": "number",
                        "units": "W/W",
                        "exclusiveMinimum": 0.0,
                        "default": 3.2,
                        "note": "Heating coefficient of performance at the rated inlet air and water temperatures, rated condenser inlet water temperature, rated air flow rate, and rated water flow rate. Can optionally include condenser pump power and evaporator fan power (see fields below)."
                    },
                    "rated_sensible_heat_ratio_at_speed_6": {
                        "type": "number",
                        "minimum": 0.5,
                        "maximum": 1.0,
                        "default": 0.85,
                        "note": "Gross air-side sensible heat ratio at the rated inlet air temperatures, rated condenser inlet water temperature, rated air flow rate, and rated water flow rate. Sensible heat ratio equals gross sensible cooling capacity divided by gross total cooling capacity. Rated SHR (gross) should not include evaporator fan heat, only sensible cooling and dehumidification by the coil alone."
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
                    "speed_6_reference_unit_water_pump_input_power_at_rated_conditions": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0
                    },
                    "speed_6_total_wh_capacity_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used curve = a + b*wb + c*wb**2 + d*ewt + e*ewt**2 + f*wb*ewt wb = entering wet-bulb temperature or dry bulb temperature upon selection (C) ewt = water entering temperature seen by the condenser (C)"
                    },
                    "speed_6_total_wh_capacity_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
                    },
                    "speed_6_total_wh_capacity_function_of_water_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used quadratic curve = a + b*ffw + c*ffw**2 cubic curve = a + b*ffw + c*ffw**2 + d*ffw**3 ffw = Fraction of the full load Water Flow"
                    },
                    "speed_6_cop_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used curve = a + b*wb + c*wb**2 + d*ewt + e*ewt**2 + f*wb*ewt wb = entering wet-bulb temperature or dry bulb temperature upon selection (C) ewt = water entering temperature seen by the condenser (C)"
                    },
                    "speed_6_cop_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
                    },
                    "speed_6_cop_function_of_water_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used quadratic curve = a + b*ffw + c*ffw**2 cubic curve = a + b*ffw + c*ffw**2 + d*ffw**3 ffw = Fraction of the full load Water Flow"
                    },
                    "rated_water_heating_capacity_at_speed_7": {
                        "type": "number",
                        "units": "W",
                        "exclusiveMinimum": 0.0,
                        "note": "Heating capacity at the rated inlet air temperatures, rated condenser inlet water temperature, rated air flow rate, and rated water flow rate. Can optionally include condenser pump heat."
                    },
                    "rated_water_heating_cop_at_speed_7": {
                        "type": "number",
                        "units": "W/W",
                        "exclusiveMinimum": 0.0,
                        "default": 3.2,
                        "note": "Heating coefficient of performance at the rated inlet air and water temperatures, rated condenser inlet water temperature, rated air flow rate, and rated water flow rate. Can optionally include condenser pump power and evaporator fan power (see fields below)."
                    },
                    "rated_sensible_heat_ratio_at_speed_7": {
                        "type": "number",
                        "minimum": 0.5,
                        "maximum": 1.0,
                        "default": 0.85,
                        "note": "Gross air-side sensible heat ratio at the rated inlet air temperatures, rated condenser inlet water temperature, rated air flow rate, and rated water flow rate. Sensible heat ratio equals gross sensible cooling capacity divided by gross total cooling capacity. Rated SHR (gross) should not include evaporator fan heat, only sensible cooling and dehumidification by the coil alone."
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
                    "speed_7_reference_unit_water_pump_input_power_at_rated_conditions": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0
                    },
                    "speed_7_total_wh_capacity_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used curve = a + b*wb + c*wb**2 + d*ewt + e*ewt**2 + f*wb*ewt wb = entering wet-bulb temperature or dry bulb temperature upon selection (C) ewt = water entering temperature seen by the condenser (C)"
                    },
                    "speed_7_total_wh_capacity_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
                    },
                    "speed_7_total_wh_capacity_function_of_water_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used quadratic curve = a + b*ffw + c*ffw**2 cubic curve = a + b*ffw + c*ffw**2 + d*ffw**3 ffw = Fraction of the full load Water Flow"
                    },
                    "speed_7_cop_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used curve = a + b*wb + c*wb**2 + d*ewt + e*ewt**2 + f*wb*ewt wb = entering wet-bulb temperature or dry bulb temperature upon selection (C) ewt = water entering temperature seen by the condenser (C)"
                    },
                    "speed_7_cop_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
                    },
                    "speed_7_cop_function_of_water_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used quadratic curve = a + b*ffw + c*ffw**2 cubic curve = a + b*ffw + c*ffw**2 + d*ffw**3 ffw = Fraction of the full load Water Flow"
                    },
                    "rated_water_heating_capacity_at_speed_8": {
                        "type": "number",
                        "units": "W",
                        "exclusiveMinimum": 0.0,
                        "note": "Heating capacity at the rated inlet air temperatures, rated condenser inlet water temperature, rated air flow rate, and rated water flow rate. Can optionally include condenser pump heat."
                    },
                    "rated_water_heating_cop_at_speed_8": {
                        "type": "number",
                        "units": "W/W",
                        "exclusiveMinimum": 0.0,
                        "default": 3.2,
                        "note": "Heating coefficient of performance at the rated inlet air and water temperatures, rated condenser inlet water temperature, rated air flow rate, and rated water flow rate. Can optionally include condenser pump power and evaporator fan power (see fields below)."
                    },
                    "rated_sensible_heat_ratio_at_speed_8": {
                        "type": "number",
                        "minimum": 0.5,
                        "maximum": 1.0,
                        "default": 0.85,
                        "note": "Gross air-side sensible heat ratio at the rated inlet air temperatures, rated condenser inlet water temperature, rated air flow rate, and rated water flow rate. Sensible heat ratio equals gross sensible cooling capacity divided by gross total cooling capacity. Rated SHR (gross) should not include evaporator fan heat, only sensible cooling and dehumidification by the coil alone."
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
                    "speed_8_reference_unit_water_pump_input_power_at_rated_conditions": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0
                    },
                    "speed_8_total_wh_capacity_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used curve = a + b*wb + c*wb**2 + d*ewt + e*ewt**2 + f*wb*ewt wb = entering wet-bulb temperature or dry bulb temperature upon selection (C) ewt = water entering temperature seen by the condenser (C)"
                    },
                    "speed_8_total_wh_capacity_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
                    },
                    "speed_8_total_wh_capacity_function_of_water_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used quadratic curve = a + b*ffw + c*ffw**2 cubic curve = a + b*ffw + c*ffw**2 + d*ffw**3 ffw = Fraction of the full load Water Flow"
                    },
                    "speed_8_cop_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used curve = a + b*wb + c*wb**2 + d*ewt + e*ewt**2 + f*wb*ewt wb = entering wet-bulb temperature or dry bulb temperature upon selection (C) ewt = water entering temperature seen by the condenser (C)"
                    },
                    "speed_8_cop_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
                    },
                    "speed_8_cop_function_of_water_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used quadratic curve = a + b*ffw + c*ffw**2 cubic curve = a + b*ffw + c*ffw**2 + d*ffw**3 ffw = Fraction of the full load Water Flow"
                    },
                    "rated_water_heating_capacity_at_speed_9": {
                        "type": "number",
                        "units": "W",
                        "exclusiveMinimum": 0.0,
                        "note": "Heating capacity at the rated inlet air temperatures, rated condenser inlet water temperature, rated air flow rate, and rated water flow rate. Can optionally include condenser pump heat."
                    },
                    "rated_water_heating_cop_at_speed_9": {
                        "type": "number",
                        "units": "W/W",
                        "exclusiveMinimum": 0.0,
                        "default": 3.2,
                        "note": "Heating coefficient of performance at the rated inlet air and water temperatures, rated condenser inlet water temperature, rated air flow rate, and rated water flow rate. Can optionally include condenser pump power and evaporator fan power (see fields below)."
                    },
                    "rated_sensible_heat_ratio_at_speed_9": {
                        "type": "number",
                        "minimum": 0.5,
                        "maximum": 1.0,
                        "default": 0.85,
                        "note": "Gross air-side sensible heat ratio at the rated inlet air temperatures, rated condenser inlet water temperature, rated air flow rate, and rated water flow rate. Sensible heat ratio equals gross sensible cooling capacity divided by gross total cooling capacity. Rated SHR (gross) should not include evaporator fan heat, only sensible cooling and dehumidification by the coil alone."
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
                    "speed_9_reference_unit_water_pump_input_power_at_rated_conditions": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0
                    },
                    "speed_9_total_wh_capacity_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used curve = a + b*wb + c*wb**2 + d*ewt + e*ewt**2 + f*wb*ewt wb = entering wet-bulb temperature or dry bulb temperature upon selection (C) ewt = water entering temperature seen by the condenser (C)"
                    },
                    "speed_9_total_wh_capacity_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
                    },
                    "speed_9_total_wh_capacity_function_of_water_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used quadratic curve = a + b*ffw + c*ffw**2 cubic curve = a + b*ffw + c*ffw**2 + d*ffw**3 ffw = Fraction of the full load Water Flow"
                    },
                    "speed_9_cop_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used curve = a + b*wb + c*wb**2 + d*ewt + e*ewt**2 + f*wb*ewt wb = entering wet-bulb temperature or dry bulb temperature upon selection (C) ewt = water entering temperature seen by the condenser (C)"
                    },
                    "speed_9_cop_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
                    },
                    "speed_9_cop_function_of_water_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used quadratic curve = a + b*ffw + c*ffw**2 cubic curve = a + b*ffw + c*ffw**2 + d*ffw**3 ffw = Fraction of the full load Water Flow"
                    },
                    "rated_water_heating_capacity_at_speed_10": {
                        "type": "number",
                        "units": "W",
                        "exclusiveMinimum": 0.0,
                        "note": "Heating capacity at the rated inlet air temperatures, rated condenser inlet water temperature, rated air flow rate, and rated water flow rate. Can optionally include condenser pump heat."
                    },
                    "rated_water_heating_cop_at_speed_10": {
                        "type": "number",
                        "units": "W/W",
                        "exclusiveMinimum": 0.0,
                        "default": 3.2,
                        "note": "Heating coefficient of performance at the rated inlet air and water temperatures, rated condenser inlet water temperature, rated air flow rate, and rated water flow rate. Can optionally include condenser pump power and evaporator fan power (see fields below)."
                    },
                    "rated_sensible_heat_ratio_at_speed_10": {
                        "type": "number",
                        "minimum": 0.5,
                        "maximum": 1.0,
                        "default": 0.85,
                        "note": "Gross air-side sensible heat ratio at the rated inlet air temperatures, rated condenser inlet water temperature, rated air flow rate, and rated water flow rate. Sensible heat ratio equals gross sensible cooling capacity divided by gross total cooling capacity. Rated SHR (gross) should not include evaporator fan heat, only sensible cooling and dehumidification by the coil alone."
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
                    "speed_10_reference_unit_water_pump_input_power_at_rated_conditions": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0
                    },
                    "speed_10_total_wh_capacity_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used curve = a + b*wb + c*wb**2 + d*ewt + e*ewt**2 + f*wb*ewt wb = entering wet-bulb temperature or dry bulb temperature upon selection (C) ewt = water entering temperature seen by the condenser (C)"
                    },
                    "speed_10_total_wh_capacity_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
                    },
                    "speed_10_total_wh_capacity_function_of_water_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used quadratic curve = a + b*ffw + c*ffw**2 cubic curve = a + b*ffw + c*ffw**2 + d*ffw**3 ffw = Fraction of the full load Water Flow"
                    },
                    "speed_10_cop_function_of_temperature_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used curve = a + b*wb + c*wb**2 + d*ewt + e*ewt**2 + f*wb*ewt wb = entering wet-bulb temperature or dry bulb temperature upon selection (C) ewt = water entering temperature seen by the condenser (C)"
                    },
                    "speed_10_cop_function_of_air_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used quadratic curve = a + b*ffa + c*ffa**2 cubic curve = a + b*ffa + c*ffa**2 + d*ffa**3 ffa = Fraction of the full load Air Flow"
                    },
                    "speed_10_cop_function_of_water_flow_fraction_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ],
                        "note": "Table:Lookup object can also be used quadratic curve = a + b*ffw + c*ffw**2 cubic curve = a + b*ffw + c*ffw**2 + d*ffw**3 ffw = Fraction of the full load Water Flow"
                    }
                },
                "required": [
                    "rated_water_heating_capacity",
                    "evaporator_air_inlet_node_name",
                    "evaporator_air_outlet_node_name",
                    "condenser_water_inlet_node_name",
                    "condenser_water_outlet_node_name",
                    "rated_water_heating_capacity_at_speed_1",
                    "speed_1_reference_unit_rated_air_flow_rate",
                    "speed_1_reference_unit_rated_water_flow_rate",
                    "speed_1_reference_unit_water_pump_input_power_at_rated_conditions",
                    "speed_1_total_wh_capacity_function_of_temperature_curve_name",
                    "speed_1_total_wh_capacity_function_of_air_flow_fraction_curve_name",
                    "speed_1_total_wh_capacity_function_of_water_flow_fraction_curve_name",
                    "speed_1_cop_function_of_temperature_curve_name",
                    "speed_1_cop_function_of_air_flow_fraction_curve_name",
                    "speed_1_cop_function_of_water_flow_fraction_curve_name"
                ]
            }
        },
        "group": "Coils",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "HeatPumpWaterHeaterDXCoilsVariableSpeed"
            ],
            "note": "Unique name for this instance of a variable-speed heat pump water heater DX coil."
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
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
                "rated_water_heating_capacity": {
                    "field_name": "Rated Water Heating Capacity",
                    "field_type": "n"
                },
                "rated_evaporator_inlet_air_dry_bulb_temperature": {
                    "field_name": "Rated Evaporator Inlet Air Dry-Bulb Temperature",
                    "field_type": "n"
                },
                "rated_evaporator_inlet_air_wet_bulb_temperature": {
                    "field_name": "Rated Evaporator Inlet Air Wet-Bulb Temperature",
                    "field_type": "n"
                },
                "rated_condenser_inlet_water_temperature": {
                    "field_name": "Rated Condenser Inlet Water Temperature",
                    "field_type": "n"
                },
                "rated_evaporator_air_flow_rate": {
                    "field_name": "Rated Evaporator Air Flow Rate",
                    "field_type": "n"
                },
                "rated_condenser_water_flow_rate": {
                    "field_name": "Rated Condenser Water Flow Rate",
                    "field_type": "n"
                },
                "evaporator_fan_power_included_in_rated_cop": {
                    "field_name": "Evaporator Fan Power Included in Rated COP",
                    "field_type": "a"
                },
                "condenser_pump_power_included_in_rated_cop": {
                    "field_name": "Condenser Pump Power Included in Rated COP",
                    "field_type": "a"
                },
                "condenser_pump_heat_included_in_rated_heating_capacity_and_rated_cop": {
                    "field_name": "Condenser Pump Heat Included in Rated Heating Capacity and Rated COP",
                    "field_type": "a"
                },
                "fraction_of_condenser_pump_heat_to_water": {
                    "field_name": "Fraction of Condenser Pump Heat to Water",
                    "field_type": "n"
                },
                "evaporator_air_inlet_node_name": {
                    "field_name": "Evaporator Air Inlet Node Name",
                    "field_type": "a"
                },
                "evaporator_air_outlet_node_name": {
                    "field_name": "Evaporator Air Outlet Node Name",
                    "field_type": "a"
                },
                "condenser_water_inlet_node_name": {
                    "field_name": "Condenser Water Inlet Node Name",
                    "field_type": "a"
                },
                "condenser_water_outlet_node_name": {
                    "field_name": "Condenser Water Outlet Node Name",
                    "field_type": "a"
                },
                "crankcase_heater_capacity": {
                    "field_name": "Crankcase Heater Capacity",
                    "field_type": "n"
                },
                "maximum_ambient_temperature_for_crankcase_heater_operation": {
                    "field_name": "Maximum Ambient Temperature for Crankcase Heater Operation",
                    "field_type": "n"
                },
                "evaporator_air_temperature_type_for_curve_objects": {
                    "field_name": "Evaporator Air Temperature Type for Curve Objects",
                    "field_type": "a"
                },
                "part_load_fraction_correlation_curve_name": {
                    "field_name": "Part Load Fraction Correlation Curve Name",
                    "field_type": "a"
                },
                "rated_water_heating_capacity_at_speed_1": {
                    "field_name": "Rated Water Heating Capacity at Speed 1",
                    "field_type": "n"
                },
                "rated_water_heating_cop_at_speed_1": {
                    "field_name": "Rated Water Heating COP at Speed 1",
                    "field_type": "n"
                },
                "rated_sensible_heat_ratio_at_speed_1": {
                    "field_name": "Rated Sensible Heat Ratio at Speed 1",
                    "field_type": "n"
                },
                "speed_1_reference_unit_rated_air_flow_rate": {
                    "field_name": "Speed 1 Reference Unit Rated Air Flow Rate",
                    "field_type": "n"
                },
                "speed_1_reference_unit_rated_water_flow_rate": {
                    "field_name": "Speed 1 Reference Unit Rated Water Flow Rate",
                    "field_type": "n"
                },
                "speed_1_reference_unit_water_pump_input_power_at_rated_conditions": {
                    "field_name": "Speed 1 Reference Unit Water Pump Input Power At Rated Conditions",
                    "field_type": "n"
                },
                "speed_1_total_wh_capacity_function_of_temperature_curve_name": {
                    "field_name": "Speed 1 Total WH Capacity Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_1_total_wh_capacity_function_of_air_flow_fraction_curve_name": {
                    "field_name": "Speed 1 Total WH Capacity Function of Air Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "speed_1_total_wh_capacity_function_of_water_flow_fraction_curve_name": {
                    "field_name": "Speed 1 Total WH Capacity Function of Water Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "speed_1_cop_function_of_temperature_curve_name": {
                    "field_name": "Speed 1 COP Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_1_cop_function_of_air_flow_fraction_curve_name": {
                    "field_name": "Speed 1 COP Function of Air Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "speed_1_cop_function_of_water_flow_fraction_curve_name": {
                    "field_name": "Speed 1 COP Function of Water Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "rated_water_heating_capacity_at_speed_2": {
                    "field_name": "Rated Water Heating Capacity at Speed 2",
                    "field_type": "n"
                },
                "rated_water_heating_cop_at_speed_2": {
                    "field_name": "Rated Water Heating COP at Speed 2",
                    "field_type": "n"
                },
                "rated_sensible_heat_ratio_at_speed_2": {
                    "field_name": "Rated Sensible Heat Ratio at Speed 2",
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
                "speed_2_reference_unit_water_pump_input_power_at_rated_conditions": {
                    "field_name": "Speed 2 Reference Unit Water Pump Input Power At Rated Conditions",
                    "field_type": "n"
                },
                "speed_2_total_wh_capacity_function_of_temperature_curve_name": {
                    "field_name": "Speed 2 Total WH Capacity Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_2_total_wh_capacity_function_of_air_flow_fraction_curve_name": {
                    "field_name": "Speed 2 Total WH Capacity Function of Air Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "speed_2_total_wh_capacity_function_of_water_flow_fraction_curve_name": {
                    "field_name": "Speed 2 Total WH Capacity Function of Water Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "speed_2_cop_function_of_temperature_curve_name": {
                    "field_name": "Speed 2 COP Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_2_cop_function_of_air_flow_fraction_curve_name": {
                    "field_name": "Speed 2 COP Function of Air Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "speed_2_cop_function_of_water_flow_fraction_curve_name": {
                    "field_name": "Speed 2 COP Function of Water Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "rated_water_heating_capacity_at_speed_3": {
                    "field_name": "Rated Water Heating Capacity at speed 3",
                    "field_type": "n"
                },
                "rated_water_heating_cop_at_speed_3": {
                    "field_name": "Rated Water Heating COP at Speed 3",
                    "field_type": "n"
                },
                "rated_sensible_heat_ratio_at_speed_3": {
                    "field_name": "Rated Sensible Heat Ratio at Speed 3",
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
                "speed_3_reference_unit_water_pump_input_power_at_rated_conditions": {
                    "field_name": "Speed 3 Reference Unit Water Pump Input Power At Rated Conditions",
                    "field_type": "n"
                },
                "speed_3_total_wh_capacity_function_of_temperature_curve_name": {
                    "field_name": "Speed 3 Total WH Capacity Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_3_total_wh_capacity_function_of_air_flow_fraction_curve_name": {
                    "field_name": "Speed 3 Total WH Capacity Function of Air Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "speed_3_total_wh_capacity_function_of_water_flow_fraction_curve_name": {
                    "field_name": "Speed 3 Total WH Capacity Function of Water Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "speed_3_cop_function_of_temperature_curve_name": {
                    "field_name": "Speed 3 COP Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_3_cop_function_of_air_flow_fraction_curve_name": {
                    "field_name": "Speed 3 COP Function of Air Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "speed_3_cop_function_of_water_flow_fraction_curve_name": {
                    "field_name": "Speed 3 COP Function of Water Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "rated_water_heating_capacity_at_speed_4": {
                    "field_name": "Rated Water Heating Capacity at Speed 4",
                    "field_type": "n"
                },
                "rated_water_heating_cop_at_speed_4": {
                    "field_name": "Rated Water Heating COP at Speed 4",
                    "field_type": "n"
                },
                "rated_sensible_heat_ratio_at_speed_4": {
                    "field_name": "Rated Sensible Heat Ratio at Speed 4",
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
                "speed_4_reference_unit_water_pump_input_power_at_rated_conditions": {
                    "field_name": "Speed 4 Reference Unit Water Pump Input Power At Rated Conditions",
                    "field_type": "n"
                },
                "speed_4_total_wh_capacity_function_of_temperature_curve_name": {
                    "field_name": "Speed 4 Total WH Capacity Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_4_total_wh_capacity_function_of_air_flow_fraction_curve_name": {
                    "field_name": "Speed 4 Total WH Capacity Function of Air Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "speed_4_total_wh_capacity_function_of_water_flow_fraction_curve_name": {
                    "field_name": "Speed 4 Total WH Capacity Function of Water Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "speed_4_cop_function_of_temperature_curve_name": {
                    "field_name": "Speed 4 COP Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_4_cop_function_of_air_flow_fraction_curve_name": {
                    "field_name": "Speed 4 COP Function of Air Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "speed_4_cop_function_of_water_flow_fraction_curve_name": {
                    "field_name": "Speed 4 COP Function of Water Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "rated_water_heating_capacity_at_speed_5": {
                    "field_name": "Rated Water Heating Capacity at Speed 5",
                    "field_type": "n"
                },
                "rated_water_heating_cop_at_speed_5": {
                    "field_name": "Rated Water Heating COP at Speed 5",
                    "field_type": "n"
                },
                "rated_sensible_heat_ratio_at_speed_5": {
                    "field_name": "Rated Sensible Heat Ratio at Speed 5",
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
                "speed_5_reference_unit_water_pump_input_power_at_rated_conditions": {
                    "field_name": "Speed 5 Reference Unit Water Pump Input Power At Rated Conditions",
                    "field_type": "n"
                },
                "speed_5_total_wh_capacity_function_of_temperature_curve_name": {
                    "field_name": "Speed 5 Total WH Capacity Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_5_total_wh_capacity_function_of_air_flow_fraction_curve_name": {
                    "field_name": "Speed 5 Total WH Capacity Function of Air Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "speed_5_total_wh_capacity_function_of_water_flow_fraction_curve_name": {
                    "field_name": "Speed 5 Total WH Capacity Function of Water Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "speed_5_cop_function_of_temperature_curve_name": {
                    "field_name": "Speed 5 COP Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_5_cop_function_of_air_flow_fraction_curve_name": {
                    "field_name": "Speed 5 COP Function of Air Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "speed_5_cop_function_of_water_flow_fraction_curve_name": {
                    "field_name": "Speed 5 COP Function of Water Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "rated_water_heating_capacity_at_speed_6": {
                    "field_name": "Rated Water Heating Capacity at Speed 6",
                    "field_type": "n"
                },
                "rated_water_heating_cop_at_speed_6": {
                    "field_name": "Rated Water Heating COP at Speed 6",
                    "field_type": "n"
                },
                "rated_sensible_heat_ratio_at_speed_6": {
                    "field_name": "Rated Sensible Heat Ratio at Speed 6",
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
                "speed_6_reference_unit_water_pump_input_power_at_rated_conditions": {
                    "field_name": "Speed 6 Reference Unit Water Pump Input Power At Rated Conditions",
                    "field_type": "n"
                },
                "speed_6_total_wh_capacity_function_of_temperature_curve_name": {
                    "field_name": "Speed 6 Total WH Capacity Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_6_total_wh_capacity_function_of_air_flow_fraction_curve_name": {
                    "field_name": "Speed 6 Total WH Capacity Function of Air Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "speed_6_total_wh_capacity_function_of_water_flow_fraction_curve_name": {
                    "field_name": "Speed 6 Total WH Capacity Function of Water Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "speed_6_cop_function_of_temperature_curve_name": {
                    "field_name": "Speed 6 COP Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_6_cop_function_of_air_flow_fraction_curve_name": {
                    "field_name": "Speed 6 COP Function of Air Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "speed_6_cop_function_of_water_flow_fraction_curve_name": {
                    "field_name": "Speed 6 COP Function of Water Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "rated_water_heating_capacity_at_speed_7": {
                    "field_name": "Rated Water Heating Capacity at Speed 7",
                    "field_type": "n"
                },
                "rated_water_heating_cop_at_speed_7": {
                    "field_name": "Rated Water Heating COP at Speed 7",
                    "field_type": "n"
                },
                "rated_sensible_heat_ratio_at_speed_7": {
                    "field_name": "Rated Sensible Heat Ratio at Speed 7",
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
                "speed_7_reference_unit_water_pump_input_power_at_rated_conditions": {
                    "field_name": "Speed 7 Reference Unit Water Pump Input Power At Rated Conditions",
                    "field_type": "n"
                },
                "speed_7_total_wh_capacity_function_of_temperature_curve_name": {
                    "field_name": "Speed 7 Total WH Capacity Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_7_total_wh_capacity_function_of_air_flow_fraction_curve_name": {
                    "field_name": "Speed 7 Total WH Capacity Function of Air Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "speed_7_total_wh_capacity_function_of_water_flow_fraction_curve_name": {
                    "field_name": "Speed 7 Total WH Capacity Function of Water Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "speed_7_cop_function_of_temperature_curve_name": {
                    "field_name": "Speed 7 COP Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_7_cop_function_of_air_flow_fraction_curve_name": {
                    "field_name": "Speed 7 COP Function of Air Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "speed_7_cop_function_of_water_flow_fraction_curve_name": {
                    "field_name": "Speed 7 COP Function of Water Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "rated_water_heating_capacity_at_speed_8": {
                    "field_name": "Rated Water Heating Capacity at Speed 8",
                    "field_type": "n"
                },
                "rated_water_heating_cop_at_speed_8": {
                    "field_name": "Rated Water Heating COP at Speed 8",
                    "field_type": "n"
                },
                "rated_sensible_heat_ratio_at_speed_8": {
                    "field_name": "Rated Sensible Heat Ratio at Speed 8",
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
                "speed_8_reference_unit_water_pump_input_power_at_rated_conditions": {
                    "field_name": "Speed 8 Reference Unit Water Pump Input Power At Rated Conditions",
                    "field_type": "n"
                },
                "speed_8_total_wh_capacity_function_of_temperature_curve_name": {
                    "field_name": "Speed 8 Total WH Capacity Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_8_total_wh_capacity_function_of_air_flow_fraction_curve_name": {
                    "field_name": "Speed 8 Total WH Capacity Function of Air Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "speed_8_total_wh_capacity_function_of_water_flow_fraction_curve_name": {
                    "field_name": "Speed 8 Total WH Capacity Function of Water Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "speed_8_cop_function_of_temperature_curve_name": {
                    "field_name": "Speed 8 COP Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_8_cop_function_of_air_flow_fraction_curve_name": {
                    "field_name": "Speed 8 COP Function of Air Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "speed_8_cop_function_of_water_flow_fraction_curve_name": {
                    "field_name": "Speed 8 COP Function of Water Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "rated_water_heating_capacity_at_speed_9": {
                    "field_name": "Rated Water Heating Capacity at Speed 9",
                    "field_type": "n"
                },
                "rated_water_heating_cop_at_speed_9": {
                    "field_name": "Rated Water Heating COP at Speed 9",
                    "field_type": "n"
                },
                "rated_sensible_heat_ratio_at_speed_9": {
                    "field_name": "Rated Sensible Heat Ratio at Speed 9",
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
                "speed_9_reference_unit_water_pump_input_power_at_rated_conditions": {
                    "field_name": "Speed 9 Reference Unit Water Pump Input Power At Rated Conditions",
                    "field_type": "n"
                },
                "speed_9_total_wh_capacity_function_of_temperature_curve_name": {
                    "field_name": "Speed 9 Total WH Capacity Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_9_total_wh_capacity_function_of_air_flow_fraction_curve_name": {
                    "field_name": "Speed 9 Total WH Capacity Function of Air Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "speed_9_total_wh_capacity_function_of_water_flow_fraction_curve_name": {
                    "field_name": "Speed 9 Total WH Capacity Function of Water Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "speed_9_cop_function_of_temperature_curve_name": {
                    "field_name": "Speed 9 COP Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_9_cop_function_of_air_flow_fraction_curve_name": {
                    "field_name": "Speed 9 COP Function of Air Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "speed_9_cop_function_of_water_flow_fraction_curve_name": {
                    "field_name": "Speed 9 COP Function of Water Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "rated_water_heating_capacity_at_speed_10": {
                    "field_name": "Rated Water Heating Capacity at Speed 10",
                    "field_type": "n"
                },
                "rated_water_heating_cop_at_speed_10": {
                    "field_name": "Rated Water Heating COP at Speed 10",
                    "field_type": "n"
                },
                "rated_sensible_heat_ratio_at_speed_10": {
                    "field_name": "Rated Sensible Heat Ratio at Speed 10",
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
                "speed_10_reference_unit_water_pump_input_power_at_rated_conditions": {
                    "field_name": "Speed 10 Reference Unit Water Pump Input Power At Rated Conditions",
                    "field_type": "n"
                },
                "speed_10_total_wh_capacity_function_of_temperature_curve_name": {
                    "field_name": "Speed 10 Total WH Capacity Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_10_total_wh_capacity_function_of_air_flow_fraction_curve_name": {
                    "field_name": "Speed 10 Total WH Capacity Function of Air Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "speed_10_total_wh_capacity_function_of_water_flow_fraction_curve_name": {
                    "field_name": "Speed 10 Total WH Capacity Function of Water Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "speed_10_cop_function_of_temperature_curve_name": {
                    "field_name": "Speed 10 COP Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "speed_10_cop_function_of_air_flow_fraction_curve_name": {
                    "field_name": "Speed 10 COP Function of Air Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "speed_10_cop_function_of_water_flow_fraction_curve_name": {
                    "field_name": "Speed 10 COP Function of Water Flow Fraction Curve Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "number_of_speeds",
                "nominal_speed_level",
                "rated_water_heating_capacity",
                "rated_evaporator_inlet_air_dry_bulb_temperature",
                "rated_evaporator_inlet_air_wet_bulb_temperature",
                "rated_condenser_inlet_water_temperature",
                "rated_evaporator_air_flow_rate",
                "rated_condenser_water_flow_rate",
                "evaporator_fan_power_included_in_rated_cop",
                "condenser_pump_power_included_in_rated_cop",
                "condenser_pump_heat_included_in_rated_heating_capacity_and_rated_cop",
                "fraction_of_condenser_pump_heat_to_water",
                "evaporator_air_inlet_node_name",
                "evaporator_air_outlet_node_name",
                "condenser_water_inlet_node_name",
                "condenser_water_outlet_node_name",
                "crankcase_heater_capacity",
                "maximum_ambient_temperature_for_crankcase_heater_operation",
                "evaporator_air_temperature_type_for_curve_objects",
                "part_load_fraction_correlation_curve_name",
                "rated_water_heating_capacity_at_speed_1",
                "rated_water_heating_cop_at_speed_1",
                "rated_sensible_heat_ratio_at_speed_1",
                "speed_1_reference_unit_rated_air_flow_rate",
                "speed_1_reference_unit_rated_water_flow_rate",
                "speed_1_reference_unit_water_pump_input_power_at_rated_conditions",
                "speed_1_total_wh_capacity_function_of_temperature_curve_name",
                "speed_1_total_wh_capacity_function_of_air_flow_fraction_curve_name",
                "speed_1_total_wh_capacity_function_of_water_flow_fraction_curve_name",
                "speed_1_cop_function_of_temperature_curve_name",
                "speed_1_cop_function_of_air_flow_fraction_curve_name",
                "speed_1_cop_function_of_water_flow_fraction_curve_name",
                "rated_water_heating_capacity_at_speed_2",
                "rated_water_heating_cop_at_speed_2",
                "rated_sensible_heat_ratio_at_speed_2",
                "speed_2_reference_unit_rated_air_flow_rate",
                "speed_2_reference_unit_rated_water_flow_rate",
                "speed_2_reference_unit_water_pump_input_power_at_rated_conditions",
                "speed_2_total_wh_capacity_function_of_temperature_curve_name",
                "speed_2_total_wh_capacity_function_of_air_flow_fraction_curve_name",
                "speed_2_total_wh_capacity_function_of_water_flow_fraction_curve_name",
                "speed_2_cop_function_of_temperature_curve_name",
                "speed_2_cop_function_of_air_flow_fraction_curve_name",
                "speed_2_cop_function_of_water_flow_fraction_curve_name",
                "rated_water_heating_capacity_at_speed_3",
                "rated_water_heating_cop_at_speed_3",
                "rated_sensible_heat_ratio_at_speed_3",
                "speed_3_reference_unit_rated_air_flow_rate",
                "speed_3_reference_unit_rated_water_flow_rate",
                "speed_3_reference_unit_water_pump_input_power_at_rated_conditions",
                "speed_3_total_wh_capacity_function_of_temperature_curve_name",
                "speed_3_total_wh_capacity_function_of_air_flow_fraction_curve_name",
                "speed_3_total_wh_capacity_function_of_water_flow_fraction_curve_name",
                "speed_3_cop_function_of_temperature_curve_name",
                "speed_3_cop_function_of_air_flow_fraction_curve_name",
                "speed_3_cop_function_of_water_flow_fraction_curve_name",
                "rated_water_heating_capacity_at_speed_4",
                "rated_water_heating_cop_at_speed_4",
                "rated_sensible_heat_ratio_at_speed_4",
                "speed_4_reference_unit_rated_air_flow_rate",
                "speed_4_reference_unit_rated_water_flow_rate",
                "speed_4_reference_unit_water_pump_input_power_at_rated_conditions",
                "speed_4_total_wh_capacity_function_of_temperature_curve_name",
                "speed_4_total_wh_capacity_function_of_air_flow_fraction_curve_name",
                "speed_4_total_wh_capacity_function_of_water_flow_fraction_curve_name",
                "speed_4_cop_function_of_temperature_curve_name",
                "speed_4_cop_function_of_air_flow_fraction_curve_name",
                "speed_4_cop_function_of_water_flow_fraction_curve_name",
                "rated_water_heating_capacity_at_speed_5",
                "rated_water_heating_cop_at_speed_5",
                "rated_sensible_heat_ratio_at_speed_5",
                "speed_5_reference_unit_rated_air_flow_rate",
                "speed_5_reference_unit_rated_water_flow_rate",
                "speed_5_reference_unit_water_pump_input_power_at_rated_conditions",
                "speed_5_total_wh_capacity_function_of_temperature_curve_name",
                "speed_5_total_wh_capacity_function_of_air_flow_fraction_curve_name",
                "speed_5_total_wh_capacity_function_of_water_flow_fraction_curve_name",
                "speed_5_cop_function_of_temperature_curve_name",
                "speed_5_cop_function_of_air_flow_fraction_curve_name",
                "speed_5_cop_function_of_water_flow_fraction_curve_name",
                "rated_water_heating_capacity_at_speed_6",
                "rated_water_heating_cop_at_speed_6",
                "rated_sensible_heat_ratio_at_speed_6",
                "speed_6_reference_unit_rated_air_flow_rate",
                "speed_6_reference_unit_rated_water_flow_rate",
                "speed_6_reference_unit_water_pump_input_power_at_rated_conditions",
                "speed_6_total_wh_capacity_function_of_temperature_curve_name",
                "speed_6_total_wh_capacity_function_of_air_flow_fraction_curve_name",
                "speed_6_total_wh_capacity_function_of_water_flow_fraction_curve_name",
                "speed_6_cop_function_of_temperature_curve_name",
                "speed_6_cop_function_of_air_flow_fraction_curve_name",
                "speed_6_cop_function_of_water_flow_fraction_curve_name",
                "rated_water_heating_capacity_at_speed_7",
                "rated_water_heating_cop_at_speed_7",
                "rated_sensible_heat_ratio_at_speed_7",
                "speed_7_reference_unit_rated_air_flow_rate",
                "speed_7_reference_unit_rated_water_flow_rate",
                "speed_7_reference_unit_water_pump_input_power_at_rated_conditions",
                "speed_7_total_wh_capacity_function_of_temperature_curve_name",
                "speed_7_total_wh_capacity_function_of_air_flow_fraction_curve_name",
                "speed_7_total_wh_capacity_function_of_water_flow_fraction_curve_name",
                "speed_7_cop_function_of_temperature_curve_name",
                "speed_7_cop_function_of_air_flow_fraction_curve_name",
                "speed_7_cop_function_of_water_flow_fraction_curve_name",
                "rated_water_heating_capacity_at_speed_8",
                "rated_water_heating_cop_at_speed_8",
                "rated_sensible_heat_ratio_at_speed_8",
                "speed_8_reference_unit_rated_air_flow_rate",
                "speed_8_reference_unit_rated_water_flow_rate",
                "speed_8_reference_unit_water_pump_input_power_at_rated_conditions",
                "speed_8_total_wh_capacity_function_of_temperature_curve_name",
                "speed_8_total_wh_capacity_function_of_air_flow_fraction_curve_name",
                "speed_8_total_wh_capacity_function_of_water_flow_fraction_curve_name",
                "speed_8_cop_function_of_temperature_curve_name",
                "speed_8_cop_function_of_air_flow_fraction_curve_name",
                "speed_8_cop_function_of_water_flow_fraction_curve_name",
                "rated_water_heating_capacity_at_speed_9",
                "rated_water_heating_cop_at_speed_9",
                "rated_sensible_heat_ratio_at_speed_9",
                "speed_9_reference_unit_rated_air_flow_rate",
                "speed_9_reference_unit_rated_water_flow_rate",
                "speed_9_reference_unit_water_pump_input_power_at_rated_conditions",
                "speed_9_total_wh_capacity_function_of_temperature_curve_name",
                "speed_9_total_wh_capacity_function_of_air_flow_fraction_curve_name",
                "speed_9_total_wh_capacity_function_of_water_flow_fraction_curve_name",
                "speed_9_cop_function_of_temperature_curve_name",
                "speed_9_cop_function_of_air_flow_fraction_curve_name",
                "speed_9_cop_function_of_water_flow_fraction_curve_name",
                "rated_water_heating_capacity_at_speed_10",
                "rated_water_heating_cop_at_speed_10",
                "rated_sensible_heat_ratio_at_speed_10",
                "speed_10_reference_unit_rated_air_flow_rate",
                "speed_10_reference_unit_rated_water_flow_rate",
                "speed_10_reference_unit_water_pump_input_power_at_rated_conditions",
                "speed_10_total_wh_capacity_function_of_temperature_curve_name",
                "speed_10_total_wh_capacity_function_of_air_flow_fraction_curve_name",
                "speed_10_total_wh_capacity_function_of_water_flow_fraction_curve_name",
                "speed_10_cop_function_of_temperature_curve_name",
                "speed_10_cop_function_of_air_flow_fraction_curve_name",
                "speed_10_cop_function_of_water_flow_fraction_curve_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "evaporator_fan_power_included_in_rated_cop",
                    "condenser_pump_power_included_in_rated_cop",
                    "condenser_pump_heat_included_in_rated_heating_capacity_and_rated_cop",
                    "evaporator_air_inlet_node_name",
                    "evaporator_air_outlet_node_name",
                    "condenser_water_inlet_node_name",
                    "condenser_water_outlet_node_name",
                    "evaporator_air_temperature_type_for_curve_objects",
                    "part_load_fraction_correlation_curve_name",
                    "speed_1_total_wh_capacity_function_of_temperature_curve_name",
                    "speed_1_total_wh_capacity_function_of_air_flow_fraction_curve_name",
                    "speed_1_total_wh_capacity_function_of_water_flow_fraction_curve_name",
                    "speed_1_cop_function_of_temperature_curve_name",
                    "speed_1_cop_function_of_air_flow_fraction_curve_name",
                    "speed_1_cop_function_of_water_flow_fraction_curve_name",
                    "speed_2_total_wh_capacity_function_of_temperature_curve_name",
                    "speed_2_total_wh_capacity_function_of_air_flow_fraction_curve_name",
                    "speed_2_total_wh_capacity_function_of_water_flow_fraction_curve_name",
                    "speed_2_cop_function_of_temperature_curve_name",
                    "speed_2_cop_function_of_air_flow_fraction_curve_name",
                    "speed_2_cop_function_of_water_flow_fraction_curve_name",
                    "speed_3_total_wh_capacity_function_of_temperature_curve_name",
                    "speed_3_total_wh_capacity_function_of_air_flow_fraction_curve_name",
                    "speed_3_total_wh_capacity_function_of_water_flow_fraction_curve_name",
                    "speed_3_cop_function_of_temperature_curve_name",
                    "speed_3_cop_function_of_air_flow_fraction_curve_name",
                    "speed_3_cop_function_of_water_flow_fraction_curve_name",
                    "speed_4_total_wh_capacity_function_of_temperature_curve_name",
                    "speed_4_total_wh_capacity_function_of_air_flow_fraction_curve_name",
                    "speed_4_total_wh_capacity_function_of_water_flow_fraction_curve_name",
                    "speed_4_cop_function_of_temperature_curve_name",
                    "speed_4_cop_function_of_air_flow_fraction_curve_name",
                    "speed_4_cop_function_of_water_flow_fraction_curve_name",
                    "speed_5_total_wh_capacity_function_of_temperature_curve_name",
                    "speed_5_total_wh_capacity_function_of_air_flow_fraction_curve_name",
                    "speed_5_total_wh_capacity_function_of_water_flow_fraction_curve_name",
                    "speed_5_cop_function_of_temperature_curve_name",
                    "speed_5_cop_function_of_air_flow_fraction_curve_name",
                    "speed_5_cop_function_of_water_flow_fraction_curve_name",
                    "speed_6_total_wh_capacity_function_of_temperature_curve_name",
                    "speed_6_total_wh_capacity_function_of_air_flow_fraction_curve_name",
                    "speed_6_total_wh_capacity_function_of_water_flow_fraction_curve_name",
                    "speed_6_cop_function_of_temperature_curve_name",
                    "speed_6_cop_function_of_air_flow_fraction_curve_name",
                    "speed_6_cop_function_of_water_flow_fraction_curve_name",
                    "speed_7_total_wh_capacity_function_of_temperature_curve_name",
                    "speed_7_total_wh_capacity_function_of_air_flow_fraction_curve_name",
                    "speed_7_total_wh_capacity_function_of_water_flow_fraction_curve_name",
                    "speed_7_cop_function_of_temperature_curve_name",
                    "speed_7_cop_function_of_air_flow_fraction_curve_name",
                    "speed_7_cop_function_of_water_flow_fraction_curve_name",
                    "speed_8_total_wh_capacity_function_of_temperature_curve_name",
                    "speed_8_total_wh_capacity_function_of_air_flow_fraction_curve_name",
                    "speed_8_total_wh_capacity_function_of_water_flow_fraction_curve_name",
                    "speed_8_cop_function_of_temperature_curve_name",
                    "speed_8_cop_function_of_air_flow_fraction_curve_name",
                    "speed_8_cop_function_of_water_flow_fraction_curve_name",
                    "speed_9_total_wh_capacity_function_of_temperature_curve_name",
                    "speed_9_total_wh_capacity_function_of_air_flow_fraction_curve_name",
                    "speed_9_total_wh_capacity_function_of_water_flow_fraction_curve_name",
                    "speed_9_cop_function_of_temperature_curve_name",
                    "speed_9_cop_function_of_air_flow_fraction_curve_name",
                    "speed_9_cop_function_of_water_flow_fraction_curve_name",
                    "speed_10_total_wh_capacity_function_of_temperature_curve_name",
                    "speed_10_total_wh_capacity_function_of_air_flow_fraction_curve_name",
                    "speed_10_total_wh_capacity_function_of_water_flow_fraction_curve_name",
                    "speed_10_cop_function_of_temperature_curve_name",
                    "speed_10_cop_function_of_air_flow_fraction_curve_name",
                    "speed_10_cop_function_of_water_flow_fraction_curve_name"
                ]
            },
            "numerics": {
                "fields": [
                    "number_of_speeds",
                    "nominal_speed_level",
                    "rated_water_heating_capacity",
                    "rated_evaporator_inlet_air_dry_bulb_temperature",
                    "rated_evaporator_inlet_air_wet_bulb_temperature",
                    "rated_condenser_inlet_water_temperature",
                    "rated_evaporator_air_flow_rate",
                    "rated_condenser_water_flow_rate",
                    "fraction_of_condenser_pump_heat_to_water",
                    "crankcase_heater_capacity",
                    "maximum_ambient_temperature_for_crankcase_heater_operation",
                    "rated_water_heating_capacity_at_speed_1",
                    "rated_water_heating_cop_at_speed_1",
                    "rated_sensible_heat_ratio_at_speed_1",
                    "speed_1_reference_unit_rated_air_flow_rate",
                    "speed_1_reference_unit_rated_water_flow_rate",
                    "speed_1_reference_unit_water_pump_input_power_at_rated_conditions",
                    "rated_water_heating_capacity_at_speed_2",
                    "rated_water_heating_cop_at_speed_2",
                    "rated_sensible_heat_ratio_at_speed_2",
                    "speed_2_reference_unit_rated_air_flow_rate",
                    "speed_2_reference_unit_rated_water_flow_rate",
                    "speed_2_reference_unit_water_pump_input_power_at_rated_conditions",
                    "rated_water_heating_capacity_at_speed_3",
                    "rated_water_heating_cop_at_speed_3",
                    "rated_sensible_heat_ratio_at_speed_3",
                    "speed_3_reference_unit_rated_air_flow_rate",
                    "speed_3_reference_unit_rated_water_flow_rate",
                    "speed_3_reference_unit_water_pump_input_power_at_rated_conditions",
                    "rated_water_heating_capacity_at_speed_4",
                    "rated_water_heating_cop_at_speed_4",
                    "rated_sensible_heat_ratio_at_speed_4",
                    "speed_4_reference_unit_rated_air_flow_rate",
                    "speed_4_reference_unit_rated_water_flow_rate",
                    "speed_4_reference_unit_water_pump_input_power_at_rated_conditions",
                    "rated_water_heating_capacity_at_speed_5",
                    "rated_water_heating_cop_at_speed_5",
                    "rated_sensible_heat_ratio_at_speed_5",
                    "speed_5_reference_unit_rated_air_flow_rate",
                    "speed_5_reference_unit_rated_water_flow_rate",
                    "speed_5_reference_unit_water_pump_input_power_at_rated_conditions",
                    "rated_water_heating_capacity_at_speed_6",
                    "rated_water_heating_cop_at_speed_6",
                    "rated_sensible_heat_ratio_at_speed_6",
                    "speed_6_reference_unit_rated_air_flow_rate",
                    "speed_6_reference_unit_rated_water_flow_rate",
                    "speed_6_reference_unit_water_pump_input_power_at_rated_conditions",
                    "rated_water_heating_capacity_at_speed_7",
                    "rated_water_heating_cop_at_speed_7",
                    "rated_sensible_heat_ratio_at_speed_7",
                    "speed_7_reference_unit_rated_air_flow_rate",
                    "speed_7_reference_unit_rated_water_flow_rate",
                    "speed_7_reference_unit_water_pump_input_power_at_rated_conditions",
                    "rated_water_heating_capacity_at_speed_8",
                    "rated_water_heating_cop_at_speed_8",
                    "rated_sensible_heat_ratio_at_speed_8",
                    "speed_8_reference_unit_rated_air_flow_rate",
                    "speed_8_reference_unit_rated_water_flow_rate",
                    "speed_8_reference_unit_water_pump_input_power_at_rated_conditions",
                    "rated_water_heating_capacity_at_speed_9",
                    "rated_water_heating_cop_at_speed_9",
                    "rated_sensible_heat_ratio_at_speed_9",
                    "speed_9_reference_unit_rated_air_flow_rate",
                    "speed_9_reference_unit_rated_water_flow_rate",
                    "speed_9_reference_unit_water_pump_input_power_at_rated_conditions",
                    "rated_water_heating_capacity_at_speed_10",
                    "rated_water_heating_cop_at_speed_10",
                    "rated_sensible_heat_ratio_at_speed_10",
                    "speed_10_reference_unit_rated_air_flow_rate",
                    "speed_10_reference_unit_rated_water_flow_rate",
                    "speed_10_reference_unit_water_pump_input_power_at_rated_conditions"
                ]
            }
        },
        "type": "object",
        "memo": "vairlable-speed Heat pump water heater (VSHPWH) heating coil, air-to-water direct-expansion (DX) system which includes a variable-speed water heating coil, evaporator air coil, evaporator fan, electric compressor, and water pump. Part of a WaterHeater:HeatPump system.",
        "min_fields": 33.0
    }
}
```
