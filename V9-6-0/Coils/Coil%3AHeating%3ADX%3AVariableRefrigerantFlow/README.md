```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "availability_schedule": {
                    "type": "string",
                    "note": "Availability schedule name for this system. Schedule value > 0 means the system is available. If this field is blank, the system is always available.",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "gross_rated_heating_capacity": {
                    "note": "Heating capacity not accounting for the effect of supply air fan heat capacity excluding supply air fan heat rating point outside dry-bulb temp 8.33 C, outside wet-bulb temp 6.11 C rating point heating coil entering air dry-bulb 21.11 C, coil entering wetbulb 15.55 C",
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
                "rated_air_flow_rate": {
                    "units": "m3/s",
                    "note": "volume flow rate corresponding to rated total capacity should be between 0.00004027 m3/s and .00006041 m3/s per watt of rated heating capacity",
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
                "coil_air_inlet_node": {
                    "type": "string"
                },
                "coil_air_outlet_node": {
                    "type": "string"
                },
                "heating_capacity_ratio_modifier_function_of_temperature_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions",
                        "UnivariateFunctions"
                    ]
                },
                "heating_capacity_modifier_function_of_flow_fraction_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "quadratic curve = a + b*ff + c*ff**2 cubic curve = a + b*ff + c*ff**2 + d*ff**3 ff = fraction of the full load flow"
                }
            },
            "required": [
                "gross_rated_heating_capacity",
                "rated_air_flow_rate",
                "coil_air_inlet_node",
                "coil_air_outlet_node",
                "heating_capacity_ratio_modifier_function_of_temperature_curve_name",
                "heating_capacity_modifier_function_of_flow_fraction_curve_name"
            ]
        }
    },
    "group": "Coils",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "HeatingCoilsDX",
            "HeatingCoilsDXSingleSpeed",
            "HeatingCoilsDXVarRefrigFlow"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "availability_schedule": {
                "field_name": "Availability Schedule",
                "field_type": "a"
            },
            "gross_rated_heating_capacity": {
                "field_name": "Gross Rated Heating Capacity",
                "field_type": "n"
            },
            "rated_air_flow_rate": {
                "field_name": "Rated Air Flow Rate",
                "field_type": "n"
            },
            "coil_air_inlet_node": {
                "field_name": "Coil Air Inlet Node",
                "field_type": "a"
            },
            "coil_air_outlet_node": {
                "field_name": "Coil Air Outlet Node",
                "field_type": "a"
            },
            "heating_capacity_ratio_modifier_function_of_temperature_curve_name": {
                "field_name": "Heating Capacity Ratio Modifier Function of Temperature Curve Name",
                "field_type": "a"
            },
            "heating_capacity_modifier_function_of_flow_fraction_curve_name": {
                "field_name": "Heating Capacity Modifier Function of Flow Fraction Curve Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "availability_schedule",
            "gross_rated_heating_capacity",
            "rated_air_flow_rate",
            "coil_air_inlet_node",
            "coil_air_outlet_node",
            "heating_capacity_ratio_modifier_function_of_temperature_curve_name",
            "heating_capacity_modifier_function_of_flow_fraction_curve_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "availability_schedule",
                "coil_air_inlet_node",
                "coil_air_outlet_node",
                "heating_capacity_ratio_modifier_function_of_temperature_curve_name",
                "heating_capacity_modifier_function_of_flow_fraction_curve_name"
            ]
        },
        "numerics": {
            "fields": [
                "gross_rated_heating_capacity",
                "rated_air_flow_rate"
            ]
        }
    },
    "type": "object",
    "memo": "Variable refrigerant flow (VRF) direct expansion (DX) heating coil (air-to-air heat pump). Used with ZoneHVAC:TerminalUnit:VariableRefrigerantFlow. Condensing unit is modeled separately, see AirConditioner:VariableRefrigerantFlow.",
    "min_fields": 5.0
}
```
