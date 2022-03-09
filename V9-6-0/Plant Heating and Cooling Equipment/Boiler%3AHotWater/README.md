```
{
    "Boiler:HotWater": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "fuel_type": {
                        "type": "string",
                        "enum": [
                            "Coal",
                            "Diesel",
                            "Electricity",
                            "FuelOilNo1",
                            "FuelOilNo2",
                            "Gasoline",
                            "NaturalGas",
                            "OtherFuel1",
                            "OtherFuel2",
                            "Propane"
                        ]
                    },
                    "nominal_capacity": {
                        "units": "W",
                        "anyOf": [
                            {
                                "type": "number",
                                "minimum": 0.0
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "nominal_thermal_efficiency": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "maximum": 1.0,
                        "note": "Based on the higher heating value of fuel."
                    },
                    "efficiency_curve_temperature_evaluation_variable": {
                        "type": "string",
                        "enum": [
                            "EnteringBoiler",
                            "LeavingBoiler"
                        ]
                    },
                    "normalized_boiler_efficiency_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "BivariateFunctions",
                            "UnivariateFunctions"
                        ],
                        "note": "Linear, Quadratic and Cubic efficiency curves are solely a function of PLR. All other efficiency curve types are a function of PLR and boiler water temperature. Linear = C1 + C2*PLR Quadratic = C1 + C2*PLR + C3*PLR^2 Cubic = C1 + C2*PLR + C3*PLR^2 + C4*PLR^3 Biquadratic = C1 + C2*PLR + C3*PLR^2 + C4*T + C5*T^2 + C6*PLR*T QuadraticLinear = C1 + C2*PLR + C3*PLR^2 + (C4 + C5*PLR + C6*PLR^2)*T BiCubic = C1+C2*PLR+C3*PLR^2+C4*T+C5*T^2+C6*PLR*T+C7*PLR^3+C8*T^3+C9*PLR^2*T+C10*PLR*T^2 TriQuadratic curves are not allowed. PLR = part-load ratio T = boiler water temperature (either entering or leaving)."
                    },
                    "design_water_flow_rate": {
                        "units": "m3/s",
                        "ip-units": "gal/min",
                        "default": "Autosize",
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
                    "minimum_part_load_ratio": {
                        "type": "number",
                        "minimum": 0.0,
                        "default": 0.0
                    },
                    "maximum_part_load_ratio": {
                        "type": "number",
                        "minimum": 0.0,
                        "default": 1.0
                    },
                    "optimum_part_load_ratio": {
                        "type": "number",
                        "minimum": 0.0,
                        "default": 1.0
                    },
                    "boiler_water_inlet_node_name": {
                        "type": "string"
                    },
                    "boiler_water_outlet_node_name": {
                        "type": "string"
                    },
                    "water_outlet_upper_temperature_limit": {
                        "type": "number",
                        "units": "C",
                        "default": 99.9
                    },
                    "boiler_flow_mode": {
                        "type": "string",
                        "note": "Select operating mode for fluid flow through the boiler. \"NotModulated\" is for either variable or constant pumping with flow controlled by the external plant system. \"ConstantFlow\" is for constant pumping with flow controlled by boiler to operate at full design flow rate. \"LeavingSetpointModulated\" is for variable pumping with flow controlled by boiler to vary flow to target a leaving temperature setpoint.",
                        "enum": [
                            "",
                            "ConstantFlow",
                            "LeavingSetpointModulated",
                            "NotModulated"
                        ],
                        "default": "NotModulated"
                    },
                    "parasitic_electric_load": {
                        "type": "number",
                        "units": "W",
                        "minimum": 0.0,
                        "default": 0.0
                    },
                    "sizing_factor": {
                        "type": "number",
                        "note": "Multiplies the autosized capacity and flow rates",
                        "exclusiveMinimum": 0.0,
                        "default": 1.0
                    },
                    "end_use_subcategory": {
                        "type": "string",
                        "note": "Any text may be used here to categorize the end-uses in the ABUPS End Uses by Subcategory table.",
                        "retaincase": true,
                        "default": "General"
                    }
                },
                "required": [
                    "fuel_type",
                    "nominal_thermal_efficiency",
                    "boiler_water_inlet_node_name",
                    "boiler_water_outlet_node_name"
                ]
            }
        },
        "group": "Plant Heating and Cooling Equipment",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "Boilers",
                "validBranchEquipmentNames",
                "validPlantEquipmentNames"
            ],
            "reference-class-name": [
                "validBranchEquipmentTypes",
                "validPlantEquipmentTypes"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "fuel_type": {
                    "field_name": "Fuel Type",
                    "field_type": "a"
                },
                "nominal_capacity": {
                    "field_name": "Nominal Capacity",
                    "field_type": "n"
                },
                "nominal_thermal_efficiency": {
                    "field_name": "Nominal Thermal Efficiency",
                    "field_type": "n"
                },
                "efficiency_curve_temperature_evaluation_variable": {
                    "field_name": "Efficiency Curve Temperature Evaluation Variable",
                    "field_type": "a"
                },
                "normalized_boiler_efficiency_curve_name": {
                    "field_name": "Normalized Boiler Efficiency Curve Name",
                    "field_type": "a"
                },
                "design_water_flow_rate": {
                    "field_name": "Design Water Flow Rate",
                    "field_type": "n"
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
                "boiler_water_inlet_node_name": {
                    "field_name": "Boiler Water Inlet Node Name",
                    "field_type": "a"
                },
                "boiler_water_outlet_node_name": {
                    "field_name": "Boiler Water Outlet Node Name",
                    "field_type": "a"
                },
                "water_outlet_upper_temperature_limit": {
                    "field_name": "Water Outlet Upper Temperature Limit",
                    "field_type": "n"
                },
                "boiler_flow_mode": {
                    "field_name": "Boiler Flow Mode",
                    "field_type": "a"
                },
                "parasitic_electric_load": {
                    "field_name": "Parasitic Electric Load",
                    "field_type": "n"
                },
                "sizing_factor": {
                    "field_name": "Sizing Factor",
                    "field_type": "n"
                },
                "end_use_subcategory": {
                    "field_name": "End-Use Subcategory",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "fuel_type",
                "nominal_capacity",
                "nominal_thermal_efficiency",
                "efficiency_curve_temperature_evaluation_variable",
                "normalized_boiler_efficiency_curve_name",
                "design_water_flow_rate",
                "minimum_part_load_ratio",
                "maximum_part_load_ratio",
                "optimum_part_load_ratio",
                "boiler_water_inlet_node_name",
                "boiler_water_outlet_node_name",
                "water_outlet_upper_temperature_limit",
                "boiler_flow_mode",
                "parasitic_electric_load",
                "sizing_factor",
                "end_use_subcategory"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "fuel_type",
                    "efficiency_curve_temperature_evaluation_variable",
                    "normalized_boiler_efficiency_curve_name",
                    "boiler_water_inlet_node_name",
                    "boiler_water_outlet_node_name",
                    "boiler_flow_mode",
                    "end_use_subcategory"
                ]
            },
            "numerics": {
                "fields": [
                    "nominal_capacity",
                    "nominal_thermal_efficiency",
                    "design_water_flow_rate",
                    "minimum_part_load_ratio",
                    "maximum_part_load_ratio",
                    "optimum_part_load_ratio",
                    "water_outlet_upper_temperature_limit",
                    "parasitic_electric_load",
                    "sizing_factor"
                ]
            }
        },
        "type": "object",
        "memo": "This boiler model is an adaptation of the empirical model from the Building Loads and System Thermodynamics (BLAST) program. Boiler performance curves are generated by fitting catalog data to polynomial equations. A constant efficiency boiler may be modeled by leaving the normalized boiler efficiency curve name input blank.",
        "min_fields": 12.0
    }
}
```
