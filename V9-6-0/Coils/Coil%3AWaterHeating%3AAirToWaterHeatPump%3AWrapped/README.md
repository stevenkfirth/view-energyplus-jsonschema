```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "rated_heating_capacity": {
                    "type": "number",
                    "units": "W",
                    "exclusiveMinimum": 0.0,
                    "note": "Heating capacity at the rated inlet air temperatures, rated condenser inlet water temperature, rated air flow rate, and rated water flow rate. Can optionally include condenser pump heat."
                },
                "rated_cop": {
                    "type": "number",
                    "units": "W/W",
                    "exclusiveMinimum": 0.0,
                    "default": 3.2,
                    "note": "Heating coefficient of performance at the rated inlet air temperatures, rated condenser inlet water temperature, rated air flow rate, and rated water flow rate. Can optionally include condenser pump power and evaporator fan power (see fields below)."
                },
                "rated_sensible_heat_ratio": {
                    "type": "number",
                    "minimum": 0.5,
                    "maximum": 1.0,
                    "default": 0.85,
                    "note": "Gross air-side sensible heat ratio at the rated inlet air temperatures, rated condenser inlet water temperature, rated air flow rate, and rated water flow rate. Sensible heat ratio equals gross sensible cooling capacity divided by gross total cooling capacity. Rated SHR (gross) should not include evaporator fan heat, only sensible cooling and dehumidification by the coil alone."
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
                "rated_condenser_water_temperature": {
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
                "evaporator_air_inlet_node_name": {
                    "type": "string",
                    "note": "The node from which the DX coil draws its inlet air."
                },
                "evaporator_air_outlet_node_name": {
                    "type": "string",
                    "note": "The node to which the DX coil sends its outlet air."
                },
                "crankcase_heater_capacity": {
                    "type": "number",
                    "minimum": 0.0,
                    "default": 0.0,
                    "units": "W",
                    "note": "The compressor crankcase heater only operates when the dry-bulb temperature of air surrounding the compressor is below the Maximum Ambient Temperature for Crankcase Heater Operation and the DX coil is off. The ambient temperature surrounding the compressor is set by the WaterHeater:HeatPump:WrappedCondenser parent object (field Compressor Location)."
                },
                "maximum_ambient_temperature_for_crankcase_heater_operation": {
                    "type": "number",
                    "minimum": 0.0,
                    "default": 10.0,
                    "units": "C",
                    "note": "The compressor crankcase heater only operates when the dry-bulb temperature of air surrounding the compressor is below the Maximum Outdoor Temperature for Crankcase Heater Operation and the unit is off. The ambient temperature surrounding the compressor is set by the WaterHeater:HeatPump:WrappedCondenser parent object (field Compressor Location)."
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
                "heating_capacity_function_of_temperature_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions",
                        "UnivariateFunctions"
                    ],
                    "note": "Heating capacity modifier curve (function of temperature) should be biquadratic or cubic. Biquadratic curve = a + b(ta) + c(ta)^2 + d(tw) + e(tw)^2 + f(ta)(tw). Cubic curve = a + b(ta) + c(ta)^2 + d(ta)^3. ta = evaporator inlet air [dry-bulb or wet-bulb] temperature (C). tw = condenser inlet water temperature (C). The field Evaporator Air Temperature Type for Curve Objects determines if dry-bulb or wet-bulb is used as the evaporator inlet air temperature (ta)."
                },
                "heating_capacity_function_of_air_flow_fraction_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "Heating capacity modifier curve (function of air flow fraction) should be quadratic or cubic. Quadratic curve = a + b(ff) + c(ff)^2. Cubic curve = a + b(ff) + c(ff)^2 + d(ff)^3. ff = fraction of the rated evaporator air flow rate. Use curve coefficients of 1,0,0 or leave this field blank when neglecting performance impacts due to variations in air flow rate fraction."
                },
                "heating_cop_function_of_temperature_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions",
                        "UnivariateFunctions"
                    ],
                    "note": "Heating COP modifier curve (function of temperature) should be biquadratic or cubic. Biquadratic curve = a + b(ta) + c(ta)^2 + d(tw) + e(tw)^2 + f(ta)(tw). Cubic curve = a + b(ta) + c(ta)^2 + d(ta)^3. ta = evaporator inlet air [dry-bulb or wet-bulb] temperature (C). tw = condenser inlet water temperature (C). The field Evaporator Air Temperature Type for Curve Objects determines if dry-bulb or wet-bulb is used as the evaporator inlet air temperature (ta)."
                },
                "heating_cop_function_of_air_flow_fraction_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "Heating COP modifier curve (function of air flow fraction) should be quadratic or cubic. Quadratic curve = a + b(ff) + c(ff)^2. Cubic curve = a + b(ff) + c(ff)^2 + d(ff)^3. ff = fraction of the rated evaporator air flow rate. Use curve coefficients of 1,0,0 or leave this field blank when neglecting performance impacts due to variations in air flow rate fraction."
                },
                "part_load_fraction_correlation_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "Part Load Fraction Correlation (function of part load ratio) should be quadratic or cubic. Quadratic curve = a + b(PLR) + c(PLR)^2. Cubic curve = a + b(PLR) + c(PLR)^2 + d(PLR)^3. PLR = part load ratio (heating delivered/steady state heating capacity). Use curve coefficients of 1,0,0 or leave this field blank when neglecting performance impacts due to variations in part load ratio."
                }
            },
            "required": [
                "rated_heating_capacity",
                "evaporator_air_inlet_node_name",
                "evaporator_air_outlet_node_name"
            ]
        }
    },
    "group": "Coils",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "HeatPumpWaterHeaterDXCoilsWrapped"
        ],
        "note": "Unique name for this instance of a heat pump water heater DX coil."
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "rated_heating_capacity": {
                "field_name": "Rated Heating Capacity",
                "field_type": "n"
            },
            "rated_cop": {
                "field_name": "Rated COP",
                "field_type": "n"
            },
            "rated_sensible_heat_ratio": {
                "field_name": "Rated Sensible Heat Ratio",
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
            "rated_condenser_water_temperature": {
                "field_name": "Rated Condenser Water Temperature",
                "field_type": "n"
            },
            "rated_evaporator_air_flow_rate": {
                "field_name": "Rated Evaporator Air Flow Rate",
                "field_type": "n"
            },
            "evaporator_fan_power_included_in_rated_cop": {
                "field_name": "Evaporator Fan Power Included in Rated COP",
                "field_type": "a"
            },
            "evaporator_air_inlet_node_name": {
                "field_name": "Evaporator Air Inlet Node Name",
                "field_type": "a"
            },
            "evaporator_air_outlet_node_name": {
                "field_name": "Evaporator Air Outlet Node Name",
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
            "heating_capacity_function_of_temperature_curve_name": {
                "field_name": "Heating Capacity Function of Temperature Curve Name",
                "field_type": "a"
            },
            "heating_capacity_function_of_air_flow_fraction_curve_name": {
                "field_name": "Heating Capacity Function of Air Flow Fraction Curve Name",
                "field_type": "a"
            },
            "heating_cop_function_of_temperature_curve_name": {
                "field_name": "Heating COP Function of Temperature Curve Name",
                "field_type": "a"
            },
            "heating_cop_function_of_air_flow_fraction_curve_name": {
                "field_name": "Heating COP Function of Air Flow Fraction Curve Name",
                "field_type": "a"
            },
            "part_load_fraction_correlation_curve_name": {
                "field_name": "Part Load Fraction Correlation Curve Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "rated_heating_capacity",
            "rated_cop",
            "rated_sensible_heat_ratio",
            "rated_evaporator_inlet_air_dry_bulb_temperature",
            "rated_evaporator_inlet_air_wet_bulb_temperature",
            "rated_condenser_water_temperature",
            "rated_evaporator_air_flow_rate",
            "evaporator_fan_power_included_in_rated_cop",
            "evaporator_air_inlet_node_name",
            "evaporator_air_outlet_node_name",
            "crankcase_heater_capacity",
            "maximum_ambient_temperature_for_crankcase_heater_operation",
            "evaporator_air_temperature_type_for_curve_objects",
            "heating_capacity_function_of_temperature_curve_name",
            "heating_capacity_function_of_air_flow_fraction_curve_name",
            "heating_cop_function_of_temperature_curve_name",
            "heating_cop_function_of_air_flow_fraction_curve_name",
            "part_load_fraction_correlation_curve_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "evaporator_fan_power_included_in_rated_cop",
                "evaporator_air_inlet_node_name",
                "evaporator_air_outlet_node_name",
                "evaporator_air_temperature_type_for_curve_objects",
                "heating_capacity_function_of_temperature_curve_name",
                "heating_capacity_function_of_air_flow_fraction_curve_name",
                "heating_cop_function_of_temperature_curve_name",
                "heating_cop_function_of_air_flow_fraction_curve_name",
                "part_load_fraction_correlation_curve_name"
            ]
        },
        "numerics": {
            "fields": [
                "rated_heating_capacity",
                "rated_cop",
                "rated_sensible_heat_ratio",
                "rated_evaporator_inlet_air_dry_bulb_temperature",
                "rated_evaporator_inlet_air_wet_bulb_temperature",
                "rated_condenser_water_temperature",
                "rated_evaporator_air_flow_rate",
                "crankcase_heater_capacity",
                "maximum_ambient_temperature_for_crankcase_heater_operation"
            ]
        }
    },
    "type": "object",
    "memo": "Heat pump water heater (HPWH) heating coil, air-to-water direct-expansion (DX) system which includes a water heating coil, evaporator air coil, evaporator fan, electric compressor, and water pump. Part of a WaterHeater:HeatPump:WrappedCondenser system.",
    "min_fields": 14.0
}
```
