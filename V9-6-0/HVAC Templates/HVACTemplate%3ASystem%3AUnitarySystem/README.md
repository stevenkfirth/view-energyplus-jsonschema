```
{
    "HVACTemplate:System:UnitarySystem": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "system_availability_schedule_name": {
                        "type": "string",
                        "note": "If blank, always available. Also see Supply Fan Operating Mode Schedule Name field.",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "control_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "Load",
                            "SetPoint"
                        ],
                        "default": "Load",
                        "note": "Load control requires a Controlling Zone name. SetPoint control requires set points at coil outlet nodes. The user must add appropriate SetpointManager objects to the idf file."
                    },
                    "control_zone_or_thermostat_location_name": {
                        "type": "string",
                        "note": "This field is required if Control Type is Load.",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ]
                    },
                    "cooling_supply_air_flow_rate": {
                        "note": "Supply air flow rate during cooling operation This field may be set to \"autosize\". If a value is entered, it will *not* be multiplied by any sizing factor or by zone multipliers. If using zone multipliers a value entered here must be large enough to serve the multiplied zones.",
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
                    "heating_supply_air_flow_rate": {
                        "note": "Supply air flow rate during heating operation This field may be set to \"autosize\". If a value is entered, it will *not* be multiplied by any sizing factor or by zone multipliers. If using zone multipliers a value entered here must be large enough to serve the multiplied zones.",
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
                    "no_load_supply_air_flow_rate": {
                        "note": "Supply air flow rate when no cooling or heating is needed Only used when heat pump fan operating mode is Continuous. This air flow rate is used when no heating or cooling is required and the DX coil compressor is off. If this field is left blank or zero, the supply air flow rate from the previous on cycle (either cooling or heating) is used. This field may be set to \"autosize\". If a value is entered, it will *not* be multiplied by any sizing factor or by zone multipliers. If using zone multipliers a value entered here must be large enough to serve the multiplied zones.",
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
                    "supply_fan_operating_mode_schedule_name": {
                        "type": "string",
                        "note": "Refers to a schedule to specify unitary supply fan operating mode. Schedule values of 0 indicate cycling fan (auto) Schedule values of 1 indicate continuous fan (on) If this field is left blank, a schedule of always zero (cycling fan) will be used.",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
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
                            "ChilledWater",
                            "ChilledWaterDetailedFlatModel",
                            "HeatExchangerAssistedChilledWater",
                            "HeatExchangerAssistedDX",
                            "MultiSpeedDX",
                            "None",
                            "SingleSpeedDX",
                            "SingleSpeedDXWaterCooled",
                            "TwoSpeedDX",
                            "TwoStageDX",
                            "TwoStageHumidityControlDX"
                        ],
                        "default": "SingleSpeedDX"
                    },
                    "number_of_speeds_for_cooling": {
                        "type": "number",
                        "note": "Used only for Cooling Coil Type = MultiSpeedDX.",
                        "minimum": 0.0,
                        "maximum": 4.0,
                        "default": 1.0
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
                    "dx_cooling_coil_gross_rated_total_capacity": {
                        "note": "Total cooling capacity not accounting for the effect of supply air fan heat Rating point: air entering the cooling coil at 26.7 C dry-bulb/19.4 C wet-bulb, and air entering the outdoor condenser coil at 35 C dry-bulb/23.9 C wet-bulb",
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
                        "note": "Rated sensible heat ratio (gross sensible capacity/gross total capacity) Sensible and total capacities do not include effect of supply fan heat",
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
                        "note": "Gross cooling capacity divided by power input to the compressor and outdoor fan, does not include supply fan heat or supply fan electric power input",
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
                            "MultiSpeedDXHeatPumpAirSource",
                            "MultiStageElectric",
                            "MultiStageGas",
                            "None",
                            "SingleSpeedDXHeatPumpAirSource",
                            "SingleSpeedDXHeatPumpWaterSource"
                        ],
                        "default": "Gas"
                    },
                    "number_of_speeds_or_stages_for_heating": {
                        "type": "number",
                        "note": "Used only for Heating Coil Type = MultiSpeedDXHeatPumpAirSource), MultiStageElectric, or MultiStageGas.",
                        "minimum": 0.0,
                        "maximum": 4.0,
                        "default": 1.0
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
                    "heating_coil_gross_rated_capacity": {
                        "note": "Rated heating capacity excluding the effect of supply air fan heat Rating point outdoor dry-bulb temp 8.33 C, outdoor wet-bulb temp 6.11 C Rating point heating coil entering air dry-bulb 21.11 C, coil entering wet-bulb 15.55 C",
                        "units": "W",
                        "default": "Autosize",
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
                    "heat_pump_heating_coil_gross_rated_cop": {
                        "type": "number",
                        "note": "Heating Coil Rated Capacity divided by power input to the compressor and outdoor fan, does not include supply air fan heat or supply air fan electrical energy. Rating point outdoor dry-bulb temp 8.33 C, outdoor wet-bulb temp 6.11 C Rating point heating coil entering air dry-bulb 21.11 C, coil entering wet-bulb 15.55 C Applies only to DX coils",
                        "units": "W/W",
                        "exclusiveMinimum": 0.0,
                        "default": 2.75
                    },
                    "heat_pump_heating_minimum_outdoor_dry_bulb_temperature": {
                        "type": "number",
                        "minimum": -20.0,
                        "default": -8.0,
                        "units": "C"
                    },
                    "heat_pump_defrost_maximum_outdoor_dry_bulb_temperature": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 7.22,
                        "default": 5.0,
                        "units": "C"
                    },
                    "heat_pump_defrost_strategy": {
                        "type": "string",
                        "enum": [
                            "",
                            "Resistive",
                            "ReverseCycle"
                        ],
                        "default": "ReverseCycle"
                    },
                    "heat_pump_defrost_control": {
                        "type": "string",
                        "enum": [
                            "",
                            "OnDemand",
                            "Timed"
                        ],
                        "default": "Timed"
                    },
                    "heat_pump_defrost_time_period_fraction": {
                        "type": "number",
                        "minimum": 0.0,
                        "default": 0.058333,
                        "note": "Fraction of time in defrost mode only applicable if Timed defrost control is specified"
                    },
                    "supplemental_heating_or_reheat_coil_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "DesuperHeater",
                            "Electric",
                            "Gas",
                            "HotWater",
                            "None"
                        ],
                        "default": "None"
                    },
                    "supplemental_heating_or_reheat_coil_availability_schedule_name": {
                        "type": "string",
                        "note": "If blank, always on",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "supplemental_heating_or_reheat_coil_capacity": {
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
                    "supplemental_heating_or_reheat_coil_maximum_outdoor_dry_bulb_temperature": {
                        "type": "number",
                        "maximum": 21.0,
                        "default": 21.0,
                        "units": "C",
                        "note": "Supplemental heater will not operate when outdoor temperature exceeds this value."
                    },
                    "supplemental_gas_heating_or_reheat_coil_efficiency": {
                        "type": "number",
                        "note": "Applies only if Supplemental Heating Coil Type is Gas",
                        "maximum": 1.0,
                        "minimum": 0.0,
                        "default": 0.8
                    },
                    "supplemental_gas_heating_or_reheat_coil_parasitic_electric_load": {
                        "type": "number",
                        "note": "Applies only if Supplemental Heating Coil Type is Gas",
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
                        "note": "Schedule values multiply the minimum outdoor air flow rate If blank, multiplier is always one",
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
                    "economizer_maximum_limit_dry_bulb_temperature": {
                        "type": "number",
                        "units": "C",
                        "note": "Enter the maximum outdoor dry-bulb temperature limit for FixedDryBulb economizer control type. No input or blank input means this limit is not operative. Limit is applied regardless of economizer control type."
                    },
                    "economizer_maximum_limit_enthalpy": {
                        "type": "number",
                        "units": "J/kg",
                        "note": "Enter the maximum outdoor enthalpy limit for FixedEnthalpy economizer control type. No input or blank input means this limit is not operative Limit is applied regardless of economizer control type."
                    },
                    "economizer_maximum_limit_dewpoint_temperature": {
                        "type": "number",
                        "units": "C",
                        "note": "Enter the maximum outdoor dewpoint temperature limit for FixedDewPointAndDryBulb economizer control type. No input or blank input means this limit is not operative. Limit is applied regardless of economizer control type."
                    },
                    "economizer_minimum_limit_dry_bulb_temperature": {
                        "type": "number",
                        "units": "C",
                        "note": "Enter the minimum outdoor dry-bulb temperature limit for economizer control. No input or blank input means this limit is not operative Limit is applied regardless of economizer control type."
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
                        "note": "None = meet sensible load only CoolReheat = cool beyond the dry-bulb setpoint, reheat with reheat coil If no reheat coil specified, cold supply temps may occur. Multimode = activate enhanced dehumidification mode as needed and meet sensible load. Valid only for Cooling Coil Type = TwoStageHumidityControlDX or HeatExchangerAssistedDX",
                        "enum": [
                            "",
                            "CoolReheat",
                            "Multimode",
                            "None"
                        ],
                        "default": "None"
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
                    "sizing_option": {
                        "type": "string",
                        "note": "Select whether autosized system supply flow rate is the sum of Coincident or NonCoincident zone air flow rates.",
                        "enum": [
                            "",
                            "Coincident",
                            "NonCoincident"
                        ],
                        "default": "NonCoincident"
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
                "control_type": {
                    "field_name": "Control Type",
                    "field_type": "a"
                },
                "control_zone_or_thermostat_location_name": {
                    "field_name": "Control Zone or Thermostat Location Name",
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
                "supply_fan_operating_mode_schedule_name": {
                    "field_name": "Supply Fan Operating Mode Schedule Name",
                    "field_type": "a"
                },
                "supply_fan_placement": {
                    "field_name": "Supply Fan Placement",
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
                "number_of_speeds_for_cooling": {
                    "field_name": "Number of Speeds for Cooling",
                    "field_type": "n"
                },
                "cooling_coil_availability_schedule_name": {
                    "field_name": "Cooling Coil Availability Schedule Name",
                    "field_type": "a"
                },
                "cooling_design_supply_air_temperature": {
                    "field_name": "Cooling Design Supply Air Temperature",
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
                "number_of_speeds_or_stages_for_heating": {
                    "field_name": "Number of Speeds or Stages for Heating",
                    "field_type": "n"
                },
                "heating_coil_availability_schedule_name": {
                    "field_name": "Heating Coil Availability Schedule Name",
                    "field_type": "a"
                },
                "heating_design_supply_air_temperature": {
                    "field_name": "Heating Design Supply Air Temperature",
                    "field_type": "n"
                },
                "heating_coil_gross_rated_capacity": {
                    "field_name": "Heating Coil Gross Rated Capacity",
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
                "heat_pump_heating_coil_gross_rated_cop": {
                    "field_name": "Heat Pump Heating Coil Gross Rated COP",
                    "field_type": "n"
                },
                "heat_pump_heating_minimum_outdoor_dry_bulb_temperature": {
                    "field_name": "Heat Pump Heating Minimum Outdoor Dry-Bulb Temperature",
                    "field_type": "n"
                },
                "heat_pump_defrost_maximum_outdoor_dry_bulb_temperature": {
                    "field_name": "Heat Pump Defrost Maximum Outdoor Dry-Bulb Temperature",
                    "field_type": "n"
                },
                "heat_pump_defrost_strategy": {
                    "field_name": "Heat Pump Defrost Strategy",
                    "field_type": "a"
                },
                "heat_pump_defrost_control": {
                    "field_name": "Heat Pump Defrost Control",
                    "field_type": "a"
                },
                "heat_pump_defrost_time_period_fraction": {
                    "field_name": "Heat Pump Defrost Time Period Fraction",
                    "field_type": "n"
                },
                "supplemental_heating_or_reheat_coil_type": {
                    "field_name": "Supplemental Heating or Reheat Coil Type",
                    "field_type": "a"
                },
                "supplemental_heating_or_reheat_coil_availability_schedule_name": {
                    "field_name": "Supplemental Heating or Reheat Coil Availability Schedule Name",
                    "field_type": "a"
                },
                "supplemental_heating_or_reheat_coil_capacity": {
                    "field_name": "Supplemental Heating or Reheat Coil Capacity",
                    "field_type": "n"
                },
                "supplemental_heating_or_reheat_coil_maximum_outdoor_dry_bulb_temperature": {
                    "field_name": "Supplemental Heating or Reheat Coil Maximum Outdoor Dry-Bulb Temperature",
                    "field_type": "n"
                },
                "supplemental_gas_heating_or_reheat_coil_efficiency": {
                    "field_name": "Supplemental Gas Heating or Reheat Coil Efficiency",
                    "field_type": "n"
                },
                "supplemental_gas_heating_or_reheat_coil_parasitic_electric_load": {
                    "field_name": "Supplemental Gas Heating or Reheat Coil Parasitic Electric Load",
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
                "economizer_maximum_limit_dry_bulb_temperature": {
                    "field_name": "Economizer Maximum Limit Dry-Bulb Temperature",
                    "field_type": "n"
                },
                "economizer_maximum_limit_enthalpy": {
                    "field_name": "Economizer Maximum Limit Enthalpy",
                    "field_type": "n"
                },
                "economizer_maximum_limit_dewpoint_temperature": {
                    "field_name": "Economizer Maximum Limit Dewpoint Temperature",
                    "field_type": "n"
                },
                "economizer_minimum_limit_dry_bulb_temperature": {
                    "field_name": "Economizer Minimum Limit Dry-Bulb Temperature",
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
                "sizing_option": {
                    "field_name": "Sizing Option",
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
                "control_type",
                "control_zone_or_thermostat_location_name",
                "cooling_supply_air_flow_rate",
                "heating_supply_air_flow_rate",
                "no_load_supply_air_flow_rate",
                "supply_fan_operating_mode_schedule_name",
                "supply_fan_placement",
                "supply_fan_total_efficiency",
                "supply_fan_delta_pressure",
                "supply_fan_motor_efficiency",
                "supply_fan_motor_in_air_stream_fraction",
                "cooling_coil_type",
                "number_of_speeds_for_cooling",
                "cooling_coil_availability_schedule_name",
                "cooling_design_supply_air_temperature",
                "dx_cooling_coil_gross_rated_total_capacity",
                "dx_cooling_coil_gross_rated_sensible_heat_ratio",
                "dx_cooling_coil_gross_rated_cop",
                "heating_coil_type",
                "number_of_speeds_or_stages_for_heating",
                "heating_coil_availability_schedule_name",
                "heating_design_supply_air_temperature",
                "heating_coil_gross_rated_capacity",
                "gas_heating_coil_efficiency",
                "gas_heating_coil_parasitic_electric_load",
                "heat_pump_heating_coil_gross_rated_cop",
                "heat_pump_heating_minimum_outdoor_dry_bulb_temperature",
                "heat_pump_defrost_maximum_outdoor_dry_bulb_temperature",
                "heat_pump_defrost_strategy",
                "heat_pump_defrost_control",
                "heat_pump_defrost_time_period_fraction",
                "supplemental_heating_or_reheat_coil_type",
                "supplemental_heating_or_reheat_coil_availability_schedule_name",
                "supplemental_heating_or_reheat_coil_capacity",
                "supplemental_heating_or_reheat_coil_maximum_outdoor_dry_bulb_temperature",
                "supplemental_gas_heating_or_reheat_coil_efficiency",
                "supplemental_gas_heating_or_reheat_coil_parasitic_electric_load",
                "maximum_outdoor_air_flow_rate",
                "minimum_outdoor_air_flow_rate",
                "minimum_outdoor_air_schedule_name",
                "economizer_type",
                "economizer_lockout",
                "economizer_maximum_limit_dry_bulb_temperature",
                "economizer_maximum_limit_enthalpy",
                "economizer_maximum_limit_dewpoint_temperature",
                "economizer_minimum_limit_dry_bulb_temperature",
                "supply_plenum_name",
                "return_plenum_name",
                "heat_recovery_type",
                "sensible_heat_recovery_effectiveness",
                "latent_heat_recovery_effectiveness",
                "heat_recovery_heat_exchanger_type",
                "heat_recovery_frost_control_type",
                "dehumidification_control_type",
                "dehumidification_relative_humidity_setpoint",
                "dehumidification_relative_humidity_setpoint_schedule_name",
                "humidifier_type",
                "humidifier_availability_schedule_name",
                "humidifier_rated_capacity",
                "humidifier_rated_electric_power",
                "humidifier_control_zone_name",
                "humidifier_relative_humidity_setpoint",
                "humidifier_relative_humidity_setpoint_schedule_name",
                "sizing_option",
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
                    "control_type",
                    "control_zone_or_thermostat_location_name",
                    "supply_fan_operating_mode_schedule_name",
                    "supply_fan_placement",
                    "cooling_coil_type",
                    "cooling_coil_availability_schedule_name",
                    "heating_coil_type",
                    "heating_coil_availability_schedule_name",
                    "heat_pump_defrost_strategy",
                    "heat_pump_defrost_control",
                    "supplemental_heating_or_reheat_coil_type",
                    "supplemental_heating_or_reheat_coil_availability_schedule_name",
                    "minimum_outdoor_air_schedule_name",
                    "economizer_type",
                    "economizer_lockout",
                    "supply_plenum_name",
                    "return_plenum_name",
                    "heat_recovery_type",
                    "heat_recovery_heat_exchanger_type",
                    "heat_recovery_frost_control_type",
                    "dehumidification_control_type",
                    "dehumidification_relative_humidity_setpoint_schedule_name",
                    "humidifier_type",
                    "humidifier_availability_schedule_name",
                    "humidifier_control_zone_name",
                    "humidifier_relative_humidity_setpoint_schedule_name",
                    "sizing_option",
                    "return_fan"
                ]
            },
            "numerics": {
                "fields": [
                    "cooling_supply_air_flow_rate",
                    "heating_supply_air_flow_rate",
                    "no_load_supply_air_flow_rate",
                    "supply_fan_total_efficiency",
                    "supply_fan_delta_pressure",
                    "supply_fan_motor_efficiency",
                    "supply_fan_motor_in_air_stream_fraction",
                    "number_of_speeds_for_cooling",
                    "cooling_design_supply_air_temperature",
                    "dx_cooling_coil_gross_rated_total_capacity",
                    "dx_cooling_coil_gross_rated_sensible_heat_ratio",
                    "dx_cooling_coil_gross_rated_cop",
                    "number_of_speeds_or_stages_for_heating",
                    "heating_design_supply_air_temperature",
                    "heating_coil_gross_rated_capacity",
                    "gas_heating_coil_efficiency",
                    "gas_heating_coil_parasitic_electric_load",
                    "heat_pump_heating_coil_gross_rated_cop",
                    "heat_pump_heating_minimum_outdoor_dry_bulb_temperature",
                    "heat_pump_defrost_maximum_outdoor_dry_bulb_temperature",
                    "heat_pump_defrost_time_period_fraction",
                    "supplemental_heating_or_reheat_coil_capacity",
                    "supplemental_heating_or_reheat_coil_maximum_outdoor_dry_bulb_temperature",
                    "supplemental_gas_heating_or_reheat_coil_efficiency",
                    "supplemental_gas_heating_or_reheat_coil_parasitic_electric_load",
                    "maximum_outdoor_air_flow_rate",
                    "minimum_outdoor_air_flow_rate",
                    "economizer_maximum_limit_dry_bulb_temperature",
                    "economizer_maximum_limit_enthalpy",
                    "economizer_maximum_limit_dewpoint_temperature",
                    "economizer_minimum_limit_dry_bulb_temperature",
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
        "memo": "Unitary HVAC system with optional cooling and heating. Supports DX and chilled water, cooling, gas, electric, and hot water heating, air-to-air and water-to-air heat pumps.",
        "min_fields": 71.0
    }
}
```
