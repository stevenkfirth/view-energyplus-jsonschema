```
{
    "AirLoopHVAC:ZoneSplitter": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
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
                "inlet_node_name"
            ],
            "alphas": {
                "fields": [
                    "name",
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
        "memo": "Split one air stream into N outlet streams (currently 500 per air loop, but extensible). Node names cannot be duplicated within a single zone splitter (AirLoopHVAC:ZoneSplitter) list.",
        "extensible_size": 1.0
    }
}
```
