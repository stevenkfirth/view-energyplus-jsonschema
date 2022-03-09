```
{
    "HVACTemplate:System:ConstantVolume": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "system_availability_schedule_name": {
                        "type": "string",
                        "note": "If blank, always on;  Schedule is used in availability manager and fan scheduling. Also see \"Night Cycle Control\" field.",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "supply_fan_maximum_flow_rate": {
                        "note": "This field may be set to \"autosize\". If a value is entered, it will *not* be multiplied by any sizing factor or by zone multipliers. If using zone multipliers a value entered here must be large enough to serve the multiplied zones.",
                        "default": "Autosize",
                        "units": "m3/s",
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
                    "supply_fan_total_efficiency": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.7
                    },
                    "supply_fan_delta_pressure": {
                        "type": "number",
                        "units": "Pa",
                        "ip-units": "inH2O",
                        "minimum": 0.0,
                        "default": 600.0
                    },
                    "supply_fan_motor_efficiency": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.9
                    },
                    "supply_fan_motor_in_air_stream_fraction": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 1.0
                    },
                    "supply_fan_placement": {
                        "type": "string",
                        "enum": [
                            "",
                            "BlowThrough",
                            "DrawThrough"
                        ],
                        "default": "DrawThrough"
                    },
                    "cooling_coil_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "ChilledWater",
                            "ChilledWaterDetailedFlatModel",
                            "HeatExchangerAssistedChilledWater",
                            "None"
                        ],
                        "default": "ChilledWater"
                    },
                    "cooling_coil_availability_schedule_name": {
                        "type": "string",
                        "note": "If blank, always on",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "cooling_coil_setpoint_control_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "ControlZone",
                            "FixedSetpoint",
                            "OutdoorAirTemperatureReset",
                            "Scheduled",
                            "Warmest"
                        ],
                        "default": "FixedSetpoint"
                    },
                    "cooling_coil_control_zone_name": {
                        "type": "string",
                        "note": "name of the HVACTemplate:ZoneConstantVolume object that contains the cooling thermostat when Cooling Coil Setpoint Control Type = ControlZone",
                        "data_type": "object_list",
                        "object_list": [
                            "HVACTemplateConstantVolumeZones"
                        ]
                    },
                    "cooling_coil_design_setpoint_temperature": {
                        "type": "number",
                        "note": "Used for sizing and as constant setpoint if no Cooling Coil Setpoint Schedule Name is specified.",
                        "default": 12.8,
                        "units": "C"
                    },
                    "cooling_coil_setpoint_schedule_name": {
                        "type": "string",
                        "note": "Leave blank if constant setpoint",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "cooling_coil_setpoint_at_outdoor_dry_bulb_low": {
                        "type": "number",
                        "note": "Applicable only for OutdoorAirTemperatureReset control.",
                        "units": "C",
                        "default": 15.6
                    },
                    "cooling_coil_reset_outdoor_dry_bulb_low": {
                        "type": "number",
                        "note": "Applicable only for OutdoorAirTemperatureReset control. Defaults are 15.6C (60F) at 15.6C (60F) to 12.8C (55F) at 23.3C (74F)",
                        "units": "C",
                        "default": 15.6
                    },
                    "cooling_coil_setpoint_at_outdoor_dry_bulb_high": {
                        "type": "number",
                        "note": "Applicable only for OutdoorAirTemperatureReset control.",
                        "units": "C",
                        "default": 12.8
                    },
                    "cooling_coil_reset_outdoor_dry_bulb_high": {
                        "type": "number",
                        "note": "Applicable only for OutdoorAirTemperatureReset control.",
                        "units": "C",
                        "default": 23.3
                    },
                    "heating_coil_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "Electric",
                            "Gas",
                            "HotWater",
                            "None"
                        ],
                        "default": "HotWater"
                    },
                    "heating_coil_availability_schedule_name": {
                        "type": "string",
                        "note": "If blank, always on",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "heating_coil_setpoint_control_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "ControlZone",
                            "FixedSetpoint",
                            "OutdoorAirTemperatureReset",
                            "Scheduled"
                        ],
                        "default": "FixedSetpoint"
                    },
                    "heating_coil_control_zone_name": {
                        "type": "string",
                        "note": "name of the HVACTemplate:ZoneConstantVolume object that contains the heating thermostat",
                        "data_type": "object_list",
                        "object_list": [
                            "HVACTemplateConstantVolumeZones"
                        ]
                    },
                    "heating_coil_design_setpoint": {
                        "type": "number",
                        "note": "Used for sizing and as constant setpoint if no Heating Coil Setpoint Schedule Name is specified.",
                        "default": 10.0,
                        "units": "C"
                    },
                    "heating_coil_setpoint_schedule_name": {
                        "type": "string",
                        "note": "Leave blank if constant setpoint",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "heating_coil_setpoint_at_outdoor_dry_bulb_low": {
                        "type": "number",
                        "note": "Applicable only for OutdoorAirTemperatureReset control.",
                        "units": "C",
                        "default": 15.0
                    },
                    "heating_coil_reset_outdoor_dry_bulb_low": {
                        "type": "number",
                        "note": "Applicable only for OutdoorAirTemperatureReset control. Defaults are 15.6C (60F) at 15.6C (60F) to 12.8C (55F) at 23.3C (74F)",
                        "units": "C",
                        "default": 7.8
                    },
                    "heating_coil_setpoint_at_outdoor_dry_bulb_high": {
                        "type": "number",
                        "note": "Applicable only for OutdoorAirTemperatureReset control.",
                        "units": "C",
                        "default": 12.2
                    },
                    "heating_coil_reset_outdoor_dry_bulb_high": {
                        "type": "number",
                        "note": "Applicable only for OutdoorAirTemperatureReset control.",
                        "units": "C",
                        "default": 12.2
                    },
                    "heating_coil_capacity": {
                        "default": "Autosize",
                        "units": "W",
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
                    "gas_heating_coil_efficiency": {
                        "type": "number",
                        "maximum": 1.0,
                        "minimum": 0.0,
                        "default": 0.8
                    },
                    "gas_heating_coil_parasitic_electric_load": {
                        "type": "number",
                        "units": "W",
                        "ip-units": "W",
                        "minimum": 0.0,
                        "default": 0.0
                    },
                    "preheat_coil_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "Electric",
                            "Gas",
                            "HotWater",
                            "None"
                        ],
                        "default": "None"
                    },
                    "preheat_coil_availability_schedule_name": {
                        "type": "string",
                        "note": "If blank, always on",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "preheat_coil_design_setpoint": {
                        "type": "number",
                        "note": "Used for sizing and as constant setpoint if no Preheat Coil Setpoint Schedule Name specified.",
                        "units": "C",
                        "default": 7.2
                    },
                    "preheat_coil_setpoint_schedule_name": {
                        "type": "string",
                        "note": "Leave blank if constant setpoint",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "gas_preheat_coil_efficiency": {
                        "type": "number",
                        "maximum": 1.0,
                        "minimum": 0.0,
                        "default": 0.8
                    },
                    "gas_preheat_coil_parasitic_electric_load": {
                        "type": "number",
                        "units": "W",
                        "ip-units": "W",
                        "minimum": 0.0,
                        "default": 0.0
                    },
                    "maximum_outdoor_air_flow_rate": {
                        "default": "Autosize",
                        "units": "m3/s",
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
                    "minimum_outdoor_air_flow_rate": {
                        "default": "Autosize",
                        "units": "m3/s",
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
                    "minimum_outdoor_air_schedule_name": {
                        "type": "string",
                        "note": "Schedule values multiply the Minimum Outdoor Air Flow Rate If blank, multiplier is always one",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "economizer_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "DifferentialDryBulb",
                            "DifferentialDryBulbAndEnthalpy",
                            "DifferentialEnthalpy",
                            "ElectronicEnthalpy",
                            "FixedDewPointAndDryBulb",
                            "FixedDryBulb",
                            "FixedEnthalpy",
                            "NoEconomizer"
                        ],
                        "default": "NoEconomizer"
                    },
                    "economizer_upper_temperature_limit": {
                        "type": "number",
                        "note": "Outdoor temperature above which economizer is disabled and heat recovery is enabled (if available). Blank means no limit.",
                        "units": "C"
                    },
                    "economizer_lower_temperature_limit": {
                        "type": "number",
                        "note": "Outdoor temperature below which economizer is disabled and heat recovery is enabled (if available). Blank means no limit.",
                        "units": "C"
                    },
                    "economizer_upper_enthalpy_limit": {
                        "type": "number",
                        "note": "Outdoor enthalpy above which economizer is disabled and heat recovery is enabled (if available). Blank means no limit.",
                        "units": "J/kg"
                    },
                    "economizer_maximum_limit_dewpoint_temperature": {
                        "type": "number",
                        "units": "C",
                        "note": "Enter the maximum outdoor dewpoint temperature limit for FixedDewPointAndDryBulb economizer control type. No input or blank input means this limit is not operative. Limit is applied regardless of economizer control type."
                    },
                    "supply_plenum_name": {
                        "type": "string",
                        "note": "Plenum zone name. Supply plenum serves all zones on this system. Blank if none.",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ]
                    },
                    "return_plenum_name": {
                        "type": "string",
                        "note": "Plenum zone name. Supply plenum serves all zones on this system. Blank if none.",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ]
                    },
                    "night_cycle_control": {
                        "type": "string",
                        "enum": [
                            "",
                            "CycleOnAny",
                            "CycleOnAnyZoneFansOnly",
                            "CycleOnControlZone",
                            "StayOff"
                        ],
                        "default": "StayOff"
                    },
                    "night_cycle_control_zone_name": {
                        "type": "string",
                        "note": "Applicable only if Night Cycle Control is Cycle On Control Zone.",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ]
                    },
                    "heat_recovery_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "Enthalpy",
                            "None",
                            "Sensible"
                        ],
                        "default": "None"
                    },
                    "sensible_heat_recovery_effectiveness": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.7
                    },
                    "latent_heat_recovery_effectiveness": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.65
                    },
                    "heat_recovery_heat_exchanger_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "Plate",
                            "Rotary"
                        ],
                        "default": "Plate"
                    },
                    "heat_recovery_frost_control_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "ExhaustAirRecirculation",
                            "ExhaustOnly",
                            "MinimumExhaustTemperature",
                            "None"
                        ],
                        "default": "None"
                    },
                    "dehumidification_control_type": {
                        "type": "string",
                        "note": "None = meet sensible load only CoolReheat = cool beyond the dry-bulb setpoint as required to meet the humidity setpoint.",
                        "enum": [
                            "",
                            "CoolReheat",
                            "None"
                        ],
                        "default": "None"
                    },
                    "dehumidification_control_zone_name": {
                        "type": "string",
                        "note": "Zone name where humidistat is located",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ]
                    },
                    "dehumidification_relative_humidity_setpoint": {
                        "type": "number",
                        "note": "Zone relative humidity setpoint in percent (0 to 100) Ignored if Dehumidification Relative Humidity Setpoint Schedule specified below",
                        "minimum": 0.0,
                        "maximum": 100.0,
                        "default": 60.0,
                        "units": "percent"
                    },
                    "dehumidification_relative_humidity_setpoint_schedule_name": {
                        "type": "string",
                        "note": "Leave blank to use constant setpoint specified in Dehumidification Relative Humidity Setpoint above. Schedule values must be in percent relative humidity (0 to 100).",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "humidifier_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "ElectricSteam",
                            "None"
                        ],
                        "default": "None"
                    },
                    "humidifier_availability_schedule_name": {
                        "type": "string",
                        "note": "If blank, always available",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "humidifier_rated_capacity": {
                        "type": "number",
                        "note": "Moisture output rate at full rated power input. The humidifier does not currently autosize, so the default is very large to allow for adequate capacity.",
                        "units": "m3/s",
                        "minimum": 0.0,
                        "default": 1e-06,
                        "ip-units": "gal/min"
                    },
                    "humidifier_rated_electric_power": {
                        "note": "Electric power input at rated capacity moisture output. Power consumption is proportional to moisture output with no part-load penalty.",
                        "units": "W",
                        "default": "Autosize",
                        "ip-units": "W",
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
                    "humidifier_control_zone_name": {
                        "type": "string",
                        "note": "Zone name where humidistat is located",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ]
                    },
                    "humidifier_relative_humidity_setpoint": {
                        "type": "number",
                        "note": "Zone relative humidity setpoint in percent (0 to 100). Ignored if Humidifier Relative Humidity Setpoint Schedule specified below",
                        "minimum": 0.0,
                        "maximum": 100.0,
                        "default": 30.0,
                        "units": "percent"
                    },
                    "humidifier_relative_humidity_setpoint_schedule_name": {
                        "type": "string",
                        "note": "Leave blank to use constant setpoint specified in Humidifier Relative Humidity Setpoint above. Schedule values must be in percent relative humidity (0 to 100).",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "return_fan": {
                        "type": "string",
                        "note": "Specifies if the system has a return fan.",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "No"
                    },
                    "return_fan_total_efficiency": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.7
                    },
                    "return_fan_delta_pressure": {
                        "type": "number",
                        "units": "Pa",
                        "ip-units": "inH2O",
                        "minimum": 0.0,
                        "default": 300.0
                    },
                    "return_fan_motor_efficiency": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.9
                    },
                    "return_fan_motor_in_air_stream_fraction": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 1.0
                    }
                }
            }
        },
        "group": "HVAC Templates",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "CompactHVACSystemConstantVolume",
                "HVACTemplateSystems"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "system_availability_schedule_name": {
                    "field_name": "System Availability Schedule Name",
                    "field_type": "a"
                },
                "supply_fan_maximum_flow_rate": {
                    "field_name": "Supply Fan Maximum Flow Rate",
                    "field_type": "n"
                },
                "supply_fan_total_efficiency": {
                    "field_name": "Supply Fan Total Efficiency",
                    "field_type": "n"
                },
                "supply_fan_delta_pressure": {
                    "field_name": "Supply Fan Delta Pressure",
                    "field_type": "n"
                },
                "supply_fan_motor_efficiency": {
                    "field_name": "Supply Fan Motor Efficiency",
                    "field_type": "n"
                },
                "supply_fan_motor_in_air_stream_fraction": {
                    "field_name": "Supply Fan Motor in Air Stream Fraction",
                    "field_type": "n"
                },
                "supply_fan_placement": {
                    "field_name": "Supply Fan Placement",
                    "field_type": "a"
                },
                "cooling_coil_type": {
                    "field_name": "Cooling Coil Type",
                    "field_type": "a"
                },
                "cooling_coil_availability_schedule_name": {
                    "field_name": "Cooling Coil Availability Schedule Name",
                    "field_type": "a"
                },
                "cooling_coil_setpoint_control_type": {
                    "field_name": "Cooling Coil Setpoint Control Type",
                    "field_type": "a"
                },
                "cooling_coil_control_zone_name": {
                    "field_name": "Cooling Coil Control Zone name",
                    "field_type": "a"
                },
                "cooling_coil_design_setpoint_temperature": {
                    "field_name": "Cooling Coil Design Setpoint Temperature",
                    "field_type": "n"
                },
                "cooling_coil_setpoint_schedule_name": {
                    "field_name": "Cooling Coil Setpoint Schedule Name",
                    "field_type": "a"
                },
                "cooling_coil_setpoint_at_outdoor_dry_bulb_low": {
                    "field_name": "Cooling Coil Setpoint at Outdoor Dry-Bulb Low",
                    "field_type": "n"
                },
                "cooling_coil_reset_outdoor_dry_bulb_low": {
                    "field_name": "Cooling Coil Reset Outdoor Dry-Bulb Low",
                    "field_type": "n"
                },
                "cooling_coil_setpoint_at_outdoor_dry_bulb_high": {
                    "field_name": "Cooling Coil Setpoint at Outdoor Dry-Bulb High",
                    "field_type": "n"
                },
                "cooling_coil_reset_outdoor_dry_bulb_high": {
                    "field_name": "Cooling Coil Reset Outdoor Dry-Bulb High",
                    "field_type": "n"
                },
                "heating_coil_type": {
                    "field_name": "Heating Coil Type",
                    "field_type": "a"
                },
                "heating_coil_availability_schedule_name": {
                    "field_name": "Heating Coil Availability Schedule Name",
                    "field_type": "a"
                },
                "heating_coil_setpoint_control_type": {
                    "field_name": "Heating Coil Setpoint Control Type",
                    "field_type": "a"
                },
                "heating_coil_control_zone_name": {
                    "field_name": "Heating Coil Control Zone name",
                    "field_type": "a"
                },
                "heating_coil_design_setpoint": {
                    "field_name": "Heating Coil Design Setpoint",
                    "field_type": "n"
                },
                "heating_coil_setpoint_schedule_name": {
                    "field_name": "Heating Coil Setpoint Schedule Name",
                    "field_type": "a"
                },
                "heating_coil_setpoint_at_outdoor_dry_bulb_low": {
                    "field_name": "Heating Coil Setpoint at Outdoor Dry-Bulb Low",
                    "field_type": "n"
                },
                "heating_coil_reset_outdoor_dry_bulb_low": {
                    "field_name": "Heating Coil Reset Outdoor Dry-Bulb Low",
                    "field_type": "n"
                },
                "heating_coil_setpoint_at_outdoor_dry_bulb_high": {
                    "field_name": "Heating Coil Setpoint at Outdoor Dry-Bulb High",
                    "field_type": "n"
                },
                "heating_coil_reset_outdoor_dry_bulb_high": {
                    "field_name": "Heating Coil Reset Outdoor Dry-Bulb High",
                    "field_type": "n"
                },
                "heating_coil_capacity": {
                    "field_name": "Heating Coil Capacity",
                    "field_type": "n"
                },
                "gas_heating_coil_efficiency": {
                    "field_name": "Gas Heating Coil Efficiency",
                    "field_type": "n"
                },
                "gas_heating_coil_parasitic_electric_load": {
                    "field_name": "Gas Heating Coil Parasitic Electric Load",
                    "field_type": "n"
                },
                "preheat_coil_type": {
                    "field_name": "Preheat Coil Type",
                    "field_type": "a"
                },
                "preheat_coil_availability_schedule_name": {
                    "field_name": "Preheat Coil Availability Schedule Name",
                    "field_type": "a"
                },
                "preheat_coil_design_setpoint": {
                    "field_name": "Preheat Coil Design Setpoint",
                    "field_type": "n"
                },
                "preheat_coil_setpoint_schedule_name": {
                    "field_name": "Preheat Coil Setpoint Schedule Name",
                    "field_type": "a"
                },
                "gas_preheat_coil_efficiency": {
                    "field_name": "Gas Preheat Coil Efficiency",
                    "field_type": "n"
                },
                "gas_preheat_coil_parasitic_electric_load": {
                    "field_name": "Gas Preheat Coil Parasitic Electric Load",
                    "field_type": "n"
                },
                "maximum_outdoor_air_flow_rate": {
                    "field_name": "Maximum Outdoor Air Flow Rate",
                    "field_type": "n"
                },
                "minimum_outdoor_air_flow_rate": {
                    "field_name": "Minimum Outdoor Air Flow Rate",
                    "field_type": "n"
                },
                "minimum_outdoor_air_schedule_name": {
                    "field_name": "Minimum Outdoor Air Schedule Name",
                    "field_type": "a"
                },
                "economizer_type": {
                    "field_name": "Economizer Type",
                    "field_type": "a"
                },
                "economizer_upper_temperature_limit": {
                    "field_name": "Economizer Upper Temperature Limit",
                    "field_type": "n"
                },
                "economizer_lower_temperature_limit": {
                    "field_name": "Economizer Lower Temperature Limit",
                    "field_type": "n"
                },
                "economizer_upper_enthalpy_limit": {
                    "field_name": "Economizer Upper Enthalpy Limit",
                    "field_type": "n"
                },
                "economizer_maximum_limit_dewpoint_temperature": {
                    "field_name": "Economizer Maximum Limit Dewpoint Temperature",
                    "field_type": "n"
                },
                "supply_plenum_name": {
                    "field_name": "Supply Plenum Name",
                    "field_type": "a"
                },
                "return_plenum_name": {
                    "field_name": "Return Plenum Name",
                    "field_type": "a"
                },
                "night_cycle_control": {
                    "field_name": "Night Cycle Control",
                    "field_type": "a"
                },
                "night_cycle_control_zone_name": {
                    "field_name": "Night Cycle Control Zone Name",
                    "field_type": "a"
                },
                "heat_recovery_type": {
                    "field_name": "Heat Recovery Type",
                    "field_type": "a"
                },
                "sensible_heat_recovery_effectiveness": {
                    "field_name": "Sensible Heat Recovery Effectiveness",
                    "field_type": "n"
                },
                "latent_heat_recovery_effectiveness": {
                    "field_name": "Latent Heat Recovery Effectiveness",
                    "field_type": "n"
                },
                "heat_recovery_heat_exchanger_type": {
                    "field_name": "Heat Recovery Heat Exchanger Type",
                    "field_type": "a"
                },
                "heat_recovery_frost_control_type": {
                    "field_name": "Heat Recovery Frost Control Type",
                    "field_type": "a"
                },
                "dehumidification_control_type": {
                    "field_name": "Dehumidification Control Type",
                    "field_type": "a"
                },
                "dehumidification_control_zone_name": {
                    "field_name": "Dehumidification Control Zone Name",
                    "field_type": "a"
                },
                "dehumidification_relative_humidity_setpoint": {
                    "field_name": "Dehumidification Relative Humidity Setpoint",
                    "field_type": "n"
                },
                "dehumidification_relative_humidity_setpoint_schedule_name": {
                    "field_name": "Dehumidification Relative Humidity Setpoint Schedule Name",
                    "field_type": "a"
                },
                "humidifier_type": {
                    "field_name": "Humidifier Type",
                    "field_type": "a"
                },
                "humidifier_availability_schedule_name": {
                    "field_name": "Humidifier Availability Schedule Name",
                    "field_type": "a"
                },
                "humidifier_rated_capacity": {
                    "field_name": "Humidifier Rated Capacity",
                    "field_type": "n"
                },
                "humidifier_rated_electric_power": {
                    "field_name": "Humidifier Rated Electric Power",
                    "field_type": "n"
                },
                "humidifier_control_zone_name": {
                    "field_name": "Humidifier Control Zone Name",
                    "field_type": "a"
                },
                "humidifier_relative_humidity_setpoint": {
                    "field_name": "Humidifier Relative Humidity Setpoint",
                    "field_type": "n"
                },
                "humidifier_relative_humidity_setpoint_schedule_name": {
                    "field_name": "Humidifier Relative Humidity Setpoint Schedule Name",
                    "field_type": "a"
                },
                "return_fan": {
                    "field_name": "Return Fan",
                    "field_type": "a"
                },
                "return_fan_total_efficiency": {
                    "field_name": "Return Fan Total Efficiency",
                    "field_type": "n"
                },
                "return_fan_delta_pressure": {
                    "field_name": "Return Fan Delta Pressure",
                    "field_type": "n"
                },
                "return_fan_motor_efficiency": {
                    "field_name": "Return Fan Motor Efficiency",
                    "field_type": "n"
                },
                "return_fan_motor_in_air_stream_fraction": {
                    "field_name": "Return Fan Motor in Air Stream Fraction",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "system_availability_schedule_name",
                "supply_fan_maximum_flow_rate",
                "supply_fan_total_efficiency",
                "supply_fan_delta_pressure",
                "supply_fan_motor_efficiency",
                "supply_fan_motor_in_air_stream_fraction",
                "supply_fan_placement",
                "cooling_coil_type",
                "cooling_coil_availability_schedule_name",
                "cooling_coil_setpoint_control_type",
                "cooling_coil_control_zone_name",
                "cooling_coil_design_setpoint_temperature",
                "cooling_coil_setpoint_schedule_name",
                "cooling_coil_setpoint_at_outdoor_dry_bulb_low",
                "cooling_coil_reset_outdoor_dry_bulb_low",
                "cooling_coil_setpoint_at_outdoor_dry_bulb_high",
                "cooling_coil_reset_outdoor_dry_bulb_high",
                "heating_coil_type",
                "heating_coil_availability_schedule_name",
                "heating_coil_setpoint_control_type",
                "heating_coil_control_zone_name",
                "heating_coil_design_setpoint",
                "heating_coil_setpoint_schedule_name",
                "heating_coil_setpoint_at_outdoor_dry_bulb_low",
                "heating_coil_reset_outdoor_dry_bulb_low",
                "heating_coil_setpoint_at_outdoor_dry_bulb_high",
                "heating_coil_reset_outdoor_dry_bulb_high",
                "heating_coil_capacity",
                "gas_heating_coil_efficiency",
                "gas_heating_coil_parasitic_electric_load",
                "preheat_coil_type",
                "preheat_coil_availability_schedule_name",
                "preheat_coil_design_setpoint",
                "preheat_coil_setpoint_schedule_name",
                "gas_preheat_coil_efficiency",
                "gas_preheat_coil_parasitic_electric_load",
                "maximum_outdoor_air_flow_rate",
                "minimum_outdoor_air_flow_rate",
                "minimum_outdoor_air_schedule_name",
                "economizer_type",
                "economizer_upper_temperature_limit",
                "economizer_lower_temperature_limit",
                "economizer_upper_enthalpy_limit",
                "economizer_maximum_limit_dewpoint_temperature",
                "supply_plenum_name",
                "return_plenum_name",
                "night_cycle_control",
                "night_cycle_control_zone_name",
                "heat_recovery_type",
                "sensible_heat_recovery_effectiveness",
                "latent_heat_recovery_effectiveness",
                "heat_recovery_heat_exchanger_type",
                "heat_recovery_frost_control_type",
                "dehumidification_control_type",
                "dehumidification_control_zone_name",
                "dehumidification_relative_humidity_setpoint",
                "dehumidification_relative_humidity_setpoint_schedule_name",
                "humidifier_type",
                "humidifier_availability_schedule_name",
                "humidifier_rated_capacity",
                "humidifier_rated_electric_power",
                "humidifier_control_zone_name",
                "humidifier_relative_humidity_setpoint",
                "humidifier_relative_humidity_setpoint_schedule_name",
                "return_fan",
                "return_fan_total_efficiency",
                "return_fan_delta_pressure",
                "return_fan_motor_efficiency",
                "return_fan_motor_in_air_stream_fraction"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "system_availability_schedule_name",
                    "supply_fan_placement",
                    "cooling_coil_type",
                    "cooling_coil_availability_schedule_name",
                    "cooling_coil_setpoint_control_type",
                    "cooling_coil_control_zone_name",
                    "cooling_coil_setpoint_schedule_name",
                    "heating_coil_type",
                    "heating_coil_availability_schedule_name",
                    "heating_coil_setpoint_control_type",
                    "heating_coil_control_zone_name",
                    "heating_coil_setpoint_schedule_name",
                    "preheat_coil_type",
                    "preheat_coil_availability_schedule_name",
                    "preheat_coil_setpoint_schedule_name",
                    "minimum_outdoor_air_schedule_name",
                    "economizer_type",
                    "supply_plenum_name",
                    "return_plenum_name",
                    "night_cycle_control",
                    "night_cycle_control_zone_name",
                    "heat_recovery_type",
                    "heat_recovery_heat_exchanger_type",
                    "heat_recovery_frost_control_type",
                    "dehumidification_control_type",
                    "dehumidification_control_zone_name",
                    "dehumidification_relative_humidity_setpoint_schedule_name",
                    "humidifier_type",
                    "humidifier_availability_schedule_name",
                    "humidifier_control_zone_name",
                    "humidifier_relative_humidity_setpoint_schedule_name",
                    "return_fan"
                ]
            },
            "numerics": {
                "fields": [
                    "supply_fan_maximum_flow_rate",
                    "supply_fan_total_efficiency",
                    "supply_fan_delta_pressure",
                    "supply_fan_motor_efficiency",
                    "supply_fan_motor_in_air_stream_fraction",
                    "cooling_coil_design_setpoint_temperature",
                    "cooling_coil_setpoint_at_outdoor_dry_bulb_low",
                    "cooling_coil_reset_outdoor_dry_bulb_low",
                    "cooling_coil_setpoint_at_outdoor_dry_bulb_high",
                    "cooling_coil_reset_outdoor_dry_bulb_high",
                    "heating_coil_design_setpoint",
                    "heating_coil_setpoint_at_outdoor_dry_bulb_low",
                    "heating_coil_reset_outdoor_dry_bulb_low",
                    "heating_coil_setpoint_at_outdoor_dry_bulb_high",
                    "heating_coil_reset_outdoor_dry_bulb_high",
                    "heating_coil_capacity",
                    "gas_heating_coil_efficiency",
                    "gas_heating_coil_parasitic_electric_load",
                    "preheat_coil_design_setpoint",
                    "gas_preheat_coil_efficiency",
                    "gas_preheat_coil_parasitic_electric_load",
                    "maximum_outdoor_air_flow_rate",
                    "minimum_outdoor_air_flow_rate",
                    "economizer_upper_temperature_limit",
                    "economizer_lower_temperature_limit",
                    "economizer_upper_enthalpy_limit",
                    "economizer_maximum_limit_dewpoint_temperature",
                    "sensible_heat_recovery_effectiveness",
                    "latent_heat_recovery_effectiveness",
                    "dehumidification_relative_humidity_setpoint",
                    "humidifier_rated_capacity",
                    "humidifier_rated_electric_power",
                    "humidifier_relative_humidity_setpoint",
                    "return_fan_total_efficiency",
                    "return_fan_delta_pressure",
                    "return_fan_motor_efficiency",
                    "return_fan_motor_in_air_stream_fraction"
                ]
            }
        },
        "type": "object",
        "memo": "Constant Air Volume air loop with optional chilled water cooling coil, optional heating coil and optional preheat.",
        "min_fields": 70.0
    }
}
```
