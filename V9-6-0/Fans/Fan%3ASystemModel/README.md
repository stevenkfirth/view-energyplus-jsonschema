```
{
    "Fan:SystemModel": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "availability_schedule_name": {
                        "type": "string",
                        "note": "Availability schedule name for this fan. Schedule value > 0 means the fan is available. If this field is blank, the fan is always available.",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "air_inlet_node_name": {
                        "type": "string"
                    },
                    "air_outlet_node_name": {
                        "type": "string"
                    },
                    "design_maximum_air_flow_rate": {
                        "units": "m3/s",
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
                    "speed_control_method": {
                        "type": "string",
                        "enum": [
                            "",
                            "Continuous",
                            "Discrete"
                        ],
                        "default": "Discrete"
                    },
                    "electric_power_minimum_flow_rate_fraction": {
                        "type": "number",
                        "default": 0.2,
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "design_pressure_rise": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "units": "Pa",
                        "ip-units": "inH2O"
                    },
                    "motor_efficiency": {
                        "type": "number",
                        "default": 0.9,
                        "exclusiveMinimum": 0.0,
                        "maximum": 1.0
                    },
                    "motor_in_air_stream_fraction": {
                        "type": "number",
                        "note": "0.0 means fan motor outside of air stream, 1.0 means motor inside of air stream",
                        "default": 1.0,
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "design_electric_power_consumption": {
                        "units": "W",
                        "default": "Autosize",
                        "note": "Fan power consumption at maximum air flow rate. If autosized the method used to scale power is chosen in the following field",
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
                    "design_power_sizing_method": {
                        "type": "string",
                        "enum": [
                            "",
                            "PowerPerFlow",
                            "PowerPerFlowPerPressure",
                            "TotalEfficiencyAndPressure"
                        ],
                        "default": "PowerPerFlowPerPressure"
                    },
                    "electric_power_per_unit_flow_rate": {
                        "type": "number",
                        "units": "W/(m3/s)",
                        "ip-units": "W/(ft3/min)"
                    },
                    "electric_power_per_unit_flow_rate_per_unit_pressure": {
                        "type": "number",
                        "units": "W/((m3/s)-Pa)",
                        "ip-units": "W/((ft3/min)-inH2O)",
                        "default": 1.66667
                    },
                    "fan_total_efficiency": {
                        "type": "number",
                        "default": 0.7,
                        "exclusiveMinimum": 0.0,
                        "maximum": 1.0
                    },
                    "electric_power_function_of_flow_fraction_curve_name": {
                        "type": "string",
                        "note": "independent variable is normalized flow rate, current flow divided by Design Maximum Air Flow Rate. dependent variable is modification factor multiplied by Design Power Consumption. This field is required if Speed Control Method is set to Continuous or if the Number of Speeds is greater than 1 and Speed Electric Power Fraction fields are not used.",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ]
                    },
                    "night_ventilation_mode_pressure_rise": {
                        "type": "number",
                        "note": "Total system fan pressure rise at the fan when in night mode using AvailabilityManager:NightVentilation",
                        "units": "Pa",
                        "ip-units": "inH2O"
                    },
                    "night_ventilation_mode_flow_fraction": {
                        "type": "number",
                        "note": "Fraction of Design Maximum Air Flow Rate to use when in night mode using AvailabilityManager:NightVentilation",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "motor_loss_zone_name": {
                        "type": "string",
                        "note": "optional, if used fan motor heat losses that not added to air stream are transferred to zone as internal gains",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ]
                    },
                    "motor_loss_radiative_fraction": {
                        "type": "number",
                        "note": "optional. If zone identified in previous field then this determines the split between convection and radiation for the fan motor's skin losses",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "end_use_subcategory": {
                        "type": "string",
                        "note": "Any text may be used here to categorize the end-uses in the ABUPS End Uses by Subcategory table.",
                        "retaincase": true,
                        "default": "General"
                    },
                    "number_of_speeds": {
                        "type": "number",
                        "note": "number of different speed levels available when Speed Control Method is set to Discrete Speed need to be arranged in increasing order in remaining field sets. If set to 1, or omitted, and Speed Control Method is Discrete then constant fan speed is the design maximum.",
                        "default": 1.0
                    },
                    "speed_fractions": {
                        "type": "array",
                        "items": {
                            "properties": {
                                "speed_flow_fraction": {
                                    "type": "number",
                                    "minimum": 0.0,
                                    "maximum": 1.0
                                },
                                "speed_electric_power_fraction": {
                                    "type": "number",
                                    "note": "if left blank then use Electric Power Function of Flow Fraction Curve",
                                    "minimum": 0.0,
                                    "maximum": 1.0
                                }
                            },
                            "type": "object"
                        }
                    }
                },
                "required": [
                    "air_inlet_node_name",
                    "air_outlet_node_name",
                    "design_maximum_air_flow_rate",
                    "design_pressure_rise"
                ]
            }
        },
        "group": "Fans",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "Fans",
                "FansSystemModel",
                "validBranchEquipmentNames",
                "validOASysEquipmentNames"
            ],
            "reference-class-name": [
                "validBranchEquipmentTypes",
                "validOASysEquipmentTypes"
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
                "air_inlet_node_name": {
                    "field_name": "Air Inlet Node Name",
                    "field_type": "a"
                },
                "air_outlet_node_name": {
                    "field_name": "Air Outlet Node Name",
                    "field_type": "a"
                },
                "design_maximum_air_flow_rate": {
                    "field_name": "Design Maximum Air Flow Rate",
                    "field_type": "n"
                },
                "speed_control_method": {
                    "field_name": "Speed Control Method",
                    "field_type": "a"
                },
                "electric_power_minimum_flow_rate_fraction": {
                    "field_name": "Electric Power Minimum Flow Rate Fraction",
                    "field_type": "n"
                },
                "design_pressure_rise": {
                    "field_name": "Design Pressure Rise",
                    "field_type": "n"
                },
                "motor_efficiency": {
                    "field_name": "Motor Efficiency",
                    "field_type": "n"
                },
                "motor_in_air_stream_fraction": {
                    "field_name": "Motor In Air Stream Fraction",
                    "field_type": "n"
                },
                "design_electric_power_consumption": {
                    "field_name": "Design Electric Power Consumption",
                    "field_type": "n"
                },
                "design_power_sizing_method": {
                    "field_name": "Design Power Sizing Method",
                    "field_type": "a"
                },
                "electric_power_per_unit_flow_rate": {
                    "field_name": "Electric Power Per Unit Flow Rate",
                    "field_type": "n"
                },
                "electric_power_per_unit_flow_rate_per_unit_pressure": {
                    "field_name": "Electric Power Per Unit Flow Rate Per Unit Pressure",
                    "field_type": "n"
                },
                "fan_total_efficiency": {
                    "field_name": "Fan Total Efficiency",
                    "field_type": "n"
                },
                "electric_power_function_of_flow_fraction_curve_name": {
                    "field_name": "Electric Power Function of Flow Fraction Curve Name",
                    "field_type": "a"
                },
                "night_ventilation_mode_pressure_rise": {
                    "field_name": "Night Ventilation Mode Pressure Rise",
                    "field_type": "n"
                },
                "night_ventilation_mode_flow_fraction": {
                    "field_name": "Night Ventilation Mode Flow Fraction",
                    "field_type": "n"
                },
                "motor_loss_zone_name": {
                    "field_name": "Motor Loss Zone Name",
                    "field_type": "a"
                },
                "motor_loss_radiative_fraction": {
                    "field_name": "Motor Loss Radiative Fraction",
                    "field_type": "n"
                },
                "end_use_subcategory": {
                    "field_name": "End-Use Subcategory",
                    "field_type": "a"
                },
                "number_of_speeds": {
                    "field_name": "Number of Speeds",
                    "field_type": "n"
                },
                "speed_flow_fraction": {
                    "field_name": "Speed Flow Fraction",
                    "field_type": "n"
                },
                "speed_electric_power_fraction": {
                    "field_name": "Speed Electric Power Fraction",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "availability_schedule_name",
                "air_inlet_node_name",
                "air_outlet_node_name",
                "design_maximum_air_flow_rate",
                "speed_control_method",
                "electric_power_minimum_flow_rate_fraction",
                "design_pressure_rise",
                "motor_efficiency",
                "motor_in_air_stream_fraction",
                "design_electric_power_consumption",
                "design_power_sizing_method",
                "electric_power_per_unit_flow_rate",
                "electric_power_per_unit_flow_rate_per_unit_pressure",
                "fan_total_efficiency",
                "electric_power_function_of_flow_fraction_curve_name",
                "night_ventilation_mode_pressure_rise",
                "night_ventilation_mode_flow_fraction",
                "motor_loss_zone_name",
                "motor_loss_radiative_fraction",
                "end_use_subcategory",
                "number_of_speeds"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "air_inlet_node_name",
                    "air_outlet_node_name",
                    "speed_control_method",
                    "design_power_sizing_method",
                    "electric_power_function_of_flow_fraction_curve_name",
                    "motor_loss_zone_name",
                    "end_use_subcategory"
                ]
            },
            "numerics": {
                "fields": [
                    "design_maximum_air_flow_rate",
                    "electric_power_minimum_flow_rate_fraction",
                    "design_pressure_rise",
                    "motor_efficiency",
                    "motor_in_air_stream_fraction",
                    "design_electric_power_consumption",
                    "electric_power_per_unit_flow_rate",
                    "electric_power_per_unit_flow_rate_per_unit_pressure",
                    "fan_total_efficiency",
                    "night_ventilation_mode_pressure_rise",
                    "night_ventilation_mode_flow_fraction",
                    "motor_loss_radiative_fraction",
                    "number_of_speeds"
                ],
                "extensions": [
                    "speed_flow_fraction",
                    "speed_electric_power_fraction"
                ]
            },
            "extensibles": [
                "speed_flow_fraction",
                "speed_electric_power_fraction"
            ],
            "extension": "speed_fractions"
        },
        "type": "object",
        "memo": "Versatile simple fan that can be used in variable air volume, constant volume, on-off cycling, two-speed or multi-speed applications. Performance at different flow rates, or speed levels, is determined using separate performance curve or table or prescribed power fractions at discrete speed levels for two-speed or multi-speed fans.",
        "min_fields": 14.0,
        "extensible_size": 2.0
    }
}
```
