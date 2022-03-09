```
{
    "patternProperties": {
        ".*": {
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
                "cooler_wetbulb_design_effectiveness": {
                    "type": "number",
                    "note": "wet operation effectiveness with respect to wetbulb depression this is the nominal design wetbulb effectiveness at design air flow rates and water rate",
                    "minimum": 0.0,
                    "maximum": 2.0
                },
                "wetbulb_effectiveness_flow_ratio_modifier_curve_name": {
                    "type": "string",
                    "note": "this curve modifies the wetbulb effectiveness in the previous field (eff_wb_design) by multiplying the value by the result of this curve, eff_wb = eff_wb_design * func(HXFlowRatio) x = HXFlowRatio = sum of the primary and secondary flow rates divided by the sum of the design flow rates. If this input field is left blank, constant cooler wetbulb effectiveness is assumed. This input field is required in order to use operating range control based on the following three input fields: Evaporative Operation Minimum Limit Secondary Air Drybulb Temperature, Evaporative Operation Maximum Limit Outdoor Wetbulb Temperature, and Dry Operation Maximum Limit Outdoor Drybulb Temperature",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "cooler_drybulb_design_effectiveness": {
                    "type": "number",
                    "note": "dry operation effectiveness with respect to drybulb temperature difference this is the nominal design dryblub effectiveness at design air flow rates, no evaporation water active",
                    "minimum": 0.0
                },
                "drybulb_effectiveness_flow_ratio_modifier_curve_name": {
                    "type": "string",
                    "note": "this curve modifies the drybulb effectiveness in the previous field (eff_db_design) by multiplying the value by the result of this curve, eff_db = eff_db_design * f(HXFlowRatio) x = HXFlowRatio = sum of the primary and secondary flow rates divided by the sum of the design flow rates. If this input field is left blank, constant cooler drybulb effectiveness is assumed. This input field is required in order to use operating range control based on the following three input fields: Evaporative Operation Minimum Limit Secondary Air Drybulb Temperature, Evaporative Operation Maximum Limit Outdoor Wetbulb Temperature, and Dry Operation Maximum Limit Outdoor Drybulb Temperature",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "recirculating_water_pump_design_power": {
                    "units": "W",
                    "ip-units": "W",
                    "note": "This is the nominal design pump power of water recirculation and spray for evaporation at design air flow rates and cooler design effectiveness",
                    "default": "Autosize",
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
                "water_pump_power_sizing_factor": {
                    "type": "number",
                    "units": "W/(m3/s)",
                    "ip-units": "W/(gal/min)",
                    "default": 90.0,
                    "note": "This field is used when the previous field is set to autosize. The pump power is scaled with Secondary Air Design Air Flow Rate. This value was backed out from inputs in energy plus example files. Average Pump Power sizing factor was estimated from pump power and secondary air design flow rates inputs from energyplus example files is about 90.0 [W/(m3/s)] (=90.0 ~ Pump Power / Secondary Air Design Flow Rate). The factor ranges from 55.0 to 150.0 [W/(m3/s)] were noted. The pump power can be sized to zero by setting this factor to zero."
                },
                "water_pump_power_modifier_curve_name": {
                    "type": "string",
                    "note": "this curve modifies the pump power in the previous field by multiplying the design power by the result of this curve. x = ff = flow fraction on the secondary side, secondary air flow rate during operation divided by Secondary Air Design Air Flow Rate. If this input field is left blank, pump power is assumed to be proportional to part load ratio.",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "secondary_air_design_flow_rate": {
                    "units": "m3/s",
                    "default": "Autosize",
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
                "secondary_air_flow_scaling_factor": {
                    "type": "number",
                    "units": "dimensionless",
                    "default": 1.0,
                    "note": "This field is used when the previous field is set to autoize. The Primary Design Air Flow Rate is scaled using this factor to calculate the secondary design air flow rate."
                },
                "secondary_air_fan_design_power": {
                    "units": "W",
                    "note": "This is the fan design power at Secondary Design Air Flow Rate. This is the nominal design power at full speed.",
                    "default": "Autosize",
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
                "secondary_air_fan_sizing_specific_power": {
                    "type": "number",
                    "units": "W/(m3/s)",
                    "default": 250.0,
                    "note": "This field is used when the previous field is set to autosize. The fan power is scaled with Secondary Air Design Flow Rate. The default value is estimated from 125 Pa fan total pressure and fan total efficiency of 50.0% (250.0 = 125/0.5)."
                },
                "secondary_air_fan_power_modifier_curve_name": {
                    "type": "string",
                    "note": "this curve modifies the design fan power in the previous field by multiplying the value by the result of this curve. It should have a value of 1.0 at a x = 1.0. x = ff = flow fraction on the secondary side, secondary air flow rate during operation divided by Secondary Air Design Air Flow Rate. If this input field is left blank, the secondary fan power is assumed to be proportional to part load ratio.",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "primary_air_inlet_node_name": {
                    "type": "string"
                },
                "primary_air_outlet_node_name": {
                    "type": "string"
                },
                "primary_air_design_flow_rate": {
                    "units": "m3/s",
                    "default": "Autosize",
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
                "dewpoint_effectiveness_factor": {
                    "type": "number",
                    "minimum": 0.0
                },
                "secondary_air_inlet_node_name": {
                    "type": "string"
                },
                "secondary_air_outlet_node_name": {
                    "type": "string"
                },
                "sensor_node_name": {
                    "type": "string"
                },
                "relief_air_inlet_node_name": {
                    "type": "string"
                },
                "water_supply_storage_tank_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "WaterStorageTankNames"
                    ]
                },
                "drift_loss_fraction": {
                    "type": "number",
                    "minimum": 0.0,
                    "note": "Rate of drift loss as a fraction of evaporated water flow rate. If this input field is left blank, then zero drift loss is assumed.",
                    "default": 0.0
                },
                "blowdown_concentration_ratio": {
                    "type": "number",
                    "minimum": 2.0,
                    "note": "Characterizes the rate of blowdown in the evaporative cooler. Blowdown is water intentionally drained from the cooler in order to offset the build up of solids in the water that would otherwise occur because of evaporation. Ratio of solids in the blowdown water to solids in the make up water. A typical value is 3. If left blank then there is no blowdown."
                },
                "evaporative_operation_minimum_limit_secondary_air_drybulb_temperature": {
                    "type": "number",
                    "note": "This input field value defines the secondary air inlet node drybulb temperature limits in degreeCelsius. When the secondary side entering air dry bulb temperature drops below this limit, then the evaporative cooler operation mode changes to dry heat exchanger. Users specify their own limits. If this field is left blank, then there is no drybulb temperature lower limit for evaporative cooler operation. If operating range control is desired then this input field and the next two input fields should be specified or all the three should be left blank or left out. If no minimum drybulb temperature limit is desired while there are maximum drybulb and wetbulb temperature limits then specify very low minimum temperature limit value (e.g. -99.0C)."
                },
                "evaporative_operation_maximum_limit_outdoor_wetbulb_temperature": {
                    "type": "number",
                    "note": "This input field value defines the secondary air inlet node wetbulb temperature limits in degree Celsius. When the secondary side entering air wet bulb temperature exceeds this limit, then the evaporative cooler urns off and does not attempt to do any cooling. If this field is left blank, then there is no wetbulb temperature upper limit for evaporative cooler wet operation mode. If this input field is left blank then, the previous and the next input fields should also be left blank. If no maximum wetbulb temperature limits is desired while there are minimum drybulb and maximum drybulb upper temperature limits then specify very high maximum wetbulb temperature limit value (e.g. 99.0 C)."
                },
                "dry_operation_maximum_limit_outdoor_drybulb_temperature": {
                    "type": "number",
                    "note": "This input field value defines the secondary air inlet node drybulb temperature limits in degree Celsius. When the secondary side entering air drybulb temperature exceeds this limit, then the evaporative cooler will not run in dry operation mode or may be turned off depending on its wetbulb temperature. If this field is left blank, then there is no drybulb temperature maximum limit for evaporative cooler operation. If this input field is left blank then, the previous and the next input fields should also be left blank. If no maximum drybulb temperature limit is desired while there are minimum drybulb and maximum wetbulb upper temperature limits then specify very high maximum drybulb temperature limit value (e.g. 99.0 C)."
                }
            },
            "required": [
                "cooler_wetbulb_design_effectiveness",
                "primary_air_inlet_node_name",
                "primary_air_outlet_node_name",
                "secondary_air_inlet_node_name",
                "secondary_air_outlet_node_name",
                "sensor_node_name"
            ]
        }
    },
    "group": "Evaporative Coolers",
    "name": {
        "type": "string",
        "reference": [
            "EvapCoolerNames",
            "validBranchEquipmentNames",
            "validOASysEquipmentNames"
        ],
        "reference-class-name": [
            "validBranchEquipmentTypes",
            "validOASysEquipmentTypes"
        ]
    },
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
            "cooler_wetbulb_design_effectiveness": {
                "field_name": "Cooler Wetbulb Design Effectiveness",
                "field_type": "n"
            },
            "wetbulb_effectiveness_flow_ratio_modifier_curve_name": {
                "field_name": "Wetbulb Effectiveness Flow Ratio Modifier Curve Name",
                "field_type": "a"
            },
            "cooler_drybulb_design_effectiveness": {
                "field_name": "Cooler Drybulb Design Effectiveness",
                "field_type": "n"
            },
            "drybulb_effectiveness_flow_ratio_modifier_curve_name": {
                "field_name": "Drybulb Effectiveness Flow Ratio Modifier Curve Name",
                "field_type": "a"
            },
            "recirculating_water_pump_design_power": {
                "field_name": "Recirculating Water Pump Design Power",
                "field_type": "n"
            },
            "water_pump_power_sizing_factor": {
                "field_name": "Water Pump Power Sizing Factor",
                "field_type": "n"
            },
            "water_pump_power_modifier_curve_name": {
                "field_name": "Water Pump Power Modifier Curve Name",
                "field_type": "a"
            },
            "secondary_air_design_flow_rate": {
                "field_name": "Secondary Air Design Flow Rate",
                "field_type": "n"
            },
            "secondary_air_flow_scaling_factor": {
                "field_name": "Secondary Air Flow Scaling Factor",
                "field_type": "n"
            },
            "secondary_air_fan_design_power": {
                "field_name": "Secondary Air Fan Design Power",
                "field_type": "n"
            },
            "secondary_air_fan_sizing_specific_power": {
                "field_name": "Secondary Air Fan Sizing Specific Power",
                "field_type": "n"
            },
            "secondary_air_fan_power_modifier_curve_name": {
                "field_name": "Secondary Air Fan Power Modifier Curve Name",
                "field_type": "a"
            },
            "primary_air_inlet_node_name": {
                "field_name": "Primary Air Inlet Node Name",
                "field_type": "a"
            },
            "primary_air_outlet_node_name": {
                "field_name": "Primary Air Outlet Node Name",
                "field_type": "a"
            },
            "primary_air_design_flow_rate": {
                "field_name": "Primary Air Design Flow Rate",
                "field_type": "n"
            },
            "dewpoint_effectiveness_factor": {
                "field_name": "Dewpoint Effectiveness Factor",
                "field_type": "n"
            },
            "secondary_air_inlet_node_name": {
                "field_name": "Secondary Air Inlet Node Name",
                "field_type": "a"
            },
            "secondary_air_outlet_node_name": {
                "field_name": "Secondary Air Outlet Node Name",
                "field_type": "a"
            },
            "sensor_node_name": {
                "field_name": "Sensor Node Name",
                "field_type": "a"
            },
            "relief_air_inlet_node_name": {
                "field_name": "Relief Air Inlet Node Name",
                "field_type": "a"
            },
            "water_supply_storage_tank_name": {
                "field_name": "Water Supply Storage Tank Name",
                "field_type": "a"
            },
            "drift_loss_fraction": {
                "field_name": "Drift Loss Fraction",
                "field_type": "n"
            },
            "blowdown_concentration_ratio": {
                "field_name": "Blowdown Concentration Ratio",
                "field_type": "n"
            },
            "evaporative_operation_minimum_limit_secondary_air_drybulb_temperature": {
                "field_name": "Evaporative Operation Minimum Limit Secondary Air Drybulb Temperature",
                "field_type": "n"
            },
            "evaporative_operation_maximum_limit_outdoor_wetbulb_temperature": {
                "field_name": "Evaporative Operation Maximum Limit Outdoor Wetbulb Temperature",
                "field_type": "n"
            },
            "dry_operation_maximum_limit_outdoor_drybulb_temperature": {
                "field_name": "Dry Operation Maximum Limit Outdoor Drybulb Temperature",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "availability_schedule_name",
            "cooler_wetbulb_design_effectiveness",
            "wetbulb_effectiveness_flow_ratio_modifier_curve_name",
            "cooler_drybulb_design_effectiveness",
            "drybulb_effectiveness_flow_ratio_modifier_curve_name",
            "recirculating_water_pump_design_power",
            "water_pump_power_sizing_factor",
            "water_pump_power_modifier_curve_name",
            "secondary_air_design_flow_rate",
            "secondary_air_flow_scaling_factor",
            "secondary_air_fan_design_power",
            "secondary_air_fan_sizing_specific_power",
            "secondary_air_fan_power_modifier_curve_name",
            "primary_air_inlet_node_name",
            "primary_air_outlet_node_name",
            "primary_air_design_flow_rate",
            "dewpoint_effectiveness_factor",
            "secondary_air_inlet_node_name",
            "secondary_air_outlet_node_name",
            "sensor_node_name",
            "relief_air_inlet_node_name",
            "water_supply_storage_tank_name",
            "drift_loss_fraction",
            "blowdown_concentration_ratio",
            "evaporative_operation_minimum_limit_secondary_air_drybulb_temperature",
            "evaporative_operation_maximum_limit_outdoor_wetbulb_temperature",
            "dry_operation_maximum_limit_outdoor_drybulb_temperature"
        ],
        "alphas": {
            "fields": [
                "name",
                "availability_schedule_name",
                "wetbulb_effectiveness_flow_ratio_modifier_curve_name",
                "drybulb_effectiveness_flow_ratio_modifier_curve_name",
                "water_pump_power_modifier_curve_name",
                "secondary_air_fan_power_modifier_curve_name",
                "primary_air_inlet_node_name",
                "primary_air_outlet_node_name",
                "secondary_air_inlet_node_name",
                "secondary_air_outlet_node_name",
                "sensor_node_name",
                "relief_air_inlet_node_name",
                "water_supply_storage_tank_name"
            ]
        },
        "numerics": {
            "fields": [
                "cooler_wetbulb_design_effectiveness",
                "cooler_drybulb_design_effectiveness",
                "recirculating_water_pump_design_power",
                "water_pump_power_sizing_factor",
                "secondary_air_design_flow_rate",
                "secondary_air_flow_scaling_factor",
                "secondary_air_fan_design_power",
                "secondary_air_fan_sizing_specific_power",
                "primary_air_design_flow_rate",
                "dewpoint_effectiveness_factor",
                "drift_loss_fraction",
                "blowdown_concentration_ratio",
                "evaporative_operation_minimum_limit_secondary_air_drybulb_temperature",
                "evaporative_operation_maximum_limit_outdoor_wetbulb_temperature",
                "dry_operation_maximum_limit_outdoor_drybulb_temperature"
            ]
        }
    },
    "type": "object",
    "memo": "Indirect evaporative cooler with user-specified effectiveness (can represent rigid pad or wetted coil), recirculating water pump, and secondary air fan. This model is controlled to meet the primary air outlet temperature setpoint.",
    "min_fields": 21.0
}
```
