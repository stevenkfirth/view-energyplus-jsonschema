```
{
    "RoomAir:Node:AirflowNetwork:AdjacentSurfaceList": {
        "patternProperties": {
            ".*": {
                "type": "object",
                "properties": {
                    "surfaces": {
                        "type": "array",
                        "items": {
                            "properties": {
                                "surface_name": {
                                    "type": "string",
                                    "data_type": "object_list",
                                    "object_list": [
                                        "AllHeatTranSurfNames"
                                    ]
                                }
                            },
                            "type": "object"
                        }
                    }
                }
            }
        },
        "group": "Room Air Models",
        "name": {
            "type": "string",
            "reference": [
                "RoomAirNodeSurfaceLists"
            ]
        },
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "surface_name": {
                    "field_name": "Surface Name",
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
                    "surface_name"
                ]
            },
            "numerics": {
                "fields": []
            },
            "extensibles": [
                "surface_name"
            ],
            "extension": "surfaces"
        },
        "type": "object",
        "min_fields": 2.0,
        "extensible_size": 1.0
    }
}
```
