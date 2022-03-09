```
{
    "AirLoopHVAC:UnitaryHeatPump:AirToAir:MultiSpeed": {
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
                    "controlling_zone_or_thermostat_location": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ]
                    },
                    "supply_air_fan_object_type": {
                        "type": "string",
                        "enum": [
                            "Fan:ConstantVolume",
                            "Fan:OnOff"
                        ],
                        "note": "Select the type of supply air fan used in this unitary system."
                    },
                    "supply_air_fan_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "FansCVandOnOff"
                        ],
                        "note": "Enter the name of the supply air fan used in this unitary system."
                    },
                    "supply_air_fan_placement": {
                        "type": "string",
                        "enum": [
                            "BlowThrough",
                            "DrawThrough"
                        ],
                        "note": "Select supply air fan placement as either BlowThrough or DrawThrough. BlowThrough means the supply air fan is located before the cooling coil. DrawThrough means the supply air fan is located after the heating coil but before the optional supplemental heating coil."
                    },
                    "supply_air_fan_operating_mode_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "Enter the name of a schedule to control the supply air fan. Schedule values of zero mean that the supply air fan will cycle off if there is no cooling or heating load in the control zone. Non-zero schedule values mean that the supply air fan will operate continuously even if there is no cooling or heating load in the control zone. If this field is left blank, the supply air fan will operate continuously for the entire simulation period."
                    },
                    "heating_coil_object_type": {
                        "type": "string",
                        "enum": [
                            "Coil:Heating:DX:MultiSpeed",
                            "Coil:Heating:Electric:MultiStage",
                            "Coil:Heating:Gas:MultiStage",
                            "Coil:Heating:Steam",
                            "Coil:Heating:Water"
                        ],
                        "note": "Multi Speed DX, Electric, Gas, and Single speed Water and Steam coils"
                    },
                    "heating_coil_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "HeatingCoilsDXMultiSpeed",
                            "HeatingCoilsElectricMultiStage",
                            "HeatingCoilsGasMultiStage"
                        ]
                    },
                    "minimum_outdoor_dry_bulb_temperature_for_compressor_operation": {
                        "type": "number",
                        "default": -8.0,
                        "units": "C",
                        "note": "Needs to match the corresponding minimum outdoor temperature defined in the DX heating coil object."
                    },
                    "cooling_coil_object_type": {
                        "type": "string",
                        "enum": [
                            "Coil:Cooling:DX:MultiSpeed"
                        ],
                        "note": "Only works with Coil:Cooling:DX:MultiSpeed"
                    },
                    "cooling_coil_name": {
                        "type": "string",
                        "note": "Needs to match in the DX Cooling Coil object",
                        "data_type": "object_list",
                        "object_list": [
                            "CoolingCoilsDXMultiSpeed"
                        ]
                    },
                    "supplemental_heating_coil_object_type": {
                        "type": "string",
                        "enum": [
                            "Coil:Heating:Electric",
                            "Coil:Heating:Fuel",
                            "Coil:Heating:Steam",
                            "Coil:Heating:Water"
                        ],
                        "note": "works with gas, electric, hot water and steam heating coils"
                    },
                    "supplemental_heating_coil_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "HeatingCoilName"
                        ],
                        "note": "Needs to match in the supplemental heating coil object"
                    },
                    "maximum_supply_air_temperature_from_supplemental_heater": {
                        "units": "C",
                        "anyOf": [
                            {
                                "type": "number"
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "maximum_outdoor_dry_bulb_temperature_for_supplemental_heater_operation": {
                        "type": "number",
                        "maximum": 21.0,
                        "default": 21.0,
                        "units": "C"
                    },
                    "auxiliary_on_cycle_electric_power": {
                        "type": "number",
                        "units": "W",
                        "minimum": 0.0,
                        "default": 0.0
                    },
                    "auxiliary_off_cycle_electric_power": {
                        "type": "number",
                        "units": "W",
                        "minimum": 0.0,
                        "default": 0.0
                    },
                    "design_heat_recovery_water_flow_rate": {
                        "type": "number",
                        "note": "If non-zero, then the heat recovery inlet and outlet node names must be entered. Used for heat recovery to an EnergyPlus plant loop.",
                        "units": "m3/s",
                        "ip-units": "gal/min",
                        "minimum": 0.0,
                        "default": 0.0
                    },
                    "maximum_temperature_for_heat_recovery": {
                        "type": "number",
                        "units": "C",
                        "maximum": 100.0,
                        "minimum": 0.0,
                        "default": 80.0
                    },
                    "heat_recovery_water_inlet_node_name": {
                        "type": "string"
                    },
                    "heat_recovery_water_outlet_node_name": {
                        "type": "string"
                    },
                    "no_load_supply_air_flow_rate": {
                        "units": "m3/s",
                        "note": "Only used when the supply air fan operating mode is continuous (see field Supply Air Fan Operating Mode Schedule Name). This air flow rate is used when no heating or cooling is required and the coils are off. If this field is left blank or zero, the supply air flow rate from the previous on cycle (either cooling or heating) is used.",
                        "anyOf": [
                            {
                                "type": "number",
                                "minimum": 0.0
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "number_of_speeds_for_heating": {
                        "type": "number",
                        "minimum": 1.0,
                        "maximum": 4.0,
                        "note": "Enter the number of the following sets of data for air flow rates. If Heating Coil Object Type is Coil:Heating:Water or Coil:Heating:Steam, this field should be 1."
                    },
                    "number_of_speeds_for_cooling": {
                        "type": "number",
                        "minimum": 2.0,
                        "maximum": 4.0,
                        "note": "Enter the number of the following sets of data for air flow rates."
                    },
                    "heating_speed_1_supply_air_flow_rate": {
                        "units": "m3/s",
                        "note": "Enter the operating supply air flow rate during heating operation or specify autosize.",
                        "anyOf": [
                            {
                                "type": "number",
                                "exclusiveMinimum": 0.0
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "heating_speed_2_supply_air_flow_rate": {
                        "units": "m3/s",
                        "note": "Enter the operating supply air flow rate during heating operation or specify autosize.",
                        "anyOf": [
                            {
                                "type": "number",
                                "exclusiveMinimum": 0.0
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "heating_speed_3_supply_air_flow_rate": {
                        "units": "m3/s",
                        "note": "Enter the operating supply air flow rate during heating operation or specify autosize.",
                        "anyOf": [
                            {
                                "type": "number",
                                "exclusiveMinimum": 0.0
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "heating_speed_4_supply_air_flow_rate": {
                        "units": "m3/s",
                        "note": "Enter the operating supply air flow rate during heating operation or specify autosize.",
                        "anyOf": [
                            {
                                "type": "number",
                                "exclusiveMinimum": 0.0
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "cooling_speed_1_supply_air_flow_rate": {
                        "units": "m3/s",
                        "note": "Enter the operating supply air flow rate during cooling operation or specify autosize.",
                        "anyOf": [
                            {
                                "type": "number",
                                "exclusiveMinimum": 0.0
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "cooling_speed_2_supply_air_flow_rate": {
                        "units": "m3/s",
                        "note": "Enter the operating supply air flow rate during cooling operation or specify autosize.",
                        "anyOf": [
                            {
                                "type": "number",
                                "exclusiveMinimum": 0.0
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "cooling_speed_3_supply_air_flow_rate": {
                        "units": "m3/s",
                        "note": "Enter the operating supply air flow rate during cooling operation or specify autosize.",
                        "anyOf": [
                            {
                                "type": "number",
                                "exclusiveMinimum": 0.0
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "Autosize"
                                ]
                            }
                        ]
                    },
                    "cooling_speed_4_supply_air_flow_rate": {
                        "units": "m3/s",
                        "note": "Enter the operating supply air flow rate during cooling operation or specify autosize.",
                        "anyOf": [
                            {
                                "type": "number",
                                "exclusiveMinimum": 0.0
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "Autosize"
                                ]
                            }
                        ]
                    }
                },
                "required": [
                    "air_inlet_node_name",
                    "air_outlet_node_name",
                    "controlling_zone_or_thermostat_location",
                    "supply_air_fan_object_type",
                    "supply_air_fan_name",
                    "supply_air_fan_placement",
                    "heating_coil_object_type",
                    "heating_coil_name",
                    "cooling_coil_object_type",
                    "cooling_coil_name",
                    "number_of_speeds_for_heating",
                    "number_of_speeds_for_cooling",
                    "heating_speed_1_supply_air_flow_rate",
                    "cooling_speed_1_supply_air_flow_rate",
                    "cooling_speed_2_supply_air_flow_rate"
                ]
            }
        },
        "group": "Unitary Equipment",
        "name": {
            "type": "string",
            "is_required": true,
            "reference-class-name": [
                "validBranchEquipmentTypes"
            ],
            "reference": [
                "validBranchEquipmentNames"
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
                "controlling_zone_or_thermostat_location": {
                    "field_name": "Controlling Zone or Thermostat Location",
                    "field_type": "a"
                },
                "supply_air_fan_object_type": {
                    "field_name": "Supply Air Fan Object Type",
                    "field_type": "a"
                },
                "supply_air_fan_name": {
                    "field_name": "Supply Air Fan Name",
                    "field_type": "a"
                },
                "supply_air_fan_placement": {
                    "field_name": "Supply Air Fan Placement",
                    "field_type": "a"
                },
                "supply_air_fan_operating_mode_schedule_name": {
                    "field_name": "Supply Air Fan Operating Mode Schedule Name",
                    "field_type": "a"
                },
                "heating_coil_object_type": {
                    "field_name": "Heating Coil Object Type",
                    "field_type": "a"
                },
                "heating_coil_name": {
                    "field_name": "Heating Coil Name",
                    "field_type": "a"
                },
                "minimum_outdoor_dry_bulb_temperature_for_compressor_operation": {
                    "field_name": "Minimum Outdoor Dry-Bulb Temperature for Compressor Operation",
                    "field_type": "n"
                },
                "cooling_coil_object_type": {
                    "field_name": "Cooling Coil Object Type",
                    "field_type": "a"
                },
                "cooling_coil_name": {
                    "field_name": "Cooling Coil Name",
                    "field_type": "a"
                },
                "supplemental_heating_coil_object_type": {
                    "field_name": "Supplemental Heating Coil Object Type",
                    "field_type": "a"
                },
                "supplemental_heating_coil_name": {
                    "field_name": "Supplemental Heating Coil Name",
                    "field_type": "a"
                },
                "maximum_supply_air_temperature_from_supplemental_heater": {
                    "field_name": "Maximum Supply Air Temperature from Supplemental Heater",
                    "field_type": "n"
                },
                "maximum_outdoor_dry_bulb_temperature_for_supplemental_heater_operation": {
                    "field_name": "Maximum Outdoor Dry-Bulb Temperature for Supplemental Heater Operation",
                    "field_type": "n"
                },
                "auxiliary_on_cycle_electric_power": {
                    "field_name": "Auxiliary On-Cycle Electric Power",
                    "field_type": "n"
                },
                "auxiliary_off_cycle_electric_power": {
                    "field_name": "Auxiliary Off-Cycle Electric Power",
                    "field_type": "n"
                },
                "design_heat_recovery_water_flow_rate": {
                    "field_name": "Design Heat Recovery Water Flow Rate",
                    "field_type": "n"
                },
                "maximum_temperature_for_heat_recovery": {
                    "field_name": "Maximum Temperature for Heat Recovery",
                    "field_type": "n"
                },
                "heat_recovery_water_inlet_node_name": {
                    "field_name": "Heat Recovery Water Inlet Node Name",
                    "field_type": "a"
                },
                "heat_recovery_water_outlet_node_name": {
                    "field_name": "Heat Recovery Water Outlet Node Name",
                    "field_type": "a"
                },
                "no_load_supply_air_flow_rate": {
                    "field_name": "No Load Supply Air Flow Rate",
                    "field_type": "n"
                },
                "number_of_speeds_for_heating": {
                    "field_name": "Number of Speeds for Heating",
                    "field_type": "n"
                },
                "number_of_speeds_for_cooling": {
                    "field_name": "Number of Speeds for Cooling",
                    "field_type": "n"
                },
                "heating_speed_1_supply_air_flow_rate": {
                    "field_name": "Heating Speed 1 Supply Air Flow Rate",
                    "field_type": "n"
                },
                "heating_speed_2_supply_air_flow_rate": {
                    "field_name": "Heating Speed 2 Supply Air Flow Rate",
                    "field_type": "n"
                },
                "heating_speed_3_supply_air_flow_rate": {
                    "field_name": "Heating Speed 3 Supply Air Flow Rate",
                    "field_type": "n"
                },
                "heating_speed_4_supply_air_flow_rate": {
                    "field_name": "Heating Speed 4 Supply Air Flow Rate",
                    "field_type": "n"
                },
                "cooling_speed_1_supply_air_flow_rate": {
                    "field_name": "Cooling Speed 1 Supply Air Flow Rate",
                    "field_type": "n"
                },
                "cooling_speed_2_supply_air_flow_rate": {
                    "field_name": "Cooling Speed 2 Supply Air Flow Rate",
                    "field_type": "n"
                },
                "cooling_speed_3_supply_air_flow_rate": {
                    "field_name": "Cooling Speed 3 Supply Air Flow Rate",
                    "field_type": "n"
                },
                "cooling_speed_4_supply_air_flow_rate": {
                    "field_name": "Cooling Speed 4 Supply Air Flow Rate",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "availability_schedule_name",
                "air_inlet_node_name",
                "air_outlet_node_name",
                "controlling_zone_or_thermostat_location",
                "supply_air_fan_object_type",
                "supply_air_fan_name",
                "supply_air_fan_placement",
                "supply_air_fan_operating_mode_schedule_name",
                "heating_coil_object_type",
                "heating_coil_name",
                "minimum_outdoor_dry_bulb_temperature_for_compressor_operation",
                "cooling_coil_object_type",
                "cooling_coil_name",
                "supplemental_heating_coil_object_type",
                "supplemental_heating_coil_name",
                "maximum_supply_air_temperature_from_supplemental_heater",
                "maximum_outdoor_dry_bulb_temperature_for_supplemental_heater_operation",
                "auxiliary_on_cycle_electric_power",
                "auxiliary_off_cycle_electric_power",
                "design_heat_recovery_water_flow_rate",
                "maximum_temperature_for_heat_recovery",
                "heat_recovery_water_inlet_node_name",
                "heat_recovery_water_outlet_node_name",
                "no_load_supply_air_flow_rate",
                "number_of_speeds_for_heating",
                "number_of_speeds_for_cooling",
                "heating_speed_1_supply_air_flow_rate",
                "heating_speed_2_supply_air_flow_rate",
                "heating_speed_3_supply_air_flow_rate",
                "heating_speed_4_supply_air_flow_rate",
                "cooling_speed_1_supply_air_flow_rate",
                "cooling_speed_2_supply_air_flow_rate",
                "cooling_speed_3_supply_air_flow_rate",
                "cooling_speed_4_supply_air_flow_rate"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "air_inlet_node_name",
                    "air_outlet_node_name",
                    "controlling_zone_or_thermostat_location",
                    "supply_air_fan_object_type",
                    "supply_air_fan_name",
                    "supply_air_fan_placement",
                    "supply_air_fan_operating_mode_schedule_name",
                    "heating_coil_object_type",
                    "heating_coil_name",
                    "cooling_coil_object_type",
                    "cooling_coil_name",
                    "supplemental_heating_coil_object_type",
                    "supplemental_heating_coil_name",
                    "heat_recovery_water_inlet_node_name",
                    "heat_recovery_water_outlet_node_name"
                ]
            },
            "numerics": {
                "fields": [
                    "minimum_outdoor_dry_bulb_temperature_for_compressor_operation",
                    "maximum_supply_air_temperature_from_supplemental_heater",
                    "maximum_outdoor_dry_bulb_temperature_for_supplemental_heater_operation",
                    "auxiliary_on_cycle_electric_power",
                    "auxiliary_off_cycle_electric_power",
                    "design_heat_recovery_water_flow_rate",
                    "maximum_temperature_for_heat_recovery",
                    "no_load_supply_air_flow_rate",
                    "number_of_speeds_for_heating",
                    "number_of_speeds_for_cooling",
                    "heating_speed_1_supply_air_flow_rate",
                    "heating_speed_2_supply_air_flow_rate",
                    "heating_speed_3_supply_air_flow_rate",
                    "heating_speed_4_supply_air_flow_rate",
                    "cooling_speed_1_supply_air_flow_rate",
                    "cooling_speed_2_supply_air_flow_rate",
                    "cooling_speed_3_supply_air_flow_rate",
                    "cooling_speed_4_supply_air_flow_rate"
                ]
            }
        },
        "type": "object",
        "memo": "Unitary system, heating and cooling, multi-speed with constant volume supply fan (continuous or cycling), direct expansion (DX) cooling coil, heating coil (DX air-to-air heat pump, gas, electric, hot water, or steam), and supplemental heating coil (gas, electric, hot water, or steam).",
        "min_fields": 31.0
    }
}
```
