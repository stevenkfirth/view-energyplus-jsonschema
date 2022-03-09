```
{
    "AirflowNetwork:IntraZone:Linkage": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "node_1_name": {
                        "type": "string",
                        "object_list": [
                            "AirflowNetworkNodeNames",
                            "ZoneNames"
                        ],
                        "note": "Enter the name of zone or AirflowNetwork Node."
                    },
                    "node_2_name": {
                        "type": "string",
                        "object_list": [
                            "AirflowNetworkNodeNames",
                            "ZoneNames"
                        ],
                        "note": "Enter the name of zone or AirflowNetwork Node."
                    },
                    "component_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "AirflowNetworkComponentNames"
                        ],
                        "note": "Enter the name of an AirflowNetwork component. A component is one of the following AirflowNetwork:Multizone:Component objects: AirflowNetwork:MultiZone:Surface:Crack, AirflowNetwork:MultiZone:Surface:EffectiveLeakageArea, If the next field is specified, this field can be either blank or ignored."
                    },
                    "airflownetwork_multizone_surface_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "SurfAndSubSurfNames"
                        ],
                        "note": "Only used when one of two nodes defined above are not located in the same zone, and the input of the Component Name field in this object is ignored"
                    }
                },
                "required": [
                    "node_1_name",
                    "node_2_name"
                ]
            }
        },
        "group": "AirflowNetwork",
        "name": {
            "type": "string",
            "is_required": true,
            "note": "Enter a unique name for this object.",
            "reference": [
                "AirflowNetwork LinkageNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "node_1_name": {
                    "field_name": "Node 1 Name",
                    "field_type": "a"
                },
                "node_2_name": {
                    "field_name": "Node 2 Name",
                    "field_type": "a"
                },
                "component_name": {
                    "field_name": "Component Name",
                    "field_type": "a"
                },
                "airflownetwork_multizone_surface_name": {
                    "field_name": "AirflowNetwork:MultiZone:Surface Name",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "node_1_name",
                "node_2_name",
                "component_name",
                "airflownetwork_multizone_surface_name"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "node_1_name",
                    "node_2_name",
                    "component_name",
                    "airflownetwork_multizone_surface_name"
                ]
            },
            "numerics": {
                "fields": []
            }
        },
        "type": "object",
        "memo": "This object defines the connection between two nodes and a component used in the combination of RoomAir and AirflowNetwork model.",
        "min_fields": 4.0
    }
}
```
