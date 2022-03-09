```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "air_inlet_node_name": {
                    "type": "string"
                },
                "air_outlet_node_name": {
                    "type": "string"
                },
                "availability_schedule_name": {
                    "type": "string",
                    "note": "Availability schedule name for this system. Schedule value > 0 means the system is available. If this field is blank, the system is always available.",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "maximum_flow_rate": {
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
                "minimum_flow_rate": {
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
                "fan_sizing_factor": {
                    "type": "number",
                    "minimum": 1.0,
                    "default": 1.0,
                    "note": "Applied to specified or autosized max fan airflow"
                },
                "fan_wheel_diameter": {
                    "type": "number",
                    "units": "m",
                    "exclusiveMinimum": 0.0,
                    "note": "Diameter of wheel outer circumference"
                },
                "fan_outlet_area": {
                    "type": "number",
                    "units": "m2",
                    "exclusiveMinimum": 0.0,
                    "note": "Area at fan outlet plane for determining discharge velocity pressure"
                },
                "maximum_fan_static_efficiency": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "maximum": 1.0,
                    "note": "Maximum ratio between power delivered to air and fan shaft input power Determined from fan performance data"
                },
                "euler_number_at_maximum_fan_static_efficiency": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "note": "Euler number (Eu) determined from fan performance data"
                },
                "maximum_dimensionless_fan_airflow": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "note": "Corresponds to maximum ratio between fan airflow and fan shaft rotational speed for specified fan wheel diameter Determined from fan performance data"
                },
                "motor_fan_pulley_ratio": {
                    "default": 1.0,
                    "note": "Ratio of motor pulley diameter to fan pulley diameter",
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
                "belt_maximum_torque": {
                    "units": "N-m",
                    "note": "Maximum torque transmitted by belt",
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
                "belt_sizing_factor": {
                    "type": "number",
                    "minimum": 1.0,
                    "default": 1.0,
                    "note": "Applied to specified or autosized max torque transmitted by belt"
                },
                "belt_fractional_torque_transition": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.167,
                    "note": "Region 1 to 2 curve transition for belt normalized efficiency"
                },
                "motor_maximum_speed": {
                    "type": "number",
                    "units": "rev/min",
                    "exclusiveMinimum": 0.0,
                    "note": "Maximum rotational speed of fan motor shaft"
                },
                "maximum_motor_output_power": {
                    "units": "W",
                    "note": "Maximum power input to drive belt by motor",
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
                "motor_sizing_factor": {
                    "type": "number",
                    "minimum": 1.0,
                    "default": 1.0,
                    "note": "Applied to specified or autosized motor output power"
                },
                "motor_in_airstream_fraction": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 1.0,
                    "note": "0.0 means motor outside air stream 1.0 means motor inside air stream"
                },
                "vfd_efficiency_type": {
                    "type": "string",
                    "enum": [
                        "Power",
                        "Speed"
                    ],
                    "note": "Efficiency depends on fraction of full-load motor speed Efficiency depends on  fraction of full-load motor input power If field blank, then assumes constant VFD efficiency (0.97)"
                },
                "maximum_vfd_output_power": {
                    "units": "W",
                    "note": "Maximum power input to motor by VFD",
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
                "vfd_sizing_factor": {
                    "type": "number",
                    "minimum": 1.0,
                    "default": 1.0,
                    "note": "Applied to specified or autosized VFD output power"
                },
                "fan_pressure_rise_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "BivariateFunctions"
                    ],
                    "note": "Pressure rise depends on volumetric flow, system resistances, system leakage, and duct static pressure set point"
                },
                "duct_static_pressure_reset_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "Function of fan volumetric flow Minimum and maximum fan airflows correspond respectively to minimum and maximum duct static pressure set points"
                },
                "normalized_fan_static_efficiency_curve_name_non_stall_region": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "xfan <= 0 Curve should have maximum of 1.0"
                },
                "normalized_fan_static_efficiency_curve_name_stall_region": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "xfan > 0 Curve should have maximum of 1.0"
                },
                "normalized_dimensionless_airflow_curve_name_non_stall_region": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "xspd <= 0 Curve should have maximum of 1.0"
                },
                "normalized_dimensionless_airflow_curve_name_stall_region": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "xspd > 0 Curve should have maximum of 1.0"
                },
                "maximum_belt_efficiency_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "Determines maximum fan drive belt efficiency in log space as function of xbelt,max Curve should have minimum of -4.6 and maximum of 0.0 If field blank, assumes output of curve is always 1.0"
                },
                "normalized_belt_efficiency_curve_name_region_1": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "Region 1 (0 <= xbelt < xbelt,trans) Curve should have minimum > 0.0 and maximum of 1.0 If field blank, assumes output of curve is always 1.0 in Region 1"
                },
                "normalized_belt_efficiency_curve_name_region_2": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "Region 2 (xbelt,trans <= xbelt <= 1) Curve should have minimum > 0.0 and maximum of 1.0 If field blank, assumes output of curve is always 1.0 in Region 2"
                },
                "normalized_belt_efficiency_curve_name_region_3": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "Determines normalized drive belt efficiency Region 3 (xbelt > 1) Curve should have minimum > 0.0 and maximum of 1.0 If field blank, assumes output of curve is always 1.0 in Region 3"
                },
                "maximum_motor_efficiency_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "Curve should have minimum > 0.0 and maximum of 1.0 If field blank, assumes output of curve is always 1.0"
                },
                "normalized_motor_efficiency_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "Curve should have minimum > 0.0 and maximum of 1.0 If field blank, assumes output of curve is always 1.0"
                },
                "vfd_efficiency_curve_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ],
                    "note": "Determines VFD efficiency as function of motor load or speed fraction Curve should have minimum > 0.0 and maximum of 1.0 If field blank, assumes constant VFD efficiency (0.97)"
                },
                "end_use_subcategory": {
                    "type": "string",
                    "note": "Any text may be used here to categorize the end-uses in the ABUPS End Uses by Subcategory table.",
                    "retaincase": true,
                    "default": "General"
                }
            },
            "required": [
                "air_inlet_node_name",
                "air_outlet_node_name",
                "fan_wheel_diameter",
                "fan_outlet_area",
                "maximum_fan_static_efficiency",
                "euler_number_at_maximum_fan_static_efficiency",
                "maximum_dimensionless_fan_airflow",
                "belt_maximum_torque",
                "motor_maximum_speed",
                "maximum_motor_output_power",
                "maximum_vfd_output_power",
                "fan_pressure_rise_curve_name",
                "duct_static_pressure_reset_curve_name",
                "normalized_fan_static_efficiency_curve_name_non_stall_region",
                "normalized_fan_static_efficiency_curve_name_stall_region",
                "normalized_dimensionless_airflow_curve_name_non_stall_region",
                "normalized_dimensionless_airflow_curve_name_stall_region"
            ]
        }
    },
    "group": "Fans",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "Fans",
            "FansComponentModel",
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
            "air_inlet_node_name": {
                "field_name": "Air Inlet Node Name",
                "field_type": "a"
            },
            "air_outlet_node_name": {
                "field_name": "Air Outlet Node Name",
                "field_type": "a"
            },
            "availability_schedule_name": {
                "field_name": "Availability Schedule Name",
                "field_type": "a"
            },
            "maximum_flow_rate": {
                "field_name": "Maximum Flow Rate",
                "field_type": "n"
            },
            "minimum_flow_rate": {
                "field_name": "Minimum Flow Rate",
                "field_type": "n"
            },
            "fan_sizing_factor": {
                "field_name": "Fan Sizing Factor",
                "field_type": "n"
            },
            "fan_wheel_diameter": {
                "field_name": "Fan Wheel Diameter",
                "field_type": "n"
            },
            "fan_outlet_area": {
                "field_name": "Fan Outlet Area",
                "field_type": "n"
            },
            "maximum_fan_static_efficiency": {
                "field_name": "Maximum Fan Static Efficiency",
                "field_type": "n"
            },
            "euler_number_at_maximum_fan_static_efficiency": {
                "field_name": "Euler Number at Maximum Fan Static Efficiency",
                "field_type": "n"
            },
            "maximum_dimensionless_fan_airflow": {
                "field_name": "Maximum Dimensionless Fan Airflow",
                "field_type": "n"
            },
            "motor_fan_pulley_ratio": {
                "field_name": "Motor Fan Pulley Ratio",
                "field_type": "n"
            },
            "belt_maximum_torque": {
                "field_name": "Belt Maximum Torque",
                "field_type": "n"
            },
            "belt_sizing_factor": {
                "field_name": "Belt Sizing Factor",
                "field_type": "n"
            },
            "belt_fractional_torque_transition": {
                "field_name": "Belt Fractional Torque Transition",
                "field_type": "n"
            },
            "motor_maximum_speed": {
                "field_name": "Motor Maximum Speed",
                "field_type": "n"
            },
            "maximum_motor_output_power": {
                "field_name": "Maximum Motor Output Power",
                "field_type": "n"
            },
            "motor_sizing_factor": {
                "field_name": "Motor Sizing Factor",
                "field_type": "n"
            },
            "motor_in_airstream_fraction": {
                "field_name": "Motor In Airstream Fraction",
                "field_type": "n"
            },
            "vfd_efficiency_type": {
                "field_name": "VFD Efficiency Type",
                "field_type": "a"
            },
            "maximum_vfd_output_power": {
                "field_name": "Maximum VFD Output Power",
                "field_type": "n"
            },
            "vfd_sizing_factor": {
                "field_name": "VFD Sizing Factor",
                "field_type": "n"
            },
            "fan_pressure_rise_curve_name": {
                "field_name": "Fan Pressure Rise Curve Name",
                "field_type": "a"
            },
            "duct_static_pressure_reset_curve_name": {
                "field_name": "Duct Static Pressure Reset Curve Name",
                "field_type": "a"
            },
            "normalized_fan_static_efficiency_curve_name_non_stall_region": {
                "field_name": "Normalized Fan Static Efficiency Curve Name-Non-Stall Region",
                "field_type": "a"
            },
            "normalized_fan_static_efficiency_curve_name_stall_region": {
                "field_name": "Normalized Fan Static Efficiency Curve Name-Stall Region",
                "field_type": "a"
            },
            "normalized_dimensionless_airflow_curve_name_non_stall_region": {
                "field_name": "Normalized Dimensionless Airflow Curve Name-Non-Stall Region",
                "field_type": "a"
            },
            "normalized_dimensionless_airflow_curve_name_stall_region": {
                "field_name": "Normalized Dimensionless Airflow Curve Name-Stall Region",
                "field_type": "a"
            },
            "maximum_belt_efficiency_curve_name": {
                "field_name": "Maximum Belt Efficiency Curve Name",
                "field_type": "a"
            },
            "normalized_belt_efficiency_curve_name_region_1": {
                "field_name": "Normalized Belt Efficiency Curve Name - Region 1",
                "field_type": "a"
            },
            "normalized_belt_efficiency_curve_name_region_2": {
                "field_name": "Normalized Belt Efficiency Curve Name - Region 2",
                "field_type": "a"
            },
            "normalized_belt_efficiency_curve_name_region_3": {
                "field_name": "Normalized Belt Efficiency Curve Name - Region 3",
                "field_type": "a"
            },
            "maximum_motor_efficiency_curve_name": {
                "field_name": "Maximum Motor Efficiency Curve Name",
                "field_type": "a"
            },
            "normalized_motor_efficiency_curve_name": {
                "field_name": "Normalized Motor Efficiency Curve Name",
                "field_type": "a"
            },
            "vfd_efficiency_curve_name": {
                "field_name": "VFD Efficiency Curve Name",
                "field_type": "a"
            },
            "end_use_subcategory": {
                "field_name": "End-Use Subcategory",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "air_inlet_node_name",
            "air_outlet_node_name",
            "availability_schedule_name",
            "maximum_flow_rate",
            "minimum_flow_rate",
            "fan_sizing_factor",
            "fan_wheel_diameter",
            "fan_outlet_area",
            "maximum_fan_static_efficiency",
            "euler_number_at_maximum_fan_static_efficiency",
            "maximum_dimensionless_fan_airflow",
            "motor_fan_pulley_ratio",
            "belt_maximum_torque",
            "belt_sizing_factor",
            "belt_fractional_torque_transition",
            "motor_maximum_speed",
            "maximum_motor_output_power",
            "motor_sizing_factor",
            "motor_in_airstream_fraction",
            "vfd_efficiency_type",
            "maximum_vfd_output_power",
            "vfd_sizing_factor",
            "fan_pressure_rise_curve_name",
            "duct_static_pressure_reset_curve_name",
            "normalized_fan_static_efficiency_curve_name_non_stall_region",
            "normalized_fan_static_efficiency_curve_name_stall_region",
            "normalized_dimensionless_airflow_curve_name_non_stall_region",
            "normalized_dimensionless_airflow_curve_name_stall_region",
            "maximum_belt_efficiency_curve_name",
            "normalized_belt_efficiency_curve_name_region_1",
            "normalized_belt_efficiency_curve_name_region_2",
            "normalized_belt_efficiency_curve_name_region_3",
            "maximum_motor_efficiency_curve_name",
            "normalized_motor_efficiency_curve_name",
            "vfd_efficiency_curve_name",
            "end_use_subcategory"
        ],
        "alphas": {
            "fields": [
                "name",
                "air_inlet_node_name",
                "air_outlet_node_name",
                "availability_schedule_name",
                "vfd_efficiency_type",
                "fan_pressure_rise_curve_name",
                "duct_static_pressure_reset_curve_name",
                "normalized_fan_static_efficiency_curve_name_non_stall_region",
                "normalized_fan_static_efficiency_curve_name_stall_region",
                "normalized_dimensionless_airflow_curve_name_non_stall_region",
                "normalized_dimensionless_airflow_curve_name_stall_region",
                "maximum_belt_efficiency_curve_name",
                "normalized_belt_efficiency_curve_name_region_1",
                "normalized_belt_efficiency_curve_name_region_2",
                "normalized_belt_efficiency_curve_name_region_3",
                "maximum_motor_efficiency_curve_name",
                "normalized_motor_efficiency_curve_name",
                "vfd_efficiency_curve_name",
                "end_use_subcategory"
            ]
        },
        "numerics": {
            "fields": [
                "maximum_flow_rate",
                "minimum_flow_rate",
                "fan_sizing_factor",
                "fan_wheel_diameter",
                "fan_outlet_area",
                "maximum_fan_static_efficiency",
                "euler_number_at_maximum_fan_static_efficiency",
                "maximum_dimensionless_fan_airflow",
                "motor_fan_pulley_ratio",
                "belt_maximum_torque",
                "belt_sizing_factor",
                "belt_fractional_torque_transition",
                "motor_maximum_speed",
                "maximum_motor_output_power",
                "motor_sizing_factor",
                "motor_in_airstream_fraction",
                "maximum_vfd_output_power",
                "vfd_sizing_factor"
            ]
        }
    },
    "type": "object",
    "memo": "A detailed fan type for constant-air-volume (CAV) and variable-air-volume (VAV) systems. It includes inputs that describe the air-distribution system as well as the fan, drive belt (if used), motor, and variable-frequency-drive (if used)."
}
```
