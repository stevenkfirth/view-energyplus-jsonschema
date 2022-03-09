```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "outlet_node_name": {
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
                "outlet_node_name"
            ]
        }
    },
    "group": "Air Distribution",
    "name": {
        "type": "string",
        "is_required": true,
        "reference": [
            "AirLoopHVACMixerNames"
        ]
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "outlet_node_name": {
                "field_name": "Outlet Node Name",
                "field_type": "a"
            },
            "inlet_node_name": {
                "field_name": "Inlet Node Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "outlet_node_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "outlet_node_name"
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
    "memo": "Mix N inlet air streams from Relief Air Stream Node in OutdoorAir:Mixer objects served by AirLoopHVAC objects listed in AirLoopHVAC:DedicatedOutdoorAirSystem into one (currently 10 as default, but extensible). Node names cannot be duplicated within a single mixer list.",
    "extensible_size": 1.0
}
```
