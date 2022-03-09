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
                "fan_total_efficiency": {
                    "type": "number",
                    "default": 0.7,
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
                "fan_power_minimum_flow_rate_input_method": {
                    "type": "string",
                    "enum": [
                        "",
                        "FixedFlowRate",
                        "Fraction"
                    ],
                    "default": "Fraction"
                },
                "fan_power_minimum_flow_fraction": {
                    "type": "number",
                    "maximum": 1.0,
                    "minimum": 0.0,
                    "default": 0.25
                },
                "fan_power_minimum_air_flow_rate": {
                    "type": "number",
                    "units": "m3/s",
                    "minimum": 0.0
                },
                "motor_efficiency": {
                    "type": "number",
                    "default": 0.9,
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
                "fan_power_coefficient_1": {
                    "type": "number",
                    "note": "all Fan Power Coefficients should not be 0.0 or no fan power will be consumed. Fan Power Coefficents are specified as function of full flow rate/power Equation:"
                },
                "fan_power_coefficient_2": {
                    "type": "number"
                },
                "fan_power_coefficient_3": {
                    "type": "number"
                },
                "fan_power_coefficient_4": {
                    "type": "number"
                },
                "fan_power_coefficient_5": {
                    "type": "number"
                },
                "air_inlet_node_name": {
                    "type": "string"
                },
                "air_outlet_node_name": {
                    "type": "string"
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
            "FansCVandOnOffandVAV",
            "FansCVandVAV",
            "FansOnOffandVAV",
            "FansVAV",
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
            "fan_power_minimum_flow_rate_input_method": {
                "field_name": "Fan Power Minimum Flow Rate Input Method",
                "field_type": "a"
            },
            "fan_power_minimum_flow_fraction": {
                "field_name": "Fan Power Minimum Flow Fraction",
                "field_type": "n"
            },
            "fan_power_minimum_air_flow_rate": {
                "field_name": "Fan Power Minimum Air Flow Rate",
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
            "fan_power_coefficient_1": {
                "field_name": "Fan Power Coefficient 1",
                "field_type": "n"
            },
            "fan_power_coefficient_2": {
                "field_name": "Fan Power Coefficient 2",
                "field_type": "n"
            },
            "fan_power_coefficient_3": {
                "field_name": "Fan Power Coefficient 3",
                "field_type": "n"
            },
            "fan_power_coefficient_4": {
                "field_name": "Fan Power Coefficient 4",
                "field_type": "n"
            },
            "fan_power_coefficient_5": {
                "field_name": "Fan Power Coefficient 5",
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
            "fan_power_minimum_flow_rate_input_method",
            "fan_power_minimum_flow_fraction",
            "fan_power_minimum_air_flow_rate",
            "motor_efficiency",
            "motor_in_airstream_fraction",
            "fan_power_coefficient_1",
            "fan_power_coefficient_2",
            "fan_power_coefficient_3",
            "fan_power_coefficient_4",
            "fan_power_coefficient_5",
            "air_inlet_node_name",
            "air_outlet_node_name",
            "end_use_subcategory"
        ],
        "alphas": {
            "fields": [
                "name",
                "availability_schedule_name",
                "fan_power_minimum_flow_rate_input_method",
                "air_inlet_node_name",
                "air_outlet_node_name",
                "end_use_subcategory"
            ]
        },
        "numerics": {
            "fields": [
                "fan_total_efficiency",
                "pressure_rise",
                "maximum_flow_rate",
                "fan_power_minimum_flow_fraction",
                "fan_power_minimum_air_flow_rate",
                "motor_efficiency",
                "motor_in_airstream_fraction",
                "fan_power_coefficient_1",
                "fan_power_coefficient_2",
                "fan_power_coefficient_3",
                "fan_power_coefficient_4",
                "fan_power_coefficient_5"
            ]
        }
    },
    "type": "object",
    "memo": "Variable air volume fan where the electric power input varies according to a performance curve as a function of flow fraction.",
    "min_fields": 17.0
}
```
