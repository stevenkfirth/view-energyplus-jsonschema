```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "system_availability_schedule_name": {
                    "type": "string",
                    "note": "If blank, always on; DOAS System always on. Schedule is used in availability manager and fan scheduling.",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "air_outlet_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "DirectIntoZone"
                    ],
                    "default": "DirectIntoZone"
                },
                "supply_fan_flow_rate": {
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
                    "default": 1000.0
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
                        "HeatExchangerAssistedDX",
                        "None",
                        "TwoSpeedDX",
                        "TwoStageDX",
                        "TwoStageHumidityControlDX"
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
                        "FixedSetpoint",
                        "OutdoorAirTemperatureReset",
                        "Scheduled"
                    ],
                    "default": "FixedSetpoint"
                },
                "cooling_coil_design_setpoint": {
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
                "dx_cooling_coil_gross_rated_total_capacity": {
                    "note": "Total cooling capacity not accounting for the effect of supply air fan heat",
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
                "dx_cooling_coil_gross_rated_sensible_heat_ratio": {
                    "note": "Gross SHR",
                    "default": "Autosize",
                    "anyOf": [
                        {
                            "type": "number",
                            "minimum": 0.5,
                            "maximum": 1.0
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
                "dx_cooling_coil_gross_rated_cop": {
                    "type": "number",
                    "note": "Gross cooling capacity divided by power input to the compressor and outdoor fan, does not include supply fan heat or supply fan electrical energy input",
                    "units": "W/W",
                    "exclusiveMinimum": 0.0,
                    "default": 3.0
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
                    "note": "When selecting OutdoorAirTemperatureReset, the Heating Coil Design Setpoint may need to be changed",
                    "enum": [
                        "",
                        "FixedSetpoint",
                        "OutdoorAirTemperatureReset",
                        "Scheduled"
                    ],
                    "default": "FixedSetpoint"
                },
                "heating_coil_design_setpoint": {
                    "type": "number",
                    "note": "Used for sizing and as constant setpoint if no Heating Coil Setpoint Schedule Name is specified.",
                    "default": 12.2,
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
                    "note": "Applicable only for OutdoorAirTemperatureReset control. Defaults 15.0C (59F) at 7.8C (46F) to 12.2C (54F) at 12.2C (54F)",
                    "units": "C",
                    "default": 15.0
                },
                "heating_coil_reset_outdoor_dry_bulb_low": {
                    "type": "number",
                    "note": "Applicable only for OutdoorAirTemperatureReset control.",
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
                "heat_recovery_sensible_effectiveness": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.7
                },
                "heat_recovery_latent_effectiveness": {
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
                    "note": "None = meet sensible load only CoolReheatHeatingCoil = cool beyond the dry-bulb setpoint, reheat with heating coil Valid for all cooling coil types. If no heating coil specified, cold supply temps may occur. CoolReheatDesuperheater = cool beyond the dry-bulb setpoint as required to meet the humidity setpoint, reheat with desuperheater coil. Valid only for Cooling Coil Type = TwoSpeedDX, TwoStageDX, TwoStageHumidityControlDX, or HeatExchangerAssistedDX. Multimode = activate enhanced dehumidification mode as needed and meet sensible load. Valid only for Cooling Coil Type = TwoStageHumidityControlDX or HeatExchangerAssistedDX",
                    "enum": [
                        "",
                        "CoolReheatDesuperheater",
                        "CoolReheatHeatingCoil",
                        "Multimode",
                        "None"
                    ],
                    "default": "None"
                },
                "dehumidification_setpoint": {
                    "type": "number",
                    "note": "The supply air humidity ratio for dehumidification control. Default of 0.00924 kgWater/kgDryAir is equivalent to 12.8C (55F) dewpoint. Ignored if Dehumidification Setpoint Schedule specified below",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.00924,
                    "units": "kgWater/kgDryAir"
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
                "humidifier_constant_setpoint": {
                    "type": "number",
                    "note": "The supply air humidity ratio for humidification control. Ignored if Humidifier Setpoint Schedule specified below",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.003,
                    "units": "kgWater/kgDryAir"
                },
                "dehumidification_setpoint_schedule_name": {
                    "type": "string",
                    "note": "Leave blank to use constant setpoint specified in Dehumidification Setpoint above. Schedule values must be in units of humidity ratio (kgWater/kgDryAir or lbWater/lbDryAir)",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "humidifier_setpoint_schedule_name": {
                    "type": "string",
                    "note": "Leave blank to use constant setpoint specified in Humidifier Constant Setpoint above. Schedule values must be in units of humidity ratio (kgWater/kgDryAir or lbWater/lbDryAir)",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                }
            }
        }
    },
    "group": "HVAC Templates",
    "name": {
        "type": "string",
        "reference": [
            "HVACTemplateDOASSystems",
            "HVACTemplateSystems"
        ]
    },
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
            "air_outlet_type": {
                "field_name": "Air Outlet Type",
                "field_type": "a"
            },
            "supply_fan_flow_rate": {
                "field_name": "Supply Fan Flow Rate",
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
            "cooling_coil_design_setpoint": {
                "field_name": "Cooling Coil Design Setpoint",
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
            "dx_cooling_coil_gross_rated_total_capacity": {
                "field_name": "DX Cooling Coil Gross Rated Total Capacity",
                "field_type": "n"
            },
            "dx_cooling_coil_gross_rated_sensible_heat_ratio": {
                "field_name": "DX Cooling Coil Gross Rated Sensible Heat Ratio",
                "field_type": "n"
            },
            "dx_cooling_coil_gross_rated_cop": {
                "field_name": "DX Cooling Coil Gross Rated COP",
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
            "gas_heating_coil_efficiency": {
                "field_name": "Gas Heating Coil Efficiency",
                "field_type": "n"
            },
            "gas_heating_coil_parasitic_electric_load": {
                "field_name": "Gas Heating Coil Parasitic Electric Load",
                "field_type": "n"
            },
            "heat_recovery_type": {
                "field_name": "Heat Recovery Type",
                "field_type": "a"
            },
            "heat_recovery_sensible_effectiveness": {
                "field_name": "Heat Recovery Sensible Effectiveness",
                "field_type": "n"
            },
            "heat_recovery_latent_effectiveness": {
                "field_name": "Heat Recovery Latent Effectiveness",
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
            "dehumidification_setpoint": {
                "field_name": "Dehumidification Setpoint",
                "field_type": "n"
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
            "humidifier_constant_setpoint": {
                "field_name": "Humidifier Constant Setpoint",
                "field_type": "n"
            },
            "dehumidification_setpoint_schedule_name": {
                "field_name": "Dehumidification Setpoint Schedule Name",
                "field_type": "a"
            },
            "humidifier_setpoint_schedule_name": {
                "field_name": "Humidifier Setpoint Schedule Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "system_availability_schedule_name",
            "air_outlet_type",
            "supply_fan_flow_rate",
            "supply_fan_total_efficiency",
            "supply_fan_delta_pressure",
            "supply_fan_motor_efficiency",
            "supply_fan_motor_in_air_stream_fraction",
            "supply_fan_placement",
            "cooling_coil_type",
            "cooling_coil_availability_schedule_name",
            "cooling_coil_setpoint_control_type",
            "cooling_coil_design_setpoint",
            "cooling_coil_setpoint_schedule_name",
            "cooling_coil_setpoint_at_outdoor_dry_bulb_low",
            "cooling_coil_reset_outdoor_dry_bulb_low",
            "cooling_coil_setpoint_at_outdoor_dry_bulb_high",
            "cooling_coil_reset_outdoor_dry_bulb_high",
            "dx_cooling_coil_gross_rated_total_capacity",
            "dx_cooling_coil_gross_rated_sensible_heat_ratio",
            "dx_cooling_coil_gross_rated_cop",
            "heating_coil_type",
            "heating_coil_availability_schedule_name",
            "heating_coil_setpoint_control_type",
            "heating_coil_design_setpoint",
            "heating_coil_setpoint_schedule_name",
            "heating_coil_setpoint_at_outdoor_dry_bulb_low",
            "heating_coil_reset_outdoor_dry_bulb_low",
            "heating_coil_setpoint_at_outdoor_dry_bulb_high",
            "heating_coil_reset_outdoor_dry_bulb_high",
            "gas_heating_coil_efficiency",
            "gas_heating_coil_parasitic_electric_load",
            "heat_recovery_type",
            "heat_recovery_sensible_effectiveness",
            "heat_recovery_latent_effectiveness",
            "heat_recovery_heat_exchanger_type",
            "heat_recovery_frost_control_type",
            "dehumidification_control_type",
            "dehumidification_setpoint",
            "humidifier_type",
            "humidifier_availability_schedule_name",
            "humidifier_rated_capacity",
            "humidifier_rated_electric_power",
            "humidifier_constant_setpoint",
            "dehumidification_setpoint_schedule_name",
            "humidifier_setpoint_schedule_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "system_availability_schedule_name",
                "air_outlet_type",
                "supply_fan_placement",
                "cooling_coil_type",
                "cooling_coil_availability_schedule_name",
                "cooling_coil_setpoint_control_type",
                "cooling_coil_setpoint_schedule_name",
                "heating_coil_type",
                "heating_coil_availability_schedule_name",
                "heating_coil_setpoint_control_type",
                "heating_coil_setpoint_schedule_name",
                "heat_recovery_type",
                "heat_recovery_heat_exchanger_type",
                "heat_recovery_frost_control_type",
                "dehumidification_control_type",
                "humidifier_type",
                "humidifier_availability_schedule_name",
                "dehumidification_setpoint_schedule_name",
                "humidifier_setpoint_schedule_name"
            ]
        },
        "numerics": {
            "fields": [
                "supply_fan_flow_rate",
                "supply_fan_total_efficiency",
                "supply_fan_delta_pressure",
                "supply_fan_motor_efficiency",
                "supply_fan_motor_in_air_stream_fraction",
                "cooling_coil_design_setpoint",
                "cooling_coil_setpoint_at_outdoor_dry_bulb_low",
                "cooling_coil_reset_outdoor_dry_bulb_low",
                "cooling_coil_setpoint_at_outdoor_dry_bulb_high",
                "cooling_coil_reset_outdoor_dry_bulb_high",
                "dx_cooling_coil_gross_rated_total_capacity",
                "dx_cooling_coil_gross_rated_sensible_heat_ratio",
                "dx_cooling_coil_gross_rated_cop",
                "heating_coil_design_setpoint",
                "heating_coil_setpoint_at_outdoor_dry_bulb_low",
                "heating_coil_reset_outdoor_dry_bulb_low",
                "heating_coil_setpoint_at_outdoor_dry_bulb_high",
                "heating_coil_reset_outdoor_dry_bulb_high",
                "gas_heating_coil_efficiency",
                "gas_heating_coil_parasitic_electric_load",
                "heat_recovery_sensible_effectiveness",
                "heat_recovery_latent_effectiveness",
                "dehumidification_setpoint",
                "humidifier_rated_capacity",
                "humidifier_rated_electric_power",
                "humidifier_constant_setpoint"
            ]
        }
    },
    "type": "object",
    "memo": "This object creates a dedicated outdoor air system that must be used with HVACTemplate:Zone:* objects for BaseboardHeat FanCoil PTAC PTHP WaterToAirHeatPump and VRF. Does not support HVACTemplate:Zone:VAV or other central multizone systems",
    "min_fields": 46.0
}
```
