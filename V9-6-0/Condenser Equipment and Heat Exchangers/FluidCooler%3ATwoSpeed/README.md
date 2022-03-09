```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "water_inlet_node_name": {
                    "type": "string",
                    "note": "Name of fluid cooler water inlet node"
                },
                "water_outlet_node_name": {
                    "type": "string",
                    "note": "Name of fluid cooler water outlet node"
                },
                "performance_input_method": {
                    "type": "string",
                    "enum": [
                        "",
                        "NominalCapacity",
                        "UFactorTimesAreaAndDesignWaterFlowRate"
                    ],
                    "default": "NominalCapacity",
                    "note": "User can define fluid cooler thermal performance by specifying the fluid cooler UA and the Design Water Flow Rate, or by specifying the fluid cooler nominal capacity"
                },
                "high_fan_speed_u_factor_times_area_value": {
                    "units": "W/K",
                    "note": "Leave field blank if fluid cooler Performance Input Method is NominalCapacity",
                    "anyOf": [
                        {
                            "type": "number",
                            "exclusiveMinimum": 0.0,
                            "maximum": 2100000.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "Autosize"
                            ]
                        }
                    ]
                },
                "low_fan_speed_u_factor_times_area_value": {
                    "units": "W/K",
                    "note": "Leave field blank if fluid cooler Performance Input Method is NominalCapacity Low speed fluid cooler UA must be less than high speed fluid cooler UA Low speed fluid cooler UA must be greater than free convection fluid cooler UA",
                    "anyOf": [
                        {
                            "type": "number",
                            "exclusiveMinimum": 0.0,
                            "maximum": 300000.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "Autocalculate"
                            ]
                        }
                    ]
                },
                "low_fan_speed_u_factor_times_area_sizing_factor": {
                    "type": "number",
                    "default": 0.6,
                    "note": "This field is only used if the previous field is set to autocalculate and the Performance Input Method is UFactorTimesAreaAndDesignWaterFlowRate"
                },
                "high_speed_nominal_capacity": {
                    "type": "number",
                    "units": "W",
                    "exclusiveMinimum": 0.0,
                    "note": "Nominal fluid cooler capacity at high fan speed"
                },
                "low_speed_nominal_capacity": {
                    "units": "W",
                    "note": "Nominal fluid cooler capacity at low fan speed",
                    "anyOf": [
                        {
                            "type": "number",
                            "exclusiveMinimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "Autocalculate"
                            ]
                        }
                    ]
                },
                "low_speed_nominal_capacity_sizing_factor": {
                    "type": "number",
                    "default": 0.5,
                    "note": "This field is only used if the previous field is set to autocalculate and the Performance Input Method is NominalCapacity"
                },
                "design_entering_water_temperature": {
                    "type": "number",
                    "units": "C",
                    "exclusiveMinimum": 0.0,
                    "ip-units": "F",
                    "note": "Design Entering Water Temperature must be specified for both the performance input methods and its value must be greater than Design Entering Air Temperature."
                },
                "design_entering_air_temperature": {
                    "type": "number",
                    "units": "C",
                    "exclusiveMinimum": 0.0,
                    "ip-units": "F",
                    "note": "Design Entering Air Temperature must be specified for both the performance input methods and its value must be greater than Design Entering Air Wet-bulb Temperature."
                },
                "design_entering_air_wet_bulb_temperature": {
                    "type": "number",
                    "units": "C",
                    "exclusiveMinimum": 0.0,
                    "ip-units": "F",
                    "note": "Design Entering Air Wet-bulb Temperature must be specified for both the performance input methods and its value must be less than Design Entering Air Temperature."
                },
                "design_water_flow_rate": {
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
                "high_fan_speed_air_flow_rate": {
                    "units": "m3/s",
                    "note": "Air Flow Rate at High Fan Speed must be greater than Air Flow Rate at Low Fan Speed",
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
                "high_fan_speed_fan_power": {
                    "units": "W",
                    "ip-units": "W",
                    "note": "This is the fan motor electric input power at high speed",
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
                "low_fan_speed_air_flow_rate": {
                    "units": "m3/s",
                    "note": "Air Flow Rate at Low Fan Speed must be less than Air Flow Rate at High Fan Speed",
                    "anyOf": [
                        {
                            "type": "number",
                            "exclusiveMinimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "Autocalculate"
                            ]
                        }
                    ]
                },
                "low_fan_speed_air_flow_rate_sizing_factor": {
                    "type": "number",
                    "default": 0.5,
                    "note": "This field is only used if the previous field is set to autocalculate."
                },
                "low_fan_speed_fan_power": {
                    "units": "W",
                    "ip-units": "W",
                    "note": "This is the fan motor electric input power at low speed",
                    "anyOf": [
                        {
                            "type": "number",
                            "exclusiveMinimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "Autocalculate"
                            ]
                        }
                    ]
                },
                "low_fan_speed_fan_power_sizing_factor": {
                    "type": "number",
                    "default": 0.16,
                    "note": "This field is only used if the previous field is set to autocalculate."
                },
                "outdoor_air_inlet_node_name": {
                    "type": "string"
                }
            },
            "required": [
                "water_inlet_node_name",
                "water_outlet_node_name",
                "design_entering_water_temperature",
                "design_entering_air_temperature",
                "design_entering_air_wet_bulb_temperature",
                "design_water_flow_rate",
                "high_fan_speed_air_flow_rate",
                "high_fan_speed_fan_power",
                "low_fan_speed_air_flow_rate",
                "low_fan_speed_fan_power"
            ]
        }
    },
    "group": "Condenser Equipment and Heat Exchangers",
    "name": {
        "type": "string",
        "is_required": true,
        "note": "fluid cooler name",
        "reference-class-name": [
            "validBranchEquipmentTypes",
            "validCondenserEquipmentTypes",
            "validPlantEquipmentTypes"
        ],
        "reference": [
            "validBranchEquipmentNames",
            "validCondenserEquipmentNames",
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
            "water_inlet_node_name": {
                "field_name": "Water Inlet Node Name",
                "field_type": "a"
            },
            "water_outlet_node_name": {
                "field_name": "Water Outlet Node Name",
                "field_type": "a"
            },
            "performance_input_method": {
                "field_name": "Performance Input Method",
                "field_type": "a"
            },
            "high_fan_speed_u_factor_times_area_value": {
                "field_name": "High Fan Speed U-factor Times Area Value",
                "field_type": "n"
            },
            "low_fan_speed_u_factor_times_area_value": {
                "field_name": "Low Fan Speed U-factor Times Area Value",
                "field_type": "n"
            },
            "low_fan_speed_u_factor_times_area_sizing_factor": {
                "field_name": "Low Fan Speed U-Factor Times Area Sizing Factor",
                "field_type": "n"
            },
            "high_speed_nominal_capacity": {
                "field_name": "High Speed Nominal Capacity",
                "field_type": "n"
            },
            "low_speed_nominal_capacity": {
                "field_name": "Low Speed Nominal Capacity",
                "field_type": "n"
            },
            "low_speed_nominal_capacity_sizing_factor": {
                "field_name": "Low Speed Nominal Capacity Sizing Factor",
                "field_type": "n"
            },
            "design_entering_water_temperature": {
                "field_name": "Design Entering Water Temperature",
                "field_type": "n"
            },
            "design_entering_air_temperature": {
                "field_name": "Design Entering Air Temperature",
                "field_type": "n"
            },
            "design_entering_air_wet_bulb_temperature": {
                "field_name": "Design Entering Air Wet-bulb Temperature",
                "field_type": "n"
            },
            "design_water_flow_rate": {
                "field_name": "Design Water Flow Rate",
                "field_type": "n"
            },
            "high_fan_speed_air_flow_rate": {
                "field_name": "High Fan Speed Air Flow Rate",
                "field_type": "n"
            },
            "high_fan_speed_fan_power": {
                "field_name": "High Fan Speed Fan Power",
                "field_type": "n"
            },
            "low_fan_speed_air_flow_rate": {
                "field_name": "Low Fan Speed Air Flow Rate",
                "field_type": "n"
            },
            "low_fan_speed_air_flow_rate_sizing_factor": {
                "field_name": "Low Fan Speed Air Flow Rate Sizing Factor",
                "field_type": "n"
            },
            "low_fan_speed_fan_power": {
                "field_name": "Low Fan Speed Fan Power",
                "field_type": "n"
            },
            "low_fan_speed_fan_power_sizing_factor": {
                "field_name": "Low Fan Speed Fan Power Sizing Factor",
                "field_type": "n"
            },
            "outdoor_air_inlet_node_name": {
                "field_name": "Outdoor Air Inlet Node Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "water_inlet_node_name",
            "water_outlet_node_name",
            "performance_input_method",
            "high_fan_speed_u_factor_times_area_value",
            "low_fan_speed_u_factor_times_area_value",
            "low_fan_speed_u_factor_times_area_sizing_factor",
            "high_speed_nominal_capacity",
            "low_speed_nominal_capacity",
            "low_speed_nominal_capacity_sizing_factor",
            "design_entering_water_temperature",
            "design_entering_air_temperature",
            "design_entering_air_wet_bulb_temperature",
            "design_water_flow_rate",
            "high_fan_speed_air_flow_rate",
            "high_fan_speed_fan_power",
            "low_fan_speed_air_flow_rate",
            "low_fan_speed_air_flow_rate_sizing_factor",
            "low_fan_speed_fan_power",
            "low_fan_speed_fan_power_sizing_factor",
            "outdoor_air_inlet_node_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "water_inlet_node_name",
                "water_outlet_node_name",
                "performance_input_method",
                "outdoor_air_inlet_node_name"
            ]
        },
        "numerics": {
            "fields": [
                "high_fan_speed_u_factor_times_area_value",
                "low_fan_speed_u_factor_times_area_value",
                "low_fan_speed_u_factor_times_area_sizing_factor",
                "high_speed_nominal_capacity",
                "low_speed_nominal_capacity",
                "low_speed_nominal_capacity_sizing_factor",
                "design_entering_water_temperature",
                "design_entering_air_temperature",
                "design_entering_air_wet_bulb_temperature",
                "design_water_flow_rate",
                "high_fan_speed_air_flow_rate",
                "high_fan_speed_fan_power",
                "low_fan_speed_air_flow_rate",
                "low_fan_speed_air_flow_rate_sizing_factor",
                "low_fan_speed_fan_power",
                "low_fan_speed_fan_power_sizing_factor"
            ]
        }
    },
    "type": "object",
    "memo": "The fluid cooler is modeled as a cross flow heat exchanger (both streams unmixed) with two-speed fans (induced draft configuration).",
    "min_fields": 20.0
}
```
