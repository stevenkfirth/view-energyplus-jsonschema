```
{
    "Fan:OnOff": {
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
                    "fan_total_efficiency": {
                        "type": "number",
                        "default": 0.6,
                        "exclusiveMinimum": 0.0,
                        "maximum": 1.0
                    },
                    "pressure_rise": {
                        "type": "number",
                        "units": "Pa",
                        "ip-units": "inH2O"
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
                    "motor_efficiency": {
                        "type": "number",
                        "default": 0.8,
                        "exclusiveMinimum": 0.0,
                        "maximum": 1.0
                    },
                    "motor_in_airstream_fraction": {
                        "type": "number",
                        "note": "0.0 means fan motor outside of air stream, 1.0 means motor inside of air stream",
                        "default": 1.0,
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "air_inlet_node_name": {
                        "type": "string"
                    },
                    "air_outlet_node_name": {
                        "type": "string"
                    },
                    "fan_power_ratio_function_of_speed_ratio_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ]
                    },
                    "fan_efficiency_ratio_function_of_speed_ratio_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ]
                    },
                    "end_use_subcategory": {
                        "type": "string",
                        "note": "Any text may be used here to categorize the end-uses in the ABUPS End Uses by Subcategory table.",
                        "retaincase": true,
                        "default": "General"
                    }
                },
                "required": [
                    "pressure_rise",
                    "air_inlet_node_name",
                    "air_outlet_node_name"
                ]
            }
        },
        "group": "Fans",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "Fans",
                "FansCVandOnOff",
                "FansCVandOnOffandVAV",
                "FansOnOff",
                "FansOnOffandVAV"
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
                "fan_total_efficiency": {
                    "field_name": "Fan Total Efficiency",
                    "field_type": "n"
                },
                "pressure_rise": {
                    "field_name": "Pressure Rise",
                    "field_type": "n"
                },
                "maximum_flow_rate": {
                    "field_name": "Maximum Flow Rate",
                    "field_type": "n"
                },
                "motor_efficiency": {
                    "field_name": "Motor Efficiency",
                    "field_type": "n"
                },
                "motor_in_airstream_fraction": {
                    "field_name": "Motor In Airstream Fraction",
                    "field_type": "n"
                },
                "air_inlet_node_name": {
                    "field_name": "Air Inlet Node Name",
                    "field_type": "a"
                },
                "air_outlet_node_name": {
                    "field_name": "Air Outlet Node Name",
                    "field_type": "a"
                },
                "fan_power_ratio_function_of_speed_ratio_curve_name": {
                    "field_name": "Fan Power Ratio Function of Speed Ratio Curve Name",
                    "field_type": "a"
                },
                "fan_efficiency_ratio_function_of_speed_ratio_curve_name": {
                    "field_name": "Fan Efficiency Ratio Function of Speed Ratio Curve Name",
                    "field_type": "a"
                },
                "end_use_subcategory": {
                    "field_name": "End-Use Subcategory",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "availability_schedule_name",
                "fan_total_efficiency",
                "pressure_rise",
                "maximum_flow_rate",
                "motor_efficiency",
                "motor_in_airstream_fraction",
                "air_inlet_node_name",
                "air_outlet_node_name",
                "fan_power_ratio_function_of_speed_ratio_curve_name",
                "fan_efficiency_ratio_function_of_speed_ratio_curve_name",
                "end_use_subcategory"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "air_inlet_node_name",
                    "air_outlet_node_name",
                    "fan_power_ratio_function_of_speed_ratio_curve_name",
                    "fan_efficiency_ratio_function_of_speed_ratio_curve_name",
                    "end_use_subcategory"
                ]
            },
            "numerics": {
                "fields": [
                    "fan_total_efficiency",
                    "pressure_rise",
                    "maximum_flow_rate",
                    "motor_efficiency",
                    "motor_in_airstream_fraction"
                ]
            }
        },
        "type": "object",
        "memo": "Constant volume fan that is intended to cycle on and off based on cooling/heating load or other control signals. This fan can also operate continuously like Fan:ConstantVolume.",
        "min_fields": 9.0
    }
}
```
