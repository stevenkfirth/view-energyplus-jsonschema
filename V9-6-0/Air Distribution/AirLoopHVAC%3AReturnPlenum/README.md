```
{
    "AirLoopHVAC:ReturnPlenum": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "zone_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ]
                    },
                    "zone_node_name": {
                        "type": "string"
                    },
                    "outlet_node_name": {
                        "type": "string"
                    },
                    "induced_air_outlet_node_or_nodelist_name": {
                        "type": "string"
                    },
                    "nodes": {
                        "type": "array",
                        "items": {
                            "properties": {
                                "inlet_node_name": {
                                    "type": "string"
                                }
                            },
                            "type": "object",
                            "required": [
                                "inlet_node_name"
                            ]
                        }
                    }
                },
                "required": [
                    "zone_name",
                    "zone_node_name",
                    "outlet_node_name"
                ]
            }
        },
        "group": "Air Distribution",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "ReturnPathComponentNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "zone_name": {
                    "field_name": "Zone Name",
                    "field_type": "a"
                },
                "zone_node_name": {
                    "field_name": "Zone Node Name",
                    "field_type": "a"
                },
                "outlet_node_name": {
                    "field_name": "Outlet Node Name",
                    "field_type": "a"
                },
                "induced_air_outlet_node_or_nodelist_name": {
                    "field_name": "Induced Air Outlet Node or NodeList Name",
                    "field_type": "a"
                },
                "inlet_node_name": {
                    "field_name": "Inlet Node Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "zone_name",
                "zone_node_name",
                "outlet_node_name",
                "induced_air_outlet_node_or_nodelist_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "zone_name",
                    "zone_node_name",
                    "outlet_node_name",
                    "induced_air_outlet_node_or_nodelist_name"
                ],
                "extensions": [
                    "inlet_node_name"
                ]
            },
            "numerics": {
                "fields": []
            },
            "extensibles": [
                "inlet_node_name"
            ],
            "extension": "nodes"
        },
        "type": "object",
        "memo": "Connects N zone inlet air streams, through zone return plenum, to outlet (currently 500 per air loop) Node names cannot be duplicated within a single plenum list.",
        "extensible_size": 1.0
    }
}
```
