```
{
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
            "AirLoopHVACSplitterNames"
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
    "memo": "Split one air stream from AirLoopHVAC:DedicatedOutdoorAirSystem outlet node into N outlet streams (currently 10 as default, but extensible). Node names should be Outdoor Air Stream Node Name in OutdoorAir:Mixer objects served by AirLoopHVAC objects listed in AirLoopHVAC:DedicatedOutdoorAirSystem.",
    "extensible_size": 1.0
}
```
