```
{
    "WaterHeater:Mixed": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "tank_volume": {
                        "units": "m3",
                        "default": 0.0,
                        "ip-units": "gal",
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
                    "setpoint_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "deadband_temperature_difference": {
                        "type": "number",
                        "units": "deltaC",
                        "minimum": 0.0,
                        "default": 0.0
                    },
                    "maximum_temperature_limit": {
                        "type": "number",
                        "units": "C"
                    },
                    "heater_control_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "Cycle",
                            "Modulate"
                        ],
                        "default": "Cycle"
                    },
                    "heater_maximum_capacity": {
                        "units": "W",
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
                    "heater_minimum_capacity": {
                        "type": "number",
                        "note": "Only used when Heater Control Type is set to Modulate",
                        "units": "W",
                        "minimum": 0.0
                    },
                    "heater_ignition_minimum_flow_rate": {
                        "type": "number",
                        "note": "Not yet implemented",
                        "units": "m3/s",
                        "ip-units": "gal/min",
                        "minimum": 0.0,
                        "default": 0.0
                    },
                    "heater_ignition_delay": {
                        "type": "number",
                        "note": "Not yet implemented",
                        "units": "s",
                        "minimum": 0.0,
                        "default": 0.0
                    },
                    "heater_fuel_type": {
                        "type": "string",
                        "enum": [
                            "Coal",
                            "Diesel",
                            "DistrictHeating",
                            "Electricity",
                            "FuelOilNo1",
                            "FuelOilNo2",
                            "Gasoline",
                            "NaturalGas",
                            "OtherFuel1",
                            "OtherFuel2",
                            "Propane",
                            "Steam"
                        ]
                    },
                    "heater_thermal_efficiency": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "maximum": 1.0
                    },
                    "part_load_factor_curve_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "UnivariateFunctions"
                        ]
                    },
                    "off_cycle_parasitic_fuel_consumption_rate": {
                        "type": "number",
                        "units": "W",
                        "minimum": 0.0,
                        "default": 0.0
                    },
                    "off_cycle_parasitic_fuel_type": {
                        "type": "string",
                        "enum": [
                            "Coal",
                            "Diesel",
                            "DistrictHeating",
                            "Electricity",
                            "FuelOilNo1",
                            "FuelOilNo2",
                            "Gasoline",
                            "NaturalGas",
                            "OtherFuel1",
                            "OtherFuel2",
                            "Propane",
                            "Steam"
                        ]
                    },
                    "off_cycle_parasitic_heat_fraction_to_tank": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.0
                    },
                    "on_cycle_parasitic_fuel_consumption_rate": {
                        "type": "number",
                        "units": "W",
                        "minimum": 0.0,
                        "default": 0.0
                    },
                    "on_cycle_parasitic_fuel_type": {
                        "type": "string",
                        "enum": [
                            "Coal",
                            "Diesel",
                            "DistrictHeating",
                            "Electricity",
                            "FuelOilNo1",
                            "FuelOilNo2",
                            "Gasoline",
                            "NaturalGas",
                            "OtherFuel1",
                            "OtherFuel2",
                            "Propane",
                            "Steam"
                        ]
                    },
                    "on_cycle_parasitic_heat_fraction_to_tank": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.0
                    },
                    "ambient_temperature_indicator": {
                        "type": "string",
                        "enum": [
                            "Outdoors",
                            "Schedule",
                            "Zone"
                        ]
                    },
                    "ambient_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "ambient_temperature_zone_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ]
                    },
                    "ambient_temperature_outdoor_air_node_name": {
                        "type": "string",
                        "note": "required for Ambient Temperature Indicator=Outdoors"
                    },
                    "off_cycle_loss_coefficient_to_ambient_temperature": {
                        "type": "number",
                        "units": "W/K",
                        "minimum": 0.0
                    },
                    "off_cycle_loss_fraction_to_zone": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 1.0
                    },
                    "on_cycle_loss_coefficient_to_ambient_temperature": {
                        "type": "number",
                        "units": "W/K",
                        "minimum": 0.0
                    },
                    "on_cycle_loss_fraction_to_zone": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 1.0
                    },
                    "peak_use_flow_rate": {
                        "type": "number",
                        "units": "m3/s",
                        "ip-units": "gal/min",
                        "minimum": 0.0,
                        "note": "Only used if Use Side Node connections are blank"
                    },
                    "use_flow_rate_fraction_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "Only used if Use Side Node connections are blank"
                    },
                    "cold_water_supply_temperature_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "Only used if Use Side Node connections are blank Defaults to water temperatures calculated by Site:WaterMainsTemperature object"
                    },
                    "use_side_inlet_node_name": {
                        "type": "string"
                    },
                    "use_side_outlet_node_name": {
                        "type": "string"
                    },
                    "use_side_effectiveness": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 1.0
                    },
                    "source_side_inlet_node_name": {
                        "type": "string"
                    },
                    "source_side_outlet_node_name": {
                        "type": "string"
                    },
                    "source_side_effectiveness": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "maximum": 1.0,
                        "default": 1.0
                    },
                    "use_side_design_flow_rate": {
                        "default": "Autosize",
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
                                    "",
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "source_side_design_flow_rate": {
                        "default": "Autosize",
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
                                    "",
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "indirect_water_heating_recovery_time": {
                        "type": "number",
                        "default": 1.5,
                        "note": "Parameter for autosizing design flow rates for indirectly heated water tanks Time required to raise temperature of entire tank from 14.4C to 57.2C",
                        "units": "hr",
                        "exclusiveMinimum": 0.0
                    },
                    "source_side_flow_control_mode": {
                        "type": "string",
                        "enum": [
                            "",
                            "IndirectHeatAlternateSetpoint",
                            "IndirectHeatPrimarySetpoint",
                            "StorageTank"
                        ],
                        "default": "IndirectHeatPrimarySetpoint",
                        "note": "StorageTank mode always requests flow unless tank is at its Maximum Temperature Limit IndirectHeatPrimarySetpoint mode requests flow whenever primary setpoint calls for heat IndirectHeatAlternateSetpoint mode requests flow whenever alternate indirect setpoint calls for heat"
                    },
                    "indirect_alternate_setpoint_temperature_schedule_name": {
                        "type": "string",
                        "note": "This field is only used if the previous is set to IndirectHeatAlternateSetpoint",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
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
                    "setpoint_temperature_schedule_name",
                    "heater_fuel_type",
                    "heater_thermal_efficiency",
                    "ambient_temperature_indicator"
                ]
            }
        },
        "group": "Water Heaters and Thermal Storage",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "WaterHeaterMixedNames",
                "WaterHeaterNames",
                "validBranchEquipmentNames",
                "validCondenserEquipmentNames",
                "validPlantEquipmentNames"
            ],
            "reference-class-name": [
                "validBranchEquipmentTypes",
                "validCondenserEquipmentTypes",
                "validPlantEquipmentTypes"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "tank_volume": {
                    "field_name": "Tank Volume",
                    "field_type": "n"
                },
                "setpoint_temperature_schedule_name": {
                    "field_name": "Setpoint Temperature Schedule Name",
                    "field_type": "a"
                },
                "deadband_temperature_difference": {
                    "field_name": "Deadband Temperature Difference",
                    "field_type": "n"
                },
                "maximum_temperature_limit": {
                    "field_name": "Maximum Temperature Limit",
                    "field_type": "n"
                },
                "heater_control_type": {
                    "field_name": "Heater Control Type",
                    "field_type": "a"
                },
                "heater_maximum_capacity": {
                    "field_name": "Heater Maximum Capacity",
                    "field_type": "n"
                },
                "heater_minimum_capacity": {
                    "field_name": "Heater Minimum Capacity",
                    "field_type": "n"
                },
                "heater_ignition_minimum_flow_rate": {
                    "field_name": "Heater Ignition Minimum Flow Rate",
                    "field_type": "n"
                },
                "heater_ignition_delay": {
                    "field_name": "Heater Ignition Delay",
                    "field_type": "n"
                },
                "heater_fuel_type": {
                    "field_name": "Heater Fuel Type",
                    "field_type": "a"
                },
                "heater_thermal_efficiency": {
                    "field_name": "Heater Thermal Efficiency",
                    "field_type": "n"
                },
                "part_load_factor_curve_name": {
                    "field_name": "Part Load Factor Curve Name",
                    "field_type": "a"
                },
                "off_cycle_parasitic_fuel_consumption_rate": {
                    "field_name": "Off Cycle Parasitic Fuel Consumption Rate",
                    "field_type": "n"
                },
                "off_cycle_parasitic_fuel_type": {
                    "field_name": "Off Cycle Parasitic Fuel Type",
                    "field_type": "a"
                },
                "off_cycle_parasitic_heat_fraction_to_tank": {
                    "field_name": "Off Cycle Parasitic Heat Fraction to Tank",
                    "field_type": "n"
                },
                "on_cycle_parasitic_fuel_consumption_rate": {
                    "field_name": "On Cycle Parasitic Fuel Consumption Rate",
                    "field_type": "n"
                },
                "on_cycle_parasitic_fuel_type": {
                    "field_name": "On Cycle Parasitic Fuel Type",
                    "field_type": "a"
                },
                "on_cycle_parasitic_heat_fraction_to_tank": {
                    "field_name": "On Cycle Parasitic Heat Fraction to Tank",
                    "field_type": "n"
                },
                "ambient_temperature_indicator": {
                    "field_name": "Ambient Temperature Indicator",
                    "field_type": "a"
                },
                "ambient_temperature_schedule_name": {
                    "field_name": "Ambient Temperature Schedule Name",
                    "field_type": "a"
                },
                "ambient_temperature_zone_name": {
                    "field_name": "Ambient Temperature Zone Name",
                    "field_type": "a"
                },
                "ambient_temperature_outdoor_air_node_name": {
                    "field_name": "Ambient Temperature Outdoor Air Node Name",
                    "field_type": "a"
                },
                "off_cycle_loss_coefficient_to_ambient_temperature": {
                    "field_name": "Off Cycle Loss Coefficient to Ambient Temperature",
                    "field_type": "n"
                },
                "off_cycle_loss_fraction_to_zone": {
                    "field_name": "Off Cycle Loss Fraction to Zone",
                    "field_type": "n"
                },
                "on_cycle_loss_coefficient_to_ambient_temperature": {
                    "field_name": "On Cycle Loss Coefficient to Ambient Temperature",
                    "field_type": "n"
                },
                "on_cycle_loss_fraction_to_zone": {
                    "field_name": "On Cycle Loss Fraction to Zone",
                    "field_type": "n"
                },
                "peak_use_flow_rate": {
                    "field_name": "Peak Use Flow Rate",
                    "field_type": "n"
                },
                "use_flow_rate_fraction_schedule_name": {
                    "field_name": "Use Flow Rate Fraction Schedule Name",
                    "field_type": "a"
                },
                "cold_water_supply_temperature_schedule_name": {
                    "field_name": "Cold Water Supply Temperature Schedule Name",
                    "field_type": "a"
                },
                "use_side_inlet_node_name": {
                    "field_name": "Use Side Inlet Node Name",
                    "field_type": "a"
                },
                "use_side_outlet_node_name": {
                    "field_name": "Use Side Outlet Node Name",
                    "field_type": "a"
                },
                "use_side_effectiveness": {
                    "field_name": "Use Side Effectiveness",
                    "field_type": "n"
                },
                "source_side_inlet_node_name": {
                    "field_name": "Source Side Inlet Node Name",
                    "field_type": "a"
                },
                "source_side_outlet_node_name": {
                    "field_name": "Source Side Outlet Node Name",
                    "field_type": "a"
                },
                "source_side_effectiveness": {
                    "field_name": "Source Side Effectiveness",
                    "field_type": "n"
                },
                "use_side_design_flow_rate": {
                    "field_name": "Use Side Design Flow Rate",
                    "field_type": "n"
                },
                "source_side_design_flow_rate": {
                    "field_name": "Source Side Design Flow Rate",
                    "field_type": "n"
                },
                "indirect_water_heating_recovery_time": {
                    "field_name": "Indirect Water Heating Recovery Time",
                    "field_type": "n"
                },
                "source_side_flow_control_mode": {
                    "field_name": "Source Side Flow Control Mode",
                    "field_type": "a"
                },
                "indirect_alternate_setpoint_temperature_schedule_name": {
                    "field_name": "Indirect Alternate Setpoint Temperature Schedule Name",
                    "field_type": "a"
                },
                "end_use_subcategory": {
                    "field_name": "End-Use Subcategory",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "tank_volume",
                "setpoint_temperature_schedule_name",
                "deadband_temperature_difference",
                "maximum_temperature_limit",
                "heater_control_type",
                "heater_maximum_capacity",
                "heater_minimum_capacity",
                "heater_ignition_minimum_flow_rate",
                "heater_ignition_delay",
                "heater_fuel_type",
                "heater_thermal_efficiency",
                "part_load_factor_curve_name",
                "off_cycle_parasitic_fuel_consumption_rate",
                "off_cycle_parasitic_fuel_type",
                "off_cycle_parasitic_heat_fraction_to_tank",
                "on_cycle_parasitic_fuel_consumption_rate",
                "on_cycle_parasitic_fuel_type",
                "on_cycle_parasitic_heat_fraction_to_tank",
                "ambient_temperature_indicator",
                "ambient_temperature_schedule_name",
                "ambient_temperature_zone_name",
                "ambient_temperature_outdoor_air_node_name",
                "off_cycle_loss_coefficient_to_ambient_temperature",
                "off_cycle_loss_fraction_to_zone",
                "on_cycle_loss_coefficient_to_ambient_temperature",
                "on_cycle_loss_fraction_to_zone",
                "peak_use_flow_rate",
                "use_flow_rate_fraction_schedule_name",
                "cold_water_supply_temperature_schedule_name",
                "use_side_inlet_node_name",
                "use_side_outlet_node_name",
                "use_side_effectiveness",
                "source_side_inlet_node_name",
                "source_side_outlet_node_name",
                "source_side_effectiveness",
                "use_side_design_flow_rate",
                "source_side_design_flow_rate",
                "indirect_water_heating_recovery_time",
                "source_side_flow_control_mode",
                "indirect_alternate_setpoint_temperature_schedule_name",
                "end_use_subcategory"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "setpoint_temperature_schedule_name",
                    "heater_control_type",
                    "heater_fuel_type",
                    "part_load_factor_curve_name",
                    "off_cycle_parasitic_fuel_type",
                    "on_cycle_parasitic_fuel_type",
                    "ambient_temperature_indicator",
                    "ambient_temperature_schedule_name",
                    "ambient_temperature_zone_name",
                    "ambient_temperature_outdoor_air_node_name",
                    "use_flow_rate_fraction_schedule_name",
                    "cold_water_supply_temperature_schedule_name",
                    "use_side_inlet_node_name",
                    "use_side_outlet_node_name",
                    "source_side_inlet_node_name",
                    "source_side_outlet_node_name",
                    "source_side_flow_control_mode",
                    "indirect_alternate_setpoint_temperature_schedule_name",
                    "end_use_subcategory"
                ]
            },
            "numerics": {
                "fields": [
                    "tank_volume",
                    "deadband_temperature_difference",
                    "maximum_temperature_limit",
                    "heater_maximum_capacity",
                    "heater_minimum_capacity",
                    "heater_ignition_minimum_flow_rate",
                    "heater_ignition_delay",
                    "heater_thermal_efficiency",
                    "off_cycle_parasitic_fuel_consumption_rate",
                    "off_cycle_parasitic_heat_fraction_to_tank",
                    "on_cycle_parasitic_fuel_consumption_rate",
                    "on_cycle_parasitic_heat_fraction_to_tank",
                    "off_cycle_loss_coefficient_to_ambient_temperature",
                    "off_cycle_loss_fraction_to_zone",
                    "on_cycle_loss_coefficient_to_ambient_temperature",
                    "on_cycle_loss_fraction_to_zone",
                    "peak_use_flow_rate",
                    "use_side_effectiveness",
                    "source_side_effectiveness",
                    "use_side_design_flow_rate",
                    "source_side_design_flow_rate",
                    "indirect_water_heating_recovery_time"
                ]
            }
        },
        "type": "object",
        "memo": "Water heater with well-mixed, single-node water tank. May be used to model a tankless water heater (small tank volume), a hot water storage tank (zero heater capacity), or a heat pump water heater (see WaterHeater:HeatPump:PumpedCondenser.)"
    }
}
```
