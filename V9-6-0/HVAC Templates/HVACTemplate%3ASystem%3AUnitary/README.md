```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "system_availability_schedule_name": {
                    "type": "string",
                    "note": "If blank, always on; Unitary System always on. Schedule is used in availability manager and fan scheduling. Also see \"Night Cycle Control\" field.",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "control_zone_or_thermostat_location_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
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
                "supply_fan_operating_mode_schedule_name": {
                    "type": "string",
                    "note": "Refers to a schedule to specify unitary supply fan operating mode. Schedule values of 0 indicate cycling fan (auto) Schedule values of 1 indicate continuous fan (on) If this field is left blank, a schedule of always zero (cycling fan) will be used.",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
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
                "cooling_coil_type": {
                    "type": "string",
                    "enum": [
                        "",
                        "None",
                        "SingleSpeedDX"
                    ],
                    "default": "SingleSpeedDX"
                },
                "cooling_coil_availability_schedule_name": {
                    "type": "string",
                    "note": "If blank, always on",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "cooling_design_supply_air_temperature": {
                    "type": "number",
                    "note": "Used for sizing.",
                    "default": 12.8,
                    "units": "C"
                },
                "cooling_coil_gross_rated_total_capacity": {
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
                "cooling_coil_gross_rated_sensible_heat_ratio": {
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
                "cooling_coil_gross_rated_cop": {
                    "type": "number",
                    "note": "Gross cooling capacity divided by power input to the compressor and outdoor fan, does not include supply air fan heat or supply air fan electric power",
                    "units": "W/W",
                    "exclusiveMinimum": 0.0,
                    "default": 3.0
                },
                "heating_coil_type": {
                    "type": "string",
                    "enum": [
                        "Electric",
                        "Gas",
                        "HotWater"
                    ]
                },
                "heating_coil_availability_schedule_name": {
                    "type": "string",
                    "note": "If blank, always on",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "heating_design_supply_air_temperature": {
                    "type": "number",
                    "note": "Used for sizing.",
                    "default": 50.0,
                    "units": "C"
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
                    "note": "Schedule values multiply the minimum outdoor air flow rate If blank, always one",
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
                "economizer_lockout": {
                    "type": "string",
                    "enum": [
                        "",
                        "LockoutWithCompressor",
                        "LockoutWithHeating",
                        "NoLockout"
                    ],
                    "default": "NoLockout"
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
                    "note": "Plenum zone name. Return plenum serves all zones on this system. Blank if none.",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ]
                },
                "supply_fan_placement": {
                    "type": "string",
                    "enum": [
                        "",
                        "BlowThrough",
                        "DrawThrough"
                    ],
                    "default": "BlowThrough"
                },
                "night_cycle_control": {
                    "type": "string",
                    "enum": [
                        "",
                        "CycleOnAny",
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
                    "note": "Applicable only if Heat Recovery Type is Enthalpy.",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.65
                },
                "dehumidification_control_type": {
                    "type": "string",
                    "note": "None = meet sensible cooling load only CoolReheatHeatingCoil = cool beyond the dry-bulb setpoint as required to meet the humidity setpoint, reheat with main heating coil. CoolReheatDesuperheater = cool beyond the dry-bulb setpoint as required to meet the humidity setpoint, reheat with desuperheater coil.",
                    "enum": [
                        "",
                        "CoolReheatDesuperheater",
                        "CoolReheatHeatingCoil",
                        "None"
                    ],
                    "default": "None"
                },
                "dehumidification_setpoint": {
                    "type": "number",
                    "note": "Zone relative humidity setpoint in percent (0 to 100)",
                    "minimum": 0.0,
                    "maximum": 100.0,
                    "default": 60.0,
                    "units": "percent"
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
                "humidifier_setpoint": {
                    "type": "number",
                    "note": "Zone relative humidity setpoint in percent (0 to 100)",
                    "minimum": 0.0,
                    "maximum": 100.0,
                    "default": 30.0,
                    "units": "percent"
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
                    "default": 500.0
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
            },
            "required": [
                "control_zone_or_thermostat_location_name",
                "heating_coil_type"
            ]
        }
    },
    "group": "HVAC Templates",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "CompactHVACSystemUnitary",
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
            "control_zone_or_thermostat_location_name": {
                "field_name": "Control Zone or Thermostat Location Name",
                "field_type": "a"
            },
            "supply_fan_maximum_flow_rate": {
                "field_name": "Supply Fan Maximum Flow Rate",
                "field_type": "n"
            },
            "supply_fan_operating_mode_schedule_name": {
                "field_name": "Supply Fan Operating Mode Schedule Name",
                "field_type": "a"
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
            "cooling_coil_type": {
                "field_name": "Cooling Coil Type",
                "field_type": "a"
            },
            "cooling_coil_availability_schedule_name": {
                "field_name": "Cooling Coil Availability Schedule Name",
                "field_type": "a"
            },
            "cooling_design_supply_air_temperature": {
                "field_name": "Cooling Design Supply Air Temperature",
                "field_type": "n"
            },
            "cooling_coil_gross_rated_total_capacity": {
                "field_name": "Cooling Coil Gross Rated Total Capacity",
                "field_type": "n"
            },
            "cooling_coil_gross_rated_sensible_heat_ratio": {
                "field_name": "Cooling Coil Gross Rated Sensible Heat Ratio",
                "field_type": "n"
            },
            "cooling_coil_gross_rated_cop": {
                "field_name": "Cooling Coil Gross Rated COP",
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
            "heating_design_supply_air_temperature": {
                "field_name": "Heating Design Supply Air Temperature",
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
            "economizer_lockout": {
                "field_name": "Economizer Lockout",
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
            "supply_fan_placement": {
                "field_name": "Supply Fan Placement",
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
            "humidifier_control_zone_name": {
                "field_name": "Humidifier Control Zone Name",
                "field_type": "a"
            },
            "humidifier_setpoint": {
                "field_name": "Humidifier Setpoint",
                "field_type": "n"
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
            "control_zone_or_thermostat_location_name",
            "supply_fan_maximum_flow_rate",
            "supply_fan_operating_mode_schedule_name",
            "supply_fan_total_efficiency",
            "supply_fan_delta_pressure",
            "supply_fan_motor_efficiency",
            "supply_fan_motor_in_air_stream_fraction",
            "cooling_coil_type",
            "cooling_coil_availability_schedule_name",
            "cooling_design_supply_air_temperature",
            "cooling_coil_gross_rated_total_capacity",
            "cooling_coil_gross_rated_sensible_heat_ratio",
            "cooling_coil_gross_rated_cop",
            "heating_coil_type",
            "heating_coil_availability_schedule_name",
            "heating_design_supply_air_temperature",
            "heating_coil_capacity",
            "gas_heating_coil_efficiency",
            "gas_heating_coil_parasitic_electric_load",
            "maximum_outdoor_air_flow_rate",
            "minimum_outdoor_air_flow_rate",
            "minimum_outdoor_air_schedule_name",
            "economizer_type",
            "economizer_lockout",
            "economizer_upper_temperature_limit",
            "economizer_lower_temperature_limit",
            "economizer_upper_enthalpy_limit",
            "economizer_maximum_limit_dewpoint_temperature",
            "supply_plenum_name",
            "return_plenum_name",
            "supply_fan_placement",
            "night_cycle_control",
            "night_cycle_control_zone_name",
            "heat_recovery_type",
            "sensible_heat_recovery_effectiveness",
            "latent_heat_recovery_effectiveness",
            "dehumidification_control_type",
            "dehumidification_setpoint",
            "humidifier_type",
            "humidifier_availability_schedule_name",
            "humidifier_rated_capacity",
            "humidifier_rated_electric_power",
            "humidifier_control_zone_name",
            "humidifier_setpoint",
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
                "control_zone_or_thermostat_location_name",
                "supply_fan_operating_mode_schedule_name",
                "cooling_coil_type",
                "cooling_coil_availability_schedule_name",
                "heating_coil_type",
                "heating_coil_availability_schedule_name",
                "minimum_outdoor_air_schedule_name",
                "economizer_type",
                "economizer_lockout",
                "supply_plenum_name",
                "return_plenum_name",
                "supply_fan_placement",
                "night_cycle_control",
                "night_cycle_control_zone_name",
                "heat_recovery_type",
                "dehumidification_control_type",
                "humidifier_type",
                "humidifier_availability_schedule_name",
                "humidifier_control_zone_name",
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
                "cooling_design_supply_air_temperature",
                "cooling_coil_gross_rated_total_capacity",
                "cooling_coil_gross_rated_sensible_heat_ratio",
                "cooling_coil_gross_rated_cop",
                "heating_design_supply_air_temperature",
                "heating_coil_capacity",
                "gas_heating_coil_efficiency",
                "gas_heating_coil_parasitic_electric_load",
                "maximum_outdoor_air_flow_rate",
                "minimum_outdoor_air_flow_rate",
                "economizer_upper_temperature_limit",
                "economizer_lower_temperature_limit",
                "economizer_upper_enthalpy_limit",
                "economizer_maximum_limit_dewpoint_temperature",
                "sensible_heat_recovery_effectiveness",
                "latent_heat_recovery_effectiveness",
                "dehumidification_setpoint",
                "humidifier_rated_capacity",
                "humidifier_rated_electric_power",
                "humidifier_setpoint",
                "return_fan_total_efficiency",
                "return_fan_delta_pressure",
                "return_fan_motor_efficiency",
                "return_fan_motor_in_air_stream_fraction"
            ]
        }
    },
    "type": "object",
    "memo": "Unitary furnace with air conditioner",
    "min_fields": 51.0
}
```
