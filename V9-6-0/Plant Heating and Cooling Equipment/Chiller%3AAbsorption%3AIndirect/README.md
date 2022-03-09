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
                    "units": "C",
                    "default": 30.0,
                    "note": "Used only when condenser flow rate is autosized."
                },
                "condenser_inlet_temperature_lower_limit": {
                    "type": "number",
                    "units": "C",
                    "default": 15.0,
                    "note": "Provides warnings when entering condenser temperature is below minimum. Capacity is not adjusted when entering condenser temperature is below minimum."
                },
                "chilled_water_outlet_temperature_lower_limit": {
                    "type": "number",
                    "units": "C",
                    "default": 5.0,
                    "note": "Capacity is adjusted when leaving chilled water temperature is below minimum."
                },
                "design_chilled_water_flow_rate": {
                    "units": "m3/s",
                    "default": "Autosize",
                    "ip-units": "gal/min",
                    "note": "For variable flow this is the max flow & for constant flow this is the flow.",
                    "anyOf": [
                        {
                            "type": "number",
                            "exclusiveMinimum": 0.0
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
                    "units": "m3/s",
                    "default": "Autosize",
                    "ip-units": "gal/min",
                    "anyOf": [
                        {
                            "type": "number",
                            "exclusiveMinimum": 0.0
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
                "generator_heat_input_function_of_part_load_ratio_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "pump_electric_input_function_of_part_load_ratio_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "generator_inlet_node_name": {
                    "type": "string",
                    "note": "Enter the generator inlet node name which connects this chiller to a steam or hot water plant, otherwise leave this field blank. Generator nodes are used to model heat input to the chiller."
                },
                "generator_outlet_node_name": {
                    "type": "string",
                    "note": "Enter the generator outlet node name which connects this chiller to a steam or hot water plant, otherwise leave this field blank. Generator nodes are used to model heat input to the chiller."
                },
                "capacity_correction_function_of_condenser_temperature_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "Curve which shows the change in normalized capacity to changes in condenser temperature."
                },
                "capacity_correction_function_of_chilled_water_temperature_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "Curve which shows the change in normalized capacity to changes in leaving chilled water temperature."
                },
                "capacity_correction_function_of_generator_temperature_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "Used when generator fluid type is hot water Curve which shows the change in normalized capacity to changes in generator temperature."
                },
                "generator_heat_input_correction_function_of_condenser_temperature_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "Curve which shows the change in normalized heat input to changes in condenser temperature."
                },
                "generator_heat_input_correction_function_of_chilled_water_temperature_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "Curve which shows the change in normalized heat input to changes in leaving chilled water temperature."
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
                    "note": "For variable flow this is the max flow and for constant flow this is the flow.",
                    "anyOf": [
                        {
                            "type": "number"
                        },
                        {
                            "type": "string",
                            "enum": [
                                "Autosize"
                            ]
                        }
                    ]
                },
                "temperature_lower_limit_generator_inlet": {
                    "type": "number",
                    "units": "C",
                    "default": 0.0,
                    "note": "Provides warnings when entering generator temperature is below minimum. Capacity is not adjusted when entering generator temperature is below minimum."
                },
                "degree_of_subcooling_in_steam_generator": {
                    "type": "number",
                    "units": "C",
                    "minimum": 0.0,
                    "maximum": 20.0,
                    "default": 1.0,
                    "note": "This field is not used when the generator inlet/outlet nodes are not specified or the generator is connected to a hot water loop."
                },
                "degree_of_subcooling_in_steam_condensate_loop": {
                    "type": "number",
                    "units": "C",
                    "minimum": 0.0,
                    "default": 0.0,
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
                "condenser_outlet_node_name",
                "generator_heat_input_function_of_part_load_ratio_curve_name"
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
            "condenser_inlet_temperature_lower_limit": {
                "field_name": "Condenser Inlet Temperature Lower Limit",
                "field_type": "n"
            },
            "chilled_water_outlet_temperature_lower_limit": {
                "field_name": "Chilled Water Outlet Temperature Lower Limit",
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
            "chiller_flow_mode": {
                "field_name": "Chiller Flow Mode",
                "field_type": "a"
            },
            "generator_heat_input_function_of_part_load_ratio_curve_name": {
                "field_name": "Generator Heat Input Function of Part Load Ratio Curve Name",
                "field_type": "a"
            },
            "pump_electric_input_function_of_part_load_ratio_curve_name": {
                "field_name": "Pump Electric Input Function of Part Load Ratio Curve Name",
                "field_type": "a"
            },
            "generator_inlet_node_name": {
                "field_name": "Generator Inlet Node Name",
                "field_type": "a"
            },
            "generator_outlet_node_name": {
                "field_name": "Generator Outlet Node Name",
                "field_type": "a"
            },
            "capacity_correction_function_of_condenser_temperature_curve_name": {
                "field_name": "Capacity Correction Function of Condenser Temperature Curve Name",
                "field_type": "a"
            },
            "capacity_correction_function_of_chilled_water_temperature_curve_name": {
                "field_name": "Capacity Correction Function of Chilled Water Temperature Curve Name",
                "field_type": "a"
            },
            "capacity_correction_function_of_generator_temperature_curve_name": {
                "field_name": "Capacity Correction Function of Generator Temperature Curve Name",
                "field_type": "a"
            },
            "generator_heat_input_correction_function_of_condenser_temperature_curve_name": {
                "field_name": "Generator Heat Input Correction Function of Condenser Temperature Curve Name",
                "field_type": "a"
            },
            "generator_heat_input_correction_function_of_chilled_water_temperature_curve_name": {
                "field_name": "Generator Heat Input Correction Function of Chilled Water Temperature Curve Name",
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
            "temperature_lower_limit_generator_inlet": {
                "field_name": "Temperature Lower Limit Generator Inlet",
                "field_type": "n"
            },
            "degree_of_subcooling_in_steam_generator": {
                "field_name": "Degree of Subcooling in Steam Generator",
                "field_type": "n"
            },
            "degree_of_subcooling_in_steam_condensate_loop": {
                "field_name": "Degree of Subcooling in Steam Condensate Loop",
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
            "condenser_inlet_temperature_lower_limit",
            "chilled_water_outlet_temperature_lower_limit",
            "design_chilled_water_flow_rate",
            "design_condenser_water_flow_rate",
            "chiller_flow_mode",
            "generator_heat_input_function_of_part_load_ratio_curve_name",
            "pump_electric_input_function_of_part_load_ratio_curve_name",
            "generator_inlet_node_name",
            "generator_outlet_node_name",
            "capacity_correction_function_of_condenser_temperature_curve_name",
            "capacity_correction_function_of_chilled_water_temperature_curve_name",
            "capacity_correction_function_of_generator_temperature_curve_name",
            "generator_heat_input_correction_function_of_condenser_temperature_curve_name",
            "generator_heat_input_correction_function_of_chilled_water_temperature_curve_name",
            "generator_heat_source_type",
            "design_generator_fluid_flow_rate",
            "temperature_lower_limit_generator_inlet",
            "degree_of_subcooling_in_steam_generator",
            "degree_of_subcooling_in_steam_condensate_loop",
            "sizing_factor"
        ],
        "alphas": {
            "fields": [
                "name",
                "chilled_water_inlet_node_name",
                "chilled_water_outlet_node_name",
                "condenser_inlet_node_name",
                "condenser_outlet_node_name",
                "chiller_flow_mode",
                "generator_heat_input_function_of_part_load_ratio_curve_name",
                "pump_electric_input_function_of_part_load_ratio_curve_name",
                "generator_inlet_node_name",
                "generator_outlet_node_name",
                "capacity_correction_function_of_condenser_temperature_curve_name",
                "capacity_correction_function_of_chilled_water_temperature_curve_name",
                "capacity_correction_function_of_generator_temperature_curve_name",
                "generator_heat_input_correction_function_of_condenser_temperature_curve_name",
                "generator_heat_input_correction_function_of_chilled_water_temperature_curve_name",
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
                "condenser_inlet_temperature_lower_limit",
                "chilled_water_outlet_temperature_lower_limit",
                "design_chilled_water_flow_rate",
                "design_condenser_water_flow_rate",
                "design_generator_fluid_flow_rate",
                "temperature_lower_limit_generator_inlet",
                "degree_of_subcooling_in_steam_generator",
                "degree_of_subcooling_in_steam_condensate_loop",
                "sizing_factor"
            ]
        }
    },
    "type": "object",
    "memo": "This indirect absorption chiller model is an enhanced model from the Building Loads and System Thermodynamics (BLAST) program. Chiller performance curves are generated by fitting catalog data to third order polynomial equations. The chiller capacity is a function of condenser, chilled water, and generator temperatures. The heat input is a function of part-load ratio, condenser temperature, and chilled water temperature.",
    "min_fields": 17.0
}
```
