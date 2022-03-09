```
{
    "patternProperties": {
        "^.*\\S.*$": {
            "type": "object",
            "properties": {
                "zone_name": {
                    "type": "string",
                    "note": "Name of Zone being described. Any existing zone name",
                    "data_type": "object_list",
                    "object_list": [
                        "ZoneNames"
                    ]
                },
                "control_point_roomairflownetwork_node_name": {
                    "type": "string",
                    "data_type": "object_list",
                    "object_list": [
                        "RoomAirflowNetworkNodes"
                    ]
                },
                "nodes": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "roomairflownetwork_node_name": {
                                "type": "string",
                                "data_type": "object_list",
                                "object_list": [
                                    "RoomAirflowNetworkNodes"
                                ]
                            }
                        },
                        "type": "object"
                    }
                }
            },
            "required": [
                "zone_name"
            ]
        }
    },
    "group": "Room Air Models",
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
            "zone_name": {
                "field_name": "Zone Name",
                "field_type": "a"
            },
            "control_point_roomairflownetwork_node_name": {
                "field_name": "Control Point RoomAirflowNetwork:Node Name",
                "field_type": "a"
            },
            "roomairflownetwork_node_name": {
                "field_name": "RoomAirflowNetwork:Node Name",
                "field_type": "a"
            }
        },
        "fields": [
            "name",
            "zone_name",
            "control_point_roomairflownetwork_node_name"
        ],
        "alphas": {
            "fields": [
                "name",
                "zone_name",
                "control_point_roomairflownetwork_node_name"
            ],
            "extensions": [
                "roomairflownetwork_node_name"
            ]
        },
        "numerics": {
            "fields": []
        },
        "extensibles": [
            "roomairflownetwork_node_name"
        ],
        "extension": "nodes"
    },
    "type": "object",
    "memo": "RoomAir modeling using Airflow pressure network solver",
    "min_fields": 5.0,
    "extensible_size": 1.0
}
```
