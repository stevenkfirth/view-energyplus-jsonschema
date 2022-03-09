```
{
    "ZoneHVAC:FourPipeFanCoil": {
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
                    "capacity_control_method": {
                        "type": "string",
                        "enum": [
                            "ASHRAE90VariableFan",
                            "ConstantFanVariableFlow",
                            "CyclingFan",
                            "MultiSpeedFan",
                            "VariableFanConstantFlow",
                            "VariableFanVariableFlow"
                        ]
                    },
                    "maximum_supply_air_flow_rate": {
                        "units": "m3/s",
                        "anyOf": [
                            {
                                "type": "number"
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "low_speed_supply_air_flow_ratio": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "default": 0.33
                    },
                    "medium_speed_supply_air_flow_ratio": {
                        "type": "number",
                        "note": "Medium Speed Supply Air Flow Ratio should be greater than Low Speed Supply Air Flow Ratio",
                        "exclusiveMinimum": 0.0,
                        "default": 0.66
                    },
                    "maximum_outdoor_air_flow_rate": {
                        "units": "m3/s",
                        "anyOf": [
                            {
                                "type": "number"
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "outdoor_air_schedule_name": {
                        "type": "string",
                        "note": "Value of schedule multiplies maximum outdoor air flow rate",
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
                        "note": "Currently only one type OutdoorAir:Mixer object is available. This field should be left blank if the FanCoil is connected to central dedicated outdoor air through an AirTerminal:SingleDuct:Mixer object."
                    },
                    "outdoor_air_mixer_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "OutdoorAirMixers"
                        ],
                        "note": "If this field is blank, the OutdoorAir:Mixer is not used. This optional field specifies the name of the OutdoorAir:Mixer object. When used, this name needs to match name of the OutdoorAir:Mixer object. This field should be left blank if the FanCoil is connected to central dedicated outdoor air through an AirTerminal:SingleDuct:Mixer object."
                    },
                    "supply_air_fan_object_type": {
                        "type": "string",
                        "enum": [
                            "Fan:ConstantVolume",
                            "Fan:OnOff",
                            "Fan:SystemModel",
                            "Fan:VariableVolume"
                        ],
                        "note": "Fan type must be according to capacity control method (see I/O) For ConstantFanVariableFlow a Fan:OnOff or Fan:ConstantVolume is valid. For CyclingFan a Fan:OnOff is valid. For VariableFanVariableFlow or VariableFanConstantFlow a Fan:VariableVolume is valid. For ASHRAE90.1 a Fan:OnOff or Fan:VariableVolume is valid. Fan:SystemModel is valid for all capacity control methods. The fan's inlet node should be the same as the outdoor air mixer's mixed air node."
                    },
                    "supply_air_fan_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "FansCVandOnOffandVAV",
                            "FansSystemModel"
                        ]
                    },
                    "cooling_coil_object_type": {
                        "type": "string",
                        "enum": [
                            "Coil:Cooling:Water",
                            "Coil:Cooling:Water:DetailedGeometry",
                            "CoilSystem:Cooling:Water:HeatExchangerAssisted"
                        ]
                    },
                    "cooling_coil_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "CoolingCoilsWater"
                        ]
                    },
                    "maximum_cold_water_flow_rate": {
                        "units": "m3/s",
                        "ip-units": "gal/min",
                        "anyOf": [
                            {
                                "type": "number"
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "minimum_cold_water_flow_rate": {
                        "type": "number",
                        "default": 0.0,
                        "units": "m3/s",
                        "ip-units": "gal/min"
                    },
                    "cooling_convergence_tolerance": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "default": 0.001
                    },
                    "heating_coil_object_type": {
                        "type": "string",
                        "enum": [
                            "Coil:Heating:Electric",
                            "Coil:Heating:Water"
                        ]
                    },
                    "heating_coil_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "HeatingCoilsElectric",
                            "HeatingCoilsWater"
                        ]
                    },
                    "maximum_hot_water_flow_rate": {
                        "units": "m3/s",
                        "ip-units": "gal/min",
                        "anyOf": [
                            {
                                "type": "number"
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "minimum_hot_water_flow_rate": {
                        "type": "number",
                        "default": 0.0,
                        "units": "m3/s",
                        "ip-units": "gal/min"
                    },
                    "heating_convergence_tolerance": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "default": 0.001
                    },
                    "availability_manager_list_name": {
                        "type": "string",
                        "note": "Enter the name of an AvailabilityManagerAssignmentList object.",
                        "data_type": "object_list",
                        "object_list": [
                            "SystemAvailabilityManagerLists"
                        ]
                    },
                    "design_specification_zonehvac_sizing_object_name": {
                        "type": "string",
                        "note": "Enter the name of a DesignSpecificationZoneHVACSizing object.",
                        "data_type": "object_list",
                        "object_list": [
                            "DesignSpecificationZoneHVACSizingName"
                        ]
                    },
                    "supply_air_fan_operating_mode_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "Enter the name of a schedule that controls fan operation. Schedule Name values of 0 denote cycling fan operation (fan cycles with cooling coil). Schedule values greater than 0 denote constant fan operation (fan runs continually regardless of coil operation). The fan operating mode defaults to cycling fan operation if this field is left blank. This input field is currently used with MultiStageFan capacity control method"
                    },
                    "minimum_supply_air_temperature_in_cooling_mode": {
                        "note": "For Capacity Control Method = ASHRAE90VariableFan, enter the minimum air temperature in cooling mode. Leave this field blank or enter 0 to control to the zone load per ASHRAE 90.1. In this case, a zone sizing simulation is required.",
                        "units": "C",
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
                    "maximum_supply_air_temperature_in_heating_mode": {
                        "note": "For Capacity Control Method = ASHRAE90VariableFan, enter the maximum air temperature in heating mode. Leave this field blank or enter 0 to control to the zone load per ASHRAE 90.1. In this case, a zone sizing simulation is required.",
                        "units": "C",
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
                    }
                },
                "required": [
                    "capacity_control_method",
                    "maximum_supply_air_flow_rate",
                    "maximum_outdoor_air_flow_rate",
                    "air_inlet_node_name",
                    "air_outlet_node_name",
                    "supply_air_fan_object_type",
                    "supply_air_fan_name",
                    "cooling_coil_object_type",
                    "cooling_coil_name",
                    "maximum_cold_water_flow_rate",
                    "heating_coil_object_type",
                    "heating_coil_name",
                    "maximum_hot_water_flow_rate"
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
                "capacity_control_method": {
                    "field_name": "Capacity Control Method",
                    "field_type": "a"
                },
                "maximum_supply_air_flow_rate": {
                    "field_name": "Maximum Supply Air Flow Rate",
                    "field_type": "n"
                },
                "low_speed_supply_air_flow_ratio": {
                    "field_name": "Low Speed Supply Air Flow Ratio",
                    "field_type": "n"
                },
                "medium_speed_supply_air_flow_ratio": {
                    "field_name": "Medium Speed Supply Air Flow Ratio",
                    "field_type": "n"
                },
                "maximum_outdoor_air_flow_rate": {
                    "field_name": "Maximum Outdoor Air Flow Rate",
                    "field_type": "n"
                },
                "outdoor_air_schedule_name": {
                    "field_name": "Outdoor Air Schedule Name",
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
                "supply_air_fan_object_type": {
                    "field_name": "Supply Air Fan Object Type",
                    "field_type": "a"
                },
                "supply_air_fan_name": {
                    "field_name": "Supply Air Fan Name",
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
                "maximum_cold_water_flow_rate": {
                    "field_name": "Maximum Cold Water Flow Rate",
                    "field_type": "n"
                },
                "minimum_cold_water_flow_rate": {
                    "field_name": "Minimum Cold Water Flow Rate",
                    "field_type": "n"
                },
                "cooling_convergence_tolerance": {
                    "field_name": "Cooling Convergence Tolerance",
                    "field_type": "n"
                },
                "heating_coil_object_type": {
                    "field_name": "Heating Coil Object Type",
                    "field_type": "a"
                },
                "heating_coil_name": {
                    "field_name": "Heating Coil Name",
                    "field_type": "a"
                },
                "maximum_hot_water_flow_rate": {
                    "field_name": "Maximum Hot Water Flow Rate",
                    "field_type": "n"
                },
                "minimum_hot_water_flow_rate": {
                    "field_name": "Minimum Hot Water Flow Rate",
                    "field_type": "n"
                },
                "heating_convergence_tolerance": {
                    "field_name": "Heating Convergence Tolerance",
                    "field_type": "n"
                },
                "availability_manager_list_name": {
                    "field_name": "Availability Manager List Name",
                    "field_type": "a"
                },
                "design_specification_zonehvac_sizing_object_name": {
                    "field_name": "Design Specification ZoneHVAC Sizing Object Name",
                    "field_type": "a"
                },
                "supply_air_fan_operating_mode_schedule_name": {
                    "field_name": "Supply Air Fan Operating Mode Schedule Name",
                    "field_type": "a"
                },
                "minimum_supply_air_temperature_in_cooling_mode": {
                    "field_name": "Minimum Supply Air Temperature in Cooling Mode",
                    "field_type": "n"
                },
                "maximum_supply_air_temperature_in_heating_mode": {
                    "field_name": "Maximum Supply Air Temperature in Heating Mode",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "availability_schedule_name",
                "capacity_control_method",
                "maximum_supply_air_flow_rate",
                "low_speed_supply_air_flow_ratio",
                "medium_speed_supply_air_flow_ratio",
                "maximum_outdoor_air_flow_rate",
                "outdoor_air_schedule_name",
                "air_inlet_node_name",
                "air_outlet_node_name",
                "outdoor_air_mixer_object_type",
                "outdoor_air_mixer_name",
                "supply_air_fan_object_type",
                "supply_air_fan_name",
                "cooling_coil_object_type",
                "cooling_coil_name",
                "maximum_cold_water_flow_rate",
                "minimum_cold_water_flow_rate",
                "cooling_convergence_tolerance",
                "heating_coil_object_type",
                "heating_coil_name",
                "maximum_hot_water_flow_rate",
                "minimum_hot_water_flow_rate",
                "heating_convergence_tolerance",
                "availability_manager_list_name",
                "design_specification_zonehvac_sizing_object_name",
                "supply_air_fan_operating_mode_schedule_name",
                "minimum_supply_air_temperature_in_cooling_mode",
                "maximum_supply_air_temperature_in_heating_mode"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "capacity_control_method",
                    "outdoor_air_schedule_name",
                    "air_inlet_node_name",
                    "air_outlet_node_name",
                    "outdoor_air_mixer_object_type",
                    "outdoor_air_mixer_name",
                    "supply_air_fan_object_type",
                    "supply_air_fan_name",
                    "cooling_coil_object_type",
                    "cooling_coil_name",
                    "heating_coil_object_type",
                    "heating_coil_name",
                    "availability_manager_list_name",
                    "design_specification_zonehvac_sizing_object_name",
                    "supply_air_fan_operating_mode_schedule_name"
                ]
            },
            "numerics": {
                "fields": [
                    "maximum_supply_air_flow_rate",
                    "low_speed_supply_air_flow_ratio",
                    "medium_speed_supply_air_flow_ratio",
                    "maximum_outdoor_air_flow_rate",
                    "maximum_cold_water_flow_rate",
                    "minimum_cold_water_flow_rate",
                    "cooling_convergence_tolerance",
                    "maximum_hot_water_flow_rate",
                    "minimum_hot_water_flow_rate",
                    "heating_convergence_tolerance",
                    "minimum_supply_air_temperature_in_cooling_mode",
                    "maximum_supply_air_temperature_in_heating_mode"
                ]
            }
        },
        "type": "object",
        "memo": "Four pipe fan coil system. Forced-convection hydronic heating-cooling unit with supply fan, hot water heating coil, chilled water cooling coil, and fixed-position outdoor air mixer.",
        "min_fields": 24.0
    }
}
```
