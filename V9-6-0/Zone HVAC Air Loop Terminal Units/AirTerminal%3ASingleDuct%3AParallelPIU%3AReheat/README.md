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
                "maximum_primary_air_flow_rate": {
                    "units": "m3/s",
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
                "maximum_secondary_air_flow_rate": {
                    "units": "m3/s",
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
                "minimum_primary_air_flow_fraction": {
                    "note": "When set to autosize, the calculated air flow is determined based on the System Outdoor Air Method used in the air loop's Sizing:System object.",
                    "anyOf": [
                        {
                            "type": "number",
                            "minimum": 0.0,
                            "maximum": 1.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "Autosize"
                            ]
                        }
                    ]
                },
                "fan_on_flow_fraction": {
                    "note": "the fraction of the primary air flow at which fan turns on",
                    "anyOf": [
                        {
                            "type": "number",
                            "minimum": 0.0,
                            "maximum": 1.0
                        },
                        {
                            "type": "string",
                            "enum": [
                                "Autosize"
                            ]
                        }
                    ]
                },
                "supply_air_inlet_node_name": {
                    "type": "string"
                },
                "secondary_air_inlet_node_name": {
                    "type": "string"
                },
                "outlet_node_name": {
                    "type": "string"
                },
                "reheat_coil_air_inlet_node_name": {
                    "type": "string",
                    "note": "mixer outlet node"
                },
                "zone_mixer_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneMixers"
                    ]
                },
                "fan_name": {
                    "type": "string",
                    "note": "Fan type must be Fan:SystemModel or Fan:ConstantVolume",
                    "data_type": "object_list",
                    "object_list": [
                        "FansCV",
                        "FansSystemModel"
                    ]
                },
                "reheat_coil_object_type": {
                    "type": "string",
                    "enum": [
                        "Coil:Heating:Electric",
                        "Coil:Heating:Fuel",
                        "Coil:Heating:Steam",
                        "Coil:Heating:Water"
                    ]
                },
                "reheat_coil_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "HeatingCoilName"
                    ]
                },
                "maximum_hot_water_or_steam_flow_rate": {
                    "note": "Not used when reheat coil type is gas or electric",
                    "units": "m3/s",
                    "ip-units": "gal/min",
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
                "minimum_hot_water_or_steam_flow_rate": {
                    "type": "number",
                    "note": "Not used when reheat coil type is gas or electric",
                    "units": "m3/s",
                    "minimum": 0.0,
                    "default": 0.0,
                    "ip-units": "gal/min"
                },
                "convergence_tolerance": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "default": 0.001
                }
            },
            "required": [
                "maximum_primary_air_flow_rate",
                "maximum_secondary_air_flow_rate",
                "minimum_primary_air_flow_fraction",
                "fan_on_flow_fraction",
                "reheat_coil_object_type",
                "reheat_coil_name"
            ]
        }
    },
    "group": "Zone HVAC Air Loop Terminal Units",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "AirTerminalUnitNames"
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
            "maximum_primary_air_flow_rate": {
                "field_name": "Maximum Primary Air Flow Rate",
                "field_type": "n"
            },
            "maximum_secondary_air_flow_rate": {
                "field_name": "Maximum Secondary Air Flow Rate",
                "field_type": "n"
            },
            "minimum_primary_air_flow_fraction": {
                "field_name": "Minimum Primary Air Flow Fraction",
                "field_type": "n"
            },
            "fan_on_flow_fraction": {
                "field_name": "Fan On Flow Fraction",
                "field_type": "n"
            },
            "supply_air_inlet_node_name": {
                "field_name": "Supply Air Inlet Node Name",
                "field_type": "a"
            },
            "secondary_air_inlet_node_name": {
                "field_name": "Secondary Air Inlet Node Name",
                "field_type": "a"
            },
            "outlet_node_name": {
                "field_name": "Outlet Node Name",
                "field_type": "a"
            },
            "reheat_coil_air_inlet_node_name": {
                "field_name": "Reheat Coil Air Inlet Node Name",
                "field_type": "a"
            },
            "zone_mixer_name": {
                "field_name": "Zone Mixer Name",
                "field_type": "a"
            },
            "fan_name": {
                "field_name": "Fan Name",
                "field_type": "a"
            },
            "reheat_coil_object_type": {
                "field_name": "Reheat Coil Object Type",
                "field_type": "a"
            },
            "reheat_coil_name": {
                "field_name": "Reheat Coil Name",
                "field_type": "a"
            },
            "maximum_hot_water_or_steam_flow_rate": {
                "field_name": "Maximum Hot Water or Steam Flow Rate",
                "field_type": "n"
            },
            "minimum_hot_water_or_steam_flow_rate": {
                "field_name": "Minimum Hot Water or Steam Flow Rate",
                "field_type": "n"
            },
            "convergence_tolerance": {
                "field_name": "Convergence Tolerance",
                "field_type": "n"
            }
        },
        "fields": [
            "name",
            "availability_schedule_name",
            "maximum_primary_air_flow_rate",
            "maximum_secondary_air_flow_rate",
            "minimum_primary_air_flow_fraction",
            "fan_on_flow_fraction",
            "supply_air_inlet_node_name",
            "secondary_air_inlet_node_name",
            "outlet_node_name",
            "reheat_coil_air_inlet_node_name",
            "zone_mixer_name",
            "fan_name",
            "reheat_coil_object_type",
            "reheat_coil_name",
            "maximum_hot_water_or_steam_flow_rate",
            "minimum_hot_water_or_steam_flow_rate",
            "convergence_tolerance"
        ],
        "alphas": {
            "fields": [
                "name",
                "availability_schedule_name",
                "supply_air_inlet_node_name",
                "secondary_air_inlet_node_name",
                "outlet_node_name",
                "reheat_coil_air_inlet_node_name",
                "zone_mixer_name",
                "fan_name",
                "reheat_coil_object_type",
                "reheat_coil_name"
            ]
        },
        "numerics": {
            "fields": [
                "maximum_primary_air_flow_rate",
                "maximum_secondary_air_flow_rate",
                "minimum_primary_air_flow_fraction",
                "fan_on_flow_fraction",
                "maximum_hot_water_or_steam_flow_rate",
                "minimum_hot_water_or_steam_flow_rate",
                "convergence_tolerance"
            ]
        }
    },
    "type": "object",
    "memo": "Central air system terminal unit, single duct, variable volume, parallel powered induction unit (PIU), with reheat coil (hot water, electric, gas, or steam)."
}
```
