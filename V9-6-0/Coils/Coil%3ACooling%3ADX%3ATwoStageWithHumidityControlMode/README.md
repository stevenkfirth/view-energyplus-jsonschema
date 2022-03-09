```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "availability_schedule_name": {
                    "type": "string",
                    "note": "Availability schedule name for this system. Schedule value > 0 means the system is available. If this field is blank, the system is always available.",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "air_inlet_node_name": {
                    "type": "string"
                },
                "air_outlet_node_name": {
                    "type": "string"
                },
                "crankcase_heater_capacity": {
                    "type": "number",
                    "minimum": 0.0,
                    "default": 0.0,
                    "units": "W",
                    "ip-units": "W"
                },
                "maximum_outdoor_dry_bulb_temperature_for_crankcase_heater_operation": {
                    "type": "number",
                    "minimum": 0.0,
                    "default": 10.0,
                    "units": "C"
                },
                "number_of_capacity_stages": {
                    "type": "number",
                    "minimum": 1.0,
                    "maximum": 2.0,
                    "default": 1.0
                },
                "number_of_enhanced_dehumidification_modes": {
                    "type": "number",
                    "minimum": 0.0,
                    "maximum": 1.0,
                    "default": 0.0
                },
                "normal_mode_stage_1_coil_performance_object_type": {
                    "type": "string",
                    "enum": [
                        "CoilPerformance:DX:Cooling"
                    ]
                },
                "normal_mode_stage_1_coil_performance_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "CoilPerformanceDX"
                    ]
                },
                "normal_mode_stage_1_2_coil_performance_object_type": {
                    "type": "string",
                    "enum": [
                        "CoilPerformance:DX:Cooling"
                    ]
                },
                "normal_mode_stage_1_2_coil_performance_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "CoilPerformanceDX"
                    ]
                },
                "dehumidification_mode_1_stage_1_coil_performance_object_type": {
                    "type": "string",
                    "enum": [
                        "CoilPerformance:DX:Cooling"
                    ]
                },
                "dehumidification_mode_1_stage_1_coil_performance_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "CoilPerformanceDX"
                    ]
                },
                "dehumidification_mode_1_stage_1_2_coil_performance_object_type": {
                    "type": "string",
                    "enum": [
                        "CoilPerformance:DX:Cooling"
                    ]
                },
                "dehumidification_mode_1_stage_1_2_coil_performance_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "CoilPerformanceDX"
                    ]
                },
                "supply_water_storage_tank_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "WaterStorageTankNames"
                    ]
                },
                "condensate_collection_water_storage_tank_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "WaterStorageTankNames"
                    ]
                },
                "minimum_outdoor_dry_bulb_temperature_for_compressor_operation": {
                    "type": "number",
                    "default": -25.0,
                    "units": "C"
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
                }
            },
            "required": [
                "air_inlet_node_name",
                "air_outlet_node_name",
                "normal_mode_stage_1_coil_performance_object_type",
                "normal_mode_stage_1_coil_performance_name"
            ]
        }
    },
    "group": "Coils",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "AFNCoilNames",
            "CoolingCoilsDX",
            "CoolingCoilsDXMultiModeOrSingleSpeed",
            "DesuperHeatingCoilSources"
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
            "air_inlet_node_name": {
                "field_name": "Air Inlet Node Name",
                "field_type": "a"
            },
            "air_outlet_node_name": {
                "field_name": "Air Outlet Node Name",
                "field_type": "a"
            },
            "crankcase_heater_capacity": {
                "field_name": "Crankcase Heater Capacity",
                "field_type": "n"
            },
            "maximum_outdoor_dry_bulb_temperature_for_crankcase_heater_operation": {
                "field_name": "Maximum Outdoor Dry-Bulb Temperature for Crankcase Heater Operation",
                "field_type": "n"
            },
            "number_of_capacity_stages": {
                "field_name": "Number of Capacity Stages",
                "field_type": "n"
            },
            "number_of_enhanced_dehumidification_modes": {
                "field_name": "Number of Enhanced Dehumidification Modes",
                "field_type": "n"
            },
            "normal_mode_stage_1_coil_performance_object_type": {
                "field_name": "Normal Mode Stage 1 Coil Performance Object Type",
                "field_type": "a"
            },
            "normal_mode_stage_1_coil_performance_name": {
                "field_name": "Normal Mode Stage 1 Coil Performance Name",
                "field_type": "a"
            },
            "normal_mode_stage_1_2_coil_performance_object_type": {
                "field_name": "Normal Mode Stage 1+2 Coil Performance Object Type",
                "field_type": "a"
            },
            "normal_mode_stage_1_2_coil_performance_name": {
                "field_name": "Normal Mode Stage 1+2 Coil Performance Name",
                "field_type": "a"
            },
            "dehumidification_mode_1_stage_1_coil_performance_object_type": {
                "field_name": "Dehumidification Mode 1 Stage 1 Coil Performance Object Type",
                "field_type": "a"
            },
            "dehumidification_mode_1_stage_1_coil_performance_name": {
                "field_name": "Dehumidification Mode 1 Stage 1 Coil Performance Name",
                "field_type": "a"
            },
            "dehumidification_mode_1_stage_1_2_coil_performance_object_type": {
                "field_name": "Dehumidification Mode 1 Stage 1+2 Coil Performance Object Type",
                "field_type": "a"
            },
            "dehumidification_mode_1_stage_1_2_coil_performance_name": {
                "field_name": "Dehumidification Mode 1 Stage 1+2 Coil Performance Name",
                "field_type": "a"
            },
            "supply_water_storage_tank_name": {
                "field_name": "Supply Water Storage Tank Name",
                "field_type": "a"
            },
            "condensate_collection_water_storage_tank_name": {
                "field_name": "Condensate Collection Water Storage Tank Name",
                "field_type": "a"
            },
            "minimum_outdoor_dry_bulb_temperature_for_compressor_operation": {
                "field_name": "Minimum Outdoor Dry-Bulb Temperature for Compressor Operation",
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
            }
        },
        "fields": [
            "name",
            "availability_schedule_name",
            "air_inlet_node_name",
            "air_outlet_node_name",
            "crankcase_heater_capacity",
            "maximum_outdoor_dry_bulb_temperature_for_crankcase_heater_operation",
            "number_of_capacity_stages",
            "number_of_enhanced_dehumidification_modes",
            "normal_mode_stage_1_coil_performance_object_type",
            "normal_mode_stage_1_coil_performance_name",
            "normal_mode_stage_1_2_coil_performance_object_type",
            "normal_mode_stage_1_2_coil_performance_name",
            "dehumidification_mode_1_stage_1_coil_performance_object_type",
            "dehumidification_mode_1_stage_1_coil_performance_name",
            "dehumidification_mode_1_stage_1_2_coil_performance_object_type",
            "dehumidification_mode_1_stage_1_2_coil_performance_name",
            "supply_water_storage_tank_name",
            "condensate_collection_water_storage_tank_name",
            "minimum_outdoor_dry_bulb_temperature_for_compressor_operation",
            "basin_heater_capacity",
            "basin_heater_setpoint_temperature",
            "basin_heater_operating_schedule_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "availability_schedule_name",
                "air_inlet_node_name",
                "air_outlet_node_name",
                "normal_mode_stage_1_coil_performance_object_type",
                "normal_mode_stage_1_coil_performance_name",
                "normal_mode_stage_1_2_coil_performance_object_type",
                "normal_mode_stage_1_2_coil_performance_name",
                "dehumidification_mode_1_stage_1_coil_performance_object_type",
                "dehumidification_mode_1_stage_1_coil_performance_name",
                "dehumidification_mode_1_stage_1_2_coil_performance_object_type",
                "dehumidification_mode_1_stage_1_2_coil_performance_name",
                "supply_water_storage_tank_name",
                "condensate_collection_water_storage_tank_name",
                "basin_heater_operating_schedule_name"
            ]
        },
        "numerics": {
            "fields": [
                "crankcase_heater_capacity",
                "maximum_outdoor_dry_bulb_temperature_for_crankcase_heater_operation",
                "number_of_capacity_stages",
                "number_of_enhanced_dehumidification_modes",
                "minimum_outdoor_dry_bulb_temperature_for_compressor_operation",
                "basin_heater_capacity",
                "basin_heater_setpoint_temperature"
            ]
        }
    },
    "type": "object",
    "memo": "Direct expansion (DX) cooling coil and condensing unit (includes electric compressor and condenser fan), two-stage with humidity control mode (e.g. sub-cool or hot gas reheat). Optional inputs for moisture evaporation from wet coil when compressor cycles off with continuous fan operation. Requires two to four sets of performance data, see CoilPerformance:DX:Cooling. Stages are modeled as a face-split coil.",
    "min_fields": 10.0
}
```
