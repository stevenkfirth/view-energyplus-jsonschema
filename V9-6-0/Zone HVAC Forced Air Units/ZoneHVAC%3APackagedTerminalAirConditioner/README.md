```
{
    "ZoneHVAC:PackagedTerminalAirConditioner": {
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
                        "note": "Air inlet node for the PTAC must be a zone air exhaust Node."
                    },
                    "air_outlet_node_name": {
                        "type": "string",
                        "note": "Air outlet node for the PTAC must be a zone air inlet node."
                    },
                    "outdoor_air_mixer_object_type": {
                        "type": "string",
                        "enum": [
                            "OutdoorAir:Mixer"
                        ],
                        "note": "Currently only one OutdoorAir:Mixer object type is available. This field should be left blank if the PTAC is connected to central dedicated outdoor air through an AirTerminal:SingleDuct:Mixer object."
                    },
                    "outdoor_air_mixer_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "OutdoorAirMixers"
                        ],
                        "note": "If this field is blank, the OutdoorAir:Mixer is not used. This optional field specifies the name of the OutdoorAir:Mixer object. When used, this name needs to match name of the OutdoorAir:Mixer object. This field should be left blank if the PTAC is connected to central dedicated outdoor air through an AirTerminal:SingleDuct:Mixer object."
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
                        "note": "Must be less than or equal to fan size. Only used when supply air fan operating mode schedule values specify continuous fan (schedule values greater than 0 specify continuous fan operation). This air flow rate is used when no heating or cooling is required and the cooling or heating coil is off. If this field is left blank or zero, the supply air flow rate from the previous on cycle (either cooling or heating) is used.",
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
                        "note": "Must be less than or equal to supply air flow rate during cooling operation. This field is set to zero flow when the PTAC is connected to central dedicated outdoor air through air terminal single duct mixer object.",
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
                        "note": "Must be less than or equal to supply air flow rate during heating operation. This field is set to zero flow when the PTAC is connected to central dedicated outdoor air through air terminal single duct mixer object.",
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
                        "note": "Only used when supply air fan operating mode schedule values specify continuous fan (schedule values greater than 0 specify continuous fan operation). This air flow rate is used when no heating or cooling is required and the cooling or heating coil is off. If this field is left blank or zero, the outdoor air flow rate from the previous on cycle (either cooling or heating) is used. This field is set to zero flow when the PTAC is connected to central dedicated outdoor air through air terminal single duct mixer object.",
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
                        "note": "Fan:ConstantVolume only works when continuous fan operation is used the entire simulation (all supply air fan operating mode schedule values are greater than 0). If any fan operating mode schedule values are 0 a Fan:SystemModel or Fan:OnOff object must be used."
                    },
                    "supply_air_fan_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "FansCVandOnOff",
                            "FansSystemModel"
                        ],
                        "note": "Needs to match in the fan object."
                    },
                    "heating_coil_object_type": {
                        "type": "string",
                        "enum": [
                            "Coil:Heating:Electric",
                            "Coil:Heating:Fuel",
                            "Coil:Heating:Steam",
                            "Coil:Heating:Water"
                        ],
                        "note": "Select the type of heating coil."
                    },
                    "heating_coil_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "HeatingCoilName"
                        ],
                        "note": "Needs to match in the heating coil object."
                    },
                    "cooling_coil_object_type": {
                        "type": "string",
                        "enum": [
                            "Coil:Cooling:DX:SingleSpeed",
                            "Coil:Cooling:DX:VariableSpeed",
                            "CoilSystem:Cooling:DX:HeatExchangerAssisted"
                        ],
                        "note": "Select the type of Cooling Coil. Only works with Coil:Cooling:DX:SingleSpeed or CoilSystem:Cooling:DX:HeatExchangerAssisted or Coil:Cooling:DX:VariableSpeed."
                    },
                    "cooling_coil_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "CoolingCoilsDXSingleSpeed",
                            "CoolingCoilsDXVariableSpeed"
                        ],
                        "note": "Needs to match a DX cooling coil object."
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
                        "note": "Enter the name of a schedule that controls fan operation. Schedule Name values of 0 denote cycling fan operation (fan cycles with cooling or heating coil). Schedule Name values greater than 0 denote constant fan operation (fan runs continually regardless of coil operation)."
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
                    "cooling_coil_name"
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
            "note": "Unique name for this packaged terminal air conditioner object."
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
                "cooling_coil_object_type",
                "cooling_coil_name",
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
                    "minimum_supply_air_temperature_in_cooling_mode",
                    "maximum_supply_air_temperature_in_heating_mode"
                ]
            }
        },
        "type": "object",
        "memo": "Packaged terminal air conditioner (PTAC). Forced-convection heating-cooling unit with supply fan, direct expansion (DX) cooling coil, heating coil (gas, electric, hot water, or steam) and fixed-position outdoor air mixer.",
        "min_fields": 18.0
    }
}
```
