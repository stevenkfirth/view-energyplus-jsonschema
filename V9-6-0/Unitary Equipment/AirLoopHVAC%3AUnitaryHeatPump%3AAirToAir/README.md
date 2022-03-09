```
{
    "AirLoopHVAC:UnitaryHeatPump:AirToAir": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "availability_schedule_name": {
                        "type": "string",
                        "note": "Availability schedule name for this system. Schedule value > 0 means the system is available. If this field is blank, the system is always available. A schedule value greater than zero (usually 1 is used) indicates that the unit is available to operate as needed. A value less than or equal to zero (usually zero is used) denotes that the unit must be off.",
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
                    "cooling_supply_air_flow_rate": {
                        "units": "m3/s",
                        "note": "Must be less than or equal to the fan's maximum flow rate.",
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
                    "heating_supply_air_flow_rate": {
                        "units": "m3/s",
                        "note": "Must be less than or equal to the fan's maximum flow rate.",
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
                    "no_load_supply_air_flow_rate": {
                        "units": "m3/s",
                        "note": "Must be less than or equal to the fan's maximum flow rate. Only used when fan operating mode is continuous (disregarded for cycling fan mode). This air flow rate is used when no heating or cooling is required (i.e., the DX coil compressor and supplemental heating coil are off). If this field is left blank or zero, the supply air flow rate from the previous on cycle (either cooling or heating) is used.",
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
                        "note": "Fan:ConstantVolume only works with continuous fan operating mode (i.e. fan operating mode schedule values are greater than 0 or the fan operating mode schedule name field is left blank)."
                    },
                    "supply_air_fan_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "FansCVandOnOff"
                        ],
                        "note": "Needs to match in the fan object"
                    },
                    "heating_coil_object_type": {
                        "type": "string",
                        "enum": [
                            "Coil:Heating:DX:SingleSpeed",
                            "Coil:Heating:DX:VariableSpeed",
                            "CoilSystem:IntegratedHeatPump:AirSource"
                        ],
                        "note": "Only works with Coil:Heating:DX:SingleSpeed or Coil:Heating:DX:VariableSpeed or CoilSystem:IntegratedHeatPump:AirSource"
                    },
                    "heating_coil_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "HeatingCoilsDXSingleSpeed",
                            "HeatingCoilsDXVariableSpeed",
                            "IntegratedHeatPumps"
                        ],
                        "note": "Needs to match in the DX heating coil object"
                    },
                    "cooling_coil_object_type": {
                        "type": "string",
                        "enum": [
                            "Coil:Cooling:DX:SingleSpeed",
                            "Coil:Cooling:DX:VariableSpeed",
                            "CoilSystem:Cooling:DX:HeatExchangerAssisted",
                            "CoilSystem:IntegratedHeatPump:AirSource"
                        ],
                        "note": "Only works with Coil:Cooling:DX:SingleSpeed or CoilSystem:Cooling:DX:HeatExchangerAssisted or Coil:Cooling:DX:VariableSpeed or CoilSystem:IntegratedHeatPump:AirSource"
                    },
                    "cooling_coil_name": {
                        "type": "string",
                        "note": "Needs to match in the DX cooling coil object",
                        "data_type": "object_list",
                        "object_list": [
                            "CoolingCoilsDXSingleSpeed",
                            "CoolingCoilsDXVariableSpeed",
                            "IntegratedHeatPumps"
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
                    "fan_placement": {
                        "type": "string",
                        "enum": [
                            "",
                            "BlowThrough",
                            "DrawThrough"
                        ],
                        "default": "BlowThrough"
                    },
                    "supply_air_fan_operating_mode_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "A fan operating mode schedule value of 0 indicates cycling fan mode (supply air fan cycles on and off in tandem with the cooling or heating coil). Any other schedule value indicates continuous fan mode (supply air fan operates continuously regardless of cooling or heating coil operation). Leaving this schedule name blank will default to cycling fan mode for the entire simulation period."
                    },
                    "dehumidification_control_type": {
                        "type": "string",
                        "enum": [
                            "",
                            "CoolReheat",
                            "Multimode",
                            "None"
                        ],
                        "default": "None",
                        "note": "None = meet sensible load only Multimode = activate enhanced dehumidification mode as needed and meet sensible load. Valid only with cooling coil type CoilSystem:Cooling:DX:HeatExchangerAssisted. This control mode allows the heat exchanger to be turned on and off based on the zone dehumidification requirements. A ZoneControl:Humidistat object is also required. CoolReheat = cool beyond the dry-bulb setpoint. as required to meet the humidity setpoint. Valid with all cooling coil types. When a heat exchanger assisted Cooling coil is used, the heat exchanger is locked on at all times. A ZoneControl:Humidistat object is also required."
                    }
                },
                "required": [
                    "air_inlet_node_name",
                    "air_outlet_node_name",
                    "cooling_supply_air_flow_rate",
                    "heating_supply_air_flow_rate",
                    "controlling_zone_or_thermostat_location",
                    "supply_air_fan_object_type",
                    "supply_air_fan_name",
                    "heating_coil_object_type",
                    "heating_coil_name",
                    "cooling_coil_object_type",
                    "cooling_coil_name",
                    "supplemental_heating_coil_object_type",
                    "supplemental_heating_coil_name",
                    "maximum_supply_air_temperature_from_supplemental_heater"
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
                "heating_coil_object_type": {
                    "field_name": "Heating Coil Object Type",
                    "field_type": "a"
                },
                "heating_coil_name": {
                    "field_name": "Heating Coil Name",
                    "field_type": "a"
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
                "fan_placement": {
                    "field_name": "Fan Placement",
                    "field_type": "a"
                },
                "supply_air_fan_operating_mode_schedule_name": {
                    "field_name": "Supply Air Fan Operating Mode Schedule Name",
                    "field_type": "a"
                },
                "dehumidification_control_type": {
                    "field_name": "Dehumidification Control Type",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "availability_schedule_name",
                "air_inlet_node_name",
                "air_outlet_node_name",
                "cooling_supply_air_flow_rate",
                "heating_supply_air_flow_rate",
                "no_load_supply_air_flow_rate",
                "controlling_zone_or_thermostat_location",
                "supply_air_fan_object_type",
                "supply_air_fan_name",
                "heating_coil_object_type",
                "heating_coil_name",
                "cooling_coil_object_type",
                "cooling_coil_name",
                "supplemental_heating_coil_object_type",
                "supplemental_heating_coil_name",
                "maximum_supply_air_temperature_from_supplemental_heater",
                "maximum_outdoor_dry_bulb_temperature_for_supplemental_heater_operation",
                "fan_placement",
                "supply_air_fan_operating_mode_schedule_name",
                "dehumidification_control_type"
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
                    "heating_coil_object_type",
                    "heating_coil_name",
                    "cooling_coil_object_type",
                    "cooling_coil_name",
                    "supplemental_heating_coil_object_type",
                    "supplemental_heating_coil_name",
                    "fan_placement",
                    "supply_air_fan_operating_mode_schedule_name",
                    "dehumidification_control_type"
                ]
            },
            "numerics": {
                "fields": [
                    "cooling_supply_air_flow_rate",
                    "heating_supply_air_flow_rate",
                    "no_load_supply_air_flow_rate",
                    "maximum_supply_air_temperature_from_supplemental_heater",
                    "maximum_outdoor_dry_bulb_temperature_for_supplemental_heater_operation"
                ]
            }
        },
        "type": "object",
        "memo": "Unitary heat pump system, heating and cooling, single-speed with supply fan, direct expansion (DX) cooling coil, DX heating coil (air-to-air heat pump), and supplemental heating coil (gas, electric, hot water, or steam).",
        "min_fields": 19.0
    }
}
```
