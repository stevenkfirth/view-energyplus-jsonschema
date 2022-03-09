```
{
    "ZoneHVAC:PackagedTerminalHeatPump": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "availability_schedule_name": {
                        "type": "string",
                        "note": "Availability schedule name for this system. Schedule value > 0 means the system is available. If this field is blank, the system is always available. Schedule values of 0 denote the unit is off.",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "air_inlet_node_name": {
                        "type": "string",
                        "note": "Air inlet node for the PTHP must be a zone air exhaust node."
                    },
                    "air_outlet_node_name": {
                        "type": "string",
                        "note": "Air outlet node for the PTHP must be a zone air inlet node."
                    },
                    "outdoor_air_mixer_object_type": {
                        "type": "string",
                        "enum": [
                            "OutdoorAir:Mixer"
                        ],
                        "note": "Currently only one OutdoorAir:Mixer object type is available. This field should be left blank if the PTHP is connected to central dedicated outdoor air through an AirTerminal:SingleDuct:Mixer object."
                    },
                    "outdoor_air_mixer_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "OutdoorAirMixers"
                        ],
                        "note": "If this field is blank, the OutdoorAir:Mixer is not used. This optional field specifies the name of the OutdoorAir:Mixer object. When used, this name needs to match name of the OutdoorAir:Mixer object. This field should be left blank if the PTHP is connected to central dedicated outdoor air through an AirTerminal:SingleDuct:Mixer object."
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
                        "note": "Must be less than or equal to supply air flow rate during cooling operation. This field is set to zero flow when the PTHP is connected to central dedicated outdoor air through air terminal single duct mixer object.",
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
                        "note": "Must be less than or equal to supply air flow rate during heating operation. This field is set to zero flow when the PTHP is connected to central dedicated outdoor air through air terminal single duct mixer object.",
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
                            "Fan:ConstantVolume",
                            "Fan:OnOff",
                            "Fan:SystemModel"
                        ],
                        "note": "Fan:ConstantVolume only works with fan operating mode is continuous."
                    },
                    "supply_air_fan_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "FansCVandOnOff",
                            "FansSystemModel"
                        ],
                        "note": "Needs to match a fan object."
                    },
                    "heating_coil_object_type": {
                        "type": "string",
                        "enum": [
                            "Coil:Heating:DX:SingleSpeed",
                            "Coil:Heating:DX:VariableSpeed"
                        ],
                        "note": "Only works with Coil:Heating:DX:SingleSpeed or Coil:Heating:DX:VariableSpeed."
                    },
                    "heating_coil_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "HeatingCoilsDXSingleSpeed",
                            "HeatingCoilsDXVariableSpeed"
                        ],
                        "note": "Needs to match in the DX Heating Coil object."
                    },
                    "heating_convergence_tolerance": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "default": 0.001,
                        "units": "dimensionless",
                        "note": "Defines Heating convergence tolerance as a fraction of Heating load to be met."
                    },
                    "cooling_coil_object_type": {
                        "type": "string",
                        "enum": [
                            "Coil:Cooling:DX:SingleSpeed",
                            "Coil:Cooling:DX:VariableSpeed",
                            "CoilSystem:Cooling:DX:HeatExchangerAssisted"
                        ],
                        "note": "Only works with Coil:Cooling:DX:SingleSpeed or CoilSystem:Cooling:DX:HeatExchangerAssisted or Coil:Cooling:DX:VariableSpeed."
                    },
                    "cooling_coil_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "CoolingCoilsDXSingleSpeed",
                            "CoolingCoilsDXVariableSpeed"
                        ],
                        "note": "Needs to match in the DX Cooling Coil object."
                    },
                    "cooling_convergence_tolerance": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "default": 0.001,
                        "units": "dimensionless",
                        "note": "Defines Cooling convergence tolerance as a fraction of the Cooling load to be met."
                    },
                    "supplemental_heating_coil_object_type": {
                        "type": "string",
                        "enum": [
                            "Coil:Heating:Electric",
                            "Coil:Heating:Fuel",
                            "Coil:Heating:Steam",
                            "Coil:Heating:Water"
                        ],
                        "note": "works with gas, electric, hot water and steam heating coil."
                    },
                    "supplemental_heating_coil_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "HeatingCoilName"
                        ],
                        "note": "Needs to match in the supplemental heating coil object."
                    },
                    "maximum_supply_air_temperature_from_supplemental_heater": {
                        "units": "C",
                        "note": "Supply air temperature from the supplemental heater will not exceed this value.",
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
                    "maximum_outdoor_dry_bulb_temperature_for_supplemental_heater_operation": {
                        "type": "number",
                        "maximum": 21.0,
                        "default": 21.0,
                        "units": "C",
                        "note": "Supplemental heater will not operate when outdoor temperature exceeds this value."
                    },
                    "fan_placement": {
                        "type": "string",
                        "enum": [
                            "",
                            "BlowThrough",
                            "DrawThrough"
                        ],
                        "default": "DrawThrough",
                        "note": "Select fan placement as either blow through or draw through."
                    },
                    "supply_air_fan_operating_mode_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "Enter the name of a schedule that controls fan operation. Schedule values of 0 denote cycling fan operation (fan cycles with cooling or heating coil). Schedule Name values greater than 0 denote constant fan operation (fan runs continually regardless of coil operation). The fan operating mode defaults to cycling fan operation if this field is left blank."
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
                    "capacity_control_method": {
                        "type": "string",
                        "enum": [
                            "",
                            "None",
                            "SingleZoneVAV"
                        ],
                        "default": "None"
                    },
                    "minimum_supply_air_temperature_in_cooling_mode": {
                        "note": "For Capacity Control Method = SingleZoneVAV, enter the minimum air temperature limit for reduced fan speed.",
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
                        "note": "For Capacity Control Method = SingleZoneVAV, enter the maximum air temperature limit for reduced fan speed.",
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
                    "supplemental_heating_coil_name",
                    "maximum_supply_air_temperature_from_supplemental_heater"
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
            ],
            "note": "Unique name for this packaged terminal heat pump object."
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
                "heating_convergence_tolerance": {
                    "field_name": "Heating Convergence Tolerance",
                    "field_type": "n"
                },
                "cooling_coil_object_type": {
                    "field_name": "Cooling Coil Object Type",
                    "field_type": "a"
                },
                "cooling_coil_name": {
                    "field_name": "Cooling Coil Name",
                    "field_type": "a"
                },
                "cooling_convergence_tolerance": {
                    "field_name": "Cooling Convergence Tolerance",
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
                "design_specification_zonehvac_sizing_object_name": {
                    "field_name": "Design Specification ZoneHVAC Sizing Object Name",
                    "field_type": "a"
                },
                "capacity_control_method": {
                    "field_name": "Capacity Control Method",
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
                "heating_convergence_tolerance",
                "cooling_coil_object_type",
                "cooling_coil_name",
                "cooling_convergence_tolerance",
                "supplemental_heating_coil_object_type",
                "supplemental_heating_coil_name",
                "maximum_supply_air_temperature_from_supplemental_heater",
                "maximum_outdoor_dry_bulb_temperature_for_supplemental_heater_operation",
                "fan_placement",
                "supply_air_fan_operating_mode_schedule_name",
                "availability_manager_list_name",
                "design_specification_zonehvac_sizing_object_name",
                "capacity_control_method",
                "minimum_supply_air_temperature_in_cooling_mode",
                "maximum_supply_air_temperature_in_heating_mode"
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
                    "fan_placement",
                    "supply_air_fan_operating_mode_schedule_name",
                    "availability_manager_list_name",
                    "design_specification_zonehvac_sizing_object_name",
                    "capacity_control_method"
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
                    "heating_convergence_tolerance",
                    "cooling_convergence_tolerance",
                    "maximum_supply_air_temperature_from_supplemental_heater",
                    "maximum_outdoor_dry_bulb_temperature_for_supplemental_heater_operation",
                    "minimum_supply_air_temperature_in_cooling_mode",
                    "maximum_supply_air_temperature_in_heating_mode"
                ]
            }
        },
        "type": "object",
        "memo": "Packaged terminal heat pump (PTHP). Forced-convection heating-cooling unit with supply fan, direct expansion (DX) cooling coil, DX heating coil (air-to-air heat pump), supplemental heating coil (gas, electric, hot water, or steam), and fixed-position outdoor air mixer.",
        "min_fields": 26.0
    }
}
```
