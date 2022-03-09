```
{
    "HVACTemplate:Plant:ChilledWaterLoop": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "pump_schedule_name": {
                        "type": "string",
                        "note": "If blank, always available Applies to both chilled water and condenser loop pumps",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "pump_control_type": {
                        "type": "string",
                        "note": "Applies to both chilled water and condenser loop pumps",
                        "enum": [
                            "",
                            "Continuous",
                            "Intermittent"
                        ],
                        "default": "Intermittent"
                    },
                    "chiller_plant_operation_scheme_type": {
                        "type": "string",
                        "note": "Default operation type makes all equipment available at all times operating in order of Priority specified in HVACTemplate:Plant:Chiller objects.",
                        "enum": [
                            "",
                            "Default",
                            "UserDefined"
                        ],
                        "default": "Default"
                    },
                    "chiller_plant_equipment_operation_schemes_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "PlantOperationSchemes"
                        ],
                        "note": "Name of a PlantEquipmentOperationSchemes object Ignored if Chiller Plant Operation Scheme Type = Default"
                    },
                    "chilled_water_setpoint_schedule_name": {
                        "type": "string",
                        "note": "Leave blank if constant setpoint",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "chilled_water_design_setpoint": {
                        "type": "number",
                        "note": "Used for sizing and as constant setpoint if no Chilled Water Setpoint Schedule Name is specified.",
                        "default": 7.22,
                        "units": "C"
                    },
                    "chilled_water_pump_configuration": {
                        "type": "string",
                        "note": "VariablePrimaryNoSecondary - variable flow to chillers and coils ConstantPrimaryNoSecondary - constant flow to chillers and coils, excess bypassed ConstantPrimaryVariableSecondary - constant flow to chillers, variable flow to coils VariablePrimaryConstantSecondary - currently unsupported - variable flow to chillers, constant flow to coils",
                        "enum": [
                            "",
                            "ConstantPrimaryNoSecondary",
                            "ConstantPrimaryVariableSecondary",
                            "VariablePrimaryNoSecondary"
                        ],
                        "default": "ConstantPrimaryNoSecondary"
                    },
                    "primary_chilled_water_pump_rated_head": {
                        "type": "number",
                        "units": "Pa",
                        "minimum": 0.0,
                        "default": 179352.0,
                        "note": "default head is 60 feet H2O",
                        "ip-units": "ftH2O"
                    },
                    "secondary_chilled_water_pump_rated_head": {
                        "type": "number",
                        "units": "Pa",
                        "minimum": 0.0,
                        "default": 179352.0,
                        "note": "default head is 60 feet H2O",
                        "ip-units": "ftH2O"
                    },
                    "condenser_plant_operation_scheme_type": {
                        "type": "string",
                        "note": "Default operation type makes all equipment available at all times operating in order of Priority specified in HVACTemplate:Plant:Tower objects. May be left blank if not serving any water cooled chillers",
                        "enum": [
                            "",
                            "Default",
                            "UserDefined"
                        ],
                        "default": "Default"
                    },
                    "condenser_equipment_operation_schemes_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "CondenserOperationSchemes"
                        ],
                        "note": "Name of a CondenserEquipmentOperationSchemes object Ignored if Condenser Plant Operation Scheme Type = Default May be left blank if not serving any water cooled chillers"
                    },
                    "condenser_water_temperature_control_type": {
                        "type": "string",
                        "note": "May be left blank if not serving any water cooled chillers",
                        "enum": [
                            "OutdoorWetBulbTemperature",
                            "SpecifiedSetpoint"
                        ]
                    },
                    "condenser_water_setpoint_schedule_name": {
                        "type": "string",
                        "note": "Leave blank if constant setpoint May be left blank if not serving any water cooled chillers",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "condenser_water_design_setpoint": {
                        "type": "number",
                        "note": "Used for sizing and as constant setpoint if no Condenser Water Setpoint Schedule Name is specified. May be left blank if not serving any water cooled chillers",
                        "default": 29.4,
                        "units": "C"
                    },
                    "condenser_water_pump_rated_head": {
                        "type": "number",
                        "note": "May be left blank if not serving any water cooled chillers default head is 60 feet H2O",
                        "units": "Pa",
                        "minimum": 0.0,
                        "default": 179352.0,
                        "ip-units": "ftH2O"
                    },
                    "chilled_water_setpoint_reset_type": {
                        "type": "string",
                        "note": "Overrides Chilled Water Setpoint Schedule Name",
                        "enum": [
                            "",
                            "None",
                            "OutdoorAirTemperatureReset"
                        ],
                        "default": "None"
                    },
                    "chilled_water_setpoint_at_outdoor_dry_bulb_low": {
                        "type": "number",
                        "note": "Applicable only for OutdoorAirTemperatureReset control.",
                        "units": "C",
                        "default": 12.2
                    },
                    "chilled_water_reset_outdoor_dry_bulb_low": {
                        "type": "number",
                        "note": "Applicable only for OutdoorAirTemperatureReset control.",
                        "units": "C",
                        "default": 15.6
                    },
                    "chilled_water_setpoint_at_outdoor_dry_bulb_high": {
                        "type": "number",
                        "note": "Applicable only for OutdoorAirTemperatureReset control.",
                        "units": "C",
                        "default": 6.7
                    },
                    "chilled_water_reset_outdoor_dry_bulb_high": {
                        "type": "number",
                        "note": "Applicable only for OutdoorAirTemperatureReset control.",
                        "units": "C",
                        "default": 26.7
                    },
                    "chilled_water_primary_pump_type": {
                        "type": "string",
                        "note": "Describes the type of pump configuration used for the primary portion of the chilled water loop.",
                        "enum": [
                            "",
                            "FiveHeaderedPumps",
                            "FourHeaderedPumps",
                            "PumpPerChiller",
                            "SinglePump",
                            "ThreeHeaderedPumps",
                            "TwoHeaderedPumps"
                        ],
                        "default": "SinglePump"
                    },
                    "chilled_water_secondary_pump_type": {
                        "type": "string",
                        "note": "Describes the type of pump configuration used for the secondary portion of the chilled water loop.",
                        "enum": [
                            "",
                            "FiveHeaderedPumps",
                            "FourHeaderedPumps",
                            "SinglePump",
                            "ThreeHeaderedPumps",
                            "TwoHeaderedPumps"
                        ],
                        "default": "SinglePump"
                    },
                    "condenser_water_pump_type": {
                        "type": "string",
                        "note": "Describes the type of pump configuration used for the condenser water loop.",
                        "enum": [
                            "",
                            "FiveHeaderedPumps",
                            "FourHeaderedPumps",
                            "PumpPerTower",
                            "SinglePump",
                            "ThreeHeaderedPumps",
                            "TwoHeaderedPumps"
                        ],
                        "default": "SinglePump"
                    },
                    "chilled_water_supply_side_bypass_pipe": {
                        "type": "string",
                        "note": "Determines if a supply side bypass pipe is present in the chilled water loop.",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "Yes"
                    },
                    "chilled_water_demand_side_bypass_pipe": {
                        "type": "string",
                        "note": "Determines if a demand side bypass pipe is present in the chilled water loop.",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "Yes"
                    },
                    "condenser_water_supply_side_bypass_pipe": {
                        "type": "string",
                        "note": "Determines if a supply side bypass pipe is present in the condenser water loop.",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "Yes"
                    },
                    "condenser_water_demand_side_bypass_pipe": {
                        "type": "string",
                        "note": "Determines if a demand side bypass pipe is present in the condenser water loop.",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "Yes"
                    },
                    "fluid_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "EthyleneGlycol30",
                            "EthyleneGlycol40",
                            "EthyleneGlycol50",
                            "EthyleneGlycol60",
                            "PropyleneGlycol30",
                            "PropyleneGlycol40",
                            "PropyleneGlycol50",
                            "PropyleneGlycol60",
                            "Water"
                        ],
                        "default": "Water"
                    },
                    "loop_design_delta_temperature": {
                        "type": "number",
                        "note": "The temperature difference used in sizing the loop flow rate.",
                        "units": "deltaC",
                        "default": 6.67
                    },
                    "minimum_outdoor_dry_bulb_temperature": {
                        "type": "number",
                        "note": "The minimum outdoor dry-bulb temperature that the chilled water loops operate. Leave blank for no limit.",
                        "units": "C"
                    },
                    "chilled_water_load_distribution_scheme": {
                        "type": "string",
                        "enum": [
                            "",
                            "Optimal",
                            "SequentialLoad",
                            "SequentialUniformPLR",
                            "UniformLoad",
                            "UniformPLR"
                        ],
                        "default": "SequentialLoad"
                    },
                    "condenser_water_load_distribution_scheme": {
                        "type": "string",
                        "enum": [
                            "",
                            "Optimal",
                            "SequentialLoad",
                            "SequentialUniformPLR",
                            "UniformLoad",
                            "UniformPLR"
                        ],
                        "default": "SequentialLoad"
                    }
                }
            }
        },
        "group": "HVAC Templates",
        "name": {
            "type": "string",
            "is_required": true
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "pump_schedule_name": {
                    "field_name": "Pump Schedule Name",
                    "field_type": "a"
                },
                "pump_control_type": {
                    "field_name": "Pump Control Type",
                    "field_type": "a"
                },
                "chiller_plant_operation_scheme_type": {
                    "field_name": "Chiller Plant Operation Scheme Type",
                    "field_type": "a"
                },
                "chiller_plant_equipment_operation_schemes_name": {
                    "field_name": "Chiller Plant Equipment Operation Schemes Name",
                    "field_type": "a"
                },
                "chilled_water_setpoint_schedule_name": {
                    "field_name": "Chilled Water Setpoint Schedule Name",
                    "field_type": "a"
                },
                "chilled_water_design_setpoint": {
                    "field_name": "Chilled Water Design Setpoint",
                    "field_type": "n"
                },
                "chilled_water_pump_configuration": {
                    "field_name": "Chilled Water Pump Configuration",
                    "field_type": "a"
                },
                "primary_chilled_water_pump_rated_head": {
                    "field_name": "Primary Chilled Water Pump Rated Head",
                    "field_type": "n"
                },
                "secondary_chilled_water_pump_rated_head": {
                    "field_name": "Secondary Chilled Water Pump Rated Head",
                    "field_type": "n"
                },
                "condenser_plant_operation_scheme_type": {
                    "field_name": "Condenser Plant Operation Scheme Type",
                    "field_type": "a"
                },
                "condenser_equipment_operation_schemes_name": {
                    "field_name": "Condenser Equipment Operation Schemes Name",
                    "field_type": "a"
                },
                "condenser_water_temperature_control_type": {
                    "field_name": "Condenser Water Temperature Control Type",
                    "field_type": "a"
                },
                "condenser_water_setpoint_schedule_name": {
                    "field_name": "Condenser Water Setpoint Schedule Name",
                    "field_type": "a"
                },
                "condenser_water_design_setpoint": {
                    "field_name": "Condenser Water Design Setpoint",
                    "field_type": "n"
                },
                "condenser_water_pump_rated_head": {
                    "field_name": "Condenser Water Pump Rated Head",
                    "field_type": "n"
                },
                "chilled_water_setpoint_reset_type": {
                    "field_name": "Chilled Water Setpoint Reset Type",
                    "field_type": "a"
                },
                "chilled_water_setpoint_at_outdoor_dry_bulb_low": {
                    "field_name": "Chilled Water Setpoint at Outdoor Dry-Bulb Low",
                    "field_type": "n"
                },
                "chilled_water_reset_outdoor_dry_bulb_low": {
                    "field_name": "Chilled Water Reset Outdoor Dry-Bulb Low",
                    "field_type": "n"
                },
                "chilled_water_setpoint_at_outdoor_dry_bulb_high": {
                    "field_name": "Chilled Water Setpoint at Outdoor Dry-Bulb High",
                    "field_type": "n"
                },
                "chilled_water_reset_outdoor_dry_bulb_high": {
                    "field_name": "Chilled Water Reset Outdoor Dry-Bulb High",
                    "field_type": "n"
                },
                "chilled_water_primary_pump_type": {
                    "field_name": "Chilled Water Primary Pump Type",
                    "field_type": "a"
                },
                "chilled_water_secondary_pump_type": {
                    "field_name": "Chilled Water Secondary Pump Type",
                    "field_type": "a"
                },
                "condenser_water_pump_type": {
                    "field_name": "Condenser Water Pump Type",
                    "field_type": "a"
                },
                "chilled_water_supply_side_bypass_pipe": {
                    "field_name": "Chilled Water Supply Side Bypass Pipe",
                    "field_type": "a"
                },
                "chilled_water_demand_side_bypass_pipe": {
                    "field_name": "Chilled Water Demand Side Bypass Pipe",
                    "field_type": "a"
                },
                "condenser_water_supply_side_bypass_pipe": {
                    "field_name": "Condenser Water Supply Side Bypass Pipe",
                    "field_type": "a"
                },
                "condenser_water_demand_side_bypass_pipe": {
                    "field_name": "Condenser Water Demand Side Bypass Pipe",
                    "field_type": "a"
                },
                "fluid_type": {
                    "field_name": "Fluid Type",
                    "field_type": "a"
                },
                "loop_design_delta_temperature": {
                    "field_name": "Loop Design Delta Temperature",
                    "field_type": "n"
                },
                "minimum_outdoor_dry_bulb_temperature": {
                    "field_name": "Minimum Outdoor Dry Bulb Temperature",
                    "field_type": "n"
                },
                "chilled_water_load_distribution_scheme": {
                    "field_name": "Chilled Water Load Distribution Scheme",
                    "field_type": "a"
                },
                "condenser_water_load_distribution_scheme": {
                    "field_name": "Condenser Water Load Distribution Scheme",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "pump_schedule_name",
                "pump_control_type",
                "chiller_plant_operation_scheme_type",
                "chiller_plant_equipment_operation_schemes_name",
                "chilled_water_setpoint_schedule_name",
                "chilled_water_design_setpoint",
                "chilled_water_pump_configuration",
                "primary_chilled_water_pump_rated_head",
                "secondary_chilled_water_pump_rated_head",
                "condenser_plant_operation_scheme_type",
                "condenser_equipment_operation_schemes_name",
                "condenser_water_temperature_control_type",
                "condenser_water_setpoint_schedule_name",
                "condenser_water_design_setpoint",
                "condenser_water_pump_rated_head",
                "chilled_water_setpoint_reset_type",
                "chilled_water_setpoint_at_outdoor_dry_bulb_low",
                "chilled_water_reset_outdoor_dry_bulb_low",
                "chilled_water_setpoint_at_outdoor_dry_bulb_high",
                "chilled_water_reset_outdoor_dry_bulb_high",
                "chilled_water_primary_pump_type",
                "chilled_water_secondary_pump_type",
                "condenser_water_pump_type",
                "chilled_water_supply_side_bypass_pipe",
                "chilled_water_demand_side_bypass_pipe",
                "condenser_water_supply_side_bypass_pipe",
                "condenser_water_demand_side_bypass_pipe",
                "fluid_type",
                "loop_design_delta_temperature",
                "minimum_outdoor_dry_bulb_temperature",
                "chilled_water_load_distribution_scheme",
                "condenser_water_load_distribution_scheme"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "pump_schedule_name",
                    "pump_control_type",
                    "chiller_plant_operation_scheme_type",
                    "chiller_plant_equipment_operation_schemes_name",
                    "chilled_water_setpoint_schedule_name",
                    "chilled_water_pump_configuration",
                    "condenser_plant_operation_scheme_type",
                    "condenser_equipment_operation_schemes_name",
                    "condenser_water_temperature_control_type",
                    "condenser_water_setpoint_schedule_name",
                    "chilled_water_setpoint_reset_type",
                    "chilled_water_primary_pump_type",
                    "chilled_water_secondary_pump_type",
                    "condenser_water_pump_type",
                    "chilled_water_supply_side_bypass_pipe",
                    "chilled_water_demand_side_bypass_pipe",
                    "condenser_water_supply_side_bypass_pipe",
                    "condenser_water_demand_side_bypass_pipe",
                    "fluid_type",
                    "chilled_water_load_distribution_scheme",
                    "condenser_water_load_distribution_scheme"
                ]
            },
            "numerics": {
                "fields": [
                    "chilled_water_design_setpoint",
                    "primary_chilled_water_pump_rated_head",
                    "secondary_chilled_water_pump_rated_head",
                    "condenser_water_design_setpoint",
                    "condenser_water_pump_rated_head",
                    "chilled_water_setpoint_at_outdoor_dry_bulb_low",
                    "chilled_water_reset_outdoor_dry_bulb_low",
                    "chilled_water_setpoint_at_outdoor_dry_bulb_high",
                    "chilled_water_reset_outdoor_dry_bulb_high",
                    "loop_design_delta_temperature",
                    "minimum_outdoor_dry_bulb_temperature"
                ]
            }
        },
        "type": "object",
        "maxProperties": 1,
        "memo": "Plant and condenser loops to serve all HVACTemplate chilled water coils, chillers, and towers.",
        "min_fields": 21.0
    }
}
```
