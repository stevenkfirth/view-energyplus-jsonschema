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
                    "note": "A fan operating mode schedule value of 0 indicates cycling fan mode (supply air fan cycles on and off in tandem with the heating coil). Any other schedule value indicates continuous fan mode (supply air fan operates continuously regardless of heating coil operation). Leaving this schedule name blank will default to cycling fan mode for the entire simulation period."
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
                "heating_supply_air_flow_rate": {
                    "note": "This value should be > 0 and <= than the fan air flow rate.",
                    "units": "m3/s",
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
                    "note": "Fan:ConstantVolume only works with continuous fan operating mode (i.e. fan operating mode schedule values are greater than 0)."
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
                }
            },
            "required": [
                "unitary_system_air_inlet_node_name",
                "unitary_system_air_outlet_node_name",
                "heating_supply_air_flow_rate",
                "controlling_zone_or_thermostat_location",
                "supply_fan_object_type",
                "supply_fan_name",
                "heating_coil_object_type",
                "heating_coil_name"
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
            "heating_supply_air_flow_rate": {
                "field_name": "Heating Supply Air Flow Rate",
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
            }
        },
        "fields": [
            "name",
            "availability_schedule_name",
            "unitary_system_air_inlet_node_name",
            "unitary_system_air_outlet_node_name",
            "supply_air_fan_operating_mode_schedule_name",
            "maximum_supply_air_temperature",
            "heating_supply_air_flow_rate",
            "controlling_zone_or_thermostat_location",
            "supply_fan_object_type",
            "supply_fan_name",
            "fan_placement",
            "heating_coil_object_type",
            "heating_coil_name"
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
                "heating_coil_name"
            ]
        },
        "numerics": {
            "fields": [
                "maximum_supply_air_temperature",
                "heating_supply_air_flow_rate"
            ]
        }
    },
    "type": "object",
    "memo": "Unitary system, heating-only with constant volume supply fan (continuous or cycling) and heating coil (gas, electric, hot water, or steam). Identical to AirLoopHVAC:Unitary:Furnace:HeatOnly.",
    "min_fields": 13.0
}
```
