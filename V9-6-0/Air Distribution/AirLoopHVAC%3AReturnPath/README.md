```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "return_air_path_outlet_node_name": {
                    "type": "string"
                },
                "components": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "component_object_type": {
                                "type": "string",
                                "enum": [
                                    "AirLoopHVAC:ReturnPlenum",
                                    "AirLoopHVAC:ZoneMixer"
                                ]
                            },
                            "component_name": {
                                "type": "string",
                                "data_type": "object_list",
                                "object_list": [
                                    "ReturnPathComponentNames"
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
                "return_air_path_outlet_node_name"
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
            "return_air_path_outlet_node_name": {
                "field_name": "Return Air Path Outlet Node Name",
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
            "return_air_path_outlet_node_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "return_air_path_outlet_node_name"
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
    "memo": "A return air path can only contain one AirLoopHVAC:ZoneMixer and one or more AirLoopHVAC:ReturnPlenum objects.",
    "extensible_size": 2.0
}
```
