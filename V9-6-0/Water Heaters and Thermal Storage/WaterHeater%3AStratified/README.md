```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "end_use_subcategory": {
                    "type": "string",
                    "note": "Any text may be used here to categorize the end-uses in the ABUPS End Uses by Subcategory table.",
                    "retaincase": true,
                    "default": "General"
                },
                "tank_volume": {
                    "units": "m3",
                    "ip-units": "gal",
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
                "tank_height": {
                    "units": "m",
                    "note": "Height is measured in the axial direction for horizontal cylinders",
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
                "tank_shape": {
                    "type": "string",
                    "enum": [
                        "",
                        "HorizontalCylinder",
                        "Other",
                        "VerticalCylinder"
                    ],
                    "default": "VerticalCylinder"
                },
                "tank_perimeter": {
                    "type": "number",
                    "units": "m",
                    "minimum": 0.0,
                    "note": "Only used if Tank Shape is Other"
                },
                "maximum_temperature_limit": {
                    "type": "number",
                    "units": "C"
                },
                "heater_priority_control": {
                    "type": "string",
                    "enum": [
                        "",
                        "MasterSlave",
                        "Simultaneous"
                    ],
                    "default": "MasterSlave"
                },
                "heater_1_setpoint_temperature_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "heater_1_deadband_temperature_difference": {
                    "type": "number",
                    "units": "deltaC",
                    "minimum": 0.0,
                    "default": 0.0
                },
                "heater_1_capacity": {
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
                "heater_1_height": {
                    "type": "number",
                    "units": "m",
                    "minimum": 0.0
                },
                "heater_2_setpoint_temperature_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "heater_2_deadband_temperature_difference": {
                    "type": "number",
                    "units": "deltaC",
                    "minimum": 0.0,
                    "default": 0.0
                },
                "heater_2_capacity": {
                    "type": "number",
                    "units": "W",
                    "minimum": 0.0
                },
                "heater_2_height": {
                    "type": "number",
                    "units": "m",
                    "minimum": 0.0
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
                "off_cycle_parasitic_height": {
                    "type": "number",
                    "units": "m",
                    "minimum": 0.0,
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
                "on_cycle_parasitic_height": {
                    "type": "number",
                    "units": "m",
                    "minimum": 0.0,
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
                "uniform_skin_loss_coefficient_per_unit_area_to_ambient_temperature": {
                    "type": "number",
                    "units": "W/m2-K",
                    "minimum": 0.0
                },
                "skin_loss_fraction_to_zone": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 1.0
                },
                "off_cycle_flue_loss_coefficient_to_ambient_temperature": {
                    "type": "number",
                    "units": "W/K",
                    "minimum": 0.0
                },
                "off_cycle_flue_loss_fraction_to_zone": {
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
                    "note": "If blank, defaults to 1.0 at all times Only used if use side node connections are blank"
                },
                "cold_water_supply_temperature_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "Only used if use side node connections are blank Defaults to water temperatures calculated by Site:WaterMainsTemperature object"
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
                    "default": 1.0,
                    "note": "The use side effectiveness in the stratified tank model is a simplified analogy of a heat exchanger's effectiveness. This effectiveness is equal to the fraction of use mass flow rate that directly mixes with the tank fluid. And one minus the effectiveness is the fraction that bypasses the tank. The use side mass flow rate that bypasses the tank is mixed with the fluid or water leaving the stratified tank."
                },
                "use_side_inlet_height": {
                    "type": "number",
                    "units": "m",
                    "minimum": 0.0,
                    "default": 0.0,
                    "note": "Defaults to bottom of tank"
                },
                "use_side_outlet_height": {
                    "units": "m",
                    "default": "Autocalculate",
                    "note": "Defaults to top of tank",
                    "anyOf": [
                        {
                            "type": "number",
                            "minimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "",
                                "Autocalculate"
                            ]
                        }
                    ]
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
                    "default": 1.0,
                    "note": "The source side effectiveness in the stratified tank model is a simplified analogy of a heat exchanger's effectiveness. This effectiveness is equal to the fraction of source mass flow rate that directly mixes with the tank fluid. And one minus the effectiveness is the fraction that bypasses the tank. The source side mass flow rate that bypasses the tank is mixed with the fluid or water leaving the stratified tank."
                },
                "source_side_inlet_height": {
                    "units": "m",
                    "default": "Autocalculate",
                    "note": "Defaults to top of tank",
                    "anyOf": [
                        {
                            "type": "number",
                            "minimum": 0.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "",
                                "Autocalculate"
                            ]
                        }
                    ]
                },
                "source_side_outlet_height": {
                    "type": "number",
                    "units": "m",
                    "minimum": 0.0,
                    "default": 0.0,
                    "note": "Defaults to bottom of tank"
                },
                "inlet_mode": {
                    "type": "string",
                    "enum": [
                        "",
                        "Fixed",
                        "Seeking"
                    ],
                    "default": "Fixed"
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
                    "note": "Parameter for autosizing design flow rates for indirectly heated water tanks time required to raise temperature of entire tank from 14.4C to 57.2C",
                    "units": "hr",
                    "exclusiveMinimum": 0.0
                },
                "number_of_nodes": {
                    "type": "number",
                    "minimum": 1.0,
                    "maximum": 12.0,
                    "default": 1.0
                },
                "additional_destratification_conductivity": {
                    "type": "number",
                    "units": "W/m-K",
                    "minimum": 0.0,
                    "default": 0.0
                },
                "node_1_additional_loss_coefficient": {
                    "type": "number",
                    "units": "W/K",
                    "default": 0.0
                },
                "node_2_additional_loss_coefficient": {
                    "type": "number",
                    "units": "W/K",
                    "default": 0.0
                },
                "node_3_additional_loss_coefficient": {
                    "type": "number",
                    "units": "W/K",
                    "default": 0.0
                },
                "node_4_additional_loss_coefficient": {
                    "type": "number",
                    "units": "W/K",
                    "default": 0.0
                },
                "node_5_additional_loss_coefficient": {
                    "type": "number",
                    "units": "W/K",
                    "default": 0.0
                },
                "node_6_additional_loss_coefficient": {
                    "type": "number",
                    "units": "W/K",
                    "default": 0.0
                },
                "node_7_additional_loss_coefficient": {
                    "type": "number",
                    "units": "W/K",
                    "default": 0.0
                },
                "node_8_additional_loss_coefficient": {
                    "type": "number",
                    "units": "W/K",
                    "default": 0.0
                },
                "node_9_additional_loss_coefficient": {
                    "type": "number",
                    "units": "W/K",
                    "default": 0.0
                },
                "node_10_additional_loss_coefficient": {
                    "type": "number",
                    "units": "W/K",
                    "default": 0.0
                },
                "node_11_additional_loss_coefficient": {
                    "type": "number",
                    "units": "W/K",
                    "default": 0.0
                },
                "node_12_additional_loss_coefficient": {
                    "type": "number",
                    "units": "W/K",
                    "default": 0.0
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
                    "note": "StorageTank mode always requests flow unless tank is at its Maximum Temperature Limit IndirectHeatPrimarySetpoint mode requests flow whenever primary setpoint for heater 1 calls for heat IndirectHeatAlternateSetpoint mode requests flow whenever alternate indirect setpoint calls for heat"
                },
                "indirect_alternate_setpoint_temperature_schedule_name": {
                    "type": "string",
                    "note": "This field is only used if the previous is set to IndirectHeatAlternateSetpoint",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                }
            },
            "required": [
                "tank_volume",
                "tank_height",
                "heater_1_setpoint_temperature_schedule_name",
                "heater_2_setpoint_temperature_schedule_name",
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
            "WaterHeaterNames",
            "WaterHeaterStratifiedNames",
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
            "end_use_subcategory": {
                "field_name": "End-Use Subcategory",
                "field_type": "a"
            },
            "tank_volume": {
                "field_name": "Tank Volume",
                "field_type": "n"
            },
            "tank_height": {
                "field_name": "Tank Height",
                "field_type": "n"
            },
            "tank_shape": {
                "field_name": "Tank Shape",
                "field_type": "a"
            },
            "tank_perimeter": {
                "field_name": "Tank Perimeter",
                "field_type": "n"
            },
            "maximum_temperature_limit": {
                "field_name": "Maximum Temperature Limit",
                "field_type": "n"
            },
            "heater_priority_control": {
                "field_name": "Heater Priority Control",
                "field_type": "a"
            },
            "heater_1_setpoint_temperature_schedule_name": {
                "field_name": "Heater 1 Setpoint Temperature Schedule Name",
                "field_type": "a"
            },
            "heater_1_deadband_temperature_difference": {
                "field_name": "Heater 1 Deadband Temperature Difference",
                "field_type": "n"
            },
            "heater_1_capacity": {
                "field_name": "Heater 1 Capacity",
                "field_type": "n"
            },
            "heater_1_height": {
                "field_name": "Heater 1 Height",
                "field_type": "n"
            },
            "heater_2_setpoint_temperature_schedule_name": {
                "field_name": "Heater 2 Setpoint Temperature Schedule Name",
                "field_type": "a"
            },
            "heater_2_deadband_temperature_difference": {
                "field_name": "Heater 2 Deadband Temperature Difference",
                "field_type": "n"
            },
            "heater_2_capacity": {
                "field_name": "Heater 2 Capacity",
                "field_type": "n"
            },
            "heater_2_height": {
                "field_name": "Heater 2 Height",
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
            "off_cycle_parasitic_height": {
                "field_name": "Off Cycle Parasitic Height",
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
            "on_cycle_parasitic_height": {
                "field_name": "On Cycle Parasitic Height",
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
            "uniform_skin_loss_coefficient_per_unit_area_to_ambient_temperature": {
                "field_name": "Uniform Skin Loss Coefficient per Unit Area to Ambient Temperature",
                "field_type": "n"
            },
            "skin_loss_fraction_to_zone": {
                "field_name": "Skin Loss Fraction to Zone",
                "field_type": "n"
            },
            "off_cycle_flue_loss_coefficient_to_ambient_temperature": {
                "field_name": "Off Cycle Flue Loss Coefficient to Ambient Temperature",
                "field_type": "n"
            },
            "off_cycle_flue_loss_fraction_to_zone": {
                "field_name": "Off Cycle Flue Loss Fraction to Zone",
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
            "use_side_inlet_height": {
                "field_name": "Use Side Inlet Height",
                "field_type": "n"
            },
            "use_side_outlet_height": {
                "field_name": "Use Side Outlet Height",
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
            "source_side_inlet_height": {
                "field_name": "Source Side Inlet Height",
                "field_type": "n"
            },
            "source_side_outlet_height": {
                "field_name": "Source Side Outlet Height",
                "field_type": "n"
            },
            "inlet_mode": {
                "field_name": "Inlet Mode",
                "field_type": "a"
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
            "number_of_nodes": {
                "field_name": "Number of Nodes",
                "field_type": "n"
            },
            "additional_destratification_conductivity": {
                "field_name": "Additional Destratification Conductivity",
                "field_type": "n"
            },
            "node_1_additional_loss_coefficient": {
                "field_name": "Node 1 Additional Loss Coefficient",
                "field_type": "n"
            },
            "node_2_additional_loss_coefficient": {
                "field_name": "Node 2 Additional Loss Coefficient",
                "field_type": "n"
            },
            "node_3_additional_loss_coefficient": {
                "field_name": "Node 3 Additional Loss Coefficient",
                "field_type": "n"
            },
            "node_4_additional_loss_coefficient": {
                "field_name": "Node 4 Additional Loss Coefficient",
                "field_type": "n"
            },
            "node_5_additional_loss_coefficient": {
                "field_name": "Node 5 Additional Loss Coefficient",
                "field_type": "n"
            },
            "node_6_additional_loss_coefficient": {
                "field_name": "Node 6 Additional Loss Coefficient",
                "field_type": "n"
            },
            "node_7_additional_loss_coefficient": {
                "field_name": "Node 7 Additional Loss Coefficient",
                "field_type": "n"
            },
            "node_8_additional_loss_coefficient": {
                "field_name": "Node 8 Additional Loss Coefficient",
                "field_type": "n"
            },
            "node_9_additional_loss_coefficient": {
                "field_name": "Node 9 Additional Loss Coefficient",
                "field_type": "n"
            },
            "node_10_additional_loss_coefficient": {
                "field_name": "Node 10 Additional Loss Coefficient",
                "field_type": "n"
            },
            "node_11_additional_loss_coefficient": {
                "field_name": "Node 11 Additional Loss Coefficient",
                "field_type": "n"
            },
            "node_12_additional_loss_coefficient": {
                "field_name": "Node 12 Additional Loss Coefficient",
                "field_type": "n"
            },
            "source_side_flow_control_mode": {
                "field_name": "Source Side Flow Control Mode",
                "field_type": "a"
            },
            "indirect_alternate_setpoint_temperature_schedule_name": {
                "field_name": "Indirect Alternate Setpoint Temperature Schedule Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "end_use_subcategory",
            "tank_volume",
            "tank_height",
            "tank_shape",
            "tank_perimeter",
            "maximum_temperature_limit",
            "heater_priority_control",
            "heater_1_setpoint_temperature_schedule_name",
            "heater_1_deadband_temperature_difference",
            "heater_1_capacity",
            "heater_1_height",
            "heater_2_setpoint_temperature_schedule_name",
            "heater_2_deadband_temperature_difference",
            "heater_2_capacity",
            "heater_2_height",
            "heater_fuel_type",
            "heater_thermal_efficiency",
            "off_cycle_parasitic_fuel_consumption_rate",
            "off_cycle_parasitic_fuel_type",
            "off_cycle_parasitic_heat_fraction_to_tank",
            "off_cycle_parasitic_height",
            "on_cycle_parasitic_fuel_consumption_rate",
            "on_cycle_parasitic_fuel_type",
            "on_cycle_parasitic_heat_fraction_to_tank",
            "on_cycle_parasitic_height",
            "ambient_temperature_indicator",
            "ambient_temperature_schedule_name",
            "ambient_temperature_zone_name",
            "ambient_temperature_outdoor_air_node_name",
            "uniform_skin_loss_coefficient_per_unit_area_to_ambient_temperature",
            "skin_loss_fraction_to_zone",
            "off_cycle_flue_loss_coefficient_to_ambient_temperature",
            "off_cycle_flue_loss_fraction_to_zone",
            "peak_use_flow_rate",
            "use_flow_rate_fraction_schedule_name",
            "cold_water_supply_temperature_schedule_name",
            "use_side_inlet_node_name",
            "use_side_outlet_node_name",
            "use_side_effectiveness",
            "use_side_inlet_height",
            "use_side_outlet_height",
            "source_side_inlet_node_name",
            "source_side_outlet_node_name",
            "source_side_effectiveness",
            "source_side_inlet_height",
            "source_side_outlet_height",
            "inlet_mode",
            "use_side_design_flow_rate",
            "source_side_design_flow_rate",
            "indirect_water_heating_recovery_time",
            "number_of_nodes",
            "additional_destratification_conductivity",
            "node_1_additional_loss_coefficient",
            "node_2_additional_loss_coefficient",
            "node_3_additional_loss_coefficient",
            "node_4_additional_loss_coefficient",
            "node_5_additional_loss_coefficient",
            "node_6_additional_loss_coefficient",
            "node_7_additional_loss_coefficient",
            "node_8_additional_loss_coefficient",
            "node_9_additional_loss_coefficient",
            "node_10_additional_loss_coefficient",
            "node_11_additional_loss_coefficient",
            "node_12_additional_loss_coefficient",
            "source_side_flow_control_mode",
            "indirect_alternate_setpoint_temperature_schedule_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "end_use_subcategory",
                "tank_shape",
                "heater_priority_control",
                "heater_1_setpoint_temperature_schedule_name",
                "heater_2_setpoint_temperature_schedule_name",
                "heater_fuel_type",
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
                "inlet_mode",
                "source_side_flow_control_mode",
                "indirect_alternate_setpoint_temperature_schedule_name"
            ]
        },
        "numerics": {
            "fields": [
                "tank_volume",
                "tank_height",
                "tank_perimeter",
                "maximum_temperature_limit",
                "heater_1_deadband_temperature_difference",
                "heater_1_capacity",
                "heater_1_height",
                "heater_2_deadband_temperature_difference",
                "heater_2_capacity",
                "heater_2_height",
                "heater_thermal_efficiency",
                "off_cycle_parasitic_fuel_consumption_rate",
                "off_cycle_parasitic_heat_fraction_to_tank",
                "off_cycle_parasitic_height",
                "on_cycle_parasitic_fuel_consumption_rate",
                "on_cycle_parasitic_heat_fraction_to_tank",
                "on_cycle_parasitic_height",
                "uniform_skin_loss_coefficient_per_unit_area_to_ambient_temperature",
                "skin_loss_fraction_to_zone",
                "off_cycle_flue_loss_coefficient_to_ambient_temperature",
                "off_cycle_flue_loss_fraction_to_zone",
                "peak_use_flow_rate",
                "use_side_effectiveness",
                "use_side_inlet_height",
                "use_side_outlet_height",
                "source_side_effectiveness",
                "source_side_inlet_height",
                "source_side_outlet_height",
                "use_side_design_flow_rate",
                "source_side_design_flow_rate",
                "indirect_water_heating_recovery_time",
                "number_of_nodes",
                "additional_destratification_conductivity",
                "node_1_additional_loss_coefficient",
                "node_2_additional_loss_coefficient",
                "node_3_additional_loss_coefficient",
                "node_4_additional_loss_coefficient",
                "node_5_additional_loss_coefficient",
                "node_6_additional_loss_coefficient",
                "node_7_additional_loss_coefficient",
                "node_8_additional_loss_coefficient",
                "node_9_additional_loss_coefficient",
                "node_10_additional_loss_coefficient",
                "node_11_additional_loss_coefficient",
                "node_12_additional_loss_coefficient"
            ]
        }
    },
    "type": "object",
    "memo": "Water heater with stratified, multi-node water tank. May be used to model a tankless water heater (small tank volume), a hot water storage tank (zero heater capacity), or a heat pump water heater (see WaterHeater:HeatPump:*.)"
}
```
