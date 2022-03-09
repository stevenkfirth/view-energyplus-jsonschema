```
{
    "HVACTemplate:Plant:HotWaterLoop": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "pump_schedule_name": {
                        "type": "string",
                        "note": "If blank, always available",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "pump_control_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "Continuous",
                            "Intermittent"
                        ],
                        "default": "Intermittent"
                    },
                    "hot_water_plant_operation_scheme_type": {
                        "type": "string",
                        "note": "Default operation type makes all equipment available at all times operating in order of Priority specified in HVACTemplate:Plant:Boiler objects.",
                        "enum": [
                            "",
                            "Default",
                            "UserDefined"
                        ],
                        "default": "Default"
                    },
                    "hot_water_plant_equipment_operation_schemes_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "PlantOperationSchemes"
                        ],
                        "note": "Name of a PlantEquipmentOperationSchemes object Ignored if Plant Operation Scheme Type = Default"
                    },
                    "hot_water_setpoint_schedule_name": {
                        "type": "string",
                        "note": "Leave blank if constant setpoint",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ]
                    },
                    "hot_water_design_setpoint": {
                        "type": "number",
                        "note": "Used for sizing and as constant setpoint if no Setpoint Schedule Name is specified.",
                        "default": 82.0,
                        "units": "C"
                    },
                    "hot_water_pump_configuration": {
                        "type": "string",
                        "note": "VariableFlow - variable flow to boilers and coils, excess bypassed ConstantFlow - constant flow to boilers and coils, excess bypassed",
                        "enum": [
                            "",
                            "ConstantFlow",
                            "VariableFlow"
                        ],
                        "default": "ConstantFlow"
                    },
                    "hot_water_pump_rated_head": {
                        "type": "number",
                        "units": "Pa",
                        "minimum": 0.0,
                        "default": 179352.0,
                        "note": "Default head is 60 feet H2O",
                        "ip-units": "ftH2O"
                    },
                    "hot_water_setpoint_reset_type": {
                        "type": "string",
                        "note": "Overrides Hot Water Setpoint Schedule Name",
                        "enum": [
                            "",
                            "None",
                            "OutdoorAirTemperatureReset"
                        ],
                        "default": "None"
                    },
                    "hot_water_setpoint_at_outdoor_dry_bulb_low": {
                        "type": "number",
                        "note": "Applicable only for OutdoorAirTemperatureReset control.",
                        "units": "C",
                        "default": 82.2
                    },
                    "hot_water_reset_outdoor_dry_bulb_low": {
                        "type": "number",
                        "note": "Applicable only for OutdoorAirTemperatureReset control.",
                        "units": "C",
                        "default": -6.7
                    },
                    "hot_water_setpoint_at_outdoor_dry_bulb_high": {
                        "type": "number",
                        "note": "Applicable only for OutdoorAirTemperatureReset control.",
                        "units": "C",
                        "default": 65.6
                    },
                    "hot_water_reset_outdoor_dry_bulb_high": {
                        "type": "number",
                        "note": "Applicable only for OutdoorAirTemperatureReset control.",
                        "units": "C",
                        "default": 10.0
                    },
                    "hot_water_pump_type": {
                        "type": "string",
                        "note": "Describes the type of pump configuration used for the hot water loop.",
                        "enum": [
                            "",
                            "FiveHeaderedPumps",
                            "FourHeaderedPumps",
                            "PumpPerBoiler",
                            "SinglePump",
                            "ThreeHeaderedPumps",
                            "TwoHeaderedPumps"
                        ],
                        "default": "SinglePump"
                    },
                    "supply_side_bypass_pipe": {
                        "type": "string",
                        "note": "Determines if a supply side bypass pipe is present in the hot water loop.",
                        "enum": [
                            "",
                            "No",
                            "Yes"
                        ],
                        "default": "Yes"
                    },
                    "demand_side_bypass_pipe": {
                        "type": "string",
                        "note": "Determines if a demand side bypass pipe is present in the hot water loop.",
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
                        "default": 11.0
                    },
                    "maximum_outdoor_dry_bulb_temperature": {
                        "type": "number",
                        "note": "The maximum outdoor dry-bulb temperature that the hot water loops operate. Leave blank for no limit.",
                        "units": "C"
                    },
                    "load_distribution_scheme": {
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
                "hot_water_plant_operation_scheme_type": {
                    "field_name": "Hot Water Plant Operation Scheme Type",
                    "field_type": "a"
                },
                "hot_water_plant_equipment_operation_schemes_name": {
                    "field_name": "Hot Water Plant Equipment Operation Schemes Name",
                    "field_type": "a"
                },
                "hot_water_setpoint_schedule_name": {
                    "field_name": "Hot Water Setpoint Schedule Name",
                    "field_type": "a"
                },
                "hot_water_design_setpoint": {
                    "field_name": "Hot Water Design Setpoint",
                    "field_type": "n"
                },
                "hot_water_pump_configuration": {
                    "field_name": "Hot Water Pump Configuration",
                    "field_type": "a"
                },
                "hot_water_pump_rated_head": {
                    "field_name": "Hot Water Pump Rated Head",
                    "field_type": "n"
                },
                "hot_water_setpoint_reset_type": {
                    "field_name": "Hot Water Setpoint Reset Type",
                    "field_type": "a"
                },
                "hot_water_setpoint_at_outdoor_dry_bulb_low": {
                    "field_name": "Hot Water Setpoint at Outdoor Dry-Bulb Low",
                    "field_type": "n"
                },
                "hot_water_reset_outdoor_dry_bulb_low": {
                    "field_name": "Hot Water Reset Outdoor Dry-Bulb Low",
                    "field_type": "n"
                },
                "hot_water_setpoint_at_outdoor_dry_bulb_high": {
                    "field_name": "Hot Water Setpoint at Outdoor Dry-Bulb High",
                    "field_type": "n"
                },
                "hot_water_reset_outdoor_dry_bulb_high": {
                    "field_name": "Hot Water Reset Outdoor Dry-Bulb High",
                    "field_type": "n"
                },
                "hot_water_pump_type": {
                    "field_name": "Hot Water Pump Type",
                    "field_type": "a"
                },
                "supply_side_bypass_pipe": {
                    "field_name": "Supply Side Bypass Pipe",
                    "field_type": "a"
                },
                "demand_side_bypass_pipe": {
                    "field_name": "Demand Side Bypass Pipe",
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
                "maximum_outdoor_dry_bulb_temperature": {
                    "field_name": "Maximum Outdoor Dry Bulb Temperature",
                    "field_type": "n"
                },
                "load_distribution_scheme": {
                    "field_name": "Load Distribution Scheme",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "pump_schedule_name",
                "pump_control_type",
                "hot_water_plant_operation_scheme_type",
                "hot_water_plant_equipment_operation_schemes_name",
                "hot_water_setpoint_schedule_name",
                "hot_water_design_setpoint",
                "hot_water_pump_configuration",
                "hot_water_pump_rated_head",
                "hot_water_setpoint_reset_type",
                "hot_water_setpoint_at_outdoor_dry_bulb_low",
                "hot_water_reset_outdoor_dry_bulb_low",
                "hot_water_setpoint_at_outdoor_dry_bulb_high",
                "hot_water_reset_outdoor_dry_bulb_high",
                "hot_water_pump_type",
                "supply_side_bypass_pipe",
                "demand_side_bypass_pipe",
                "fluid_type",
                "loop_design_delta_temperature",
                "maximum_outdoor_dry_bulb_temperature",
                "load_distribution_scheme"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "pump_schedule_name",
                    "pump_control_type",
                    "hot_water_plant_operation_scheme_type",
                    "hot_water_plant_equipment_operation_schemes_name",
                    "hot_water_setpoint_schedule_name",
                    "hot_water_pump_configuration",
                    "hot_water_setpoint_reset_type",
                    "hot_water_pump_type",
                    "supply_side_bypass_pipe",
                    "demand_side_bypass_pipe",
                    "fluid_type",
                    "load_distribution_scheme"
                ]
            },
            "numerics": {
                "fields": [
                    "hot_water_design_setpoint",
                    "hot_water_pump_rated_head",
                    "hot_water_setpoint_at_outdoor_dry_bulb_low",
                    "hot_water_reset_outdoor_dry_bulb_low",
                    "hot_water_setpoint_at_outdoor_dry_bulb_high",
                    "hot_water_reset_outdoor_dry_bulb_high",
                    "loop_design_delta_temperature",
                    "maximum_outdoor_dry_bulb_temperature"
                ]
            }
        },
        "type": "object",
        "maxProperties": 1,
        "memo": "Plant loop to serve all HVACTemplate hot water coils and boilers.",
        "min_fields": 14.0
    }
}
```
