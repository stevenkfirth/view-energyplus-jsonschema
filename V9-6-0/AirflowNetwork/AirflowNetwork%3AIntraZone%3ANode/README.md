```
{
    "AirflowNetwork:IntraZone:Node": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "roomair_node_airflownetwork_name": {
                        "type": "string",
                        "object_list": [
                            "RoomAirflowNetworkNodes"
                        ],
                        "note": "Enter the name of a RoomAir:Node object defined in a RoomAirSettings:AirflowNetwork object."
                    },
                    "zone_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "AirFlowNetworkMultizoneZones"
                        ],
                        "note": "Enter the name of a zone object defined in a AirflowNetwork:MultiZone:Zone object."
                    },
                    "node_height": {
                        "type": "number",
                        "units": "m",
                        "default": 0.0,
                        "note": "Enter the reference height used to calculate the relative pressure"
                    }
                },
                "required": [
                    "roomair_node_airflownetwork_name",
                    "zone_name"
                ]
            }
        },
        "group": "AirflowNetwork",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "AirflowNetworkNodeNames"
            ],
            "note": "Enter a unique name for this object."
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "roomair_node_airflownetwork_name": {
                    "field_name": "RoomAir:Node:AirflowNetwork Name",
                    "field_type": "a"
                },
                "zone_name": {
                    "field_name": "Zone Name",
                    "field_type": "a"
                },
                "node_height": {
                    "field_name": "Node Height",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "roomair_node_airflownetwork_name",
                "zone_name",
                "node_height"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "roomair_node_airflownetwork_name",
                    "zone_name"
                ]
            },
            "numerics": {
                "fields": [
                    "node_height"
                ]
            }
        },
        "type": "object",
        "memo": "This object represents a node in a zone in the combination of RoomAir and AirflowNetwork model.",
        "min_fields": 2.0
    }
}
```
