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
                "maximum_total_air_flow_rate": {
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
                "induction_ratio": {
                    "type": "number",
                    "minimum": 0.0,
                    "default": 2.5,
                    "note": "ratio of induced air flow rate to primary air flow rate"
                },
                "supply_air_inlet_node_name": {
                    "type": "string"
                },
                "induced_air_inlet_node_name": {
                    "type": "string",
                    "note": "should be a zone exhaust node, also the heating coil inlet node"
                },
                "air_outlet_node_name": {
                    "type": "string",
                    "note": "should be a zone inlet node"
                },
                "heating_coil_object_type": {
                    "type": "string",
                    "enum": [
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
                "maximum_hot_water_flow_rate": {
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
                "minimum_hot_water_flow_rate": {
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
                "cooling_coil_object_type": {
                    "type": "string",
                    "enum": [
                        "Coil:Cooling:Water",
                        "Coil:Cooling:Water:DetailedGeometry"
                    ]
                },
                "cooling_coil_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "CoolingCoilName"
                    ]
                },
                "maximum_cold_water_flow_rate": {
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
                "minimum_cold_water_flow_rate": {
                    "type": "number",
                    "units": "m3/s",
                    "minimum": 0.0,
                    "default": 0.0,
                    "ip-units": "gal/min"
                },
                "cooling_convergence_tolerance": {
                    "type": "number",
                    "exclusiveMinimum": 0.0,
                    "default": 0.001
                },
                "zone_mixer_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneMixers"
                    ]
                }
            },
            "required": [
                "maximum_total_air_flow_rate",
                "supply_air_inlet_node_name",
                "induced_air_inlet_node_name",
                "air_outlet_node_name",
                "heating_coil_object_type",
                "heating_coil_name",
                "zone_mixer_name"
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
            "maximum_total_air_flow_rate": {
                "field_name": "Maximum Total Air Flow Rate",
                "field_type": "n"
            },
            "induction_ratio": {
                "field_name": "Induction Ratio",
                "field_type": "n"
            },
            "supply_air_inlet_node_name": {
                "field_name": "Supply Air Inlet Node Name",
                "field_type": "a"
            },
            "induced_air_inlet_node_name": {
                "field_name": "Induced Air Inlet Node Name",
                "field_type": "a"
            },
            "air_outlet_node_name": {
                "field_name": "Air Outlet Node Name",
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
            "maximum_hot_water_flow_rate": {
                "field_name": "Maximum Hot Water Flow Rate",
                "field_type": "n"
            },
            "minimum_hot_water_flow_rate": {
                "field_name": "Minimum Hot Water Flow Rate",
                "field_type": "n"
            },
            "heating_convergence_tolerance": {
                "field_name": "Heating Convergence Tolerance",
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
            "maximum_cold_water_flow_rate": {
                "field_name": "Maximum Cold Water Flow Rate",
                "field_type": "n"
            },
            "minimum_cold_water_flow_rate": {
                "field_name": "Minimum Cold Water Flow Rate",
                "field_type": "n"
            },
            "cooling_convergence_tolerance": {
                "field_name": "Cooling Convergence Tolerance",
                "field_type": "n"
            },
            "zone_mixer_name": {
                "field_name": "Zone Mixer Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "availability_schedule_name",
            "maximum_total_air_flow_rate",
            "induction_ratio",
            "supply_air_inlet_node_name",
            "induced_air_inlet_node_name",
            "air_outlet_node_name",
            "heating_coil_object_type",
            "heating_coil_name",
            "maximum_hot_water_flow_rate",
            "minimum_hot_water_flow_rate",
            "heating_convergence_tolerance",
            "cooling_coil_object_type",
            "cooling_coil_name",
            "maximum_cold_water_flow_rate",
            "minimum_cold_water_flow_rate",
            "cooling_convergence_tolerance",
            "zone_mixer_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "availability_schedule_name",
                "supply_air_inlet_node_name",
                "induced_air_inlet_node_name",
                "air_outlet_node_name",
                "heating_coil_object_type",
                "heating_coil_name",
                "cooling_coil_object_type",
                "cooling_coil_name",
                "zone_mixer_name"
            ]
        },
        "numerics": {
            "fields": [
                "maximum_total_air_flow_rate",
                "induction_ratio",
                "maximum_hot_water_flow_rate",
                "minimum_hot_water_flow_rate",
                "heating_convergence_tolerance",
                "maximum_cold_water_flow_rate",
                "minimum_cold_water_flow_rate",
                "cooling_convergence_tolerance"
            ]
        }
    },
    "type": "object",
    "memo": "Central air system terminal unit, single duct, variable volume, induction unit with hot water reheat coil and chilled water recool coil.",
    "min_fields": 18.0
}
```
