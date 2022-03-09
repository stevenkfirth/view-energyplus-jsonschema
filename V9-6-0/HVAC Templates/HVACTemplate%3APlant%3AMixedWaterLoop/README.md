```
{
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
                "operation_scheme_type": {
                    "type": "string",
                    "note": "Default operation type makes all equipment available at all times operating in order of Priority specified in HVACTemplate:Plant:Boiler and HVACTemplate:Plant:Tower objects.",
                    "enum": [
                        "",
                        "Default",
                        "UserDefined"
                    ],
                    "default": "Default"
                },
                "equipment_operation_schemes_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "PlantOperationSchemes"
                    ],
                    "note": "Name of a PlantEquipmentOperationSchemes object Ignored if Plant Operation Scheme Type = Default"
                },
                "high_temperature_setpoint_schedule_name": {
                    "type": "string",
                    "note": "Leave blank if constant setpoint",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "high_temperature_design_setpoint": {
                    "type": "number",
                    "note": "Used for sizing and as constant setpoint if no Setpoint Schedule Name is specified.",
                    "default": 33.0,
                    "units": "C"
                },
                "low_temperature_setpoint_schedule_name": {
                    "type": "string",
                    "note": "Leave blank if constant setpoint May be left blank if not serving any water cooled chillers",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "low_temperature_design_setpoint": {
                    "type": "number",
                    "note": "Used for sizing and as constant setpoint if no Condenser Water Setpoint Schedule Name is specified. May be left blank if not serving any water cooled chillers",
                    "default": 20.0,
                    "units": "C"
                },
                "water_pump_configuration": {
                    "type": "string",
                    "note": "VariableFlow - variable flow to boilers and coils, excess bypassed ConstantFlow - constant flow to boilers and coils, excess bypassed",
                    "enum": [
                        "",
                        "ConstantFlow",
                        "VariableFlow"
                    ],
                    "default": "ConstantFlow"
                },
                "water_pump_rated_head": {
                    "type": "number",
                    "note": "May be left blank if not serving any water cooled chillers default head is 60 feet H2O",
                    "units": "Pa",
                    "minimum": 0.0,
                    "default": 179352.0,
                    "ip-units": "ftH2O"
                },
                "water_pump_type": {
                    "type": "string",
                    "note": "Describes the type of pump configuration used for the mixed water loop.",
                    "enum": [
                        "",
                        "FiveHeaderedPumps",
                        "FourHeaderedPumps",
                        "PumpPerTowerOrBoiler",
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
                    "default": 5.6
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
            "operation_scheme_type": {
                "field_name": "Operation Scheme Type",
                "field_type": "a"
            },
            "equipment_operation_schemes_name": {
                "field_name": "Equipment Operation Schemes Name",
                "field_type": "a"
            },
            "high_temperature_setpoint_schedule_name": {
                "field_name": "High Temperature Setpoint Schedule Name",
                "field_type": "a"
            },
            "high_temperature_design_setpoint": {
                "field_name": "High Temperature Design Setpoint",
                "field_type": "n"
            },
            "low_temperature_setpoint_schedule_name": {
                "field_name": "Low Temperature Setpoint Schedule Name",
                "field_type": "a"
            },
            "low_temperature_design_setpoint": {
                "field_name": "Low Temperature Design Setpoint",
                "field_type": "n"
            },
            "water_pump_configuration": {
                "field_name": "Water Pump Configuration",
                "field_type": "a"
            },
            "water_pump_rated_head": {
                "field_name": "Water Pump Rated Head",
                "field_type": "n"
            },
            "water_pump_type": {
                "field_name": "Water Pump Type",
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
            "load_distribution_scheme": {
                "field_name": "Load Distribution Scheme",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "pump_schedule_name",
            "pump_control_type",
            "operation_scheme_type",
            "equipment_operation_schemes_name",
            "high_temperature_setpoint_schedule_name",
            "high_temperature_design_setpoint",
            "low_temperature_setpoint_schedule_name",
            "low_temperature_design_setpoint",
            "water_pump_configuration",
            "water_pump_rated_head",
            "water_pump_type",
            "supply_side_bypass_pipe",
            "demand_side_bypass_pipe",
            "fluid_type",
            "loop_design_delta_temperature",
            "load_distribution_scheme"
        ],
        "alphas": {
            "fields": [
                "name",
                "pump_schedule_name",
                "pump_control_type",
                "operation_scheme_type",
                "equipment_operation_schemes_name",
                "high_temperature_setpoint_schedule_name",
                "low_temperature_setpoint_schedule_name",
                "water_pump_configuration",
                "water_pump_type",
                "supply_side_bypass_pipe",
                "demand_side_bypass_pipe",
                "fluid_type",
                "load_distribution_scheme"
            ]
        },
        "numerics": {
            "fields": [
                "high_temperature_design_setpoint",
                "low_temperature_design_setpoint",
                "water_pump_rated_head",
                "loop_design_delta_temperature"
            ]
        }
    },
    "type": "object",
    "maxProperties": 1,
    "memo": "Central plant loop portion of a water source heat pump system.",
    "min_fields": 11.0
}
```
