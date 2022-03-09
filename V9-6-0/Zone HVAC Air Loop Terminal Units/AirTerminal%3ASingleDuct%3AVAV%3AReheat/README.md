```
{
    "AirTerminal:SingleDuct:VAV:Reheat": {
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
                    "damper_air_outlet_node_name": {
                        "type": "string",
                        "note": "the outlet node of the damper and the inlet node of the reheat coil this is an internal node to the terminal unit and connects the damper and reheat coil"
                    },
                    "air_inlet_node_name": {
                        "type": "string",
                        "note": "the inlet node to the terminal unit and the damper"
                    },
                    "maximum_air_flow_rate": {
                        "units": "m3/s",
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
                    "zone_minimum_air_flow_input_method": {
                        "type": "string",
                        "enum": [
                            "",
                            "Constant",
                            "FixedFlowRate",
                            "Scheduled"
                        ],
                        "default": "Constant",
                        "note": "Constant = Constant Minimum Air Flow Fraction (a fraction of Maximum Air Flow Rate) FixedFlowRate = Fixed Minimum Air Flow Rate (a fixed minimum air volume flow rate) Scheduled = Scheduled Minimum Air Flow Fraction (a fraction of Maximum Air Flow"
                    },
                    "constant_minimum_air_flow_fraction": {
                        "default": "Autosize",
                        "note": "This field is used if the field Zone Minimum Air Flow Input Method is Constant If the field Zone Minimum Air Flow Input Method is Scheduled, then this field is optional; if a value is entered, then it is used for sizing normal-action reheat coils. If both this field and the following field are entered, the larger result is used. The values for autosizing are picked up from the Sizing:Zone input fields \"Cooling Minimum Air Flow per Zone Floor Area\", \"Cooling Minimum Air Flow\", and \"Cooling Minimum Air Flow Fraction\". If there is no sizing calculation a default of 0.000762 m3/s-m2 (0.15 cfm/ft2) is used.",
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
                    "fixed_minimum_air_flow_rate": {
                        "units": "m3/s",
                        "default": "Autosize",
                        "note": "This field is used if the field Zone Minimum Air Flow Input Method is FixedFlowRate. If the field Zone Minimum Air Flow Input Method is Scheduled, then this field is optional; if a value is entered, then it is used for sizing normal-action reheat coils. If both this field and the previous field are entered, the larger result is used. The values for autosizing are picked up from the Sizing:Zone input fields \"Cooling Minimum Air Flow per Zone Floor Area\", \"Cooling Minimum Air Flow\", and \"Cooling Minimum Air Flow Fraction\". If there is no sizing calculation a default of 0.000762 m3/s-m2 (0.15 cfm/ft2) is used.",
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
                    "minimum_air_flow_fraction_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "This field is used if the field Zone Minimum Air Flow Input Method is Scheduled Schedule values are fractions, 0.0 to 1.0. If the field Constant Minimum Air Flow Fraction is blank, then the average of the minimum and maximum schedule values is used for sizing normal-action reheat coils."
                    },
                    "reheat_coil_object_type": {
                        "type": "string",
                        "enum": [
                            "Coil:Heating:Electric",
                            "Coil:Heating:Fuel",
                            "Coil:Heating:Steam",
                            "Coil:Heating:Water"
                        ]
                    },
                    "reheat_coil_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "HeatingCoilName"
                        ]
                    },
                    "maximum_hot_water_or_steam_flow_rate": {
                        "note": "Not used when reheat coil type is gas or electric",
                        "units": "m3/s",
                        "ip-units": "gal/min",
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
                    "minimum_hot_water_or_steam_flow_rate": {
                        "type": "number",
                        "note": "Not used when reheat coil type is gas or electric",
                        "units": "m3/s",
                        "minimum": 0.0,
                        "default": 0.0,
                        "ip-units": "gal/min"
                    },
                    "air_outlet_node_name": {
                        "type": "string",
                        "note": "The outlet node of the terminal unit and the reheat coil. This is also the zone inlet node."
                    },
                    "convergence_tolerance": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "default": 0.001
                    },
                    "damper_heating_action": {
                        "type": "string",
                        "enum": [
                            "",
                            "Normal",
                            "Reverse",
                            "ReverseWithLimits"
                        ],
                        "default": "ReverseWithLimits",
                        "note": "Normal means the damper is fixed at the minimum position in heating mode Reverse means the damper can open fully during reheat ReverseWithLimits means the damper will open partially during reheat as specified in the following 2 fields"
                    },
                    "maximum_flow_per_zone_floor_area_during_reheat": {
                        "units": "m3/s-m2",
                        "default": "Autosize",
                        "note": "Used only when Reheat Coil Object Type = Coil:Heating:Water and Damper Heating Action = ReverseWithLimits When autocalculating, the maximum flow per zone is set to 0.002032 m3/s-m2 (0.4 cfm/sqft) This optional field limits the maximum flow allowed in reheat mode. At no time will the maximum flow rate calculated here exceed the value of Maximum Air Flow Rate.",
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
                    "maximum_flow_fraction_during_reheat": {
                        "default": "Autosize",
                        "note": "Used only when Reheat Coil Object Type = Coil:Heating:Water and Damper Heating Action = ReverseWithLimits When autocalculating, the maximum flow fraction is set to the ratio of 0.002032 m3/s-m2 (0.4 cfm/sqft) multiplied by the zone floor area and the Maximum Air Flow Rate. This optional field limits the maximum flow allowed in reheat mode. At no time will the maximum flow rate calculated here exceed the value of Maximum Air Flow Rate.",
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
                    "maximum_reheat_air_temperature": {
                        "type": "number",
                        "units": "C",
                        "exclusiveMinimum": 0.0,
                        "note": "Specifies the maximum allowable supply air temperature leaving the reheat coil. If left blank, there is no limit and no default. If unknown, 35C (95F) is recommended."
                    },
                    "design_specification_outdoor_air_object_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "DSOASpaceListNames",
                            "DesignSpecificationOutdoorAirNames"
                        ],
                        "note": "When the name of a DesignSpecification:OutdoorAir object is entered, the terminal unit will increase flow as needed to meet this outdoor air requirement. If Outdoor Air Flow per Person is non-zero, then the outdoor air requirement will be computed based on the current number of occupants in the zone. At no time will the supply air flow rate exceed the value for Maximum Air Flow Rate. If this field is blank, then the terminal unit will not be controlled for outdoor air flow."
                    },
                    "minimum_air_flow_turndown_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "This field adjusts the design minimum flow rate by multiplying it using this schedule of fraction values. This field can be used with any of the three \"Zone Minimum Air Flow Input Method\". Schedule values are fractions, 0.0 to 1.0. This field adjusts the minimum airflow turndown below the design minimum air flow and is intended for use with ASHRAE Standard 170. If this field is left blank, then the turndown minimum air flow fraction value is set to 1."
                    }
                },
                "required": [
                    "damper_air_outlet_node_name",
                    "air_inlet_node_name",
                    "maximum_air_flow_rate",
                    "reheat_coil_object_type",
                    "reheat_coil_name",
                    "air_outlet_node_name"
                ]
            }
        },
        "group": "Zone HVAC Air Loop Terminal Units",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "AFNTerminalUnitNames",
                "AirTerminalUnitNames"
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
                "damper_air_outlet_node_name": {
                    "field_name": "Damper Air Outlet Node Name",
                    "field_type": "a"
                },
                "air_inlet_node_name": {
                    "field_name": "Air Inlet Node Name",
                    "field_type": "a"
                },
                "maximum_air_flow_rate": {
                    "field_name": "Maximum Air Flow Rate",
                    "field_type": "n"
                },
                "zone_minimum_air_flow_input_method": {
                    "field_name": "Zone Minimum Air Flow Input Method",
                    "field_type": "a"
                },
                "constant_minimum_air_flow_fraction": {
                    "field_name": "Constant Minimum Air Flow Fraction",
                    "field_type": "n"
                },
                "fixed_minimum_air_flow_rate": {
                    "field_name": "Fixed Minimum Air Flow Rate",
                    "field_type": "n"
                },
                "minimum_air_flow_fraction_schedule_name": {
                    "field_name": "Minimum Air Flow Fraction Schedule Name",
                    "field_type": "a"
                },
                "reheat_coil_object_type": {
                    "field_name": "Reheat Coil Object Type",
                    "field_type": "a"
                },
                "reheat_coil_name": {
                    "field_name": "Reheat Coil Name",
                    "field_type": "a"
                },
                "maximum_hot_water_or_steam_flow_rate": {
                    "field_name": "Maximum Hot Water or Steam Flow Rate",
                    "field_type": "n"
                },
                "minimum_hot_water_or_steam_flow_rate": {
                    "field_name": "Minimum Hot Water or Steam Flow Rate",
                    "field_type": "n"
                },
                "air_outlet_node_name": {
                    "field_name": "Air Outlet Node Name",
                    "field_type": "a"
                },
                "convergence_tolerance": {
                    "field_name": "Convergence Tolerance",
                    "field_type": "n"
                },
                "damper_heating_action": {
                    "field_name": "Damper Heating Action",
                    "field_type": "a"
                },
                "maximum_flow_per_zone_floor_area_during_reheat": {
                    "field_name": "Maximum Flow per Zone Floor Area During Reheat",
                    "field_type": "n"
                },
                "maximum_flow_fraction_during_reheat": {
                    "field_name": "Maximum Flow Fraction During Reheat",
                    "field_type": "n"
                },
                "maximum_reheat_air_temperature": {
                    "field_name": "Maximum Reheat Air Temperature",
                    "field_type": "n"
                },
                "design_specification_outdoor_air_object_name": {
                    "field_name": "Design Specification Outdoor Air Object Name",
                    "field_type": "a"
                },
                "minimum_air_flow_turndown_schedule_name": {
                    "field_name": "Minimum Air Flow Turndown Schedule Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "availability_schedule_name",
                "damper_air_outlet_node_name",
                "air_inlet_node_name",
                "maximum_air_flow_rate",
                "zone_minimum_air_flow_input_method",
                "constant_minimum_air_flow_fraction",
                "fixed_minimum_air_flow_rate",
                "minimum_air_flow_fraction_schedule_name",
                "reheat_coil_object_type",
                "reheat_coil_name",
                "maximum_hot_water_or_steam_flow_rate",
                "minimum_hot_water_or_steam_flow_rate",
                "air_outlet_node_name",
                "convergence_tolerance",
                "damper_heating_action",
                "maximum_flow_per_zone_floor_area_during_reheat",
                "maximum_flow_fraction_during_reheat",
                "maximum_reheat_air_temperature",
                "design_specification_outdoor_air_object_name",
                "minimum_air_flow_turndown_schedule_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "damper_air_outlet_node_name",
                    "air_inlet_node_name",
                    "zone_minimum_air_flow_input_method",
                    "minimum_air_flow_fraction_schedule_name",
                    "reheat_coil_object_type",
                    "reheat_coil_name",
                    "air_outlet_node_name",
                    "damper_heating_action",
                    "design_specification_outdoor_air_object_name",
                    "minimum_air_flow_turndown_schedule_name"
                ]
            },
            "numerics": {
                "fields": [
                    "maximum_air_flow_rate",
                    "constant_minimum_air_flow_fraction",
                    "fixed_minimum_air_flow_rate",
                    "maximum_hot_water_or_steam_flow_rate",
                    "minimum_hot_water_or_steam_flow_rate",
                    "convergence_tolerance",
                    "maximum_flow_per_zone_floor_area_during_reheat",
                    "maximum_flow_fraction_during_reheat",
                    "maximum_reheat_air_temperature"
                ]
            }
        },
        "type": "object",
        "memo": "Central air system terminal unit, single duct, variable volume, with reheat coil (hot water, electric, gas, or steam).",
        "min_fields": 18.0
    }
}
```
