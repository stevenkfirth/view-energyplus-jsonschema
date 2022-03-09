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
                "cooler_design_effectiveness": {
                    "type": "number",
                    "note": "effectiveness with respect to wet-bulb depression",
                    "minimum": 0.0,
                    "maximum": 1.0
                },
                "effectiveness_flow_ratio_modifier_curve_name": {
                    "type": "string",
                    "note": "this curve modifies the design effectiveness in the previous field by multiplying the value by the result of this curve. The effectiveness flow modifier curve is a function of flow fraction. Flow fraction is the ratio of current primary air flow rate to the primary air design flow rate. If this input field is left blank then, the effectiveness is assumed to be constant.",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
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
                "recirculating_water_pump_design_power": {
                    "units": "W",
                    "ip-units": "W",
                    "note": "This is the design water pump or spray for evaporation at the primary air design air flow rates and cooler design effectiveness",
                    "default": "Autosize",
                    "anyOf": [
                        {
                            "type": "number",
                            "minimum": 0.0
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
                    "note": "This field is used when the previous field is set to autosize. The pump power is scaled with Primary Air Design Air Flow Rate. This value was backed out from inputs in energy plus example files. Average Pump Power sizing factor was estimated from pump power and primary air design flow rates inputs from energyplus example files is about 90.0 [W/(m3/s)] (=90.0 ~ Pump Power / Primary Air Design Flow Rate). The factor ranges from 55.0 to 150.0 [W/(m3/s)]. The pump power can be sized to zero by setting this factor to zero."
                },
                "water_pump_power_modifier_curve_name": {
                    "type": "string",
                    "note": "this curve modifies the pump power in the previous field by multiplying the design power by the result of this curve. x = ff = flow fraction on the primary air. The flow fraction is the primary air flow rate during current operation divided by Primary Air Design Flow Rate",
                    "data_type": "object_list",
                    "object_list": [
                        "UnivariateFunctions"
                    ]
                },
                "air_inlet_node_name": {
                    "type": "string"
                },
                "air_outlet_node_name": {
                    "type": "string"
                },
                "sensor_node_name": {
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
                    "note": "Rate of drift loss as a fraction of evaporated water flow rate"
                },
                "blowdown_concentration_ratio": {
                    "type": "number",
                    "minimum": 2.0,
                    "note": "Characterizes the rate of blowdown in the evaporative cooler. Blowdown is water intentionally drained from the cooler in order to offset the build up of solids in the water that would otherwise occur because of evaporation. Ratio of solids in the blowdown water to solids in the make up water. A typical value is 3. If left blank then there is no blowdown."
                },
                "evaporative_operation_minimum_drybulb_temperature": {
                    "type": "number",
                    "minimum": -99.0,
                    "note": "This numeric field defines the evaporative cooler air inlet node drybulb temperature minimum limit in degrees Celsius. The evaporative cooler will be turned off when the evaporator cooler air inlet node dry-bulb temperature falls below this limit. The typical minimum value is 16degC. Users are allowed to specify their own limits. If this field is left blank, then there is no drybulb lower temperature limit for evaporative cooler operation."
                },
                "evaporative_operation_maximum_limit_wetbulb_temperature": {
                    "type": "number",
                    "note": "when outdoor wetbulb temperature rises above this limit the cooler shuts down. This numeric field defines the evaporative cooler air inlet node wet-bulb temperature maximum limit in degrees Celsius. The evaporative cooler will be turned off when the evaporative cooler air inlet node wet-bulb temperature exceeds this limit. The typical maximum value is 24degC. Users are allowed to specify their own limits. If this field is left blank, then there is no upper wetbulb temperature limit for evaporative cooler operation."
                },
                "evaporative_operation_maximum_limit_drybulb_temperature": {
                    "type": "number",
                    "note": "This numeric field defines the evaporative cooler air inlet node dry-bulb temperature maximum limit in degrees Celsius. The evaporative cooler will be turned off when its air inlet node drybulb temperature exceeds this limit. The typical maximum value is 26degC. Users are allowed to specify their own limits. If this field is left blank, then there is no upper temperature limit for evaporative cooler operation."
                }
            },
            "required": [
                "air_inlet_node_name",
                "air_outlet_node_name",
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
            "cooler_design_effectiveness": {
                "field_name": "Cooler Design Effectiveness",
                "field_type": "n"
            },
            "effectiveness_flow_ratio_modifier_curve_name": {
                "field_name": "Effectiveness Flow Ratio Modifier Curve Name",
                "field_type": "a"
            },
            "primary_air_design_flow_rate": {
                "field_name": "Primary Air Design Flow Rate",
                "field_type": "n"
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
            "air_inlet_node_name": {
                "field_name": "Air Inlet Node Name",
                "field_type": "a"
            },
            "air_outlet_node_name": {
                "field_name": "Air Outlet Node Name",
                "field_type": "a"
            },
            "sensor_node_name": {
                "field_name": "Sensor Node Name",
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
            "evaporative_operation_minimum_drybulb_temperature": {
                "field_name": "Evaporative Operation Minimum Drybulb Temperature",
                "field_type": "n"
            },
            "evaporative_operation_maximum_limit_wetbulb_temperature": {
                "field_name": "Evaporative Operation Maximum Limit Wetbulb Temperature",
                "field_type": "n"
            },
            "evaporative_operation_maximum_limit_drybulb_temperature": {
                "field_name": "Evaporative Operation Maximum Limit Drybulb Temperature",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "availability_schedule_name",
            "cooler_design_effectiveness",
            "effectiveness_flow_ratio_modifier_curve_name",
            "primary_air_design_flow_rate",
            "recirculating_water_pump_design_power",
            "water_pump_power_sizing_factor",
            "water_pump_power_modifier_curve_name",
            "air_inlet_node_name",
            "air_outlet_node_name",
            "sensor_node_name",
            "water_supply_storage_tank_name",
            "drift_loss_fraction",
            "blowdown_concentration_ratio",
            "evaporative_operation_minimum_drybulb_temperature",
            "evaporative_operation_maximum_limit_wetbulb_temperature",
            "evaporative_operation_maximum_limit_drybulb_temperature"
        ],
        "alphas": {
            "fields": [
                "name",
                "availability_schedule_name",
                "effectiveness_flow_ratio_modifier_curve_name",
                "water_pump_power_modifier_curve_name",
                "air_inlet_node_name",
                "air_outlet_node_name",
                "sensor_node_name",
                "water_supply_storage_tank_name"
            ]
        },
        "numerics": {
            "fields": [
                "cooler_design_effectiveness",
                "primary_air_design_flow_rate",
                "recirculating_water_pump_design_power",
                "water_pump_power_sizing_factor",
                "drift_loss_fraction",
                "blowdown_concentration_ratio",
                "evaporative_operation_minimum_drybulb_temperature",
                "evaporative_operation_maximum_limit_wetbulb_temperature",
                "evaporative_operation_maximum_limit_drybulb_temperature"
            ]
        }
    },
    "type": "object",
    "memo": "Direct evaporative cooler with user-specified effectiveness (can represent rigid pad or similar media), and recirculating water pump, and secondary air fan. This model is controlled to meet the primary air outlet temperature setpoint.",
    "min_fields": 11.0
}
```
