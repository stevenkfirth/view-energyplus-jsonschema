```
{
    "ZoneProperty:LocalEnvironment": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "zone_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ],
                        "note": "Enter the name of a zone object"
                    },
                    "outdoor_air_node_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "OutdoorAirNodeNames"
                        ],
                        "note": "Enter the name of an OutdoorAir:Node object"
                    }
                }
            }
        },
        "group": "Advanced Construction, Surface, Zone Concepts",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "ZoneLocalEnvironmentNames"
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
                "outdoor_air_node_name": {
                    "field_name": "Outdoor Air Node Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "zone_name",
                "outdoor_air_node_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "zone_name",
                    "outdoor_air_node_name"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "memo": "This object defines the local environment properties of a zone object. A corresponding outdoor air node should be defined and linked to the zone object.",
        "min_fields": 3.0
    }
}
```
