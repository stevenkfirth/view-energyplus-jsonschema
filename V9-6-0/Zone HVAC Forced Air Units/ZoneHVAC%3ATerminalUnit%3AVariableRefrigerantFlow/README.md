```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "terminal_unit_availability_schedule": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "The unit is available the entire simulation if this field is left blank Schedule values of 0 denote the unit is off."
                },
                "terminal_unit_air_inlet_node_name": {
                    "type": "string",
                    "note": "the inlet node to the terminal unit"
                },
                "terminal_unit_air_outlet_node_name": {
                    "type": "string",
                    "note": "the outlet node of the terminal unit"
                },
                "cooling_supply_air_flow_rate": {
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
                "no_cooling_supply_air_flow_rate": {
                    "units": "m3/s",
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
                "heating_supply_air_flow_rate": {
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
                "no_heating_supply_air_flow_rate": {
                    "units": "m3/s",
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
                    "note": "This field is used only when an oudoor air mixer is included. This field is set to zero flow when the VRF terminal unit is connected to central dedicated outdoor air through air terminal single duct mixer object. When this VRF terminal is used as air loop equipment the autosized flow rate will be set to 0 when an outdoor air system is connected to this air loop, otherwise the outdoor air flow rate will equal the maximum outdoor air flow rate.",
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
                    "note": "This field is used only when an oudoor air mixer is included. This field is set to zero flow when the VRF terminal unit is connected to central dedicated outdoor air through air terminal single duct mixer object. When this VRF terminal is used as air loop equipment the autosized flow rate will be set to 0 when an outdoor air system is connected to this air loop, otherwise the outdoor air flow rate will equal the maximum outdoor air flow rate.",
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
                    "note": "This field is used only when an oudoor air mixer is included. This field is set to zero flow when the VRF terminal unit is connected to central dedicated outdoor air through air terminal single duct mixer object. When this VRF terminal is used as air loop equipment the autosized flow rate will be set to 0 when an outdoor air system is connected to this air loop, otherwise the outdoor air flow rate will equal the maximum outdoor air flow rate.",
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
                "supply_air_fan_operating_mode_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "Required for zone equipment. Leave blank if terminal unit is used in AirLoopHVAC:OutdoorAirSystem:EquipmentList. Also leave blank if terminal unit is used on main AirloopHVAC branch and terminal unit has no fan."
                },
                "supply_air_fan_placement": {
                    "type": "string",
                    "enum": [
                        "",
                        "BlowThrough",
                        "DrawThrough"
                    ],
                    "default": "BlowThrough",
                    "note": "Select fan placement as either blow through or draw through. Required for zone equipment. This field is ignored if the VRF terminal unit is used in AirLoopHVAC:OutdoorAirSystem:EquipmentList. This field is also ignored if VRF terminal unit is used on main AirloopHVAC branch and terminal unit has no fan."
                },
                "supply_air_fan_object_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "Fan:ConstantVolume",
                        "Fan:OnOff",
                        "Fan:SystemModel",
                        "Fan:VariableVolume"
                    ],
                    "default": "Fan:ConstantVolume",
                    "note": "Supply Air Fan Object Type must be Fan:SystemModel, Fan:OnOff, or Fan:ConstantVolume if AirConditioner:VariableRefrigerantFlow is used to model VRF outdoor unit Supply Air Fan Object Type must be Fan:SystemModel or Fan:VariableVolume if AirConditioner:VariableRefrigerantFlow:FluidTemperatureControl or AirConditioner:VariableRefrigerantFlow:FluidTemperatureControl:HR is used to model VRF outdoor unit Required for zone equipment. Leave blank if terminal unit is used in AirLoopHVAC:OutdoorAirSystem:EquipmentList. Also leave blank if terminal unit is used on main AirloopHVAC branch and terminal unit has no fan."
                },
                "supply_air_fan_object_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "FansCVandOnOffandVAV",
                        "FansSystemModel"
                    ]
                },
                "outside_air_mixer_object_type": {
                    "type": "string",
                    "enum": [
                        "OutdoorAir:Mixer"
                    ],
                    "note": "Currently only one type OutdoorAir:Mixer object is available. If this field is blank, and outside air mixer is not used. This field should be left blank if the VRF terminal unit is connected to central dedicated outdoor air through an AirTerminal:SingleDuct:Mixer object. This field may also be left blank when the VRF terminal is used in the air loop or outdoor air system."
                },
                "outside_air_mixer_object_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "OutdoorAirMixers"
                    ],
                    "note": "If this field is blank, the OutdoorAir:Mixer is not used. This optional field specifies the name of the OutdoorAir:Mixer object. When used, this name needs to match name of the OutdoorAir:Mixer object. This field should be left blank if the VRF terminal unit is connected to central dedicated outdoor air through an AirTerminal:SingleDuct:Mixer object. This field may also be left blank when the VRF terminal is used in the air loop or outdoor air system."
                },
                "cooling_coil_object_type": {
                    "type": "string",
                    "enum": [
                        "Coil:Cooling:DX:VariableRefrigerantFlow",
                        "Coil:Cooling:DX:VariableRefrigerantFlow:FluidTemperatureControl"
                    ],
                    "note": "Cooling Coil Type must be Coil:Cooling:DX:VariableRefrigerantFlow if AirConditioner:VariableRefrigerantFlow is used to model VRF outdoor unit Cooling Coil Type must be Coil:Cooling:DX:VariableRefrigerantFlow:FluidTemperatureControl if AirConditioner:VariableRefrigerantFlow:FluidTemperatureControl or if AirConditioner:VariableRefrigerantFlow:FluidTemperatureControl:HR is used to model VRF outdoor unit This field may be left blank if heating-only mode is used"
                },
                "cooling_coil_object_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "CoolingCoilsDXVarRefrigFlow",
                        "CoolingCoilsDXVarRefrigFlowFluidTemperatureControl"
                    ],
                    "note": "Cooling Coil Type must be Coil:Cooling:DX:VariableRefrigerantFlow This field may be left blank if heating-only mode is used"
                },
                "heating_coil_object_type": {
                    "type": "string",
                    "enum": [
                        "Coil:Heating:DX:VariableRefrigerantFlow",
                        "Coil:Heating:DX:VariableRefrigerantFlow:FluidTemperatureControl"
                    ],
                    "note": "Heating Coil Type must be Coil:Heating:DX:VariableRefrigerantFlow if AirConditioner:VariableRefrigerantFlow is used to model VRF outdoor unit Heating Coil Type must be Coil:Heating:DX:VariableRefrigerantFlow:FluidTemperatureControl if AirConditioner:VariableRefrigerantFlow:FluidTemperatureControl or if AirConditioner:VariableRefrigerantFlow:FluidTemperatureControl:HR is used to model VRF outdoor unit This field may be left blank if cooling-only mode is used"
                },
                "heating_coil_object_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "HeatingCoilsDXVarRefrigFlow",
                        "HeatingCoilsDXVarRefrigFlowFluidTemperatureControl"
                    ],
                    "note": "Heating Coil Type must be Coil:Heating:DX:VariableRefrigerantFlow This field may be left blank if cooling-only mode is used"
                },
                "zone_terminal_unit_on_parasitic_electric_energy_use": {
                    "type": "number",
                    "units": "W",
                    "minimum": 0.0,
                    "default": 0.0
                },
                "zone_terminal_unit_off_parasitic_electric_energy_use": {
                    "type": "number",
                    "units": "W",
                    "minimum": 0.0,
                    "default": 0.0
                },
                "rated_heating_capacity_sizing_ratio": {
                    "type": "number",
                    "units": "W/W",
                    "minimum": 1.0,
                    "default": 1.0,
                    "note": "If this terminal unit's heating coil is autosized, the heating capacity is sized to be equal to the cooling capacity multiplied by this sizing ratio. This input applies to the terminal unit heating coil and overrides the sizing ratio entered in the AirConditioner:VariableRefrigerantFlow object."
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
                    "units": "C",
                    "note": "Supplemental heater will not operate when outdoor temperature exceeds this value."
                },
                "controlling_zone_or_thermostat_location": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ],
                    "note": "Used only for AirloopHVAC equipment on a main branch and defines zone name where thermostat is located. Not required for zone equipment. Leave blank if terminal unit is used in AirLoopHVAC:OutdoorAirSystem:EquipmentList. Required when terminal unit is used on main AirloopHVAC branch and coils are not set point controlled. When terminal unit is used in air loop and is load controlled, this zone's thermostat will control operation."
                }
            },
            "required": [
                "terminal_unit_air_inlet_node_name",
                "terminal_unit_air_outlet_node_name"
            ]
        }
    },
    "group": "Zone HVAC Forced Air Units",
    "legacy_idd": {
        "field_info": {
            "terminal_unit_availability_schedule": {
                "field_name": "Terminal Unit Availability Schedule",
                "field_type": "a"
            },
            "terminal_unit_air_inlet_node_name": {
                "field_name": "Terminal Unit Air Inlet Node Name",
                "field_type": "a"
            },
            "terminal_unit_air_outlet_node_name": {
                "field_name": "Terminal Unit Air Outlet Node Name",
                "field_type": "a"
            },
            "cooling_supply_air_flow_rate": {
                "field_name": "Cooling Supply Air Flow Rate",
                "field_type": "n"
            },
            "no_cooling_supply_air_flow_rate": {
                "field_name": "No Cooling Supply Air Flow Rate",
                "field_type": "n"
            },
            "heating_supply_air_flow_rate": {
                "field_name": "Heating Supply Air Flow Rate",
                "field_type": "n"
            },
            "no_heating_supply_air_flow_rate": {
                "field_name": "No Heating Supply Air Flow Rate",
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
            "supply_air_fan_operating_mode_schedule_name": {
                "field_name": "Supply Air Fan Operating Mode Schedule Name",
                "field_type": "a"
            },
            "supply_air_fan_placement": {
                "field_name": "Supply Air Fan Placement",
                "field_type": "a"
            },
            "supply_air_fan_object_type": {
                "field_name": "Supply Air Fan Object Type",
                "field_type": "a"
            },
            "supply_air_fan_object_name": {
                "field_name": "Supply Air Fan Object Name",
                "field_type": "a"
            },
            "outside_air_mixer_object_type": {
                "field_name": "Outside Air Mixer Object Type",
                "field_type": "a"
            },
            "outside_air_mixer_object_name": {
                "field_name": "Outside Air Mixer Object Name",
                "field_type": "a"
            },
            "cooling_coil_object_type": {
                "field_name": "Cooling Coil Object Type",
                "field_type": "a"
            },
            "cooling_coil_object_name": {
                "field_name": "Cooling Coil Object Name",
                "field_type": "a"
            },
            "heating_coil_object_type": {
                "field_name": "Heating Coil Object Type",
                "field_type": "a"
            },
            "heating_coil_object_name": {
                "field_name": "Heating Coil Object Name",
                "field_type": "a"
            },
            "zone_terminal_unit_on_parasitic_electric_energy_use": {
                "field_name": "Zone Terminal Unit On Parasitic Electric Energy Use",
                "field_type": "n"
            },
            "zone_terminal_unit_off_parasitic_electric_energy_use": {
                "field_name": "Zone Terminal Unit Off Parasitic Electric Energy Use",
                "field_type": "n"
            },
            "rated_heating_capacity_sizing_ratio": {
                "field_name": "Rated Heating Capacity Sizing Ratio",
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
            "controlling_zone_or_thermostat_location": {
                "field_name": "Controlling Zone or Thermostat Location",
                "field_type": "a"
            },
            "name": {
                "field_name": "Zone Terminal Unit Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "terminal_unit_availability_schedule",
            "terminal_unit_air_inlet_node_name",
            "terminal_unit_air_outlet_node_name",
            "cooling_supply_air_flow_rate",
            "no_cooling_supply_air_flow_rate",
            "heating_supply_air_flow_rate",
            "no_heating_supply_air_flow_rate",
            "cooling_outdoor_air_flow_rate",
            "heating_outdoor_air_flow_rate",
            "no_load_outdoor_air_flow_rate",
            "supply_air_fan_operating_mode_schedule_name",
            "supply_air_fan_placement",
            "supply_air_fan_object_type",
            "supply_air_fan_object_name",
            "outside_air_mixer_object_type",
            "outside_air_mixer_object_name",
            "cooling_coil_object_type",
            "cooling_coil_object_name",
            "heating_coil_object_type",
            "heating_coil_object_name",
            "zone_terminal_unit_on_parasitic_electric_energy_use",
            "zone_terminal_unit_off_parasitic_electric_energy_use",
            "rated_heating_capacity_sizing_ratio",
            "availability_manager_list_name",
            "design_specification_zonehvac_sizing_object_name",
            "supplemental_heating_coil_object_type",
            "supplemental_heating_coil_name",
            "maximum_supply_air_temperature_from_supplemental_heater",
            "maximum_outdoor_dry_bulb_temperature_for_supplemental_heater_operation",
            "controlling_zone_or_thermostat_location"
        ],
        "alphas": {
            "fields": [
                "name",
                "terminal_unit_availability_schedule",
                "terminal_unit_air_inlet_node_name",
                "terminal_unit_air_outlet_node_name",
                "supply_air_fan_operating_mode_schedule_name",
                "supply_air_fan_placement",
                "supply_air_fan_object_type",
                "supply_air_fan_object_name",
                "outside_air_mixer_object_type",
                "outside_air_mixer_object_name",
                "cooling_coil_object_type",
                "cooling_coil_object_name",
                "heating_coil_object_type",
                "heating_coil_object_name",
                "availability_manager_list_name",
                "design_specification_zonehvac_sizing_object_name",
                "supplemental_heating_coil_object_type",
                "supplemental_heating_coil_name",
                "controlling_zone_or_thermostat_location"
            ]
        },
        "numerics": {
            "fields": [
                "cooling_supply_air_flow_rate",
                "no_cooling_supply_air_flow_rate",
                "heating_supply_air_flow_rate",
                "no_heating_supply_air_flow_rate",
                "cooling_outdoor_air_flow_rate",
                "heating_outdoor_air_flow_rate",
                "no_load_outdoor_air_flow_rate",
                "zone_terminal_unit_on_parasitic_electric_energy_use",
                "zone_terminal_unit_off_parasitic_electric_energy_use",
                "rated_heating_capacity_sizing_ratio",
                "maximum_supply_air_temperature_from_supplemental_heater",
                "maximum_outdoor_dry_bulb_temperature_for_supplemental_heater_operation"
            ]
        }
    },
    "type": "object",
    "memo": "A terminal unit with variable refrigerant flow (VRF) DX cooling and heating coils (air-to-air heat pump). The VRF terminal units are served by an AirConditioner:VariableRefrigerantFlow or AirConditioner:VariableRefrigerantFlow:FluidTemperatureControl:* system. Terminal units can be configured as zone, air loop or outside air system equipment.",
    "min_fields": 19.0,
    "name": {
        "type": "string",
        "reference": [
            "DOAToZonalUnit",
            "ZoneEquipmentNames",
            "ZoneTerminalUnitNames",
            "validBranchEquipmentNames",
            "validOASysEquipmentNames"
        ],
        "reference-class-name": [
            "validBranchEquipmentTypes",
            "validOASysEquipmentTypes"
        ]
    }
}
```
