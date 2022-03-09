```
{
    "AirTerminal:DualDuct:ConstantVolume": {
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
                        "type": "string",
                        "note": "The outlet node of the terminal unit. This is also the zone inlet node."
                    },
                    "hot_air_inlet_node_name": {
                        "type": "string"
                    },
                    "cold_air_inlet_node_name": {
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
                    }
                },
                "required": [
                    "air_outlet_node_name",
                    "hot_air_inlet_node_name",
                    "cold_air_inlet_node_name",
                    "maximum_air_flow_rate"
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
                "air_outlet_node_name": {
                    "field_name": "Air Outlet Node Name",
                    "field_type": "a"
                },
                "hot_air_inlet_node_name": {
                    "field_name": "Hot Air Inlet Node Name",
                    "field_type": "a"
                },
                "cold_air_inlet_node_name": {
                    "field_name": "Cold Air Inlet Node Name",
                    "field_type": "a"
                },
                "maximum_air_flow_rate": {
                    "field_name": "Maximum Air Flow Rate",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "availability_schedule_name",
                "air_outlet_node_name",
                "hot_air_inlet_node_name",
                "cold_air_inlet_node_name",
                "maximum_air_flow_rate"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "availability_schedule_name",
                    "air_outlet_node_name",
                    "hot_air_inlet_node_name",
                    "cold_air_inlet_node_name"
                ]
            },
            "numerics": {
                "fields": [
                    "maximum_air_flow_rate"
                ]
            }
        },
        "type": "object",
        "memo": "Central air system terminal unit, dual duct, constant volume.",
        "min_fields": 6.0
    }
}
```
