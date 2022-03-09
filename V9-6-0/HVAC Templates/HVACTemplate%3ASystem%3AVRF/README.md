```
{
    "HVACTemplate:System:VRF": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "system_availability_schedule_name": {
                        "type": "string",
                        "note": "Availability schedule name for this system. Schedule value > 0 means the system is available. If this field is blank, the system is always available.",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "gross_rated_total_cooling_capacity": {
                        "units": "W",
                        "default": "Autosize",
                        "note": "Enter the total cooling capacity in watts at rated conditions or set to autosize. Total cooling capacity not accounting for the effect of supply air fan heat",
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
                    "gross_rated_cooling_cop": {
                        "type": "number",
                        "units": "W/W",
                        "exclusiveMinimum": 0.0,
                        "default": 3.3,
                        "note": "Enter the coefficient of performance at rated conditions or leave blank to use default. COP includes compressor and condenser fan electrical energy input COP does not include supply fan heat or supply fan electric power input"
                    },
                    "minimum_outdoor_temperature_in_cooling_mode": {
                        "type": "number",
                        "units": "C",
                        "default": -6.0,
                        "note": "Enter the minimum outdoor temperature allowed for cooling operation. Cooling is disabled below this temperature."
                    },
                    "maximum_outdoor_temperature_in_cooling_mode": {
                        "type": "number",
                        "units": "C",
                        "default": 43.0,
                        "note": "Enter the maximum outdoor temperature allowed for cooling operation. Cooling is disabled above this temperature."
                    },
                    "gross_rated_heating_capacity": {
                        "units": "W",
                        "default": "Autosize",
                        "note": "Enter the heating capacity in watts at rated conditions or set to autosize. Heating capacity not accounting for the effect of supply air fan heat",
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
                    "rated_heating_capacity_sizing_ratio": {
                        "type": "number",
                        "units": "W/W",
                        "minimum": 1.0,
                        "default": 1.0,
                        "note": "If the Gross Rated Heating Capacity is autosized, the heating capacity is sized to be equal to the cooling capacity multiplied by this sizing ratio. The zone terminal unit heating coils are also sized using this ratio unless the sizing ratio input in the ZoneHVAC:TerminalUnit:VariableRefrigerantFlow object is entered."
                    },
                    "gross_rated_heating_cop": {
                        "type": "number",
                        "units": "W/W",
                        "exclusiveMinimum": 0.0,
                        "note": "COP includes compressor and condenser fan electrical energy input COP does not include supply fan heat or supply fan electrical energy input",
                        "default": 3.4
                    },
                    "minimum_outdoor_temperature_in_heating_mode": {
                        "type": "number",
                        "units": "C",
                        "default": -20.0,
                        "note": "Enter the minimum outdoor temperature allowed for heating operation."
                    },
                    "maximum_outdoor_temperature_in_heating_mode": {
                        "type": "number",
                        "units": "C",
                        "default": 16.0,
                        "note": "Enter the maximum outdoor temperature allowed for heating operation."
                    },
                    "minimum_heat_pump_part_load_ratio": {
                        "type": "number",
                        "units": "dimensionless",
                        "note": "Enter the minimum heat pump part-load ratio (PLR). When the cooling or heating PLR is below this value, the heat pump compressor will cycle to meet the cooling or heating demand.",
                        "default": 0.15
                    },
                    "zone_name_for_master_thermostat_location": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ],
                        "note": "Enter the name of the zone where the master thermostat is located."
                    },
                    "master_thermostat_priority_control_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "LoadPriority",
                            "MasterThermostatPriority",
                            "Scheduled",
                            "ThermostatOffsetPriority",
                            "ZonePriority"
                        ],
                        "default": "MasterThermostatPriority",
                        "note": "Choose a thermostat control logic scheme. If these control types fail to control zone temperature within a reasonable limit, consider using multiple VRF systems"
                    },
                    "thermostat_priority_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "this field is required if Master Thermostat Priority Control Type is Scheduled. Schedule values of 0 denote cooling, 1 for heating, and all other values disable the system."
                    },
                    "heat_pump_waste_heat_recovery": {
                        "type": "string",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "No",
                        "note": "This field is reserved for future use. The only valid choice is No."
                    },
                    "equivalent_piping_length_used_for_piping_correction_factor_in_cooling_mode": {
                        "type": "number",
                        "units": "m",
                        "default": 30.0,
                        "note": "Enter the equivalent length of the farthest terminal unit from the condenser"
                    },
                    "vertical_height_used_for_piping_correction_factor": {
                        "type": "number",
                        "units": "m",
                        "default": 10.0,
                        "note": "Enter the height difference between the highest and lowest terminal unit"
                    },
                    "equivalent_piping_length_used_for_piping_correction_factor_in_heating_mode": {
                        "type": "number",
                        "units": "m",
                        "default": 30.0,
                        "note": "Enter the equivalent length of the farthest terminal unit from the condenser"
                    },
                    "crankcase_heater_power_per_compressor": {
                        "type": "number",
                        "units": "W",
                        "default": 33.0,
                        "note": "Enter the value of the resistive heater located in the compressor(s). This heater is used to warm the refrigerant and oil when the compressor is off."
                    },
                    "number_of_compressors": {
                        "type": "number",
                        "units": "dimensionless",
                        "default": 2.0,
                        "note": "Enter the total number of compressor. This input is used only for crankcase heater calculations."
                    },
                    "ratio_of_compressor_size_to_total_compressor_capacity": {
                        "type": "number",
                        "units": "W/W",
                        "default": 0.5,
                        "note": "Enter the ratio of the first stage compressor to total compressor capacity. All other compressors are assumed to be equally sized. This inputs is used only for crankcase heater calculations."
                    },
                    "maximum_outdoor_dry_bulb_temperature_for_crankcase_heater": {
                        "type": "number",
                        "units": "C",
                        "default": 5.0,
                        "note": "Enter the maximum outdoor temperature above which the crankcase heaters are disabled."
                    },
                    "defrost_strategy": {
                        "type": "string",
                        "enum": [
                            "",
                            "Resistive",
                            "ReverseCycle"
                        ],
                        "default": "Resistive",
                        "note": "Select a defrost strategy. Reverse cycle reverses the operating mode from heating to cooling to melt frost formation on the condenser coil. The resistive strategy uses a resistive heater to melt the frost."
                    },
                    "defrost_control": {
                        "type": "string",
                        "enum": [
                            "",
                            "OnDemand",
                            "Timed"
                        ],
                        "default": "Timed",
                        "note": "Choose a defrost control type. Either use a fixed Timed defrost period or select OnDemand to defrost only when necessary."
                    },
                    "defrost_time_period_fraction": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "default": 0.058333,
                        "note": "Fraction of time in defrost mode. Only applicable if timed defrost control is specified."
                    },
                    "resistive_defrost_heater_capacity": {
                        "units": "W",
                        "default": "Autosize",
                        "note": "Enter the size of the resistive defrost heating element. Only applicable if resistive defrost strategy is specified",
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
                    "maximum_outdoor_dry_bulb_temperature_for_defrost_operation": {
                        "type": "number",
                        "units": "C",
                        "default": 5.0,
                        "note": "Enter the maximum outdoor temperature above which defrost operation is disabled."
                    },
                    "condenser_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "AirCooled",
                            "EvaporativelyCooled",
                            "WaterCooled"
                        ],
                        "default": "AirCooled",
                        "note": "Select either an air cooled or evaporatively cooled condenser."
                    },
                    "water_condenser_volume_flow_rate": {
                        "units": "m3/s",
                        "default": "Autosize",
                        "note": "Only used when Condenser Type = WaterCooled.",
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
                    "evaporative_condenser_effectiveness": {
                        "type": "number",
                        "units": "dimensionless",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "default": 0.9,
                        "note": "Enter the effectiveness of the evaporatively cooled condenser. This field is only used when the Condenser Type = EvaporativelyCooled."
                    },
                    "evaporative_condenser_air_flow_rate": {
                        "units": "m3/s",
                        "default": "Autosize",
                        "note": "Used to calculate evaporative condenser water use. This field is only used when the Condenser Type = EvaporativelyCooled.",
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
                    "evaporative_condenser_pump_rated_power_consumption": {
                        "units": "W",
                        "default": 0.0,
                        "note": "Rated power consumed by the evaporative condenser's water pump. This field is only used when the Condenser Type = EvaporativelyCooled.",
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
                    "basin_heater_capacity": {
                        "type": "number",
                        "units": "W/K",
                        "minimum": 0.0,
                        "default": 0.0,
                        "note": "This field is only used for Condenser Type = EvaporativelyCooled and for periods when the basin heater is available (field Basin Heater Operating Schedule Name). For this situation, the heater maintains the basin water temperature at the basin heater setpoint temperature when the outdoor air temperature falls below the setpoint temperature. The basin heater only operates when the DX coil is off."
                    },
                    "basin_heater_setpoint_temperature": {
                        "type": "number",
                        "units": "C",
                        "minimum": 2.0,
                        "default": 2.0,
                        "note": "This field is only used for Condenser Type = EvaporativelyCooled. Enter the outdoor dry-bulb temperature when the basin heater turns on."
                    },
                    "basin_heater_operating_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "This field is only used for Condenser Type = EvaporativelyCooled. Schedule values greater than 0 allow the basin heater to operate whenever the outdoor air dry-bulb temperature is below the basin heater setpoint temperature. If a schedule name is not entered, the basin heater is allowed to operate throughout the entire simulation."
                    },
                    "fuel_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "Diesel",
                            "Electricity",
                            "FuelOilNo1",
                            "FuelOilNo2",
                            "Gasoline",
                            "NaturalGas",
                            "OtherFuel1",
                            "OtherFuel2",
                            "Propane"
                        ],
                        "default": "Electricity"
                    },
                    "minimum_outdoor_temperature_in_heat_recovery_mode": {
                        "type": "number",
                        "units": "C",
                        "note": "The minimum outdoor temperature below which heat recovery mode will not operate.",
                        "default": -15.0
                    },
                    "maximum_outdoor_temperature_in_heat_recovery_mode": {
                        "type": "number",
                        "units": "C",
                        "note": "The maximum outdoor temperature above which heat recovery mode will not operate.",
                        "default": 45.0
                    }
                }
            }
        },
        "group": "HVAC Templates",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "CompactHVACSystemVRF",
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
                "gross_rated_total_cooling_capacity": {
                    "field_name": "Gross Rated Total Cooling Capacity",
                    "field_type": "n"
                },
                "gross_rated_cooling_cop": {
                    "field_name": "Gross Rated Cooling COP",
                    "field_type": "n"
                },
                "minimum_outdoor_temperature_in_cooling_mode": {
                    "field_name": "Minimum Outdoor Temperature in Cooling Mode",
                    "field_type": "n"
                },
                "maximum_outdoor_temperature_in_cooling_mode": {
                    "field_name": "Maximum Outdoor Temperature in Cooling Mode",
                    "field_type": "n"
                },
                "gross_rated_heating_capacity": {
                    "field_name": "Gross Rated Heating Capacity",
                    "field_type": "n"
                },
                "rated_heating_capacity_sizing_ratio": {
                    "field_name": "Rated Heating Capacity Sizing Ratio",
                    "field_type": "n"
                },
                "gross_rated_heating_cop": {
                    "field_name": "Gross Rated Heating COP",
                    "field_type": "n"
                },
                "minimum_outdoor_temperature_in_heating_mode": {
                    "field_name": "Minimum Outdoor Temperature in Heating Mode",
                    "field_type": "n"
                },
                "maximum_outdoor_temperature_in_heating_mode": {
                    "field_name": "Maximum Outdoor Temperature in Heating Mode",
                    "field_type": "n"
                },
                "minimum_heat_pump_part_load_ratio": {
                    "field_name": "Minimum Heat Pump Part-Load Ratio",
                    "field_type": "n"
                },
                "zone_name_for_master_thermostat_location": {
                    "field_name": "Zone Name for Master Thermostat Location",
                    "field_type": "a"
                },
                "master_thermostat_priority_control_type": {
                    "field_name": "Master Thermostat Priority Control Type",
                    "field_type": "a"
                },
                "thermostat_priority_schedule_name": {
                    "field_name": "Thermostat Priority Schedule Name",
                    "field_type": "a"
                },
                "heat_pump_waste_heat_recovery": {
                    "field_name": "Heat Pump Waste Heat Recovery",
                    "field_type": "a"
                },
                "equivalent_piping_length_used_for_piping_correction_factor_in_cooling_mode": {
                    "field_name": "Equivalent Piping Length used for Piping Correction Factor in Cooling Mode",
                    "field_type": "n"
                },
                "vertical_height_used_for_piping_correction_factor": {
                    "field_name": "Vertical Height used for Piping Correction Factor",
                    "field_type": "n"
                },
                "equivalent_piping_length_used_for_piping_correction_factor_in_heating_mode": {
                    "field_name": "Equivalent Piping Length used for Piping Correction Factor in Heating Mode",
                    "field_type": "n"
                },
                "crankcase_heater_power_per_compressor": {
                    "field_name": "Crankcase Heater Power per Compressor",
                    "field_type": "n"
                },
                "number_of_compressors": {
                    "field_name": "Number of Compressors",
                    "field_type": "n"
                },
                "ratio_of_compressor_size_to_total_compressor_capacity": {
                    "field_name": "Ratio of Compressor Size to Total Compressor Capacity",
                    "field_type": "n"
                },
                "maximum_outdoor_dry_bulb_temperature_for_crankcase_heater": {
                    "field_name": "Maximum Outdoor Dry-bulb Temperature for Crankcase Heater",
                    "field_type": "n"
                },
                "defrost_strategy": {
                    "field_name": "Defrost Strategy",
                    "field_type": "a"
                },
                "defrost_control": {
                    "field_name": "Defrost Control",
                    "field_type": "a"
                },
                "defrost_time_period_fraction": {
                    "field_name": "Defrost Time Period Fraction",
                    "field_type": "n"
                },
                "resistive_defrost_heater_capacity": {
                    "field_name": "Resistive Defrost Heater Capacity",
                    "field_type": "n"
                },
                "maximum_outdoor_dry_bulb_temperature_for_defrost_operation": {
                    "field_name": "Maximum Outdoor Dry-bulb Temperature for Defrost Operation",
                    "field_type": "n"
                },
                "condenser_type": {
                    "field_name": "Condenser Type",
                    "field_type": "a"
                },
                "water_condenser_volume_flow_rate": {
                    "field_name": "Water Condenser Volume Flow Rate",
                    "field_type": "n"
                },
                "evaporative_condenser_effectiveness": {
                    "field_name": "Evaporative Condenser Effectiveness",
                    "field_type": "n"
                },
                "evaporative_condenser_air_flow_rate": {
                    "field_name": "Evaporative Condenser Air Flow Rate",
                    "field_type": "n"
                },
                "evaporative_condenser_pump_rated_power_consumption": {
                    "field_name": "Evaporative Condenser Pump Rated Power Consumption",
                    "field_type": "n"
                },
                "basin_heater_capacity": {
                    "field_name": "Basin Heater Capacity",
                    "field_type": "n"
                },
                "basin_heater_setpoint_temperature": {
                    "field_name": "Basin Heater Setpoint Temperature",
                    "field_type": "n"
                },
                "basin_heater_operating_schedule_name": {
                    "field_name": "Basin Heater Operating Schedule Name",
                    "field_type": "a"
                },
                "fuel_type": {
                    "field_name": "Fuel Type",
                    "field_type": "a"
                },
                "minimum_outdoor_temperature_in_heat_recovery_mode": {
                    "field_name": "Minimum Outdoor Temperature in Heat Recovery Mode",
                    "field_type": "n"
                },
                "maximum_outdoor_temperature_in_heat_recovery_mode": {
                    "field_name": "Maximum Outdoor Temperature in Heat Recovery Mode",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "system_availability_schedule_name",
                "gross_rated_total_cooling_capacity",
                "gross_rated_cooling_cop",
                "minimum_outdoor_temperature_in_cooling_mode",
                "maximum_outdoor_temperature_in_cooling_mode",
                "gross_rated_heating_capacity",
                "rated_heating_capacity_sizing_ratio",
                "gross_rated_heating_cop",
                "minimum_outdoor_temperature_in_heating_mode",
                "maximum_outdoor_temperature_in_heating_mode",
                "minimum_heat_pump_part_load_ratio",
                "zone_name_for_master_thermostat_location",
                "master_thermostat_priority_control_type",
                "thermostat_priority_schedule_name",
                "heat_pump_waste_heat_recovery",
                "equivalent_piping_length_used_for_piping_correction_factor_in_cooling_mode",
                "vertical_height_used_for_piping_correction_factor",
                "equivalent_piping_length_used_for_piping_correction_factor_in_heating_mode",
                "crankcase_heater_power_per_compressor",
                "number_of_compressors",
                "ratio_of_compressor_size_to_total_compressor_capacity",
                "maximum_outdoor_dry_bulb_temperature_for_crankcase_heater",
                "defrost_strategy",
                "defrost_control",
                "defrost_time_period_fraction",
                "resistive_defrost_heater_capacity",
                "maximum_outdoor_dry_bulb_temperature_for_defrost_operation",
                "condenser_type",
                "water_condenser_volume_flow_rate",
                "evaporative_condenser_effectiveness",
                "evaporative_condenser_air_flow_rate",
                "evaporative_condenser_pump_rated_power_consumption",
                "basin_heater_capacity",
                "basin_heater_setpoint_temperature",
                "basin_heater_operating_schedule_name",
                "fuel_type",
                "minimum_outdoor_temperature_in_heat_recovery_mode",
                "maximum_outdoor_temperature_in_heat_recovery_mode"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "system_availability_schedule_name",
                    "zone_name_for_master_thermostat_location",
                    "master_thermostat_priority_control_type",
                    "thermostat_priority_schedule_name",
                    "heat_pump_waste_heat_recovery",
                    "defrost_strategy",
                    "defrost_control",
                    "condenser_type",
                    "basin_heater_operating_schedule_name",
                    "fuel_type"
                ]
            },
            "numerics": {
                "fields": [
                    "gross_rated_total_cooling_capacity",
                    "gross_rated_cooling_cop",
                    "minimum_outdoor_temperature_in_cooling_mode",
                    "maximum_outdoor_temperature_in_cooling_mode",
                    "gross_rated_heating_capacity",
                    "rated_heating_capacity_sizing_ratio",
                    "gross_rated_heating_cop",
                    "minimum_outdoor_temperature_in_heating_mode",
                    "maximum_outdoor_temperature_in_heating_mode",
                    "minimum_heat_pump_part_load_ratio",
                    "equivalent_piping_length_used_for_piping_correction_factor_in_cooling_mode",
                    "vertical_height_used_for_piping_correction_factor",
                    "equivalent_piping_length_used_for_piping_correction_factor_in_heating_mode",
                    "crankcase_heater_power_per_compressor",
                    "number_of_compressors",
                    "ratio_of_compressor_size_to_total_compressor_capacity",
                    "maximum_outdoor_dry_bulb_temperature_for_crankcase_heater",
                    "defrost_time_period_fraction",
                    "resistive_defrost_heater_capacity",
                    "maximum_outdoor_dry_bulb_temperature_for_defrost_operation",
                    "water_condenser_volume_flow_rate",
                    "evaporative_condenser_effectiveness",
                    "evaporative_condenser_air_flow_rate",
                    "evaporative_condenser_pump_rated_power_consumption",
                    "basin_heater_capacity",
                    "basin_heater_setpoint_temperature",
                    "minimum_outdoor_temperature_in_heat_recovery_mode",
                    "maximum_outdoor_temperature_in_heat_recovery_mode"
                ]
            }
        },
        "type": "object",
        "memo": "Variable refrigerant flow (VRF) heat pump condensing unit. Serves one or more VRF zone terminal units (HVACTemplate:Zone:VRF).",
        "min_fields": 39.0
    }
}
```
