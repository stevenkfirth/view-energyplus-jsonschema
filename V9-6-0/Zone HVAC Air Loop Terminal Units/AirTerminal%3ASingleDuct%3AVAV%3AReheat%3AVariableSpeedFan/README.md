```
{
    "AirTerminal:SingleDuct:VAV:Reheat:VariableSpeedFan": {
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
                    "maximum_cooling_air_flow_rate": {
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
                    "maximum_heating_air_flow_rate": {
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
                    "zone_minimum_air_flow_fraction": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0,
                        "note": "fraction of cooling air flow rate"
                    },
                    "air_inlet_node_name": {
                        "type": "string",
                        "note": "The name of the HVAC system node that is the air inlet node for the terminal unit. This is also the air inlet node for the unit's fan."
                    },
                    "air_outlet_node_name": {
                        "type": "string",
                        "note": "The name of the HVAC system node that is the air outlet node for the terminal unit. This is also the air outlet node for the unit's heating coil's air outlet node. This node is also a zone inlet node."
                    },
                    "fan_object_type": {
                        "type": "string",
                        "enum": [
                            "Fan:SystemModel",
                            "Fan:VariableVolume"
                        ]
                    },
                    "fan_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "FansSystemModel",
                            "FansVAV"
                        ]
                    },
                    "heating_coil_object_type": {
                        "type": "string",
                        "enum": [
                            "Coil:Heating:Electric",
                            "Coil:Heating:Fuel",
                            "Coil:Heating:Steam",
                            "Coil:Heating:Water"
                        ]
                    },
                    "heating_coil_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "HeatingCoilName"
                        ]
                    },
                    "maximum_hot_water_or_steam_flow_rate": {
                        "note": "Not used when heating coil type is gas or electric",
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
                        "note": "Not used when heating coil type is gas or electric",
                        "units": "m3/s",
                        "minimum": 0.0,
                        "default": 0.0,
                        "ip-units": "gal/min"
                    },
                    "heating_convergence_tolerance": {
                        "type": "number",
                        "exclusiveMinimum": 0.0,
                        "default": 0.001
                    },
                    "minimum_air_flow_turndown_schedule_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ScheduleNames"
                        ],
                        "note": "This field adjusts the fan-off minimum flow rate by multiplying it using this scheduled fraction values. This field is used with \"Zone Minimum Air Flow Fraction\". Schedule values are fractions 0.0 to 1.0. This field adjusts the minimum airflow turndown below the design minimum air flow and is intended for use with ASHRAE Standard 170. If this field is left blank, then the turndown minimum air flow fraction value is set to 1 and the model uses the fixed fraction specified in in the field \"Zone Minimum Air Flow Fraction\"."
                    }
                },
                "required": [
                    "maximum_cooling_air_flow_rate",
                    "maximum_heating_air_flow_rate",
                    "zone_minimum_air_flow_fraction",
                    "fan_object_type",
                    "fan_name",
                    "heating_coil_object_type",
                    "heating_coil_name"
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
                "maximum_cooling_air_flow_rate": {
                    "field_name": "Maximum Cooling Air Flow Rate",
                    "field_type": "n"
                },
                "maximum_heating_air_flow_rate": {
                    "field_name": "Maximum Heating Air Flow Rate",
                    "field_type": "n"
                },
                "zone_minimum_air_flow_fraction": {
                    "field_name": "Zone Minimum Air Flow Fraction",
                    "field_type": "n"
                },
                "air_inlet_node_name": {
                    "field_name": "Air Inlet Node Name",
                    "field_type": "a"
                },
                "air_outlet_node_name": {
                    "field_name": "Air Outlet Node Name",
                    "field_type": "a"
                },
                "fan_object_type": {
                    "field_name": "Fan Object Type",
                    "field_type": "a"
                },
                "fan_name": {
                    "field_name": "Fan Name",
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
                "maximum_hot_water_or_steam_flow_rate": {
                    "field_name": "Maximum Hot Water or Steam Flow Rate",
                    "field_type": "n"
                },
                "minimum_hot_water_or_steam_flow_rate": {
                    "field_name": "Minimum Hot Water or Steam Flow Rate",
                    "field_type": "n"
                },
                "heating_convergence_tolerance": {
                    "field_name": "Heating Convergence Tolerance",
                    "field_type": "n"
                },
                "minimum_air_flow_turndown_schedule_name": {
                    "field_name": "Minimum Air Flow Turndown Schedule Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "availability_schedule_name",
                "maximum_cooling_air_flow_rate",
                "maximum_heating_air_flow_rate",
                "zone_minimum_air_flow_fraction",
                "air_inlet_node_name",
                "air_outlet_node_name",
                "fan_object_type",
                "fan_name",
                "heating_coil_object_type",
                "heating_coil_name",
                "maximum_hot_water_or_steam_flow_rate",
                "minimum_hot_water_or_steam_flow_rate",
                "heating_convergence_tolerance",
                "minimum_air_flow_turndown_schedule_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "air_inlet_node_name",
                    "air_outlet_node_name",
                    "fan_object_type",
                    "fan_name",
                    "heating_coil_object_type",
                    "heating_coil_name",
                    "minimum_air_flow_turndown_schedule_name"
                ]
            },
            "numerics": {
                "fields": [
                    "maximum_cooling_air_flow_rate",
                    "maximum_heating_air_flow_rate",
                    "zone_minimum_air_flow_fraction",
                    "maximum_hot_water_or_steam_flow_rate",
                    "minimum_hot_water_or_steam_flow_rate",
                    "heating_convergence_tolerance"
                ]
            }
        },
        "type": "object",
        "memo": "Central air system terminal unit, single duct, variable volume, with reheat coil (hot water, electric, gas, or steam) and variable-speed fan. These units are usually employed in underfloor air distribution (UFAD) systems where the air is supplied at low static pressure through an underfloor plenum. The fan is used to control the flow of conditioned air that enters the space."
    }
}
```
