```
{
    "NodeList": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "nodes": {
                        "type": "array",
                        "items": {
                            "properties": {
                                "node_name": {
                                    "type": "string"
                                }
                            },
                            "type": "object",
                            "required": [
                                "node_name"
                            ]
                        }
                    }
                }
            }
        },
        "group": "Node-Branch Management",
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
                "node_name": {
                    "field_name": "Node Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name"
            ],
            "alphas": {
                "fields": [
                    "name"
                ],
                "extensions": [
                    "node_name"
                ]
            },
            "numerics": {
                "fields": []
            },
            "extensibles": [
                "node_name"
            ],
            "extension": "nodes"
        },
        "type": "object",
        "memo": "This object is used in places where lists of nodes may be needed, e.g. ZoneHVAC:EquipmentConnections field Zone Air Inlet Node or NodeList Name",
        "min_fields": 2.0,
        "extensible_size": 1.0
    }
}
```
