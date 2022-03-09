```
{
    "RoomAir:Node:AirflowNetwork": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "zone_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ]
                    },
                    "fraction_of_zone_air_volume": {
                        "type": "number",
                        "minimum": 0.0,
                        "maximum": 1.0
                    },
                    "roomair_node_airflownetwork_adjacentsurfacelist_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "RoomAirNodeSurfaceLists"
                        ]
                    },
                    "roomair_node_airflownetwork_internalgains_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "RoomAirNodeGains"
                        ]
                    },
                    "roomair_node_airflownetwork_hvacequipment_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "RoomAirNodeHVACEquipment"
                        ]
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
            "reference": [
                "RoomAirflowNetworkNodes"
            ]
        },
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
                "fraction_of_zone_air_volume": {
                    "field_name": "Fraction of Zone Air Volume",
                    "field_type": "n"
                },
                "roomair_node_airflownetwork_adjacentsurfacelist_name": {
                    "field_name": "RoomAir:Node:AirflowNetwork:AdjacentSurfaceList Name",
                    "field_type": "a"
                },
                "roomair_node_airflownetwork_internalgains_name": {
                    "field_name": "RoomAir:Node:AirflowNetwork:InternalGains Name",
                    "field_type": "a"
                },
                "roomair_node_airflownetwork_hvacequipment_name": {
                    "field_name": "RoomAir:Node:AirflowNetwork:HVACEquipment Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "zone_name",
                "fraction_of_zone_air_volume",
                "roomair_node_airflownetwork_adjacentsurfacelist_name",
                "roomair_node_airflownetwork_internalgains_name",
                "roomair_node_airflownetwork_hvacequipment_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "zone_name",
                    "roomair_node_airflownetwork_adjacentsurfacelist_name",
                    "roomair_node_airflownetwork_internalgains_name",
                    "roomair_node_airflownetwork_hvacequipment_name"
                ]
            },
            "numerics": {
                "fields": [
                    "fraction_of_zone_air_volume"
                ]
            }
        },
        "type": "object",
        "memo": "define an air node for some types of nodal air models"
    }
}
```
