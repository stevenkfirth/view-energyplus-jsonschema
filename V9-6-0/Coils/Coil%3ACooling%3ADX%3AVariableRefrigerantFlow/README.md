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
                "gross_rated_total_cooling_capacity": {
                    "note": "Total cooling capacity not accounting for the effect of supply air fan heat Cooling capacity excluding supply air fan heat",
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
                "gross_rated_sensible_heat_ratio": {
                    "note": "Sensible heat ratio excluding supply air fan heat",
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
                    "note": "Volume flow rate corresponding to rated total cooling capacity should be between 0.00004027 m3/s and .00006041 m3/s per watt of rated total cooling capacity",
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
                "cooling_capacity_ratio_modifier_function_of_temperature_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions",
                        "UnivariateFunctions"
                    ]
                },
                "cooling_capacity_modifier_curve_function_of_flow_fraction_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "quadratic curve = a + b*ff + c*ff**2 cubic curve = a + b*ff + c*ff**2 + d*ff**3 ff = fraction of the full load flow"
                },
                "coil_air_inlet_node": {
                    "type": "string"
                },
                "coil_air_outlet_node": {
                    "type": "string"
                },
                "name_of_water_storage_tank_for_condensate_collection": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "WaterStorageTankNames"
                    ]
                }
            },
            "required": [
                "gross_rated_total_cooling_capacity",
                "gross_rated_sensible_heat_ratio",
                "rated_air_flow_rate",
                "cooling_capacity_ratio_modifier_function_of_temperature_curve_name",
                "cooling_capacity_modifier_curve_function_of_flow_fraction_name",
                "coil_air_inlet_node",
                "coil_air_outlet_node"
            ]
        }
    },
    "group": "Coils",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "CoolingCoilsDXVarRefrigFlow"
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
            "gross_rated_total_cooling_capacity": {
                "field_name": "Gross Rated Total Cooling Capacity",
                "field_type": "n"
            },
            "gross_rated_sensible_heat_ratio": {
                "field_name": "Gross Rated Sensible Heat Ratio",
                "field_type": "n"
            },
            "rated_air_flow_rate": {
                "field_name": "Rated Air Flow Rate",
                "field_type": "n"
            },
            "cooling_capacity_ratio_modifier_function_of_temperature_curve_name": {
                "field_name": "Cooling Capacity Ratio Modifier Function of Temperature Curve Name",
                "field_type": "a"
            },
            "cooling_capacity_modifier_curve_function_of_flow_fraction_name": {
                "field_name": "Cooling Capacity Modifier Curve Function of Flow Fraction Name",
                "field_type": "a"
            },
            "coil_air_inlet_node": {
                "field_name": "Coil Air Inlet Node",
                "field_type": "a"
            },
            "coil_air_outlet_node": {
                "field_name": "Coil Air Outlet Node",
                "field_type": "a"
            },
            "name_of_water_storage_tank_for_condensate_collection": {
                "field_name": "Name of Water Storage Tank for Condensate Collection",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "availability_schedule_name",
            "gross_rated_total_cooling_capacity",
            "gross_rated_sensible_heat_ratio",
            "rated_air_flow_rate",
            "cooling_capacity_ratio_modifier_function_of_temperature_curve_name",
            "cooling_capacity_modifier_curve_function_of_flow_fraction_name",
            "coil_air_inlet_node",
            "coil_air_outlet_node",
            "name_of_water_storage_tank_for_condensate_collection"
        ],
        "alphas": {
            "fields": [
                "name",
                "availability_schedule_name",
                "cooling_capacity_ratio_modifier_function_of_temperature_curve_name",
                "cooling_capacity_modifier_curve_function_of_flow_fraction_name",
                "coil_air_inlet_node",
                "coil_air_outlet_node",
                "name_of_water_storage_tank_for_condensate_collection"
            ]
        },
        "numerics": {
            "fields": [
                "gross_rated_total_cooling_capacity",
                "gross_rated_sensible_heat_ratio",
                "rated_air_flow_rate"
            ]
        }
    },
    "type": "object",
    "memo": "Variable refrigerant flow (VRF) direct expansion (DX) cooling coil. Used with ZoneHVAC:TerminalUnit:VariableRefrigerantFlow. Condensing unit is modeled separately, see AirConditioner:VariableRefrigerantFlow.",
    "min_fields": 9.0
}
```
