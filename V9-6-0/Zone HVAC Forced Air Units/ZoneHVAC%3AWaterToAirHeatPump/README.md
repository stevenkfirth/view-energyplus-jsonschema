```
{
    "ZoneHVAC:WaterToAirHeatPump": {
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
                    "air_inlet_node_name": {
                        "type": "string"
                    },
                    "air_outlet_node_name": {
                        "type": "string"
                    },
                    "outdoor_air_mixer_object_type": {
                        "type": "string",
                        "enum": [
                            "OutdoorAir:Mixer"
                        ],
                        "note": "Currently only one OutdoorAir:Mixer object type is available. This field should be left blank if the WSHP is connected to central dedicated outdoor air through an AirTerminal:SingleDuct:Mixer object."
                    },
                    "outdoor_air_mixer_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "OutdoorAirMixers"
                        ],
                        "note": "If this field is blank, the OutdoorAir:Mixer is not used. This optional field specifies the name of the OutdoorAir:Mixer object. When used, this name needs to match name of the OutdoorAir:Mixer object. This field should be left blank if the WSHP is connected to central dedicated outdoor air through an AirTerminal:SingleDuct:Mixer object."
                    },
                    "cooling_supply_air_flow_rate": {
                        "units": "m3/s",
                        "note": "Must be less than or equal to fan size.",
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
                    "heating_supply_air_flow_rate": {
                        "units": "m3/s",
                        "note": "Must be less than or equal to fan size.",
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
                    "no_load_supply_air_flow_rate": {
                        "units": "m3/s",
                        "note": "Must be less than or equal to fan size. Only used when heat pump fan operating mode is continuous. This air flow rate is used when no heating or cooling is required and the DX coil compressor is off. If this field is left blank or zero, the supply air flow rate from the previous on cycle (either cooling or heating) is used.",
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
                    "cooling_outdoor_air_flow_rate": {
                        "units": "m3/s",
                        "note": "Must be less than or equal to supply air flow rate during cooling operation. This field is set to zero flow when the WSHP is connected to central dedicated outdoor air through air terminal single duct mixer object.",
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
                    "heating_outdoor_air_flow_rate": {
                        "units": "m3/s",
                        "note": "Must be less than or equal to supply air flow rate during heating operation. This field is set to zero flow when the WSHP is connected to central dedicated outdoor air through air terminal single duct mixer object.",
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
                    "no_load_outdoor_air_flow_rate": {
                        "units": "m3/s",
                        "note": "Only used when heat pump Fan operating mode is continuous. This air flow rate is used when no heating or cooling is required and the DX coil compressor is off. If this field is left blank or zero, the outdoor air flow rate from the previous on cycle (either cooling or heating) is used. This field is set to zero flow when the PTHP is connected to central dedicated outdoor air through air terminal single duct mixer object.",
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
                    "supply_air_fan_object_type": {
                        "type": "string",
                        "enum": [
                            "Fan:OnOff",
                            "Fan:SystemModel"
                        ]
                    },
                    "supply_air_fan_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "FansOnOff",
                            "FansSystemModel"
                        ],
                        "note": "Needs to match Fan:SystemModel or Fan:OnOff object"
                    },
                    "heating_coil_object_type": {
                        "type": "string",
                        "enum": [
                            "Coil:Heating:WaterToAirHeatPump:EquationFit",
                            "Coil:Heating:WaterToAirHeatPump:VariableSpeedEquationFit"
                        ]
                    },
                    "heating_coil_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "HeatingCoilsWaterToAirHP",
                            "HeatingCoilsWaterToAirVSHP"
                        ],
                        "note": "Needs to match in the water-to-air heat pump heating coil object"
                    },
                    "cooling_coil_object_type": {
                        "type": "string",
                        "enum": [
                            "Coil:Cooling:WaterToAirHeatPump:EquationFit",
                            "Coil:Cooling:WaterToAirHeatPump:VariableSpeedEquationFit"
                        ]
                    },
                    "cooling_coil_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "CoolingCoilsWaterToAirHP",
                            "CoolingCoilsWaterToAirVSHP"
                        ],
                        "note": "Needs to match in the water-to-air heat pump cooling coil object"
                    },
                    "maximum_cycling_rate": {
                        "type": "number",
                        "units": "cycles/hr",
                        "minimum": 0.0,
                        "maximum": 5.0,
                        "default": 2.5,
                        "note": "The maximum on-off cycling rate for the compressor Suggested value is 2.5 for a typical heat pump"
                    },
                    "heat_pump_time_constant": {
                        "type": "number",
                        "units": "s",
                        "minimum": 0.0,
                        "maximum": 500.0,
                        "default": 60.0,
                        "note": "Time constant for the cooling coil's capacity to reach steady state after startup Suggested value is 60 for a typical heat pump"
                    },
                    "fraction_of_on_cycle_power_use": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 0.05,
                        "default": 0.01,
                        "note": "The fraction of on-cycle power use to adjust the part load fraction based on the off-cycle power consumption due to crankcase heaters, controls, fans, and etc. Suggested value is 0.01 for a typical heat pump"
                    },
                    "heat_pump_fan_delay_time": {
                        "type": "number",
                        "units": "s",
                        "minimum": 0.0,
                        "default": 60.0,
                        "note": "Programmed time delay for heat pump fan to shut off after compressor cycle off. Only required when fan operating mode is cycling Enter 0 when fan operating mode is continuous"
                    },
                    "supplemental_heating_coil_object_type": {
                        "type": "string",
                        "enum": [
                            "Coil:Heating:Electric",
                            "Coil:Heating:Fuel",
                            "Coil:Heating:Steam",
                            "Coil:Heating:Water"
                        ],
                        "note": "works with gas, electric, hot water and steam heating coils"
                    },
                    "supplemental_heating_coil_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "HeatingCoilName"
                        ],
                        "note": "Needs to match in the supplemental heating coil object"
                    },
                    "maximum_supply_air_temperature_from_supplemental_heater": {
                        "units": "C",
                        "default": "Autosize",
                        "note": "Supply air temperature from the supplemental heater will not exceed this value.",
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
                    "maximum_outdoor_dry_bulb_temperature_for_supplemental_heater_operation": {
                        "type": "number",
                        "maximum": 21.0,
                        "default": 21.0,
                        "units": "C"
                    },
                    "outdoor_dry_bulb_temperature_sensor_node_name": {
                        "type": "string"
                    },
                    "fan_placement": {
                        "type": "string",
                        "enum": [
                            "",
                            "BlowThrough",
                            "DrawThrough"
                        ],
                        "default": "BlowThrough"
                    },
                    "supply_air_fan_operating_mode_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "Enter the name of a schedule that controls fan operation. Schedule values of 0 denote cycling fan operation (fan cycles with cooling or heating coil). Schedule values greater than 0 denote constant fan operation (fan runs continually regardless of coil operation). The fan operating mode defaults to cycling fan operation if this field is left blank."
                    },
                    "availability_manager_list_name": {
                        "type": "string",
                        "note": "Enter the name of an AvailabilityManagerAssignmentList object.",
                        "data_type": "object_list",
                        "object_list": [
                            "SystemAvailabilityManagerLists"
                        ]
                    },
                    "heat_pump_coil_water_flow_mode": {
                        "type": "string",
                        "enum": [
                            "",
                            "Constant",
                            "ConstantOnDemand",
                            "Cycling"
                        ],
                        "default": "Cycling",
                        "note": "used only when the heat pump coils are of the type WaterToAirHeatPump:EquationFit Constant results in 100% water flow regardless of compressor PLR Cycling results in water flow that matches compressor PLR ConstantOnDemand results in 100% water flow whenever the coil is on, but is 0% whenever the coil has no load"
                    },
                    "design_specification_zonehvac_sizing_object_name": {
                        "type": "string",
                        "note": "Enter the name of a DesignSpecificationZoneHVACSizing object.",
                        "data_type": "object_list",
                        "object_list": [
                            "DesignSpecificationZoneHVACSizingName"
                        ]
                    }
                },
                "required": [
                    "air_inlet_node_name",
                    "air_outlet_node_name",
                    "cooling_supply_air_flow_rate",
                    "heating_supply_air_flow_rate",
                    "cooling_outdoor_air_flow_rate",
                    "heating_outdoor_air_flow_rate",
                    "supply_air_fan_object_type",
                    "supply_air_fan_name",
                    "heating_coil_object_type",
                    "heating_coil_name",
                    "cooling_coil_object_type",
                    "cooling_coil_name",
                    "supplemental_heating_coil_object_type",
                    "supplemental_heating_coil_name"
                ]
            }
        },
        "group": "Zone HVAC Forced Air Units",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "DOAToZonalUnit",
                "ZoneEquipmentNames"
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
                "outdoor_air_mixer_object_type": {
                    "field_name": "Outdoor Air Mixer Object Type",
                    "field_type": "a"
                },
                "outdoor_air_mixer_name": {
                    "field_name": "Outdoor Air Mixer Name",
                    "field_type": "a"
                },
                "cooling_supply_air_flow_rate": {
                    "field_name": "Cooling Supply Air Flow Rate",
                    "field_type": "n"
                },
                "heating_supply_air_flow_rate": {
                    "field_name": "Heating Supply Air Flow Rate",
                    "field_type": "n"
                },
                "no_load_supply_air_flow_rate": {
                    "field_name": "No Load Supply Air Flow Rate",
                    "field_type": "n"
                },
                "cooling_outdoor_air_flow_rate": {
                    "field_name": "Cooling Outdoor Air Flow Rate",
                    "field_type": "n"
                },
                "heating_outdoor_air_flow_rate": {
                    "field_name": "Heating Outdoor Air Flow Rate",
                    "field_type": "n"
                },
                "no_load_outdoor_air_flow_rate": {
                    "field_name": "No Load Outdoor Air Flow Rate",
                    "field_type": "n"
                },
                "supply_air_fan_object_type": {
                    "field_name": "Supply Air Fan Object Type",
                    "field_type": "a"
                },
                "supply_air_fan_name": {
                    "field_name": "Supply Air Fan Name",
                    "field_type": "a"
                },
                "heating_coil_object_type": {
                    "field_name": "Heating Coil Object Type",
                    "field_type": "a"
                },
                "heating_coil_name": {
                    "field_name": "Heating Coil Name",
                    "field_type": "a"
                },
                "cooling_coil_object_type": {
                    "field_name": "Cooling Coil Object Type",
                    "field_type": "a"
                },
                "cooling_coil_name": {
                    "field_name": "Cooling Coil Name",
                    "field_type": "a"
                },
                "maximum_cycling_rate": {
                    "field_name": "Maximum Cycling Rate",
                    "field_type": "n"
                },
                "heat_pump_time_constant": {
                    "field_name": "Heat Pump Time Constant",
                    "field_type": "n"
                },
                "fraction_of_on_cycle_power_use": {
                    "field_name": "Fraction of On-Cycle Power Use",
                    "field_type": "n"
                },
                "heat_pump_fan_delay_time": {
                    "field_name": "Heat Pump Fan Delay Time",
                    "field_type": "n"
                },
                "supplemental_heating_coil_object_type": {
                    "field_name": "Supplemental Heating Coil Object Type",
                    "field_type": "a"
                },
                "supplemental_heating_coil_name": {
                    "field_name": "Supplemental Heating Coil Name",
                    "field_type": "a"
                },
                "maximum_supply_air_temperature_from_supplemental_heater": {
                    "field_name": "Maximum Supply Air Temperature from Supplemental Heater",
                    "field_type": "n"
                },
                "maximum_outdoor_dry_bulb_temperature_for_supplemental_heater_operation": {
                    "field_name": "Maximum Outdoor Dry-Bulb Temperature for Supplemental Heater Operation",
                    "field_type": "n"
                },
                "outdoor_dry_bulb_temperature_sensor_node_name": {
                    "field_name": "Outdoor Dry-Bulb Temperature Sensor Node Name",
                    "field_type": "a"
                },
                "fan_placement": {
                    "field_name": "Fan Placement",
                    "field_type": "a"
                },
                "supply_air_fan_operating_mode_schedule_name": {
                    "field_name": "Supply Air Fan Operating Mode Schedule Name",
                    "field_type": "a"
                },
                "availability_manager_list_name": {
                    "field_name": "Availability Manager List Name",
                    "field_type": "a"
                },
                "heat_pump_coil_water_flow_mode": {
                    "field_name": "Heat Pump Coil Water Flow Mode",
                    "field_type": "a"
                },
                "design_specification_zonehvac_sizing_object_name": {
                    "field_name": "Design Specification ZoneHVAC Sizing Object Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "availability_schedule_name",
                "air_inlet_node_name",
                "air_outlet_node_name",
                "outdoor_air_mixer_object_type",
                "outdoor_air_mixer_name",
                "cooling_supply_air_flow_rate",
                "heating_supply_air_flow_rate",
                "no_load_supply_air_flow_rate",
                "cooling_outdoor_air_flow_rate",
                "heating_outdoor_air_flow_rate",
                "no_load_outdoor_air_flow_rate",
                "supply_air_fan_object_type",
                "supply_air_fan_name",
                "heating_coil_object_type",
                "heating_coil_name",
                "cooling_coil_object_type",
                "cooling_coil_name",
                "maximum_cycling_rate",
                "heat_pump_time_constant",
                "fraction_of_on_cycle_power_use",
                "heat_pump_fan_delay_time",
                "supplemental_heating_coil_object_type",
                "supplemental_heating_coil_name",
                "maximum_supply_air_temperature_from_supplemental_heater",
                "maximum_outdoor_dry_bulb_temperature_for_supplemental_heater_operation",
                "outdoor_dry_bulb_temperature_sensor_node_name",
                "fan_placement",
                "supply_air_fan_operating_mode_schedule_name",
                "availability_manager_list_name",
                "heat_pump_coil_water_flow_mode",
                "design_specification_zonehvac_sizing_object_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "air_inlet_node_name",
                    "air_outlet_node_name",
                    "outdoor_air_mixer_object_type",
                    "outdoor_air_mixer_name",
                    "supply_air_fan_object_type",
                    "supply_air_fan_name",
                    "heating_coil_object_type",
                    "heating_coil_name",
                    "cooling_coil_object_type",
                    "cooling_coil_name",
                    "supplemental_heating_coil_object_type",
                    "supplemental_heating_coil_name",
                    "outdoor_dry_bulb_temperature_sensor_node_name",
                    "fan_placement",
                    "supply_air_fan_operating_mode_schedule_name",
                    "availability_manager_list_name",
                    "heat_pump_coil_water_flow_mode",
                    "design_specification_zonehvac_sizing_object_name"
                ]
            },
            "numerics": {
                "fields": [
                    "cooling_supply_air_flow_rate",
                    "heating_supply_air_flow_rate",
                    "no_load_supply_air_flow_rate",
                    "cooling_outdoor_air_flow_rate",
                    "heating_outdoor_air_flow_rate",
                    "no_load_outdoor_air_flow_rate",
                    "maximum_cycling_rate",
                    "heat_pump_time_constant",
                    "fraction_of_on_cycle_power_use",
                    "heat_pump_fan_delay_time",
                    "maximum_supply_air_temperature_from_supplemental_heater",
                    "maximum_outdoor_dry_bulb_temperature_for_supplemental_heater_operation"
                ]
            }
        },
        "type": "object",
        "memo": "Water-to-air heat pump. Forced-convection heating-cooling unit with supply fan, water-to-air cooling and heating coils, supplemental heating coil (gas, electric, hot water, or steam), and fixed-position outdoor air mixer.",
        "min_fields": 25.0
    }
}
```
