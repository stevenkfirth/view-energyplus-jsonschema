```
{
    "EvaporativeFluidCooler:TwoSpeed": {
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
                    "high_fan_speed_air_flow_rate": {
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
                        "note": "Low speed air flow rate must be less than high speed air flow rate",
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
                        "note": "This field is only used if the previous field is set to autocalculate"
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
                    "design_spray_water_flow_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "exclusiveMinimum": 0.0,
                        "ip-units": "gal/min"
                    },
                    "performance_input_method": {
                        "type": "string",
                        "enum": [
                            "StandardDesignCapacity",
                            "UFactorTimesAreaAndDesignWaterFlowRate",
                            "UserSpecifiedDesignCapacity"
                        ],
                        "note": "User can define fluid cooler thermal performance by specifying the fluid cooler UA and the Design Water Flow Rate, or by specifying the fluid cooler Standard Design Capacity or by specifying Design Capacity for Non standard conditions."
                    },
                    "outdoor_air_inlet_node_name": {
                        "type": "string",
                        "note": "Enter the name of an outdoor air node"
                    },
                    "heat_rejection_capacity_and_nominal_capacity_sizing_ratio": {
                        "type": "number",
                        "default": 1.25
                    },
                    "high_speed_standard_design_capacity": {
                        "type": "number",
                        "units": "W",
                        "exclusiveMinimum": 0.0,
                        "note": "Standard design capacity with entering water at 35C (95F), leaving water at 29.44C (85F), entering air at 25.56C (78F) wet-bulb temperature and 35C (95F) dry-bulb temperature. Design water flow rate assumed to be 5.382E-8 m3/s per watt (3 gpm/ton). Standard design capacity times the Heat Rejection Capacity and Nominal Capacity Sizing Ratio (e.g. 1.25) gives the actual fluid cooler heat rejection at these operating conditions. Only used for Performance Input Method = StandardDesignCapacity; for other input methods, this field is ignored. The standard conditions mentioned above for Standard design capacity are already specified in the EnergyPlus. So the input fields such as design entering water temp., design entering air wet-bulb and dry-bulb temp. and design water flow rate, if provided in the input, will be ignored for the StandardDesignCapacity performance input method. Also, the standard conditions are for water as a fluid type so this performance input method can only be used with water as a fluid type (as specified in CondenserLoop object)."
                    },
                    "low_speed_standard_design_capacity": {
                        "units": "W",
                        "note": "Standard design capacity with entering water at 35C (95F), leaving water at 29.44C (85F), entering air at 25.56C (78F) wet-bulb temperature and 35C (95F) dry-bulb temperature. Design water flow rate assumed to be 5.382E-8 m3/s per watt (3 gpm/ton). Standard design capacity times the Heat Rejection Capacity and Nominal Capacity Sizing Ratio (e.g. 1.25) gives the actual fluid cooler heat rejection at these operating conditions. Only used for Performance Input Method = StandardDesignCapacity; for other input methods, this field is ignored. The standard conditions mentioned above for Standard design capacity are already specified in the EnergyPlus. So the input fields such as design entering water temp., design entering air wet-bulb and dry-bulb temp. and design water flow rate, if provided in the input, will be ignored for the StandardDesignCapacity performance input method. Also, the standard conditions are for water as a fluid type so this performance input method can only be used with water as a fluid type (as specified in CondenserLoop object).",
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
                    "low_speed_standard_capacity_sizing_factor": {
                        "type": "number",
                        "default": 0.5,
                        "note": "This field is only used if the previous field is set to autocalculate"
                    },
                    "high_fan_speed_u_factor_times_area_value": {
                        "units": "W/K",
                        "note": "Only used for Performance Input Method = UFactorTimesAreaAndDesignWaterFlowRate; for other Performance Input Methods, this field is ignored.",
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
                        "note": "Only used for Performance Input Method = UFactorTimesAreaAndDesignWaterFlowRate; for other input methods, this field is ignored. Low speed fluid cooler UA must be less than high speed fluid cooler UA",
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
                    "design_water_flow_rate": {
                        "units": "m3/s",
                        "ip-units": "gal/min",
                        "note": "Input value is ignored if fluid cooler Performance Input Method= StandardDesignCapacity",
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
                    "high_speed_user_specified_design_capacity": {
                        "type": "number",
                        "units": "W",
                        "exclusiveMinimum": 0.0,
                        "note": "Only used for Performance Input Method = UserSpecifiedDesignCapacity; for other Performance Input Methods, this field is ignored."
                    },
                    "low_speed_user_specified_design_capacity": {
                        "units": "W",
                        "note": "Only used for Performance Input Method = UserSpecifiedDesignCapacity; for other Performance Input Methods, this field is ignored.",
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
                    "low_speed_user_specified_design_capacity_sizing_factor": {
                        "type": "number",
                        "default": 0.5,
                        "note": "This field is only used if the previous field is set to autocalculate"
                    },
                    "design_entering_water_temperature": {
                        "type": "number",
                        "units": "C",
                        "exclusiveMinimum": 0.0,
                        "ip-units": "F",
                        "note": "Only used for Performance Input Method = UserSpecifiedDesignCapacity; for other Performance Input Methods, this field is ignored. Design Entering Water Temperature must be greater than Design Entering Air Temperature."
                    },
                    "design_entering_air_temperature": {
                        "type": "number",
                        "units": "C",
                        "exclusiveMinimum": 0.0,
                        "ip-units": "F",
                        "note": "Only used for Performance Input Method = UserSpecifiedDesignCapacity; for other Performance Input Methods, this field is ignored. Design Entering Air Temperature must be greater than Design Entering Air Wet-bulb Temperature."
                    },
                    "design_entering_air_wet_bulb_temperature": {
                        "type": "number",
                        "units": "C",
                        "exclusiveMinimum": 0.0,
                        "ip-units": "F",
                        "note": "Only used for Performance Input Method = UserSpecifiedDesignCapacity; for other Performance Input Methods, this field is ignored. Design Entering Air Wet-bulb Temperature must be less than Design Entering Air Temperature."
                    },
                    "high_speed_sizing_factor": {
                        "type": "number",
                        "note": "Multiplies the autosized capacity and flow rates",
                        "exclusiveMinimum": 0.0,
                        "default": 1.0
                    },
                    "evaporation_loss_mode": {
                        "type": "string",
                        "enum": [
                            "",
                            "LossFactor",
                            "SaturatedExit"
                        ],
                        "default": "SaturatedExit"
                    },
                    "evaporation_loss_factor": {
                        "type": "number",
                        "units": "percent/K",
                        "note": "Rate of water evaporation from the Fluid Cooler and lost to the outdoor air [%/K] Empirical correlation is used to calculate default loss factor if it not explicitly provided."
                    },
                    "drift_loss_percent": {
                        "type": "number",
                        "units": "percent",
                        "default": 0.008,
                        "note": "Default value is under investigation. For now cooling tower's default value is taken."
                    },
                    "blowdown_calculation_mode": {
                        "type": "string",
                        "enum": [
                            "",
                            "ConcentrationRatio",
                            "ScheduledRate"
                        ],
                        "default": "ConcentrationRatio"
                    },
                    "blowdown_concentration_ratio": {
                        "type": "number",
                        "minimum": 2.0,
                        "default": 3.0,
                        "note": "Characterizes the rate of blowdown in the Evaporative Fluid Cooler. Blowdown is water intentionally drained from the Evaporative Fluid Cooler in order to offset the build up of solids in the water that would otherwise occur because of evaporation. Ratio of solids in the blowdown water to solids in the make up water. Default value is under investigation. For now cooling tower's default value is taken."
                    },
                    "blowdown_makeup_water_usage_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "Makeup water usage due to blowdown results from occasionally draining some amount of water in the Evaporative Fluid Cooler basin to purge scale or other contaminants to reduce their concentration in order to maintain an acceptable level of water quality. Schedule values should reflect water usage in m3/s."
                    },
                    "supply_water_storage_tank_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "WaterStorageTankNames"
                        ]
                    }
                },
                "required": [
                    "water_inlet_node_name",
                    "water_outlet_node_name",
                    "high_fan_speed_air_flow_rate",
                    "high_fan_speed_fan_power",
                    "low_fan_speed_air_flow_rate",
                    "low_fan_speed_fan_power",
                    "design_spray_water_flow_rate",
                    "performance_input_method"
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
                "design_spray_water_flow_rate": {
                    "field_name": "Design Spray Water Flow Rate",
                    "field_type": "n"
                },
                "performance_input_method": {
                    "field_name": "Performance Input Method",
                    "field_type": "a"
                },
                "outdoor_air_inlet_node_name": {
                    "field_name": "Outdoor Air Inlet Node Name",
                    "field_type": "a"
                },
                "heat_rejection_capacity_and_nominal_capacity_sizing_ratio": {
                    "field_name": "Heat Rejection Capacity and Nominal Capacity Sizing Ratio",
                    "field_type": "n"
                },
                "high_speed_standard_design_capacity": {
                    "field_name": "High Speed Standard Design Capacity",
                    "field_type": "n"
                },
                "low_speed_standard_design_capacity": {
                    "field_name": "Low Speed Standard Design Capacity",
                    "field_type": "n"
                },
                "low_speed_standard_capacity_sizing_factor": {
                    "field_name": "Low Speed Standard Capacity Sizing Factor",
                    "field_type": "n"
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
                "design_water_flow_rate": {
                    "field_name": "Design Water Flow Rate",
                    "field_type": "n"
                },
                "high_speed_user_specified_design_capacity": {
                    "field_name": "High Speed User Specified Design Capacity",
                    "field_type": "n"
                },
                "low_speed_user_specified_design_capacity": {
                    "field_name": "Low Speed User Specified Design Capacity",
                    "field_type": "n"
                },
                "low_speed_user_specified_design_capacity_sizing_factor": {
                    "field_name": "Low Speed User Specified Design Capacity Sizing Factor",
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
                "high_speed_sizing_factor": {
                    "field_name": "High Speed Sizing Factor",
                    "field_type": "n"
                },
                "evaporation_loss_mode": {
                    "field_name": "Evaporation Loss Mode",
                    "field_type": "a"
                },
                "evaporation_loss_factor": {
                    "field_name": "Evaporation Loss Factor",
                    "field_type": "n"
                },
                "drift_loss_percent": {
                    "field_name": "Drift Loss Percent",
                    "field_type": "n"
                },
                "blowdown_calculation_mode": {
                    "field_name": "Blowdown Calculation Mode",
                    "field_type": "a"
                },
                "blowdown_concentration_ratio": {
                    "field_name": "Blowdown Concentration Ratio",
                    "field_type": "n"
                },
                "blowdown_makeup_water_usage_schedule_name": {
                    "field_name": "Blowdown Makeup Water Usage Schedule Name",
                    "field_type": "a"
                },
                "supply_water_storage_tank_name": {
                    "field_name": "Supply Water Storage Tank Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "water_inlet_node_name",
                "water_outlet_node_name",
                "high_fan_speed_air_flow_rate",
                "high_fan_speed_fan_power",
                "low_fan_speed_air_flow_rate",
                "low_fan_speed_air_flow_rate_sizing_factor",
                "low_fan_speed_fan_power",
                "low_fan_speed_fan_power_sizing_factor",
                "design_spray_water_flow_rate",
                "performance_input_method",
                "outdoor_air_inlet_node_name",
                "heat_rejection_capacity_and_nominal_capacity_sizing_ratio",
                "high_speed_standard_design_capacity",
                "low_speed_standard_design_capacity",
                "low_speed_standard_capacity_sizing_factor",
                "high_fan_speed_u_factor_times_area_value",
                "low_fan_speed_u_factor_times_area_value",
                "low_fan_speed_u_factor_times_area_sizing_factor",
                "design_water_flow_rate",
                "high_speed_user_specified_design_capacity",
                "low_speed_user_specified_design_capacity",
                "low_speed_user_specified_design_capacity_sizing_factor",
                "design_entering_water_temperature",
                "design_entering_air_temperature",
                "design_entering_air_wet_bulb_temperature",
                "high_speed_sizing_factor",
                "evaporation_loss_mode",
                "evaporation_loss_factor",
                "drift_loss_percent",
                "blowdown_calculation_mode",
                "blowdown_concentration_ratio",
                "blowdown_makeup_water_usage_schedule_name",
                "supply_water_storage_tank_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "water_inlet_node_name",
                    "water_outlet_node_name",
                    "performance_input_method",
                    "outdoor_air_inlet_node_name",
                    "evaporation_loss_mode",
                    "blowdown_calculation_mode",
                    "blowdown_makeup_water_usage_schedule_name",
                    "supply_water_storage_tank_name"
                ]
            },
            "numerics": {
                "fields": [
                    "high_fan_speed_air_flow_rate",
                    "high_fan_speed_fan_power",
                    "low_fan_speed_air_flow_rate",
                    "low_fan_speed_air_flow_rate_sizing_factor",
                    "low_fan_speed_fan_power",
                    "low_fan_speed_fan_power_sizing_factor",
                    "design_spray_water_flow_rate",
                    "heat_rejection_capacity_and_nominal_capacity_sizing_ratio",
                    "high_speed_standard_design_capacity",
                    "low_speed_standard_design_capacity",
                    "low_speed_standard_capacity_sizing_factor",
                    "high_fan_speed_u_factor_times_area_value",
                    "low_fan_speed_u_factor_times_area_value",
                    "low_fan_speed_u_factor_times_area_sizing_factor",
                    "design_water_flow_rate",
                    "high_speed_user_specified_design_capacity",
                    "low_speed_user_specified_design_capacity",
                    "low_speed_user_specified_design_capacity_sizing_factor",
                    "design_entering_water_temperature",
                    "design_entering_air_temperature",
                    "design_entering_air_wet_bulb_temperature",
                    "high_speed_sizing_factor",
                    "evaporation_loss_factor",
                    "drift_loss_percent",
                    "blowdown_concentration_ratio"
                ]
            }
        },
        "type": "object",
        "memo": "This model is based on Merkel's theory, which is also the basis for the cooling tower model in EnergyPlus. The Evaporative fluid cooler is modeled as a counter flow heat exchanger.",
        "min_fields": 23.0
    }
}
```
