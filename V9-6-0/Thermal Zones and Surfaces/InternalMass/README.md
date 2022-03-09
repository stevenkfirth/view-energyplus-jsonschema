```
{
    "InternalMass": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "construction_name": {
                        "type": "string",
                        "note": "To be matched with a construction in this input file",
                        "data_type": "object_list",
                        "object_list": [
                            "ConstructionNames"
                        ]
                    },
                    "zone_or_zonelist_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneAndZoneListNames"
                        ],
                        "note": "Zone the surface is a part of. used to be Interior Environment"
                    },
                    "space_or_spacelist_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "SpaceAndSpaceListNames"
                        ],
                        "note": "Space the surface is a part of (optional, see description of Space object for more details). This field is ignored when a ZoneList Name is specified for Zone or ZoneList Name."
                    },
                    "surface_area": {
                        "type": "number",
                        "units": "m2",
                        "exclusiveMinimum": 0.0
                    }
                },
                "required": [
                    "construction_name",
                    "zone_or_zonelist_name",
                    "surface_area"
                ]
            }
        },
        "group": "Thermal Zones and Surfaces",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "AllHeatTranAngFacNames",
                "AllHeatTranSurfNames",
                "RadiantSurfaceNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "construction_name": {
                    "field_name": "Construction Name",
                    "field_type": "a"
                },
                "zone_or_zonelist_name": {
                    "field_name": "Zone or ZoneList Name",
                    "field_type": "a"
                },
                "space_or_spacelist_name": {
                    "field_name": "Space or SpaceList Name",
                    "field_type": "a"
                },
                "surface_area": {
                    "field_name": "Surface Area",
                    "field_type": "n"
                }
            },
            "fields": [
                "name",
                "construction_name",
                "zone_or_zonelist_name",
                "space_or_spacelist_name",
                "surface_area"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "construction_name",
                    "zone_or_zonelist_name",
                    "space_or_spacelist_name"
                ]
            },
            "numerics": {
                "fields": [
                    "surface_area"
                ]
            }
        },
        "type": "object",
        "memo": "Used to describe internal zone surface area that does not need to be part of geometric representation. This should be the total surface area exposed to the zone air. If you use a ZoneList in the Zone or ZoneList name field then this definition applies to all the zones in the ZoneList. Likewise for SpaceList."
    }
}
```
