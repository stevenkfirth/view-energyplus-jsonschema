```
{
    "patternProperties": {
        ".*": {
            "type": "object",
            "properties": {
                "zone_or_zonelist_or_space_or_spacelist_name": {
                    "type": "string",
                    "note": "View factors may be entered for a space, zone, group of spaces, or group of zones in the same enclosure by way of Constructon:AirBoundary or open spaces within a zone. This name must align with an enclosure encompassing the same zones or spaces.",
                    "data_type": "object_list",
                    "object_list": [
                        "SpaceListNames",
                        "SpaceNames",
                        "ZoneListNames",
                        "ZoneNames"
                    ]
                },
                "view_factors": {
                    "type": "array",
                    "items": {
                        "properties": {
                            "from_surface": {
                                "type": "string",
                                "data_type": "object_list",
                                "object_list": [
                                    "AllHeatTranSurfNames"
                                ]
                            },
                            "to_surface": {
                                "type": "string",
                                "data_type": "object_list",
                                "object_list": [
                                    "AllHeatTranSurfNames"
                                ]
                            },
                            "view_factor": {
                                "type": "number",
                                "note": "This value is the view factor value From Surface => To Surface",
                                "maximum": 1.0
                            }
                        },
                        "type": "object"
                    }
                }
            }
        }
    },
    "group": "Advanced Construction, Surface, Zone Concepts",
    "legacy_idd": {
        "field_info": {
            "zone_or_zonelist_or_space_or_spacelist_name": {
                "field_name": "Zone or ZoneList or Space or SpaceList Name",
                "field_type": "a"
            },
            "from_surface": {
                "field_name": "From Surface",
                "field_type": "a"
            },
            "to_surface": {
                "field_name": "To Surface",
                "field_type": "a"
            },
            "view_factor": {
                "field_name": "View Factor",
                "field_type": "n"
            }
        },
        "fields": [
            "zone_or_zonelist_or_space_or_spacelist_name"
        ],
        "alphas": {
            "fields": [
                "zone_or_zonelist_or_space_or_spacelist_name"
            ],
            "extensions": [
                "from_surface",
                "to_surface"
            ]
        },
        "numerics": {
            "fields": [],
            "extensions": [
                "view_factor"
            ]
        },
        "extensibles": [
            "from_surface",
            "to_surface",
            "view_factor"
        ],
        "extension": "view_factors"
    },
    "type": "object",
    "memo": "View factors for Surface to Surface in a zone. (Number of Surfaces)**2 are expected. Any omitted surface pairs will be assumed to have a view factor of zero.",
    "extensible_size": 3.0,
    "format": "ViewFactor"
}
```
