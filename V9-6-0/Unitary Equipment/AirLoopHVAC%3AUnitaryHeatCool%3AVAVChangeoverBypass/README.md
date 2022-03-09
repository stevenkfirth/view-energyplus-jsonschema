```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "availability_schedule_name": {
                    "type": "string",
                    "note": "Availability schedule name for this system. Schedule value > 0 means the system is available. If this field is blank, the system is always available. Enter the availability schedule name. Schedule values of zero denote system is Off. Non-zero schedule values denote system is available to operate.",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "cooling_supply_air_flow_rate": {
                    "units": "m3/s",
                    "note": "Enter the system air flow rate during cooling operation or specify autosize.",
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
                    "note": "Enter the system air flow rate during heating operation or specify autosize.",
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
                    "note": "Only used when the supply air fan operating mode is continuous (see field Supply air fan operating mode schedule name). This system air flow rate is used when no heating or cooling is required and the coils are off. If this field is left blank or zero, the system air flow rate from the previous on cycle (either cooling or heating) is used.",
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
                    "note": "Enter the outdoor air flow rate during cooling operation or specify autosize.",
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
                    "note": "Enter the outdoor air flow rate during heating operation or specify autosize.",
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
                    "note": "Only used when the supply air fan operating mode is continuous (see field Supply air fan operating mode schedule name). This outdoor air flow rate is used when no heating or cooling is required and the coils are off. If this field is left blank or zero, the outdoor air flow rate from the previous on cycle (either cooling or heating) is used.",
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
                "outdoor_air_flow_rate_multiplier_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "Enter the name of a schedule that contains multipliers for the outdoor air flow rates. Schedule values must be from 0 to 1. If field is left blank, model assumes multiplier is 1 for the entire simulation period."
                },
                "air_inlet_node_name": {
                    "type": "string",
                    "note": "Enter the name of the unitary system's air inlet node."
                },
                "bypass_duct_mixer_node_name": {
                    "type": "string",
                    "note": "Enter the name of the bypass duct mixer node. This name should be the name of the return air node for the outdoor air mixer associated with this system. This node name must be different from the air inlet node name."
                },
                "bypass_duct_splitter_node_name": {
                    "type": "string",
                    "note": "Enter the name of the bypass duct splitter node. This splitter air node is the outlet node of the last component in this unitary system. For blow through fan placement, the splitter air node is the outlet node of the heating coil. For draw through fan placement, the splitter node is the outlet node of the supply air fan."
                },
                "air_outlet_node_name": {
                    "type": "string",
                    "note": "Enter the name of the unitary system's air outlet node."
                },
                "outdoor_air_mixer_object_type": {
                    "type": "string",
                    "enum": [
                        "OutdoorAir:Mixer"
                    ],
                    "note": "currently only one type OutdoorAir:Mixer object is available."
                },
                "outdoor_air_mixer_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "OutdoorAirMixers"
                    ],
                    "note": "Enter the name of the outdoor air mixer used with this unitary system."
                },
                "supply_air_fan_object_type": {
                    "type": "string",
                    "enum": [
                        "Fan:ConstantVolume",
                        "Fan:OnOff",
                        "Fan:SystemModel"
                    ],
                    "note": "Specify the type of supply air fan used in this unitary system."
                },
                "supply_air_fan_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "FansCVandOnOff",
                        "FansSystemModel"
                    ],
                    "note": "Enter the name of the supply air fan used in this unitary system."
                },
                "supply_air_fan_placement": {
                    "type": "string",
                    "enum": [
                        "BlowThrough",
                        "DrawThrough"
                    ],
                    "note": "Specify supply air fan placement as either blow through or draw through. BlowThrough means the supply air fan is located before the cooling coil. DrawThrough means the supply air fan is located after the heating coil."
                },
                "supply_air_fan_operating_mode_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "Enter the name of a schedule to control the supply air fan. Schedule Name values of zero mean that the supply air fan will cycle off if there is no cooling or heating load in any of the zones being served by this system. Non-zero schedule values mean that the supply air fan will operate continuously even if there is no cooling or heating load in any of the zones being served. If this field is left blank, the supply air fan will operate continuously for the entire simulation period."
                },
                "cooling_coil_object_type": {
                    "type": "string",
                    "enum": [
                        "Coil:Cooling:DX:SingleSpeed",
                        "Coil:Cooling:DX:TwoStageWithHumidityControlMode",
                        "Coil:Cooling:DX:VariableSpeed",
                        "CoilSystem:Cooling:DX:HeatExchangerAssisted"
                    ],
                    "note": "Specify the type of cooling coil used in this unitary system."
                },
                "cooling_coil_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "CoolingCoilsDXMultiModeOrSingleSpeed",
                        "CoolingCoilsDXVariableSpeed"
                    ],
                    "note": "Enter the name of the cooling coil used in this unitary system."
                },
                "heating_coil_object_type": {
                    "type": "string",
                    "enum": [
                        "Coil:Heating:DX:SingleSpeed",
                        "Coil:Heating:DX:VariableSpeed",
                        "Coil:Heating:Electric",
                        "Coil:Heating:Fuel",
                        "Coil:Heating:Steam",
                        "Coil:Heating:Water"
                    ],
                    "note": "works with DX, gas, electric, hot water and steam heating coils Specify the type of heating coil used in this unitary system."
                },
                "heating_coil_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "HeatingCoilName",
                        "HeatingCoilsDXVariableSpeed"
                    ],
                    "note": "Enter the name of the heating coil used in this unitary system."
                },
                "priority_control_mode": {
                    "type": "string",
                    "enum": [
                        "",
                        "CoolingPriority",
                        "HeatingPriority",
                        "LoadPriority",
                        "ZonePriority"
                    ],
                    "default": "ZonePriority",
                    "note": "CoolingPriority = system provides cooling if any zone requires cooling. HeatingPriority = system provides heating if any zone requires heating. ZonePriority = system controlled based on the total number of zones requiring cooling or heating (highest number of zones in cooling or heating determines the system's operating mode). LoadPriority = system provides cooling or heating based on total zone loads."
                },
                "minimum_outlet_air_temperature_during_cooling_operation": {
                    "type": "number",
                    "units": "C",
                    "exclusiveMinimum": 0.0,
                    "default": 8.0,
                    "note": "Specify the minimum outlet air temperature allowed for this unitary system during cooling operation. This value should be less than the maximum outlet air temperature during heating operation."
                },
                "maximum_outlet_air_temperature_during_heating_operation": {
                    "type": "number",
                    "units": "C",
                    "exclusiveMinimum": 0.0,
                    "default": 50.0,
                    "note": "Specify the maximum outlet air temperature allowed for this unitary system during heating operation. This value should be greater than the minimum outlet air temperature during cooling operation."
                },
                "dehumidification_control_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "CoolReheat",
                        "Multimode",
                        "None"
                    ],
                    "default": "None",
                    "note": "None = meet sensible load only. Multimode = activate enhanced dehumidification mode as needed and meet sensible load. Valid only with Coil:Cooling:DX:TwoStageWithHumidityControlMode. CoolReheat = cool beyond the Dry-Bulb temperature setpoint as required to meet the humidity setpoint. Valid only with Coil:Cooling:DX:TwoStageWithHumidityControlMode. For all dehumidification controls, the max humidity setpoint on this unitary system's air outlet node is used. This must be set using ZoneControl:Humidistat and SetpointManager:SingleZone:Humidity:Maximum, SetpointManager:MultiZone:Humidity:Maximum or SetpointManager:MultiZone:MaximumHumidity:Average objects."
                },
                "plenum_or_mixer_inlet_node_name": {
                    "type": "string",
                    "note": "Enter the name of the bypass duct node connected to a plenum or mixer. This field is required when this HVAC System is connected to a plenum or mixer. This is a different node name than that entered in the Bypass Duct Splitter Node Name field."
                },
                "minimum_runtime_before_operating_mode_change": {
                    "type": "number",
                    "units": "hr",
                    "minimum": 0.0,
                    "default": 0.25,
                    "note": "This is the minimum amount of time the unit operates in cooling or heating mode before changing modes."
                }
            },
            "required": [
                "cooling_supply_air_flow_rate",
                "heating_supply_air_flow_rate",
                "cooling_outdoor_air_flow_rate",
                "heating_outdoor_air_flow_rate",
                "air_inlet_node_name",
                "bypass_duct_mixer_node_name",
                "bypass_duct_splitter_node_name",
                "air_outlet_node_name",
                "outdoor_air_mixer_object_type",
                "outdoor_air_mixer_name",
                "supply_air_fan_object_type",
                "supply_air_fan_name",
                "supply_air_fan_placement",
                "cooling_coil_object_type",
                "cooling_coil_name",
                "heating_coil_object_type",
                "heating_coil_name"
            ]
        }
    },
    "group": "Unitary Equipment",
    "name": {
        "type": "string",
        "is_required": true,
        "note": "Enter a unique name for this unitary system.",
        "reference-class-name": [
            "validBranchEquipmentTypes"
        ],
        "reference": [
            "validBranchEquipmentNames"
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
            "outdoor_air_flow_rate_multiplier_schedule_name": {
                "field_name": "Outdoor Air Flow Rate Multiplier Schedule Name",
                "field_type": "a"
            },
            "air_inlet_node_name": {
                "field_name": "Air Inlet Node Name",
                "field_type": "a"
            },
            "bypass_duct_mixer_node_name": {
                "field_name": "Bypass Duct Mixer Node Name",
                "field_type": "a"
            },
            "bypass_duct_splitter_node_name": {
                "field_name": "Bypass Duct Splitter Node Name",
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
            "supply_air_fan_placement": {
                "field_name": "Supply Air Fan Placement",
                "field_type": "a"
            },
            "supply_air_fan_operating_mode_schedule_name": {
                "field_name": "Supply Air Fan Operating Mode Schedule Name",
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
            "heating_coil_object_type": {
                "field_name": "Heating Coil Object Type",
                "field_type": "a"
            },
            "heating_coil_name": {
                "field_name": "Heating Coil Name",
                "field_type": "a"
            },
            "priority_control_mode": {
                "field_name": "Priority Control Mode",
                "field_type": "a"
            },
            "minimum_outlet_air_temperature_during_cooling_operation": {
                "field_name": "Minimum Outlet Air Temperature During Cooling Operation",
                "field_type": "n"
            },
            "maximum_outlet_air_temperature_during_heating_operation": {
                "field_name": "Maximum Outlet Air Temperature During Heating Operation",
                "field_type": "n"
            },
            "dehumidification_control_type": {
                "field_name": "Dehumidification Control Type",
                "field_type": "a"
            },
            "plenum_or_mixer_inlet_node_name": {
                "field_name": "Plenum or Mixer Inlet Node Name",
                "field_type": "a"
            },
            "minimum_runtime_before_operating_mode_change": {
                "field_name": "Minimum Runtime Before Operating Mode Change",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "availability_schedule_name",
            "cooling_supply_air_flow_rate",
            "heating_supply_air_flow_rate",
            "no_load_supply_air_flow_rate",
            "cooling_outdoor_air_flow_rate",
            "heating_outdoor_air_flow_rate",
            "no_load_outdoor_air_flow_rate",
            "outdoor_air_flow_rate_multiplier_schedule_name",
            "air_inlet_node_name",
            "bypass_duct_mixer_node_name",
            "bypass_duct_splitter_node_name",
            "air_outlet_node_name",
            "outdoor_air_mixer_object_type",
            "outdoor_air_mixer_name",
            "supply_air_fan_object_type",
            "supply_air_fan_name",
            "supply_air_fan_placement",
            "supply_air_fan_operating_mode_schedule_name",
            "cooling_coil_object_type",
            "cooling_coil_name",
            "heating_coil_object_type",
            "heating_coil_name",
            "priority_control_mode",
            "minimum_outlet_air_temperature_during_cooling_operation",
            "maximum_outlet_air_temperature_during_heating_operation",
            "dehumidification_control_type",
            "plenum_or_mixer_inlet_node_name",
            "minimum_runtime_before_operating_mode_change"
        ],
        "alphas": {
            "fields": [
                "name",
                "availability_schedule_name",
                "outdoor_air_flow_rate_multiplier_schedule_name",
                "air_inlet_node_name",
                "bypass_duct_mixer_node_name",
                "bypass_duct_splitter_node_name",
                "air_outlet_node_name",
                "outdoor_air_mixer_object_type",
                "outdoor_air_mixer_name",
                "supply_air_fan_object_type",
                "supply_air_fan_name",
                "supply_air_fan_placement",
                "supply_air_fan_operating_mode_schedule_name",
                "cooling_coil_object_type",
                "cooling_coil_name",
                "heating_coil_object_type",
                "heating_coil_name",
                "priority_control_mode",
                "dehumidification_control_type",
                "plenum_or_mixer_inlet_node_name"
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
                "minimum_outlet_air_temperature_during_cooling_operation",
                "maximum_outlet_air_temperature_during_heating_operation",
                "minimum_runtime_before_operating_mode_change"
            ]
        }
    },
    "type": "object",
    "memo": "Unitary system, heating and cooling with constant volume supply fan (continuous or cycling), direct expansion (DX) cooling coil, heating coil (gas, electric, hot water, steam, or DX air-to-air heat pump) and bypass damper for variable volume flow to terminal units. Used with AirTerminal:SingleDuct:VAV:HeatAndCool:Reheat or AirTerminal:SingleDuct:VAV:HeatAndCool:NoReheat.",
    "min_fields": 23.0
}
```
