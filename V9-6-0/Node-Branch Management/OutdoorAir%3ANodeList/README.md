```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "nodes": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "node_or_nodelist_name": {
                                "type": "string"
                            }
                        },
                        "type": "object",
                        "required": [
                            "node_or_nodelist_name"
                        ]
                    }
                }
            }
        }
    },
    "group": "Node-Branch Management",
    "legacy_idd": {
        "field_info": {
            "node_or_nodelist_name": {
                "field_name": "Node or NodeList Name",
                "field_type": "a"
            }
        },
        "fields": [],
        "alphas": {
            "fields": [],
            "extensions": [
                "node_or_nodelist_name"
            ]
        },
        "numerics": {
            "fields": []
        },
        "extensibles": [
            "node_or_nodelist_name"
        ],
        "extension": "nodes"
    },
    "type": "object",
    "memo": "This object sets the temperature and humidity conditions for an outdoor air node using the weather data values. to vary outdoor air node conditions with height above ground use OutdoorAir:Node instead of this object. This object may be used more than once. The same node name may not appear in both an OutdoorAir:Node object and an OutdoorAir:NodeList object.",
    "extensible_size": 1.0
}
```
