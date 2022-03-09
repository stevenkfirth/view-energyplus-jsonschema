```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "nominal_capacity": {
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
                "nominal_pumping_power": {
                    "units": "W",
                    "ip-units": "W",
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
                    "type": "string"
                },
                "minimum_part_load_ratio": {
                    "type": "number",
                    "minimum": 0.0
                },
                "maximum_part_load_ratio": {
                    "type": "number",
                    "minimum": 0.0
                },
                "optimum_part_load_ratio": {
                    "type": "number",
                    "minimum": 0.0
                },
                "design_condenser_inlet_temperature": {
                    "type": "number",
                    "units": "C"
                },
                "design_chilled_water_flow_rate": {
                    "note": "For variable volume this is the max flow & for constant flow this is the flow.",
                    "units": "m3/s",
                    "ip-units": "gal/min",
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
                "design_condenser_water_flow_rate": {
                    "note": "The steam use coefficients below specify the steam use as a fraction of chiller operating capacity",
                    "units": "m3/s",
                    "ip-units": "gal/min",
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
                "coefficient_1_of_the_hot_water_or_steam_use_part_load_ratio_curve": {
                    "type": "number"
                },
                "coefficient_2_of_the_hot_water_or_steam_use_part_load_ratio_curve": {
                    "type": "number"
                },
                "coefficient_3_of_the_hot_water_or_steam_use_part_load_ratio_curve": {
                    "type": "number"
                },
                "coefficient_1_of_the_pump_electric_use_part_load_ratio_curve": {
                    "type": "number",
                    "note": "The pump electric use coefficients specify the pumping power as a Fraction of Nominal pumping power"
                },
                "coefficient_2_of_the_pump_electric_use_part_load_ratio_curve": {
                    "type": "number"
                },
                "coefficient_3_of_the_pump_electric_use_part_load_ratio_curve": {
                    "type": "number"
                },
                "chilled_water_outlet_temperature_lower_limit": {
                    "type": "number",
                    "units": "C"
                },
                "generator_inlet_node_name": {
                    "type": "string"
                },
                "generator_outlet_node_name": {
                    "type": "string"
                },
                "chiller_flow_mode": {
                    "type": "string",
                    "note": "Select operating mode for fluid flow through the chiller. \"NotModulated\" is for either variable or constant pumping with flow controlled by the external plant system. \"ConstantFlow\" is for constant pumping with flow controlled by chiller to operate at full design flow rate. \"LeavingSetpointModulated\" is for variable pumping with flow controlled by chiller to vary flow to target a leaving temperature setpoint.",
                    "enum": [
                        "",
                        "ConstantFlow",
                        "LeavingSetpointModulated",
                        "NotModulated"
                    ],
                    "default": "NotModulated"
                },
                "generator_heat_source_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "HotWater",
                        "Steam"
                    ],
                    "default": "Steam",
                    "note": "The Generator side of the chiller can be connected to a hot water or steam plant where the generator inlet and outlet nodes are connected to a plant loop. If the generator is not connected to a plant loop, and the generator inlet/outlet nodes are not used, this field should be specified as steam or left blank. When a plant is not used, the model assumes steam as the heat source."
                },
                "design_generator_fluid_flow_rate": {
                    "units": "m3/s",
                    "ip-units": "gal/min",
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
                "degree_of_subcooling_in_steam_generator": {
                    "type": "number",
                    "units": "C",
                    "default": 1.0,
                    "note": "This field is not used when the generator inlet/outlet nodes are not specified or the generator is connected to a hot water loop."
                },
                "sizing_factor": {
                    "type": "number",
                    "note": "Multiplies the autosized capacity and flow rates",
                    "exclusiveMinimum": 0.0,
                    "default": 1.0
                }
            },
            "required": [
                "nominal_capacity",
                "nominal_pumping_power",
                "chilled_water_inlet_node_name",
                "chilled_water_outlet_node_name",
                "condenser_inlet_node_name",
                "condenser_outlet_node_name"
            ]
        }
    },
    "group": "Plant Heating and Cooling Equipment",
    "name": {
        "type": "string",
        "reference": [
            "Chillers",
            "validBranchEquipmentNames",
            "validPlantEquipmentNames"
        ],
        "is_required": true,
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
            "nominal_capacity": {
                "field_name": "Nominal Capacity",
                "field_type": "n"
            },
            "nominal_pumping_power": {
                "field_name": "Nominal Pumping Power",
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
            "design_condenser_inlet_temperature": {
                "field_name": "Design Condenser Inlet Temperature",
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
            "coefficient_1_of_the_hot_water_or_steam_use_part_load_ratio_curve": {
                "field_name": "Coefficient 1 of the Hot Water or Steam Use Part Load Ratio Curve",
                "field_type": "n"
            },
            "coefficient_2_of_the_hot_water_or_steam_use_part_load_ratio_curve": {
                "field_name": "Coefficient 2 of the Hot Water or Steam Use Part Load Ratio Curve",
                "field_type": "n"
            },
            "coefficient_3_of_the_hot_water_or_steam_use_part_load_ratio_curve": {
                "field_name": "Coefficient 3 of the Hot Water or Steam Use Part Load Ratio Curve",
                "field_type": "n"
            },
            "coefficient_1_of_the_pump_electric_use_part_load_ratio_curve": {
                "field_name": "Coefficient 1 of the Pump Electric Use Part Load Ratio Curve",
                "field_type": "n"
            },
            "coefficient_2_of_the_pump_electric_use_part_load_ratio_curve": {
                "field_name": "Coefficient 2 of the Pump Electric Use Part Load Ratio Curve",
                "field_type": "n"
            },
            "coefficient_3_of_the_pump_electric_use_part_load_ratio_curve": {
                "field_name": "Coefficient 3 of the Pump Electric Use Part Load Ratio Curve",
                "field_type": "n"
            },
            "chilled_water_outlet_temperature_lower_limit": {
                "field_name": "Chilled Water Outlet Temperature Lower Limit",
                "field_type": "n"
            },
            "generator_inlet_node_name": {
                "field_name": "Generator Inlet Node Name",
                "field_type": "a"
            },
            "generator_outlet_node_name": {
                "field_name": "Generator Outlet Node Name",
                "field_type": "a"
            },
            "chiller_flow_mode": {
                "field_name": "Chiller Flow Mode",
                "field_type": "a"
            },
            "generator_heat_source_type": {
                "field_name": "Generator Heat Source Type",
                "field_type": "a"
            },
            "design_generator_fluid_flow_rate": {
                "field_name": "Design Generator Fluid Flow Rate",
                "field_type": "n"
            },
            "degree_of_subcooling_in_steam_generator": {
                "field_name": "Degree of Subcooling in Steam Generator",
                "field_type": "n"
            },
            "sizing_factor": {
                "field_name": "Sizing Factor",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "nominal_capacity",
            "nominal_pumping_power",
            "chilled_water_inlet_node_name",
            "chilled_water_outlet_node_name",
            "condenser_inlet_node_name",
            "condenser_outlet_node_name",
            "minimum_part_load_ratio",
            "maximum_part_load_ratio",
            "optimum_part_load_ratio",
            "design_condenser_inlet_temperature",
            "design_chilled_water_flow_rate",
            "design_condenser_water_flow_rate",
            "coefficient_1_of_the_hot_water_or_steam_use_part_load_ratio_curve",
            "coefficient_2_of_the_hot_water_or_steam_use_part_load_ratio_curve",
            "coefficient_3_of_the_hot_water_or_steam_use_part_load_ratio_curve",
            "coefficient_1_of_the_pump_electric_use_part_load_ratio_curve",
            "coefficient_2_of_the_pump_electric_use_part_load_ratio_curve",
            "coefficient_3_of_the_pump_electric_use_part_load_ratio_curve",
            "chilled_water_outlet_temperature_lower_limit",
            "generator_inlet_node_name",
            "generator_outlet_node_name",
            "chiller_flow_mode",
            "generator_heat_source_type",
            "design_generator_fluid_flow_rate",
            "degree_of_subcooling_in_steam_generator",
            "sizing_factor"
        ],
        "alphas": {
            "fields": [
                "name",
                "chilled_water_inlet_node_name",
                "chilled_water_outlet_node_name",
                "condenser_inlet_node_name",
                "condenser_outlet_node_name",
                "generator_inlet_node_name",
                "generator_outlet_node_name",
                "chiller_flow_mode",
                "generator_heat_source_type"
            ]
        },
        "numerics": {
            "fields": [
                "nominal_capacity",
                "nominal_pumping_power",
                "minimum_part_load_ratio",
                "maximum_part_load_ratio",
                "optimum_part_load_ratio",
                "design_condenser_inlet_temperature",
                "design_chilled_water_flow_rate",
                "design_condenser_water_flow_rate",
                "coefficient_1_of_the_hot_water_or_steam_use_part_load_ratio_curve",
                "coefficient_2_of_the_hot_water_or_steam_use_part_load_ratio_curve",
                "coefficient_3_of_the_hot_water_or_steam_use_part_load_ratio_curve",
                "coefficient_1_of_the_pump_electric_use_part_load_ratio_curve",
                "coefficient_2_of_the_pump_electric_use_part_load_ratio_curve",
                "coefficient_3_of_the_pump_electric_use_part_load_ratio_curve",
                "chilled_water_outlet_temperature_lower_limit",
                "design_generator_fluid_flow_rate",
                "degree_of_subcooling_in_steam_generator",
                "sizing_factor"
            ]
        }
    },
    "type": "object",
    "memo": "This indirect absorption chiller model is the empirical model from the Building Loads and System Thermodynamics (BLAST) program. Chiller performance curves are generated by fitting catalog data to third order polynomial equations. Two sets of coefficients are required.",
    "min_fields": 23.0
}
```
