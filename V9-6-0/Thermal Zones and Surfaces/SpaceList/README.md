```
{
    "SpaceList": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "spaces": {
                        "type": "array",
                        "items": {
                            "properties": {
                                "space_name": {
                                    "type": "string",
                                    "data_type": "object_list",
                                    "object_list": [
                                        "SpaceNames"
                                    ]
                                }
                            },
                            "type": "object",
                            "required": [
                                "space_name"
                            ]
                        }
                    }
                }
            }
        },
        "group": "Thermal Zones and Surfaces",
        "name": {
            "type": "string",
            "note": "Name of the Space List",
            "is_required": true,
            "reference": [
                "SpaceAndSpaceListNames",
                "SpaceListNames"
            ]
        },
        "additionalProperties": false,
        "legacy_idd": {
            "field_info": {
                "name": {
                    "field_name": "Name",
                    "field_type": "a"
                },
                "space_name": {
                    "field_name": "Space Name",
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
                    "space_name"
                ]
            },
            "numerics": {
                "fields": []
            },
            "extensibles": [
                "space_name"
            ],
            "extension": "spaces"
        },
        "type": "object",
        "memo": "Defines a list of Spaces which can be referenced as a group. The SpaceList name may be used elsewhere in the input to apply a parameter to all Spaces in the list. SpaceLists can be used effectively with the following objects: InternalMass, People, Lights, ElectricEquipment, GasEquipment, HotWaterEquipment, and others.",
        "min_fields": 2.0,
        "extensible_size": 1.0
    }
}
```
