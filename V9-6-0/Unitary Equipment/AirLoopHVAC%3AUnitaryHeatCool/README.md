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
                "unitary_system_air_inlet_node_name": {
                    "type": "string"
                },
                "unitary_system_air_outlet_node_name": {
                    "type": "string"
                },
                "supply_air_fan_operating_mode_schedule_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ScheduleNames"
                    ],
                    "note": "A fan operating mode schedule value of 0 indicates cycling fan mode (supply air fan cycles on and off in tandem with the cooling or heating coil). Any other schedule value indicates continuous fan mode (supply air fan operates continuously regardless of cooling or heating coil operation). Provide a schedule with non-zero values when high humidity control is specified. Leaving this schedule name blank will default to cycling fan mode for the entire simulation period."
                },
                "maximum_supply_air_temperature": {
                    "units": "C",
                    "default": 80.0,
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
                    "note": "Must be less than or equal to the fan's maximum flow rate. Only used when fan operating mode is continuous (disregarded for cycling fan mode). This air flow rate is used when no heating or cooling is required (i.e., the DX coil compressor and heating coil are off). If this field is left blank or zero, the supply air flow rate from the previous on cycle (either cooling or heating) is used.",
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
                "supply_fan_object_type": {
                    "type": "string",
                    "enum": [
                        "Fan:ConstantVolume",
                        "Fan:OnOff"
                    ],
                    "note": "Fan:ConstantVolume only works with continuous fan operating mode (i.e. supply air fan operating mode schedule values not equal to 0)."
                },
                "supply_fan_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "FansCVandOnOff"
                    ]
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
                "heating_coil_object_type": {
                    "type": "string",
                    "enum": [
                        "Coil:Heating:Electric",
                        "Coil:Heating:Fuel",
                        "Coil:Heating:Steam",
                        "Coil:Heating:Water"
                    ],
                    "note": "works with gas, electric, hot water and steam heating coils"
                },
                "heating_coil_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "HeatingCoilName"
                    ]
                },
                "cooling_coil_object_type": {
                    "type": "string",
                    "enum": [
                        "Coil:Cooling:DX:SingleSpeed",
                        "Coil:Cooling:DX:VariableSpeed",
                        "CoilSystem:Cooling:DX:HeatExchangerAssisted"
                    ],
                    "note": "Only works with DX cooling coil types or Coil:Cooling:DX:VariableSpeed."
                },
                "cooling_coil_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "CoolingCoilsDXSingleSpeed",
                        "CoolingCoilsDXVariableSpeed"
                    ]
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
                },
                "reheat_coil_object_type": {
                    "type": "string",
                    "enum": [
                        "Coil:Heating:Desuperheater",
                        "Coil:Heating:Electric",
                        "Coil:Heating:Fuel",
                        "Coil:Heating:Steam",
                        "Coil:Heating:Water"
                    ],
                    "note": "Only required if dehumidification control type is \"CoolReheat\" works with gas, electric, desuperheating, hot water and steam heating coils"
                },
                "reheat_coil_name": {
                    "type": "string",
                    "note": "Only required if dehumidification control type is \"CoolReheat\"",
                    "data_type": "object_list",
                    "object_list": [
                        "HeatingCoilName"
                    ]
                }
            },
            "required": [
                "unitary_system_air_inlet_node_name",
                "unitary_system_air_outlet_node_name",
                "cooling_supply_air_flow_rate",
                "heating_supply_air_flow_rate",
                "controlling_zone_or_thermostat_location",
                "supply_fan_object_type",
                "supply_fan_name",
                "heating_coil_object_type",
                "heating_coil_name",
                "cooling_coil_object_type",
                "cooling_coil_name"
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
            "unitary_system_air_inlet_node_name": {
                "field_name": "Unitary System Air Inlet Node Name",
                "field_type": "a"
            },
            "unitary_system_air_outlet_node_name": {
                "field_name": "Unitary System Air Outlet Node Name",
                "field_type": "a"
            },
            "supply_air_fan_operating_mode_schedule_name": {
                "field_name": "Supply Air Fan Operating Mode Schedule Name",
                "field_type": "a"
            },
            "maximum_supply_air_temperature": {
                "field_name": "Maximum Supply Air Temperature",
                "field_type": "n"
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
            "supply_fan_object_type": {
                "field_name": "Supply Fan Object Type",
                "field_type": "a"
            },
            "supply_fan_name": {
                "field_name": "Supply Fan Name",
                "field_type": "a"
            },
            "fan_placement": {
                "field_name": "Fan Placement",
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
            "dehumidification_control_type": {
                "field_name": "Dehumidification Control Type",
                "field_type": "a"
            },
            "reheat_coil_object_type": {
                "field_name": "Reheat Coil Object Type",
                "field_type": "a"
            },
            "reheat_coil_name": {
                "field_name": "Reheat Coil Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "availability_schedule_name",
            "unitary_system_air_inlet_node_name",
            "unitary_system_air_outlet_node_name",
            "supply_air_fan_operating_mode_schedule_name",
            "maximum_supply_air_temperature",
            "cooling_supply_air_flow_rate",
            "heating_supply_air_flow_rate",
            "no_load_supply_air_flow_rate",
            "controlling_zone_or_thermostat_location",
            "supply_fan_object_type",
            "supply_fan_name",
            "fan_placement",
            "heating_coil_object_type",
            "heating_coil_name",
            "cooling_coil_object_type",
            "cooling_coil_name",
            "dehumidification_control_type",
            "reheat_coil_object_type",
            "reheat_coil_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "availability_schedule_name",
                "unitary_system_air_inlet_node_name",
                "unitary_system_air_outlet_node_name",
                "supply_air_fan_operating_mode_schedule_name",
                "controlling_zone_or_thermostat_location",
                "supply_fan_object_type",
                "supply_fan_name",
                "fan_placement",
                "heating_coil_object_type",
                "heating_coil_name",
                "cooling_coil_object_type",
                "cooling_coil_name",
                "dehumidification_control_type",
                "reheat_coil_object_type",
                "reheat_coil_name"
            ]
        },
        "numerics": {
            "fields": [
                "maximum_supply_air_temperature",
                "cooling_supply_air_flow_rate",
                "heating_supply_air_flow_rate",
                "no_load_supply_air_flow_rate"
            ]
        }
    },
    "type": "object",
    "memo": "Unitary system, heating and cooling with constant volume supply fan (continuous or cycling), direct expansion (DX) cooling coil, heating coil (gas, electric, hot water, or steam), and optional reheat coil for dehumidification control. Identical to AirLoopHVAC:Unitary:Furnace:HeatCool.",
    "min_fields": 17.0
}
```
