```
{
    "ChillerHeater:Absorption:DirectFired": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "nominal_cooling_capacity": {
                        "default": "Autosize",
                        "units": "W",
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
                    "heating_to_cooling_capacity_ratio": {
                        "type": "number",
                        "note": "A positive fraction that represents the ratio of the heating capacity divided by the cooling capacity at rated conditions.",
                        "minimum": 0.0,
                        "default": 0.8
                    },
                    "fuel_input_to_cooling_output_ratio": {
                        "type": "number",
                        "note": "The positive fraction that represents the ratio of the instantaneous fuel used divided by the cooling capacity at rated conditions.",
                        "exclusiveMinimum": 0.0,
                        "default": 0.97
                    },
                    "fuel_input_to_heating_output_ratio": {
                        "type": "number",
                        "note": "The positive fraction that represents the ratio of the instantaneous fuel used divided by the nominal heating capacity.",
                        "minimum": 0.0,
                        "default": 1.25
                    },
                    "electric_input_to_cooling_output_ratio": {
                        "type": "number",
                        "note": "The positive fraction that represents the ratio of the instantaneous electricity used divided by the cooling capacity at rated conditions. If the chiller is both heating and cooling only the cooling electricity is used.",
                        "minimum": 0.0,
                        "default": 0.01
                    },
                    "electric_input_to_heating_output_ratio": {
                        "type": "number",
                        "note": "The positive fraction that represents the ratio of the instantaneous electricity used divided by the nominal heating capacity. If the chiller is both heating and cooling only the cooling electricity is used.",
                        "minimum": 0.0,
                        "default": 0.0
                    },
                    "chilled_water_inlet_node_name": {
                        "type": "string"
                    },
                    "chilled_water_outlet_node_name": {
                        "type": "string"
                    },
                    "condenser_inlet_node_name": {
                        "type": "string"
                    },
                    "condenser_outlet_node_name": {
                        "type": "string",
                        "note": "Not required if air-cooled"
                    },
                    "hot_water_inlet_node_name": {
                        "type": "string"
                    },
                    "hot_water_outlet_node_name": {
                        "type": "string"
                    },
                    "minimum_part_load_ratio": {
                        "type": "number",
                        "note": "The positive fraction that represents the minimum cooling output possible when operated continually at rated temperature conditions divided by the nominal cooling capacity at those same conditions. If the load on the chiller is below this fraction the chiller will cycle.",
                        "exclusiveMinimum": 0.0,
                        "default": 0.1
                    },
                    "maximum_part_load_ratio": {
                        "type": "number",
                        "note": "The positive fraction that represents the maximum cooling output possible at rated temperature conditions divided by the nominal cooling capacity at those same conditions. If greater than 1.0, the chiller is typically thought of as capable of being overloaded.",
                        "minimum": 0.5,
                        "default": 1.0
                    },
                    "optimum_part_load_ratio": {
                        "type": "number",
                        "note": "The positive fraction that represents the optimal cooling output at rated temperature conditions divided by the nominal cooling capacity at those same conditions. It represents the most desirable operating point for the chiller.",
                        "exclusiveMinimum": 0.0,
                        "default": 1.0
                    },
                    "design_entering_condenser_water_temperature": {
                        "type": "number",
                        "note": "The temperature of the water entering the condenser of the chiller when operating at design conditions. This is usually based on the temperature delivered by the cooling tower in a water cooled application.",
                        "default": 29.0,
                        "units": "C"
                    },
                    "design_leaving_chilled_water_temperature": {
                        "type": "number",
                        "note": "The temperature of the water leaving the evaporator of the chiller when operating at design conditions also called the chilled water supply temperature or leaving chilled water temperature.",
                        "default": 7.0,
                        "units": "C"
                    },
                    "design_chilled_water_flow_rate": {
                        "note": "For variable volume this is the max flow & for constant flow this is the flow.",
                        "default": "Autosize",
                        "units": "m3/s",
                        "ip-units": "gal/min",
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
                    "design_condenser_water_flow_rate": {
                        "note": "The water flow rate at design conditions through the condenser. This field is not used for Condenser Type = AirCooled",
                        "default": "Autosize",
                        "units": "m3/s",
                        "ip-units": "gal/min",
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
                    "design_hot_water_flow_rate": {
                        "note": "The water flow rate at design conditions through the heater side.",
                        "default": "Autosize",
                        "units": "m3/s",
                        "ip-units": "gal/min",
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
                    "cooling_capacity_function_of_temperature_curve_name": {
                        "type": "string",
                        "note": "The CoolCapFT curve represents the fraction of the cooling capacity of the chiller as it varies by temperature. The curve is normalized so that at design conditions the value of the curve should be 1.0. This is a biquadratic curve with the input variables being the leaving chilled water temperature and either the entering or leaving condenser water temperature.",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ]
                    },
                    "fuel_input_to_cooling_output_ratio_function_of_temperature_curve_name": {
                        "type": "string",
                        "note": "The curve represents the fraction of the fuel input to the chiller at full load as it varies by temperature. The curve is normalized so that at design conditions the value of the curve should be 1.0. This is a biquadratic curve with the input variables being the leaving chilled water temperature and either the entering or leaving condenser water temperature.",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ]
                    },
                    "fuel_input_to_cooling_output_ratio_function_of_part_load_ratio_curve_name": {
                        "type": "string",
                        "note": "The curve represents the fraction of the fuel input to the chiller as the load on the chiller varies but the operating temperatures remain at the design values. The curve is normalized so that at full load the value of the curve should be 1.0. The curve is usually linear or quadratic.",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ]
                    },
                    "electric_input_to_cooling_output_ratio_function_of_temperature_curve_name": {
                        "type": "string",
                        "note": "The curve represents the fraction of the electricity to the chiller at full load as it varies by temperature. The curve is normalized so that at design conditions the value of the curve should be 1.0. This is a biquadratic curve with the input variables being the leaving chilled water temperature and either the entering or leaving condenser water temperature.",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions"
                        ]
                    },
                    "electric_input_to_cooling_output_ratio_function_of_part_load_ratio_curve_name": {
                        "type": "string",
                        "note": "The curve represents the fraction of the electricity to the chiller as the load on the chiller varies but the operating temperatures remain at the design values. The curve is normalized so that at full load the value of the curve should be 1.0. The curve is usually linear or quadratic.",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ]
                    },
                    "heating_capacity_function_of_cooling_capacity_curve_name": {
                        "type": "string",
                        "note": "The curve represents how the heating capacity of the chiller varies with cooling capacity when the chiller is simultaneous heating and cooling. The curve is normalized so an input of 1.0 represents the nominal cooling capacity and an output of 1.0 represents the full heating capacity (see the Heating to cooling capacity ratio input) The curve is usually linear or quadratic.",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ]
                    },
                    "fuel_input_to_heat_output_ratio_during_heating_only_operation_curve_name": {
                        "type": "string",
                        "note": "When the chiller is operating as only a heater, this curve is used to represent the fraction of fuel used as the heating load varies. It is normalized so that a value of 1.0 is the full heating capacity. The curve is usually linear or quadratic and will probably be similar to a boiler curve for most chillers.",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ]
                    },
                    "temperature_curve_input_variable": {
                        "type": "string",
                        "enum": [
                            "",
                            "EnteringCondenser",
                            "LeavingCondenser"
                        ],
                        "default": "EnteringCondenser",
                        "note": "Sets the second independent variable in the three temperature dependent performance curves to either the leaving or entering condenser water temperature. Manufacturers express the performance of their chillers using either the leaving condenser water temperature (to the tower) or the entering condenser water temperature (from the tower)."
                    },
                    "condenser_type": {
                        "type": "string",
                        "note": "The condenser can either be air cooled or connected to a cooling tower.",
                        "enum": [
                            "",
                            "AirCooled",
                            "WaterCooled"
                        ],
                        "default": "WaterCooled"
                    },
                    "chilled_water_temperature_lower_limit": {
                        "type": "number",
                        "note": "The chilled water supply temperature below which the chiller will shut off.",
                        "units": "C",
                        "default": 2.0
                    },
                    "fuel_higher_heating_value": {
                        "type": "number",
                        "note": "Not currently used.",
                        "units": "kJ/kg",
                        "default": 0.0
                    },
                    "fuel_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "Diesel",
                            "FuelOilNo1",
                            "FuelOilNo2",
                            "Gasoline",
                            "NaturalGas",
                            "OtherFuel1",
                            "OtherFuel2",
                            "Propane"
                        ],
                        "default": "NaturalGas"
                    },
                    "sizing_factor": {
                        "type": "number",
                        "note": "Multiplies the autosized capacity and flow rates",
                        "exclusiveMinimum": 0.0,
                        "default": 1.0
                    }
                },
                "required": [
                    "chilled_water_inlet_node_name",
                    "chilled_water_outlet_node_name",
                    "condenser_inlet_node_name",
                    "hot_water_inlet_node_name",
                    "hot_water_outlet_node_name"
                ]
            }
        },
        "group": "Plant Heating and Cooling Equipment",
        "name": {
            "type": "string",
            "is_required": true,
            "reference-class-name": [
                "validBranchEquipmentTypes",
                "validPlantEquipmentTypes"
            ],
            "reference": [
                "validBranchEquipmentNames",
                "validPlantEquipmentNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "nominal_cooling_capacity": {
                    "field_name": "Nominal Cooling Capacity",
                    "field_type": "n"
                },
                "heating_to_cooling_capacity_ratio": {
                    "field_name": "Heating to Cooling Capacity Ratio",
                    "field_type": "n"
                },
                "fuel_input_to_cooling_output_ratio": {
                    "field_name": "Fuel Input to Cooling Output Ratio",
                    "field_type": "n"
                },
                "fuel_input_to_heating_output_ratio": {
                    "field_name": "Fuel Input to Heating Output Ratio",
                    "field_type": "n"
                },
                "electric_input_to_cooling_output_ratio": {
                    "field_name": "Electric Input to Cooling Output Ratio",
                    "field_type": "n"
                },
                "electric_input_to_heating_output_ratio": {
                    "field_name": "Electric Input to Heating Output Ratio",
                    "field_type": "n"
                },
                "chilled_water_inlet_node_name": {
                    "field_name": "Chilled Water Inlet Node Name",
                    "field_type": "a"
                },
                "chilled_water_outlet_node_name": {
                    "field_name": "Chilled Water Outlet Node Name",
                    "field_type": "a"
                },
                "condenser_inlet_node_name": {
                    "field_name": "Condenser Inlet Node Name",
                    "field_type": "a"
                },
                "condenser_outlet_node_name": {
                    "field_name": "Condenser Outlet Node Name",
                    "field_type": "a"
                },
                "hot_water_inlet_node_name": {
                    "field_name": "Hot Water Inlet Node Name",
                    "field_type": "a"
                },
                "hot_water_outlet_node_name": {
                    "field_name": "Hot Water Outlet Node Name",
                    "field_type": "a"
                },
                "minimum_part_load_ratio": {
                    "field_name": "Minimum Part Load Ratio",
                    "field_type": "n"
                },
                "maximum_part_load_ratio": {
                    "field_name": "Maximum Part Load Ratio",
                    "field_type": "n"
                },
                "optimum_part_load_ratio": {
                    "field_name": "Optimum Part Load Ratio",
                    "field_type": "n"
                },
                "design_entering_condenser_water_temperature": {
                    "field_name": "Design Entering Condenser Water Temperature",
                    "field_type": "n"
                },
                "design_leaving_chilled_water_temperature": {
                    "field_name": "Design Leaving Chilled Water Temperature",
                    "field_type": "n"
                },
                "design_chilled_water_flow_rate": {
                    "field_name": "Design Chilled Water Flow Rate",
                    "field_type": "n"
                },
                "design_condenser_water_flow_rate": {
                    "field_name": "Design Condenser Water Flow Rate",
                    "field_type": "n"
                },
                "design_hot_water_flow_rate": {
                    "field_name": "Design Hot Water Flow Rate",
                    "field_type": "n"
                },
                "cooling_capacity_function_of_temperature_curve_name": {
                    "field_name": "Cooling Capacity Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "fuel_input_to_cooling_output_ratio_function_of_temperature_curve_name": {
                    "field_name": "Fuel Input to Cooling Output Ratio Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "fuel_input_to_cooling_output_ratio_function_of_part_load_ratio_curve_name": {
                    "field_name": "Fuel Input to Cooling Output Ratio Function of Part Load Ratio Curve Name",
                    "field_type": "a"
                },
                "electric_input_to_cooling_output_ratio_function_of_temperature_curve_name": {
                    "field_name": "Electric Input to Cooling Output Ratio Function of Temperature Curve Name",
                    "field_type": "a"
                },
                "electric_input_to_cooling_output_ratio_function_of_part_load_ratio_curve_name": {
                    "field_name": "Electric Input to Cooling Output Ratio Function of Part Load Ratio Curve Name",
                    "field_type": "a"
                },
                "heating_capacity_function_of_cooling_capacity_curve_name": {
                    "field_name": "Heating Capacity Function of Cooling Capacity Curve Name",
                    "field_type": "a"
                },
                "fuel_input_to_heat_output_ratio_during_heating_only_operation_curve_name": {
                    "field_name": "Fuel Input to Heat Output Ratio During Heating Only Operation Curve Name",
                    "field_type": "a"
                },
                "temperature_curve_input_variable": {
                    "field_name": "Temperature Curve Input Variable",
                    "field_type": "a"
                },
                "condenser_type": {
                    "field_name": "Condenser Type",
                    "field_type": "a"
                },
                "chilled_water_temperature_lower_limit": {
                    "field_name": "Chilled Water Temperature Lower Limit",
                    "field_type": "n"
                },
                "fuel_higher_heating_value": {
                    "field_name": "Fuel Higher Heating Value",
                    "field_type": "n"
                },
                "fuel_type": {
                    "field_name": "Fuel Type",
                    "field_type": "a"
                },
                "sizing_factor": {
                    "field_name": "Sizing Factor",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "nominal_cooling_capacity",
                "heating_to_cooling_capacity_ratio",
                "fuel_input_to_cooling_output_ratio",
                "fuel_input_to_heating_output_ratio",
                "electric_input_to_cooling_output_ratio",
                "electric_input_to_heating_output_ratio",
                "chilled_water_inlet_node_name",
                "chilled_water_outlet_node_name",
                "condenser_inlet_node_name",
                "condenser_outlet_node_name",
                "hot_water_inlet_node_name",
                "hot_water_outlet_node_name",
                "minimum_part_load_ratio",
                "maximum_part_load_ratio",
                "optimum_part_load_ratio",
                "design_entering_condenser_water_temperature",
                "design_leaving_chilled_water_temperature",
                "design_chilled_water_flow_rate",
                "design_condenser_water_flow_rate",
                "design_hot_water_flow_rate",
                "cooling_capacity_function_of_temperature_curve_name",
                "fuel_input_to_cooling_output_ratio_function_of_temperature_curve_name",
                "fuel_input_to_cooling_output_ratio_function_of_part_load_ratio_curve_name",
                "electric_input_to_cooling_output_ratio_function_of_temperature_curve_name",
                "electric_input_to_cooling_output_ratio_function_of_part_load_ratio_curve_name",
                "heating_capacity_function_of_cooling_capacity_curve_name",
                "fuel_input_to_heat_output_ratio_during_heating_only_operation_curve_name",
                "temperature_curve_input_variable",
                "condenser_type",
                "chilled_water_temperature_lower_limit",
                "fuel_higher_heating_value",
                "fuel_type",
                "sizing_factor"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "chilled_water_inlet_node_name",
                    "chilled_water_outlet_node_name",
                    "condenser_inlet_node_name",
                    "condenser_outlet_node_name",
                    "hot_water_inlet_node_name",
                    "hot_water_outlet_node_name",
                    "cooling_capacity_function_of_temperature_curve_name",
                    "fuel_input_to_cooling_output_ratio_function_of_temperature_curve_name",
                    "fuel_input_to_cooling_output_ratio_function_of_part_load_ratio_curve_name",
                    "electric_input_to_cooling_output_ratio_function_of_temperature_curve_name",
                    "electric_input_to_cooling_output_ratio_function_of_part_load_ratio_curve_name",
                    "heating_capacity_function_of_cooling_capacity_curve_name",
                    "fuel_input_to_heat_output_ratio_during_heating_only_operation_curve_name",
                    "temperature_curve_input_variable",
                    "condenser_type",
                    "fuel_type"
                ]
            },
            "numerics": {
                "fields": [
                    "nominal_cooling_capacity",
                    "heating_to_cooling_capacity_ratio",
                    "fuel_input_to_cooling_output_ratio",
                    "fuel_input_to_heating_output_ratio",
                    "electric_input_to_cooling_output_ratio",
                    "electric_input_to_heating_output_ratio",
                    "minimum_part_load_ratio",
                    "maximum_part_load_ratio",
                    "optimum_part_load_ratio",
                    "design_entering_condenser_water_temperature",
                    "design_leaving_chilled_water_temperature",
                    "design_chilled_water_flow_rate",
                    "design_condenser_water_flow_rate",
                    "design_hot_water_flow_rate",
                    "chilled_water_temperature_lower_limit",
                    "fuel_higher_heating_value",
                    "sizing_factor"
                ]
            }
        },
        "type": "object",
        "memo": "Direct fired gas absorption chiller-heater using performance curves similar to DOE-2",
        "min_fields": 34.0
    }
}
```
