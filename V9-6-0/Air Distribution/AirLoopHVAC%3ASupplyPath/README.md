```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "supply_air_path_inlet_node_name": {
                    "type": "string"
                },
                "components": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "component_object_type": {
                                "type": "string",
                                "note": "Supply path components must be listed in flow order.",
                                "enum": [
                                    "AirLoopHVAC:SupplyPlenum",
                                    "AirLoopHVAC:ZoneSplitter"
                                ]
                            },
                            "component_name": {
                                "type": "string",
                                "data_type": "object_list",
                                "object_list": [
                                    "SupplyPathComponentNames"
                                ]
                            }
                        },
                        "type": "object",
                        "required": [
                            "component_name",
                            "component_object_type"
                        ]
                    }
                }
            },
            "required": [
                "supply_air_path_inlet_node_name"
            ]
        }
    },
    "group": "Air Distribution",
    "name": {
        "type": "string",
        "is_required": true
    },
    "additionalProperties": false,
    "legacy_idd": {
        "field_info": {
            "name": {
                "field_name": "Name",
                "field_type": "a"
            },
            "supply_air_path_inlet_node_name": {
                "field_name": "Supply Air Path Inlet Node Name",
                "field_type": "a"
            },
            "component_object_type": {
                "field_name": "Component Object Type",
                "field_type": "a"
            },
            "component_name": {
                "field_name": "Component Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "supply_air_path_inlet_node_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "supply_air_path_inlet_node_name"
            ],
            "extensions": [
                "component_object_type",
                "component_name"
            ]
        },
        "numerics": {
            "fields": []
        },
        "extensibles": [
            "component_object_type",
            "component_name"
        ],
        "extension": "components"
    },
    "type": "object",
    "memo": "A supply path can only contain AirLoopHVAC:ZoneSplitter and AirLoopHVAC:SupplyPlenum objects which may be in series or parallel.",
    "extensible_size": 2.0
}
```
