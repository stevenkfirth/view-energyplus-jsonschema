```
{
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
                "inlet_node_name": {
                    "type": "string"
                },
                "nodes": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "outlet_node_name": {
                                "type": "string"
                            }
                        },
                        "type": "object",
                        "required": [
                            "outlet_node_name"
                        ]
                    }
                }
            },
            "required": [
                "zone_name",
                "zone_node_name",
                "inlet_node_name"
            ]
        }
    },
    "group": "Air Distribution",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "SupplyPathComponentNames"
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
            "inlet_node_name": {
                "field_name": "Inlet Node Name",
                "field_type": "a"
            },
            "outlet_node_name": {
                "field_name": "Outlet Node Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "zone_name",
            "zone_node_name",
            "inlet_node_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "zone_name",
                "zone_node_name",
                "inlet_node_name"
            ],
            "extensions": [
                "outlet_node_name"
            ]
        },
        "numerics": {
            "fields": []
        },
        "extensibles": [
            "outlet_node_name"
        ],
        "extension": "nodes"
    },
    "type": "object",
    "memo": "Connects 1 zone inlet air stream, through zone supply plenum, to one or more outlets. Node names cannot be duplicated within a single supply plenum list.",
    "extensible_size": 1.0
}
```
