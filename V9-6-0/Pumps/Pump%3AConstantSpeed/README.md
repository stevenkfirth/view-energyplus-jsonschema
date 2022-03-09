```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "inlet_node_name": {
                    "type": "string"
                },
                "outlet_node_name": {
                    "type": "string"
                },
                "design_flow_rate": {
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
                "design_pump_head": {
                    "type": "number",
                    "units": "Pa",
                    "default": 179352.0,
                    "note": "default head is 60 feet",
                    "ip-units": "ftH2O"
                },
                "design_power_consumption": {
                    "note": "When autosized the type of scaling factor is chosen in the input field Design Power Sizing Method",
                    "units": "W",
                    "ip-units": "W",
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
                "motor_efficiency": {
                    "type": "number",
                    "note": "This is the motor efficiency only. When the Design Power Consumption is autosized using PowerPerFlowPerPressure, the Design Shaft Power per Unit Flow Rate per Unit Head is used in addition to the motor efficiency.",
                    "exclusiveMinimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.9
                },
                "fraction_of_motor_inefficiencies_to_fluid_stream": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.0
                },
                "pump_control_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "Continuous",
                        "Intermittent"
                    ],
                    "default": "Continuous"
                },
                "pump_flow_rate_schedule_name": {
                    "type": "string",
                    "note": "Modifies the rated flow rate of the pump on a time basis. Default is that the pump is on and runs according to its other operational requirements specified above. The schedule is for special pump operations.",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "pump_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "This references any single independent variable polynomial curve in order to do pressure vs. flow calculations for this pump. The available types are then: Linear, Quadratic, Cubic, and Quartic The non-dimensional pump pressure relationship is of the following form: (psi = C4*phi^4 + C3*phi^3 + C2*phi^2 + C1*phi + C0) Where the non-dimensional variables are defined as: delP = rho * ((N/60)^2) * (D^2) * psi mdot = rho * (N/60) * (D^3) * phi"
                },
                "impeller_diameter": {
                    "type": "number",
                    "units": "m",
                    "note": "\"D\" in above expression in field A6"
                },
                "rotational_speed": {
                    "type": "number",
                    "units": "rev/min",
                    "note": "\"N\" in above expression in field A6"
                },
                "zone_name": {
                    "type": "string",
                    "note": "optional, if used pump losses transfered to zone as internal gains",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ]
                },
                "skin_loss_radiative_fraction": {
                    "type": "number",
                    "note": "optional. If zone identified in previous field then this determines the split between convection and radiation for the skin losses",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "design_power_sizing_method": {
                    "type": "string",
                    "note": "Used to indicate which sizing factor is used to calculate Design Power Consumption. PowerPerFlow indicates that Design Electric Power per Unit Flow Rate is used as scaling factor. Design Power Consumption = Design Maximum Flow Rate * scaling factor PowerPerFlowPerPressure indicates that Design Shaft Power per Unit Flow Rate per Unit Head is used as scaling factor. Design Power Consumption = Design Maximum Flow Rate * Design Pump Head * scaling factor / Motor Efficiency",
                    "enum": [
                        "",
                        "PowerPerFlow",
                        "PowerPerFlowPerPressure"
                    ],
                    "default": "PowerPerFlowPerPressure"
                },
                "design_electric_power_per_unit_flow_rate": {
                    "type": "number",
                    "note": "Used to size Design Power Consumption from design flow rate",
                    "default": 348701.1,
                    "units": "W/(m3/s)",
                    "ip-units": "W/(gal/min)",
                    "exclusiveMinimum": 0.0
                },
                "design_shaft_power_per_unit_flow_rate_per_unit_head": {
                    "type": "number",
                    "note": "Used to size Design Power Consumption from design flow rate for head and motor efficiency",
                    "default": 1.282051282,
                    "units": "W/((m3/s)-Pa)",
                    "ip-units": "W/((gal/min)-ftH20)",
                    "exclusiveMinimum": 0.0
                },
                "end_use_subcategory": {
                    "type": "string",
                    "note": "Any text may be used here to categorize the end-uses in the ABUPS End Uses by Subcategory table.",
                    "retaincase": true,
                    "default": "General"
                }
            },
            "required": [
                "inlet_node_name",
                "outlet_node_name"
            ]
        }
    },
    "group": "Pumps",
    "name": {
        "type": "string",
        "is_required": true,
        "reference-class-name": [
            "validBranchEquipmentTypes"
        ],
        "reference": [
            "validBranchEquipmentNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "inlet_node_name": {
                "field_name": "Inlet Node Name",
                "field_type": "a"
            },
            "outlet_node_name": {
                "field_name": "Outlet Node Name",
                "field_type": "a"
            },
            "design_flow_rate": {
                "field_name": "Design Flow Rate",
                "field_type": "n"
            },
            "design_pump_head": {
                "field_name": "Design Pump Head",
                "field_type": "n"
            },
            "design_power_consumption": {
                "field_name": "Design Power Consumption",
                "field_type": "n"
            },
            "motor_efficiency": {
                "field_name": "Motor Efficiency",
                "field_type": "n"
            },
            "fraction_of_motor_inefficiencies_to_fluid_stream": {
                "field_name": "Fraction of Motor Inefficiencies to Fluid Stream",
                "field_type": "n"
            },
            "pump_control_type": {
                "field_name": "Pump Control Type",
                "field_type": "a"
            },
            "pump_flow_rate_schedule_name": {
                "field_name": "Pump Flow Rate Schedule Name",
                "field_type": "a"
            },
            "pump_curve_name": {
                "field_name": "Pump Curve Name",
                "field_type": "a"
            },
            "impeller_diameter": {
                "field_name": "Impeller Diameter",
                "field_type": "n"
            },
            "rotational_speed": {
                "field_name": "Rotational Speed",
                "field_type": "n"
            },
            "zone_name": {
                "field_name": "Zone Name",
                "field_type": "a"
            },
            "skin_loss_radiative_fraction": {
                "field_name": "Skin Loss Radiative Fraction",
                "field_type": "n"
            },
            "design_power_sizing_method": {
                "field_name": "Design Power Sizing Method",
                "field_type": "a"
            },
            "design_electric_power_per_unit_flow_rate": {
                "field_name": "Design Electric Power per Unit Flow Rate",
                "field_type": "n"
            },
            "design_shaft_power_per_unit_flow_rate_per_unit_head": {
                "field_name": "Design Shaft Power per Unit Flow Rate per Unit Head",
                "field_type": "n"
            },
            "end_use_subcategory": {
                "field_name": "End-Use Subcategory",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "inlet_node_name",
            "outlet_node_name",
            "design_flow_rate",
            "design_pump_head",
            "design_power_consumption",
            "motor_efficiency",
            "fraction_of_motor_inefficiencies_to_fluid_stream",
            "pump_control_type",
            "pump_flow_rate_schedule_name",
            "pump_curve_name",
            "impeller_diameter",
            "rotational_speed",
            "zone_name",
            "skin_loss_radiative_fraction",
            "design_power_sizing_method",
            "design_electric_power_per_unit_flow_rate",
            "design_shaft_power_per_unit_flow_rate_per_unit_head",
            "end_use_subcategory"
        ],
        "alphas": {
            "fields": [
                "name",
                "inlet_node_name",
                "outlet_node_name",
                "pump_control_type",
                "pump_flow_rate_schedule_name",
                "pump_curve_name",
                "zone_name",
                "design_power_sizing_method",
                "end_use_subcategory"
            ]
        },
        "numerics": {
            "fields": [
                "design_flow_rate",
                "design_pump_head",
                "design_power_consumption",
                "motor_efficiency",
                "fraction_of_motor_inefficiencies_to_fluid_stream",
                "impeller_diameter",
                "rotational_speed",
                "skin_loss_radiative_fraction",
                "design_electric_power_per_unit_flow_rate",
                "design_shaft_power_per_unit_flow_rate_per_unit_head"
            ]
        }
    },
    "type": "object",
    "memo": "This pump model is described in the ASHRAE secondary HVAC toolkit.",
    "min_fields": 9.0
}
```
