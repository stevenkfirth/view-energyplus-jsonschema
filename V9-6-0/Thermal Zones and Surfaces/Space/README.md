```
{
    "Space": {
        "patternProperties": {
            "^.*\\S.*$": {
                "type": "object",
                "properties": {
                    "zone_name": {
                        "type": "string",
                        "data_type": "object_list",
                        "object_list": [
                            "ZoneNames"
                        ]
                    },
                    "floor_area": {
                        "note": "If this field is 0.0, negative or autocalculate, then the floor area of the space is automatically calculated and used in subsequent calculations. If this field is positive, then the number entered here will be used.",
                        "units": "m2",
                        "default": "Autocalculate",
                        "anyOf": [
                            {
                                "type": "number"
                            },
                            {
                                "type": "string",
                                "enum": [
                                    "",
                                    "Autocalculate"
                                ]
                            }
                        ]
                    },
                    "space_type": {
                        "type": "string",
                        "note": "Space type is used to tag spaces by activity type, such as office, classroom, storage, etc.",
                        "default": "General"
                    },
                    "tags": {
                        "type": "array",
                        "items": {
                            "properties": {
                                "tag": {
                                    "type": "string",
                                    "note": "Optional reporting tag"
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
        "group": "Thermal Zones and Surfaces",
        "name": {
            "type": "string",
            "is_required": true,
            "reference": [
                "SpaceAndSpaceListNames",
                "SpaceNames"
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
                "floor_area": {
                    "field_name": "Floor Area",
                    "field_type": "n"
                },
                "space_type": {
                    "field_name": "Space Type",
                    "field_type": "a"
                },
                "tag": {
                    "field_name": "Tag",
                    "field_type": "a"
                }
            },
            "fields": [
                "name",
                "zone_name",
                "floor_area",
                "space_type"
            ],
            "alphas": {
                "fields": [
                    "name",
                    "zone_name",
                    "space_type"
                ],
                "extensions": [
                    "tag"
                ]
            },
            "numerics": {
                "fields": [
                    "floor_area"
                ]
            },
            "extensibles": [
                "tag"
            ],
            "extension": "tags"
        },
        "type": "object",
        "memo": "Defines a space (room) in the building. All Spaces are part of a Zone. Every Zone contains one or more spaces. Space is an optional input. If a Zone has no Space(s) specified in input then a default Space named <Zone Name> will be created. If some surfaces in a Zone are assigned to a space and some are not, then a default Space named <Zone Name>-Remainder will be created.  Input references to Space Names must have a matching Space object (default space names may not be referenced except in output variable keys).",
        "min_fields": 3.0,
        "extensible_size": 1.0
    }
}
```
