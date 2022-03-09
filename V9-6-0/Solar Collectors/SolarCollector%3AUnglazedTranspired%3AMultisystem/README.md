```
{
    "SolarCollector:UnglazedTranspired:Multisystem": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "solar_collector_name": {
                        "type": "string",
                        "note": "Enter the name of a SolarCollector:UnglazedTranspired object.",
                        "data_type": "object_list",
                        "object_list": [
                            "UTSCNames"
                        ]
                    },
                    "systems": {
                        "type": "array",
                        "items": {
                            "properties": {
                                "outdoor_air_system_collector_inlet_node": {
                                    "type": "string"
                                },
                                "outdoor_air_system_collector_outlet_node": {
                                    "type": "string"
                                },
                                "outdoor_air_system_mixed_air_node": {
                                    "type": "string"
                                },
                                "outdoor_air_system_zone_node": {
                                    "type": "string"
                                }
                            },
                            "type": "object"
                        }
                    }
                },
                "required": [
                    "solar_collector_name"
                ]
            }
        },
        "group": "Solar Collectors",
        "legacy_idd": {
            "field_info": {
                "solar_collector_name": {
                    "field_name": "Solar Collector Name",
                    "field_type": "a"
                },
                "outdoor_air_system_collector_inlet_node": {
                    "field_name": "Outdoor Air System Collector Inlet Node",
                    "field_type": "a"
                },
                "outdoor_air_system_collector_outlet_node": {
                    "field_name": "Outdoor Air System Collector Outlet Node",
                    "field_type": "a"
                },
                "outdoor_air_system_mixed_air_node": {
                    "field_name": "Outdoor Air System Mixed Air Node",
                    "field_type": "a"
                },
                "outdoor_air_system_zone_node": {
                    "field_name": "Outdoor Air System Zone Node",
                    "field_type": "a"
                }
            },
            "fields": [
                "solar_collector_name"
            ],
            "alphas": {
                "fields": [
                    "solar_collector_name"
                ],
                "extensions": [
                    "outdoor_air_system_collector_inlet_node",
                    "outdoor_air_system_collector_outlet_node",
                    "outdoor_air_system_mixed_air_node",
                    "outdoor_air_system_zone_node"
                ]
            },
            "numerics": {
                "fields": []
            },
            "extensibles": [
                "outdoor_air_system_collector_inlet_node",
                "outdoor_air_system_collector_outlet_node",
                "outdoor_air_system_mixed_air_node",
                "outdoor_air_system_zone_node"
            ],
            "extension": "systems"
        },
        "type": "object",
        "memo": "quad-tuples of inlet, outlet, control, and zone nodes for multiple different outdoor air systems attached to same collector",
        "extensible_size": 4.0
    }
}
```
