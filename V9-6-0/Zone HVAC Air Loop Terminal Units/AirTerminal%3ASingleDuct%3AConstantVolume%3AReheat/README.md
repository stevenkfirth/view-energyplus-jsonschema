```
{
    "AirTerminal:SingleDuct:ConstantVolume:Reheat": {
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
                    "air_outlet_node_name": {
                        "type": "string"
                    },
                    "air_inlet_node_name": {
                        "type": "string"
                    },
                    "maximum_air_flow_rate": {
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
                    },
                    "maximum_reheat_air_temperature": {
                        "type": "number",
                        "note": "Specifies the maximum allowable supply air temperature leaving the reheat coil. If left blank, there is no limit and no default. If unknown, 35C (95F) is recommended.",
                        "units": "C",
                        "exclusiveMinimum": 0.0
                    }
                },
                "required": [
                    "air_outlet_node_name",
                    "air_inlet_node_name",
                    "maximum_air_flow_rate",
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
                "AFNTerminalUnitNames",
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
                "air_outlet_node_name": {
                    "field_name": "Air Outlet Node Name",
                    "field_type": "a"
                },
                "air_inlet_node_name": {
                    "field_name": "Air Inlet Node Name",
                    "field_type": "a"
                },
                "maximum_air_flow_rate": {
                    "field_name": "Maximum Air Flow Rate",
                    "field_type": "n"
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
                },
                "maximum_reheat_air_temperature": {
                    "field_name": "Maximum Reheat Air Temperature",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "availability_schedule_name",
                "air_outlet_node_name",
                "air_inlet_node_name",
                "maximum_air_flow_rate",
                "reheat_coil_object_type",
                "reheat_coil_name",
                "maximum_hot_water_or_steam_flow_rate",
                "minimum_hot_water_or_steam_flow_rate",
                "convergence_tolerance",
                "maximum_reheat_air_temperature"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "air_outlet_node_name",
                    "air_inlet_node_name",
                    "reheat_coil_object_type",
                    "reheat_coil_name"
                ]
            },
            "numerics": {
                "fields": [
                    "maximum_air_flow_rate",
                    "maximum_hot_water_or_steam_flow_rate",
                    "minimum_hot_water_or_steam_flow_rate",
                    "convergence_tolerance",
                    "maximum_reheat_air_temperature"
                ]
            }
        },
        "type": "object",
        "memo": "Central air system terminal unit, single duct, constant volume, with reheat coil (hot water, electric, gas, or steam)."
    }
}
```
