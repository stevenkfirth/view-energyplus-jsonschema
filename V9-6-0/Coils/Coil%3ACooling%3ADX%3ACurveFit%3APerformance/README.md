```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "crankcase_heater_capacity": {
                    "type": "number",
                    "minimum": 0.0,
                    "default": 0.0,
                    "units": "W",
                    "ip-units": "W"
                },
                "minimum_outdoor_dry_bulb_temperature_for_compressor_operation": {
                    "type": "number",
                    "default": -25.0,
                    "units": "C"
                },
                "maximum_outdoor_dry_bulb_temperature_for_crankcase_heater_operation": {
                    "type": "number",
                    "minimum": 0.0,
                    "default": 10.0,
                    "units": "C"
                },
                "unit_internal_static_air_pressure": {
                    "type": "number",
                    "note": "Enter pressure drop for the unit containing the coil. This value is only used to calculate Energy Efficiency Ratio (EER), Integrated Energy Efficiency Ratio (IEER), and the Standard Rating (Net) Cooling Capacity. This value is not used for modeling the evaporator fan during simulations.",
                    "units": "Pa",
                    "exclusiveMinimum": 0.0
                },
                "capacity_control_method": {
                    "type": "string",
                    "enum": [
                        "",
                        "Continuous",
                        "Discrete"
                    ],
                    "default": "Discrete"
                },
                "evaporative_condenser_basin_heater_capacity": {
                    "type": "number",
                    "note": "This field is only used for Condenser Type = EvaporativelyCooled and for periods when the basin heater is available (field Basin Heater Operating Schedule Name). For this situation, the heater maintains the basin water temperature at the basin heater setpoint temperature when the outdoor air temperature falls below the setpoint temperature. The basin heater only operates when the DX coil is off.",
                    "units": "W/K",
                    "minimum": 0.0,
                    "default": 0.0
                },
                "evaporative_condenser_basin_heater_setpoint_temperature": {
                    "type": "number",
                    "note": "This field is only used for Condenser Type = EvaporativelyCooled. Enter the outdoor dry-bulb temperature when the basin heater turns on.",
                    "units": "C",
                    "minimum": 2.0,
                    "default": 2.0
                },
                "evaporative_condenser_basin_heater_operating_schedule_name": {
                    "type": "string",
                    "note": "This field is only used for Condenser Type = EvaporativelyCooled. Schedule values greater than 0 allow the basin heater to operate whenever the outdoor air dry-bulb temperature is below the basin heater setpoint temperature. If a schedule name is not entered, the basin heater is allowed to operate throughout the entire simulation.",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ]
                },
                "compressor_fuel_type": {
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
                "base_operating_mode": {
                    "type": "string",
                    "note": "Operating Mode 1 is always used as the base design operating mode.",
                    "data_type": "object_list",
                    "object_list": [
                        "DXCoolingOperatingModeNames"
                    ]
                },
                "alternative_operating_mode_1": {
                    "type": "string",
                    "note": "The alternative operating mode is used for enhanced dehumidification. If this is blank, the coil will always operate in the base operating mode. If an alternate mode is defined here, the coil will use the enhanced mode if activated by the parent system controls.",
                    "data_type": "object_list",
                    "object_list": [
                        "DXCoolingOperatingModeNames"
                    ]
                },
                "alternative_operating_mode_2": {
                    "type": "string",
                    "note": "The alternative operating mode is used for enhanced dehumidification. If this is blank, the coil will always operate in the base operating mode or Alternative Mode 1. If both Alternative Operating Mode 1 and Mode 2 are defined here, the coil will perform both Subcool and Reheat modes for enhanced dehumidification. Alternative Operating Mode 1 is used as Subcool mode, and Alternative Operating Mode 2 is used as Reheat mode.",
                    "data_type": "object_list",
                    "object_list": [
                        "DXCoolingOperatingModeNames"
                    ]
                }
            },
            "required": [
                "base_operating_mode"
            ]
        }
    },
    "group": "Coils",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "DXCoolingPerformanceNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "crankcase_heater_capacity": {
                "field_name": "Crankcase Heater Capacity",
                "field_type": "n"
            },
            "minimum_outdoor_dry_bulb_temperature_for_compressor_operation": {
                "field_name": "Minimum Outdoor Dry-Bulb Temperature for Compressor Operation",
                "field_type": "n"
            },
            "maximum_outdoor_dry_bulb_temperature_for_crankcase_heater_operation": {
                "field_name": "Maximum Outdoor Dry-Bulb Temperature for Crankcase Heater Operation",
                "field_type": "n"
            },
            "unit_internal_static_air_pressure": {
                "field_name": "Unit Internal Static Air Pressure",
                "field_type": "n"
            },
            "capacity_control_method": {
                "field_name": "Capacity Control Method",
                "field_type": "a"
            },
            "evaporative_condenser_basin_heater_capacity": {
                "field_name": "Evaporative Condenser Basin Heater Capacity",
                "field_type": "n"
            },
            "evaporative_condenser_basin_heater_setpoint_temperature": {
                "field_name": "Evaporative Condenser Basin Heater Setpoint Temperature",
                "field_type": "n"
            },
            "evaporative_condenser_basin_heater_operating_schedule_name": {
                "field_name": "Evaporative Condenser Basin Heater Operating Schedule Name",
                "field_type": "a"
            },
            "compressor_fuel_type": {
                "field_name": "Compressor Fuel Type",
                "field_type": "a"
            },
            "base_operating_mode": {
                "field_name": "Base Operating Mode",
                "field_type": "a"
            },
            "alternative_operating_mode_1": {
                "field_name": "Alternative Operating Mode 1",
                "field_type": "a"
            },
            "alternative_operating_mode_2": {
                "field_name": "Alternative Operating Mode 2",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "crankcase_heater_capacity",
            "minimum_outdoor_dry_bulb_temperature_for_compressor_operation",
            "maximum_outdoor_dry_bulb_temperature_for_crankcase_heater_operation",
            "unit_internal_static_air_pressure",
            "capacity_control_method",
            "evaporative_condenser_basin_heater_capacity",
            "evaporative_condenser_basin_heater_setpoint_temperature",
            "evaporative_condenser_basin_heater_operating_schedule_name",
            "compressor_fuel_type",
            "base_operating_mode",
            "alternative_operating_mode_1",
            "alternative_operating_mode_2"
        ],
        "alphas": {
            "fields": [
                "name",
                "capacity_control_method",
                "evaporative_condenser_basin_heater_operating_schedule_name",
                "compressor_fuel_type",
                "base_operating_mode",
                "alternative_operating_mode_1",
                "alternative_operating_mode_2"
            ]
        },
        "numerics": {
            "fields": [
                "crankcase_heater_capacity",
                "minimum_outdoor_dry_bulb_temperature_for_compressor_operation",
                "maximum_outdoor_dry_bulb_temperature_for_crankcase_heater_operation",
                "unit_internal_static_air_pressure",
                "evaporative_condenser_basin_heater_capacity",
                "evaporative_condenser_basin_heater_setpoint_temperature"
            ]
        }
    },
    "type": "object",
    "memo": "DX cooling coil performance specification referencing one or more operating modes. Mode 1 is always the base design operating mode. Additional modes are optional states such as subcool reheat for humidity control.",
    "min_fields": 11.0
}
```
